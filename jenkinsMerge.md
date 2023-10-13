## Merging a branch job in Jenkins

#### Firstly follow the steps in [jenkinsCreateJob.md](jenkinsCreateJob.md) to create a new job. 
#### After running a test to test if the dev branch is properly validated.
#### It is important to test on the dev branch as we dont want to work in main or for any 
### Configure Source Code Management: 
Create a new Jenkins job or navigate to an existing one.
Under "Source Code Management," select "Git."
Enter your repository URL and select your GitHub credentials.
Specify the branch to build (e.g., */dev). 

### Build Configuration:
Configure the build steps as per your project requirements (e.g., compile code, run tests).

### Configure Git Publisher:
- Scroll down to "Post-build Actions."
- Click "Add post-build action" and select "Git Publisher."
- Check "Push Only If Build Succeeds" if you only want to push when the build is successful.
- Under "Branches," click "Add Branch" and configure as follows:
- Branch to push: Enter the name of the branch you want to push (e.g. main).
- Target remote name: e.g. "origin" (or use the remote name you have configured for GitHub).