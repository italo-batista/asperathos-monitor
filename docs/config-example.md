# Config example

## monitor.cfg: 
```
[monasca]
# The endpoint for the Monasca's service.
monasca_endpoint = http://<ip:port>
# The username with permissions to publish and get metrics from monasca.
username = <monasca_user>
# The above-mentioned user's password
password = <password>
# The above-mentioned user's keystone project
project_name = <monasca_project_name>
# The keystone authentication endpoint
auth_url = http://<ip>:<port>/v3/
# Monasca API version
api_version = 2_0

# Flask configuration
[service]
# The host where the monitor service will be deployed
host = <host_ip>
# The port where the monitor service will be deployed
port = <port_number>
# Enable or disable flask debug
debug = True or False
# How many retries the service must do before abort an monitoring task
retries = 30

# This section is optional and must be used only when you pretend to
# run some OpenStack based plugin.
[credentials]
# Path to a private key associated with some OpenStack keypair
key_pair = <path_to_private_key>
```
