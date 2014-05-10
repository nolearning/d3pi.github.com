---
layout: post
title: The Discussion On Kernel Architecture

[There was a discussion about why Linux use monolithic kernel?](http://www.zhihu.com/question/20314255)

The question was discussed many times before. In 1990s, Linus choosed the way as it was simple to implement. In micro kernel architecture there need do be a machanism to communicate between different system parts and different Level, including resource clone in bidirection for security and robust reason, indirected call, message queue and so on. In contrast,  monolithic kernel make many operations as direct call with pointers which refer to real resouces, it is simple.

Moving on the linux kernel, monolithic kernel architecture doesn't make linux development and run worse but better.

There some reference:
http://www.absoluteastronomy.com/topics/Monolithic_kernel
http://www.absoluteastronomy.com/topics/Microkernel
http://www.absoluteastronomy.com/topics/Hybrid_kernel
http://c2.com/cgi/wiki?MicroKernel
