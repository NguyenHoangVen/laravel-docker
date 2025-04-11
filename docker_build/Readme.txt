============================================================
Dockerfile:
============================================================
=>  It is used to build docker image.

    # 🧱 1. Base image
    FROM php:8.2-fpm

    # 🛠️ 2. Cài đặt các extension cần thiết
    RUN docker-php-ext-install pdo pdo_mysql

    # 🗂️ 3. Thiết lập thư mục làm việc
    WORKDIR /var/www/html

    # 📦 4. Copy mã nguồn vào container
    COPY . /var/www/html

    # ⚙️ 5. Gán quyền (tuỳ chọn)
    RUN chown -R www-data:www-data /var/www/html


==============================================================
    dokcker composer
==============================================================
1.services :Defines the containers that will run. Each service is like a named container.
2.build : Used when you want to build a Docker image from a Dockerfile.
3.image: Use an existing Docker image from Docker Hub (or a private registry).
4.container_name: Gives your container a fixed name (instead of random auto-generated names).
5. ports: Maps host ports to container ports.
    ports:
        - "8080:80"   # Host:Container
6. volumnes: Mounts folders/files from your machine to the container.

==============================================================
    Check status container
==============================================================
- docker composer build 
- docker composer up -d

- docker ps #Container dang chay
- docker ps -a # container da tat
- docker inspect <container_name> # kiem tra cu the container
- docker logs <container_name> # check logs cua container