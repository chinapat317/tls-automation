# Certificate managing
1. Seperation concern of each part of application by
  ##### Certificate managing container:  
  - requests certificate  
  - renews certificate  
  - writes certificate files  
  ##### Proxy/Gateway container:  
  - reads certificate files  
  - terminates HTTPS  
  ##### Application container:  
  - serves application content only  
  - does not know about TLS certificate files  
  In case that every services have to use certificate to connect between services make each services trust CA which is managed by Certificate managing instead of trust the certificate file directly to make process easier to revoke or assign new certificate to services.  
2. Storage of certificate.  
  In case of self managing with medium security. Storing inside the infrastructure of system(/etc/cert) is easier to access than other path and safe than inside application directory  
  In case of self managing with high security. Storing inside secure third party storage e.g. AWS secret manager would be safer than inside the application server.
3. Create automate renewal by using certificate managing service to trigger services that get renew certificate to reboot instead of manually renew and reboot to lower services down time.  
