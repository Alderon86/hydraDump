# Dump Runtime Protected Apps on IOS 12.x

<strong>This is a temporary Workaround to Dump Apps on IOS 12.x using Clutch2!</strong>

This Repo contains a little guide and the Script which will allow you to dump Runtime Protected Apps, Lets get started!

# Requirements

- Jailbroken Iphone on IOS 12.x (works up to latest 12.4)
- Filza or any other working Filebrowser
- Target App from Appstore
- Clutch2 from https://github.com/KJCracks/Clutch
- Clutch requirements:
  - ldid
  - plutil																																						
  - optool																																				
  - zip																																						
  - MiniZip

# Installation

First start and compile Clutch2 yourself by downloading and building it or grab a finished Release and scp it over to your phone into 
- ` /usr/bin/`

Give Clutch proper permissions via 
- `chmod 755 /usr/bin/Clutch`

Ok the easy Part is done, now lets head over to a save place to work into:
- `cd /private/var/mobile/Documents`

Now we have to get the entitlements from bash and save them:
- `ldid -e `which bash` > ent.xml`

Resign Clutch with the ent. "-Sent.xml" is the correct usage:
- ldid -Sent.xml `which Clutch`

Now inject into trust cache:
- inject `which Clutch`

Copy over hydraDump into:
- /usr/bin/

Give it also proper permissions:
- `chmod 755 /usr/bin/hydraDump`

# Usage

First of all run Clutch -i to get the targets application number.

You now know how Clutch labeld your Target Application, remember that Number we will need it later on.

Start Filza or whatever browser you are using and head over to: 
- `/private/var/containers/Bundle/Application/`

There you will find the Applications installation Directory labled something like `1234-abcd-5678-efgh`

Once you found the Targets Directory copy that Number over and put it into the hydraDump script on line 26.

Dont worry the script itself has comments everywhere in case of what is allowed to touch and what not.

Also edit line `54` and `59` that is where the number will go we found earlier witch Clutch -i

OK! We are Setup now to dump Apps on IOS 12.x

Open up the Terminal

Switch to root user via `su` and simply run ./hydraDump

Congratulations IOS 12.x dump should be succesfully saved under /var/tmp/clutch/ApplicationFolder

Now remove all backups and copy over the decryptet bin from `var` to *.app root dir.

Dont forget to rename `Frameworks-` back into `Frameworks` (yes this projects ships with a feature :) )

If you like this Project and want to see more IOS releases in the feature follow me or give me a star.

