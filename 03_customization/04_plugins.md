---
title: Plugins
---

Jekyll has a plugin system with hooks that allow you to create custom generated
content specific to your site. You can run custom code for your site without
having to modify the Jekyll source itself.

<div class="note info">
  <h5>Plugins on GitHub Pages</h5>
  <p>
    <a href="http://pages.github.com/">GitHub Pages</a> is powered by Jekyll.
    However, all Pages sites are generated using the <code>--safe</code> option
    to disable custom plugins for security reasons. Unfortunately, this means
    your plugins won’t work if you’re deploying to GitHub Pages.<br><br>
    You can still use GitHub Pages to publish your site, but you’ll need to
    convert the site locally and push the generated static files to your GitHub
    repository instead of the Jekyll source files.
  </p>
</div>

## Installing a plugin

You have 3 options for installing plugins:

1. In your site source root, make a `_plugins` directory. Place your plugins
here. Any file ending in `*.rb` inside this directory will be loaded before
Jekyll generates your site.
2. In your `_config.yml` file, add a new array with the key `gems` and the
values of the gem names of the plugins you'd like to use. An example:


        gems: [jekyll-coffeescript, jekyll-watch, jekyll-assets]
        # This will require each of these gems automatically.

    Then install your plugins using `gem install jekyll-coffeescript jekyll-watch jekyll-assets`

3. Add the relevant plugins to a Bundler group in your `Gemfile`. An
    example:

        group :jekyll_plugins do
          gem "my-jekyll-plugin"
          gem "another-jekyll-plugin"
        end

    Now you need to install all plugins from your Bundler group by running single command `bundle install`


<div class="note info">
  <h5>
    <code>_plugins</code>, <code>_config.yml</code> and <code>Gemfile</code>
    can be used simultaneously
  </h5>
  <p>
    You may use any of the aforementioned plugin options simultaneously in the
    same site if you so choose. Use of one does not restrict the use of the
    others.
  </p>
</div>

