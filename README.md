#NeverIdle

*I like you, but don't delete my phone, okay? *

This program is written by hand, and the following introduction is also written as you like, don't touch it if you don't like it.

## One click script One click to go

```shell
bash <(curl -s -L https://gist.githubusercontent.com/Ansen/e45320205faf5786d3282ac880f20bab/raw/onekey-NeverIdle.sh)
```

MJJs will probably love this. Thanks to script author @Ansen

The following commands are executed by default, but of course they cannot cover all requirements.  
For example, AMD does not have 2G memory, and there is no requirement to waste memory.  
Therefore, it is still recommended that you install it yourself, which is also very convenient and fast.

## Usage

Download the executable from Release. Note the distinction between amd64 and arm64.

Start a screen on the server, then execute this program, and search for usage.

Command parameters:

```shell
./NeverIdle -c 2h -m 2 -n 4h
```

in:

-c means to enable periodic CPU waste, followed by the interval between each waste.  
If every 12 hours, 23 minutes and 34 seconds is wasted, it is 12h23m34s. Fill in according to the format.

-cp means to enable coarse-grained CPU percentage waste, and the waste rate will change in real time with the usage level of the machine.  
If the maximum waste of 20% of the CPU is -cp 0.2. The value range of the percentage is [0, 1] and be careful not to use it with `-c`.

-m refers to the amount of memory to enable wasting, followed by a number in GiB.  
After startup, the corresponding amount of memory will be occupied and will not be released until the process is manually killed.

-n means to enable network periodic waste, followed by the interval time of each waste.  
The format is the same as CPU. The Ookla Speed ​​Test will be executed regularly (and the results will be output!)

-t refers to setting the number of concurrent connections that the network periodically wastes.  
The default is 10. The larger the value, the more resources will be consumed. Generally, it does not need to be changed.

-p means to set the process priority, followed by a priority value. If not specified, the lowest priority of the platform will be used by default.  
For UNIX-like systems (such as Linux, FreeBSD and macOS), the value range is [-20,19], and the higher the number, the lower the priority.  
For Windows, see [official documentation](https://learn.microsoft.com/zh-cn/windows/win32/api/processthreadsapi/nf-processthreadsapi-setpriorityclass).  
It is recommended not to specify, the default is the lowest priority, making way for all other processes.

* Immediately execute all the functions you configure once you start the program, and you can observe the effect. *
