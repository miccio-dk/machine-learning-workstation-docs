# GPU usage
This page contains information on the high-performance GPUs mounted on the workstation.

## Available GPUs
The workstation is equipped with three Nvidia TITAN X Pascal graphics cards, to be used for computing purposes, and one Nvidia GeForce GT 710 used as graphics adapter.

## Specify device
From a python script, your can set the GPU(s) seen by the cuda drivers.
Add the following lines:
```py
import os

os.environ['CUDA_VISIBLE_DEVICES']='<DEVICE_LIST>'
```

Please note: `<DEVICE_LIST>` can be 0, 2, or 3.
You can specify a different value for each of your scripts, and they will run on different GPUs.
It is recommended to always manually set this variable, otherwise the script will end up reserving all the GPUs, even if they won't be used.

## Check usage
In order to check which GPUs are currently in use, and which processes are using them, you can run the following command:
```sh
nvidia-smi
```

Here's an example output of the command above:
```
+-----------------------------------------------------------------------------+
| NVIDIA-SMI 384.130                Driver Version: 384.130                   |
|-------------------------------+----------------------+----------------------+
| GPU  Name        Persistence-M| Bus-Id        Disp.A | Volatile Uncorr. ECC |
| Fan  Temp  Perf  Pwr:Usage/Cap|         Memory-Usage | GPU-Util  Compute M. |
|===============================+======================+======================|
|   0  GeForce GT 710      Off  | 00000000:02:00.0 N/A |                  N/A |
| N/A   33C    P0    N/A /  N/A |      0MiB /  2000MiB |     N/A      Default |
+-------------------------------+----------------------+----------------------+
|   1  TITAN X (Pascal)    Off  | 00000000:03:00.0 Off |                  N/A |
| 25%   44C    P0    57W / 250W |      0MiB / 12189MiB |      0%      Default |
+-------------------------------+----------------------+----------------------+
|   2  TITAN X (Pascal)    Off  | 00000000:82:00.0 Off |                  N/A |
| 26%   45C    P0    54W / 250W |      0MiB / 12189MiB |      2%      Default |
+-------------------------------+----------------------+----------------------+
|   3  TITAN X (Pascal)    Off  | 00000000:83:00.0 Off |                  N/A |
| 23%   36C    P8    10W / 250W |  11761MiB / 12189MiB |      0%      Default |
+-------------------------------+----------------------+----------------------+

+-----------------------------------------------------------------------------+
| Processes:                                                       GPU Memory |
|  GPU       PID   Type   Process name                             Usage      |
|=============================================================================|
|    0                    Not Supported                                       |
|    3      6428      C   ...18/miniconda3/envs/denoising/bin/python 11751MiB |
+-----------------------------------------------------------------------------+
```

In this case, only one GPU is in use (namely, the #3) which can be deducted from the `Memory-Usage` column.
At the bottom, you can find the process identifier of what's using the GPU, in the `PID` column (6428).

To obtain more information about the process:
```sh
ps aux | grep <PID>
```

If the process has been executed by you, you can attempt at terminating it:
```sh
kill <PID>
```
