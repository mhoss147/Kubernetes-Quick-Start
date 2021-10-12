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
        
        
        
        
        





  
  
    
    
    
    




Reference: Linux Academy


