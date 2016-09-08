# Universal Wiki Converter readme.txt file

#
#  Project History
#
This project is a fork of https://github.com/sameertawil/universal-wiki-converter
which itself is a fork of https://github.com/AtlassianContribs/universal-wiki-converter
which itself is a fork of https://bitbucket.org/appfusions/universal-wiki-converter


AppFusions repo has 3 main flaws
* no update starting from october 2015
* read access only
* pull requests never merged (see https://bitbucket.org/appfusions/universal-wiki-converter/pull-requests/)

Quoting Sorin Sbarnea
    As it seems that pull requests are ignored here, I invite you to try join
    a real open-source and community driven fork at https://github.com/AtlassianContribs/universal-wiki-converter/wiki


#
# Build process
#
To build the UWC use ANT (http://ant.apache.org/):
* cd devel (the devel dir.)
* ant      (the default target will build the UWC under 

Note: you do not need to build the UWC to run it; only if you're doing development work with it. 

To run the newly built UWC
* cd target/uwc/
* chmod a+x *sh
* ./run_uwc_devel.sh

## using Maven

```shell
mvn install:install-file -DgroupId=com.atlassian.confluence \
                           -DartifactId=confluence-xmlrpc \
                           -Dversion=5.2.0 \
                           -Dfile=lib/confluence-xmlrpc-wrapper-v5.2.0.jar \
                           -Dpackaging=jar
mvn install:install-file -DgroupId=net.antonioshome.swing \
                           -DartifactId=treewrapper \
                           -Dversion=1.1.1.1 \
                           -Dfile=lib/treewrapper.jar \
                           -Dpackaging=jar
mvn install:install-file -DgroupId=org.jvnet.substance \
                           -DartifactId=substance \
                           -Dversion=2.3final \
                           -Dfile=lib/substance.jar \
                           -Dpackaging=jar
mvn install:install-file -DgroupId=com.atlassian.confluence \
                          -DartifactId=sharepoint-wrapper \
						  -Dversion=1.0 \
						  -Dfile=lib/sharepoint-wrapper-1.0.jar \
						  -Dpackaging=jar
```

Don't forget to setup your environment variabls.
```
export JAVA_HOME=/c/Program\ Files/Java/jdk1.7.0_51
```

#
# More
#
More details and documentation is here: https://migrations.atlassian.net/wiki/display/UWC/Universal+Wiki+Converter

#
# ABOUT THE UWC
#
This code is open source and is up to date with Atlassian's latest storage format of Atlassian Confluence
(introduced in Confluence 4). We successfully use/run the UWC for Confluence 5.X releases, however, there are *many* flavors and versions of MIGRATE_FROM wikis. 

As such, we feel it is accurate to say that this is "a tool", yet not always the end-to-end solution or silver bullet. Wiki formats are varied, and so please understand that the UWC will get you further along, but there may be post-processing, additional scripting, username database merging, or other things required to assist in the process. 

Please refer to the Wiki Migration Checklist (http://www.appfusions.com/display/Dashboard/Wiki+Migration+Checklist) to educate yourself on what is invoived in a migration. The checklist is not to suggest that all content elements are problematic. They aren't. But some are, and not always the same between different flavors of wikis that are being migrated from.

We do provide paid ongoing small and big support for migrations, depending on needs. Email us at info@appfusions.com and let us know what you are trying to do and we can see if we can help you!  We have many client references too.

