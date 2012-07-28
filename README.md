fancybox-rails
==============

[![Build Status](http://travis-ci.org/hecticjeff/fancybox-rails.png)](http://travis-ci.org/hecticjeff/fancybox-rails)

Use [fancybox](http://www.fancyapps.com/fancybox/) with rails 3.1 asset pipeline.

## Installation

This gem vendors jquery fancybox 2 for Rails 3.1 and greater. The files
will be added to the asset pipeline and available for you to use.

First add the following lines to your applications `Gemfile`:

``` ruby
gem 'jquery-rails'
gem 'fancybox-rails'
```

Then run `bundle install` to update your application's bundle.

Now you need to edit your `app/assets/javascripts/application.js`
file and add the following line:

``` javascript
//= require jquery
//= require fancybox
```

And then edit your `app/assets/stylesheets/application.css` file to
look something like:

``` css
/*
 *= require_self
 *= require fancybox
 *= require_tree .
 */
```

That's it!

## Usage

This gem initializes fancybox based on the data attribute "data-fancybox".
This allows you to use fancybox out of the box like this:

``` <%= link_to "fancybox test", '#content_div', data: { fancybox: true } %> ```

You can also do more sophisticated things with fancybox 2, such as setting
the content type. For example, for an AJAX request:

``` <%= link_to "fancybox ajax test", 'ajax_url', data: { fancybox: true, fancybox_type: 'ajax' } %> ```

However, you can still use fancybox as you might otherwise wish. For example,
based on a class:

``` javascript
$(document).ready(function() {
  $("a.fancybox").fancybox();
});
```

See the fancybox Web site for more detailed usage documentation.

## More information

* [Contributors](https://github.com/hecticjeff/fancybox-rails/contributors)
* [DHH's RailsConf 2011 talk on the rails 3.1 asset pipeline](http://www.youtube.com/watch?v=cGdCI2HhfAU)

Copyright (c) Chris Mytton

## License

[Fancybox 2 license](http://www.fancyapps.com/fancybox/#license)