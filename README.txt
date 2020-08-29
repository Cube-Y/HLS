How to use HLS

1. Update & upgrade to the latest version.

sudo apt update
sudo apt upgrade


2. Add the nginx repository. Since it is not Offical, it is confirmed, but proceed with [Enter].

sudo add-apt-repository ppa:nginx/stable


3. Add the rtsp module.

sudo apt install -y nginx libnginx-mod-rtmp


4. Add the rtmp setting to the end of nginx.conf.

sudo nano /etc/nginx/nginx.conf

Add the attached nginx.conf to this file


5. Restart the service.

sudo service nginx restart


6. Add html5-compatible viewer video-js to index.html.

Replace {ip} with your server IP and {key} with your stream key.

sudo nano /var/www/html/index.html

Add the included index.html here


7. Use OBS etc. for distribution

Set the delivery information as follows.

Replace {ip} with your server IP and {key} with your stream key.

Delivery destination: rtmp://{ip}:1935/live
Dream key: {key}


8.UI construction

Add attached live/index.html

 Index.html
            ---Live directory--|
            Index index.html

After that, when you access http://[IP address)/live/, the distribution will be displayed.

This completes building the distribution server. Thank you for your hard work.
