wApps: all you need is a manifest
----
A **wApp** is a web application in a hurry to be part of a wider webApp ecosystem. All this integreation requires is the defenition of a manifest file where the wApps are identified. This file can be placed anywhere your browser can see and you can control. Using Dropbox or Google drive to share your manifests is quite alright. The wApps ecosystem can them be invoked with the parameter **manifest** and the multiple wApps identified will be integrated as part of a single web application. This github repository maintains the root manifest which is used by default when no manifest is specified. If you want your wApps to be added to those already specified in another manifest you would then use the parameter **addmanifest** instead. For convinience and security, the wApps application itself is kept and developped at [wapps.googlecode.com](http://wapps.googlecode.com), where it enjoys the protection of SSL serving. In order to make the most of GitHub's outstanding social coding features, the root manifest is kept here. If serving wApps through https is not important to you, you can also use [wapps.github.com](http://wapps.github.com)

In a nutshell, all you need is to concatenate your manifest URL with 
[https://wapps.googlecode.com/git/index.html?manifest=< URL of your manifest >](https://wapps.googlecode.com/git/index.html).

![image](http://wapps.googlecode.com/git/ScreenShot.png)

###Parameters
* **manifest**: URL of the primary manifest. If none is specified, then the one kept in this github repository,[https://raw.github.com/wApps/manifest/master/manifest.js](),will be used. In other words, [https://wapps.googlecode.com/git/index.html]() is equivalent to [https://wapps.googlecode.com/git/index.html?manifest=https://raw.github.com/wApps/manifest/master/manifest.js]()
* **addmanifest**: URL of the secondary manifest. The new wApps will be added to the ones defines in the primary manifest, if they are new (if they don't have a name already in use).
* **loadApps**: comma separated list of wApps to be automatically activated and displayed under "myApps". For example, [http://wapps.github.com?loadApps=ET callHome,someWApp](), or the https hosted equivalent, [https://wapps.googlecode.com/git/index.html?loadApps=ET callHome,someWApp](). 

### Manifest
This is the only file an wApps ecosystem needs to maintain. It includes four sections: 1) Branding, 2) Tabs, 3) Apps, and 4) Authors. The configuration is straight forward and it is best undertood by inspecting an existing manifest, such as the [root manifest](https://github.com/wApps/manifest/blob/master/manifest.js) maintained in this github repository. As the inspection of this file will reveal, the manifest is a JavaScript file, and each app will use a .builUI(id) method that assembles the wApp's UI within a DOM element with that id. The processing of the manifest object by the wApps application, [wApps.js](https://code.google.com/p/wapps/source/browse/wApps.js), adds a this.require method, which will load code from a URL before moving on to the UI assembly. The remote code loading is only thriggered if the object specified by this.namespace is not already there. If it is, wApps proceeds directly to UI assembly. The only namespaces taken by the wApps ecosystem, besides "wApps", are those created by jQuery and twitter bootstrap (what is it?). 

If you have a wApp that is of general interrest and want to added it to the root manifest, you are welcome to add it to add it here as a pull request.

### Security and trust
Because they are executed in a shared nam space, wApps are an experiment is social coding. Each manifest defines a community of developers that trusts eachother. Hacking information from one wApp by another can be avoided by using iframes, as illustrated in teh root manifest. However, to some extent, that also defeats the purpose of the app ecosystem, where analytical workflows can be assembled with great flexibility by combining contributions from multiple wApps. An interresting balance between these two situations is to use iframes with event listeners. Either way, stricking the righ balance between flexibility and security is entirely left to the developper, who gets define the .buildUI function.

