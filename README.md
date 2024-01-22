# gitAris
## update cara clone menggunakan [token](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token)
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
- git clone -b <branchname> https://github.com/orang_lain.git --> clone repo/all branch dan fetch ke branch tertentu
- git clone -b <branchname> --single-branch https://github.com/orang_lain.git --> clone dan fetch hanya branch tertentu
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
- `git add --all`
- `git status` = melihat daftar file yang siap di commit
- `git commit -m "ini adalah file html" `


## PUSH
- pastikan di bab #config, tambahhkan username/pass jika belum ada
- pastikan remote punya izin (di bab #remote), add/rm remote jika perlu

- `git push origin `
- sudo git push origin --> untuk by pass agar tidak menggunakan sudo --> `sudo chown -R aris:aris /home/aris/tesRepo/Spoon-Knife/.git`
  - saat melakukan push, branch yang aktif = 'main'.
  - biasanya diminta branch agar bisa push--> perintah dibawah ini akan otomatis membuat branch baru = 'master'
    - `git push --set-upstream origin master`
  - di github, perubahan masuk di branch master, dan bisa dirubah manjadi branch default.
- jika menginginkan perubahan terdapat juga di branch lain, gunakan merge

## BRANCH
- `git branch` = list branch
- `git branch nama_branch` = membuat branch baru
- `git checkout master` = pindah ke branch teretentu (master)
-` git branch -d crazy-experiment` = delete branch

## STASH
- `git stash`
- case: posisi aktif di branch 'master' dan update code, jika ingin pindah ke branch 'dev', di stash dulu agar perubahan code di 'master' tidak tampak di 'dev'

## MERGE
- Misal branch 'hal-depan' (kondisi sudah terisi content code) ada file baru/perubahan, dan ingin menambahkan file/perubahan itu ke branch 'master'
  - `git checkout master`
  - `git merge hal_depan`

- Misal BUAT branch baru 'hal_depan' (kondisi kosong) dan ingin mengisi branch tsb dengan 'master' (terdapat content utama):
  - di vscode, kondisi ada di  branch 'master' beserta kode2yna sedang aktif ,  
  - `git branch hal_depan`
  - `git checkout hal_depan`
  - buat perubahan pada kode
  - git add/commit/push



## PULL
- misal menginginkan code di vs code up to date terhadap github web
  - `git checkout master`
  - `git pull`
 
- `git init` ------------> membuat git pada folder tertentu.
- `git status`
- `git add index.html` -----------> menambahkan/Track file dalam git 
- `git add --all`
 

## ======================= Branching Strategy ========================
- So at least we have 4 branch during development?
  - Master
  - release
  - development
  - feature

- 'feature' merged to 'development', then 'development' merged to 'release', then at least 'release' merged to 'Master' ? something like that ?
-------------------

- "Gitflow Workflow." Here's a breakdown of the branches you mentioned and their typical flow in this workflow:
- Master:
  - Represents the stable and production-ready code. Code from release branches is merged into master when a new version is ready for deployment.
- Release:
  - Created from the develop branch when preparing for a release. The release branch allows for final testing, bug fixing, and making any necessary adjustments before merging into both master and develop.
- Develop:
  - The main branch for ongoing development. Feature branches are created from develop, and completed features are merged back into develop. It serves as a staging area for new features before they are released.
- Feature:
  - Feature branches are created from develop and used for developing new features. Once a feature is complete, it is merged back into develop. These branches are short-lived and focused on specific tasks.

- The typical flow in the Gitflow Workflow is as follows:
  - Feature Development:
    - Create a new feature branch from develop.
    - Implement and test the feature on the feature branch.
    - Once the feature is complete, merge it back into develop.
  - Release Preparation:
    - Create a release branch from develop.
    - Perform final testing, bug fixing, and any necessary adjustments on the release branch.
    - Once the release is ready, merge the release branch into both master and develop.
  - Hotfix (if needed):
    - If critical issues arise in the production code (on master), create a hotfix branch from master.
    - Fix the issue on the hotfix branch.
    - Merge the hotfix branch back into both master and develop.
- This branching strategy helps in organizing the development process, ensuring stability in production, and allowing for parallel development of features. However, it's important to note that the choice of branching strategy can vary based on team preferences, project requirements, and the development workflow in use.

## ----------- Merge Use case --------------
- Certainly! If you want to merge the changes from the 'release' branch into the 'master' branch, here's a step-by-step example:

  - Switch to the 'master' branch:
    - `git checkout master`
  - Ensure 'master' is up-to-date:
    - `git pull origin master`
  - Merge 'release' into 'master':
    - `git merge release`
    - If there are no conflicts, Git will perform the merge automatically. If there are conflicts, you'll need to resolve them manually before completing the merge.
  - Conflict Case
    - Resolve Conflicts (if any):
    - If conflicts occur during the merge, Git will pause the process and highlight the conflicting files. Open those files, resolve the conflicts, and then continue the merge.
    - After resolving conflicts, mark the files as resolved
    - `git add .`
- Continue with the merge
  - `git merge --continue`
- Commit the Merge:
  - If there were no conflicts or once you've resolved them, commit the merge.
  - `git commit -m "Merge 'release' into 'master'"`
- Push the Changes to Remote Repository:
  - `git push origin master`

## other
Commit
=========================
Setelah melakukan perubahan pada kode di dir lokal
- `git diff` ----------> see perubahan  file
- `git add index.html`
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
