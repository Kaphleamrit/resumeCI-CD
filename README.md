# Static Website Hosting on AWS S3 with GitHub Actions [Live Deployment](http://kaphley-resume-website.s3-website-us-east-1.amazonaws.com)
This project demonstrates how to host a static website on Amazon S3 and automate deployment using GitHub Actions. When you push a new change to your GitHub repository's `main` branch, the updated files are automatically deployed to your S3 bucket.

## Project Structure

- **`index.html`**: The main HTML file of the website.
- **`style.css`**: The stylesheet for the website.
- **`.github/workflows/deploy.yml`**: GitHub Actions workflow for automated deployment to S3.

## Prerequisites

- An AWS account with S3 configured.
- A GitHub repository with GitHub Actions enabled.
- AWS CLI configured with the necessary access permissions.
- A registered domain (optional), or you can use the S3 website URL for access.

## Setup Instructions

### 1. Create an S3 Bucket
1. Log into your AWS account and create a new **S3 bucket**.
2. Enable **static website hosting** for the bucket.
3. Note the S3 bucket name and website endpoint.

### 2. Set Up GitHub Actions for Deployment
1. Create a GitHub repository or use an existing one.
2. Add the provided `deploy.yml` file under `.github/workflows/`.
3. Configure **AWS Secrets** in GitHub:
    - Go to your repository’s **Settings** > **Secrets and variables** > **Actions** > **New repository secret**.
    - Add your **AWS_ACCESS_KEY_ID** and **AWS_SECRET_ACCESS_KEY**.

### 3. Modify `deploy.yml`
1. Update the **bucket name** in the `deploy.yml` file to point to your S3 bucket.
2. Optionally, add exclusions if you don't want to deploy certain files or folders.

### 4. Deploy Changes Automatically
1. After setting up the workflow, push changes to the `main` branch.
2. GitHub Actions will automatically deploy the updated content to your S3 bucket.

## Custom Domain (Optional)
If you have a custom domain, you can set up Route 53 to point to your S3 bucket for seamless access to your static website.

### Example Domain Setup
- **Subdomain**: `www.example.com` (points to the S3 bucket).
- **DNS Records**: Add A records or CNAME records in Route 53 to point to the bucket URL.

## License

This project is open-source and available under the [MIT License](LICENSE).

---

Enjoy hosting your static website on AWS S3!
