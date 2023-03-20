# [Node IPC](https://github.com/RIAEvangelist/node-ipc)
## Advantages: 
- We are able to custom the configuration for the project base on Node IPC.
https://github.com/RIAEvangelist/node-ipc#ipc-config
- Types of IPC Sockets
https://github.com/RIAEvangelist/node-ipc#types-of-ipc-sockets

# Electron IPC: https://github.com/electron/electron 
## Advantages:
- We do not need to implement the main and renderer processes. The implementation of Electron is ready for establishing the project
- Electron also support feature for security in these process.
- A large number of people in the community. It means that many issues were resolved in the Electron project already.



# Architect Solutions:
## 1. Hidden renderer process
    Overview:
        - It’s basically just another browser window managed by your application.
        - Suitable for low or medium-complexity categories.
    Disadvantages:
        - Performance degradation when running the long-lived, CPU-intensive operations in a hidden renderer process.
        - There is no direct way for hidden renderers to communicate with the visible renderer(s).
        - Renderers communicate via the main application process by IPC, take efforts on implementing IPC to interact between renderers via main process.
https://miro.medium.com/max/700/1*BF5zzSZ97fdBGs1_x-JSaQ.png
    References:
        - https://blog.logrocket.com/advanced-electron-js-architecture/
## 2. Web workers
    Overview:
        - Useful in handling smaller computational tasks than hidden renderer within a request.
    Disadvantages:
        - Web workers should not be used for long-running tasks like server processes.
        - Web workers do not have access to the renderer’s DOM, so you can not perform any kind of UI manipulation with them.
        - Additionally Web workers can not use Electrons NodeJS integration, means for example you do not have access to local resources like the file system.
        - Sometimes child threads get delayed as it shares the same io stream used by the Nodejs process along with the main thread in case main thread got delayed.

    References:
        - https://blog.logrocket.com/advanced-electron-js-architecture/
        - https://spectrumstutz.com/nodejs/nodejs-child-process-worker-threads/

## 3. Create/fork new process in main.js
    Overview:
        - A new Nodejs instance.
    Disadvantages:
        - Limited by the maximum threads of CPU.
    References:
        - https://blog.logrocket.com/advanced-electron-js-architecture/
        - https://spectrumstutz.com/nodejs/nodejs-child-process-worker-threads/

Summary:
    - Depending on the cases, we need to utilize the combinations of the ways to prevent blocking the application. But with the expensive tasks, fork child process is suitable solution at this time.
So we have implemented the demo above to describe the child process architecture.
