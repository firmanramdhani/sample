# Panduan Pembelajaran Git (Tahap Awal) 🚀

Selamat datang di repositori latihan Git! Repositori ini dirancang khusus sebagai panduan dan tempat latihan dasar bagi pemula yang baru memulai belajar Version Control System menggunakan **Git**.

---

## 📌 Daftar Isi
1. [Prasyarat & Konfigurasi Awal](#-prasyarat--konfigurasi-awal)
2. [Konsep Dasar Git](#-konsep-dasar-git)
3. [Perintah Dasar Git yang Sering Digunakan](#-perintah-dasar-git-yang-sering-digunakan)
4. [Latihan Praktik Mandiri (Langkah demi Langkah)](#-latihan-praktik-mandiri-langkah-demi-langkah)
5. [Tips Menulis Pesan Commit yang Baik](#-tips-menulis-pesan-commit-yang-baik)
6. [Apa itu .gitignore?](#-apa-itu-gitignore)

---

## 🛠️ Prasyarat & Konfigurasi Awal

Sebelum mulai, pastikan Git sudah terpasang di komputer Anda. Periksa dengan perintah:

```bash
git --version
```

### Konfigurasi Identitas
Jika baru pertama kali memasang Git, atur nama dan email Anda (digunakan sebagai identitas pembuat commit):

```bash
git config --global user.name "Nama Lengkap Anda"
git config --global user.email "emailanda@example.com"
```

Cek konfigurasi yang sudah tersimpan:
```bash
git config --list
```

---

## 🧠 Konsep Dasar Git

Git bekerja dengan 3 area utama di komputer lokal Anda:

```text
[ Working Directory ]  --->  git add  --->  [ Staging Area ]  --->  git commit  --->  [ Git Repository ]
 (File yang diedit)                          (File siap simpan)                         (Riwayat tersimpan)
```

1. **Working Directory**: Tempat Anda membuat atau mengedit file.
2. **Staging Area**: Area persiapan untuk memilih perubahan mana saja yang akan disimpan.
3. **Repository (.git)**: Tempat Git menyimpan seluruh riwayat perubahan secara permanen.

---

## 📋 Perintah Dasar Git yang Sering Digunakan

| Perintah | Deskripsi |
| :--- | :--- |
| `git init` | Membuat repositori Git baru di folder saat ini |
| `git status` | Melihat status file (untracked, modified, staged) |
| `git add <file>` | Memindahkan file ke Staging Area |
| `git add .` | Memindahkan semua perubahan file ke Staging Area |
| `git commit -m "pesan"` | Menyimpan perubahan ke repository dengan pesan keterangan |
| `git log --oneline` | Melihat riwayat commit dalam format ringkas |
| `git diff` | Melihat detail perubahan baris kode sebelum di-stage |
| `git branch` | Melihat daftar branch yang ada |
| `git branch <nama-branch>` | Membuat branch baru |
| `git switch <nama-branch>` | Berpindah ke branch lain |
| `git merge <nama-branch>` | Menggabungkan branch lain ke branch saat ini |

---

## 🎯 Latihan Praktik Mandiri (Langkah demi Langkah)

Cobalah ikuti skenario latihan sederhana berikut di terminal:

### 1. Periksa Status Repositori
```bash
git status
```

### 2. Buat File Baru
Buat sebuah file catatan, misalnya `catatan.txt`:
```bash
echo "Halo, saya sedang belajar Git!" > catatan.txt
```

### 3. Masukkan ke Staging Area
```bash
git add catatan.txt
```
Periksa kembali dengan `git status` (nama file akan berwarna hijau).

### 4. Simpan Perubahan (Commit)
```bash
git commit -m "feat: tambahkan file catatan belajar"
```

### 5. Cek Riwayat Commit
```bash
git log --oneline
```

### 6. Latihan Percabangan (Branching)
```bash
# Buat dan pindah ke branch baru
git switch -c fitur-baru

# Edit atau buat file baru di branch ini
echo "Fitur tambahan sedang dikerjakan" >> catatan.txt

# Simpan di branch fitur-baru
git add catatan.txt
git commit -m "feat: tambahkan detail pada catatan"

# Kembali ke branch utama (master / main)
git switch master

# Gabungkan perubahan dari fitur-baru ke master
git merge fitur-baru
```

---

## ✍️ Tips Menulis Pesan Commit yang Baik

Gunakan pesan commit yang jelas dan deskriptif. Format yang umum digunakan adalah format *Conventional Commits*:

- `feat:` untuk penambahan fitur baru (contoh: `feat: tambah halaman login`)
- `fix:` untuk perbaikan bug/kesalahan (contoh: `fix: perbaiki validasi form email`)
- `docs:` untuk perubahan dokumentasi (contoh: `docs: perbarui panduan instalasi di README`)
- `refactor:` untuk merapikan kode tanpa mengubah fungsi

---

## 🙈 Apa itu `.gitignore`?

File `.gitignore` digunakan untuk memberitahu Git file atau folder apa saja yang **tidak perlu dilacak** (misalnya file konfigurasi rahasia, folder `node_modules/`, file sementara `.DS_Store`, dsb).

Contoh isi `.gitignore`:
```text
.DS_Store
*.log
node_modules/
.env
```

---

Selamat belajar dan berlatih Git! 🎉
