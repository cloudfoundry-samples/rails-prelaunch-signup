## Rails App for a Startup Prelaunch Signup Site - Deployable on Cloud Foundry!

Rails 3.2 "beta launching soon" example application that shows how to create a Rails application for a startup prelaunch signup site.

Please see https://github.com/RailsApps/rails-prelaunch-signup for detailed information

### Deploying to Cloud Foundry

Cloud Foundry runs your Rails app in production mode, therefore you need to precompile assets prior to deploying:

```bash
rake assets:precompile
```

To deploy the application to Cloud Foundry, simply use the provided manifest.yml file.  You need only to provide the application with a name and URL.

```bash
vmc push
Would you like to deploy from the current directory? [Yn]:
Application Name: mynewsite
Application Deployed URL [mynewsite.cloudfoundry.com]:
```

### Enabling Email
The feature that sends a welcome email to new users has been disabled for Cloud Foundry deployment, as you cannot send outbound traffic through the SMTP port.  We recommend using the SendGrid service to send email, and it should be possible to modify this sample to do so.