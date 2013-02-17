wApps: all you need is manifest
----
A **wApp** is a web application in a hurry to be part of a wider webApp ecosystem. All this integreation requires is the defenition of a manifest file where the wApps are identified. This file can be placed anywhere your browser can see and you can control. Using Dropbox or Google drive to share your manifests is quite alright. The wApps ecosystem can them be invoked with the parameter **manifest** and the multiple wApps identified will be integrated as part of a single web application. This github repository maintains the root manifest which is used by default when no manifest is specified. If you want your wApps to be added to those already specified in another manifest you would then use the parameter **addmanifest** instead. For convinience and security, the wApps application itself is kept and developped at [wapps.googlecode.com](http://wapps.googlecode.com), where it enjoys the protection of SSL serving. Also for convenience's sake, this time reflecting the outstanding social coding features of github, the root manifest is kept here.

In a nutshell, all you need is to concatenate your manifest URL with 
[https://wapps.googlecode.com/git/index.html?manifest=< URL of your manifest >](https://wapps.googlecode.com/git/index.html).

###Parameters
* **manifest**: URL of the primary manifest. If none is specified, then the one kept in this github repository, ,will be used.
* **addmanifest**: 
* **myapps**: comma separated list of wApps to be automatically activated.