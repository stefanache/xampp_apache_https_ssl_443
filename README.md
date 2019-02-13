<h3>
            How to Create Valid https(SSL protocol on port 443) in localhost for XAMPP / Windows 10
</h3>
<pre>
In the past I seen 2 very interesting links:
            https://shellcreeper.com/how-to-create-valid-ssl-in-localhost-for-xampp/
            https://florianbrinkmann.com/en/4215/https-virtual-hosts-xampp/
I want to reduce the work to create the url like https://site.test  if already have installed
the xampp  on windows 10.The my xampp is installed on c:\xampp and have control pannel.
My webserver apache work on my localhost at port 8081 so in browser can be called with 
http://localhost:8081 and the www-root directory is c:\xampp\htdocs
So track the following steps:
            1. create one subdirectory crt in directory C:\xampp\apache
               The result will be 
                                 C:\xampp\apache\crt
            2. Download the both files and copy in C:\xampp\apache\crt\ directory
                                 cert.conf
                                 makecert.bat
               therefore result 2 files
                                 C:\xampp\apache\crt\cert.conf
                                 C:\xampp\apache\crt\makecert.bat
            3. Run macert.bat and put at first question the response:
                                 site.test
               and the rest accept all.
               The result will be one subdirecory site.test and in this c:\xampp\apache\crt\site.test\
               will be 2 files(server.key,server.crt): 
                 -RSA private key:
                                 c:\xampp\apache\crt\site.test\server.key
                 -Digital autosigned certificate:
                                 c:\xampp\apache\crt\site.test\server.crt
</pre>

