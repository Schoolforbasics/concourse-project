# Concoure Project for Training

In this project you will learn how to setup a pipeline to deploy an app to CF in phase1 and how to scale the app you deployed using Concoure in phase2.

Since we are in the process of changing the way we do our intermal pipelines and the VPN is just set up successfully, we will not design concourse project which does bosh deployments. However, I believe this exercise will help you master concourse pipelines faster when you work on  more complicated pipelines.


## Before we start

1) Go to `https://github.com/starkandwayne/deployments#vpn-installation-mac` , update the VPN client configuration on your laptop. Detele your old credentials which you used for cf training if you saved in your keychain. When you try to connect to VPN next time, it will ask you for user name and password, use the new one we created. You should be able to access to the VPN now.

2) Go to `https://github.com/xiujiao/cf-env` and fork the repo to your account.

3) Run the Fly command to target the concourse at `https://185.99.186.164` or `https://ci.vsphere.starkandwayne.com`.

Tips: 
(1) Use a alias for your concourse target;

(2) Remember to use `sync` to always get the right version of the Fly CLI;

(3) Use `-k` to make fly not check the remote certificates if it fails to get url.

4) Run `fly -t your_target_alias pipelines`, you should see some existing pipelines in the output.

At the time that XJ run the command, the output is as follows, you should be able to see the similar output. 
```
name                                     paused
aws-s3-cf-service-broker-pivotaltile     no
logstash-docker-images                   no
slack-notification-resource-boshrelease  no
```
## After you finish the project

Please clean up the pipeline you set up by running:

`fly -t your_target_alias destroy-pipeline -p your_pipeline_name` and `cf delete your_app_name`.

Hooray!

XJ is tired but happy :)
