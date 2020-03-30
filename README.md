WT - FeedHenry JavaScript SDK
========================

## Pull Requests

Be sure for each pull request that the base branch is WT and not the original FeedHenry repo.

## Version Branches

Version branches (ex. version-1.1.1) should be based off of the main develop branch. After development on the version is complete, tag the branch and merge it back into develop.

## Release Branches

To release a new version:
1. Create a branch off of the current version branch (ex. release-1.1.1).
2. Run `npm run build`.
3. Force add the entire `dist` folder and any changes to the `libs` folder. (To make this easier, remove `dist` and `libs` from the .gitignore before adding files)
4. Rebuild the latest version of https://github.com/willowtreeapps/fh-js-sdk with the new version of fh-sync-js.

FeedHenry Sync Javascript client
========================

Data synchonization javascript client.
Library can be used for offline storage of mobile applications data.

## Required setup

To use the sync client you need a sync server setup first see https://github.com/feedhenry/fh-sync or https://github.com/feedhenry/fh-sync-server.
Sync client using default Ajax handler to call sync server.   
Server URL can be configured using following variables 

- cloudUrl - URL to sync server
- cloudPath (optional) - allows to use custom endpoint for sync (defaults to `/sync/`)


For example: 
```javascript

syncClient.init({
    cloudUrl:"http://localhost:3000",
    do_console_log: true,
    sync_frequency: 1,
    sync_active: false,
    storage_strategy: ['memory'],
    crashed_count_wait: 0
});

```


## Building

    npm install
    grunt 

## Cordova client template

You can try [Cordova Sync Template](https://github.com/feedhenry-templates/feedhenry-cordova-sync-app). It uses fh-sync-js as a library for connecting to running sync server instance.

## Relation for fh-js-sdk

Feedhenry JS SDK contains various libraries and also includes fh-sync-js library.
