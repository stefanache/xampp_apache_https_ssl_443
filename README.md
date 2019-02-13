<h3>
            How to Create Valid https(SSL protocol on port 443) in localhost for XAMPP / Windows 10
</h3>
<pre>
In the past I seen two very interesting tutorials:
            https://shellcreeper.com/how-to-create-valid-ssl-in-localhost-for-xampp/
            https://florianbrinkmann.com/en/4215/https-virtual-hosts-xampp/
I want to give one guide of creating the url like https://site.test , if already have installed
the xampp  on windows 10.The my xampp is installed on c:\xampp and have control-panel.
My webserver apache work on my localhost at port 8081 so in browser can be called with 
http://localhost:8081 and the www-root directory is c:\xampp\htdocs.
So track the following steps into this procedure:
            1. create one subdirectory crt in directory C:\xampp\apache
               The result will be the directory
                                 C:\xampp\apache\crt
            2. Download the both files(cert.conf, makecert.bat) from my github repository
               and copy in this new C:\xampp\apache\crt\ directory,
               therefore will be 2 files as result:
                                 C:\xampp\apache\crt\cert.conf
                                 C:\xampp\apache\crt\makecert.bat
            3. Run macert.bat and put at first question the response:
                                 site.test
               and the rest accept all.
               The result will be one subdirecory site.test and in this c:\xampp\apache\crt\site.test\
               will be 2 files(server.key,server.crt) as result: 
                 -RSA private key:
                                 c:\xampp\apache\crt\site.test\server.key
                 -Digital autosigned certificate:
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
                                    
                                    
</pre> 

