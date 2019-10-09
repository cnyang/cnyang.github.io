---
layout: post
title: "crontab install"
categories:
  - Note
tags:
---
## crontab install
crontab -e

*/1 * * * * /var/www/html/slifeoss-web/storage/crontabJob/test.py

test.py:

    #!/usr/bin/python3
    import logging
    logging.basicConfig(level=logging.DEBUG,
                         format='%(asctime)s - %(levelname)s : %(message)s',
                         filename='/var/www/html/slifeoss-web/storage/crontabJob/mylog.txt')
    logging.info("info message")

chmod [+x test.py](https://paper.dropbox.com/doc/x-test.py-RcPfKGOpfoAxEG5DcCwKw) 


30 16 * * * /var/www/html/slifeoss-web/storage/crontabJob/bindUserAccountToAdmin.py >/dev/null 2>&1

0 0 1 */3 * psql -U postgres -s smartlife -a -f /var/www/html/slifeoss-web/storage/crontabJob/updatePassPer3M.sql >/dev/null 2>&1


