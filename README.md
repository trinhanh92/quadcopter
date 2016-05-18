# How to use:
### Libraries

 1. **libmicrohttpd** (http server api)
 - download [lastest libmicrohttpd](http://ftpmirror.gnu.org/libmicrohttpd/libmicrohttpd-0.9.49.tar.gz)
 - install:
> ./configure
> make
> sudo make install

 - usage:
> include "microhttpd.h"

 2.  **openssl** (used for md5 encryption)
 - download
>sudo apt-get install libssl-dev 

 - usage:
> include "openssl/md5.h"

 3. **json** (used for json string parsing)
 + download: clone soure [here](https://github.com/zserge/jsmn)
 + install :
>  copy libjsmn.a to "libraries/json" folder  
    include "jsmn.h"

### Folder structure:

>--> app/                		// main application
--> libraries/          		// contain libraries used for app
    		    --> json/           // json lib
--> README.md           // this file - project guide
--> testcase_curl.txt 

### Build and Run:
 >cd app/
 make
 ./quadcopter
 
###Test with cURL:
- open other terminal window
- try to use testcase in file `testcase_curl.txt`
- Note that: Change 'localhost' by your remote device'sIP
###Note:
Port forwarding 80 to 8080:
>sudo iptables -t nat -A OUTPUT -o lo -p tcp --dport 80 -j REDIRECT --to-port 8080

Run following command to auto port forwarding on boot:
>sudo sh -c "iptables-save > /etc/iptables.rules"