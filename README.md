# Travis-Issue-7361

Project created to document the issue [#7361](https://github.com/travis-ci/travis-ci/issues/7361) in travis-ci

# Description

This simple project with just a very simple travis configuration shows how the version of fastlane is outdated in
the deploy step even though it is updated before_deploy.

[Here](https://github.com/dcordero/Travis-Issue-7361/blame/master/README.md#L777) you can see that `fastlane --version` shows `fastlane 2.18.1` after executing `script`. Which is correct.

[Here](https://github.com/dcordero/Travis-Issue-7361/blame/master/README.md#L800) you can see that `fastlane --version` shows `fastlane 1.111.0` even though it was updated [here](https://github.com/dcordero/Travis-Issue-7361/blame/master/README.md#L781)

- The failing job can be found here: https://travis-ci.org/dcordero/Travis-Issue-7361/builds/204203405

# Error log

```
Worker information
hostname: worker-jupiter-brain:3eb520e3-a8dd-4b77-ab54-6b5052533e7c
version: v2.6.2-8-g42382d7 https://github.com/travis-ci/worker/tree/42382d728490166eff93d8242e994664150a296a
instance: f2bd8148-d881-436c-bbce-581df07fd6aa:travis-ci-macos10.12-xcode8.2-1481567376
startup: 2m18.825164558s
Build system information
Build language: objective-c
Build id: 204203405
Job id: 204203406
travis-build version: 2b04abe3b

grep: /etc/apt/sources.list.d/*: No such file or directory
sudo: apt-get: command not found
$ export DEBIAN_FRONTEND=noninteractive
Fix WWDRCA Certificate
Unable to delete certificate matching "0950B6CD3D2F37EA246A1AAA20DFAADBD6FE1F75"security: AppleWWDRCA.cer: already in /Library/Keychains/System.keychain
$ rvm use
Warning! PATH is not properly set up, '/Users/travis/.rvm/gems/ruby-2.0.0-p648/bin' is not at first place,
         usually this is caused by shell initialization files - check them for 'PATH=...' entries,
         it might also help to re-add RVM to your dotfiles: 'rvm get stable --auto-dotfiles',
         to fix temporarily in this shell session run: 'rvm use ruby-2.0.0-p648'.
Using /Users/travis/.rvm/gems/ruby-2.0.0-p648
$ git clone --depth=50 --branch=master https://github.com/dcordero/Travis-Issue-7361.git dcordero/Travis-Issue-7361
Cloning into 'dcordero/Travis-Issue-7361'...
remote: Counting objects: 15, done.
remote: Compressing objects: 100% (13/13), done.
remote: Total 15 (delta 3), reused 6 (delta 0), pack-reused 0
Unpacking objects: 100% (15/15), done.

$ cd dcordero/Travis-Issue-7361
$ git checkout -qf e47e81e7d6a7f60ca5c9b003d14794ed0d746c69
$ rvm use default
Using /Users/travis/.rvm/gems/ruby-2.0.0-p648

$ ruby --version
ruby 2.0.0p648 (2015-12-16 revision 53162) [x86_64-darwin16.1.0]
$ rvm --version
rvm 1.27.0 (latest) by Wayne E. Seguin <wayneeseguin@gmail.com>, Michal Papis <mpapis@gmail.com> [https://rvm.io/]
$ bundle --version
Bundler version 1.13.6
$ xcodebuild -version -sdk
iPhoneOS10.2.sdk - iOS 10.2 (iphoneos10.2)
SDKVersion: 10.2
Path: /Applications/Xcode.app/Contents/Developer/Platforms/iPhoneOS.platform/Developer/SDKs/iPhoneOS10.2.sdk
PlatformVersion: 10.2
PlatformPath: /Applications/Xcode.app/Contents/Developer/Platforms/iPhoneOS.platform
ProductBuildVersion: 14C89
ProductCopyright: 1983-2016 Apple Inc.
ProductName: iPhone OS
ProductVersion: 10.2

iPhoneSimulator10.2.sdk - Simulator - iOS 10.2 (iphonesimulator10.2)
SDKVersion: 10.2
Path: /Applications/Xcode.app/Contents/Developer/Platforms/iPhoneSimulator.platform/Developer/SDKs/iPhoneSimulator10.2.sdk
PlatformVersion: 10.2
PlatformPath: /Applications/Xcode.app/Contents/Developer/Platforms/iPhoneSimulator.platform
ProductBuildVersion: 14C89
ProductCopyright: 1983-2016 Apple Inc.
ProductName: iPhone OS
ProductVersion: 10.2

MacOSX10.12.sdk - macOS 10.12 (macosx10.12)
SDKVersion: 10.12
Path: /Applications/Xcode.app/Contents/Developer/Platforms/MacOSX.platform/Developer/SDKs/MacOSX10.12.sdk
PlatformVersion: 1.1
PlatformPath: /Applications/Xcode.app/Contents/Developer/Platforms/MacOSX.platform
ProductBuildVersion: 16C58
ProductCopyright: 1983-2016 Apple Inc.
ProductName: Mac OS X
ProductUserVisibleVersion: 10.12.2
ProductVersion: 10.12.2

AppleTVOS10.1.sdk - tvOS 10.1 (appletvos10.1)
SDKVersion: 10.1
Path: /Applications/Xcode.app/Contents/Developer/Platforms/AppleTVOS.platform/Developer/SDKs/AppleTVOS10.1.sdk
PlatformVersion: 10.1
PlatformPath: /Applications/Xcode.app/Contents/Developer/Platforms/AppleTVOS.platform
ProductBuildVersion: 14U591
ProductCopyright: 1983-2016 Apple Inc.
ProductName: Apple TVOS
ProductVersion: 10.1

AppleTVSimulator10.1.sdk - Simulator - tvOS 10.1 (appletvsimulator10.1)
SDKVersion: 10.1
Path: /Applications/Xcode.app/Contents/Developer/Platforms/AppleTVSimulator.platform/Developer/SDKs/AppleTVSimulator10.1.sdk
PlatformVersion: 10.1
PlatformPath: /Applications/Xcode.app/Contents/Developer/Platforms/AppleTVSimulator.platform
ProductBuildVersion: 14U591
ProductCopyright: 1983-2016 Apple Inc.
ProductName: Apple TVOS
ProductVersion: 10.1

WatchOS3.1.sdk - watchOS 3.1 (watchos3.1)
SDKVersion: 3.1
Path: /Applications/Xcode.app/Contents/Developer/Platforms/WatchOS.platform/Developer/SDKs/WatchOS3.1.sdk
PlatformVersion: 3.1
PlatformPath: /Applications/Xcode.app/Contents/Developer/Platforms/WatchOS.platform
ProductBuildVersion: 14S471a
ProductCopyright: 1983-2016 Apple Inc.
ProductName: Watch OS
ProductVersion: 3.1

WatchSimulator3.1.sdk - Simulator - watchOS 3.1 (watchsimulator3.1)
SDKVersion: 3.1
Path: /Applications/Xcode.app/Contents/Developer/Platforms/WatchSimulator.platform/Developer/SDKs/WatchSimulator3.1.sdk
PlatformVersion: 3.1
PlatformPath: /Applications/Xcode.app/Contents/Developer/Platforms/WatchSimulator.platform
ProductBuildVersion: 14S471a
ProductCopyright: 1983-2016 Apple Inc.
ProductName: Watch OS
ProductVersion: 3.1

Xcode 8.2
Build version 8C38
$ xctool -version
0.3.1
$ xcrun simctl list
== Device Types ==
iPhone 4s (com.apple.CoreSimulator.SimDeviceType.iPhone-4s)
iPhone 5 (com.apple.CoreSimulator.SimDeviceType.iPhone-5)
iPhone 5s (com.apple.CoreSimulator.SimDeviceType.iPhone-5s)
iPhone 6 (com.apple.CoreSimulator.SimDeviceType.iPhone-6)
iPhone 6 Plus (com.apple.CoreSimulator.SimDeviceType.iPhone-6-Plus)
iPhone 6s (com.apple.CoreSimulator.SimDeviceType.iPhone-6s)
iPhone 6s Plus (com.apple.CoreSimulator.SimDeviceType.iPhone-6s-Plus)
iPhone 7 (com.apple.CoreSimulator.SimDeviceType.iPhone-7)
iPhone 7 Plus (com.apple.CoreSimulator.SimDeviceType.iPhone-7-Plus)
iPhone SE (com.apple.CoreSimulator.SimDeviceType.iPhone-SE)
iPad 2 (com.apple.CoreSimulator.SimDeviceType.iPad-2)
iPad Retina (com.apple.CoreSimulator.SimDeviceType.iPad-Retina)
iPad Air (com.apple.CoreSimulator.SimDeviceType.iPad-Air)
iPad Air 2 (com.apple.CoreSimulator.SimDeviceType.iPad-Air-2)
iPad Pro (9.7-inch) (com.apple.CoreSimulator.SimDeviceType.iPad-Pro--9-7-inch-)
iPad Pro (12.9-inch) (com.apple.CoreSimulator.SimDeviceType.iPad-Pro)
Apple TV 1080p (com.apple.CoreSimulator.SimDeviceType.Apple-TV-1080p)
Apple Watch - 38mm (com.apple.CoreSimulator.SimDeviceType.Apple-Watch-38mm)
Apple Watch - 42mm (com.apple.CoreSimulator.SimDeviceType.Apple-Watch-42mm)
Apple Watch Series 2 - 38mm (com.apple.CoreSimulator.SimDeviceType.Apple-Watch-Series-2-38mm)
Apple Watch Series 2 - 42mm (com.apple.CoreSimulator.SimDeviceType.Apple-Watch-Series-2-42mm)
== Runtimes ==
iOS 8.1 (8.1 - 12B411) (com.apple.CoreSimulator.SimRuntime.iOS-8-1)
iOS 8.2 (8.2 - 12D508) (com.apple.CoreSimulator.SimRuntime.iOS-8-2)
iOS 8.3 (8.3 - 12F70) (com.apple.CoreSimulator.SimRuntime.iOS-8-3)
iOS 8.4 (8.4 - 12H141) (com.apple.CoreSimulator.SimRuntime.iOS-8-4)
iOS 9.0 (9.0 - 13A344) (com.apple.CoreSimulator.SimRuntime.iOS-9-0)
iOS 9.1 (9.1 - 13B143) (com.apple.CoreSimulator.SimRuntime.iOS-9-1)
iOS 9.2 (9.2 - 13C75) (com.apple.CoreSimulator.SimRuntime.iOS-9-2)
iOS 9.3 (9.3 - 13E233) (com.apple.CoreSimulator.SimRuntime.iOS-9-3)
iOS 10.0 (10.0 - 14A345) (com.apple.CoreSimulator.SimRuntime.iOS-10-0)
iOS 10.1 (10.1 - 14B72) (com.apple.CoreSimulator.SimRuntime.iOS-10-1)
iOS 10.2 (10.2 - 14C89) (com.apple.CoreSimulator.SimRuntime.iOS-10-2)
tvOS 9.0 (9.0 - 13T395) (com.apple.CoreSimulator.SimRuntime.tvOS-9-0)
tvOS 9.1 (9.1 - 13U85) (com.apple.CoreSimulator.SimRuntime.tvOS-9-1)
tvOS 9.2 (9.2 - 13Y234) (com.apple.CoreSimulator.SimRuntime.tvOS-9-2)
tvOS 10.0 (10.0 - 14T328) (com.apple.CoreSimulator.SimRuntime.tvOS-10-0)
tvOS 10.1 (10.1 - 14U591) (com.apple.CoreSimulator.SimRuntime.tvOS-10-1)
watchOS 2.0 (2.0 - 13S343) (com.apple.CoreSimulator.SimRuntime.watchOS-2-0)
watchOS 2.1 (2.1 - 13S661) (com.apple.CoreSimulator.SimRuntime.watchOS-2-1)
watchOS 2.2 (2.2 - 13V144) (com.apple.CoreSimulator.SimRuntime.watchOS-2-2)
watchOS 3.1 (3.1 - 14S471a) (com.apple.CoreSimulator.SimRuntime.watchOS-3-1)
== Devices ==
-- iOS 8.1 --
    iPhone 4s (AC3AB71C-F551-4FD0-8052-39B8CAC80D3B) (Shutdown)
    iPhone 5 (6F2BC083-C1D9-43C2-9F41-E9503A6D1921) (Shutdown)
    iPhone 5s (44C429DC-A30A-4774-826F-DB0C35D2F5A5) (Shutdown)
    iPhone 6 (C35D9EA1-67B7-4801-877C-BD3FD8C6399C) (Shutdown)
    iPhone 6 Plus (E6D792FA-9462-4F9A-8B5A-D08D23963279) (Shutdown)
    iPad 2 (8C638466-C2D8-4340-85F0-41ED767B9BEC) (Shutdown)
    iPad Retina (F5E8F4BB-28C1-49A3-A8DD-E4E23B7A16CE) (Shutdown)
    iPad Air (55DCFD12-6B10-41A4-8A23-6AC171189F00) (Shutdown)
-- iOS 8.2 --
    iPhone 4s (F6209CCE-1243-4324-890C-DC22B76B2CC9) (Shutdown)
    iPhone 5 (DD81F996-55F2-47E3-AD48-283968BA159B) (Shutdown)
    iPhone 5s (A3F50863-096B-4185-872F-99DFF0FA2928) (Shutdown)
    iPhone 6 (7C3D3BA3-2FE7-4A51-AF37-779CA81920C5) (Shutdown)
    iPhone 6 Plus (F569D573-A36A-48AC-A4F2-2EF4F52B56B5) (Shutdown)
    iPad 2 (F0970A1D-F056-414E-B482-61F078BB9E86) (Shutdown)
    iPad Retina (F93294FB-0264-4B01-9AB6-073C460C953C) (Shutdown)
    iPad Air (5CAA68DE-7CE9-4B99-A3AA-C32A8F8A230C) (Shutdown)
-- iOS 8.3 --
    iPhone 4s (321BD46A-DE3D-46F9-82A3-8AAC71A911B4) (Shutdown)
    iPhone 5 (589404DD-7204-4F73-98C3-A2FE3F330941) (Shutdown)
    iPhone 5s (65093260-E68D-4731-8B4E-BC2B9A9D6859) (Shutdown)
    iPhone 6 (B2F45F65-C893-4B37-B1EA-BEF17F849856) (Shutdown)
    iPhone 6 Plus (E3E764DF-0DF1-4F5A-8EA4-D77836DD373B) (Shutdown)
    iPad 2 (1F5F0CCA-52D5-4A7C-BA31-AB6EDD451691) (Shutdown)
    iPad Retina (E191B1FB-22B9-4846-B93F-8E15B5F45D5B) (Shutdown)
    iPad Air (C8D74377-B287-4071-A9DE-63A7EA31C32A) (Shutdown)
-- iOS 8.4 --
    iPhone 4s (1053E19B-A1C6-45F8-B819-C9281ABFBC2C) (Shutdown)
    iPhone 5 (99DB1061-BE8A-410C-A5E3-3512EFA61BD3) (Shutdown)
    iPhone 5s (7DB8B443-C0B5-4D6F-977E-79F09228428F) (Shutdown)
    iPhone 6 (3907EC2E-F6D7-4D05-A226-25056C2C4683) (Shutdown)
    iPhone 6 Plus (272FCA2E-F650-4832-92D6-08C4656A9C28) (Shutdown)
    iPad 2 (A097E532-F57E-4AA2-96A0-8A7C344BAD5C) (Shutdown)
    iPad Retina (392F247C-ADE3-46B4-9262-03432A84F096) (Shutdown)
    iPad Air (1B5583B0-E810-416A-8A81-DBEABE56A35D) (Shutdown)
-- iOS 9.0 --
    iPhone 4s (0886D36F-72FB-42F6-8007-8FE409EE35E6) (Shutdown)
    iPhone 5 (6F97FC08-BAAD-42E6-930E-49A16EAE38B4) (Shutdown)
    iPhone 5s (32230199-DB64-4B0F-B9E1-0009C533C98C) (Shutdown)
    iPhone 6 (0324A2A6-D186-48C1-907C-0A3CA7BD781A) (Shutdown)
    iPhone 6 Plus (233D7D7D-C18D-41BA-9A65-58D4FDD7CB8A) (Shutdown)
    iPhone 6s (892621FB-1543-48E0-9B99-70898361EAD5) (Shutdown)
    iPhone 6s Plus (F463B12B-7A60-47C0-AFF7-FF8CA92E1A2F) (Shutdown)
    iPad 2 (536D9B5B-E856-40BE-BBB1-B8312F352C36) (Shutdown)
    iPad Retina (01A64601-24F9-4AE3-A3C0-CE285B6CC4AB) (Shutdown)
    iPad Air (D93933F2-C71D-4B89-9ACA-1613AD71B396) (Shutdown)
    iPad Air 2 (596BB493-70CD-467E-AA17-4DBCE92EBD71) (Shutdown)
-- iOS 9.1 --
    iPhone 4s (E3F218DB-AD9F-4C1A-85A0-37EC1BE30B77) (Shutdown)
    iPhone 5 (E223D562-1EA7-44AD-A54B-32EE1169C796) (Shutdown)
    iPhone 5s (8BFBEE7B-1A54-4FAD-944A-06D9F64EF8B9) (Shutdown)
    iPhone 6 (DF696861-44B7-4CE0-A7D9-E58A97768628) (Shutdown)
    iPhone 6 Plus (F3E0CA22-B251-4D65-A597-9E19D39C6533) (Shutdown)
    iPhone 6s (76B1028E-02A5-4C77-973C-B12DB7D9DE7B) (Shutdown)
    iPhone 6s Plus (CDAC6786-0736-4F64-BBEB-9476475C9E75) (Shutdown)
    iPad 2 (00484212-35D5-417B-B0D1-9DC621EF59FC) (Shutdown)
    iPad Retina (75E517F9-49D5-4A6A-AF3A-EE09605DDCDC) (Shutdown)
    iPad Air (8A5BFD2B-151D-415E-9E03-4419FBE9DAC8) (Shutdown)
    iPad Air 2 (3CF52C84-73B2-4694-BF08-41F29AF8DB4F) (Shutdown)
    iPad Pro (8C2615FE-96DD-4A9E-AC89-BEF41DD4E2A3) (Shutdown)
-- iOS 9.2 --
    iPhone 4s (A232CAD4-B916-42CF-9A78-7A537CD63FF0) (Shutdown)
    iPhone 5 (EAC20281-4473-4F1C-8639-DD3364303FE9) (Shutdown)
    iPhone 5s (8FF1300E-C713-4091-893A-D4F3CBF53CE7) (Shutdown)
    iPhone 6 (25E9BB3E-E416-49F1-88F6-F1CE3C2AD380) (Shutdown)
    iPhone 6 Plus (3E6FA9F8-51CA-4507-94AD-4E4ABE709474) (Shutdown)
    iPhone 6s (F0B62C6E-FE28-4AD9-9588-619037ECC349) (Shutdown)
    iPhone 6s Plus (0D026736-2FF4-4D56-A7A8-CA4EB43AFCFC) (Shutdown)
    iPad 2 (BCC6EDC9-6CC0-49F3-8D58-2864FE2BC058) (Shutdown)
    iPad Retina (B8D45FD6-2968-40A3-BF48-A9AECFBE9BB1) (Shutdown)
    iPad Air (AA94CA5F-B388-453E-AC1F-7ED1B176C534) (Shutdown)
    iPad Air 2 (25AF43E4-1138-49AC-BF8B-03257A3A21F2) (Shutdown)
    iPad Pro (0161F7E9-2B33-46CB-A5C9-509CF156DC01) (Shutdown)
-- iOS 9.3 --
    iPhone 4s (EDBD1320-3ACF-488A-ADD9-034B65ECE1D2) (Shutdown)
    iPhone 5 (C0004C95-78E1-4A3F-B1E6-380DA60AFB35) (Shutdown)
    iPhone 5s (E239A990-0219-4456-8180-4FE5ED0B39E8) (Shutdown)
    iPhone 6 (808A0798-21A1-4579-B15E-DA3CC5782582) (Shutdown)
    iPhone 6 Plus (9D1EC03F-C9CC-46AC-9575-7EB6714E176B) (Shutdown)
    iPhone 6s (3A559597-4B66-46A6-9B79-0D29EDEC8548) (Shutdown)
    iPhone 6s Plus (132FBB24-912B-416D-9E15-17B44D4D1BA6) (Shutdown)
    iPad 2 (5E55D50C-32B1-48A1-A244-C66B436180B3) (Shutdown)
    iPad Retina (9B22D995-267E-4FB4-8C9F-7BE92FB336EB) (Shutdown)
    iPad Air (98BC31B8-29FC-414A-AB51-3829D1BE1C07) (Shutdown)
    iPad Air 2 (D2685C2E-C298-4FA0-A42B-6624B447C227) (Shutdown)
    iPad Pro (6EB0D072-6317-443D-AAE2-4A965723BA88) (Shutdown)
-- iOS 10.0 --
    iPhone 5 (C6F7DEAE-2901-40C5-9D6F-1B408BB4960E) (Shutdown)
    iPhone 5s (6B841AF0-3FE6-4B33-B022-D5887643B791) (Shutdown)
    iPhone 6 (655E6800-2BE5-4706-AB65-92B50F99A2EF) (Shutdown)
    iPhone 6 Plus (264697C1-E4EB-4985-AB30-A9B90E117F84) (Shutdown)
    iPhone 6s (74EAD8ED-9246-4F49-B02B-BBE2B0EBB8A4) (Shutdown)
    iPhone 6s Plus (DB4D64F5-216F-4AAB-9933-969E4FF1B827) (Shutdown)
    iPhone SE (4C741B6B-7647-4DD6-84A0-A71F44552573) (Shutdown)
    iPad Retina (8EF5A478-A243-4986-9F82-B709795478A4) (Shutdown)
    iPad Air (C650BF69-EEC3-487C-BCCA-463CB74F9718) (Shutdown)
    iPad Air 2 (900EA122-D2E1-48E0-A966-312C7953B065) (Shutdown)
    iPad Pro (9.7 inch) (B2F00ECB-ED23-44B0-8461-B8371827727B) (Shutdown)
    iPad Pro (12.9 inch) (CA3CC9FA-151D-4D1E-9958-6DC7E96854F0) (Shutdown)
-- iOS 10.1 --
    iPhone 5 (8B338331-D9E1-475A-8EC8-C8E34CACE061) (Shutdown)
    iPhone 5s (5F87C288-0141-4755-84DF-498E91D720E1) (Shutdown)
    iPhone 6 (3B5E817B-744D-4086-AAB0-55CB35A17717) (Shutdown)
    iPhone 6 Plus (53AC5D81-1B58-48DD-89CB-B90F2E744692) (Shutdown)
    iPhone 6s (0D86C5D8-FFE3-4FAA-8FCA-1AE0C5DF7AB8) (Shutdown)
    iPhone 6s Plus (748984E8-36FD-4AA9-BF13-CD6C0BCE2868) (Shutdown)
    iPhone 7 (E35A39A9-0197-4428-A846-D75DDE6F0E98) (Shutdown)
    iPhone 7 Plus (9464677E-9962-4C3B-91E8-C969B6337A68) (Shutdown)
    iPhone SE (8F22171A-FD13-45C9-A45B-68529E1385BD) (Shutdown)
    iPad Retina (A6CCC288-9B2A-4A96-87A1-EE44C037CBA2) (Shutdown)
    iPad Air (3984C553-D193-45BF-85B9-6EB98F51CBB1) (Shutdown)
    iPad Air 2 (46BA2896-3D27-4F16-A0B3-3A9D8800546D) (Shutdown)
    iPad Pro (9.7 inch) (4EEA61AA-7619-4E70-8399-7BD7DB762B4D) (Shutdown)
    iPad Pro (12.9 inch) (E6F3E94D-818C-4211-9D4B-F23493AA3D22) (Shutdown)
-- iOS 10.2 --
    iPhone 5 (D0257C83-DB81-4567-93EC-4C6DF23DC24C) (Shutdown)
    iPhone 5 (5555EE5F-D4E7-4997-8EEA-41A93B41F3AF) (Shutdown)
    iPhone 5s (79C525D3-2383-4201-AC3A-81810F9F4E03) (Shutdown)
    iPhone 5s (2AAA645C-1882-4F81-B866-6241B900C185) (Shutdown)
    iPhone 6 (AD8E8C76-910E-437D-88C2-4D6F6EBE3355) (Shutdown)
    iPhone 6 (1FD54EA7-5A25-4D6F-8599-D6F7687DA4EE) (Shutdown)
    iPhone 6 Plus (540CDF74-5FF3-488E-8AEB-79D16AB7517D) (Shutdown)
    iPhone 6 Plus (EB1167CF-3545-44BC-9D95-482D286F6C66) (Shutdown)
    iPhone 6s (BE8E0914-5B5F-45C2-8C99-879894AF72B0) (Shutdown)
    iPhone 6s (31E6604A-19AA-4B68-B560-C33C584BC80D) (Shutdown)
    iPhone 6s Plus (CFD2ED5A-CDA8-4177-BEF8-08B0E3DBF8B1) (Shutdown)
    iPhone 6s Plus (CE9C5FE6-C6EC-4EC0-AB36-1BB063E8C4AD) (Shutdown)
    iPhone 7 (E40727B3-41FB-4D6E-B4CB-BFA87109EB12) (Shutdown)
    iPhone 7 (22FA2149-1241-469C-BF6D-462D3837DB72) (Shutdown)
    iPhone 7 Plus (8188B40E-F57F-4519-AC47-E43D884B9016) (Shutdown)
    iPhone 7 Plus (7B6F8C6B-B67A-4F64-BB70-AE1FF077ACC2) (Shutdown)
    iPhone SE (DB794781-65A7-4884-8D00-AAC3CBD39A44) (Shutdown)
    iPhone SE (63A0BA5F-3911-496F-BF2E-512830B4AD7F) (Shutdown)
    iPad Retina (F7F55A8E-B941-425C-879E-A043FD99B5F1) (Shutdown)
    iPad Air (1E01E5B5-0D10-4259-A0C9-85BF8FDD5D23) (Shutdown)
    iPad Air 2 (FFD505F4-2E1D-4BD8-9975-870CF411DDFC) (Shutdown)
    iPad Pro (9.7 inch) (708F16B6-193F-4FC3-B620-2EE3B9FD6C0D) (Shutdown)
    iPad Pro (12.9 inch) (7AB0B6C6-1A12-4608-AF63-538784CA0F3F) (Shutdown)
-- tvOS 9.0 --
    Apple TV 1080p (BD4A3F2E-30B7-469E-8F91-22D334A6CE48) (Shutdown)
-- tvOS 9.1 --
    Apple TV 1080p (3ADB51D9-59BF-44B6-88B8-C0A9064B9DE2) (Shutdown)
-- tvOS 9.2 --
    Apple TV 1080p (0B5AA3F5-4756-4636-A617-B5154489F901) (Shutdown)
-- tvOS 10.0 --
    Apple TV 1080p (E211A072-9222-47AE-BE2B-3182DAE62214) (Shutdown)
-- tvOS 10.1 --
    Apple TV 1080p (5761D8AB-2838-4681-A528-D0949FF240C5) (Shutdown)
-- watchOS 2.0 --
    Apple Watch - 38mm (F9045327-3FCE-4BB8-9AE4-58F27F73A222) (Shutdown)
    Apple Watch - 42mm (779E935B-41F4-4F7E-8E4C-C3DF310DAD9F) (Shutdown)
-- watchOS 2.1 --
    Apple Watch - 38mm (A126182B-3CE7-4607-B309-E4CF9F41E3E3) (Shutdown)
    Apple Watch - 42mm (CC955A99-FA0C-448A-A64A-241CB53DC31F) (Shutdown)
-- watchOS 2.2 --
    Apple Watch - 38mm (81633E96-10D4-4B56-A3C5-2F85C8E35234) (Shutdown)
    Apple Watch - 42mm (E303E53F-0E83-4D86-A1B0-C228D72AADF7) (Shutdown)
-- watchOS 3.1 --
    Apple Watch - 38mm (128F0B76-67BC-449D-8A46-5A6940CB0A20) (Shutdown)
    Apple Watch - 42mm (F19F5D51-F6B9-4DF4-83D1-1935E68DB9A1) (Shutdown)
    Apple Watch Series 2 - 38mm (F4060CB8-396F-4203-A324-BF682603FCBA) (Shutdown)
    Apple Watch Series 2 - 42mm (33A10678-30FB-42B2-BC4B-744D7279A0FC) (Shutdown)
== Device Pairs ==
430ABBAD-8F2E-4B78-AAD4-ADE37C30859E (active, disconnected)
    Watch: Apple Watch Series 2 - 38mm (F4060CB8-396F-4203-A324-BF682603FCBA) (Shutdown)
    Phone: iPhone 7 (22FA2149-1241-469C-BF6D-462D3837DB72) (Shutdown)
189F805F-D994-4FE2-9708-4F2C1E68C178 (active, disconnected)
    Watch: Apple Watch Series 2 - 42mm (33A10678-30FB-42B2-BC4B-744D7279A0FC) (Shutdown)
    Phone: iPhone 7 Plus (8188B40E-F57F-4519-AC47-E43D884B9016) (Shutdown)
$ gem update --system
Updating rubygems-update
Fetching: rubygems-update-2.6.10.gem (100%)
Successfully installed rubygems-update-2.6.10
Installing RubyGems 2.6.10
RubyGems 2.6.10 installed

=== 2.6.10 / 2017-01-23

Bug fixes:

* Fix `require` calling the wrong `gem` method when it is overridden.
  Pull request #1822 by Samuel Giddins.

=== 2.6.9 / 2017-01-20

Bug fixes:

* Allow initializing versions with empty strings. Pull request #1767 by
  Luis Sagastume.
* Fix TypeError on 2.4. Pull request #1788 by Nobuyoshi Nakada.
* Don't output mkmf.log message if compilation didn't fail. Pull request
  #1808 by Jeremy Evans.
* Fixed broken links and overzealous URL encoding in gem server. Pull
  request #1809 by Nicole Orchard.
* Update vendored Molinillo to 0.5.5. Pull request #1812 by Samuel
  Giddins.
* RakeBuilder: avoid frozen string issue. Pull request #1819 by Olle
  Jonsson.

=== 2.6.8 / 2016-10-29

Bug fixes:

* Improve SSL verification failure message. Pull request #1751
  by Eric Hodel.
* Ensure `to_spec` falls back on prerelease specs. Pull request
  #1755 by André Arko.
* Update vendored Molinillo to 0.5.3. Pull request #1763 by
  Samuel Giddins.

=== 2.6.7 / 2016-09-26

Bug fixes:

* Install native extensions in the correct location when using the
  `--user-install` flag. Pull request #1683 by Noah Kantrowitz.
* When calling `Gem.sources`, load sources from `configuration`
  if present, else use the default sources. Pull request #1699
  by Luis Sagastume.
* Fail gracefully when attempting to redirect without a Location.
  Pull request #1711 by Samuel Giddins.
* Update vendored Molinillo to 0.5.1. Pull request #1714 by
  Samuel Giddins.

=== 2.6.6 / 2016-06-22

Bug fixes:

* Sort installed versions to make sure we install the latest version when
  running `gem update --system`. As a one-time fix, run
  `gem update --system=2.6.6`. Pull request #1601 by David Radcliffe.

=== 2.6.5 / 2016-06-21

Minor enhancements:

* Support for unified Integer in Ruby 2.4. Pull request #1618
  by SHIBATA Hiroshi.
* Update vendored Molinillo to 0.5.0 for performance improvements.
  Pull request #1638 by Samuel Giddins.

Bug fixes:

* Raise an explicit error if Signer#sign is called with no certs. Pull
  request #1605 by Daniel Berger.
* Update `update_bundled_ca_certificates` utility script for directory
  nesting. Pull request #1583 by James Wen.
* Fix broken symlink support in tar writer (+ fix broken test). Pull
  request #1578 by Cezary Baginski.
* Remove extension directory before (re-)installing. Pull request #1576
  by Jeremy Hinegardner.
* Regenerate test CA certificates with appropriate extensions. Pull
  request #1611 by rhenium.
* Rubygems does not terminate on failed file lock when not superuser. Pull
  request #1582 by Ellen Marie Dash.
* Fix tar headers with a 101 character name. Pull request #1612 by Paweł
  Tomulik.
* Add Gem.platform_defaults to allow implementations to override defaults.
  Pull request #1644 by Charles Oliver Nutter.
* Run Bundler tests on TravisCI. Pull request #1650 by Samuel Giddins.



Minor enhancements:

* Use Gem::Util::NULL_DEVICE instead of hard coded strings. Pull request #1588
  by Chris Charabaruk.
* Use File.symlink on MS Windows if supported. Pull request #1418
  by Nobuyoshi Nakada.

Bug fixes:

* Redact uri password from error output when gem fetch fails. Pull request
  #1565 by Brian Fletcher.
* Suppress warnings. Pull request #1594 by Nobuyoshi Nakada.
* Escape user-supplied content served on web pages by `gem server` to avoid
  potential XSS vulnerabilities. Samuel Giddins.

=== 2.6.3 / 2016-04-05

Minor enhancements:

* Lazily calculate Gem::LoadError exception messages. Pull request #1550
  by Aaron Patterson.
* New fastly cert. Pull request #1548 by David Radcliffe.
* Organize and cleanup SSL certs. Pull request #1555 by James Wen.
* [RubyGems] Make deprecation message for paths= more helpful. Pull
  request #1562 by Samuel Giddins.
* Show default gems when using "gem list". Pull request #1570 by Luis
  Sagastume.

Bug fixes:

* Stub ordering should be consistent regardless of how cache is populated.
  Pull request #1552 by Aaron Patterson.
* Handle cases when the @@stubs variable contains non-stubs. Pull request
  #1558 by Per Lundberg.
* Fix test on Windows for inconsistent temp path. Pull request #1554 by
  Hiroshi Shirosaki.
* Fix `Gem.find_spec_for_exe` picks oldest gem. Pull request #1566 by
  Shinichi Maeshima.
* [Owner] Fallback to email and userid when owner email is missing. Pull
  request #1569 by Samuel Giddins.
* [Installer] Handle nil existing executable. Pull request #1561 by Samuel
  Giddins.
* Allow two digit version numbers in the tests. Pull request #1575 by unak.

=== 2.6.2 / 2016-03-12

Bug fixes:

* Fix wrong version of gem activation for bin stub. Pull request #1527 by
  Aaron Patterson.
* Speed up gem activation failures. Pull request #1539 by Aaron Patterson.
* Fix platform sorting in the resolver. Pull request #1542 by Samuel E.
  Giddins.
* Ensure we unlock the monitor even if try_activate throws. Pull request
  #1538 by Charles Oliver Nutter.


=== 2.6.1 / 2016-02-28

Bug fixes:

* Ensure `default_path` and `home` are set for paths. Pull request #1513
  by Aaron Patterson.
* Restore but deprecate support for Array values on `Gem.paths=`. Pull
  request #1514 by Aaron Patterson.
* Fix invalid gem file preventing gem install from working. Pull request
  #1499 by Luis Sagastume.

=== 2.6.0 / 2016-02-26

Minor enhancements:

* RubyGems now defaults the `gem push` to the gem's "allowed_push_host"
  metadata setting.  Pull request #1486 by Josh Lane.
* Update bundled Molinillo to 0.4.3. Pull request #1493 by Samuel E. Giddins.
* Add version option to gem open command. Pull request #1483 by Hrvoje
  Šimić.
* Feature/add silent flag. Pull request #1455 by Luis Sagastume.
* Allow specifying gem requirements via env variables. Pull request #1472
  by Samuel E. Giddins.

Bug fixes:

* RubyGems now stores `gem push` credentials under the host you signed-in for.
  Pull request #1485 by Josh Lane.
* Move `coding` location to first line. Pull request #1471 by SHIBATA
  Hiroshi.
* [PathSupport] Handle a regexp path separator. Pull request #1469 by
  Samuel E. Giddins.
* Clean up the PathSupport object. Pull request #1094 by Aaron Patterson.
* Join with File::PATH_SEPARATOR in Gem.use_paths. Pull request #1476 by
  Samuel E. Giddins.
* Handle when the gem home and gem path arent set in the config file. Pull
  request #1478 by Samuel E. Giddins.
* Terminate TimeoutHandler. Pull request #1479 by Nobuyoshi Nakada.
* Remove redundant cache. Pull request #1482 by Eileen M. Uchitelle.
* Freeze `Gem::Version@segments` instance variable. Pull request #1487 by
  Ben Dean.
* Gem cleanup is trying to uninstall gems outside GEM_HOME and reporting
  an error after it tries. Pull request #1353 by Luis Sagastume.
* Avoid duplicated sources. Pull request #1489 by Luis Sagastume.
* Better description for quiet flag. Pull request #1491 by Luis Sagastume.
* Raise error if find_by_name returns with nil. Pull request #1494 by
  Zoltán Hegedüs.
* Find_files only from loaded_gems when using gemdeps. Pull request #1277
  by Michal Papis.

=== 2.5.2 / 2016-01-31

Bug fixes:

* Fix memoization of Gem::Version#prerelease? Pull request #1125 by Matijs van
  Zuijlen.
* Handle trailing colons in GEM_PATH, by Damien Robert.
* Improve the Gemfile `gemspec` method, fixing #1204 and #1033. Pull request
  #1276 by Michael Papis.
* Warn only once when a gemspec license is invalid. Pull request #1414 by Samuel
  E. Giddins.
* Check for exact constants before using them, fixing Ruby bug #11940. Pull
  request #1438 by Nobuyoshi Nakada.
* Fix building C extensions on Ruby 1.9.x on Windows. Pull request #1453 by Marie
  Markwell.
* Handle symlinks containing ".." correctly. Pull request #1457 by Samuel E.
  Giddins.

Minor enhancements:

* Add `--no-rc` flag, which skips loading `.gemrc`. Pull request #1329 by Luis
  Sagastume.
* Allow basic auth to be excluded from `allowed_push_host`. By Josh Lane.
* Add `gem list --exact`, which finds gems by string match instead of regex. Pull
  request #1344 by Luis Sagastume.
* Suggest alternatives when gem license is unknown. Pull request #1443 by Samuel
  E. Giddins.
* Print a useful error if a binstub expects a newer version of a gem than is
  installed. Pull request #1407 by Samuel E. Giddins.
* Allow the (supported) s3:// scheme to be used with `--source`. Pull request
  #1416 by Dave Adams.
* Add `--[no-]post-install-message` to `install` and `update`. Pull request #1162
  by Josef Šimánek.
* Add `--host` option to `yank`, providing symmetry with `pull`. Pull request
  #1361 by Mike Virata-Stone.
* Update bundled Molinillo to 0.4.1. Pull request #1452 by Samuel E. Giddins.
* Allow calling `build` without '.gemspec'. Pull request #1454 by Stephen
  Blackstone.
* Add support for `source` option on gems in Gemfile. Pull request #1355 by
  Michael Papis.
* Function correctly when string literals are frozen on Ruby 2.3. Pull request
  #1408 by Samuel E. Giddins.

=== 2.5.1 / 2015-12-10

Bug fixes:

* Ensure platform sorting only uses strings. Affected binary installs on Windows.
  Issue #1369 reported by Ryan Atball (among others).
  Pull request #1375 by Samuel E. Giddins.
* Revert PR #1332. Unable to reproduce, and nil should be impossible.
* Gem::Specification#to_fullpath now returns .rb extensions when such a file
  exists.  Pull request #1114 by y-yagi.
* RubyGems now handles Net::HTTPFatalError instead of crashing.  Pull
  request #1314 by Samuel E. Giddins.
* Updated bundled Molinillo to 0.4.0.  Pull request #1322, #1396 by Samuel E.
  Giddins.
* Improved performance of spec loading by reducing likelihood of loading the
  complete specification.  Pull request #1373 by Aaron Patterson.
* Improved caching of requirable files  Pull request #1377 by Aaron Patterson.
* Fixed activation of gems with development dependencies.  Pull request #1388
  by Samuel E. Giddins.
* RubyGems now uses the same Molinillo vendoring strategy as Bundler.  Pull
  request #1397 by Samuel E. Giddins.
* Fixed documentation of Gem::Requirement.parse.  Pull request #1398 by
  Juanito Fatas.
* RubyGems no longer warns when a prerelease gem has prerelease dependencies.
  Pull request #1399 by Samuel E. Giddins.
* Fixed Gem::Version documentation example.  Pull request #1401 by Guilherme
  Goettems Schneider.
* Updated documentation links to https://.  Pull request #1404 by Suriyaa
  Kudo.
* Fixed double word typo.  Pull request #1411 by Jake Worth.

=== 2.5.0 / 2015-11-03

Major enhancements:

* Added the Gem::Licenses class which provides a set of standard license
  identifiers as set by spdx.org. This is now used by the
  Gem::Specification#license attribute to try to standardize (though not
  enforce) licenses set by gem authors.

  Pull request #1249 by Kyle Mitchell.

Minor enhancements:

* Use Molinillo as the resolver library.  This is the same resolver as used by
  Bundler.  Pull request #1189 by Samuel E. Giddins.
* Add `--skip=gem_name` to Pristine command.  Pull request #1018 by windwiny.
* The parsed gem dependencies file is now available via Gem.gemdeps following
  Gem.use_gemdeps.  Pull request #1224 by Hsing-Hui Hsu, issue #1213 by
  Michal Papis.
* Moved description attribute to recommended for Gem::Specification.
  Pull request #1046 by Michal Papis
* Moved `Gem::Indexer#abbreviate` and `#sanitize` to `Gem::Specification`.
  Pull request #1145 by Arthur Nogueira Neves
* Cache Gem::Version segments for `#bump` and `#release`.
  Pull request #1131 by Matijs van Zuijlen
* Fix edge case in `levenshtein_distance` for comparing longer strings.
  Pull request #1173 by Richard Schneeman
* Remove duplication from List#to_a, improving from O(n^2) to O(n) time.
  Pull request #1200 by Marc Siegel.
* Gem::Specification.add_specs is deprecated and will be removed from version
  3.0 with no replacement.  To add specs, install the gem, then reset the
  cache.
* Gem::Specification.add_spec is deprecated and will be removed from version
  3.0 with no replacement.  To add specs, install the gem, then reset the
  cache.
* Gem::Specification.remove_spec is deprecated and will be removed from version
  3.0 with no replacement.  To remove specs, uninstall the gem, then reset the
  cache by calling Gem::Specification.reset.
* Call Array#compact before calling Array#uniq for minor speed improvement in
  the Gem::Specification#files method.
  Pull request #1253 by Marat Amerov.
* Use stringio instead of custom String classes.
  Pull request #1250 by Petr Skocik.
* Use URI#host instead of URI#hostname to retain backwards compatibility with
  Ruby 1.9.2 and earlier in util library.
  Pull request #1288 by Joe Rafaniello.
* Documentation update for gem sources.
  Pull request #1324 by Ilya Vassilevsky.
* Documentation update for required_ruby_version.
  Pull request #1321 by Matt Patterson.
* Documentation update for gem update.
  Pull request #1306 by Tim Blair.
* Emit a warning on SRV resolve failure.
  Pull request #1023 by Ivan Kuchin.
* Allow duplicate dependencies between runtime and development.
  Pull request #1032 by Murray Steele.
* The gem env command now shows the user installation directory.
  Pull request #1343 by Luis Sagastume.
* The Gem::Platform#=== method now treats a nil cpu arch the same as 'universal'.
  Pull request #1356 by Daniel Berger.
* Improved memory performance in Gem::Specification.traverse.  Pull request
  #1188 by Aaron Patterson.
* RubyGems packages now support symlinks.  Pull request #1209 by Samuel E.
  Giddins.
* RubyGems no longer outputs mkmf.log if it does not exist.  Pull request
  #1222 by Andrew Hooker.
* Added Bitrig platform.  Pull request #1233 by John C. Vernaleo.
* Improved error message for first-time RubyGems developers.  Pull request
  #1241 by André Arko
* Improved performance of Gem::Specification#load with cached specs.  Pull
  request #1297 by Samuel E. Giddins.
* Gem::RemoteFetcher allows users to set HTTP headers.  Pull request #1363 by
  Agis Anastasopoulos.

Bug fixes:

* Fixed Rake homepage url in example for Gem::Specification#homepage.
  Pull request #1171 by Arthur Nogueira Neves
* Don't crash if partially uninstalled gem can't be found.
  Pull request #1283 by Cezary Baginski.
* Test warning cleanup.
  Pull request #1298 by Samuel E. Giddins.
* Documentation fix for GemDependencyAPI.
  Pull request #1308 by Michael Papis.
* Fetcher now ignores ENOLCK errors in single threaded environments. This
  handles an issue with gem installation on NFS as best we can. Addresses
  issue #1176 by Ryan Moore.
  Pull request #1327 by Daniel Berger.
* Fix some path quoting issues in the test suite.
  Pull request #1328 by Gavin Miller.
* Fix NoMethodError in running ruby processes when gems are uninstalled.
  Pull request #1332 by Peter Drake.
* Fixed a potential NoMethodError for gem cleanup.
  Pull request #1333 by Peter Drake.
* Fixed gem help bug.
  Issue #1352 reported by bogem, pull request #1357 by Luis Sagastume.

  Nobuyoshi Nokada.
* Update links in RubyGems documentation.  Pull request #1185 by Darío Hereñú.
* Prerelease gem executables can now be run.  Pull request #1186 by Samuel E.
  Giddins.
* Updated RubyGems travis-ci ruby versions.  Pull request #1187 by Samuel E.
  Giddins.
* Fixed release date of RubyGems 2.4.6.  Pull request #1190 by Frieder
  Bluemle.
* Fixed bugs in gem activation.  Pull request #1202 by Miklós Fazekas.
* Fixed documentation for `gem list`.  Pull request #1228 by Godfrey Chan.
* Fixed #1200 history entry.  Pull request #1234 by Marc Siegel.
* Fixed synchronization issue when resetting the Gem::Specification gem list.
  Pull request #1239 by Samuel E. Giddins.
* Fixed running tests in parallel.  Pull request #1257 by SHIBATA Hiroshi.
* Fixed running tests with `--program-prefix` or `--program-suffix` for ruby.
  Pull request #1258 by Shane Gibbs.
* Fixed Gem::Specification#to_yaml.  Pull request #1262 by Hiroaki Izu.
* Fixed taintedness of Gem::Specification#raw_require_paths.  Pull request
  #1268 by Sam Ruby.
* Fixed sorting of platforms when installing gems.  Pull request #1271 by
  nonsequitur.
* Use `--no-document` over deprecated documentation options when installing
  dependencies on travis.  Pull request #1272 by takiy33.
* Improved support for IPv6 addresses in URIs.  Pull request #1275 by Joe
  Rafaniello.
* Spec validation no longer crashes if a file does not exist.  Pull request
  #1278 by Samuel E. Giddins.
* Gems can now be installed within `rescue`.  Pull request #1282 by Samuel E.
  Giddins.
* Increased Diffie-Hellman key size for tests for modern OpenSSL.  Pull
  request #1290 by Vít Ondruch.
* RubyGems handles invalid config files better.  Pull request #1367 by Agis
  Anastasopoulos.

=== 2.4.8 / 2015-06-08

Bug fixes:

* Tightened API endpoint checks for CVE-2015-3900


------------------------------------------------------------------------------

RubyGems installed the following executables:
    /Users/travis/.rvm/rubies/ruby-2.0.0-p648/bin/gem

RubyGems system software updated

$ gem install fastlane --no-rdoc --no-ri --no-document --quiet
Successfully installed tty-screen-0.5.0
Successfully installed fastlane-2.18.1
2 gems installed

$ true

$ fastlane --version
fastlane installation at path:
/Users/travis/.rvm/gems/ruby-2.0.0-p648/gems/fastlane-2.18.1/bin/fastlane
-----------------------------
fastlane 2.18.1


The command "fastlane --version" exited with 0.
$ gem update fastlane
Updating installed gems
Nothing to update

Warning, new version of rvm available '1.29.1', you are using older version '1.27.0'.
You can disable this warning with:    echo rvm_autoupdate_flag=0 >> ~/.rvmrc
You can enable  auto-update  with:    echo rvm_autoupdate_flag=2 >> ~/.rvmrc
Fetching: dpl-1.8.31.gem (100%)
Successfully installed dpl-1.8.31
1 gem installed

Installing deploy dependencies

!!! Script support is experimental !!!


Preparing deploy

Deploying application
fastlane 1.111.0

#######################################################################
# fastlane 2.18.1 is available. You are on 1.111.0.
# It is recommended to use the latest version.
# Please update using `sudo gem update fastlane`.
#######################################################################

2.18.1 Hotfix for git_branch action
* Fix git-branch crash if no ENV vars present (#8321)

2.18.0 Deliver improvements and CommanderGenerator refactors




















    * gym (#8273)

2.17.1 Hotfix for match nuke
* [spaceship] provisioning_profile.expires supposedly returns a Time, not a string (fixes #8266) (#8270)
* Refactor frameit CommanderGenerator usage (#8254)

To see all new releases, open https://github.com/fastlane/fastlane/releases

Please update using `sudo gem update fastlane`



Done. Your build exited with 0.
/Users/travis/build.sh: line 155: shell_session_update: command not found
```
