# Deploy an app to CF using Concourse

In this phase, you will mainly learn how to use Concourse to deploy an app to CF.
To see what it looks like after you finish this phase, check `https://185.99.186.164/pipelines/xj-phase1`.

You need to do the followings:

## Clone cf-env repo

Clone the `cf-env` repo you forked to your github account.

## Change app name

Modify the `manifest.yml` in the repo you just cloned to, then push the change to your remote. 

```
applications:
- name: cf-env-{your_name}
  memory: 128M
  disk_quota: 128M
```
## Write your pipeline YML file, configure and verify

1) Configure `pipeline.yml` according to the hints inside the `pipeline.yml` file.
2) Set up your pipeline using the fly command:
   Hint: you need to load vars from `credentials.yml`.
3) Unpause your pipeline if you did not set unpause when you configure your pipeline.
4) Run a build of your pipeline in web user interface. If you do the steps 1) and 2) correctly, you will see the pipeline becomes green and you can see details when you
   click on each specific task.
5) Run `cf apps` in your terminal, you should see the app you just deployed using concourse. If you took the cf training Quinn gave last week, you should be able to run `cf apps` successfully, if not please run `cf login -a https://api.run.vsphere.starkandwayne.com -u training -p password --skip-ssl-validation` , and then run `cf apps`.

## Have some fun with the trigger

Let's make some change to the git resource and the pipeline should be automaticlly triggered since we set trigger to true.

1) Modify the `README.md` in the `cf-env` repo you cloned, run git add, commit and push command; 
2) Go to `https://ci.vsphere.starkandwayne.com`, visit your pipeline, you should see it is running another build automaticlly.  

