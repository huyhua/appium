[//]: # (DO NOT EDIT THIS FILE! This is an auto-generated file. Editing for this document happens in /commands-yml/commands/device/recording-screen/start-recording-screen.yml)

# Start Recording Screen

Start recording screen
## Example Usage

```java
// Java
driver.startRecordingScreen();
driver.startRecordingScreen(new BaseStartScreenRecordingOptions(....));

```

```python
# Python
self.driver.start_recording_screen()

```

```javascript
// Not supported


// wd example
await driver.startRecordingScreen();

```

```ruby
# Ruby
@driver.start_recording_screen
@driver.start_recording_screen video_size: '1280x720', time_limit: '180', bit_rate: '5000000' # Android
@driver.start_recording_screen video_type: 'h264', time_limit: '260' # iOS

```

```php
# PHP
// TODO PHP sample

```

```csharp
// C#
// TODO C# sample

```



## Support

### Appium Server

|Platform|Driver|Platform Versions|Appium Version|Driver Version|
|--------|----------------|------|--------------|--------------|
| iOS | [XCUITest](/docs/en/drivers/ios-xcuitest.md) | 9.3+ | 1.6.0+ | All |
|  | [UIAutomation](/docs/en/drivers/ios-uiautomation.md) | None | None | None |
| Android | [UiAutomator2](/docs/en/drivers/android-uiautomator2.md) | ?+ | 1.6.0+ | All |
|  | [UiAutomator](/docs/en/drivers/android-uiautomator.md) | 4.2+ | All | All |
| Mac | [Mac](/docs/en/drivers/mac.md) | None | None | None |
| Windows | [Windows](/docs/en/drivers/windows.md) | None | None | None |

### Appium Clients

|Language|Support|Documentation|
|--------|-------|-------------|
|[Java](https://github.com/appium/java-client/releases/latest)| All | [static.javadoc.io](https://static.javadoc.io/io.appium/java-client/6.1.0/io/appium/java_client/screenrecording/CanRecordScreen.html#startRecordingScreen-T-) |
|[Python](https://github.com/appium/python-client/releases/latest)| All |  |
|[Javascript (WebdriverIO)](http://webdriver.io/index.html)| All |  |
|[Javascript (WD)](https://github.com/admc/wd/releases/latest)| All | [github.com](https://github.com/admc/wd/blob/master/lib/commands.js#L3412) |
|[Ruby](https://github.com/appium/ruby_lib/releases/latest)| All | [Android](https://www.rubydoc.info/github/appium/ruby_lib_core/Appium/Core/Android/Device#start_recording_screen-instance_method) [iOS](https://www.rubydoc.info/github/appium/ruby_lib_core/Appium/Core/Ios/Xcuitest/Device#start_recording_screen-instance_method) |
|[PHP](https://github.com/appium/php-client/releases/latest)| None | [github.com](https://github.com/appium/php-client/) |
|[C#](https://github.com/appium/appium-dotnet-driver/releases/latest)| None | [github.com](https://github.com/appium/appium-dotnet-driver/) |

## HTTP API Specifications

### Endpoint

`POST /session/:session_id/appium/start_recording_screen`

### URL Parameters

|name|description|
|----|-----------|
|session_id|ID of the session to route the command to|

### JSON Parameters

|name|type|description|
|----|----|-----------|
| remote_path | `string` | The path to the remote location, where the resulting video should be uploaded. The following protocols are supported http/https, ftp. Null or empty string value (the default setting) means the content of resulting file should be encoded as Base64 and passed as the endpount response value. An exception will be thrown if the generated media file is too big to fit into the available process memory. This option only has an effect if there is screen recording process in progreess and `forceRestart` parameter is not set to `true`. |
| username | `string` | The name of the user for the remote authentication. |
| password | `string` | The password for the remote authentication. |
| method | `string` | The http multipart upload method name. The 'PUT' one is used by default. |
| force_restart | `boolean` | Whether to try to catch and upload/return the currently running screen recording (`false`, the default setting on server) or ignore the result of it and start a new recording immediately (`true`). |
| time_limit | `string` | Recording time. 180 seconds is by default. |
| video_type | `string` | (iOS Only) The format of the screen capture to be recorded. Available formats "h264", "mp4" or "fmp4". Default is "mp4". Only works for Simulator. |
| video_quality | `string` | (iOS Only) The video encoding quality (low, medium, high, photo - defaults to medium). Only works for real devices. |
| bit_rate | `string` | (iOS Only) The video bit rate for the video, in megabits per second. 4 Mbp/s(4000000) is by default for Android API level below 27. 20 Mb/s(20000000) for API level 27 and above. |
| video_size | `string` | (Android Only) The format is widthxheight. The default value is the device's native display resolution (if supported), 1280x720 if not. For best results, use a size supported by your device's Advanced Video Coding (AVC) encoder. For example, "1280x720" |
| bug_report | `string` | (Android Only) Set it to `true` in order to display additional information on the video overlay, such as a timestamp, that is helpful in videos captured to illustrate bugs. This option is only supported since API level 27 (Android O). |

### Response

null

## See Also

* [JSONWP Specification](https://github.com/appium/appium-base-driver/blob/master/lib/protocol/routes.js#L345)