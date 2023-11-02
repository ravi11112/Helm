# Helm


<b> what is Helm (Package Manager )</b>
Helm is a tool that automates the creation, packaging, configuration, and deployment of Kubernetes applications by combining your configuration files into a single reusable package.

As we have seen, Kubernetes is a powerful and popular container-orchestration system. But as we’ve also seen, migrating to and setting up your applications on Kubernetes can be a complex, daunting task. Setting up a single application can involve creating multiple interdependent Kubernetes components — **pods, services, deployments, and replica sets,** and each **component requires you to write a detailed YAML manifest file.

Enter Helm. Just like **apt** for** Ubuntu****** or **yum** and rpm for** Red Hat**, Helm is a package manager for Kubernetes that allows you as a developer or an admin to more easily package, configure, and deploy applications and services into your Kubernetes clusters.



**Helm Charts ** (contains all packages )
Helm charts are a collection of files that describe a Kubernetes cluster's resources and package them together as an application. They comprise three basic components: the chart, chart.yaml, which defines the application metadata like name, version, dependencies, etc., and values.yaml, which sets values, which is how you will set variable substitutions for reusing your chart.

Helm Registory (store the packages ,databases )

Helm Release (for deployment,create new version ,)


####################

**#Instalation of Helm in K8s Cluster** 

```curl -fsSL -o get_helm.sh https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3 ```

```chmod 700 get_helm.sh```

```./get_helm.sh```


**#Install Helm in Local Machine** 

 Install Microk8s - ```https://microk8s.io/#install-microk8s```

 Install kubectl - ```https://kubernetes.io/docs/tasks/tool...```




 ********************************************


**Important Commands**

1. helm create <chart name >  //create a new charts include packages

 helm create helloworld

```helloworld
├── charts
├── Chart.yaml
├── templates
│  ├── deployment.yaml
│  ├── _helpers.tpl
│  ├── hpa.yaml
│  ├── ingress.yaml
│  ├── NOTES.txt
│  ├── serviceaccount.yaml
│  ├── service.yaml
│  └── tests
│      └── test-connection.yaml
└── values.yaml
```


2. helm install

 helm install <FIRST_ARGUMENT_RELEASE_NAME> <SECOND_ARGUMENT_CHART_NAME> // Using Charts install the package

 helm install myhelloworld1 helloworld

 

3. helm list -a        // show list of all release



4. helm upgrate myhelloworld1 helloworld   //do some change and upgrade the charts ,create new revision

  

5. helm rollback  myhelloworld1 helloworld   //back to previous charts ,create a new version
   


6. helm delete myhelloworld1 helloworld  




#######################

**Creating Custom Helm Charts**


Create a docker image for Python application with REST API and push to the dockerhub


Create Helm Charts for your Python REST API app


Helm chart installation and post-installation verification




1. clone the git repository
   ```git clone```

2. build docker image
```docker build -t python_flask1 . ```   

3. run docker image 
```docker run -d -p 9001:9001 python_flask1 ```

4. docker login and tag to the image
 ``` docker tag img_id techraviraj/python_flask_project:python_flask1```

5.docker push 
```docker push techraviraj/python_flask_project:python_flask1 ```



then update the deployment,service,and values file in charts 

for this python application






