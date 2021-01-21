# Micro-CMS v1

## Flag 1

The test page at `/page/1` says that it supports markdown but scripts are disabled. You can inject JavaScript using any HTML element by using the `onclick` attribute. Edit the post with the following content.

    <a href="" onclick="alert('')">Link</a>

Save the post, click the link then inspect the body.

    ^FLAG^bc1f227db153fc508ed241496366fdd4a441b433dd94041bad70bb00c0ac82ce$FLAG$

## Flag 2

The page `/page/5` is forbidden. However if you manipulate the URL so that you try to edit it, `/page/edit/5` then it will reveal the flag.

    ^FLAG^f0ca9dda56440a355c5563ea9135037fbd872718f664604f55d9cb0f134761df$FLAG$

## Flag 3

Try an SQLi injection as part of the edit path, `/page/edit/8'`

    ^FLAG^ff99f73d14cccd64e6bdce33e99e62d4818e8513fd51e6520afdb4eb25d84ed2$FLAG$

## Flag 4

It has already stated that script tags are removed, however if you put a script tag in a title and then go back to the home page, the flag will be revealled. This is because the content on the home page lists the titles of the post but it doesn't appear to be escaped.

    ^FLAG^eea16305c56755a4cccf96e5d178227b615519f5b8ac08b7955005ece5858093$FLAG$

## Key points

- Try manipulating URL's where an id is part of the path
- SQLi can often be found by passing in a single quote to a url that contains an identifier or value that could be used as part of a db lookup
- Just because content is escaped on one page, doesn't mean it is escaped on another