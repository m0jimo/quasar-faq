Here is a list of questions which are asked more often then others. If you know of a question that a lot of people ask, just ask it in a comment. If you would like to add to this faq, just leave a comment in the Q & A & R (question, answer, reference) format. Use Markdown! Let's Answer this!!!

# Quasar framework FAQ
Although [Quasar framework](https://quasar.dev/introduction-to-quasar) documentation covers most of the asked questions from users I think it would be nice to have quick reference guide to Frequently Asked Questions.

## How to get a quick answer to my question?
If you like saving time to yourself and/or to Quasar users reacting to your answer please provide if possible:
- **Operating system**, **Browser** (version), **Quasar version** ```quasar --version```, and if you are using **npm** or **yarn**
- link to [jsFiddle](https://jsfiddle.quasar.dev/) or [Codepen](https://codepen.quasar.dev/) - you can create your own example in [Codepen](https://codepen.quasar.dev/) from the existing Quasar component examples e.g. [Docs - Quasar - Tabs](https://quasar.dev/vue-components/tabs#Example--Basic)

*Before proceeding following steps have your tried to [Google](https://www.google.com) your question? Or, checked out [Stackoverflow](https://stackoverflow.com/search?q=quasar)?*

1) check the [FAQ below](https://gist.github.com/m0jimo/e9a01aba076492c953174309f75e3428#cli)
2) search in [Quasar docs page](https://quasar.dev/introduction-to-quasar) (See code examples e.g. [Docs - Chat - Basic](https://quasar.dev/vue-components/chat#Usage))
3) check out [Quasar forum](https://forum.quasar.dev/)
4) join [Discord chat server](https://chat.quasar.dev/)
5) if upgrading, check out the [Upgrade Guide](https://quasar.dev/start/upgrade-guide)

R: [Docs - Quasar - Awesome ever-growing community](https://quasar.dev/introduction-to-quasar#Awesome-ever-growing-community)

---

## CLI
#### Q: ```quasar dev``` or ```quasar serve``` results in ```Unknown command```

A: When developing on Windows there can problems with NPM used locally.
1) delete ```node_modules```, ```package-lock.json```
2) re-install ```yarn install --force``` with yarn.

*General rule: use NPM for global packages, Yarn for local packages.*

R: *TODO - where is the information for new users that when developing under Windows is better to use Yarn (reasons)?*  [Docs - Upgrade guide](https://quasar.dev/start/upgrade-guide#Upgrading-from-0.x-to-v1)

---

#### Q: ```quasar build``` on Win 10 - complains about resource busy or locked. Windows restart is needed whenever I build the app.
A: There is probably other process blocking the ```dist/spa``` folder (e.g. Tortoise Git, Remote Desktop etc.). Install a [Process Monitor](https://docs.microsoft.com/en-us/sysinternals/downloads/procmon) to discover the process which blocks the folder.

---

#### Q: ```quasar upgrade``` Command not found
A: Change configuration path of Terminal in your code IDE. [Docs - cli - upgrade](https://quasar.dev/quasar-cli/cli-documentation/commands-list#upgrade)
<details>
<summary>Webstorm Location</summary>

  Go to: Settings | Tools | Terminal and ```Add 'node_modules/.bin' from the project root to $PATH```

  R: [StackOverflow - terminal shows old npm version](https://stackoverflow.com/questions/53559809/phpstorm-webstorm-terminal-shows-old-npm-version)
 </details>

---

#### Q: The build stops or appears to be **frozen** and does not complete.

A: This can happen when your template code is incomplete. Look for missing end tags, or incomplete strings.

---

#### Q: ```Failed to compile with ...``` - application is not compiled and stops - regex expression.
A: There are some cases when the regex is not parsed by Babel. Try to change the regex.
<details>
<summary>Regex example</summary>

  ```const regex = /(?<=\[start])(.*)(?=\[end])/s; const result = src.match(regex);)```
 </details>

R: [Babel - Issue #6246](https://github.com/babel/babel/issues/6246)

---

## Components
#### Q: I can't find component ```QAutocomplete```
A: Autocomplete component does not exist anymore in Quasar v1. Functionality for autocompleting is part of ```QSelect``` component

R: [Docs - QSelect](```QAutocomplete``` )

---

#### Q: ```QTable``` - I'd like to get the current data table sort status
A: Use custom sort function or undocumented property ```this.$refs.YourTableName.computedData.rows```

R: [Docs - QTable](https://quasar.dev/vue-components/table), [Example - JsFiddle](https://jsfiddle.net/mojimo/8szq74dw/), [Discord chat - @Tobias Mesquita (PT-EN) - 11.04.2019](https://chat.quasar.dev/)

---

#### Q: How do I get ```QSelect``` to display the ```label``` instead of the ```value```?

A: Often you might wish to **display the label value** of your options in the QSelect rather than the actual value. For example, if you have a QSelect for SalesRegionId but wish to show the descriptive label of that region. eg. Label: NorthWestSales Value: 3

To get this to work in that way, you need to add two settings to your QSelect:
```emit-value``` ```map-options```

R: [Docs - QSelect](https://quasar.dev/vue-components/select#Example--Map-options), [Example - Codepen](https://codepen.io/david-watson-the-encoder/pen/eqNrZz)

---

## UDM
#### Q: My code in [jsFiddle](https://jsfiddle.quasar.dev/) or [Codepen](https://codepen.quasar.dev/) doesn't work
<details>
<summary>More examples</summary>

 ```QTab``` - tabs looks like they were nested <br>
 ```Browser terminal``` contains errors

</details>

A: Be sure you are not using self closing tags.

R:  [Docs - UMD - Usage](https://quasar.dev/start/umd#Usage)

---

## IE11
#### Q: Can I use [jsFiddle](https://jsfiddle.quasar.dev/) or [Codepen](https://codepen.quasar.dev/) for IE11 issues?
A: Unfortunately those services are not supporting IE11 (to date 2019-07-10). <br>
But you can use [Codesandbox](https://codesandbox.io/s/github/quasarframework/quasar-codesandbox) and [published link](https://x35jm.sse.codesandbox.io/) works on IE11. Source needs to be edited in other modern browser.

---

## IDE
#### Q: WebStorm - how to configure Run/Debug to start debugging application?
A: Add Node.js to configuration with following paths:

Node interpreter: Project ```C:\Program Files\nodejs\node.exe```<br>
Working directory: ```D:\path\myApp```<br>
JavaScrip file: ```~\AppData\Roaming\npm\node_modules\@quasar\cli\bin\quasar```<br>
Application parameters: dev<br>
URL: ```http://localhost:8080```

#### Q: WebStorm - autocomplete doesn't work for Quasar components
A: Check out the article [Hack WebStorm to Introspect Quasar Framework Components](https://medium.com/quasar-framework/how-to-hack-webstorm-to-understand-quasar-framework-components-9cb2c95f19f3) or go directly to [Plugin - Quasar Ide Helper](https://github.com/panstromek/quasar-ide-helper)

---

## Cordova

---

## Electron

---

## General

#### Q: I got in dev tools: "property or method is not defined on the instance but referenced during render"
A: This means your template code referenced something that does not exist in your script code. Double-check your template code for a mispelling.

