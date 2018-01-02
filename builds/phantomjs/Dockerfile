FROM		ubuntu:latest
MAINTAINER	vmsnivas <vmsnivas@gmail.com>

RUN		mkdir /install
WORKDIR		/install
RUN		apt-get update && \
        	apt-get -y install python python-dev build-essential wget python3 python3-dev python3-pip npm
RUN 		wget https://bootstrap.pypa.io/get-pip.py
RUN 		python ./get-pip.py
RUN 		pip install cx_Oracle requests boto credstash datetime selenium ConfigParser simplejson jira
RUN 		pip2 install cx_Oracle requests boto credstash datetime selenium ConfigParser simplejson jira
WORKDIR 	/usr/local/share
RUN 		wget https://bitbucket.org/ariya/phantomjs/downloads/phantomjs-1.9.7-linux-x86_64.tar.bz2
RUN 		tar xjf phantomjs-1.9.7-linux-x86_64.tar.bz2
RUN 		ln -s /usr/local/share/phantomjs-1.9.7-linux-x86_64/bin/phantomjs /usr/local/share/phantomjs
RUN 		ln -s /usr/local/share/phantomjs-1.9.7-linux-x86_64/bin/phantomjs /usr/local/bin/phantomjs
RUN 		ln -s /usr/local/share/phantomjs-1.9.7-linux-x86_64/bin/phantomjs /usr/bin/phantomjs
