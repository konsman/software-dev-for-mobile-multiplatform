### Steps for Apple M2 silicon

Instruction on how to set up a development environment on new Apple MacBook Pro with M2 chip to support cross-platform mobile development.

1. Install browser: Chrome browser and login as google user.
2. Install XCode (it will install git as well) from App Store, launch at least ones.
3. Install Homebrew from https://brew.sh/ and update a zprofile
4. Install VSCode https://code.visualstudio.com and install in PATH
5. Install JDK - temurin 11 https://adoptium.net/installation/ through homebrew
6. Install Android Studio for ARM64
7. Install Kotlin Multiplatform Mobile plugin (0.5.2)
8. Install KDoctor "brew install kdoctor" - run and see problem with XCode and cocapods
9. Fix Command Line Tools field in XCode setting - select your Xcode.
10. Update ruby:

    1. "brew install ruby-install chruby"
    2. Edit .zshrc:

       source /opt/homebrew/opt/chruby/share/chruby/chruby.sh

       source /opt/homebrew/opt/chruby/share/chruby/auto.sh

       chruby ruby-3.1.2

    3. install the lates ruby: "ruby-install --latest ruby" (check what version installed and update .zshrc accordingly) (check ruby --version)

11. Install cocoapods: sudo gem install cocoapods
12. Run kdoctor and see that all conditions satisfied.
13. Build test KMM project and successfully run on iOS and Android simulators.
14. Install NVM: github.com/nvm-sh/nvm
15. Install Node (16): nvm install 16
16. install watchman https://facebook.github.io/watchman/ brew install watchman
17. define ANDROID_HOME path in profile and paths to tools and SDK
18. Test with react native test project with following changes:
    1. after running "npx react-native init AwesomeProject" you may have a problem with ruby version.
    2. change .ruby-version to current version on your machine (3.2.1 in my case)
    3. do "bundle install"
    4. in ios folder do:"pod install" (you nay need to run" pod cache clean --all )
    5. open Android project in Android Studio ( it will generate local.properties file with correct path to SDK for your project)
    6. you can now run "npx react-native run-ios" and "npx react-native run-android"
19. Install miniconda from conda.io base with python 3.1
