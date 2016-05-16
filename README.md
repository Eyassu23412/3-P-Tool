# 3-P Tool
## Overview(3-P Tool)

<p>3-P(parallel point-cloud processing) tool is a parallel processing tool that helps users to process large-scale point-clouds in parallel computing environment.3-P implements two interpolation algorithms, i.e., IDW and Kriging using MPI. It also has a configurable input parameters which can run both on GUI mode(it was built using JAVA swing libraries) and command-mode. Our processing tool provides a layer of abstraction for users to hide low level operations in parallel processing.</p>

## Usage

 <b > Programmatic access</b>

  The main folder Lidar_V2 contains different .c files. 
  <li>
    <ol>```griddig_new.c ```is the master code. It manages everything as input and output</ol>
    <ol>• ```x86_machines``` cluster configuration: contains the IP address of the cluster nodes(if the processing environment is cluster).</ol>
    <ol>• ```./cluster_gridding```  is the target name where users can run the executed MPI file.</ol>
    <ol>• 3-P tool can work in two mode: GUI and command-line mode.</ol>
  </li>

  <b> Front-end (GUI mode of 3-P)</b>
    <li>
      <ul>Detail explanation on how to run the GUI mode is provided in the ```Help tab```.</ul>
      <ul>• Make sure that you have installed java JDK on your machine before you run the GUI mode.</ul>
      <ul>• To run the GUI jar from the command line, go to the jar folder and type the following: 
          ```Java –jar “ JavaApplication.jar” ``` </ul>
      <ul>• Two folders should be created manually in the 3-P program folder. 
      <ul>• Create ```output``` folder inside the 3-P program folder. This folder holds the results of each slave processes.</ul>
      <ul>• Create ```result``` folder inside the output folder which merges the output files.</ul>
      </ul>
  </li>
 <b> Command line mode</b>

  <li>
    <ul>When we compile and run the 3-P tool on command line mode: we can choose multicore or cluster mode.</ul>
    <ul>• To compile the program, type ```make``` command in the 3-p directory.</ul>
    <ul>• Make sure the 3-P is placed in the same directory path where the MPI library is installed. Otherwise use the absolute path when u call mpiexec command. </ul>
    <ul>•	NFS (Network file system) must be configured properly in for the cluster environment and the 3-P tool should be placed in the NFS directory so that other nodes can mount the folder. The MPI library should also be installed in the NFS folder.</ul>
    <ul>•	For multicore type the following command
          <ul>•```	mpiexec -n 8 ./cluster_gridding 1 1 Data1_Ground.txt 1 1 ```</ul>
    </ul>
    <ul>•	For cluster environment type the following command
          <ul>•``` mpiexec –f x86machines -n 8 ./cluster_gridding 1 1 Data1.Ground.txt 1 1 ```</ul>
          <ul>• i.e  –n 8 is the number of processes used for execution</ul>
          <ul>• The input parameters are grid size, search range, point-cloud data, interpolation type, and mode.</ul>
          <ul>• Interpolation type: ```0 for Kriging and 1 for IDW ```</ul>
          <ul>• Mode:``` 0 for in-core and 1 for out-of-core ```</ul>
    </ul>
    <ul>• Users can split big input data points in command line mode using the split program ```(split.c) ```in gcc compiler. </ul>
  </li>

 

## Built With

* MPI - Message Passing Interface for the parallel module
* Java Swing Libraries for GUI module.

 

## Authors

* **Eyassu Berhanu** - [Eyassu23412](https://github.com/Eyassu23412)
