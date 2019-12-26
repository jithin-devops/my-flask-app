**Dependency:**

 - Install minikube in your MBP
```$ minikube version: v0.27.0```

 - Install helm
```$ brew install kubernetes-helm```
```$ helm version: "v3.0.2"```
- Enable minikube ingress
```$ minikube addons enable ingress```
 


**Start my-app using helm with below command**

```
cd my-flask-app
eval $(minikube docker-env)
docker build -t my_app:v1 .
```

```
$ helm install  my-app my-flask-app
```

- Make sure the pods are in running state before launching the url.
```
$ kubectl get pods
```

- Run below command to resolve the hostname localy with minikube IP.

```
$ echo "$(minikube ip) hello.personio" | sudo tee -a /etc/hosts
```

- Access my app using below url.
```
http://hello.personio/
```



**Notes:**

If you are deploying my-app for the second time make sure you remove the data inside "/data/db/"
```
minikube ssh
sudo su - 
rm -rf /data/db/
```
