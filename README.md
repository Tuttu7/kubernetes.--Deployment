#### Creating a deployment named httpd-frontend with image httpd:2.4-alpine and 3 replicas

```
root@controlplane:~# kubectl create deployment httpd-frontend --image=httpd:2.4-alpine --replicas=3
deployment.apps/httpd-frontend created
   
   
root@controlplane:~# kubectl get deployment
NAME                  READY   UP-TO-DATE   AVAILABLE   AGE
frontend-deployment   0/4     4            0           9m9s
httpd-frontend        3/3     3            3           35s
        
        
root@controlplane:~# kubectl get replicaset
NAME                             DESIRED   CURRENT   READY   AGE
frontend-deployment-56d8ff5458   4         4         0       9m53s
httpd-frontend-5ddf995bdf        3         3         3       79s

root@controlplane:~# kubectl get pods
NAME                                   READY   STATUS             RESTARTS   AGE
frontend-deployment-56d8ff5458-4sqqz   0/1     ImagePullBackOff   0          10m
frontend-deployment-56d8ff5458-8xr7c   0/1     ImagePullBackOff   0          10m
frontend-deployment-56d8ff5458-plxqs   0/1     ImagePullBackOff   0          10m
frontend-deployment-56d8ff5458-sk47b   0/1     ImagePullBackOff   0          10m
httpd-frontend-5ddf995bdf-42h6c        1/1     Running            0          95s
httpd-frontend-5ddf995bdf-pgsdd        1/1     Running            0          95s
httpd-frontend-5ddf995bdf-r2rdd        1/1     Running            0          95s
```
