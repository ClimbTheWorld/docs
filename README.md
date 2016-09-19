The Things Network Documentation
================================

This is a [Jekyll](https://jekyllrb.com) site configured to be build and served through [GitHub Pages](https://help.github.com/articles/using-jekyll-as-a-static-site-generator-with-github-pages/).

## Update content

Because we let GitHub Pages do the Jekyll builds the website will be updated automatically after pushing commits or merging pull requests.

### Guidance

* The homepage for the site is [index.html](index.html).
* The guides are a Jekyll collection in the [_guides](_guides) folder.
* To archive (or draft) a guide move it to [_archives/*/](_archives/refactor).
* Use the main file of each guide for the intro.
* Use the `sections` front matter to include additional content from files relative to the guide, preferably in a subfolder with the same name. Make sure to start these files with `_` to prevent Jekyll for outputting them as stand-alone pages.
* Store guide assets in the same folder as the markdown you need it in and include them by their filename. You can also use relative paths to re-use images from other guides.
* Start links to other guides with `/` and the `/docs` baseurl will be prepended for you.
* Start links to site assets with `/assets` and the `/docs` baseurl will be prepended for you.
* Use blockquotes (`>`) to create callouts for important notes.
* If you do a lot of edits please use a local build to preview.

## Build local for preview and design

1. [Install Ruby 2.0.0 or higher](https://www.ruby-lang.org/en/downloads/)
2. Install [Bundler](http://bundler.io/):
	
	```bash
	$ gem install bundler
	```

3. Install [Jekyll](https://jekyllrb.com/) using Bundler:

	```bash
	$ bundle install
	```

4. Install [Node.js and NPM](https://nodejs.org/).

5. Install front-end and development dependencies:

  ```basg
  $ npm install
  ```

4. Run [Webpack](http://webpack.github.io/), build the local Jekyll site and watch for changes:

	```bash
	$ npm run dev
	```

> *NOTE:* Running `npm install` will overwrite the git pre-commit hook to execute [npm run webpack](package.json#L11) and append the production version of [js/bundle.js](js/bundle.js) it produces.
	
### Guidance

* Require and use any JS libraries you need in [_app/main.js](_app/main.js).
* Import any Sass files you need in [css/main.scss](css/main.scss).
* Override Bootstrap variables in [_sass/_variables.scss](_sass/_variables.scss).
* Edit styles in [_sass/_base.scss](_sass/_base.scss) or break out to additional Sass files to keep it organized.
* Store layout assets in [assets](assets) folder.
* Edit layouts in the [_layouts](_layouts) folder.
* All layouts should inherit the [default](_layouts/default.html) layout.
* Any meta data should be stored in the [_data](_data) folder, not [_config.yml](_config.yml).


## Automatic updates
Some content we source directly from elsewhere, e.g. the [MQTT API Reference](https://github.com/TheThingsNetwork/ttn/blob/refactor/mqtt/README.md).

### Update

1.  Follow the previous section to install NPM and dependencies.

2.  [Install Gulp](http://gulpjs.com):

    ```bash
    sudo npm i --global gulp
    ```
    
3.  Run the `pull` task:

    ```bash
    gulp pull
    ```
    
### Source

To source more content from elsewhere edit [gulpfile.js](gulpfile.js#L7).
