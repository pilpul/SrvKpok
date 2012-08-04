##Disclaimer
This may not be of any help for anybody but I'll try to comment as good as possible
This is work-in-progress/alpha/whatever-you-call-it.

##What it does
We have a Mailman Mailinglist server and there is one user on that list that is for archiving purposes only.
The email is deliverd to a server where the mail is parsed into a mongoDB databse.

##Receive Mails
Incoming emails are redirected to the parsing python script.
This is done with a simple line in /etc/aliases
  ```ARCHIVER: |/usr/bin/python /PATH/TO/SCRIPT/mailin.py```

##Parsing
The mailin.py has some requirements which can be installed (on Debian/Ubuntu) with

For character detection
  ```sudo apt-get install pyhton-chardet``
For pythong -> MongoDB connection
 ```easy_install pymongo```

##MongoDB
To install mongoDB follow the guide on
http://docs.mongodb.org/manual/tutorial/install-mongodb-on-debian-or-ubuntu-linux/

##Sleepy.Mongoose
To make the database accessible from the app I installed [sleepy.mongoose](https://github.com/kchodorow/sleepy.mongoose)
In addition any webserver (Apache, nginx..) could be configured to proxy requests to the database..
