# Latihan Git CLI

Tutorial ini digunakan untuk belajar melakukan perubahan pada repository GitHub menggunakan terminal/PowerShell tanpa GitHub Desktop.

Repository latihan:

`https://github.com/KakRendy/SD_PCT_Rendy`

## 1. Masuk ke folder repository

Setelah repository di-clone, masuk ke foldernya:

cd "C:\Users\MyBook Hype AMD\SDPCTRendy"


Cek posisi folder:

pwd


## 2. Cek status repository

Gunakan:

git status


Perintah ini digunakan untuk melihat kondisi repository saat ini, termasuk apakah ada file yang berubah, file baru, atau perubahan yang belum di-commit.

## 3. Melihat branch

Untuk melihat branch yang sedang digunakan:

git branch --show-current


Contoh:

main


`main` adalah branch utama repository.

## 4. Melihat remote repository

Gunakan:

git remote -v


Contoh:

origin https://github.com/KakRendy/SDPCTRendy.git (fetch) origin https://github.com/KakRendy/SDPCTRendy.git (push)


`origin` adalah nama yang digunakan Git untuk menunjuk ke repository GitHub yang terhubung dengan repository lokal.

## 5. Membuat atau mengubah file

Perubahan bisa dilakukan menggunakan editor apa pun.

Dalam latihan ini, perubahan dapat dilakukan dari terminal.

Contoh membuat file:

New-Item "latihan.txt" -ItemType File


Atau menambahkan isi:

Add-Content "latihan.txt" "Belajar Git CLI"


## 6. Melihat perubahan

Setelah file berubah, gunakan:

git status


Untuk melihat detail perubahan:

git diff


`git diff` menunjukkan perbedaan antara kondisi file sekarang dengan versi yang terakhir disimpan oleh Git.

## 7. Memasukkan perubahan ke staging

Gunakan:

git add nama-file


Contoh:

git add README.md


Untuk memasukkan semua perubahan:

git add .


`git add` berarti menyiapkan perubahan untuk dimasukkan ke commit.

## 8. Membuat commit

Setelah perubahan masuk staging:

git commit -m "pesan commit"


Contoh:

git commit -m "update README"


Commit adalah catatan perubahan yang disimpan di repository Git lokal.

## 9. Melihat commit

Untuk melihat riwayat commit:

git log --oneline


Contoh:

abc1234 update README def5678 initial commit


## 10. Mengirim perubahan ke GitHub

Jika branch lokal sudah terhubung dengan branch remote:

git push


Git akan mengirim commit dari repository lokal ke GitHub.

Bentuk lengkapnya:

git push origin main


Artinya:

- `git push` = mengirim perubahan
- `origin` = repository GitHub yang terhubung
- `main` = branch yang dikirim

## 11. Alur dasar Git

Alur yang paling sering digunakan:

Ubah file ↓ git status ↓ git add . ↓ git commit -m "pesan" ↓ git push ↓ GitHub


## 12. Perbedaan commit dan push

`git commit` dan `git push` bukan hal yang sama.

### git commit

git commit -m "update"


Menyimpan perubahan sebagai commit di repository Git lokal.

### git push

git push


Mengirim commit lokal ke repository remote, misalnya GitHub.

Jadi:

git commit → menyimpan di komputer git push → mengirim ke GitHub


## 13. Mengambil perubahan dari GitHub

Untuk mengambil perubahan terbaru dari repository remote:

git pull


Biasanya digunakan sebelum mulai bekerja jika repository mungkin sudah berubah di GitHub.

## 14. Mengecek hubungan branch dengan remote

Gunakan:

git branch -vv


Contoh:

    main abc1234 [origin/main] update README


Ini menunjukkan bahwa branch lokal `main` terhubung dengan `origin/main`.

## 15. Jika `git push` gagal karena belum ada upstream

Jika Git memberikan pesan bahwa branch belum memiliki upstream, gunakan:

git push -u origin main


Parameter `-u` digunakan untuk mengatur hubungan antara branch lokal dan branch remote.

Setelah hubungan tersebut dibuat, biasanya cukup:

git push


## 16. Cek perubahan sebelum commit

Kebiasaan yang baik:

git status git diff


Kemudian:

git add . git status


Setelah itu:

git commit -m "jelaskan perubahan"


Dan terakhir:

git push


## 17. Cheat sheet

### Cek status

git status


### Lihat branch

git branch


### Lihat branch aktif

git branch --show-current


### Lihat remote

git remote -v


### Lihat perubahan

git diff


### Stage semua perubahan

git add .


### Commit

git commit -m "pesan"


### Push

git push


### Pull

git pull


### Lihat riwayat

git log --oneline


## 18. Inti yang harus dipahami

Git bekerja dengan konsep repository lokal dan repository remote.

Komputer ┌─────────────────────┐ │ Repository lokal │ │ │ │ edit → add → commit │ └──────────┬──────────┘ │ git push │ ▼ ┌─────────────────────┐ │ GitHub │ │ KakRendy/... │ └─────────────────────┘


Empat perintah utama:

git status git add . git commit -m "pesan" git push


Jika memahami empat perintah tersebut, kita sudah memahami dasar workflow Git dari command line.
