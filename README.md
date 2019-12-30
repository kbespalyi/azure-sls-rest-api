# Azure Functions

<https://serverless.com/blog/serverless-azure-functions-v1/>
<https://serverless.com/blog/serverless-azure-functions-v1-part2/>

Login to Azure
$ az login
Set Azure Subscription for which to create Service Principal
$ az account set -s <subscription-id>
Create SP with unique name
$ az ad sp create-for-rbac --name <my-unique-name>

Bash:
$ export AZURE_SUBSCRIPTION_ID='<subscriptionId (see above, step 2)>'
$ export AZURE_TENANT_ID='<tenantId>'
$ export AZURE_CLIENT_ID='<servicePrincipalId>'
$ export AZURE_CLIENT_SECRET='<password>'

$ sls deploy
$ sls invoke -f issues -p tests/data.json

If you have your service running locally (in another terminal), you can run:
$ sls offline
$ sls invoke local -f issues -p tests/data.json

Refer to [Serverless docs](https://serverless.com/framework/docs/providers/azure/guide/intro/) for more information.

With webpack:
$ sls deploy --region "North Central US" --stage "dev"
