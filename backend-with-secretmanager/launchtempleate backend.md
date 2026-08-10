#!/bin/bash
yum update -y
yum install -y git python3 python3-pip
cd /home/ec2-user
git clone https://github.com/bachureddy/python-backend-testing.git
cd python-backend-testing/backend-with-secretmanager
pip3 install -r requirements.txt
nohup python3 app.py > app.log 2>&1 &
