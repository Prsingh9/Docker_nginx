## Deploy an Nginx Web Server with Docker

## Goal
Run an Nginx server using Docker.

## Prerequisites
- Install Docker on your system.

## Step 1: Pull the Nginx Image
Run the following command to pull the official Nginx image:
```bash
docker pull nginx
```

## Step 2: Run an Nginx Container
Start a container and map port 80 to access it from your browser:
```bash
docker run -d -p 8080:80 --name my-nginx nginx
```
Now, open [http://localhost:8080](http://localhost:8080) in your browser, and you should see the Nginx welcome page.

## Step 3: Customize Nginx with Your Own HTML Page

1. Create a directory for your Nginx files:
   ```bash
   mkdir nginx_project && cd nginx_project
   ```

2. Create an `index.html` file inside this directory:
   ```html
   <!DOCTYPE html>
   <html>
   <head>
       <title>My Dockerized Nginx</title>
   </head>
   <body>
       <h1>Hello, this is a custom Nginx page inside Docker!</h1>
   </body>
   </html>
   ```

3. Run a new Nginx container with your custom HTML page:
   ```bash
   docker run -d -p 8081:80 --name custom-nginx -v $(pwd):/usr/share/nginx/html nginx
   ```

4. Refresh [http://localhost:8081](http://localhost:8081), and you should see your custom page.
