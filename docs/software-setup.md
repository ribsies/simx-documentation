---
layout: default
title: Setup Development Environment
nav_order: 4
---

### Access and pull down the repos
These are the repos you will need to pull down and the associated branches from AWS CodeCommit. Follow the instructions that were emailed to you to find the repos.
Use an SSH key to connect to code commit.

You can follow these instructions to set that up

* Unity Client
    * Branch: **Dev**
* SimX Server
    * Branch: **Dev**
* Case Files
    * Branch: **Dev**

###Import into unity
This process will take a good amount of time, so you can get this started first.

#####Build bundles
In Unity, we need to build the initial set of bundles that our local project will use to serve assets

* Open the “SimX Utilities” editor window by going to SimX - > Utilities
* In the scene window, make sure the “XR Enabled” button in the top left is green (VR mode is enabled)
* XR mode must be enabled when you build the bundles or the VR clients will load bundles that are not made for VR
* Open the “Addressable Groups” window by going to Window -> Asset Management -> Addressables -> Groups
* Verify that the profile drop down in the top left is set to “Build”
* On the right side of the top of the window, click Build -> Update a previous build
* In the file window that comes up, go into the “Windows” folder and double click the “addressables_content_state.bin” that is in that folder.
* After the build process is complete, you will have a “ServerData” folder now in your unity project root.
    * You will use that path in the next step
* Connect bundles to server
* The local server that will run on your machine will need to be able to serve the Assetbundles from somewhere on your machine. We can do that by creating a symlink from where the Assetbundles are built, to a folder in the server structure.
* Open cmd prompt as an Administrator and enter the following. Filling in the paths with the correct paths
```
mklink /J "C:\Link\To\Repo\simx-server\src\AssetBundles" "C:\Link\To\ServerData"
```
Connect case files to server

Just like the above Assetbundles folder, we need to connect the case-files repo to the server so the server can pull the case for our dev environment.
```
mklink /J "C:\Link\To\Repo\simx-server\src\Cases" "C:\Link\To\Repo\case-files"
```
After setting both of those symlinks up, you should see something like the below image in your simx-server repo under the “src” folder.

### Install AWS CLI

The server will try to access some functions that involve interacting with AWS. In order for it to work you need to define your AWS credentials using the AWS CLI environment.
* Download the AWS CLI v1 from https://docs.aws.amazon.com/cli/latest/userguide/install-windows.html
* Follow these instructions to add your credentials to the CLI environment. https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-configure.html

###Install the server

* Open `powershell` or the command line of your choice and navigate to the root of the server repo.
* You need to run the npm command that will install everything needed to make the server run.

```
npm install
```

### Run the server
* Open `powershell` or the command line of your choice and navigate to the root of the server repo.
* Run
```
npm start
```

You should see something like the image below in your terminal


### Run unity moderator
With the server running, we can now test out the moderator in Unity.
* Open the `SimX Utilities` editor window by going to `SimX -> Utilities`
* In the scene window, make sure the `XR Enabled` button in the top left is red (XR mode is disabled)
* Open the `Persistant Moderator` scene and press Play
* You should now be able to login and start a case

### Run unity VR client
Make sure all the required software is installed to enable the Oculus Link with your Quest
* Connect Quest
* Enable Oculus Link
* Open Steam VR
* Open the `SimX Utilities` editor window by going to `SimX -> Utilities`
* In the scene window, make sure the `XR Enabled`button in the top left is green (XR mode is enabled)
* Open the `Persistant Quest` scene in the project tab located at `SimX -> Scenes` and press Play
* You should now be able to move around in VR

> To bring up the SimX menu while running the Quest through Unity, press the esc key

### Build local moderator for full case testing
You will want to often build a new version of the moderator so you can run the moderator to start a case while you run the VR client through unity.
* Open the `SimX Utilities` editor window by going to `SimX -> Utilities`
* In the scene window, make sure the `XR Enabled` button in the top left is red (XR mode is disabled)
* From the top menu select `Build -> Windows -> Moderator -> Local`
* The build will go into your root unity project under `Builds`
