# tensorflow-windows-lib
This is a `.def` file for generating `tensorflow.lib` from `tensorflow.dll`. It can access only the C API of Tensorflow.

## Where can I get dll?
Every python wheel for Tensorflow includes `tensorflow.dll`, only named with
`_pywrap_tensorflow_internal.pyd`.

Alternatively, you can compile `tensorflow.so` using bazel or cmake, and
simply rename the file to `tensorflow.dll`. This is the method used by Google
in the [Windows CI script](https://github.com/tensorflow/tensorflow/blob/c9dbbb898b3b8c3fcb113f5e43bc5a764ee81a8f/tensorflow/tools/ci_build/windows/libtensorflow_cpu.sh#L71****).

## Why would one need this?
For those who have made the frustrating decision to use Tensorflow on Windows
without Python. For an example, it can be used with [Rust bindings for
Tensorflow](https://github.com/tensorflow/rust).

## Is this stable?
It works as of v1.6.0, but as the C API is not stable, this is also not
stable.

## How to
You must have Visual C++ Build Tools. From the Visual Studio Command Prompt,
use `lib.exe`,

``` lib.exe /DEF:<DEF file from this repo> /OUT:<Destination of LIB file> ```