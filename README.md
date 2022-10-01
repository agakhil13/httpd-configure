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
     servername www.myurl.com
     serveradmin root@IP
     documentroot /var/www/html
     sslengine on
     sslcertificatefile /etc/pki/tls/certs/server.crt
     sslcertificatekeyfile /etc/pki/tls/private/server.key
     </virtualhost>
     ```
    save the file and continue.

#### Generate self-signed certificate using openssl
`openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout server.key -out server.crt`
> Enter all the required details.

> Required files `server.key` and `server.crt` will generate, move the files to `/etc/pki/tls/private/server.key` and `/etc/pki/tls/certs/server.crt` respectively.

#### Restart httpd service
`systemctl restart httpd`

#### Enable https service from firewall
`firewall-cmd --permanent --add-service=https`
`firewall-cmd --reload`





       
