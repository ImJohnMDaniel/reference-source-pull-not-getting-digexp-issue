# reference-source-pull-not-getting-digexp-issue

This is the reference repo to reproduce the issue where the Salesforce CLI , using the `force:source:pull` command -- is not retrieving Digital Experience (aka Experience Bundle) metadata from the scratch org.

# Steps to reproduce issue
1. create scratch org
    - `sfdx force:org:create -a refscratch1 -d 1 -s -f config/project-scratch-def.json`
1. open the scratch org to the digital experience section.
    - `sfdx force:org:open -u refscratch1 -p /lightning/setup/SetupNetworks/home`
1. Click "New" button to create new digital experience
1. Choose "Build Your Own (LWR)" experience template
1. Click "Get Started" button
1. Enter the name "foobar" and click the "Create" button
1. Go to the "Builder" section of the digital experience
1. Create a new page -- new standard page -- new blank page -- call it "bluepage"
1. Create a new page -- new standard page -- new blank page -- call it "redpage"
1. Publish the "foobar" digital experience site
1. attempt to pull the "foobar" digital experience to source code 
    - `sfdx force:source:pull -u refscratch1`

*** FAILURE POINT ***

Lots of items are pulled from scratch org but the foobar digital experience is not.

