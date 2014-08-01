# Software Development Technology Study Resources and Help

# HTML5

Prerequisites:

- familiarity with layout markup languages

Resources:

- [http://html5doctor.com/](http://html5doctor.com/) Has up to date references on best practices for HTML5. You can study the element tags from the [http://html5doctor.com/element-index/](element index).
 - This shows recent browser usage statistics globally: [http://gs.statcounter.com/](http://gs.statcounter.com/)  
- This shows status of each HTML5 feature in major browsers: [http://caniuse.com/](http://caniuse.com/)

# Javascript
Prerequisites:

- some programming, preferably with a dynamic language

Resources:

- **node** Read-Eval-Print-Loop (REPL) interpreter  
The interpreter allows you to test javascript code in an interactive environment.
- Javascript function patterns
[http://www.adequatelygood.com/JavaScript-Module-Pattern-In-Depth.html](http://www.adequatelygood.com/JavaScript-Module-Pattern-In-Depth.html)


# TypeScript
Prerequisites:

- some Javascript
- experience with a typed language like C++

Resources:

- The [main site](http://www.typescriptlang.org) has many resources.  
- This video explains the [design of Typescript](http://media.ch9.ms/ch9/c3e5/e5e02f2e-5962-48db-9ddd-85e27a4fc3e5/IntroducingTSAndersH_mid.mp4)
- The [on-line compiler](http://www.typescriptlang.org/Playground/), which is very handy.  
- [TypeScript Modules Demystified : Internal, AMD with RequireJS](http://www.youtube.com/watch?v=KDrWLMUY0R0)
- You can ask questions live using a [web-based IRC chat client](https://webchat.freenode.net).  
  Pick any user name, and specify the **typescript** channel.
 
Notes on IRC:

- You can use [pastebin](http://pastebin.com) to transfer code or data to people anonymously.
- You can get a short URL from the [Google URL Shortener](http://goo.gl)





# Node.js Server and npm Package Manager
Prerequisites:

- none, if just using the node Read-Eval-Print-Loop (REPL)
- strong Javascript, if writing server apps

Resources:

- [The main site has many resources](http://nodejs.org)
- [The API reference](http://nodejs.org/api)
- You can ask questions live using a [web-based IRC chat client](https://webchat.freenode.net).  
  Pick any user name, and specify the **node.js** channel.



# MongoDB
Prerequisites:

- experience with JSON

Resources:

- [overview](http://docs.mongodb.org/manual/tutorial/getting-started/)
- [CRUD](http://docs.mongodb.org/manual/crud/)
- [Geospatial support](http://docs.mongodb.org/manual/applications/geospatial-indexes/)


# Grunt Build Manager
Prerequisites:

- experience building software

Resources:

- [http://gruntjs.com/]()
- [http://jessefreeman.com/dev-techniques/automating-typescript-with-node-and-grunt/]()



# AngularJS Web-App Framework
Prerequisites:

- strong Javascript
- strong HTML
- strong DOM
- some CSS


Resources:

- [http://docs.angularjs.org/guide/concepts](http://docs.angularjs.org/guide/concepts)  
Provides a clear overview of the framework.
- [When to use directives controllers or services](http://kirkbushell.me/when-to-use-directives-controllers-or-services-in-angular/)  
The first example I found for how to get a service to work.
- [Angular using Typescript](http://www.youtube.com/watch?v=u6TeBM_SC8w)


# Twitter Bootstrap
An Javascript+CSS library that provides a clean look that adjusts well for mobile devices.

Prerequisites:

- basic HTML
- basic CSS

Resources:

- [http://getbootstrap.com/]()

# Git
Prerequisites:

- basic familiarity with source control

Resources:

- [http://git-scm.com/]()


Some useful commands:

- git stash list
- git stash
- git stash apply
- git stash drop
- git stash -p show
- git archive --format=tar b5ba736 >~/tmp/b5ba736.tar


# Chrome Debugger
Prerequisites:

- familiarity with javascript
- familiarity with debuggers

Use these undocumented functions in the console:

- debug(function_name)
Puts a breakpoint at the named function
- monitor(function_name)
Logs each time the function is executed


# Services to Push Notifications to Mobile Devices
- [https://support.google.com/googleplay/android-developer/answer/2663268?hl=en](Google Cloud Messaging (GCM))
- [https://developer.apple.com/library/ios/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/Introduction.html](Push Notifications)

# Technologies to Investigate

- [An AngularJS widget that creates a complete form given a JSON schema](https://gist.github.com/dalcib/3174225) 
- [What can you do with PostgreSQL and JSON?](http://clarkdave.net/2013/06/what-can-you-do-with-postgresql-and-json/)
- [A popular DB binding for PostGres](https://github.com/brianc/node-postgres)
- [SVG editor](http://sourceforge.net/projects/inkscape/?source=dlp)