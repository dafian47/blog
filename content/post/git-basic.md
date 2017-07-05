+++
author = "M Rizki Dafianto"
comments = true
title = "Git Basic"
menu = ""
share = true
tags = ["basic","git"]
date = "2017-07-05T16:28:00+02:00"
image = "images/cover-git.jpg"
draft = false
description = "Git adalah tools yang berfungsi sebagai Version Control System (VCS) dan"
featured = false
slug = "git-basic"

+++

# Dasar Git

Git adalah *tools* yang berfungsi sebagai *Version Control System (VCS)* dan kalau diartikan ke bahasa kita artinya sebuah sistem pelacak perubahan pada file. Git sendiri dibuat oleh orang yang menciptakan *Kernel Linux*, yup... tidak salah lagi dia adalah yang mulia **Linus Torvalds**. Pada awalnya Git digunakan untuk membantu pengembangan Kernel Linux sebelum akhirnya dipakai lebih luas di berbagai pengembangan software lainnya dan dibuat *Multi-Platform* sehingga tersedia di hampir semua OS. Selain Git ada beberapa alternatif lain dari sistem VCS, contohnya: Subversion, Mercurial, CVS, dll.

# Kenapa Pakai Git

Kenapa Git penting untuk tim developer? Dengan menggunakan Git, setiap orang dalam sebuah tim dapat melakukan perubahan pada *Source Code* tanpa harus takut terjadi bentrok ataupun kesulitan dalam menggabungkan hasil perubahan yang mereka lakukan. Dengan menggunakan Git, setiap perubahan pada source-code akan terlacak pesan perubahannya, apa saja yang diubah, siapa yang mengubah dan kapan waktunya.

Link download Git [Disini](https://git-scm.com/downloads)

Jika sudah di Instal, maka Anda dapat mengecek nya dengan cara:
```
$ git version
git version 2.11.0 (Apple Git-81)
```

# Setup Git

Sekarang anda telah memiliki Git pada sistem anda, berikutnya anda akan harus melakukan beberapa penyesuai pada lingkungan Git anda. Anda hanya perlu melakukan hal ini sekali saja pada saat memperbaharui versi Git anda, penyesuai tidak perlu dilakukan lagi. Anda pun dapat mengubah penyesuaian tersebut setiap saat.

### Identitas Anda

Hal pertama yang harus anda lakukan ketika menginstalkan Git adalah mengatur username dan alamat e-mail anda. Hal ini penting karena setiap commit pada Git akan menggunakan informasi ini, dan informasi ini akan selamanya disimpan dengan commit yang anda buat tersebut:

```
$ git config --global user.name "M Rizki Dafianto"
$ git config --global user.email dafian47@gmail.com
```

### Mengecek Settingan Git

Jika anda ingin mengecek settingan anda, anda dapat menggunakan peritah git config --list untuk menampilkan semua settingan yang digunakan Git:

```
$ git config --list
user.name=M Rizki Dafianto
user.email=dafian47@gmail.com
core.autocrlf=input
core.excludesfile=/Users/dafian/.gitignore_global
...
```

# Perintah Dasar Git

Perintah-perintah dasar dari Git yang paling sering digunakan dan wajib kita kuasai yaitu: `git init`, `git status`, `git add`, `git commit`, `git pull / push`, `git checkout`, `git diff`, `git merge`, `git remote` dan `git reset`. Sebetulnya masih banyak fungsi lain dari Git untuk kasus-kasus tertentu tapi mungkin perintah yang telah disebutkan sebelumnya yang akan paling sering kita gunakan, berikut ini adalah penjelasan singkatnya:

- `git init` untuk membuat repo lokal baru pada perintah ini akan dibuat sebuah folder baru yang bernama ".git"
- `git status` untuk melihat status dari repo lokal
- `git add` untuk menambahkan file ke dalam repo yang sebelumnya sudah dibuat
- `git commit` untuk menyimpan seluruh perubahan yang terjadi
- `git pull / push` untuk menyimpan dan mengambil data dari remote repo
- `git checkout` untuk pindah branch
- `git diff` untuk membandingkan perubahan file
- `git merge` untuk melakukan penggabungan antar branch
- `git remote` untuk menambahkan remote repo baru
- `git reset` untuk membatalkan perubahan pada repo lokal

# Contoh Penerapan Git

Berikut ini adalah contoh kasus penggunaan Git pada sebuah folder:

```
$ cd /folder-project
```
Pertama masuk terlebih dahulu ke folder *Source Code* yang ingin ditambahkan ke Git.

```
$ git init
```
Setelah `git init` selesai maka akan muncul sebuah folder baru yang bernama ".git", disinilah seluruh hal yang berhubungan dengan Git akan tersimpan. 

```
$ git add
```
Berikutnya kita akan menambahkan seluruh file yang ada didalam folder.

Pada tahap ini file yang ditambahkan belum benar-benar masuk ke repo, perintah `git add` hanya memberi tanda pada file agar ditambahkan pada `git commit` berikutnya. Untuk melihat file apa saja yang akan ditambahkan ketik perintah berikut:

```
$ git status
```

Apabila telah yakin dengan perubahan yang dilakukan maka kita bisa melakukan git commit untuk menyimpan perubahan ke repo dengan perintah berikut:

```
$ git commit -m "Initial Commit"
```

Pesan pada `git commit` harus dibuat dengan singkat dan jelas untuk mempermudah developer lain dalam memahami apa yang terjadi didalam commit tersebut. Hal ini akan berguna ketika terjadi konflik pada proses merge.

### Contoh yang Disarankan

> "update new mail config on config.php"

> "remove unused code on SiteController.php"

> "revert changes on last commit because of bug on xxxxx"

### Contoh yang Tidak Jelas dan Tidak Disarankan

> "updates"

> "commit"

> "add some item"


# Remote Repository

Remote repository atau remote repo adalah tempat penyimpanan Git yang berada di cloud. Beberapa layanan yang terpopuler adalah [GitHub](https://github.com/), [Bitbucket](https://bitbucket.org/) dan [GitLab](https://gitlab.com/). Untuk development kita menggunakan GitLab sebagai remote repo karena kita bisa membuat private repo dan team pada layanan gratisnya, sementara GitHub tidak.

# Referensi

- [https://git-scm.com/book/id/](https://git-scm.com/book/id/)
- [http://blog.coldev.co/](http://blog.coldev.co/)