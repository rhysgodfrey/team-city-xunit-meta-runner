Team City xUnit Meta Runner
===========================

[![Project Status: Unsupported - The project has reached a stable, usable state but the author(s) have ceased all work on it. A new maintainer may be desired.](http://www.repostatus.org/badges/0.1.0/unsupported.svg)](http://www.repostatus.org/#unsupported)
[![Build status](https://ci.appveyor.com/api/projects/status/3tvv3y7tijdokq44)](https://ci.appveyor.com/project/rhysgodfrey/team-city-xunit-meta-runner)

> __NOTE__ - This project is now unsupported. The current build is still available for use, and feel free to fork this code base. There is an alternative plugin that is part of the [Team City Meta Runner Power Pack](https://github.com/JetBrains/meta-runner-power-pack/tree/master/xunit.net), and [Scott Mackay has an example in this blog post](http://www.wwwlicious.com/2015/09/25/teamcity-dotcover-xunit-at-last/). With xUnit becoming more central in .NET core I'd expect better support to come into a future version of TeamCity. 

Easily run [xUnit](https://github.com/xunit/xunit) tests using [Team City](http://www.jetbrains.com/teamcity/).

This Team City plugin adds an extra option when creating a Build Step in Team City 'xUnit'. This is currently quite simple and only allows the selection of one DLL containing xUnit tests to be run. Wildcards and multiple assemblies are not supported (as this is not supported by the xUnit console runner).

The plugin will copy a version of the xUnit runner to all build agents to allow tests to be run without any additional configuration. The plugin is currently using the 2.0.0-beta-build2650 version of the xUnit console runner.

The plugin has been tested on Team City 8.0.3, but should work with any version of Team City 8.

### Installation

1. Download 'xunit-build-runner.zip' from the [latest release](https://github.com/rhysgodfrey/team-city-xunit-meta-runner/releases/latest)
2. Copy this file into the _[Team City Data Directory]\plugins_ directory on the Team City Server, by default this is _C:\ProgramData\JetBrains\TeamCity\plugins_
3. Restart the Team City server

The xUnit build step type should now be available.

### Building the plugin

To build the plugin from code, use MSBuild to run _package.msbuild_, this will create the xunit-build-runner.zip file. The [MSBuild Community Tasks](https://github.com/loresoft/msbuildtasks) must be installed to run this.
