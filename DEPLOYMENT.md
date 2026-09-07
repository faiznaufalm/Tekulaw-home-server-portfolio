# Deployment Workflow

## Architecture

Developer
   |
   | git push
   v
GitHub Repository
   |
   | git pull
   v
Ubuntu Server
   |
   v
/var/www/portfolio
   |
   v
Nginx
   |
   v
HTTP :80

## Manual Deployment

### 1. Check repository state
cd /var/www/portfolio
git status
Ensure the working tree is clean before deployment.

## 2. Fetch remote changes
git fetch origin

## 3. Pull the latest version
git pull

## 4. Verify deployment
curl -s http://localhost

## 5. Verify repository state
git status

Expected result:

nothing to commit, working tree clean

## Troubleshooting
Git pull rejected because of local changes

Symptom:
error: Your local changes to the following files would be overwritten by merge

Investigation:
git status
git diff

If the local changes are not needed:
git restore <file>
git pull

If the changes need to be preserved, consider committing or stashing them instead.

## Current Deployment Model
GitHub is used for version control and as the remote repository.
Deployment is currently manual. The server administrator runs:
git pull

to update the deployed files.
Nginx serves the files directly from:

/var/www/portfolio

There is currently no automated CI/CD pipeline.
