# Persistent-Python-Webserver

### Requirements:
 
    sudo apt update
   
    sudo apt install python2 python3 python3-pip
   
### Setup:

    sudo -i

    sudo nano /etc/python-webserver.sh

#### Add: 

    # -b bind address for httpserver e.g "10.0.0.1:8000"

    cd / ; python3 -m http.server -b 10.0.0.1 &> /dev/null & pid=$!

#### Add execution permission 

    chmod +x /etc/python-webserver.sh

### Automate execution after reboot through crontab -e

    sudo crontab -e 

#### Add

    @reboot /etc/python-webserver.sh


