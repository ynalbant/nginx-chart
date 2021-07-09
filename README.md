* helm v3
* clone repo with this command "git clone https://github.com/ynalbant/nginx-chart.git " 
* get into the file "nginx-chart" using this command from your terminal " cd nginx-chart/ "
* run helm command to install , " helm install nginx(name of the deployment) .(location of the chart) 
* run kubectl command to see if the pods and services are working as expected. " kubectl get all -n namespace " 
* output should be like :
---
 k get all 
NAME                              READY   STATUS    RESTARTS   AGE
pod/nginx-nginx-74495645b-sjplb   1/1     Running   0          8m26s

NAME                  TYPE        CLUSTER-IP   EXTERNAL-IP   PORT(S)        AGE
service/kubernetes    ClusterIP   10.8.0.1     <none>        443/TCP        29h
service/nginx-nginx   NodePort    10.8.3.38    <none>        80:30001/TCP   8m27s

NAME                          READY   UP-TO-DATE   AVAILABLE   AGE
deployment.apps/nginx-nginx   1/1     1            1           8m28s

NAME                                    DESIRED   CURRENT   READY   AGE
replicaset.apps/nginx-nginx-74495645b   1         1         1       8m29s

NAME                                              REFERENCE                TARGETS         MINPODS   MAXPODS   REPLICAS   AGE
horizontalpodautoscaler.autoscaling/nginx-nginx   Deployment/nginx-nginx   <unknown>/80%   1         10        1          8m30s
---
