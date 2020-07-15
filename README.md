# Bypass File Upload on Koken CMS
This repo explain how to bypass File Upload Restrictions on Koken CMS - 0.22.24 (authenticated)

_____________________________________________________________________
## About Koken CMS
Koken is a free content management system designed for photographers, designers and artists.

Website: http://koken.me/ 

Koken CMS is avaiable on Softaculous too: https://www.softaculous.com/apps/cms/Koken

_____________________________________________________________________
## Bypass File Upload Restrictions (PoC)

The Koken CMS upload restrictions are based on a list of allowed file extensions (withelist), which facilitates bypass through the handling of the HTTP request via Burp.

After you are logged in to Koken CMS Admin Panel, select the "Import Content" option

![1](http://sejalivre.org/poc3/k1.png)

![1](http://sejalivre.org/poc3/k2.png)


As a proof of concept, I created a PHP file with the function `phpinfo()` and saved it with a double extension (image.php.jpg)

![1](http://sejalivre.org/poc3/k3.png)


I selected the `image.php.jpg` file and forwarded the request to Burp

![1](http://sejalivre.org/poc3/k4.png)


In Burp, I changed the file extension to `.php`

![1](http://sejalivre.org/poc3/k5.png)

![1](http://sejalivre.org/poc3/k6.png)


Back in the image library, there is a "Download File" button that shows where the malicious file was saved on the server.

![1](http://sejalivre.org/poc3/k7.png)


Just access it and confirm the proof of concept.

In this scenario, an attacker could send a reverse shell, for example, in order to compromise the server.

![1](http://sejalivre.org/poc3/k8.png)
