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
cd depl
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


<p align="center">
   <img src="https://github.com/Frickson/Test-node/tree/main/image/services" alt="example service configuration"/>
</p>
<p align="center"><i>Figure 1: Example Kubernetes service YAML file configuration.</i></p>
<br/>

```
kubectl get service
```
<p align="center">
   <img src="https://github.com/Frickson/Test-node/tree/main/image/services" alt="services"/>
</p>
<p align="center"><i>Figure 2: List all services</i></p>
<br/>


4. Setup Database
    - Open Phpmyadmin on broswer
    - Import database
    - Configure upload size (Optional)

https://stackoverflow.com/questions/3958615/import-file-size-limit-in-phpmyadmin

### **Step 4: Provision other Applications**
The following command will apply all the YAML files inside the **config** folder.
```
cd ..
kubectl apply -f /depl
```

### **Step 5: Access web application from browser**
1. Copy External IP and open in browser
[browser-image]
