---
layout: post
title: "Jekyll Quick Start"
tags: jekyll, markdown, debian
---

### Install Jekyll

~~~ sh
sudo apt install ruby-full
sudo gem install jekyll
~~~

### Create new site

~~~ sh
jekyll new "blog"                   # create new site
cd "blog"
bundle exec jekyll serve            # start webserver
~~~

Access your new blog at <http://localhost:4000>

### Create new post

~~~ sh
cat > "_posts/YYYY-MM-DD-title-of-post.md" << EOF
---
layout: post
title: "Jekyll Quick Start"
tags: jekyll, markdown, debian
---

### Install Jekyll

...
EOF
~~~

### Rebuild the site

~~~ sh
bundle exec jekyll build
~~~
