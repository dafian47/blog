+++
draft = false
date = "2017-07-05T16:54:24+02:00"
author = "M Rizki Dafianto"
menu = ""
thumbnail = "images/blog-sourcetree.png"
tags = ["sourcetree","git"]
share = true
slug = "using-sourcetree"
description = "Menggunakan SourceTree sebagai Git Client"
featured = false
comments = true
title = "Menggunakan SourceTree"

+++

# Register Akun Atlassian

Register Akun Atlassian [disini](https://www.atlassian.com/). Gunakan akun email Anda.

# Instalasi SourceTree

Berikut panduan singkat instalasi SourceTree. 
* Buka website [SourceTree](https://www.sourcetreeapp.com/) dan klik tombol Download
* Setelah selesai didownload, buka file tersebut (EXE untuk Windows atau DMG untuk Mac)
* Klik tombol **Use an existing account** untuk login menggunakan akun Atlassian. Bila belum klik tombol **Go to My Atlassian** dan ikuti petunjuknya untuk membuat akun baru. Gunakan akun email Anda, karena bisa digunakan untuk login Bitbucket.

{{% img src="pic/sourcetree-install.png" %}}

* Ketika ada pilihan untuk menambahkan repo, klik tombol **Skip Setup** karena kita akan menggunakan GitLab sebagai Servernya.

{{% img src="pic/sourcetree-add-repo.png" %}}

* Setelah sudah, kita kan lanjut untuk menambahkan remote mulai dari lokal kita.

# Pembuatan SSH Key untuk GitLab

Sebelumnya kita kan membuat SSH Key yang digunakan untuk *Otentifikasi* antara Local dan Server GitLab melalui akun GitLab kita. Cara nya sebagai berikut:

* Klik akun GitLab kita di pojok kanan atas, kemudian pilih Settings
* Buka tab SSH Keys, klik link *generate it* dan buka di tab baru.

```
$ cat ~/.ssh/id_rsa.pub
```

* Jalankan perintah di Terminal bila menggunakan Mac dan di Git Bash bila menggunakan Windows. Bila belum ada maka kita kan mengenerate nya.

```
$ ssh-keygen -t rsa -C "your.email@domain.com" -b 4096
```

Jalankan perintah tersebut untuk mengenerate SSH Key. Gunakan akun email Anda yang sama dengan akun GitLab.
Kemudian anda akan ditanyakan letak file RSA nya. Tekan Enter untuk membiarkannya default. Tekan Enter terus hingga selesai. Setelah selesai, jalankan perintah sebelumnya maka akan tampil seperti ini.

```
$ cat ~/.ssh/id_rsa.pub
ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDgR8Vr1AOa0xsnHRZHXBbDTPb5YClq9pcJJ34yWU3qP3uMFub4oGcWhl+8XJzavA8pffETTn1qHTg/0v7N1Z4UgbQAGCM3JGMmjCbygc7V9SGTmj6+yHnRPl7kH4DnIO6i2txfc13pofdV9f12tsfx7fWJ9W4Xhe6IITPCWGz2u8YPFXlaZQUM4L1n8xiJZAADtwUS4ft8Bzjl1/4Lr55weYjqmWhmNH9AvbonpiAVKdr2VjT627y3lcauaHmakxZXk+s6BzA5ciQoK5eZWEBrG5NlMy7J2OmNU6Pt/CSecQk/iNm0QCgiaVMkEI0M7SXMensYmDSDdTT5Lau2QOzV your.email@domain.com
```

* Copy mulai dari ssh-rsa hingga akun email kita. Dan paste di Halaman SSH-Key. Misalnya seperti ini. Dan klik tombol Add Key.

{{% img src="pic/page-ssh-key.png" %}}

* Setelah selesai kita siap menggunakan integrasi antara GitLab & SourceTree :)

# Menambahkan Remote ke Existing Project

Dalam aktivitas biasanya kita sudah membangun project kita. Seperti membuat aplikasi Android dengan Android Studio, aplikasi iOS dengan XCode, aplikasi Java dengan Spring MVC dan lainnya. Untuk hal itu kita kan membuat sample project. 

* Buatlah sebuah folder dengan nama **DemoGit**

```
$ cd root-path/
$ mkdir DemoGit
```

* Buatlah sebuah file markdown dengan nama file **README.md**. File ini berguna untuk deskripsi detail project kita. Sangat disarankan setiap project disertakan file tersebut untuk memudahkan developer lainnya ketika kerja tim.

```
$ cd DemoGit/
$ touch README.md
```

* Isikan file README.md kita. Misalnya seperti ini.

{{% img src="pic/file-readme.png" %}}

* Setelah itu jalankan perintah berikut untuk membuat repo lokal

```
$ git init
Initialized empty Git repository in /Users/dafian/Documents/DataDafi/Workspace/doc/DemoGit/.git/
```

* Tambahkan remote server GitLab project DemoGit kita dengan perintah berikut

```
$ git remote add origin git@gitlab.com:blog-development/DemoGit.git
``` 

* Tambahkan semua file agar dapat di `commit` dan di `push` ke server

```
$ git add .
```

* `commit` semua perubahan dengan perintah berikut

```
$ git commit -m "Initial Commit"
[master (root-commit) ed6fcfe] Initial commit
 1 file changed, 4 insertions(+)
 create mode 100644 README.md
```

* Dan yang terakhir `push` repo lokal kita ke repo server di GitLab

```
$ git push -u origin master
Counting objects: 3, done.
Writing objects: 100% (3/3), 244 bytes | 0 bytes/s, done.
Total 3 (delta 0), reused 0 (delta 0)
To gitlab.com:blog-development/DemoGit.git
 * [new branch]      master -> master
Branch master set up to track remote branch master from origin.
```

* Buka halaman project Git kita tadi yang bernama DemoGit. Maka tampilannya kan seperti ini

{{% img src="pic/page-first-commit.png" %}}


# Panduan Singkat SourceTree

Dalam kerja sama tim, kadang kala kita membantu developer lainnya. Dan kita harus mengkloning repo yang di server ke lokal kita. Berikut panduannya.

### Clone Repo dari GitLab ke Lokal

* Copy url SSH project yang akan di kloning. Dalam contoh berikut adalah project DemoGit.

> Contoh URL : git@gitlab.com:blog-development/DemoGit.git

* Buka SourceTree dan klik tombol New+

{{% img src="pic/sourcetree-home.png" w="300" h="500" %}}

* Pilih menu **Clone from URL**

{{% img src="pic/sourcetree-menu-clone.png" w="200" h="100" %}}

* Paste url SSH tadi di **Source URL:**. Ganti letak project di **Destination Path:**. Anda bisa mengganti nama project di **Name:**. Tunggu hingga muncul tulisan **This is Git Repository**. Setelah itu klik tombol Done.

{{% img src="pic/sourcetree-clone-repo.png" %}}

* Setelah selesai Repo disinkron, maka akan tampil sebagai berikut.

{{% img src="pic/sourcetree-lokal-repo.png" %}}

### Push Repo dari Lokal ke GitLab

Contoh kali ini kita kan melakukan `push` perubahan di lokal kita ke server.

* Sebagai contoh, edit isi file **README.md**. Tambahkan nama Anda di dalamnya.
* Setelah selesa, buka SourceTree kembali dan pilih Project nya. Maka akan tampil perubahan seperti ini.

{{% img src="pic/sourcetree-uncommited-file.png" %}}

* Lakukan `commit` pada perubahan dengan cara klik tombol **Commit** di pojok kiri atas. Kemudian kan tampil seperti ini.

{{% img src="pic/sourcetree-commit-file.png" %}}

* Centang file yang akan di `commit`. Bila terdapat ikon tanda tanya, artinya file tersebut baru dan harus di centang untuk menambahkanya ke repo lokal. Isikan deskripsi di kotak dibawah nama kita. Kemudian tekan tombol **Commit**.

{{% img src="pic/sourcetree-unpush-file.png" %}}

* Sampai sini kita sudah menyimpan di repo lokal kita. Di SourceTree terlihat ada ikon `1 ahead` yang berarti perubahan repo lokal kita terdapat satu yang baru dibandingkan repo server. Untuk melakukan sinkroni nya. Tekan tombol **Push**. Kemudian tampil dialog sebagai berikut.

{{% img src="pic/sourcetree-dialog-push.png" %}}

* Pastikan checkbox di dalam kotak master dicentang seperti contoh. Untuk melakukan branch mana yang akan disinkronisasi. Setelah itu klik tombol **OK**. Maka tidak akan ada ikon lagi. Dan periksa di Website GitLab. Apakah sudah berubah file README.md kita.

### Pull Repo dari GitLab ke Lokal

Contoh kali ini kita kan melakukan `pull` dari server ke lokal. Tambahkan File LICENSE dengan cara klik tombol **Add Lincese**. Pilih salah satu template, dalam hal ini menggunakan template License MIT.

* Buka SourceTree, dan buka project DemoGit. Maka akan tampil ikon `1 behind`, bila belum klik tombol **Fetch** untuk mengecek perubahan di server.

{{% img src="pic/sourcetree-unpull-file.png" %}}

* Kita akan melakukan sinkronisasi repo lokal dari repo server. Klik tombol **Pull**. Maka akan tampil dialog sebagai berikut.

{{% img src="pic/sourcetree-dialog-pull.png" %}}

* Biarkan secara default, kemudian klik tombol **OK**. Selesai

### Penggunaan Tag

Penggunaan Tag bisa berguna untuk menentukan versi rilisan. Sebagai contoh pada Android dan iOS, versi rilis `1.3.0`. Dalam *Source Code* bisa gunakan Tag `1.3.0` sebagai pengingat bahwa *Source Code* dengan Tag tsb menunjuk pada versi rilis yang sama. 

Cara nya klik salah satu `commit` kita yg bersifat final. Disarankan di branch *master*. Klik kanan, pilih **Tag...** dan masukan nama Tag di **Tag Name**. Kemudian klik tombol **Add**. 

# Referensi

* [SourceTree Documentation](https://confluence.atlassian.com/get-started-with-sourcetree/get-started-with-sourcetree-847359026.html)
* [GitLab SSH Key Documentation](https://gitlab.com/help/ssh/README)