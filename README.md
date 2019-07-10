# Quasar FAQ
List of questions which are asked more often then others.

Although [Quasar](https://quasar.dev/introduction-to-quasar) documentation covers most of the asked questions from users I think it would be nice to have quick reference guide to Frequently Asked Questions.

## NPM
Q: ```quasar build``` on Win 10 - complains about locked file. Windows restart is needed whenever I build the app.

A: There is probably other process blocking the ```dist/spa``` folder (e.g. Tortoise Git, Remote Desktop etc.). Install a [Process Monitor](https://docs.microsoft.com/en-us/sysinternals/downloads/procmon) to discover the process which blocks the folder.

## Components
Q: **QTable** - I'd like to get the current data table sort status

A: Use custom sort function or undocumented property ```this.$refs.YourTableName.computedData.rows``` credit to (Discord answer - @Tobias Mesquita (PT-EN) - 11.04.2019)

REF: [JsFiddle example](this.$refs.table.computedData.rows), [QTable](https://quasar.dev/vue-components/table)

## UDM
Q: **QTab** - tabs looks like they were nested

A: Check the closing tags 

REF: [QTab](https://quasar.dev/vue-components/tabs#QRouteTab-API)

## Others


[MD Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)
