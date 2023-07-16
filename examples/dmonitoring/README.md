# Introduction
This example is to evaluate the performance of dmonitoring_model.onnx from openpilot on an RK3588 platform's dedicated NPU Cores.

Done:
1. To inference a static image using NPU on RK3588. 

Future to-do:
1. To be able to stream video from USB camera or dedicated RK3588 CSI camera for inferencing
2. To evaluate the inference speed of the dmonitoring_model.onnx between quantised and non-quantised.

The following <TARGET_PLATFORM> represents RK356X or RK3588.

# Aarch64 Linux Demo

## Build

modify `GCC_COMPILER` on `build-linux_<TARGET_PLATFORM>.sh` for target platform,

then execute

```
./build-linux_<TARGET_PLATFORM>.sh
```

## *Install*

Copy install/dmonitoring_Linux to the devices under /userdata/.

- If your board has sshd service, you can use scp or other methods to copy the program and rknn model to the board.

## Run

```
adb shell
cd /userdata/dmonitoring_Linux/
```

```
export LD_LIBRARY_PATH=./lib
sudo ./dmonitoring model/<TARGET_PLATFORM>/dmonitoring_model.rknn model/ecam.jpeg
```

