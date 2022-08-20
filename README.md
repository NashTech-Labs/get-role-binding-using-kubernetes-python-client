### Install Kubernetes Python Client:

`git clone --recursive https://github.com/kubernetes-client/python.git cd`

`cd python`

`python setup.py install`

### Installation from pip:

`pip install kubernetes`

### Get List of Role Bindings in your cluster using python

For Role Bindings, we use RbacAuthorizationV1Api class from client module.

For listing Role Bindings on local cluster e.g minikube we use the following command:

`config.load_kube_config()`

### Authentication to the Kubernetes Python Client in other cluster is done by: 

`configuration.api_key = {"authorization": "Bearer" + bearer_token}`

We will use here the Bearer Token which enable requests to authenticate using an access key.

In get_role_binding.py file we have to provide our cluster details for listing Role Bindings:


Give your cluster details:
```
cluster_details={
        "bearer_token":"<Your_cluster_bearer_token>",
        "api_server_endpoint":"<Your_cluster_IP>"
    }
```

### Running the File:
```
python3 get_role_bindings.py
```

You will get the list of Role Bindings inside your cluster in the following format:

```
[{'name': 'jenkins', 'namespace': 'default'}, {'name': 'prometheus-grafana', 'namespace': 'default'}]
```

