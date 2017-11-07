# Some helper scripts

#### How to run

Assuming that you want to place the scripts in a folder named _~/bin_:

1. Clone this repository: ```git clone git@github.com:manyasone/scripts.git ~/bin```.
	(Use ```git clone git://github.com/manyasone/scripts ~/bin``` if you're not logged into github).
2. Add _~/bin_ to your PATH.
3. Make all files in _~/bin_ executable: ```chmod +x ~/bin/*```.

## List of scripts
Params in '[]' are optional.

### Ionic:
Note: Execute these scripts in the project's root folder.
- ```create-apk``` → Create android apk
    - Params (can be combined at will):
        - r → Create release apk
        - i → Install apk
        - o→ Open apk folder after creation
- ```run-all``` → Run ionic app on android and ios device.
- ```run-android``` → Run ionic app on android device.
- ```run-ios``` → Run ionic app on ios device.
- ```serveprox →``` Start ionic server and activate proxy (a proxy is used in camigolo; can be found in the project's gulpfile.js).

### Git:
Note: Most of these scripts assume that ticket branches are located in _ticket/$ticketNumber_.

- ```git checkout#``` → Check out new branch in _ticket/$ticketNumber_. Params:
    - ticketNumber
- ```git cleanup``` → Deletes all merged local and remote branches (the current branch and branches containing _dev_, _master_, _alpha_ and _beta_ in their name will be ignored).
- ```git com``` → Commit staged changes.
    - Params:
        - [ticketNumber]
        - [EH|RF|BF|BF]
        - message
- ```git devtomaster``` → Force push dev branch to origin/master. (BE CAREFUL WITH THIS ONE)
- ```git devtobeta``` → Merge and push dev to beta. (BE CAREFUL WITH THIS ONE)
- ```git full``` → Fetch and pull == full.
- ```git new``` → Fetch & pull on current branch, checkout new branch in ticket folder.
    - Mandatory param: ticketNumber.
- ```git newfromdev``` → Checkout dev branch, perform ```git new```
- ```git publish``` → Push current $branch to origin/$branch, if it's new.
- ```git remove``` → Remove branch locally and on origin.
- ```git todev``` → Merge branch to dev branch and delete it afterwards.
    - Optional param: [ticketNumber].
- ```git discard``` → Discard all uncommited changes (equal to ```git checkout -- .```).
- ```git undo``` → Undo last commit (equal to ```git reset --mixed $(git rev-parse HEAD~1)```).


### Gulp:
- ```gw``` → gulp && gulp watch
- ```addprox``` → Runs ```gulp add-proxy``` (a proxy is used in camigolo; can be found in the project's gulpfile.js)

### Fidion:
- ```fd``` → Build a new fidion apk
	- Params:
		- App flavor (see list of case-statements in script file).
 		- The other params must be prefixed with a '-' and can be combined (e.g. -bri to build a release apk and deploy it to the device).
 			- b → Build new apk
 			- r → Use release apk
 			- i → Install apk to device
 		 	- u → Uplad apk to crashlytics
 		 	- v → Reset build version code
 		 	- d → Delete apk before installing
- ```fverivy``` → Check style, run tests, find potential bugs.

### Other:
- ```scripts-update```→ Pull from origin and make files executable.
- ```mta``` → Gradle Helper script
	- Params:
		- App flavor (optional).
 		- The other params must be prefixed with a '-' and can be combined (e.g. -bri to build a release apk and deploy it to the device).
           - b → Build new apk
           - i → Install apk to device
           - r → Use release apk
           - d → Uninstall existing apk
           - o → Open apk folder
           - v → Discard version code changes
           - u → Unsigned build (`signed` is default for variant `release`, while `unsigned` is default for variant `debug`)
- ```openfolder```→ Opens a folder that has been passed as a param. Prevents errors by differentiating between OSX and Linux.