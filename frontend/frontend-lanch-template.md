#!/bin/bash
dnf update -y
dnf install -y nginx git
cd /home/ec2-user
git clone https://github.com/bachureddy/python-backend-testing.git
cp python-backend-testing/frontend/index.html /usr/share/nginx/html/index.html
cp python-backend-testing/frontend/proxy.conf /etc/nginx/conf.d/reverse-proxy.conf
nginx -t
systemctl enable nginx
systemctl restart nginx
