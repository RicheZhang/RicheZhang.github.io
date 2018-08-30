---
layout: post
title: Homebrew install multiversion java
---
# Install Multiple Java Versions on macOS High Sierra

## Install Homebrew Cask

On Mac, Homebrew is the de-facto package manager, and Homebrew Cask is the app manager. I’m going to use Cask to install Java 7 and 8.

Install Homebrew Cask first if you haven’t:
```
brew update
brew tap caskroom/cask
brew install brew-cask-completion
```

If your brew or cask is outdated, update and upgrade:
```
brew update && brew upgrade brew-cask-completion && brew cleanup && brew cask cleanup
```

## Check if we already have JDK 6, 7, 8, 9 installed by Homebrew Cask:
```
brew tap caskroom/versions
brew cask info java6
brew cask info java7
brew cask info java8
```

To check JDK 9 (latest)
```
brew cask info java
```

## Install Java 6, 7, 8, 9 (latest):

```
brew tap caskroom/versions
brew cask install java6
brew cask install java7
brew cask install java8
```

To install JDK 9 (latest)
```
brew cask install java
```

## Check if we already have JDK 6, 7, 8, 9 installed by Homebrew Cask:
```
brew tap caskroom/versions
brew cask info java6
brew cask info java7
brew cask info java8
```

To check JDK 9 (latest)
```
brew cask info java
```

## Enter jEnv

Now it is time to install `jEnv`:
```
brew install jenv
```

Add the following lines to `~/.bash_profile` This will initialize `jEnv`.

## Init jenv
```
if which jenv > /dev/null; then eval "$(jenv init -)"; fi
```

jEnv doesn’t install JDKs, so we have to tell jEnv where to look for them. Type these commands to register JDKs in jEnv (replace the minor and patch versions with yours):
```
jenv add /Library/Java/JavaVirtualMachines/jdk1.7.0_79.jdk/Contents/Home/
jenv add /Library/Java/JavaVirtualMachines/jdk1.8.0_66.jdk/Contents/Home/
```

After that, run this command to list all registered JDKs:
```
jenv versions
```

source: http://davidcai.github.io/blog/posts/install-multiple-jdk-on-mac/