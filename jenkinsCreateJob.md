### Creating a job in Jenkins

**Step 1.** Log In to Jenkins: Open your web browser and navigate to your Jenkins server's URL. <br>
**Step 2.** Log in using your credentials. <br>
**Step 3.** Create a New Job: From the Jenkins dashboard, click on "New Item" or "Create New Job" on the left-hand side. <br>
**Step 4.** Enter a name for your job and select the type of job you want to create. <br>
**Step 5.** Select Freestyle project <br>
**Step 6.** Check `Discard old builds` <br>
**Step 7.** `Max # of builds to keep: 3` <br>


**Step 8.** Press ok <br>
### Configure Source Code Management: 
**Step 1.** Create a new Jenkins job or navigate to an existing one.
**Step 2.** Under "Source Code Management," select "Git."
**Step 3.** Enter your repository URL and select your GitHub credentials.
**Step 4.** Specify the branch to build (e.g., */dev). 


### Testing Jenkins - does Jenkins have the env required for our deployment?

**Step 1.** Follow the above steps <br>
**Step 2.** Navigate to `Build` <br>
**Step 3.** Select `Execute Shell` <br>
**Step 4.** Enter the commands ` cd app` <br>
**Step 5.** Enter `Save` <br>

### Triggering the job manually

**Step 1.** Locate the job by using the dropdown and select `Build now` <br>
**Step 2**. Navigate to the # use the dropdown and select `console output` <br>
**Step 3.** You will now be able to see output from the job run

### Triggering the job automatically

**Step 1.** Select your job <br>#

**Step 2.** Navigate to `Configure`<br>

**Step 3.** Navigate to `Post-build Actions` <br>

**Step 4.** Enter the name of your second job <br>

**Step 5.** Check `Trigger only if build is stable` <br>

**Step 6.** Then `Save` <br>