FXBenchmark01
=============

Webpage: http://mihosoft.eu/?p=280

Simple JavaFX Benchmark Application based on JavaFX 2.0 BubbleMark: http://tbeernot.wordpress.com/2011/11/12/javafx-2-0-bubblemark/

## Why? ##
I have created a Visual Programming Environment using Swing. I think of switching to JavaFX. But before I start with the real implementation I want to be sure that the performance is ok. Unfortunately, JavaFX still has some critical issues that are hopefully resolved in the near future.

The purpose of this benchmark is to investigate these issues.

## Issues ##
Performance seems to heavily depend on the graphics card/driver/OS. Even more important, the framerate of a JavaFX application drops as the size of the application stage increases. This does not only happen if nodes are drawn on the whole application window but also if only a part of the window shows content. If your application runs on a large screen, e.g., a 27" iMac (2880x2560), this does really matter.

## Questions ##

- Does JavaFX use dirty region optimization like Swing?

- Does it use additional image buffers like JCanvas3D in Java3D does?

  > This would be a good explanation for the fps drop. I have the feeling that the delay introduced by increased window size is independent from the number of nodes in the sceenegraph.


## The Benchmark ##
1. perform the bubblemark (uses only wall collision)
2. add more balls
3. increase the window size and start with `1.` again

After several runs the benchmark stops and writes the results to `statistics.txt`.