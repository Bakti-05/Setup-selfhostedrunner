# Self Host Runner

### 1. set up repository
```bash
# Pada direktori baru
git init
git add README.md
git commit -m 'initial commit'
git branch -M main
git remote add origin git@github.com:<user_github>/<nama_repository>.git
git push -u origin main
```

### 2. set up self hosted runner
Masuk ke repository pada github :
> 1. Settings > Actions > Runners > New self-hosted runner
> 2. Pilih os requirement yang digunakan (disini menggunakan Linux)
> 3. Ikuti step pada : Download, dan Configure (tidak usah running run.sh terlebih dahulu)

### 3. testing
```
# pada working directory buat folder dengan nama : .github/workflows
# buat file baru didalam direktori yang baru dibuat, misal sample.yml

on: [push]

jobs:
  build:
    runs-on: self-hosted
    steps:
    - name: Checkout code
      uses: actions/checkout@v2
    - name: Run a one-line script
      run: echo Hello, world!

git add .github/<tab>
git commit -m 'menambahkan file sample'
# masuk ke linux interface dan jalankan ./run.sh
./run.sh
# masuk ke working direktori interface
git push -u origin main
```

### 4. cek action
Masuk ke dalam repository :
> 1. Pilih menu action > all workflows
> Monitor perubahan pada workflow runs
> monitor juga perubahan job pada Linux interface 
> Cek perubahan commit
```bash
$ ls _diag/
```
