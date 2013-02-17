wApps: all you need is a manifest
----
A **wApp** is a web application in a hurry to be part of a wider webApp ecosystem. All this integreation requires is the defenition of a manifest file where the wApps are identified. This file can be placed anywhere your browser can see and you can control. Using Dropbox or Google drive to share your manifests is quite alright. The wApps ecosystem can them be invoked with the parameter **manifest** and the multiple wApps identified will be integrated as part of a single web application. This github repository maintains the root manifest which is used by default when no manifest is specified. If you want your wApps to be added to those already specified in another manifest you would then use the parameter **addmanifest** instead. For convinience and security, the wApps application itself is kept and developped at [wapps.googlecode.com](http://wapps.googlecode.com), where it enjoys the protection of SSL serving. Also for convenience's sake, this time reflecting the outstanding social coding features of github, the root manifest is kept here.

In a nutshell, all you need is to concatenate your manifest URL with 
[https://wapps.googlecode.com/git/index.html?manifest=< URL of your manifest >](https://wapps.googlecode.com/git/index.html).

![image](http://wapps.googlecode.com/git/ScreenShot.png)

###Parameters
* **manifest**: URL of the primary manifest. If none is specified, then the one kept in this github repository,[https://raw.github.com/wApps/manifest/master/manifest.js](),will be used. In other words, [https://wapps.googlecode.com/git/index.html]() is equivalent to [https://wapps.googlecode.com/git/index.html?manifest=https://raw.github.com/wApps/manifest/master/manifest.js]()
* **addmanifest**: URL of the secondary manifest. The new wApps will be added to the ones defines in the primary manifest, if they are new (if they don't have a name already in use).
* **myapps**: comma separated list of wApps to be automatically activated and displayed under "myApps".

### Manifest
This is the only file an wApps ecosystem needs to maintain. It includes four sections: 1) Branding, 2) Tabs, 3) Apps, and 4) Authors. The configuration is straight forward and it is best undertood by inspecting an existing manifest, such as the [root manifest](https://github.com/wApps/manifest/blob/master/manifest.js) maintained in this github repository.
