---
layout: post
title: "Membuat Mirror Repositori Ubuntu"
tags: apt, mirror, ubuntu
---

## Install apt-mirror

~~~ sh
sudo apt install apt-mirror
~~~

## Konfigurasi repo sumber

~~~ sh
sudo editor /etc/apt/mirror.list
~~~

~~~
...
deb http://id.archive.ubuntu.com/ubuntu xenial main restricted universe multiverse
deb http://id.archive.ubuntu.com/ubuntu xenial-security main restricted universe multiverse
deb http://id.archive.ubuntu.com/ubuntu xenial-updates main restricted universe multiverse

clean http://id.archive.ubuntu.com/ubuntu
~~~

## Jalankan apt-mirror

~~~ sh
sudo apt-mirror
~~~


## Publikasikan repo via web

~~~ sh
sudo apt install apache2
sudo ln -s /var/spool/apt-mirror/mirror/id.archive.ubuntu.com/ubuntu/ \
           /var/www/html/ubuntu
~~~


## Otomatisasi *update* repo (opsional)

~~~ sh
sudo editor /etc/cron.d/apt-mirror
~~~

Hapus tanda komentar (`#`) pada baris terakhir untuk menjalankan `apt-mirror` secara otomatis tiap hari pada pukul 4:00.

~~~
0 4 * * *   apt-mirror      /usr/bin/apt-mirror > /var/spool/apt-mirror/var/cron.log
~~~

Selesai untuk bagian server.


## Setting klien

Pada klien, set sumber repo sebagai berikut (di sini, alamat IP server mirror adalah 172.20.35.101).

~~~ sh
sudo editor /etc/apt/sources.list
~~~

~~~
deb [arch=amd64] http://172.20.35.101/ubuntu xenial main restricted universe multiverse
deb [arch=amd64] http://172.20.35.101/ubuntu xenial-security main restricted universe multiverse
deb [arch=amd64] http://172.20.35.101/ubuntu xenial-updates main restricted universe multiverse
~~~

Tes dengan meng-*update* repositori.

~~~ sh
sudo apt update
~~~
