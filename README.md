# Concoure Project for Bootcamp Training

In this project you will learn how to setup a pipeline in order to deploy an app to CF in Phase I. In Phase II you will learn how to scale the app you deployed using Concourse, again using Concourse.

Since we are in the process of changing the way we do our intermal pipelines and the VPN is just recently set up successfully, we did not design a concourse project which uses bosh deployments. That said, I believe this exercise will help you master concourse pipelines faster when you go to work on  more complicated pipelines.

## Before we start

1) Go to [https://github.com/starkandwayne/deployments#vpn-installation-mac](https://github.com/starkandwayne/deployments#vpn-installation-mac) and update the VPN client configuration on your laptop. Delete your old credentials which you used for the cf training portion, if you saved them in your keychain. When you try to connect to the VPN the next time, it will ask you for the user name and password, use the new one we just created. You should be able to access to the VPN now.

2) Go to [https://github.com/xiujiao/cf-env](https://github.com/xiujiao/cf-env) and fork the repository to your own github account.

3) Run the `fly` command to target the concourse at `https://185.99.186.164` or `https://ci.vsphere.starkandwayne.com`.

Tips: 
(1) Use an alias "`{{your_target_alias}}`" for your concourse target;

(2) Remember to use `sync` so that you are always using the correct version of the Fly CLI;

(3) If `fly` fails to get the URL due to certificates, use the `-k` flag so that it ignores the certificate checking.

4) Run `fly -t {{your_target_alias}} pipelines`, you should see some existing pipelines in the output.

At the time that XJ ran this command, the output was as follows, you should be able to see similar output: 
```
name                                     paused
aws-s3-cf-service-broker-pivotaltile     no
logstash-docker-images                   no
slack-notification-resource-boshrelease  no
```

## After you finish the project

Please clean up the pipeline you set up by running:

`fly -t {{your_target_alias}} destroy-pipeline -p {{your_pipeline_name}}` and 
`cf delete {{your_app_name}}`.

Hooray!

XJ is tired but happy :)
