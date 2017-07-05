+++
date = "2017-07-05T16:44:24+02:00"
menu = ""
title = "Manajemen Konflik Git"
draft = false
image = ""
description = "Dalam kerja tim, seringkali terdapat file yang sama-sama digunakan"
share = true
tags = ["conflict","git"]
slug = "manage-conflict"
featured = false
author = "M Rizki Dafianto"
comments = true

+++

Dalam kerja tim, seringkali terdapat file yang sama-sama digunakan. Sehingga mengalami perubahan. Ketika akan melakukan `commit` maka file tersebut kan terjadi konflik. Berikut salah satu cara menanganu konfilk.

* Misalnya kita rubah file **README.md** di server dan menambahkan Copyright.
* Dan di lokal kita juga menambahkan Copyright
* Buka SourceTree, untuk kita melakukan `commit` dan `push`
* Ketika selesa melakukan `commit` dan akan melakukan `push`. SourceTree memunculkan dialog keterangan sebagai berikut. 

![SourceTree Error Ketika Akan Melakukan Push](https://raw.githubusercontent.com/dafian47/blog/master/static/pic/sourcetree-error-push.png)

* Klik tombol **OK**. Disini kita harus melakukan `pull` terlebih dahulu. Lakukan `pull` dengan klik tombol **Pull**. Maka kemudian kan tampil seperti ini. Berikut adalah tampilan ketika kita terdapat file conflict. Dan kita harus *menyelesaikannya* secara manual.

![SourceTree Menunjukan File Conflict](https://raw.githubusercontent.com/dafian47/blog/master/static/pic/sourcetree-file-conflict.png)

* Buka file yang mengalami konflik. Dalam hal ini file **README.md** di Text Editor. Maka akan tampil seperti ini.

![Text Editor File Conflict](https://raw.githubusercontent.com/dafian47/blog/master/static/pic/file-conflict.png)

* Hapus teks bertuliskan `<<<<<<< HEAD` dan `>>>>>>> 2d895eb1a3616aa474c30052dcfb30b0cd75d783`. Dan selesaikan perubahan yang konflik tersebut. Setelah selesai, save dan lakukan `commit` seperti biasa. Dan sudah dapat di `push` ke server.