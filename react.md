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



https://reactnative.dev/architecture/fabric-renderer
https://reactnative.dev/architecture/view-flattening
