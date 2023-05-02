Download Link: https://assignmentchef.com/product/solved-cop4600-ex-5-threading
<br>
<h1></h1>

<h2>Overview</h2>

The aim of this exercise is to familiarize you with multithreading in C++. In the right situation, threads can significantly speed up your programs by allowing parts of it to run concurrently rather than sequentially. Here is a simple example:

Note the use of the join() function above. Without it, it would be possible for the main function to finish executing and exit before the thread has completed execution.




<h2>Structure</h2>

To complete this exercise, you will be writing a program that spawns 10 threads, each of which will attempt to do the same job. Due to the nature of threads, you’ll notice that they finish in a different order every time.

<ol>

 <li>Write a C++ program that takes a number as a command-line argument (i.e. ./thread 1414)</li>

 <li>Write a function inside this program with two parameters: one is an ID number, and the other will be the number passed in as a command-line argument.</li>

 <li>This function will generate random numbers between 0 and 9999 until it generates one that matches the number given as a command-line argument, then print “Thread &lt;id&gt; completed.”</li>

</ol>







<ol start="3">

 <li>In your program’s main function, spawn 10 threads, each of which will call your new function with a unique ID (0 through 9) and the number given as a command-line argument.</li>

</ol>

<strong><em>Note: Your threads must be spawned inside of a loop. You should NOT have 10 individual calls to thread() in your program.  </em></strong>

<ol start="4">

 <li>Finally, once all of your threads have finished generating numbers, print “All threads have finished finding numbers.”</li>

</ol>

<strong><em>Note: In order to compile your program with threads, you will need to use the flags  </em></strong><strong>-std=c++11 -pthread</strong><strong><em> with the g++ command.  </em></strong>

<h3>Enabling Race Conditions</h3>

In order to ensure that the execution of threads finish in a randomized order, you can use the <strong>nice</strong> utility. <strong>nice</strong> is a program that allows setting or altering the priority of a process. You should give your process the lowest priority to ensure that the CPU will execute it less often. In addition, you should lower your virtual machine’s memory and maximize the number of cores. This will slow the process down and cause the threads to execute out of order due to the interruptions and race conditions.




Read about <strong>nice</strong> here: <a href="https://man7.org/linux/man-pages/man1/nice.1.html">https://man7.org/linux/man</a><a href="https://man7.org/linux/man-pages/man1/nice.1.html">–</a><a href="https://man7.org/linux/man-pages/man1/nice.1.html">pages/man1/nice.1.html</a>




<strong><em>Note: RAM and CPU settings differ depending on your machine. You should give your virtual machine at least 512 MBs. </em></strong>