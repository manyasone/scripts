# Some helper scripts

#### How to run

Assuming that you want to place the scripts in a folder named _~/bin_:

1. Clone this repository: ```git clone git@github.com:manyasone/scripts.git ~/bin```.
2. Add _~/bin_ to your PATH.
3. Make all files in _~/bin_ executable: ```chmod +x ~/bin/*```.

## List of scripts
Params in '[]' are optional.

### Ionic:
Note: Execute these scripts in the project's root folder.
- ```create-apk``` -> Create unsigned android apk in _./apk-debug_.
- ```create-apk`-r``` -> Create signed android apk in _./apk-release_.
- ```crinstall-apk`-r``` -> Run ```create-apk-r``` and install the created apk on the connected device.
- ```install-apk`-r``` -> Try to install the latest release apk on the connected device.
- ```run-all``` -> Run ionic app on android and ios device.
- ```run-android``` -> Run ionic app on android device.
- ```run-ios``` -> Run ionic app on ios device.
- ```serveprox ->``` Start ionic server and activate proxy (a proxy is used in camigolo; can be found in the project's gulpfile.js).

### Git:
Note: Most of these scripts assume that ticket branches are located in _ticket/$ticketNumber_.

- ```git checkout#``` -> Check out new branch in _ticket/$ticketNumber_. Params:
    - ticketNumber
- ```git cleanup``` -> Deletes all merged local and remote branches (the current branch and branches containing _dev_, _master_, _alpha_ and _beta_ in their name will be ignored).
- ```git com``` -> Commit staged changes.
    - Params:
        - [ticketNumber]
        - [EH|RF|BF|BF]
        - message
- ```git devtomaster``` -> Force push dev branch to origin/master.
- ```git full``` -> Fetch and pull == full.
- ```git new``` -> Fetch & pull on current branch, checkout new branch in ticket folder.
    - Mandatory param: ticketNumber.
- ```git newfromdev``` -> Checkout dev branch, perform ```git new```
- ```git pushnew``` -> Push current $branch to origin/$branch, if it's new.
- ```git remove``` -> Remove branch locally and on origin.
- ```git todev``` -> Merge branch to dev branch and delete it afterwards.
    - Optional param: [ticketNumber].

### Gulp:
- ```gw``` -> gulp && gulp watch
- ```addprox``` -> Runs ```gulp add-proxy``` (a proxy is used in camigolo; can be found in the project's gulpfile.js)

