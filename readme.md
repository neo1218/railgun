# ⚡️ railgun

> py static site generator

## Install

    $ pip install railgun-cli

## Config
you can modify site settings in [config.py](https://github.com/neo1218/railgun/blob/master/site/config.py)

### ⚡️ Site

Setting | Description
--- | ---
`SITE_NAME` | the name of your website
`SITE_URL` | your website url, important for path build
`SITE_DESC` | your website description
`SITE_OWNER` | your name...
`SITE_KEYWORDS` | the keyword description of your site

### ⚡️ Article

Setting | Description
--- | ---
`ARTICLE_TYPE` | article type, default is markdown
`ARTICLE_PER_PAGE` | The amount of the posts displayed on a single page. 0 disables pagination

### ⚡️ Owner

Setting | Description
--- | ---
`GITHUB_URL` | your github account
`WEIBO_URL` | your weibo account
`TWITTER_URL` | your twitter account
`QQ` | your QQ account
`EMAIL` | your email

### ⚡️ Deployment

Setting | Description
--- | ---
`GIT_URL`: github repo url
`BRANCH`: github repo branch, eg: master or gh-pages


> do not forget switch from ExampleConfig to MyConfig

```
config = {
    'default':  MyConfig
}
```

## Usage
railgun provided [railgun-commandline-tools](https://github.com/neo1218/railgun/blob/master/cli/railgun.py)

![railgun-cli](http://7xj431.com1.z0.glb.clouddn.com/屏幕快照 2016-11-05 上午12.45.34.png)

### ⚡️ railgun init
> generate a railgun site

```
$ railgun init railgun-site
```

railgun site structure:

    railgun-site -  - gen/ -> [railgun static files generator]
                    - config.py -> [railgun site configuration]
                    - requirement.txt -> [flask extensions]
                    app/ - pages/ -> [your articles]
                         - themes/ -> [railgun site theme]

then, you need to install flask extensions

    $ pip install -r requirement.txt

### ⚡️ railgun new
> crate a new post

```
$ railgun new filename
```

this command created **filename.md**(file extension name depends on ARTICLE_TYPE config) under **railgun-site/app/pages** folder with default article template:

```
title:
date: %Y-%m-%d %H:%M:%S
tags: ['tag1', 'tag2']
```

### ⚡️ railgun server
> start local preview server

```
$ railgun server
```

this command start preview server on http://localhost:5050/

### ⚡️ railgun upgrade
> upgrade the site's theme

eg:

```
$ cd {site}
$ git clone https://github.com/neo1218/ship-theme-cat.git app/themes/cat
$ railgun upgrade cat
```

Now you can use https://github.com/neo1218/ship-theme-cat theme.

### ⚡️ railgun build
> freezes a railgun site info static files

```
$ railgun build
```

this command build your site into static files to **railgun-site/app/build**

### ⚡️ railgun upload
> deploy railgun site

after the [deployment setup](https://github.com/neo1218/railgun#️-deployment) is complete

```
$ railgun upload
```

will deploy your site to github pages:)

## License
MIT, check [LICENSE](https://github.com/neo1218/railgun/blob/master/LICENSE) for detail.

## Change Logs
+ **V0.1.1-dev**
    - check deployment on github
