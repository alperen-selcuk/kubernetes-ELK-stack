# kubernetes-ELK-stack

<img width="1224" alt="image" src="https://github.com/user-attachments/assets/12f4be88-7e1f-4b35-92d7-afe060cae3cb" />


for this repo you can directly see all container logs on kubernetes cluster. all values file are avalaible on the repo you can just follow instraction step.

### installation 

```
kubectl create namespace logging
helm install elasticsearch elastic/elasticsearch -f elasticsearch-values.yaml -n logging
helm install filebeat elastic/filebeat -f filebeat-values.yaml -n logging
helm install logstash elastic/logstash -f logstash-values.yaml -n logging
helm install kibana elastic/kibana -f kibana-values.yaml -n logging
```

login with kibana nodeport and elasticsearch username password.

```
kubectl get secret elasticsearch-master-credentials -o jsonpath="{.data.username}" | base64 --decode

kubectl get secret elasticsearch-master-credentials -o jsonpath="{.data.password}" | base64 --decode
```

<img width="1495" alt="image" src="https://github.com/user-attachments/assets/c2beb5a5-0bf1-4d1f-9480-9d838e45c78c" />
