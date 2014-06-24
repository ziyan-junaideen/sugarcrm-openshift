# SugarCRM on OpenShift

SugarCRM is one of the popular free and open source CRMs in the wild. Although
installing an instance of SugarCRM in a VPS or dedicated server can be handled
by the documentation, there needs some modifications that need to be done to 
host it in OpenShift RedHat Cloud Computing.

With this repository, I hope I will be able t make a installer that will make 
the installation much easier for any new commer to OpenShift to use SugarCRM.

## Notice

The current version hosted is still experimental and is a pre release. This 
method should not be used to update the system. I am my self new to SugarCRM
and am not sure on how the upgrade process will work. I intend to update this
document in the future regarding upgading. As per the moment it is about 
installing a new instance SugarCRM in an empty node.

## Install

**Step1** Create an account at https://www.openshift.com

**Step2** Create a php-5.3 application and attach the mysql cartridge to it:
````    
    $ rhc app create sugarcrm php-5.3 mysql-5.1
````

**Step3** Add this upstream sugarcrm repo
````
    $ cd sugarcrm
    $ git remote add upstream -m master git://github.com/openshift-quickstart/sugarcrm-example.git
    $ git pull -s recursive -X theirs upstream master
````
**Step4** Then push the repo upstream
````    
    $ git push
````

**Step5** That's it, you can now checkout your application at:
````
    http://sugarcrm-$yournamespace.rhcloud.com
````

**Step6** Login using admin/admin (username, password)

## Special Thanks

## About me

I am Ziyan, a computer engineer and a hobbyist web developer form Colombo
Sri Lanka. I have my share of fun building custom web applications for clients
and once in a while I get requests on how to configure and intall apps in a 
variety of platforms.

SugarCRM on OpenShift has been one such request that has gained my attention
as I am my self new to OpenShift.

