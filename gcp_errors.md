# The connection to the server localhost:8080 was refused - did you specify the right host or port?

Make sure your config is set to the project -

```
gcloud config set project [PROJECT_ID]
```

Run a checklist of the Clusters in the account:
```
gcloud container clusters list
```
Check the output :
```
NAME           LOCATION       MASTER_VERSION  MASTER_IP      MACHINE_TYPE  NODE_VE.      NUM_NODES  STATUS
alpha-cluster  asia-south1-a  1.9.7-gke.6     35.200.254.78  f1-micro      1.9.7-gke.6   3          RUNNING
```
Run the following cmd to fetch credentials for your running cluster:
```
gcloud container clusters get-credentials your-cluster-name --zone your-zone       --project your-project
```
The following output follows:
Fetching cluster endpoint and auth data.
kubeconfig entry generated for alpha-cluster.
Try checking details of the node running kubectl such as below to list all pods in the current namespace, with more details:
```
kubectl get nodes -o wide
```
