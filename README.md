# ansible-filebeats-dcos

This is an ansible system the install filebeats on a DC/OS Cluster.  Add your cluster to the host file in the base
directory.  To run this:


Make sure you change the VIP in the files directory
```
     hosts: ["coordinator.<service name or elastic>.l4lb.thisdcos.directory:9200"]
```

If should end up looking like, assuming you take the default Name:
```
     hosts: ["coordinator.elastic.l4lb.thisdcos.directory:9200"]
```

```
       ./execute.sh
```

Then on any server run:

```
      /usr/share/filebeat/scripts/import_dashboards -es "http://coordinator.elastic.l4lb.thisdcos.directory:9200" -user elastic -pass changeme
```

Bring up ElasticSearch and query the filebeats index

enjoy!
