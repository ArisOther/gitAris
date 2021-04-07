# gitAris

## Pengenalan & Instalasi
- ======================
- dokumentasi lengkap ada di https://git-scm.com/book/id/v2

## NEW REPOSITORY
- github.com
- create new repository/organisation

## GIT CONFIG
- git --version
- git config --list
- git config --get remote.origin.url
- git config --global user.name "namamu" 
- git config --global user.email "winandiaris@gmail.com"
- git config --global user.password "your password"

## REMOTE
- git remote -v --> remote list
- git config --get remote.origin.url --> cek remote yang aktif
- git remote add origin https://github.com/winandiOrg/winandiPy2.git
- git remote set-url origin git@github.com:winandiaris/winandiPy.git
- git remote rm origin --> menghapus remote ang lama dulu jika diperlukan

## GIT INIT
- Memulai git di directory local:
  - Masuk ke directory baru/kosong, buat file sembarang
  - git init
  - git add .
  - git commit

- Menghubungkan ke git
  - Buat repo baru di github.com
  - git remote add origin https://github.com/ArisDjango/CrudVeryAcReact.git
  - git status
  - git push --set-upstream origin master
  - Masukkan username & password github
  - selesai

## CLONE (repo pribadi)
- buat repo kosong baru di git --> https://github.com/ArisDjango/CrudVeryAcReact.git
- cd directory_lokal
- git clone https://github.com/ArisDjango/CrudVeryAcReact.git
- Buat perubahan
- git add . --> git commit -m "sds" --> git push origin

## CLONE (repo orang lain, variasi Fork)
- cd directory
- git clone https://github.com/orang_lain.git
- git config --get remote.origin.url --> melihat remote yang aktif
- git remote set-url origin git@github.com:winandiaris/winandiPy.git --> set menjadi remote kita
- add/commit/push

## FORK
- Fork repo yang diinginkan --> https://github.com/octocat/Spoon-Knife
- tentukan fork ini di simpan di mana --> pilih dari repo kita/buat repo baru dulu jika tak punya
- hasilnya --> https://github.com/ArisOther/Spoon-Knife
- clone ke dir local kita

## LOG
- git log   = melihat perubahan/kontribusi dalam git 
- git log <branch>
- git log --oneline    = satu baris simple
- git log 423ub34    = menampilkan log berdasarkan no.

## ADD
- melihat head file --> `git rev-parse --short HEAD`  atau `git log --oneline`
- `git add .` --> add semua,
- `git add <head>` --> add kode head file tertentu
- git add ../README.md --> add nama file tertentu
- `git reset <head>` --> undo add
- `rm -Force ./.git/index.lock` --> Jika ada masalah conflict 'Another git process'

## COMMIT
- git add --all
- git status = melihat daftar file yang siap di commit
- git commit -m "ini adalah file html" 


## PUSH
- pastikan di bab #config, tambahhkan username/pass jika belum ada
- pastikan remote punya izin (di bab #remote), add/rm remote jika perlu

- git push origin 
- sudo git push origin --> untuk by pass agar tidak menggunakan sudo --> sudo chown -R aris:aris /home/aris/tesRepo/Spoon-Knife/.git
  - saat melakukan push, branch yang aktif = 'main'.
  - biasanya diminta branch agar bisa push--> perintah dibawah ini akan otomatis membuat branch baru = 'master'
    - git push --set-upstream origin master
  - di github, perubahan masuk di branch master, dan bisa dirubah manjadi branch default.
- jika menginginkan perubahan terdapat juga di branch lain, gunakan merge

## BRANCH
- git branch = list branch
- git branch nama_branch = membuat branch baru
- git checkout master = pindah ke branch teretentu (master)
- git branch -d crazy-experiment = delete branch

## MERGE
- Misal branch 'hal-depan' (kondisi sudah terisi content code) ada file baru/perubahan, dan ingin menambahkan file/perubahan itu ke branch 'master'
  - git checkout master
  - git merge hal_depan

- Misal BUAT branch baru 'hal_depan' (kondisi kosong) dan ingin mengisi branch tsb dengan 'master' (terdapat content utama):
  - di vscode, kondisi ada di  branch 'master' beserta kode2yna sedang aktif ,  
  - git branch hal_depan
  - git checkout hal_depan
  - buat perubahan pada kode
  - git add/commit/push



## PULL
- misal menginginkan code di vs code up to date terhadap github web
  - git checkout master
  - git pull
 
- git init ------------> membuat git pada folder tertentu.
- git status
- git add index.html -----------> menambahkan/Track file dalam git 
- git add --all
 

===============================================
===============================================



## other
Commit
=========================
Setelah melakukan perubahan pada kode di dir lokal
- git diff ----------> see perubahan  file
- git add index.html
- git commit -m "ini adalah file html"  
 



## Undo dan Pindah Log
- ========================
- git log ----------> history proses git, 
- git log --oneline -----------------------> show log on 1 line.
- dari proses ini kita pilih id commit yang akan kita undo
- git checkout index.html --------> untuk undo , atau
-  git checkout 123456 -- index.html ---->undo by id commit
 



## Reset
- =========================
- git reset --mixed 12345 ---------> me-reset log git tanpa menghilangkan / merubah file asli. log git yang akan hilang adalah log diatasnya. misal, jika kita memilih id 12345 maka yang hilang adalah log diatas id tersebut. sedangkan data di workspace masih tetap ada
 - git reset --hard 12345 ---------> untuk me reset log git sekaligus mengembalikan workspace kita pada kondisi awal
 



## Branch
- =======================
- Branch dilakukan ketika bermaksud kontribusi pada master
- branch akan membuat cabang/menduplikasi folder persis seperti ‘master’.
- perubahan yang terjadi di branch tidak akan berpengaruh pada master atau branch yang lain kecuali di commit. Perubahan hanya terjadi pada branch yang aktif.

- git branch --------> untuk mengetahui branch yang tersedia saat ini dan aktif (warna hijau)

- git brach baru  -------> untuk membuat branch new bernama ‘baru’

- git checkout master  -------> untuk pindah antar branch / mengaktifkan branch tertentu (contoh : pindah ke branch ‘master’)

- git branch -D --------> baru  Untuk menghapus branch ‘baru’

- git branch -m ---------->baru cabangsatu  untuk rename branch ‘baru’ menjadi ‘cabangsatu’

- git merge cabangsatu -------> maka akan menyatukan perubahan pada ‘cabangsatu’ kedalam ‘master’ (perintah ini dijalankan pada posisi branch master)




## Repository
- ==============================
- bisa dibuat di github.com



## Clone
- ======================================
- Clone dilakukan ketika tidak bermaksud melakukan kontribusi pada 'master'
- Buka konsol, lalu masuk ke direktori lokal yang ingin dijadikan tempat kloning ( contoh cd c:\\xampp\htdocs\latihan )

- git clone https://github.com/winandiaris/templated.git
   untuk clone dengan cara copy kode clone,ke konsol. Maka seluruh file akan  tercopy di folder lokal
-------------------
- Langkah lain clone:
  - Copy alamat clone github/ssh

- //cloning repo orang lain ke folder cloned-repo local milik kita
Git clone git@github.com:ZhangMYYihua/lesson-3.git cloned-repo

- //melihat remote yg aktif saat ini: adalah milik origin Yihua, bukan milik kita
Git remote
Origin

- //menghapus remote sumber
Git remote remove origin

- //membuat remote baru, diarahkan ke repo github kita (pastikan sudah punya repo)
Git remote add origin git@github.com:winandiaris/monsba.git

- //upload hasil cloning tadi/yg ada di local menggunakan remote github kita
Git push origin master





- =======================
```
Contoh:
echo "# monsba" >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin git@github.com:winandiaris/monsba.git
git push -u origin master
```
