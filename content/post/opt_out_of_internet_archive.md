---
title: "Opt out of internet archive with hugo"
date: 2020-12-28T10:00:51Z
draft: false
---

If you don't fancy old versions of your website being archived by [The Internet Archive](https://archive.org) you can use a file called robots.txt to tell its crawler to skip your site.

To do this with a hugo website is quite simple. Inside your config.toml add the following;
```toml
enableRobotsTXT: true
```

Then run your build command;
```sh
hugo -D
```

This will then generate a file called `robots.txt` inside your `public` directory.

You can then edit this with the following to tell all crawlers to not index your site;
`

User-agent: *

Disallow: /

Disallow: /posts/opt_out_of_internet_archive/

Disallow: /posts/

Disallow: /posts/useful-unix/

Disallow: /categories/

Disallow: /tags/

Disallow: /

`

Redeploy your site and now your site should not be indexed anymore.

If you want to get rid of your old indexes you need to send a request to them detailing you want the site taken down. Good luck with that.
