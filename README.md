# setup-mean-ts

Instructions for how to set up a MEAN (MongoDB / Express.js / Angular.js / Node.js) + Typescript development environment on Mac, with free software.

You should have OSX El Capitan (10.11.1) or later.  
If you don't find the answers you need in these instructions, you may [find additional help here](http://bit.ly/19Fksyd).

# Install Google Chrome Web Browser
**Dependencies**: No dependencies. You may set up Chrome whenever you like.
We use [Google Chrome](https://www.google.com/intl/en/chrome/browser/), because it:

- Uses the Javascript V8 VM (which is used by Node.js).
- Integrates well with Google tools.
- Has a powerful Javascript debugger.

## JSON Viewer

The [JSONView](https://chrome.google.com/webstore/detail/jsonview/chklaanhfefbnpoihckbnefhakgolnmc?hl=en) Chrome extension allows viewing of JSON files directly in Chrome.

If you have already installed Chrome extensions through your Google account on another machine, then those extensions should already be installed with a new installation once you have logged in to your Google account.

If this is your first time, then follow these instructions.
Complete the installation:

- Visit [chrome://extensions](chrome://extensions)
- Configure JSONView by checking **Allow access to file URLs**

Confirm the installation:  
Query the google maps servers for directions from Chicago to Los Angeles by clicking
[here](http://maps.googleapis.com/maps/api/directions/json?origin=Chicago,IL&destination=Los+Angeles,CA&waypoints=Joplin,MO|Oklahoma+City,OK&sensor=false),
then you should see nicely structured JSON in your browser.
The document should highlight structure as you move your mouse,
and it should collapse sections when you click on minus signs,
and expand sections when you click on plus signs.


# Install an Editor
We use Atom, v1.1.0 or later.  

<a name="Atom Editor"></a>
## Install Atom Editor
**Dependencies**: No dependencies. You may set up Atom whenever you like.  
Download from [https://atom.io/](https://atom.io/)

Complete the install by unzipping the archive, and dragging the Atom application into your Applications folder. Run Atom and set it to remain in your dock.

### Install TypeScript support

From within Atom, search for the *atom-typescript* add-on, and install it.  
From Settings (⌘,), under Packages, search for *atom-typescript*.
Find it in the results, and install it.


### Configure so tabs are set to 4 spaces for all text files.

From Settings (⌘,), under Editor Settings:  
- select "Soft Tabs"
- set "Tab Length" to 4.

### Configure so whitespace is standardized upon file save.

#### Strip trailing whitespace from all lines

This is standard behavior in Atom v1.1.0, controlled by the *whitespace* package.

#### Convert tabs to spaces upon file save.

From within Atom, search for the *tabs-to-spaces* add-on, and install it.

From Settings (⌘,), under Packages, search for *tabs-to-spaces*.
Find it in the results, and install it.

Update the general Atom configuration file, ~/.atom/config.cson, by adding the following settings:  
```
"*":
  "tabs-to-spaces":
    onSave: "untabify"
".source.makefile":
  "tabs-to-spaces":
    onSave: "tabify"
```

#### Exclude some directories from file search

This is not supported yet in Atom. See [find-and-replace/issues/149](https://github.com/atom/find-and-replace/issues/149)

### Configure so files are saved upon losing window focus.

From the Settings (⌘,), find *autosave* in Packages, and check the "Enabled" box.

### Set a white cursor
From the Settings (⌘,) Install, find and install the *white-cursor* package.

### Enable previewing MarkDown files
This is standard in Atom v1.1.0.


<a name="iTerm2 App"></a>
# Install iTerm2
**Dependencies**: none

Install from [https://www.iterm2.com/](https://www.iterm2.com/)



<a name="GitHub App"></a>
# Install GitHub App
**Dependencies**:  
- You must have a GitHub account.
- You should also have SSH keys. You can set them up by following this article: [https://help.github.com/articles/generating-ssh-keys](https://help.github.com/articles/generating-ssh-keys)
- There are no dependencies on any other tools. You may set up the GitHub app whenever you like.  


Get GitHub app from: [http://mac.github.com/](http://mac.github.com/)  

- Download
- Move app to Application folder  
- Run the app, and follow its configuration instructions.  
  - Make sure you install the git command line tools.

This should give you a functional GUI for managing your workspace with git.  
However, before you start using the workspace, you must finish the remaining configuration in these instructions.

# Install XCode and the Command Line Tools
**Dependencies**: XCode 7.0.0 requires OSX Yosemite/10.10.

You may set up Xcode whenever you like.
Install XCode from the Apple App Store. Make sure get the correct version for your OSX version.  
We are using:
- XCode 7.2.1 on OSX El Capitan/10.11.
- XCode 7.0.0 on OSX Yosemite/10.10.

Once you have XCode installed, install Command Line Tools:

```
xcode-select --install
```

# Install Brew Package Manager

See the Homebrew page: [http://brew.sh](http://brew.sh)

- Install  
Use the download command from the above page, it should be something like:

  ```
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
  ```
- Update the local indexes

  ```
  brew update
  brew doctor
  ```


# Install Node.js and Npm
**Dependencies**:  
- homebrew (above)

Install using homebrew:
```
homebrew install node
```

As of Nov 8, 2015, this installs:
- node v5.0.0
- npm 3.3.9



## npm
We no longer use global packages.  

In all cases, use local packages.  
This better supports deployment and testing in the cloud, where there are no global installs.

### Notes on common packages

- Typescript  
We use [TypeScript](http://www.typescriptlang.org) whenever possible, because it adds strong typing to javascript.  
Use npm to install typescript:
```
npm install typescript
```
To update:  
```
npm cache clean
npm update typescript
```
- Typescript Declaration Files Manager
We use the [TypeScript Definition manager for DefinitelyTyped](https://github.com/DefinitelyTyped/tsd) for managing TypeScript declaration files.  
However, it appears that [Typings is replacing TSD](https://github.com/DefinitelyTyped/tsd/issues/269), so we will be moving to Typings soon.

Use npm to install tsd:
```
npm install tsd
```
To update:  
```
npm cache clean
npm update tsd
```
- Test Framework  
We use [Mocha](http://visionmedia.github.io/mocha/) because it is flexible,
and karma to connect to browsers for the client.  
Use npm to install both:

   ```
   npm install mocha karma karma-mocha karma-requirejs karma-chrome-launcher karma-firefox-launcher
   ```
- Source Debugger  
We'll use [Node Inspector](https://github.com/node-inspector/node-inspector/blob/master/readme.md) for source level debugging of node programs, including mocha tests.  
Use npm to install node-inspector:

   ```
   npm install node-inspector
   ```
- Web Development Framework  
We use [express](https://npmjs.org/package/express), because it provides simple routing.
  ```
  npm install express
  ```
- Client package management  
We use bower, when npm isn't supported.

See the Bower page: [http://http://bower.io/](http://http://bower.io/)
  ```
  npm install bower
  ```


# Install MongoDB
**Dependencies**: You must have brew, and XCode.  
**Reference**: [tutorial/install-mongodb-on-os-x](http://docs.mongodb.org/manual/tutorial/install-mongodb-on-os-x/)

Use Homebrew to install MongoDB:

```
brew update
brew install mongodb
```

Create the database storage directory:

```
sudo mkdir -p /mongo_data/play
sudo chown $USER /mongo_data/play
```

And to run mongo:

```
mongod --dbpath /mongo_data/play
```


# Install Java
- The Java JDK download link. This was hard to find (the JRE link was easy). To find this link I had to search for the name of the download file, in this case it was jdk-7u55-macosx-x64.dmg
[http://www.oracle.com/technetwork/java/javase/downloads/jdk7-downloads-1880260.html](Oracle's download site)

Add these lines to your ~/.profile:

```
export JAVA_HOME=/Library/Java/JavaVirtualMachines/jdk1.7.0_55.jdk/Contents/Home
export PATH=$PATH:$JAVA_HOME/bin
```

# Install Redis
Follow the instructions at: [http://redis.io/download](http://redis.io/download)

# Install Beanstalk Message Queue
[http://kr.github.io/beanstalkd/download.html](http://kr.github.io/beanstalkd/download.html)
brew install beanstalkd
beanstalkd


# Install CLOC - Count Lines of Code

This counts lines of code, and has many options.

- [Documentation](http://cloc.sourceforge.net/)
- [Download](http://sourceforge.net/projects/cloc/files/latest/download?source=files)


#### Install

**Dependencies**: No dependencies. You may set up cloc whenever you like.

After downloading, copy it to the /usr/local/bin directory,
and create a shell function to run cloc with the correct arguments.
Make sure you change the CLOC_VER variable below to match the version of what you downloaded.

```
CLOC_VER=1.60
sudo cp /Users/$USER/Downloads/cloc-$CLOC_VER.pl /usr/local/bin
sudo chmod +x /usr/local/bin/cloc-$CLOC_VER.pl
cat - >> ~/.profile << END
function cloc()
{
    cloc-$CLOC_VER.pl --force-lang-def=$HOME/.cloc.lang_def \$*
}
END
source ~/.profile
```

Create ~/.cloc.lang_def, and set its contents to:

```
HTML
    filter remove_html_comments
    filter call_regexp_common HTML
    extension htm
    extension html
    3rd_gen_scale 1.90
Javascript
    filter remove_matches ^\s*//
    filter call_regexp_common C
    filter remove_inline //.*$
    extension js
    extension json
    3rd_gen_scale 1.48
    end_of_line_continuation \\$
Typescript
    filter remove_matches ^\s*//
    filter call_regexp_common C
    filter remove_inline //.*$
    extension ts
    3rd_gen_scale 1.48
    end_of_line_continuation \\$
```


### Examples
```
cloc schema src test  
cloc --exclude-lang=HTML,Javascript schema src test
```



# Install generateCodeVocabulary

#### Description

**generateCodeVocabulary** determines the symbols used in a collection of source files, and counts their use.  

It strips out all comments, integers, single-line strings,
and single-line slash delimited regular expressions before collecting the vocabulary.
This results in a vocabulary that contains all program symbols and keywords.

Warning: it does not work on files that have strings or regular expressions that span multiple lines.

This has been tested with TypeScript/Javascript, but should work for any language that has a CLOC configuration, and that has C-style strings, and slash delimited regular expressions.

By keeping the generated vocabulary files for each version of code, changes can be verified before submitting code to your version control system.


#### Install

**Dependencies**: This uses CLOC.


This utility is part of this **setup-mean-ts** repo.
Copy the files to /usr/local/bin:

```
chmod +x generateCodeVocabulary.py
sudo cp generateCodeVocabulary.* /usr/local/bin
```

#### Examples
These commands are run as part of our **reports** target of make:

```
    generateCodeVocabulary.py --ext ts --out reports/client.vocabulary.json src/client
    generateCodeVocabulary.py --ext ts --out reports/server.vocabulary.json src/server
    generateCodeVocabulary.py --ext ts --out reports/test.vocabulary.json test
    -rm reports/all.vocabulary.json
    generateCodeVocabulary.py --ext vocabulary.json --out reports/all.vocabulary.json reports
```
