# Git Version Control

# Rebase Demo
## 1. Membuat Repository
 ```bash
# Buat direktori baru dan masuk ke dalamnya
  mkdir git-rebase-demo && cd git-rebase-demo
  
  # Inisialisasi git
  git init
  
  # Buat file pertama dan commit ke main
  echo "File pertama" > file.txt
  git add file.txt
  git commit -m "Menambahkan file pertama"
  
  # Buat branch feature
  git checkout -b feature
  
  # Tambahkan perubahan di branch feature
  echo "Perubahan di feature branch" >> file.txt
  git add file.txt
  git commit -m "Menambahkan perubahan di feature branch"
  
  # Kembali ke main dan buat perubahan baru
  git checkout main
  echo "Perubahan di main branch" >> file.txt
  git add file.txt
  git commit -m "Menambahkan perubahan di main branch"

```
## 2. Melakukan Rebase
 ```bash
git checkout feature
git rebase main
```

## 3. Menangani Konflik Saat Rebase
 ```bash
# Jika ada konflik, edit file secara manual
 nano file.txt  # Atau gunakan VS Code, Vim, atau editor lain
    
 # Setelah menyelesaikan konflik, lanjutkan rebase
 git add file.txt
 git rebase --continue
```

## 4. Push Perubahan Setelah Rebase
```bash
  git push origin feature --force
 # --force bisa menghapus riwayat commit di remote, gunakan dengan hati-hati, terutama jika bekerja dalam tim.
```
