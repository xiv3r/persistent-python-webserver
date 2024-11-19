# Persistent Python3 Web File Server

### Requirements:
 
    sudo apt update
   
    sudo apt install nano bash python2 python3 python3-pip
   
### Setup:

    sudo nano /etc/python-webserver.sh

#### Add this

   - -b address where to bind the httpserver e.g "10.0.0.1:8000"

    cd / ; python3 -m http.server -b 10.0.0.1 &> /dev/null & pid=$!

#### Add execution permission 

    chmod +x /etc/python-webserver.sh

   
### Next Automate execution after reboot through crontab

    sudo crontab -e 

#### Add this

    */1 * * * * /etc/python-webserver.sh


