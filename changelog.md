# Implementation steps `https://aws.amazon.com/getting-started/guides/deploy-webapp-copilot/module-one/`

1. Installing Copilot CLI using this command (make sure you run `powershell` with admin access)
   `Invoke-WebRequest -OutFile 'C:\Program Files\copilot.exe' https://github.com/aws/copilot-cli/releases/latest/download/copilot-windows.exe`

2. Test it by opening `cmd` and writing `copilot --version` to see if you have it installed

3. Next, we will need to download some code to deploy. For this tutorial, we will be using a sample app that’s just a simple static website.

   - In your terminal, copy and paste this code. `git clone https://github.com/aws-samples/aws-copilot-sample-service example` and `cd example`. This will clone AWS sample app and change directories to it.

4. Copilot uses a guided text interface to determine how to deploy your application. To start this interface, run `copilot init` in a `cmd` terminal and enter the following values:

   - Chose which name you want and then choose `Load Balanced Web Service   (Internet to ECS on Fargate)` and give that service a name as well

   - Choose your `Dockerfile` or a path for your `Dockerfile`

   - You will be prompted to deployment to a test environment, chooose No...

   - You will now create an environment to run your application in by running the following command, and entering the following command `copilot env init --name prod --profile default --app copilot-guide` and choosing `Yes, use default` for configuration

   - This will create the infrastructure in the prod environment

   - Next run copilot env `deploy --name prod` to deploy the prod environment before deploying the application

   - Once this completes, you can run `copilot deploy` to deploy your application. This will take a few minutes to complete

   - Congratulations, your application is now up and running. You can access it using the URL provided by the output.
