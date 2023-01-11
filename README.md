# **Deploy Application on Kubernetes Cluster**

## Prerequisites
Before getting started, complete the following prerequisites:
1. Install Kubectl
2. Install Git

It is good if you have fundamental about:
1. Kubernetes
2. Docker
3. Git

## **Steps to Deploy Application**

### **Step 1: Clone Repository**
```
git clone https://github.com/Frickson/Test-node.git
```

### **Step 2: Create Secret, ConfigMap, Persistent Volume and Persistent Volume Claim**
The following command will apply all the YAML files inside the **config** folder.
```
cd  depl
kubectl apply -f /config
```

### **Step 3: Provision Database**
1. Create Mariadb Pod
```
kubectl apply -f dbserver.yaml
```

2. Create Phpmyadmin Pod
```
kubectl apply -f phpmyadmin
```

3. Obtain external IP address.
We can use the external IP to access Phpmyadmin pod from browser.

[make-as-image-tag]Example Kubernetes service YAML file configuration.
[image-service-type-loadbalancer]

```
kubectl get service
```

[image-ss-service-external-ip]

4. Setup Database
    - Open Phpmyadmin on broswer
    - Import database
    - Configure upload size (Optional)
    https://stackoverflow.com/questions/3958615/import-file-size-limit-in-phpmyadmin
    - 