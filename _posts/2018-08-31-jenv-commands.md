---
layout:post
title:jenv commands
---

jEnv is a command line tool to help you forget how to set the JAVA_HOME environment variable


#Installation

Linux/OS X:

```$ git clone https://github.com/gcuisinier/jenv.git ~/.jenv```

Homebrew:
```$ brew install jenv```

Bash:

~~~
$ echo 'export PATH="$HOME/.jenv/bin:$PATH"' >> ~/.bash_profile
$ echo 'eval "$(jenv init -)"' >> ~/.bash_profile
~~~


Zsh:
~~~
$ echo 'export PATH="$HOME/.jenv/bin:$PATH"' >> ~/.zshrc
$ echo 'eval "$(jenv init -)"' >> ~/.zshrc

~~~

Configure:

~~~
$ jenv add /System/Library/Java/JavaVirtualMachines/1.6.0.jdk/Contents/Home
  oracle64-1.6.0.39 added
$ jenv add /Library/Java/JavaVirtualMachines/jdk17011.jdk/Contents/Home
  oracle64-1.7.0.11 added

 ~~~

Usage:

	- List managed JDKs:
	~~~
	$ jenv versions
      system 
     oracle64-1.6.0.39
     oracle64-1.7.0.11 (set by /Users/hikage/.jenv/version)
    ~~~

    - Configure global version:
    ~~~
    $ jenv global oracle64-1.6.0.39
    ~~~
    - Configure local version(per directory)
    ~~~
    $ jenv local oracle64-1.6.0.39
    ~~~
    - Configure shell instance version
    ~~~
    $ jenv shell oracle64-1.6.0.39
    ~~~

