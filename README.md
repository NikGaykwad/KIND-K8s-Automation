KIND Cluster Setup Guide
1. Installing KIND and kubectl
  Install KIND and kubectl using the provided script or manualy

2. Setting Up the KIND Cluster
  -Create a kind-cluster-config.yaml file
     
  -Create the cluster using the configuration file:
    kind create cluster --config kind-cluster-config.yaml --name my-kind-cluster

3. Verify the cluster:
    kubectl get nodes
    kubectl cluster-info
    
4. Accessing the Cluster
  -Use kubectl to interact with the cluster:
    kubectl cluster-info

5. Setting Up the Kubernetes Dashboard
  -Deploy the Dashboard Apply the Kubernetes Dashboard manifest:
    kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/v2.7.0/aio/deploy/recommended.yaml
   
  -Apply the configuration:
    kubectl apply -f dashboard-admin-user.yml
    
  -Get the Access Token Retrieve the token for the admin-user:
    kubectl -n kubernetes-dashboard create token admin-user
    
  -Copy the token for use in the Dashboard login.

  -Access the Dashboard Start the Dashboard using kubectl proxy:
    kubectl proxy
    
  -Open the Dashboard in your browser:
    http://localhost:8001/api/v1/namespaces/kubernetes-dashboard/services/https:kubernetes-dashboard:/proxy/

  -Use the token from the previous step to log in.

5. Deleting the Cluster
   kind delete cluster --name my-kind-cluster
6. Notes
Multiple Clusters: KIND supports multiple clusters. Use unique --name for each cluster. Custom Node Images: Specify Kubernetes versions by updating the image in the configuration file. Ephemeral Clusters: KIND clusters are temporary and will be lost if Docker is restarted.

 (https://github.com/user-attachments/files/19741576/KIND.CLUSTER.SETUP.pdf)
