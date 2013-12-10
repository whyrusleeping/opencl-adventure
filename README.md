opencl-adventure
================

A diary of sorts for my exploration of opencl.  Ive wanted to learn opencl for a while now,
and Im going to log the programs i write and the troubles I have here for reference

Setup
=====

My Dev machine is an Intel 4930k, Running Fedora 19 and most importantly, and Nvidia gtx770.

Im using the official Nvidia drivers through rpmfusion [http://www.if-not-true-then-false.com/2013/fedora-19-nvidia-guide/]
in order to get the opencl libraries to be recognized by gcc, i made symlinks to them in my /usr/lib64 folder.
If you dont know where the libraries are installed at try: `sudo updatedb; locate libOpenCL` if nothing shows up,
something is wrong with your installation of your graphics drivers.

    ln -s /path/to/libOpenCL.so.1 /usr/lib64/libOpenCL.so

For the headers, i used nvidias cuda repo (although I have heard you can download the headers through Khronos) and when compiling
i specify `-I/path/to/my/opencl/include/directory/`

A typical build command for opencl for me looks like:

    g++ HelloWorld.cpp -I/usr/local/cuda-5.5/targets/x86_64-linux/include -lOpenCL -o hellow
