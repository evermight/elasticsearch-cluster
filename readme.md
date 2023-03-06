These are the configuration files used for our tutorial on Elastic Clusters:

https://www.youtube.com/playlist?list=PLPatHYWw1RVv7_AamUYTZMZ3iN-T7QBmY


If you want to use elasticsearch self signed certificates for the `xpath.security.http.ssl`, and you want kibana to connect to the cluster, you have two options:

# Option 1: add this line to your kibana.yml file
```
elasticsearch.ssl.certificateAuthorities: [ "/etc/kibana/certs/http_ca.crt" ]
```

Where the http_ca.crt is a copy of /etc/elasticsearch/certs/http_ca.crt.from node 1

# Option2: add these two lines to your kibana.yml file
```
elasticsearch.ssl.keystore.path: [ "/etc/kibana/certs/http.p12" ]
elasticsearch.ssl.truststore.path: [ "/etc/kibana/certs/http.p12" ]
```
Where the http.p12 is a copy of /etc/elasticsearch/certs/http.p12 from node 1
