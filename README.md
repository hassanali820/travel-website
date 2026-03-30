# Static Website Hosting on AWS S3

## Project Overview

This project demonstrates how to host a simple static website using AWS S3.
The website consists of basic HTML and CSS files and is publicly accessible via an S3 static website endpoint.

---

## Technologies Used

* AWS S3 (Simple Storage Service)
* HTML5
* CSS3

---

## Project Structure

```bash
├── index.html
├── style.css
└── README.md
```

---

## Steps to Deploy

### 1. Create an S3 Bucket

* Go to AWS S3 console
* Create a bucket with a unique name
* Disable **Block all public access**

---

### 2. Upload Files

* Upload `index.html` and `style.css` to the bucket

---

### 3. Configure Bucket Policy (Public Access)

Add the following bucket policy to allow public access to all files:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadGetObject",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::hassan-first-static-site/*"
    }
  ]
}
```

> Replace `hassan-first-static-site` with your actual bucket name.

---

### 4. Enable Static Website Hosting

* Go to **Properties → Static Website Hosting**
* Enable hosting
* Set:

  * Index document: `index.html`

---

### 5. Access Website

* Use the **S3 Website Endpoint URL** to access your live website

---

## Live Demo

👉 http://your-bucket-name.s3-website-region.amazonaws.com

*(Replace with your actual endpoint URL)*

---

## Notes

* Ensure bucket policy allows public read access
* Make sure file paths in `index.html` are correct
* S3 static websites support only HTTP (not HTTPS)

---

## Learning Outcome

* Understanding of AWS S3
* Hosting static websites in the cloud
* Managing permissions and bucket policies

---

## 👨‍💻 Author

Hassan Mehmood
Cloud & DevOps Engineer
