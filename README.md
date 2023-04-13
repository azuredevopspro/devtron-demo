# argo-gitops

This repo uses following secrets for deploying and configuring resources on Azure using Github actions workflow

**ADP_AZ_SUBS_WE_01_CRED** - This is service principal json object for login to azure.

Run the following commands to obtain the required json

```
az ad sp create-for-rbac --name "myApp" --role contributor \
                            --scopes /subscriptions/{subscription-id} \
                            --sdk-auth
# Replace the subscription id with appropriate value                           
# The command should output a JSON object similar to this:
 
{
    "clientId": "<GUID>",
    "clientSecret": "<STRING>",
    "subscriptionId": "<GUID>",
    "tenantId": "<GUID>",
    "resourceManagerEndpointUrl": "<URL>"
    (...)
}
```
**ADP_AZ_SUBS_WE_01_ID** - Subscription ID where resources will be deployed

**ADP_AKS_ADMIN_GROUP_ID** - Azure AD group id to be set as K8s cluster administrator.