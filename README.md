# **Networks we support**
- Cosmos
- Akash
- Quicksilver
- Juno
- Tgrade
- Stargaze
- Desmos
-  Regen

# **Steps to Deploy the Application**



### 1. Clone the repo

```bash
git clone https://github.com/Ritvik32/SnapShotService.git

```

### 2.Go inside the project folder inside which all the files are present and then do the following:
```bash
npm install
```

### 3a. To run in the Dev mode do the follwoing:
```bash
npm run dev --host
```
### 3b. To run in the Production mode do the follwoing:
```bash
npm run build
```
# **Steps to setup nginx**

### 1. First we have to install nginx on the machine check whether nginx is present on the server if not then run the commands to install the nginx:
- ```sudo apt update```
- ```sudo apt install nginx -y```

### 2. So now nginx is installed on the server go to this path /var/www/html and paste the dist file content which you got from the npm run build command.
and now we have to write the nginx configuration file so for that go to this directory /etc/nginx/site-available/ and create a file using nano with any name here I am creating file with witval name and paste the below content in the file.


```bash
server {
    server_name www.example.com;
    root /var/www/html;
    index index.html;
    location / {
       try_files $uri $uri/ /index.html;
    }
    location /api {
        proxy_pass http://localhost:3000;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
    }
}
```
### 3. Now we have to link our nginx configuration file with site-enabled directory so run the following command:
```sudo ln -s /etc/nginx/site-available/witval   /etc/nginx/site-enabled```





# **Steps to setup TLS**

### 1. ```sudo apt install certbot python3-certbot-nginx```
### 2. ```sudo certbot --nginx```



# **Add Additional Networks**
To add additional networks to the front end [Click here](./NETWORK.md)
