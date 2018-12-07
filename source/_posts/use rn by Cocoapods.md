---
title: use rn by Cocoapods
---
# use rn by Cocoapods

配置信息
rn版本0.50.0

cocoapods:1.4

Podfile

```
platform :ios, '8.0'

$rn_node_moudles_dir = '../RN/node_modules'
$rn_react_pod_dir =  $rn_node_moudles_dir+'/react-native'

def ymm_rn_debug_pod
    # Your 'node_modules' directory is probably in the root of your project,
    # but if not, adjust the `:path` accordingly
    pod 'React', :path => $rn_react_pod_dir, :subspecs => [
    
    'BatchedBridge', #if RN >= 0.43
    #CxxBridge 代替 BatchedBridge
    #'CxxBridge',

    'Core',
    'DevSupport', # Include this to enable In-App Devmenu if RN >= 0.43
    'RCTNetwork',
    'RCTWebSocket', # needed for debugging
    'RCTActionSheet',
    'RCTAnimation',
    'RCTImage',
    'RCTText',

#    'RCTActionSheet',
#    'RCTBlob',
#    'RCTSettings',
#    'RCTVibration',
#    'RCTLinkingIOS',
#    'RCTAnimation',
#    'RCTGeolocation',
    # Add any other subspecs you want to use in your project
    ]
    # Explicitly include Yoga if you are using RN >= 0.42.0
    pod 'yoga', :path => $rn_react_pod_dir+'/ReactCommon/yoga'

    # Third party deps podspec link
    pod 'DoubleConversion', :podspec => $rn_react_pod_dir+'/third-party-podspecs/DoubleConversion.podspec'
    pod 'GLog', :podspec => $rn_react_pod_dir+'/third-party-podspecs/GLog.podspec'
    pod 'Folly', :podspec => $rn_react_pod_dir+'/third-party-podspecs/Folly.podspec'

end

```

### 用CxxBridge替换BatchedBridge
将podfile修改后，会出现问题

https://github.com/facebook/react-native/issues/16381

https://github.com/facebook/react-native/pull/16664

```
   s.subspec "jschelpers" do |ss|
     ss.dependency             "Folly", "2016.09.26.00"
+    ss.dependency             "React/PrivateDatabase"
     ss.compiler_flags       = folly_compiler_flags
     ss.source_files         = "ReactCommon/jschelpers/*.{cpp,h}"
     ss.private_header_files = "ReactCommon/jschelpers/*.h"
     ss.pod_target_xcconfig  = { "HEADER_SEARCH_PATHS" => "\"$(PODS_TARGET_SRCROOT)/ReactCommon\"" }
     ss.framework            = "JavaScriptCore"
   end
 
+  s.subspec "PrivateDatabase" do |ss|
+    ss.source_files         = "ReactCommon/privatedata/*.{cpp,h}"
+    ss.private_header_files = "ReactCommon/privatedata/*.h"
+  end
+
   s.subspec "cxxreact" do |ss|
     ss.dependency             "React/jschelpers"
     ss.dependency             "boost"
     
```
