# Node Exporter Installation and Configuration  
 
``` 
wget https://github.com/prometheus/node_exporter/releases/download/v1.0.1/node_exporter-1.0.1.linux-amd64.tar.gz  
tar xvfz node_exporter-1.0.1.linux-amd64.tar.gz  
cd node_exporter-1.0.1.linux-amd64  
```

### Create systemd file  
``` 
sudo nano /etc/systemd/system/node_exporter.service  
```

### You can use the file below, adapt it to your user and group or create your own customized file based on this file and your installation
```   
[Unit]  
Description=Node Exporter  
After=network.target  
  
[Service]  
User=<your-user>  
Group=<your-user>  
Type=simple  
ExecStart=/home/<your-user>/node_exporter-1.0.1.linux-amd64/node_exporter  
  
[Install]  
WantedBy=multi-user.target  
```

### Start node exporter  
``` 
sudo systemctl start node_exporter  
```
### Enable node exporter at startup  
``` 
sudo systemctl enable node_exporter   
```
### Check the status of node exporter  
```
sudo systemctl status node_exporter  
```
