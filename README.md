# SPFx-explain
Explaining SPFx

## Node JS dependency
- I had trouble getting this yeoman generator working on the first few releases of NodeJS I tried
- I eneded up relying on the [node v14 LTS release](https://nodejs.org/download/release/latest-v14.x/)
## Initial setup via PowerShell
1) $Path_sharepointdevsite = "nftstips.sharepoint.com/sites/devsite"
2) `npm i gulp-cli yo @microsoft/generator-sharepoint --global --force`
3) `mkdir SPFx`
4) `cd SPFx`
5) `yo @microsoft/sharepoint --framework "none" --component-type "webpart" --component-name "InstantListViewFilter" --component-description "Hides rows of a view that do not contain the text entered by the user" --environment "spo" --skip-feature-deployment --is-domain-isolated
   - ? What is your solution name? (sp-fx) `ENTER`
   - ? Where do you want to place the files? (Use the current folder) `ENTER`
6) `Out-File -FilePath .\config\serve.json -InputObject ((Get-Content -path .\config\serve.json -Raw) -replace 'enter-your-SharePoint-site',$Path_sharepointdevsite)`
7) `gulp trust-dev-cert`
8) `gulp serve`
9) Your OS default browser will open and go to the location of the devsite workbench page
10) If you get an error saying "Your web part will not appear in the toolbox. Please make sure "gulp serve" is running in a web part project. Please refresh the page once "gulp serve" is running." do this:
    - open a new tab in the *same browser* and navigate to `https://localhost:4321/`
    - ensure that your browser is set to allow/trust the site/certificate
    - reload the browser's first tab and you should not get the error this time
11) Click the + button to open the "Add a web part" menu in sharepoint
12) Search for the text "instant" and you should see the web part

