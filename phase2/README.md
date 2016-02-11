# Scale a Cloud Foundry app using Concourse

In this phase, you will learn how to use a bash script to scale the CF app.
To see a working example, please visit
[https://185.99.186.164/pipelines/xj-phase2](https://185.99.186.164/pipelines/xj-phase2).

Please follow the steps below:

1) Modify `pipeline.yml` according to the hints given within the file.

2) Update your pipeline configure using the `fly` command.
   Note: It will show you the difference of the current configuration you are
         using and the one already in pipeline.
         Read it and make sure all of the changes are exactly what you expect.

3) Go to the Concourse web interface, you should see the pipeline is changed.
   Run the pipeline by clicking the '+' button.

4) Run `cf apps` on your laptop, check the instances number in the output.
