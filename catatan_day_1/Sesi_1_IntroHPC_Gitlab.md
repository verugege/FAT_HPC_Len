# Welcome to the FAT_HPC_Len wiki!
## Sesi 1 
- ICT Project Infra :
- 23000 Core
- Base CPU dan GPU
- GPU memiliki 4 x 8 GPU (NVIDIA H100)
- OS HPC RHEL9
- CPU Cluster, GPU Cluster, Geoscience Ecosystem, Virtualization Jakarta dan Virtualization Jakarta (Reloc Bali)
- Storage Layer Paralel File System (FPS), NAS, HDD

- Virtual Jakarta 1:Inatews VM, Sesicomp, Gitlab, Dev. Apps VM dan IDE

- Virtual Jakarta 2:Inatews VM,Seiscomp

## Sesi 2 - Gitlab

1. fungsi :
- version control
- menyimpan source code
- dapat dihubungkan dengan server
- membuat dokumentasi
- mengerjakan proyek bersama

2. konsep git :

Distributed, mengerjakan di lokal kompputer dan bisa di push ke gitlab server

Hambatan penggunaan git personil harus paham tentang konsep git, kadang dalam kerja kolaborasi muncul konflik saat menyimpan code ke git

Bisa dicheck siapa yg contribute dan seberapa besar kontribusinya

### workflow :

Pull -> Commit -> Push

3. Gitlab vs Github :
- Model license : opensource - Cloud SaaS
- Self hosting : sangat fleksible - Entreprise
- Biaya : Gratis untuk versi CE - Gratis untuk public dan private gratis tp terbatas fitur
- Integrasi CI/CD : Built in - Butuh Github Actions atau eksternal

4. Fitur Gitlab
- DevOps All in One Platform : tidak hanya version control tapi juga mencakup planning, coding, testing, deployment dan monitoring  dalam satu platform
- CI/CD Terintegrasi
- Self-hosting & Control Penuh : cocok untuk perushaan yg punya regulasi ketat (sector keuangan, militer atau pemerintahan)
- Manajemen Proyek Terintegrasi
- Keamanan

5. konsep dasar Gitlab
- Strucktur Branch
- Merge Request (MR)
- Best Practice
- Pipeline features : Parallel jobs, Manual Trigger dan Enviroment specific Deployment

6. Tahap umum pipeline di Gitlab :
- Build -> compile code
- Test -> jalankan unit test dan integration test
- Deploy -> Rilis aplikasi ke server staging atau production

7. Branch Gitlab :
- Main/Master Branch :
  - Branch utama yg selalu berisi kode stabil
  - Hanya menerima merge dari branch lain melalui Merge Request (MR)
  - CI/CD pipe line biasanya otomatis melakukan deploy ke production setiap kali ada perubahan di sini
- Best Practice :
  - Tidak boleh commit langsung ke main
  - semua perubahan harus lewat MR + code review
- Develop Branch (optional)
- Feature Branch
- Release Branch

8. Inisialisasi Repository
- git init : membuat repository git baru
- git clone : menyalin repository dari server ke lokal
- git add : menambahkan file tertentu ke staging area sebelum commit
- git commit -m "Pesan commit" : menympan perubahan dengan pesan tertentu
- git pull : mengambil update terbaru dari remote repository dan menggabungkannya ke branch lokal
- git push : mengirim file ke server
- git branch : menampilkan list branch
- git merge : menggabungkan branch tertentu ke branch yg sedang aktif

10. Menangani konflik : jika saat merge atau pull muncul conflict git akan menandai bagian yg bermasalah di file, bagian yg ditandai harus di diputuskan mau menggunakan yg di lokal atau di server.
- Langkah penyelesaian
    - Edit file sesuai kebutuhan
    - hapus tanda <<<<<< ========== >>>>>>>>>>>>
    - simpan file
- git reset --hard : mengembalikan semua file kedalam commit terakhir
- git checkout : membatalkan perubahan di file tertentu saja
- git log : 
- git status :
- git stash : menyimpan perubahan sementra tanpa commit
- git stash pop

## Praktek
- Open link :https://172.236.149.117
- Register
- Login
- buat project baru
- add ssh-key
- buka link https://172.236.149.117/aditya/project-bmkg
- buka terminal coba clone pake ssh : git clone git@172.236.149.117:aditya/project-bmkg.git
- cd project-bmkg

```
#download bmkg.pem
chmod 600 bmkg.pem
ssh-add ~/.ssh/bmkg.pem 
#masukan phasparase : 123456

#Clone repository
git clone git@172.236.149.117:aditya/project-bmkg.git

#buat file
buat info.txt

#update repository
git add .
git commit -m "tambah info.txt"
git push origin main
```
