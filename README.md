# SPFx-explain
Explaining SPFx


## Initial setup
node v14 LTS (presently v14.18.1)
`npm i gulp-cli yo @microsoft/generator-sharepoint --global --force`
`mkdir SPFx`
`cd SPFx`
`yo @microsoft/sharepoint --solution-name "sp-fx" --framework "none" --component-type "webpart" --component-name "InstantListViewFilter" --component-description "Hides rows of a view that do not contain the text entered by the user" --skip-install --environment "spo" --skip-feature-deployment`
[//]: # (https://mcpmag.com/articles/2018/08/08/replace-text-with-powershell.aspx)
`(Get-Content -path ..\config\serve.json -Raw) -replace 'enter-your-SharePoint-site','nftstips.sharepoint.com/sites/devsite'`
`npm i`
`gulp trust-dev-cert`
`gulp serve`
