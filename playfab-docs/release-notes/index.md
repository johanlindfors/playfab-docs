---
title: PlayFab Release Notes 2018
author: v-thopra
description: PlayFab Release Notes for 2018.
ms.author: v-thopra
ms.date: 07/12/2018
ms.topic: article
ms.prod: playfab
keywords: playfab, development, release, apis, features
ms.localizationpriority: medium
---

# PlayFab Release Notes 2018

## 181218

Date: 2018-12-18

**[XPlatCppSdk](https://github.com/PlayFab/XPlatCppSdk) Specific Changes:**

* **SDK Breaking Change** : Updated the folder structure for the XPlatCppSdk repo. If you are using the SDK with project references, an update to vcxproj files path would be required.
* Adding Xbox support to the XPlatCppSdk. Refer to the [C++ quickstart for Xbox](../sdks/xplatcpp/quickstart-xbox.md).
* **New API**
 * Added PlayFabEventApi to support Heavyweight (low throughput) and Lightweight (high throughput) custom events.


 **[UnrealMarketplacePlugin](https://github.com/PlayFab/UnrealMarketplacePlugin) Specific Changes:**

 * Adding support for Unreal Engine 4.21

## 181204

Date: 2018-12-04

**[XPlatCppSdk](https://github.com/PlayFab/XPlatCppSdk) Specific Changes:**

* Added support to build external dependencies.
* Updated nuget composition. This is not a breaking change. Added binaries for the external dependencies to the nuget and updated the properties sheet.
* Bug fixes for QoSAPI.

**[CSharpSDK](https://github.com/PlayFab/CSharpSDK) Specific Changes:**

* Added .NET Standard 1.1/2.0 (plus .Net Core) support.
* Updated nuget composition. The package now contains binaries for .Net Standard 1.1/2.0 and portables also.
* Migrated VS project files to VS 2017 standard.

**[UnitySDK](https://github.com/PlayFab/UnitySdk) Specific Changes:**

* **SDK Breaking Change**: The SimpleGet success callback signature has changed, and now must accept a new single parameter of a byte[]
* Added SimplePost.

## 181105

Date: 2018-11-05

**API Changes:**

* PlayFab now supports login and account-linking with OpenID
* Additional XboxLive ID support, and enabling Xbox login via server

In preparation for wider release of the service, we are rolling out PlayFab Multiplayer Servers 2.0 APIs. See [PlayFab Multiplayer Servers 2.0 (Thunderhead)](../features/multiplayer/servers/thunderhead.md) for more information

## 181001

Date: 2018-10-01

**API Changes:**

* A variety of deprecations have taken effect, and those elements have been removed from SDKs and documentation
    * Some Admin API methods related to unreleased features have been hidden
    * server.DeleteUsers deprecation has taken effect
    * A field deprecation for "ServerHostname", spread across a variety of matchmaking related calls in admin, client, matchmaker, and server APIs has taken effect. "ServerIPV4Address" is the replacement.

**UnitySdk Changes:**

* Minor fixes/improvements to ScreenTime analytics

**All SDKs:**

* The automated-build branch structure for GitHub repos is changing
    * The normal customer facing branches, "versioned" and "master" will be unchanged

## 180924

Date: 2018-09-24

**API Changes:**

* Adding Metadata to the [DeleteMasterPlayerAccountRequest](xref:titleid.playfabapi.com.admin.accountmanagement.deletemasterplayeraccount#deletemasterplayeraccountrequest) Model
* Bug fixes in the Unreal Marketplace Plugin to expand supported versions

## 180917  

Date: 2018-09-17

**API Changes:**

* The Server API method **DeleteUsers** is deprecated and replaced with [DeletePlayer](xref:titleid.playfabapi.com.server.accountmanagement.deleteplayer)
* Unreal Marketplace Plugin:
    * Updated Marketplace Plugin to include our Blueprint interface
    * [New Unreal Engine quickstart guide](../sdks/unreal/quickstart.md)
    * [View in Unreal Marketplace](https://www.unrealengine.com/marketplace/playfab-sdk)
    * [Upgrade Tutorial](../sdks/unreal/unreal-marketplace-plugin-upgrade-tutorial.md)

## 180906  

Date: 2018-09-06

**New API:**

* **Localization**

**New PlayStream Event Documentation:**

* [client_focus_change](../api-references/events/client-focus-change.md)
* [client_session_start](../api-references/events/client-session-start.md)
* [player_device_info](../api-references/events/player-device-info.md)

## 180829  

Date: 2018-08-29

**API Changes:**

* renaming Entity.TypeString to Entity.Type
* renaming EmptyResult to [EmptyResponse](xref:titleid.playfabapi.com.groups.groups.removemembers#emptyresponse)
* Renamed most Authentication function calls like GameServer* to MutliplayerServer*
* [Admin.GetUserAccountInfo](xref:titleid.playfabapi.com.admin.accountmanagement.getuseraccountinfo) has more detailed platform information

**Objective C Specific Changes:**

* various bug fixes and refactors
* Changing AttributeInstallRequest to be api specific

**Unreal Engine Specific Changes:**

* adding in UE marketplace plugin to SDK generator

## 180809  

Date: 2018-08-09

**API Group Changes:**

* We have separated the Entity API Group into multiple new Api Groups
* This is a big SDK Breaking change for anybody using the former Entity Api
* See our [Upgrade Guide!](../features/data/entities/entity-api-restructure-upgrade-tutorial.md)
* (Please note, the links for blog and upgrade guide may not work yet, they're almost done)

**API Changes:**

* **New Api Methods :**
  * The following APIs are released and visible in SDKs, but the accompanying documentation isn't ready yet:
    * client.[LoginWithNintendoSwitchDeviceId](xref:titleid.playfabapi.com.client.authentication.loginwithnintendoswitchdeviceid)
    * client.[UnlinkNintendoSwitchDeviceId](xref:titleid.playfabapi.com.client.accountmanagement.unlinknintendoswitchdeviceid)
    * server.[GetPlayFabIDsFromNintendoSwitchDeviceIds](xref:titleid.playfabapi.com.client.accountmanagement.getplayfabidsfromnintendoswitchdeviceids)
    * client.[LoginWithFacebookInstantGamesId](xref:titleid.playfabapi.com.client.authentication.loginwithfacebookinstantgamesid) (not ready to use yet)
    * client.[UnlinkFacebookInstantGamesId](xref:titleid.playfabapi.com.client.accountmanagement.unlinkfacebookinstantgamesid) (not ready to use yet)
    * server.[GetPlayFabIDsFromFacebookInstantGamesIds](xref:titleid.playfabapi.com.client.accountmanagement.getplayfabidsfromfacebookinstantgamesids) (not ready to use yet)
* **New PlayStream Events**
  * title_hopper_config_updated event renamed to [title_queue_config_updated](../api-references/events/title-queue-config-updated.md)
* **General changes**
  * The parameter "ServerAddress" in many models has been deprecated in favor of the new "ServerIPV4Address"

**Unreal (multiple SDKs) Specific Changes:**

* Minor updates to both SDKs/plugins leading to a final merge to the Marketplace plugin (Coming soon!)

**[PythonSdk!](https://github.com/PlayFab/PythonSdk) Specific Changes:**

* Bugfixes and improvements

**[UnitySdk](https://github.com/PlayFab/UnitySDK) and [CSharpSDK](https://github.com/PlayFab/CSharpSDK) Specific Changes:**

* Added a new structure called Plugin Manager. For now, this is just a foundation for future changes. Some old function signatures have been marked as obsolete, and should be updated. (No breaking changes though)
* Found and resolved multiple issues with HTTPS.Put, which makes Entity Files more accessible on more platforms.
* Bugfixes in the ScreenTime feature

## 180716  

Date: 2018-07-16

**[UnitySdk](https://github.com/PlayFab/UnitySDK) Changes:**

* Fixed minor issues with ScreenTime under some rare circumstances

**[CSharpSDK](https://github.com/PlayFab/CSharpSDK) Changes:**

* Added [Plugin Manager API](https://github.com/PlayFab/CSharpSDK/blob/master/PluginManager.md) to C# SDK to support optional custom implementations of JSON Serializer and HTTP client

~~**UnrealCppSdk Changes:**~~ (UPDATED : This SDK has been deprecated. For the new unreal SDK, please refer to [UnrealMarketplaceSDK](https://www.unrealengine.com/marketplace/playfab-sdk))

* Unreal 4 C++ SDK is also published on [Unreal Marketplace!](https://www.unrealengine.com/marketplace/playfab-sdk)

## 180710  

Date: 2018-07-10

**Unity Hotfix Release:**

* Further refinements and optimizations to the Screen-Time events

## 180709  

Date: 2018-07-09

**Hotfix Release:**

* Fixing some minor issues with last week's deployments
* Everything in last week's release notes should now actually work as promised

## 180706

Date: 2018-07-06

**API Changes:**

* **New API Method:**
 * entity.[WriteEvents](xref:titleid.playfabapi.com.events.playstreamevents.writeevents)

**[UnitySdk](https://github.com/PlayFab/UnitySDK) Specific Changes:**

* Screen-time tracking, described in the previous release is no longer Beta-only

## 180705  

Date: 2018-07-05

**API Changes:**

* EntityAPI.[ExecuteEntityCloudScript](xref:titleid.playfabapi.com.cloudscript.server-sidecloudscript.executeentitycloudscript)
* PlayStreamEventModel.title_hopper_config_updated

**New [PythonSdk!](https://github.com/PlayFab/PythonSdk)**

* tested with 2.7

**[UnitySdk](https://github.com/PlayFab/UnitySDK) Changes:**

* Wrapped some utilities in a namespace to avoid 3rd party conflicts
* Editor Extensions should misbehave less, and display fewer warnings
* New Feature - read our [Sessions](../features/analytics/metrics/sessions.md) tutorial.

**[JavaScriptSDK](https://github.com/PlayFab/JavaScriptSDK) Changes:**

* customData relay parameter should now work for Login functions

**[XPlatCppSdk](https://github.com/PlayFab/XPlatCppSdk) Specific Changes:**

* Large results will now be parsed correctly

## 180618  

Date: 2018-06-18

**API Changes:**

* Added new error codes in a variety of API methods
* Multiple entity-related PlayStream events now describe their [EntityLineage](../api-references/events/data-types/entitylineage.md)

## 180528  

Date: 2018-05-28

**API Changes:**

* **New API Methods:**
 * Admin.[GetPlayedTitleList](xref:titleid.playfabapi.com.admin.accountmanagement.getplayedtitlelist)
 * Admin.[DeleteMasterPlayerAccount](xref:titleid.playfabapi.com.admin.accountmanagement.deletemasterplayeraccount)
 * Admin.[ExportMasterPlayerData](xref:titleid.playfabapi.com.admin.accountmanagement.exportmasterplayerdata)
 * This is a part of the new GDPR launch. See our blog [here](https://blog.playfab.com/blog/gdpr)
* Updated Error codes in a variety of API methods
* New PlayStream Event:
 * [player_data_exported](../api-references/events/player-data-exported.md)

## 180514  

Date: 2018-05-14

**[XPlatCppSdk](https://github.com/PlayFab/XPlatCppSdk) Specific Changes:**

* Fixes in JSON serialization

## 180507  

Date: 2018-05-07

**API Changes:**

* **New API Method:**
  * entity.[GetProfiles](xref:titleid.playfabapi.com.profiles.accountmanagement.getprofiles)
* **New PlayStream Events:**
  * [entity_executed_cloud_script](../api-references/events/entity-executed-cloud-script.md)
* **Updated API Method:**
  * client.[RegisterPlayFabUser](xref:titleid.playfabapi.com.client.authentication.registerplayfabuser) now returns [result](xref:titleid.playfabapi.com.client.authentication.registerplayfabuser#registerplayfabuserresult).[EntityToken](xref:titleid.playfabapi.com.client.authentication.registerplayfabuser#entitytokenresponse)

**[UnitySdk](https://github.com/PlayFab/UnitySDK) Specific Changes:**

* HttpWebRequest certificate validation security has been improved
 * No longer default to ignoring all certificates
 * Customers are expected to implement their own certificate validation, or call PlayFab.Internal.PlayFabWebRequest.SkipCertificateValidation()

**[WindowsSdk](https://github.com/PlayFab/WindowsSDK) Specific Changes:**

* Fixed hundreds of Level 4 warnings
* The version number published in PlayFabSettings.cpp has been corrected
 * Most previous versions will have all had the wrong version number embedded in-code, and in call headers

**[XPlatCppSdk](https://github.com/PlayFab/XPlatCppSdk) has been created:**

* Currently in beta
 * Built using WindowsSdk as a template
 * May become a replacement to WindowsSdk (At least several months away)
 * Upgrade should require almost no breaking changes
  * Some cpprestsdk strings should be converted to std::string
  * some web::json::value types have been converted to json::value
 * timestamps are not fully tested in Linux
* NuGet package
* Uses lighter weight dependencies
 * Specifically jsoncpp and curl, rather than cpprestsdk
 * uses std::string everywhere, rather than a mix of 2 string types
* Adds Linux Support

## 180414  

Date: 2018-04-14

~~**UnrealCppSdk HotFix:**~~ (UPDATED : This SDK has been deprecated. For the new unreal SDK, please refer to [UnrealMarketplaceSDK](https://www.unrealengine.com/marketplace/playfab-sdk))

* ~~Issues were discovered in the Entity API release for UnrealCppSdk. These are hotfixed, and the Entity API should now work as expected.~~

## 180409  

Date: 2018-04-09

**API Changes:**

* **HotFix:**
  * Only the date was updated, not the major/minor version numbers
* **Guilds:**
  * client.[GetAccountInfo](xref:titleid.playfabapi.com.client.accountmanagement.getaccountinfo).[UserAccountInfo](xref:titleid.playfabapi.com.client.accountmanagement.getaccountinfo#useraccountinfo).[UserTitleInfo](xref:titleid.playfabapi.com.client.accountmanagement.getaccountinfo#usertitleinfo).[TitlePlayerAccount](xref:titleid.playfabapi.com.client.accountmanagement.getaccountinfo#entitykey) now contains the required information to identify other players and add them to your guild/group
  * The same information can also be found with admin.[GetUserAccountInfo](xref:titleid.playfabapi.com.admin.accountmanagement.getuseraccountinfo) and server.[GetUserAccountInfo](xref:titleid.playfabapi.com.server.accountmanagement.getuseraccountinfo)

**[UnitySdk](https://github.com/PlayFab/UnitySDK) Specific Changes:**

* Performance improvement for default HTTP settings (UnityWWW), for long-running processes

## 180403  

Date: 2018-04-03

**Unreal SDKs Updated to support v4.17 thru 4.19:**

* Removing support for UE 4.14 thru 4.16 (Please update!)

## 180329  

Date: 2018-03-29

**Unreal SDKs Updated to support Entity APIs:**

* Sorry for the delay!
* This release still targets UE 4.17, and not 4.18 or 4.19. We are in-progress working on updating versions

## 180316  

Date: 2018-03-16

**API Changes:**

* Entities! [Blog](https://api.playfab.com/blog/introducing-entities-objects-and-files)! [Quickstart Guide](../features/data/entities/quickstart.md)!
 * All Client login methods return Entity credentials if request.LoginTitlePlayerAccountEntity is set to true
* Guilds! [Blog](https://api.playfab.com/blog/announcing-groups-for-guilds-friends-clans-and-more)! [Guide](../features/social/groups/index.md)!
* Error Codes for many API methods updated for accuracy (Dozens!)

**New API Methods:**

* admin.[RevokeInventoryItems](xref:titleid.playfabapi.com.admin.playeritemmanagement.revokeinventoryitems) and server.[RevokeInventoryItems](xref:titleid.playfabapi.com.server.playeritemmanagement.revokeinventoryitems)
* A whole new [Entity API](../features/data/entities/quickstart.md)
* Many new [Entity PlayStream Events](../api-references/events/index.md) (search for "entity" on linked page)

**Most SDKs Updated to support Entity APIs:**

* **Full Support:**
 * [UnitySdk](https://github.com/PlayFab/UnitySDK)
 * [JavaScriptSDK](https://github.com/PlayFab/JavaScriptSDK)
 * [ActionScriptSDK](https://github.com/PlayFab/ActionScriptSDK)
 * [CSharpSDK](https://github.com/PlayFab/CSharpSDK)
 * [NodeSDK](https://github.com/PlayFab/NodeSDK)
 * [PostmanCollection](https://github.com/PlayFab/PostmanCollection)
 * [WindowsSDK](https://github.com/PlayFab/WindowsSDK)
 * [Cocos2d-xSDK](https://github.com/PlayFab/Cocos2d-xSDK)
 * [JavaSDK](https://github.com/PlayFab/JavaSDK)
 * [LuaSdk](https://github.com/PlayFab/LuaSDK) (Including Corona and Defold)
 * [PhpSdk](https://github.com/PlayFab/PhpSdk)
 * CloudScript
* **Will Support Soon:** Unreal Bp and Cpp (Sorry, delayed due to technical difficulties!)

## 180213  

Date: 2018-02-13

**API Changes:**

* SendAccountRecoveryEmail now supports custom account recovery email templates when a custom account recovery email template ID is passed in with the request parameters.
* All Client Login Mechanisms can now optionally return Entity API credentials
(This is part of a coming-soon feature)

**[UnitySdk](https://github.com/PlayFab/UnitySDK) Specific Changes:**

* We are dropping support for older Unity versions, see our [blog post](https://blog.playfab.com/blog/unity-version-support)
* Build files are now published using Unity version 2017.3.0f3

## 180131  

Date: 2018-01-31

**[JavaSDK](https://github.com/PlayFab/JavaSDK) Changes:**

* Java is now published to Maven

## 180129  

Date: 2018-01-29

**[UnitySdk](https://github.com/PlayFab/UnitySDK) Specific Changes:**

* Fixing issues with compression
* It should be safe to re-enable compression for all versions and all platforms

## 180123  

Date: 2018-01-23

**[UnitySdk](https://github.com/PlayFab/UnitySDK) Hotfix:**

* PlayFab UnitySDK had an issue with Unity version 2017.1
* See the [forum post](https://community.playfab.com/questions/16734/error-cs1061-no-definition-for-sendwebrequesterror.html) for details
* This has been resolved, PlayFab UnitySDK should work for all versions again

## 180122  

Date: 2018-01-22

**API Documentation Update:**

* Error codes updated on many API methods

**[CSharpSDK](https://github.com/PlayFab/CSharpSDK) and UnitySDK Specific Changes:**

* Adding a PlayFabException class, so that it's easier to catch PlayFab specific exceptions.

**[NodeSDK](https://github.com/PlayFab/NodeSDK) Specific Changes:**

* SDK Breaking Change: Require syntax for NodeSDK NPM package changed
* Major upgrade focused on NPM package
* Formerly require statements did not follow the NPM convention, requiring multiple nonstandard require statements
* Now it requires a single require statement, and follows NPM conventions
* Major version number changed, this release is now 2.0
* 1.x to 2.x [Upgrade Guide](https://github.com/PlayFab/NodeSDK/blob/master/upgrade.md)

**CloudScript Example:**

* Added TypeScript definitions for the API Error exceptions

## 180103

Date: 2018-01-03

**[LuaSdk](https://github.com/PlayFab/LuaSDK)/Defold/Corona Specific Updates:**

* Bugfix update
* Some platforms were producing a malformed URL which could not be resolved

## 180102  

Date: 2018-01-02

**[UnitySdk](https://github.com/PlayFab/UnitySDK) Specific Updates:**

* Bugfix update
* In order to avoid an issue with response headers, compression should be disabled for all device builds. This update makes that possible
* Alternately, switching to Web Request will also avoid the issue
* A new HTTP option has been added for Unity versions > 2017