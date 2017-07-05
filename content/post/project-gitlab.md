+++
menu = ""
share = true
featured = false
author = "M Rizki Dafianto"
comments = true
title = "Project di GitLab"
image = ""
slug = "project-gitlab"
draft = false
description = "Kali ini kita kan menggunakan GitLab sebagai Cloud Repository kita"
tags = ["gitlab","git"]
date = "2017-07-05T16:34:24+02:00"

+++

# Login GitLab

Silahkan Login menggunakan akun email Anda, jika belum pernah mendaftar dapat Register dari awal dengan klik tombol Sign Up. Dalam hal ini Anda dianggap telah Register. Silahkan klik tombol Sign In.

![Halaman Login](pic/page-login.png)

# Halaman Group

Setelah anda berhasil login. Masuk ke halaman Grup dengan cara klik tombol drawer di pojok kiri atas dan pilih Groups. Sehingga tampilan menjadi seperti ini.

![Halaman Group](pic/page-group.png)

# Contoh Remote Repo Menggunakan GitLab

Setelah ini anda akan membuat demo repo untuk digunakan bersama Git yang tersinkron pada GitLab ini. Yang pertama klik tombol New Project. Dan isikan sesuai kebutuhan. Misalnya sebagai berikut

![Halaman Remote Repo Baru](pic/page-create-repo.png)

- **Project name** isikan dengan nama project kita. Dalam hal ini project yang kita buat bernama DemoGit.
- **Project description** isikan dengan penjelasan dan keterangan tentang project kita. Bersifat opsional, tetapi disarankan di isi untuk memperjelas keterangan project kita. Biarkan default pengaturan lainnya. Setelah itu klik tombol Create Project.

Setelah itu otomatis anda akan di arahkan ke halaman detail project yang kita buat tadi. Misalnya seperti berikut.

![Halaman DemoGit](pic/page-demogit.png)

Scroll kebawah maka akan tampil petunjuk untuk menghubungkan repo di lokal dan repo di GitLab. Dalam hal ini kita akan memanfatkan salah satu IDE Git yaitu SourceTree. Saya memilihnya karena lebih mudah dibandingkan yang lain. Terdapat di Windows dan Mac. Dan untuk Multiple Remote dengan Bitbucket lebih mudah, dikarenakan SourceTree adalah IDE yang dibangun oleh Tim Atlassian dan Bitbucket adalah salah satu productnya sehingga integrasi keduanya sangat cocok. Karena kita menggunakan GitLab maka akan ada sedikit *Trick* untuk dapat melakukan integrasi antara SourceTree dan GitLab.