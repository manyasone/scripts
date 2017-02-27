# Some helper scripts

#### How to run

1. Clone this repository in a local folder, e.g. ~/bin
2. Add ~/bin to your PATH
3. Make all files in current dir executable: chmod +x *

## List of scripts
(Params in '[]' are optional):

### Ionic:
- ```create-apk``` -> Create unsigned android apk in ./apk-debug
- ```create-apk`-r``` -> Create signed android apk in ./apk-release
- ```crinstall-apk`-r``` -> Run 'create-apk-r' and install the created apk on connected device
- ```install-apk`-r``` -> Try to install the latest release apk on connected device
- ```run-all``` -> Run ionic app on android and ios device.
- ```run-android``` -> Run ionic app on android device.
- ```run-ios``` -> Run ionic app on ios device.
- ```serveprox ->``` Start ionic server and activate proxy. (a proxy is used in camigolo; can be found in gulpfile.js)

### Git:
- ```git checkout#``` -> Check out ticket. Params:
    - ticketNumber
- ```git cleanup``` -> Deletes all merged local and remote branches (the current branch and branches containing 'dev', 'master', 'alpha' and 'beta' in their name will be ignored).
- ```git com``` -> Commit staged changes.
    - Params:
        - [ticketNumber]
        - [EH|RF|BF|BF]
        - message
- ```git devtomaster``` -> Force push dev branch to origin/master
- ```git full``` -> Fetch and pull == full
- ```git new``` -> Fetch & pull on current branch, checkout new branch in ticket folder.
    - Param: ticketNumber
- ```git newfromdev``` -> Checkout dev branch, perform 'git new'
- ```git pushnew``` -> Push current $branch to origin/$branch, if it's new
- ```git remove``` -> Remove branch locally and on origin.
- ```git todev``` -> Merge branch to dev branch and delete it afterwards.
    - Param: [ticketNumber]

### Other:
- ```gw``` -> gulp && gulp watch
- ```addprox``` -> Runs gulp add-proxy (a proxy is used in camigolo; can be found in gulpfile.js)

