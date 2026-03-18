# Static Website Deployment on EC2 with Nginx

A simple static website built with HTML and CSS, deployed on an AWS EC2 instance using Nginx on port 80.

---

## Project Structure
travel-website/

├── index.html  
├── styles.css


---

## Prerequisites

- AWS EC2 instance with Linux (Ubuntu/CentOS/Alpine)  
- Nginx installed and running  
- Security group allowing inbound HTTP (port 80) traffic

---

## Deployment Steps

1. **Connect to your EC2 instance**:

```bash
ssh -i key.pem ec2-user@<ec2-public-ip>
```
  
2. **Install Nginx (if not already installed)**:

For Ubuntu/Debian:
```
sudo apt update
sudo apt install nginx -y
```  
3. **Start and enable Nginx**:
```
sudo systemctl start nginx
sudo systemctl enable nginx
```  
4. **Upload website files**:
Copy your HTML, CSS, and other assets to Nginx's default web directory:
```
sudo cp -r /local/path/* /var/www/html/
```
  
5. **Set proper permissions**:
```
sudo chown -R www-data:www-data /var/www/html
sudo chmod -R 755 /var/www/html
```  
6. **Test Website**:
Open a browser and go to:
```
http://<ec2-public-ip>/
```
  
**Notes

Nginx serves static files by default from /var/www/html/.  
Port 80 must be open in your EC2 Security Group.  
For future updates, simply replace files in /var/www/html/ and reload Nginx:**

```
sudo systemctl reload nginx
```
Author  
Hassan Mehmood
