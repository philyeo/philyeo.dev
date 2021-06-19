---
title: "Messing Around With Hugo Part 1"
date: 2021-06-19T14:57:56+08:00

---

So I have finally created my new website, fully equipped with blog, portfolio and social links. I used some simple theme but I wasn't able to make modification to the them and yet have it automatically build the public artifacts for the static site using Azure's and Git's automatic CI workflow integration. 

Hang on, let's backtrack abit. I love hugo static gen. It was love at first sight. I know I must have crawled and lived in a cave for a while and thus wasn't aware of this wonderful tool. Now that I am expose to it, I just can't stop working on it. 

Got my site going here with [www.philyeo.dev](https://www.philyeo.dev) and loving it. But in the beginning had some trouble with altering the theme. Everytime I did that, it keeps breaking the automatic workflow for integration. Build process would fail somehow. I tried otherways to get around it. But it seems to point to some convoluted git process that one needs to undertake. My level of git hasn't quite reach that sophistication yet, so I'll stay clear of that for now. 

But I did manage to find out about using Go modules with one's hugo project. Instead of relying on theme param in the config.toml file, simply use the go module import feature. Here I have it for my config.yaml file instead of toml version

```
module:
  imports:
  - path: github.com/jbub/ghostwriter
```

If you have toml file, than use this instead
```
[[module.imports]]
    path = "path-to-theme"
    # project theme
```

Just don't forget to comment the theme param in the toml / yaml file. 

This also got me thinking. You can write a webservice that allows you to create a frontend to create post without having to open your VSCode and them push to git for posting your articles. Something I'd be interested to work on. 