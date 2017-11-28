# tensorflow-windows-lib
This is a `.def` file for generating `tensorflow.lib` from `tensorflow.dll`. It can access only C API of Tensorflow.

## Where can I get dll?
Every python wheel for Tensorflow includes `tensorflow.dll`, only named with `_pywrap_tensorflow_internal.pyd`.

## Why would one need this?
For those who have made the frustrating decision to use Tensorflow on Windows without Python. For an example, it can be used with [Rust bindings for Tensorflow](https://github.com/tensorflow/rust).

## Is this stable?
It works, but I don't think it's stable yet.

## How to
You must have Visual C++ Build Tools. From Visual Studio Command Prompt which can access `link.exe`,

```
link.exe /DEF:<DEF file from this repo> /DLL:<Path of DLL file> /OUT:<Destination of LIB file>
```
