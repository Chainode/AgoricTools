# AgoricTools
## Monitoring Agoric Validator


## Scope

With this solution it will be possible to monitor both your Validator as well as the hardware your validator runs on. This will help you improve the overall health of your Validator as well as offer you proper insight into what happens in the Agoric network and with your machine at any point in time.  
Prometheus represents a monitoring solution for storing time series data like metrics. Grafana is another important tool which allows users to visualize the data stored in Prometheus and many more sources like Telegraf, etc. 

In combination with an Alertmanager it becomes a viable solution to monitor and improve the overall uptime and performance of your Validator.  Alertmanager can be used to define certain thresholds for which you will get alerted on Telegram, Discord, by SMS or many other options. Some example for possbile alerts: You can set your threshold for disk usage rate to 70% so that you will get alerted once that is reached in order to prepare for an upgrade for more disk space; low number of connected peers; validator is stuck (block height is not increasing over a period of time); validator is down and much more.  


## Prerequisites
* Enable export of tendermint metrics --> please check EnableTendermintMetrics in this repo: https://github.com/Chainode/AgoricTools/blob/main/EnableTendermintMetrics.md  
* Prometheus  --> please check InstallPrometheus in this repo: https://github.com/Chainode/AgoricTools/blob/main/InstallPrometheus.md  
* Node Exporter  --> please check guide InstallNodeExporter in this repo: https://github.com/Chainode/AgoricTools/blob/main/InstallNodeExporter.md  
* Grafana  --> please check guide InstallGrafana in this repo: https://github.com/Chainode/AgoricTools/blob/main/InstallGrafana.md   
* Grafana Pie Chart plugin  --> please check guide InstallGrafana in this repo: https://github.com/Chainode/AgoricTools/blob/main/InstallGrafana.md  

## Import Agoric Validator Dashboard into Grafana  
For this you will have to download the AgoricValidator.json from this repo and then in Grafana go to *Dashboards* -> *Manage* -> *Import* -> *Upload JSON file* and select the AgoricValidator.json to be uploaded.  
As a next step you should make sure the right Prometheus connection has been selected and if necessary adapt the Dashboard. 

## Final Result  
![image](https://user-images.githubusercontent.com/53407923/112890048-ad4f7980-90d6-11eb-82b8-17e275141f28.png)
