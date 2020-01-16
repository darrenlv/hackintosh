# From:
https://comsystoreply.de/blog-post/force-hidpi-resolutions-for-dell-u2515h-monitor
https://comsysto.github.io/Display-Override-PropertyList-File-Parser-and-Generator-with-HiDPI-Support-For-Scaled-Resolutions/

1.Enable HiDPI Mode
sudo defaults write /Library/Preferences/com.apple.windowserver.plist DisplayResolutionEnabled -bool true

2.Detect your Display
ioreg -lw0 | grep IODisplayPrefsKey
(All external monitors are identified by AppleDisplay and internal monitors by AppleBacklightDisplay.)

3.Customize your Resolutions
DisplayProductID-27a5.plist

4.Download plist and copy to System folder
sudo mount -uw /
sudo cp ./DisplayProductID-27a5.plist /System/Library/Displays/Contents/Resources/Overrides/DisplayVendorID-1d5/DisplayProductID-27a5

5.Restart Mac and use RDM to set Resolutions


# HiDPI Mode cmds:
+ sudo defaults write /Library/Preferences/com.apple.windowserver.plist DisplayResolutionEnabled -bool true
+ sudo defaults delete /Library/Preferences/com.apple.windowserver.plist DisplayResolutionEnabled

# 使用LCD平滑字体（可用时）
+ defaults write -g CGFontRenderingFontSmoothingDisabled -bool NO
+ defaults -currentHost write -globalDomain AppleFontSmoothing -int 3
+ defaults -currentHost write -globalDomain AppleFontSmoothing -int 2
+ defaults -currentHost write -globalDomain AppleFontSmoothing -int 1
+ defaults -currentHost delete -globalDomain AppleFontSmoothing