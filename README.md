# OAuth 2.0 add devices like FitBit

Basic connection to FitBit API using AngularJS

------------------------

There are several different ways to connect to the FitBit API. The easiest way that I had the most success was with AngularJS. This is a very basic application to demonstrate how OAuth 2.0 will work with FitBit.

###Instructions

In order to make any requests to the FitBit API you must register your application on dev.fitbit.com. You can easily find guides on how to complete this, but as a helpful tip, the information doesn't have to be exactly correct right away. By completing the registration, you will be provided with a few lines of information. For this app, the most important piece would be the "OAuth 2.0 Client ID".

Modifying the app with this client ID is the first step. Go to ```scripts/app.js```. Find the "LoginController" and you will see ```$scope.fitbit_client_id = "XXXXXX";```. Go ahead and replace _XXXXXX_ with your OAuth 2.0 Client ID.

Next, you will just have to modify a few links to match your environment. Going back to dev.fitbit.com, you will need to make sure your Callback URL is set to the exact URL where your oauth_callback.html is located _(i.e. http://www.YOURDOMAIN.com/fitbit/oauth_callback.html)_. This will also work if you're running this locally through a wamp / mamp server using localhost.

Now within the oauth_callback.html file, change ```http://.../#/dashboard``` to the full url where your dashboard template is located.

You should now be able to run the site and login to fitbit. You'll then be redirected back to the app to show you basic profile information as well as a chart (using Chart.js) showing your steps over the past 7 days.

_To view a working example, log into your fitbit account through http://collierdevlinmedia.com/fitbit/#/_

------------------------