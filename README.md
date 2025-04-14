KIND Cluster Setup Guide
1. Installing KIND and kubectl
Install KIND and kubectl using the provided script:

2. Setting Up the KIND Cluster
Create a kind-cluster-config.yaml file
Create the cluster using the configuration file

3. Accessing the Cluster
Use kubectl to interact with the cluster

4. Setting Up the Kubernetes Dashboard
Deploy the Dashboard Apply the Kubernetes Dashboard manifest

Apply the configuration

Get the Access Token Retrieve the token for the admin-user

Copy the token for use in the Dashboard login.

Access the Dashboard Start the Dashboard using kubectl proxy

Open the Dashboard in your browser:

http://localhost:8001/api/v1/namespaces/kubernetes-dashboard/services/https:kubernetes-dashboard:/proxy/
Use the token from the previous step to log in.

5. Deleting the Cluster

6. Notes
Multiple Clusters: KIND supports multiple clusters. Use unique --name for each cluster. Custom Node Images: Specify Kubernetes versions by updating the image in the configuration file. Ephemeral Clusters: KIND clusters are temporary and will be lost if Docker is restarted.