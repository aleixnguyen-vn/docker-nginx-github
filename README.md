# 🚀 Docker Nginx Auto Deployment with GitHub Actions

This repo demonstrates a simple yet powerful setup to automatically deploy a **Nginx + PHP-FPM** web app using **Docker**, **GitHub Actions**/**GitLab CI/CD**, and **IaC** via **Terraform on Vultr**.

---

## ✅ Tech Stack

* 🐳 **Docker** + **Docker Compose**
* 📡 **Nginx + PHP-FPM**
* 🔁 **CI/CD with GitHub Actions**
* 🌩️ **Terraform (IaC) on Vultr VPS**

---

## 📦 What's Included

* Nginx config optimized with gzip, cache headers, and PHP proxying
* Dockerfile + Docker Compose for Nginx and PHP
* GitHub Actions workflow that:

  * SSH into the VPS
  * Pull latest code
  * Run Docker Compose up

---

## 🏗️ Step 1: Spin Up VPS via IaC

Use the [iac-vultr-terraform](https://github.com/aleixnguyen-vn/iac-vultr-terraform) repo to spin up a fresh Vultr VPS:

### 🔧 What It Does:

* Provision Ubuntu 24.04 server (AMS region)
* Inject your SSH key
* Auto-install Docker
* Clone this repo & auto-deploy app

Compatible with **GitLab CI/CD** and **GitHub Actions** – fully automated.

➡️ After provisioning, server is ready for deploy.

---

## 🔁 Step 2: Auto Deploy with GitHub Actions

### 📁 `.github/workflows/deploy.yml`

The workflow does:

1. SSH into the VPS
2. Pull latest code
3. Run `docker compose` to rebuild and deploy

### 🔐 Required GitHub Secrets:

| Name              | Description                         |
| ----------------- | ----------------------------------- |
| `VPS_USER`        | SSH user to connect to VPS          |
| `VPS_IP`          | Public IP of your VPS               |
| `SSH_PRIVATE_KEY` | Private SSH key for deploy access   |
| `APP_DIR`         | Remote directory to deploy app into |

### 🚀 Trigger:

* On every push to `main` branch

---

## 💥 Debug Logs

* ❌ First run failed due to wrong `cd` command → fixed in rerun
* ✅ Second run passed — site deployed & live: [http://139.180.189.131/](http://139.180.189.131/)

---

## 📸 Screenshots (Add Yours)

#### ✅ GitHub Actions passed log (Check the Actions tab)
![Github Actions log](/screenshots/github_actions_log.png)

#### ✅ GitLab CI/CD passed log
![GitLab CI/CD log](/screenshots/gitlab_success.png)


#### 🌐 NGINX + PHP-FPM work flawlessly

![NGINX and PHP-FPM worked!](/screenshots/nginx_php-fpm_work_perfectly.png)

---

## 📌 Useful Links

* [Terraform IaC Repo](https://github.com/aleixnguyen-vn/iac-vultr-terraform)
* [Live App URL](http://139.180.189.131/)

---

**Author:** [@aleixnguyen-vn](https://github.com/aleixnguyen-vn)

PRs & issues welcome!
