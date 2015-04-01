# Digital Marketplace front-end toolkit

A toolkit for CSS used across Digital Marketplace projects.

## Documentation

The documentation can be accessed at [http://alphagov.github.io/digitalmarketplace-frontend-toolkit/](http://alphagov.github.io/digitalmarketplace-frontend-toolkit/).

### Static assets

The pages use `pages` as the root directory so you can include any assets from `/pages/public/javascripts` or `/pages/public/images` directly. If `pages` is not your root directory then you need to set the path to
'pages' in an environment variable, eg: `ROOT_DIRECTORY='/digitalmarketplace-frontend-toolkit'`

### Example markup

Example markup can be found in the `./pages_builder/pages` folder. It is used to generate the example pages for documentation into the './pages' folder.

## Generating the documentation pages

The documentation pages can be generated by following these steps.

### Requirements

- Python
- [PIP](https://pip.pypa.io/en/latest/)
- [virtualenv](https://virtualenv.pypa.io/en/latest/)

### Set up a virtualenv

To set up an isolated environment for the project, run these commands:

```
virtualenv ~/Envs/digitalmarketplace-frontend_toolkit
source ~/Envs/digitalmarketplace-frontend_toolkit/bin/activate
```

*Note*: you can set the virtualenv to any location on your system by swapping out `~/Envs/digitalmarketplace-frontend_toolkit` to your choice of folder.

### Install the dependancies

```
pip install -r ./pages_builder/requirements.txt
```

### Generate the pages locally

```
python pages_builder/generate_pages.py
```

### Run the server

```
cd pages
python -m SimpleHTTPServer
```

### Overwrite the documentation on Github Pages with your local copy

```
sh build_tools/push_to_github_pages.sh
```


### Sass compilation

The Sass compilation takes files from `scss` and renders CSS files in `pages/public/stylesheets`.

The `./scss`, `govuk_frontend_toolkit/stylesheets` and `./build_tools/assets` folders are included in the load path so you can import any files from them.


## Workflow considerations

### CSS image paths

In order to allow one path, whether working locally or on `origin gh-pages`,
all images referenced in the CSS are assumed to be on the github pages server.

For example, the file `breadcrumb-separator.png` is referenced as
`http://alphagov.github.io/digitalmarketplace-frontend-toolkit/images/breadcrumb-separator.png`.