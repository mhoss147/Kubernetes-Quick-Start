# Kubernetes-Quick-Start


# Kubernetes-in-Azure-using-Bash

- Click Cloud-shell
- Create a storage in Azure > select advanced settings > create storage


- Set a variable for resource group name

    az group list
    
    copy the ""name": "491-1880c2bf-deploying...""
    
    Create a variable named RG=491-1880c2bf...
    
    
- Create a cluster

    az aks create \
    
  --resource-group $RG \  (resource-group name or variable)
  
  --name Cluster1 \      (cluster name)
  
  --node-count 3 \        (number of nodes)
  
  --generate-ssh-keys \   (generate ssh keys to provide authentication to above nodes)
  
  --node-vm-size Standard_B2s \   (node size, here we want a Standard_B2s size)
  
  --enable-managed-identity       (this to create cluster to crate it's infrastructure resources)
  
  
- Configure "kubectl" to run command against the created cluster


        az aks get-credentials --name Cluster01 --resource-group $RG
        
        
- Create deployment menifest file

        touch deployment.yml

        Open the editor by clicking the curly braces { }, and open the deployment.yaml file

        Copy and paste the scripts from the github to deployment.yml

        Click the menu icon in the top right (...), and click Close Editor. Make sure to save the file

        Deploy the application:
        
        kubectl apply -f ./deployment.yaml

        In the Azure Portal, under Kubernetes services, open Cluster01.
        
        In the left-hand menu, click Workloads

        In the Deployments tab, open the new deployment, and verify that the pods are running

        
- Access the Application Externally
        
- Create a new file named service.yaml
        
        touch service.yaml
        
        Open the editor by clicking the curly braces { }, and open the service.yaml file

        Copy and paste the contents of the service.yaml file from the GitHub repo, into the new file

        Click the menu icon in the top right (...), and click Close Editor. Make sure to save the file.
        Deploy the LoadBalancer service:
        
        kubectl apply -f service.yaml
        
        Back in the Azure Portal, in the Cluster01 overview, click Services and ingresses.
        Open the newly deployed LoadBalancer.
        
        Click the External IP and verify access to the application.


        
        
        
        
        





  
  
    
    
    
    




Reference: Linux Academy


