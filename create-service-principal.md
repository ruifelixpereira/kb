### Step 2: Create a Service Principal

Kubernetes clusters have integrated support for various cloud providers as core functionality. On Azure, acs-engine uses a Service Principal to interact with Azure Resource Manager (ARM). Follow the instructions to create a new service principal:

```shell
az login
az account set --subscription="${SUBSCRIPTION_ID}"
az ad sp create-for-rbac --role="Contributor" --scopes="/subscriptions/${SUBSCRIPTION_ID}"
```

This will output your `appId`, `password`, `name`, and `tenant`. The `name` or `appId` may be used for the `servicePrincipalProfile.clientId` and the `password` is used for `servicePrincipalProfile.secret`.

Confirm your service principal by opening a new shell and run the following commands substituting in `name`, `password`, and `tenant`:

```
az login --service-principal -u NAME -p PASSWORD --tenant TENANT
az vm list-sizes --location westus
```

My sample:

```
az account set --subscription="5dd549af-d55f-4c2c-ba14-8bd7699a59b3"

az ad sp create-for-rbac --role="Contributor" --scopes="/subscriptions/5dd549af-d55f-4c2c-ba14-8bd7699a59b3"
```

