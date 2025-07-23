hi v5
---

## 🔄 CI/CD Support

This repo is ready for CI/CD automation.

- ✅ **GitHub Actions**: Sample workflow to deploy via SSH  
  → See `.github/workflows/deploy.yml`

- ✅ **GitLab CI/CD**: Included `.gitlab-ci.yml` as example  
  → Useful if migrating pipelines or hybrid setup

The deployment uses:
- Auto SSH to VPS (via key)
- Git pull & `docker compose up -d`
- Easily extensible for real-world pipelines
