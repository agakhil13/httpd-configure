### Setting SSL on centos server using httpd

#### Install httpd
`yum install httpd`

#### Install mod_ssl
`yum install mod_ssl`

#### Install openssl
`yum install openssl`

#### Create config file under httpd directory
- `cd /etc/httpd/conf.d/`
- `vi webserver.conf`
     ```console
     <virtualhost *:443>
     
     </virtualhost>

     ```
       
       
