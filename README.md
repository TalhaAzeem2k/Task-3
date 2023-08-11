# Task-3
Docker Volumes

##Step1
C:\Users\hamza\Desktop\Coding>docker volume create my_volume
my_volume

###Step2
docker run -d --name my_nginx_container -v my_volume:/usr/share/nginx/html -p 8080:80 nginx
b22ef50baf67c6571b69be135032ce4cadd4ac9eaa6183a91221e8d8e8bd3f1e

####Step3
docker cp index.html my_nginx_container:/usr/share/nginx/html/
Successfully copied 2.05kB to my_nginx_container:/usr/share/nginx/html/

#####Step4
docker stop my_nginx_container
my_nginx_container

######Step5
docker rm my_nginx_container
my_nginx_container

#######Step6
docker run -d --name my_httpd_container -v my_volume:/usr/local/apache2/htdocs -p 8081:80 httpd
Unable to find image 'httpd:latest' locally
latest: Pulling from library/httpd
648e0aadf75a: Already exists
c76ba39af630: Pull complete
b9819ffb14ec: Pull complete
37baa60548e6: Pull complete
6dbce5de7542: Pull complete
Digest: sha256:d7262c0f29a26349d6af45199b2770d499c74d45cee5c47995a1ebb336093088
Status: Downloaded newer image for httpd:latest
9fc3ec2a1e5c8ee8a2eb6f4db422516b618a9c280217f5de706705f51f456f06

########Step6
docker run -d --name my_httpd_container -v my_volume:/usr/local/apache2/htdocs -p 8081:80 httpd
docker: Error response from daemon: Conflict. The container name "/my_httpd_container" is already in use by container "9fc3ec2a1e5c8ee8a2eb6f4db422516b618a9c280217f5de706705f51f456f06". You have to remove (or rename) that container to be able to reuse that name.
See 'docker run --help'.

#########Step7
docker cp about.html my_httpd_container:/usr/local/apache2/htdocs/
Successfully copied 2.05kB to my_httpd_container:/usr/local/apache2/htdocs/


##########Step8
docker stop my_httpd_container
my_httpd_container

###########Step9
docker rm my_httpd_container
my_httpd_container

############Step10
docker volume rm my_volume
my_volume
