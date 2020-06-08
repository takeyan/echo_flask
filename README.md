### 実行例

```
docker run -d -p 5000:5000 takeyan/flask:0.0.3
curl localhost:5000/api/echo

# curl localhost:5000/api/echo
{"api":"echo","nodename":"null","pod_ip":"null","podname":"null","query_string":[""],"timestamp":"2020-06-08T01:55:11.522007"}

kubectl apply -f flask.yaml
kubectl expose pod flask --port=5000 --type=NodePort
kubectl get svc -o wide
curl localhost:32546/api/echo

# curl localhost:32546/api/echo
{"api":"echo","nodename":"tk-ub18-k8s","pod_ip":"10.42.0.11","podname":"flask","query_string":[""],"timestamp":"2020-06-08T02:03:40.680696"}
```
