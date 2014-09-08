# Ghostdown - A Markdown editor with live preview

Live demo:  http://ghostdown.meteor.com

This is a demo of [my Ghostdown package](https://github.com/jshimko/meteor-ghostdown) for Meteor.  It was created by simply doing:

`meteor create APPNAME`

and 

`meteor add jeremy:ghostdown`

The only code added for the demo was some base markup in `ghostdown.html` that surrounds the `{{> GhostEditor}}` template from the package.  It looks like this:

```html
<main class="editor">
    <section class="entry-container">
        <header>
            <section class="box entry-title">
                <input id="entry-title" class="" placeholder="Your Post Title" tabindex="1" type="text">
            </section>
        </header>
        {{> GhostEditor}}
    </section>
</main>
```

and then finally, I added and compiled [the SCSS from the Ghost UI repo](https://github.com/TryGhost/Ghost-UI/tree/master/sass) to give some base styling.


## Development

If you'd like to use this demo as a starting point for a Markdown editor, note that Ghost-UI uses [Bourbon](http://bourbon.io) mixins in the SCSS.  To make this easier, I created a Compass [config](https://github.com/jshimko/meteor-ghostdown-demo/blob/master/client/scss/config.rb) to import Bourbon (via the gem) as well as to give a place to configure CSS complilation settings.  To edit and compile the SCSS, you will need to satisfy a few dependencies on your development machine first.  (Note that the compass-notify gem is only included so there are nicer notifications on each `compass compile`.  It is entirely optional.)

To get started:

```
git clone https://github.com/jshimko/meteor-ghostdown-demo.git

cd meteor-ghostdown-demo

meteor
```

To add/edit styles, open another terminal window, install dependencies, and start Compass:

```
gem install compass compass-notify bourbon

cd client/scss/

compass watch
```

Add/edit and save SCSS files and you'll get live reload every time Meteor sees a change to the compiled `client/css/screen.css`.
