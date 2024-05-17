# projek untuk mencoba connect ke git server

## dengan self host runner
### 1. set up repository
```
# login ke akun github
# buat repository baru, dan koneksikan ke local git
# di localhost, buat directory baru
git init
# buat file README.md
git add README.md
git commit -m 'commit pertama'
git branch
# setting branch utama (karena saya lebih nyaman menggunakan branch main daripada master)
git branch -M main
git remote add origin git@github.com:<user_github>/<nama_repository>.git
git push -u origin main
```

### 2. set up self hosted runner
```
# masuk ke repository pada github
# Settings > Actions > Runners > New self-hosted runner
# pilih os requirement yang digunakan (disini menggunakan Linux)
# ikuti step pada : Download, dan Configure (tidak usah running run.sh terlebih dahulu)
```
### 3. testing
```
# pada working directory buat folder dengan nama : .github/workflows
# buat file baru didalam direktori yang baru dibuat, misal sample.yml
```
on: [push]

jobs:
  build:
    runs-on: self-hosted
    steps:
    - name: Checkout code
      uses: actions/checkout@v2
    - name: Run a one-line script
      run: echo Hello, world!
```
git add .github/<tab>
git commit -m 'menambahkan file sample'
# masuk ke linux interface dan jalankan ./run.sh
./run.sh
# masuk ke working direktori interface
git push -u origin main
```
### 4. cek action
```
# masuk ke dalam repository
# pilih menu action > all workflows
# monitor perubahan pada workflow runs
```