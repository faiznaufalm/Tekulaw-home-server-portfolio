Manual Deployment Checklist

1. cd /var/www/portfolio
2. git status
3. Check for local modifications
4. git fetch origin
5. Compare local branch with origin/main
6. If working tree is clean:
   git pull
7. Verify deployment:
   curl -s http://localhost
8. Check Nginx if website is inaccessible
9. Confirm git status is clean
