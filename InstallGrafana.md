# Install and Configure Grafana

### Install necessary packages and grafana  
```
sudo apt install software-properties-common  
wget -q -O - https://packages.grafana.com/gpg.key | sudo apt-key add -  
sudo add-apt-repository "deb https://packages.grafana.com/oss/deb stable main"  
sudo apt update  
sudo apt-cache policy grafana  
sudo apt install grafana  
```

### Install grafana pie chart plugin  
```
sudo grafana-cli plugins install grafana-piechart-panel  
```

### Start grafana server  
```
sudo systemctl start grafana-server  
```
  
### Enable grafana server at startup  
```
sudo systemctl enable grafana-server  
```
  
### Check the status of grafana server 
```
sudo systemctl status grafana-server  
```
  
  
As an end result you should be able to reach your grafana endpoint by calling it in a browser window: http://IP:3000  
By default port 3000 is used. The default user is *admin* and the initial password is also *admin*, which is strongly recommended to change to a much stronger password.  
Also make sure that your firewall allows you to connect to your grafana endpoint.

In Grafana first add prometheus as a new data source under *Configuration*. Define *"Prometheus"* as name for the data source and as URL enter "http://localhost:9091" if you are running all components (grafana and prometheus on the same instance). Otherwise you will have to enter the *IP* of the machine where Prometheus is running instead of *localhost*.
