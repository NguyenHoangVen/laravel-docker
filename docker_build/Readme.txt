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
    docker composer
==============================================================
1. services :Defines the containers that will run. Each service is like a named container.
2. build : Used when you want to build a Docker image from a Dockerfile.
3. image: Use an existing Docker image from Docker Hub (or a private registry).
4. container_name: Gives your container a fixed name (instead of random auto-generated names).
5. ports: Maps host ports to container ports.
    ports:
        - "8080:80"   # Host:Container
6. volumnes: Mounts folders/files from your machine to the container.


==============================================================
    Docker build
==============================================================
- docker composer build 
- docker composer up -d
- docker-compose down               # Stop and remove all container

==============================================================
    Docker container
==============================================================
- docker ps                         # Container is running
- docker ps -a                      # Container if off
- docker inspect <container_name>   # Check container
- docker logs <container_name>      # Check logs of container
- docker exec -it <container_id> sh # SH into container
- docker rm <container_name_or_id>  # Remove container

==============================================================
    Docker image
==============================================================
- docker images                     # List image
- docker inspect <image_id_or_name> # Information of image
- docker rmi <image_id>             # Remove image
- docker rmi $(docker images -q)    # Remove all images