# Yuk pake Docker :)

# Docker with php dan phpmyadmin

**Deskripsi Singkat:** Ini adalah folder untuk starter penggunaan php di docker.

**Spesifikasi**

- PHP 8.2.12 (bisa disesuaikan kembali)
- mysqli
- phpmyadmin

**Prasyarat**

- Docker

**Instalasi**

1. Clone repository:

```
   git clone https://github.com/ztxdy-web/docker-init-php.git
```

2. Ubah version php sesuai dengan kebutuhan di _Dockerfile_

```
    FROM php:8.2.12-apache as final
```

3. Buatlah file baru didalam folder db yang berisi password.txt, isilah file tersebut dengan password db yang baru.

4. Sesuaikan port utama yang akan digunakan pada file compose.yaml

```
  server:
    build:
      context: .
    ports:
      - 9000:80 -> saya menggunakan port 9000 di komputer dan port 80 di kontainer
```

5. Setelah itu buka terminal/cmd pada folder tersebut dan jalankan

```
    docker compose up --build
```

6. Jika sudah berhasil anda bisa mengecheck apakah sudah berjalan dengan cara membuka **http://localhost:9000** atau port yang tadi telah disesuaikan

Reference:

https://docs.docker.com/guides/php/containerize/
