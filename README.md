# Persistent Python3 Web File Server

### Requirements:
 
    sudo apt update
   
    sudo apt install python3
   
### Setup:

    sudo nano /etc/python3-webserver.sh

#### Add this

   - -b host where to bind the httpserver e.g "10.0.0.1:8000"

    cd Downloads && python3 -m http.server -b 10.0.0.1 &> /dev/null & pid=$!

#### Add execution permission 

    chmod +x /etc/python-webserver.sh

   
### Next Automate execution after reboot through crontab

    sudo crontab -e 

#### Add this

    */1 * * * * /etc/python-webserver.sh

# Code
```sh
# Python 3 Simple Web Server
import http.server
import socketserver

# Define the port number
PORT = 8000

# Handler for serving files
Handler = http.server.SimpleHTTPRequestHandler

# Create the server
with socketserver.TCPServer(("", PORT), Handler) as httpd:
    print(f"Serving on port {PORT}")
    httpd.serve_forever()
```

