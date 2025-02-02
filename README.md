# Mixpanel API Client (for API version 2.0)

Ruby access to the [Mixpanel](http://mixpanel.com/) web analytics tool.

[Mixpanel Data API Reference](http://mixpanel.com/api/docs/guides/api/v2)

## Installation

    gem install mixpanel_client
    
or if you use a Gemfile

    gem 'mixpanel_client'

## Usage

    require 'rubygems'
    require 'mixpanel_client'

    config = {'api_key' => 'changeme', 'api_secret' => 'changeme'}
    client = Mixpanel::Client.new(config)

    data = client.request do
      # Available options
      resource  'events/properties'
      event     '["test-event"]'
      name      'hello'
      values    '["uno", "dos"]'
      timezone  '-8'
      type      'general'
      unit      'hour'
      interval   24
      limit      5
      bucket    'contents'
      from_date '2011-08-11'
      to_date   '2011-08-12'
      on        'properties["product_id"]'
      where     '1 in properties["product_id"]'
      buckets   '5'
    end

    puts data.inspect

## Changelog

### 2.0.2
 * Added timezone to available options.
 * All exceptions can be caught under Mixpanel::Error.

### 2.0.1
 * Added options used in segmentation resources.

### 2.0.0
 * Manually tested compatibility with Mixpanel gem. 

### 2.0.0.beta2
 * Added JSON to gemspec for ruby versions less than 1.9.

### 2.0.0.beta1
 * Reverted to namespacing via module name because it's a better practice.
   I.e. Use `Mixpanel::Client` instead of `MixpanelClient`.
 * Added 'values' as an optional parameter
 * `gem install mixpanel_client --pre`

### 1.0.1
 * Minor housekeeping and organizing
 * Refactored specs

### 1.0.0
 * Changed "Mixpanel" class name to "MixpanelClient" to prevent naming collision in other 
   libraries. [a710a84e8ba4b6f018b7](https://github.com/keolo/mixpanel_client/commit/a710a84e8ba4b6f018b7404ab9fabc8f08b4a4f3)

## Collaborators and Maintainers
[Keolo Keagy](http://github.com/keolo) (Author)  
[Jason Logsdon](https://github.com/jasonlogsdon)  
[James R](https://github.com/Cev)  
[Mike Ferrier](http://github.com/mferrier)  
[Mike Ferrier](http://github.com/mferrier)  
[Grzegorz Forysinski](http://github.com/railwaymen)  
[Nathan Chong](http://github.com/paramaw)  
[Paul McMahon](http://github.com/pwim)  
[Chad Etzel](http://github.com/jazzychad)

## Copyright

Copyright (c) 2009+ Keolo Keagy. See LICENSE for details.
