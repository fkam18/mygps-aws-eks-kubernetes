myGPS implementation on AWS EKS Kubernetes docker  <BR>
<br>
myGPS app at https://github.com/fkam18/mygps/<br>
docker image at https://hub.docker.com/u/fkam18/<br>
<br>
How To:<br>
eksctl create cluster --name mygps --region eu-west-2<br>
eksctl get cluster<br>
kubectl create namespace mygps<br>
kubectl get namespaces<br>
kubectl apply -f mygps.yaml<br>
kubectl get all -n mygps<br>
NAME                        READY   STATUS    RESTARTS   AGE<br>
pod/mygps-c7668499b-4q496   1/1     Running   0          16s<br>
pod/mygps-c7668499b-8k4sw   1/1     Running   0          16s<br>
pod/mygps-c7668499b-clj4p   1/1     Running   0          16s<br>
pod/mygps-c7668499b-nlzcx   1/1     Running   0          16s<br>
pod/mygps-c7668499b-p6g4s   1/1     Running   0          16s<br>
<br>
NAME                    READY   UP-TO-DATE   AVAILABLE   AGE<br>
deployment.apps/mygps   5/5     5            5           17s<br>
<br>
NAME                              DESIRED   CURRENT   READY   AGE<br>
replicaset.apps/mygps-c7668499b   5         5         5       17s<br>
<br>
<br>
kubectl apply -f mygps-service.yaml<br>
kubectl get services -n mygps<br>
NAME            TYPE        CLUSTER-IP       EXTERNAL-IP   PORT(S)   AGE<br>
mygps-service   ClusterIP   10.100.216.213   <none>        80/TCP    11s<br>
<br>
kubectl exec -it <container id> -n mygps -- /bin/bash<br>
apt install curl<br>
curl mygps-service<br>
<br>
### done<br>
