# UNOCHA Front end style guide

This site is an evolving list of components and resources for OCHA websites.

The guide is a living document created to meet the needs of OCHA's developers and designers. If you have any feedback, questions or comment please contact digitalservices@humanitarianresponse.info.

## Contents

### Common Design

The [Common Design](https://un-ocha.github.io/styleguide/common-design) is a unified design system for OCHA platforms.

### OCHA Basic Drupal Theme

[OCHA Basic](https://un-ocha.github.io/styleguide/ocha) is a minimal starter theme for Drupal incorporating the Common Design header and footer.

### Individual website component libraries

The individual component libraries are intended to document the front end for the project.

[Humanitarian ID component library & guidelines](https://un-ocha.github.io/styleguide/hid)

[ReliefWeb component library & guidelines](https://un-ocha.github.io/styleguide/reliefweb)

### Shared libraries

[Icon library](https://un-ocha.github.io/styleguide/icons)

## Related links

[OCHA Basic Drupal Theme](https://github.com/UN-OCHA/ocha_basic)

[UNOCHA Graphics Style Book (pdf)](https://www.unocha.org/sites/unocha/files/dms/Documents/GraphicsStyleBook_for_public.pdf)

## Running locally

This site uses Jekyll. See [https://jekyllrb.com](https://jekyllrb.com) for Jekyll docs.

### Requirements

* [Ruby](https://www.ruby-lang.org/en/)
* [Bundler](http://bundler.io/)
* [Node](https://nodejs.org/)
* [Jekyll](https://jekyllrb.com)
* [Gulp](https://gulpjs.com)

### Clone the repo

```
git clone git@github.com:UN-OCHA/styleguide.git
```

### Install the required gems

```
rvm use
bundle install
```

If you run into issues installing `nokogiri` try following the package installation/upgrade commands for your system in this [nokogiri GitHub issue](https://github.com/sparklemotion/nokogiri/issues/1099).

### Install the front end dependencies

```
nvm use
npm install
```

### Local development

Get a full command listing:

```
gulp help
```

Run the site in development mode. It will compile everything (including Jekyll), launch [browser-sync](https://browsersync.io) for multi-device testing, and watch the filesystem for new changes:

```
gulp dev
```

Default URL is http://localhost:4000/

### Jekyll

There's a local config file `docs/_config.dev.yml` which upon completing `npm install` should be ignored by version control. You can add any local-specific Jekyll config there for testing, and leave `_config.yml` for production values.

If we ever want to set defaults in the dev config run the following command to allow git to "notice" the changes, commit them, then just run `npm i` to reset the working tree so that the file will continue being ignored.

```
# https://stackoverflow.com/a/43535767/175551
git update-index --no-skip-worktree docs/_config.dev.yml
```

### CSS & Sass

Gulp is used to generate CSS from Sass. You should use `gulp dev` as an all-in-one command, but here are a few single commands you might also find useful:

`gulp dev:sass` will generate:

* OCHA Basic extras styles (`gulp dev:sass:ochaextras`)
* Common Design styles (`gulp dev:sass:commondesign`)
* Styleguide styles (`gulp dev:sass:styleguide`)

### Deployment

There are sourcemaps included for developer convenience, but they should be excluded when finalizing changes. There is an npm task that allows a "production" compile to run, which then presents the changes for review:

```
npm run deploy
```

### Individual project CSS

#### ReliefWeb

The ReliefWeb section uses styles copied from the ReliefWeb repository.

Run `npm run update-rw-assets` to update the ReliefWeb assets (assumes you have the ReliefWeb code at /srv/rwint/data/code/).

#### HID assets

The HID section uses styles from the HID staging site.

#### OCHA Basic assets

The OCHA Basic section uses styles from the OCHA Basic github repo.
