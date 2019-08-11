## Frida For android

---

## About me
---

## Topics 


- Basics of Frida
- Dynamic  Binary Instrumentatation
- Common Challenges while pentesting Android
- Modes of operation
- Frida Installation
- Frida Common Api for Android 
- Frida Hooking
- Frida Python Binding
- References


---
## Outcomes

- Setting up the Frida
- Learn Basic Frida Commands
- Reverse Enginnering and Bypassing the apps 

---


## What is Frida


- Dynamic binary instrumentation tool

![inject-tool](https://mk0resourcesinfm536w.kinstacdn.com/wp-content/uploads/CodeInjection01162014.gif)


---
## What is Dynamic Binary Instrumentation

Types of Dynamic  Instrumentation

1) Injected

2) Embeded

---

![frida](http://www.ryantzj.com/images/instrumentation_types.png)
---
## Why frida

How we change the app logic ?

## Smali reversing

![smali](http://mstajbakhsh.ir/wp-content/uploads/2016/12/Smali-Code.png)

---
![no-](https://i.imgur.com/RUdPyQP.jpg)
---

## Dynamic Binary Instumenation

![frida](https://cdn-images-1.medium.com/max/1050/1*5JNEHSsnrE1VLfl5mpXuFg.png)


---
## Common Challenges While pentsting android apps 
1. Root Bypassing
2. Anti Debugging
3. Anti Emulation
4. Bypassing App Logic 
---
# Modes of operation

## Injected
1. spawn an existing process
2. hook to the running program
3. Requires the root access

---

## Embeded

1. Frida-gadget  a shared library


## Preloaded
1. Using a dynamic linker feature like LD_PRELOAD or DYLD_INSERT_LIBRARIES
2. Not used in android
---

## Frida Installation

`pip  install frida`


`pip install frida-tools`

---
## Frida Installation on phone
```
adb push frida-server /data/local/tmp/

adb shell "chmod 755 /data/local/tmp/frida-server"

adb shell "/data/local/tmp/frida-server &"
```

---
## Frida Basics

### Frida-ps
The tool to check the running process

To check the running process inside the emulator

`frida-ps -U` - To check the running apps inside the emulator

`frida-ps -Ua`  - To check the running apps inside the emulator

`frida-ps -Uai` - To check the running app process inside the emulator

---
## Frida-ls
This tool help to list the devices

`frida-ls-devices`


## Frida Hooking
The cli version of frida



`frida -U <process-name>`

`frida -U -f <process-name>`

`frida -U -f <process-name> --no-pause`

---
## Frida Api for Android

- Java.perform - call the function
- Java.use-use the particular class
     
``` 
 var   main = Java.use("sg.vantagepoint.root.MainActivity");
```
---
- .implementation-override the existing function
       main.isDeviceRooted.implementation
- .overload-to use polymorphism
       .overload(“datatype”).implementation

---
## Sample javascript payload
``` javascript

Java.perform(function() {

        var   main = Java.use("sg.vantagepoint.root.MainActivity");

       main.function-name.implementation = function() {
            console.log("In function A");
             return false;
         }  
   

});

```

---

## Demo 1


![demo](https://media.makeameme.org/created/its-a-secret-y0nz9m.jpg)


---
## Solution

![code1](https://frida-android.netlify.com/level1.png)

> frida -U -f <process-name> --no-pause -l l1.js
---
### Python Binding


```
import frida, sys

ss = """
Java.perform(function () {
 //logic goes here
"""
device = frida.get_usb_device()
pid = device.spawn(["sg.vantagepoint.root"])
session = device.attach(pid)
script = session.create_script(ss)
script.load()
device.resume(pid)
raw_input()
```
---

## Demo 2

![sample](https://i.kym-cdn.com/entries/icons/original/000/027/581/strange.jpg)


---
## Solution
![code](https://frida-android.netlify.com/level2.png)

>python filename.py
---


## Questions

![ques](http://pngimg.com/uploads/question_mark/question_mark_PNG82.png)
---
### References

- https://koz.io/using-frida-on-android-without-root/

- https://securitygrind.com/ssl-pinning-bypass-with-frida-gadget-gadget-injector-py/

- https://www.slideshare.net/ChandrapalBN/pentesting-android-apps-using-frida-beginners

- https://resources.infosecinstitute.com/frida/

- https://www.frida.re/docs/android/


