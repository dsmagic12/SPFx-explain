# SPFx-explain
Explaining SPFx


## Initial setup
1) [node v14 LTS](https://nodejs.org/download/release/latest-v14.x/)
2) `npm i gulp-cli yo @microsoft/generator-sharepoint --global --force`
3) `mkdir SPFx`
4) `cd SPFx`
5) `yo @microsoft/sharepoint --solution-name "sp-fx" --framework "none" --component-type "webpart" --component-name "InstantListViewFilter" --component-description "Hides rows of a view that do not contain the text entered by the user" --skip-install --environment "spo" --skip-feature-deployment`
[//]: # (https://mcpmag.com/articles/2018/08/08/replace-text-with-powershell.aspx)
6) `(Get-Content -path ..\config\serve.json -Raw) -replace 'enter-your-SharePoint-site','nftstips.sharepoint.com/sites/devsite'`
7) `npm i`
8) `gulp trust-dev-cert`
9) `gulp serve`
10) Your OS default browser will open and go to the location of the devsite workbench page
11) If you get an error about your web part will not show in the menu, and you need to run gulp serve and refresh the page then try the following...
    - open a new tab in the same browser and navigate to `https://localhost:4321/`
    - ensure that your browser is set to trust the site/certificate
    - reload the browser's first tab and you should not get the error this time


