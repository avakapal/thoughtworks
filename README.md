# thoughtworks POC
Installation of mediwiki with scaling enabled on memort and cpu limits
## Installation
copy the yaml file to your cluster location/jumpserver
```bash
Kubectl apply -f mediwiki.yaml 
```
## How to access the application 
execute kubectl get svc to get 
```bash
example:
debbieraay@cloudshell:~ (trim-heaven-271012)$ kubectl get svc
NAME                TYPE           CLUSTER-IP      EXTERNAL-IP      PORT(S)        AGE
kubernetes          ClusterIP      10.105.0.1      <none>           443/TCP        44m
mediawiki-service   LoadBalancer   10.105.11.132   35.184.150.179   80:30165/TCP   6m37s
```
Access  the application with above  External ip and port  example : http://35.184.150.179:80

##Troubleshooting
 if you face any firewall issue enable the port on firewall
 ```bash
 on GCP
gcloud compute firewall-rules create mediawiki-http --description "Incoming http allowed." --allow tcp:30165 
```
