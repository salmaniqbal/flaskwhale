
# Create Resources for WebApp for Containers in Azure

#### Create Resource Group
az group create --name flaskappons --location "West Europe"

#### Create App Service Plan
az appservice plan create --name myAppServicePlan --resource-group flaskappons --sku B1 --is-linux

#### Create WebApp for Container
az webapp create --name whaleapp2 --resource-group flaskappons --plan myAppServicePlan --deployment-container-image-name salmaniqbal/flaskwhale

#### Expose port externally
az webapp config appsettings set --resource-group flaskappons --name whaleapp2 --settings WEBSITES_PORT=9000

check this video for commands: https://www.youtube.com/watch?v=aJ8EPAH9G6E