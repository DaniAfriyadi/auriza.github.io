---
layout: post
title: "Jekyll Quick Start"
tags: jekyll, markdown, debian
---

## Instal Jekyll

~~~ sh
sudo apt install ruby-full
sudo gem install jekyll
~~~

## Buat situs baru

~~~ sh
jekyll new "blog"                   # buat situs baru pada direktori "blog"
cd "blog"
bundle exec jekyll serve            # jalankan webserver
~~~

Akses blog baru kamu di <http://localhost:4000>.


## Buat postingan baru

~~~ sh
cat > _posts/YYYY-MM-DD-title-of-post.md << EOF
---
layout: post
title: "Jekyll Quick Start"
tags: jekyll, markdown, debian
---

## Instal Jekyll

...
EOF
~~~

Server Jekyll secara otomatis akan memantau perubahan *file* dan memperbarui isi
situs. Muat ulang halaman <http://localhost:4000> untuk melihat postingan baru
kamu.


## Publikasi via GitHub Pages

Setelah blog di localhost sudah jalan, kamu bisa publikasikan blog kamu melalui
[GitHub Pages](https://pages.github.com/) secara gratis. Ikuti caranya di tautan
tersebut. Nanti, blog kamu dapat diakses di alamat <https://username.github.io>,
keren kan!
