# SeisComPML-to-QuakeML

This is a project to provide QuakeML web services.  SeisComPML is transformed to QuakeML on the fly using Apache Httpd, an XSLT, and xsltproc.

## Deployment

The application is deployed on AWS Elastic Beanstalk.  To deploy create a zip file containing the resources:

```
zip sc3ml-to-quakeml .ebextensions/* sc3ml_0.6__quakeml_1.2.xsl 
```

Using the AWS console create a Beanstalk environment using `64bit Amazon Linux running PHP 5.4` instances and upload the zip file as the application.

Once the application completes deploying then QuakeML will be available at URLs like (adjust for what ever you named your environment):

```
http://quakeml.elasticbeanstalk.com/quakeml/1.2/2013p273125.xml
```