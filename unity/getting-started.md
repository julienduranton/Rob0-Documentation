# Getting Started with Rob0 Unity SDK

Welcome to your Dashboard, here’s all the info you need to be able to link your projects to your Rob0 Console.

## System requirements

The Rob0 SDK is still under development, and we’re working hard to add support to all platforms, although it may very well already work on platforms not listed below. It has currently being tested using the following configurations: • Unity 2017 or above • iOS, Android and Standalone (PC or macOS)

### Recommended settings

In order to leverage the latest features that Unity has developed to reduce lag when reading from the GPU, the recommended settings are:

- To deploy on Android:
  - Unity 2018.1 or above
  - Vulkan graphics API
- To deploy on iOS:
  - Unity 2018.3 or above
  - Metal API
- To deploy on PC or Mac:
  - Unity 2018.1 or above
  - Graphics API that allows asynchronous GPU read back

Not sure if Rob0 is going to work in your specific configuration or need support for the earlier versions of Unity? Feel free to reach us via Intercom or email.

## Adding Rob0 to your app

### Create App on the console

To start using Rob0, you have to create a [free account](http://console.rob0.io/signIn) and login to the Rob0 Console, which provides a web interface to manage all Rob0 services.

1. Login to [Rob0 Console](http://console.rob0.io)
2. Create New Project
3. Complete the project name and description

### Configure Rob0 Editor Plugin

1. Download the latest Rob0 `.unitypackage` from the Downloads page
2. In your Unity project go to **Assets -> Import Package -> Custom Package…**
3. Select `.rob0-sdk-unity.unitypackage` and import all assets

![Import](./img/getting-started/import.png)

4. After importing, configure Rob0 App Key, go to **Rob0 -> Edit Settings**

![Access settings](./img/getting-started/settings-access.png)

5. Add the Rob0 App Key for your project

![Settings](./img/getting-started/settings.png)

This is your Rob0 App Key:

{{ApiKey}}

## Start using Rob0

At this point, you should be able to start using Rob0. Play with your app a little bit and minimize or close it. A snapshot of the last minute of use will be sent to the Rob0 Console (this might take a minute or two).

_Note: This also works in the editor, but in order to trigger the upload you need to switch to a different application while Unity is still running your project._

## Known issues

In order for the recording to work efficiently, all UI Canvas need to render to a camera. In order to capture screenshots without blocking the main thread it’s necessary to use the function:

```
Rendering.AsyncGPUReadback
```

Which is only available in Unity 2018.1 and above for all devices except Metal and OpenGL. Metal should have been included in Unity 2018.2 although it looks like it might only make it in 2018.3. [https://forum.unity.com/threads/graphics-asynchronous-gpu-readback-api.529901/](https://forum.unity.com/threads/graphics-asynchronous-gpu-readback-api.529901/)
