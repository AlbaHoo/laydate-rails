# Demo
![demo](./demo-images/all.png?raw=true)


# laydate-rails

Another date time picker JS plugin, trust me, it's simple to to use and looks ready nice.

This is simply a wrapper on top of the awesome npm package [laydate](https://www.layui.com/laydate/) so it could be used easily in rails applications.

Laydate team did an awesome job so there is no dependency on either jQuery or bootstrap, all by itself.

**Why this Gem**: My original plan was just to use npm/yarn to manage it in my rails application, but with one issue, the npm package loads css in the js by relative path, so you only need to include the js src in html, which is great in some cases. And this works great in my development env as well, but in rails production all are compiled into one simple js/css file, it breaks the relative path of css and fonts as well, anyway, the gem seems to work.

## Installation

Add this line to your application's Gemfile:

```ruby
gem 'laydate-rails'
```

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install laydate-rails

## Usage

Add `#= require laydate` to your `app/assets/javascripts/application.js(.coffee)`, if you are using ActiveAdmin like me, just add it to `app/assets/javascripts/active_admin.js.coffee`;

Add `@import "laydate-rails";` to your `app/assets/stylesheets/application.scss`, Note: `app/assets/stylesheets/active_admin.scss` for AA project;

If you don't have `application.scss`, try rename your `applications.css` file;

    mv app/assets/stylesheets/application.css app/assets/stylesheets/application.scss

You are all set

## Examples
The full API documents link: https://www.layui.com/laydate/

Basic:

html:
```
<input type="text" id="test1">
```

js:
```
laydate.render({
  elem: '#test1', // element selector
  lang: 'en' // default is Chinese version, use en for english
});
```

Advanced:

html:
```
<input type="text" id="test1">
```

js:
```
laydate.render({
  elem: '#test1',
  lang: 'en',
  type: 'date' | 'time' | 'datetime',
  range: true,
  done: afterDone, // function
  change: afterChange, // function
  theme: '#393D49', // change color if you want
  showBottom: false, // if you want to show clear/Today/confirm buttons
  value: '1989-10-14' // default value
  min: '2016-10-14',
  max: '2080-10-14'
});
```

There are many other options too, reference to the official document for more infomations;

## Contributing

Bug reports and pull requests are welcome on GitHub at https://github.com/AlbaHoo/laydate-rails.

## License

The gem is available as open source under the terms of the [MIT License](https://opensource.org/licenses/MIT).
