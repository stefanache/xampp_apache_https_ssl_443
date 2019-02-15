<h3>
            How to Create Valid https(SSL protocol on port 443) in localhost for XAMPP / Windows 10
</h3>
<pre>
In the past I seen two very interesting tutorials:
            https://shellcreeper.com/how-to-create-valid-ssl-in-localhost-for-xampp/
            https://florianbrinkmann.com/en/4215/https-virtual-hosts-xampp/
but exist and others tutorials linked of this X.509 subject  like:          
            https://www.slideshare.net/jcleblanc/php-identity-and-data-security
            https://www.devdungeon.com/content/creating-self-signed-ssl-certificates-openssl
<br/>            
I want to give one guide of creating the url like https://site.test , if already have installed
the xampp  on windows 10.The my xampp is installed on c:\xampp and have control-panel.
My webserver apache work on my localhost at port 8081 so in browser can be called with 
http://localhost:8081 and the www-root directory is c:\xampp\htdocs.
<br/>
So track the following 10 steps into this manually procedure:
            1. create one subdirectory crt in directory C:\xampp\apache
               The result will be the directory
                                 C:\xampp\apache\crt
            2. Download the files cert.conf, makecert.bat from my github repository
               and copy in this new C:\xampp\apache\crt\ directory,
               therefore will be 2 files as result:
                                 C:\xampp\apache\crt\cert.conf
                                 C:\xampp\apache\crt\makecert.bat
            3. Run macert.bat and put at first question the response:
                                 site.test
               and the rest accept all.
               The result will be one subdirecory site.test and in this c:\xampp\apache\crt\site.test\
               will be 2 files(server.key,server.crt) as result: 
                 -RSA private-key(private-key used for writting/encryption+sign to sending the message):
                                 c:\xampp\apache\crt\site.test\server.key
                 -Digital auto-signed or self-signed certificate:
                 (certificate which contain public-key used at receiving for reading/decryption message, 
                  after verification/validation of the certificate):
                                 c:\xampp\apache\crt\site.test\server.crt
            4. Go and click on this certificate  c:\xampp\apache\crt\site.test\server.crt
               and install for windows(so and for browsers) this certificate(wich contain public key)
               -click on button 
                                                Install certificate                                 
               -select the option
                                                Locale amchine
                and then click on the button    Next 
               -select the option               Place all certificate in the following store
                and then click on the button    Browse
               -select the option
                                                Trusted Root Certification Authorities
                and then click on the button    OK
                and then click on the button    Next
                and finally click on the button Finish
            5. Edit as administrator the file(hosts):
                                    C:\Windows\System32\drivers\etc\hosts
               and append(add) this new line:
                                    127.0.0.1 site.test
               check in browser to see if work this:
                                    http://site.test
               You must to see same you put in browser the address(URL)
                                   http://localhost
               Remark: in my case is http://site.test:8081 or http://localhost:8081                    
            6. Create subdirectory site_test_80 in  c:\xampp\htdocs\   directory and put the file 
                                    c:\xampp\htdocs\site_test_80\index.file 
               with content 
                                    site-test port  80
            7. Create subdirectory site_test_443 in  c:\xampp\htdocs\   directory and put the file 
                                    c:\xampp\htdocs\site_test_443\index.file 
               with content 
                                    site-test port 443
            8. download from my github repository and copy content from file httpd-xampp.conf and 
               add/append this content at the bottom of file  
                                    C:\xampp\apache\conf\extra\httpd-xampp.conf
            9. restart the apache httpd server from xampp control panel 
                                    stop apache
                                    start apache
           10. check in the browser the https URL:
               -restart the your browser before at all and put the following address(URL):
                                   https://site.test
                Now you must to see the content
                                   site-test port 443
               -Also you can verify if work and the older URLs
                                   http://site.test       (http://site.test:8081 in my case)
                                   http://localhost       (http://localhost:8081 in my case)
 That is all!
   
 Remark: The name for locally site is arbitrary(randomly)  you can take other like site.dev or other any!
         But must to change all use this new name in this procedure and in all files used!
</pre> 


