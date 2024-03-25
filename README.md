install docker on your machine

clone the source code onto your directory

	git clone https://github.com/Vishwanath-Bhat/PINTOS-Thread-Management
 
As the next step, build the source code supplied for the first project. First, run the docker container with a mount of your source: 	
(The Docker Image was created by Prof. TheirrySans University of Toloronto)

$ docker run --platform linux/amd64 --rm --name pintos -it -v "$(pwd):/pintos" thierrysans/pintos bash

Once in the Docker container, you should build the utils directory (first time only): 	

$ cd /pintos/src/utils

$ make

Then, let us build the Pintos kernel inside the docker container: 	

$ cd /pintos/src/threads

$ make

This will create a build directory under threads, populate it with a Makefile and a few subdirectories, and then build the kernel inside. The entire build should take less than 30 seconds.

IN the File threads.output contains all the test cases provided by pintos

pintos -v -k -T 60 --bochs  -- -q  run alarm-single

This test case creates N threads so we will be using it

run the above test case using GDB a debugging tool provided in pintos(u can refer official documentation for more information about it: https://thierrysans.me/CSCC69/projects/

pintos -v -k -T 60 --bochs --gdb -- -q  run alarm-single

Now open another terminal and connect to gdb port:

pintos-gdb kernel.o

debugpintos

Add breakpoints for clear visualization

b test_sleep

b thread.c:558

b interrupt.c:387

b alarm-wait.c:93

Now keep on continuing... until breakpoint 4 is hit

