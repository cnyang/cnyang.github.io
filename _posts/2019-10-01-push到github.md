---
layout: post
title: "push to github"
categories:
  - Note
tags:
---
## push到github
```
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_rsa_github
ssh-add -l -E md5 確定有東西
cd /var/www/html/slifeoss-web/
git push


```

