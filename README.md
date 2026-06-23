# Portfolio Website

## Overview

This repository contains the code for a personal portfolio website built using HTML, CSS, and JavaScript. The website showcases personal projects, skills, and contact information. It is designed to be deployed to AWS S3 for hosting. It includes an `index.html` file for the homepage and an `error.html` file for error handling.

## Technologies Used

- Frontend: HTML, CSS, JavaScript
- Deployment: AWS S3

## Prerequisites

Before you begin, ensure you have met the following requirements:

- AWS account with access to S3
- Basic knowledge of HTML, CSS, and JavaScript

## Project Structure

- `index.html`: The main HTML file for the portfolio.
- `styles.css`: The main CSS file for styling the portfolio.
- `script.js`: The JavaScript file for interactivity and additional functionality.
- `images/`: Directory containing image assets used in the portfolio.

## Setting Up the S3 Bucket
1. Create an S3 Bucket:
   - Go to the AWS S3 console.
   - Click on "Create bucket".
   - Enter a unique bucket name and choose your preferred region.
   - Uncheck "Block all public access" and acknowledge the warning.

2. Upload Files:
   - Upload `index.html` and `error.html` to your S3 bucket.

3. Configure Static Website Hosting:
   - Select the bucket and go to the "Properties" tab.
   - Scroll down to "Static website hosting".
   - Choose "Use this bucket to host a website".
   - Enter `index.html` for the index document and `error.html` for the error document.

4. Set Bucket Policy:
   - Go to the "Permissions" tab.
   - Edit the bucket policy to allow public access:
   ```json
   {
     "Version": "2012-10-17",
     "Statement": [
       {
         "Sid": "PublicReadGetObject",
         "Effect": "Allow",
         "Principal": "*",
         "Action": "s3:GetObject",
         "Resource": "arn:aws:s3:::portfoliosurvey2/*"
       }
     ]
   }

