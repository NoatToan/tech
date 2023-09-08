### Fabric
Fabric is React Native's new rendering system
The core principles are to unify more render logic in C++

### Motivations and Benefits of the new renderer

Enable React Concurrent Features on React Native.
Easier to implement server side rendering for React Native.
With support of multi-priority and synchronous events, the renderer can prioritize certain user interactions to ensure they are handled in a timely manner.


## Provides benefits:
Type safety: code generation to ensure type safety across the JS and host platforms. The code generation uses JavaScript component declarations as source of truth to generate C++ structs to hold the props. Mismatch between JavaScript and host component props triggers a build error.
Shared C++ core: the renderer is implemented in C++ and the core is shared among platforms. This increases consistency and makes it easier to adopt React Native on new platforms.
mproved Performance: With the new cross-platform implementation of the renderer system, every platform benefits from performance improvements that may have been motivated by limitations of one platform. For example, view flattening was originally a performance solution for Android and is now provided by default on both Android and iOS.
Consistency: The new render system is cross-platform, it is easier to keep consistency among different platforms.
Faster Startup: Host components are lazily initialized by default.




![image](https://github.com/NoatToan/tech/assets/49062153/9c2e94c3-9ccb-422b-89fe-2b8d159d6f6e)

### Fabric View Flattening 
![image](https://github.com/NoatToan/tech/assets/49062153/6114d3de-8ea3-4823-ad80-c1cdbbccef33)

### Threading Model
![image](https://github.com/NoatToan/tech/assets/49062153/0ceab406-ed2c-48be-93f2-e995495194f8)
![image](https://github.com/NoatToan/tech/assets/49062153/602fc0ef-8f03-48b4-bf69-b4fc25ea70ab)

### Bundled Hermes
Starting with React Native 0.69.0, every version of React Native will be built alongside to a Hermes version. We call this distribution model Bundled Hermes.

From 0.69 on, you will always have a JS engine that has been built and tested alongside each React Native version that you can use.

### Can users still use another engine?
Yes, users are free to enable/disable Hermes (with the enableHermes variable on Android, hermes_enabled on iOS). The 'Bundled Hermes' change will impact only how Hermes is built and bundled for you.

Starting with React Native 0.70, the default for enableHermes/hermes_enabled is true.

Without Hermes:
![image](https://github.com/NoatToan/tech/assets/49062153/0d3deb55-044a-403f-a6ee-37f0e40d8290)

Enabled Hermes:
![image](https://github.com/NoatToan/tech/assets/49062153/7d7ea97c-c62c-4880-8fb7-21a3e6c61e35)


https://reactnative.dev/architecture/fabric-renderer
https://reactnative.dev/architecture/view-flattening
