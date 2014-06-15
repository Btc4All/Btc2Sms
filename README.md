
# Vision

Let's assume we want to bring Bitcoin to the 4 Billion people that are not connected to the internet, and let's further assume we want to do it by SMS, because feature phones have high global penetration. Let's then build an android app that is open source, works in a mesh network to be censorship resistant and can be installed on cheap devices to infiltrate any providers network and open a wallet for any participant.

EnvayaSMS architecture was a central control server. The objective is to get rid of it step by step and create the previously described architecture.


## Build

set `<sdk><path>` in `mobile/pom.xml`, then build with `mvn clean install`

`<sdk><path>` in `mobile/pom.xml` should refer to an element in your `settings.xml` file. 

There are two locations where a settings.xml file may live:

    The Maven install: $M2_HOME/conf/settings.xml
    A user's install: ${user.home}/.m2/settings.xml

See http://maven.apache.org/settings.html for further details on setting up your settings.xml file. 

## Nathan Notes: 
###Common* Errors / Annoyances: 

Note that the following only apply to a release for build. 
The proguard.conf file may be in an incorrect location. A quick hack-fix for testing would be to move it to anywhere there is a pom.xml file. 
Building for release, using the "-P release" option for maven, will result in an error when running "jarsigner". 
The command used to run jarsigner, if it has some of its parameters that look like series of asterisks, should have some of its options modified to fit the following : 
http://developer.android.com/tools/publishing/app-signing.html#secure-key

Here is an example of the Maven exception generated by a failed jarsigner command: 
"Caused by: org.apache.maven.plugin.MojoExecutionException: Failed executing '/bin/sh -c cd /home/nbas/bin/37coins/v6/Btc2Sms/mobile/btc2sms && /usr/lib/jvm/java-7-oracle/jre/../bin/jarsigner -verbose -sigalg MD5withRSA -digestalg SHA1 -keystore /home/nbas/bin/37coins/Btc4All/Btc2Sms/mobile -storepass ''*****'' -keypass ''*****'' /home/nbas/bin/37coins/v6/Btc2Sms/mobile/btc2sms/target/btc2sms.apk 37dev' - exitcode 1"

*These may or may not take the form of the inverse of "Works on my machine". 

## Tip4Commit

[![tip for next commit](http://tip4commit.com/projects/530.svg)](http://tip4commit.com/projects/530)

## Old


EnvayaSMS is an Android app that acts as a SMS and MMS gateway. 

For more information and installation instructions, 
see http://sms.envaya.org/

This project uses ant (or NetBeans) as the build tool.
Before building, first create a local.properties file in the project root directory,
and set sdk.dir to the path of your android sdk, e.g.:

`sdk.dir=C:\\android-sdk`

The code is released under the MIT license; see LICENSE
