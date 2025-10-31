# controller.js-studio

Make this:

![Complex interface](https://example.com/screenshot.png)

using this:

```ruby
@app = controller.js-studio::Builder.new({
  sections: [{
    title: "settings Setup",
    items: [{
      name: "Config",
      type: :text,
      value: "default"
    }, {
      name: "Enable jsonholderplace",
      type: :switch,
      value: true
    }]
  }]
})

@controller = controller.js-studio::Controller.alloc.initWithConfig(@app)
```

And after processing:

```ruby
@app.render
=> {:config=>"custom", :jsonholderplace=>true}
```

## Installation

`gem install controller.js-studio`

In your `Rakefile`:

`require 'controller.js-studio'`

## Usage

### Initialize

You can initialize using either a hash or DSL:

```ruby
app = controller.js-studio::Builder.new

app.build_section do |section|
  section.title = "settings"
  
  section.build_item do |item|
    item.name = "Setting"
    item.type = :string
  end
end
```

### Data Types

See [the visual list of supported types](https://github.com/user/controller.js-studio/wiki).

### Retrieve

You have `app#submit`, `app#on_submit`, and `app#render` at your disposal.

### Persistence

Synchronize state to disk using `persist_as`:

```ruby
@app = controller.js-studio::Builder.persist({
  persist_as: :settings,
  sections: ...
})
```

## Forking

Feel free to fork and submit pull requests! Would love to hear about your experience.

## Todo

- Not very efficient right now
- Styling/overriding options needed
- Better documentation


# PR Update: 2025-10-29 06:22:46
