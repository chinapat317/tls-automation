# Prerequisite
- git
- docker
- docker-compose

# Procedure
1. Run "git clone git@github.com:chinapat317/tls-automation.git
2. Run "cd tls-automation" to get in cloned directory
3. Edit file nginx/init.conf to change domain and server name to your domain
4. Edit file nginx/nginx.conf to change domain and server name to your domain
5. Run "docker compose -f docker-compose.init.yml up --build -d" to start certbot and nginx to initiate certificate first time.
6. Run "docker compose -f docker-compose.init.yml down" to stop all services.
7. Run "docker compose -f docker-compose.def.yml up --build -d" to start certbot and nginx to use certificate and setting in nginx.conf which will auto checking every 12 hours and renew with nginx reboot if expire.