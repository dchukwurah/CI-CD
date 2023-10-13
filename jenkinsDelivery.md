## jenkins CI/**CD**

1. Firstly, we will create a new job called 'chiedozie-cd' which will be used to release our new app folder (new feature) from GitHub `main` branch to the production instance which will be running in front of clients.

2. Then we can go to 'Source Code Management' and specify our `main` branch to download from since this will now be updated with the tested dev changes.

3. Under 'Build Environment' we want to 'Provide Node & npm bin/ folder to PATH' and check the box for 'SSH Agent', selecting our tech254.pem SSH key which allows Jenkins access to the AWS EC2 instance via SSH.

4. Now, we can add a build step to 'Execute shell' as shown below. This will copy the app folder from the Jenkins workspace, which is from the merged main branch on GitHub, into the AWS EC2 instance, specifying the IP address of the EC2 instance to connect to. Then using the ssh command, we can remotely run commands to install and run the updated application.

5. Finally, we can save the job and manually build it, if it succeeds, we can add it to the pipeline by editing our configuration for the 'chiedozie-ci-merge' job adding a 'Post-build Action' to start the 'chiedozie-cd' job, using [jenkinsMerge.md](jenkinsMerge.md).

## Checking the CI/CD Pipeline

1. Now, if we make a change in the application code, for example, editing a test in 'index.ejs' to remove the word 'Sparta' logo and push the change to the `dev` branch on the GitHub repository, our Jenkins pipeline should automatically start the build process and if all is successful and the automated tests should fail and the app wouldn't be running,
2. but if we make another change that doesn't affect the tests and push ,it will be tested and a new version will be deployed