# MacOS_Sierra_Ubiquity.framework
xcode 6 crashes on load, missing framework

Error looking up handler class for extension 'Xcode.iCloud.CmdHandler.FetchEvent'

Download the Ubiquity.framework directory by pulling the repository or downloading zip

ditto ~Downloads/Ubiquity.framework /Applications/Xcode.app/Contents/Frameworks/Ubiquity.framework

cd /Applications/Xcode.app/Contents/PlugIns/iCloudSupport.ideplugin/Contents/MacOS
install_name_tool -change /System/Library/PrivateFrameworks/Ubiquity.framework/Versions/A/Ubiquity @rpath/Ubiquity.framework/Versions/A/Ubiquity ./iCloudSupport

cd /Applications
codesign --deep -f -s - ./Xcode.app

