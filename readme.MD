```
helm repo add elastic https://helm.elastic.co
helm repo update

helm install eck-operator elastic/eck-operator -n eck --create-namespace

helm install eck-stack elastic/eck-stack -f eck-stack-values.yaml --namespace eck --create-namespace

kubectl get pods -n eck
kubectl get elasticsearch -n eck
kubectl get kibana -n eck
kubectl get logstash -n eck
kubectl get apmserver -n eck
kubectl get enterprisearch -n eck
kubectl get metricbeat -n eck
kubectl get filebeat -n eck

kubectl get secret elasticsearch-es-elastic-user -n eck -o=jsonpath='{.data.elastic}' | base64 --decode; echo


helm upgrade eck-stack elastic/eck-stack -f eck-stack-values.yaml --namespace eck --create-namespace


```
