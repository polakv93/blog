---
title: Domain for this blog 🌐
date: 2024-12-12 17:00:00+0100
categories: []
tags: [github, domain, dns, hosting]
---

To have this blog on a subdomain, I bought a domain from OVH its name is `polakiewi.cz`.
For this blog, I created the subdomain `blog.polakiewi.cz`.

To attach it to the Github Pages, I need to go to the repository settings > Pages > Custom domain and add `blog.polakiewi.cz`.

![settings page](/assets/images/2024-12-12-01.png)

Also according to the documentation I need to create CNAME record in my OVH DNS settings.

```dns
blog IN CNAME polakv93.github.io. 
```

Where `blog` is my subdomain and `polakv93.github.io` is my Github Pages domain.  
So now in the browser, I can go to `https://blog.polakiewi.cz` and see my blog.  

Also is nice hove the same blog available under `https://www.blog.polakiewi.cz` so to achieve that I created another CNAME.

```dns
www.blog IN CNAME polakv93.github.io.
```

Last part is modify configuration of the jekyll `_config.yml` file.

```yml
...
url: https://blog.polakiewi.cz
...
baseurl: "/"
...
```

And that's it. 🎉
