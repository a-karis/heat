These heat templates launch an example topology with a new network, a load-balancer, instances with floating-ips and attached volumes.
You can modify environment/web-server.yaml for different default values

Web servers need a web image with HTTPD enabled. cloud-init will write the server name into /var/www/html/index.html for LB tests

Usage:
  Create
    heat stack-create -e environment/web-server.yaml -f webapp.yaml webapp -P 'web-server-count=2'
  Scale up/down
    heat stack-update -e environment/web-server.yaml -f webapp.yaml webapp -P 'web-server-count=4'

Topology:
Have a look at TOPOLOGY.txt

