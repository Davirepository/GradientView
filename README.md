# GradientView
Framework that allow to create a gradient from a set of colors 

Once you have Carthage [installed](https://github.com/Carthage/Carthage#installing-carthage), you can begin adding frameworks to your project. Note that Carthage only supports dynamic frameworks, which are only available on iOS 8 or later (or any version of OS X).

## Adding frameworks to an application

### Getting started. Building for iOS, tvOS, or watchOS

1. Create a [Cartfile](https://github.com/Carthage/Carthage/blob/master/Documentation/Artifacts.md#cartfile) that lists the frameworks you’d like to use in your project. In terminal: <br/>`cd` project path 
<br/>`touch Cartfile` 
<br/>`open -a Xcode Cartfile` 
<br/>In Cartfile copy `github "Davirepository/GradientView" >= 1.0.1` and save.
2. Run carthage update. This will fetch dependencies into a [Carthage/Checkouts](https://github.com/Carthage/Carthage/blob/master/Documentation/Artifacts.md#carthagecheckouts) folder, then build each one or download a pre-compiled framework.
3. On your application targets’ General settings tab, in the “Linked Frameworks and Libraries” section, drag and drop each framework you want to use from the [Carthage/Build](https://github.com/Carthage/Carthage/blob/master/Documentation/Artifacts.md#carthagebuild) folder on disk.
4. On your application targets’ Build Phases settings tab, click the + icon and choose New Run Script Phase. Create a Run Script in which you specify your shell (ex: /bin/sh), add the following contents to the script area below the shell: `/usr/local/bin/carthage copy-frameworks`
5. In section Input Files write this: `$(SRCROOT)/Carthage/Build/iOS/GradientView.framework`
