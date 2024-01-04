# DSPO VSCode Launchers and Settings

## Purpose
These files help run and test Data Science Pipelines Operator locally in the VSCode IDE

## Setup
To use these files, simply perform these steps:

1. Create `.vscode` directory in the root of your data-science-pipelines-operator source (ie, `~/src/data-science-pipelines-operator/.vscode`)
2. Copy the `config.yaml`, `launch.json` and `tasks.json` files to the newly-created `.vscode` folder
3. (Re-)start VSCode

**NOTE**: config.yaml is specific to DSPO and needs to be maintained/updated regularly.  With that said, it is also useful for testing changes with specifically pinned versions, values, etc.

## Launchers (Running DSPO Locally)
1. Login to an Openshift cluster using `oc login`
2. Ensure a DSPO instance isn't already running on the cluster.  Scale it down if one is, or else you may encounter unexpected behavior
3. On the left sidebar in VSCode, click the `Run and Debug` (playbutton and bug) icon.  (Default shortcut: Ctrl+Shift+D)
2. On the top left side of the menu bar, there should be a dropdown with a green arrow.  Find "Run DSPO", select it, and click the green play button.  
4. A DSPO instance is now running locally on your computer.  You can see logs in the `Debug Console` tab of your VSCode terminal

## Tasks (Simplfy common procedures)
The tasks.json file configures VSCode to have some run tasks in terminal.  This tasks.json file contains several ways to run basic dev tests, which is useful so you don't have to memorize procedures to do repetitive tasks like this.

To utilize tasks:
1. Open VSCode
2. Go to a DSPO source .go file
3. Open `Run Task...` from `Terminal` menu item (Default shortcut: Ctrl+Shift+P)
4. Select `Tasks: Run Task`
5. Select one of the Test commands to run (ie `Run Unit Tests`).
6. Select a scanner, though by default we don't use any problemMatcher here
7. Terminal will run the command and show output for you.

## Recommended IDE Settings
Assuming the Go Extension is already installed (do that if you haven't yet!):

1. Go to `File` > `Preferences` > `Settings`
2. Find `Extensions` > `Go`

Recommend enabling the following settings:
* Cover On Save
* Cover On Single Test
* Cover On Single Test File
* Cover On Test Package
* Test Tags: Edit in settings.json and add "test\_unit"

