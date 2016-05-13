## Overview

<p>3-P tool is a parallel processing tool that helps users to process large-scale point-clouds in parallel computing environment.3-P implements two interpolation algorithms, i.e., IDW and Kriging using MPI. It also has a configurable input parameters which can run both on GUI mode and command-mode. Our processing tool provides a layered of abstraction for users to hide low level operations in parallel processing.</p>

## Usage

 <b > Programmatic access</b>

  The main folder Lidar_V2 contains different .c files. 
  <li>
    <ul>•	griddig_new.c is the master code. It manages everything as input and output</ul>
    <ul>•	x86_machines cluster configuration: contains the IP address of the cluster nodes(if the processing environment is cluster).</ul>
    <ul>•	./cluster_gridding  is the target name where users can run the executed MPI file.</ul>
    <ul>•	3-P tool can work in two mode: GUI and command-line mode.</ul>
  </li>

  <b> Front-end (GUI mode of 3-P)</b>
    <li>
      <ul>•Detail explanation on how to run the GUI mode is provided in the Help tab.</ul>
      <ul>•	Make sure that you have installed java JDK on your machine before you run the GUI mode.</ul>
      <ul>•	To run the GUI jar from the command line, go to the jar folder and type the following:Java –jar “ JavaApplication.jar” </ul>
      <ul>•	The following directories should be created in the 3-P program folder. 
        <li>
          <ul>•	Create “output” folder inside the 3-P program folder. This folder holds the results of each slave processes.</ul>
          <ul>•	Create “result” folder inside the output folder which merges the output files.</ul>
        </li>
      </ul>
  </li>
 <b > Command line mode</b>

  <li>
    <ul>•	When we compile and run the 3-P tool on command line mode: we can choose multicore or cluster mode.</ul>
    <ul>• To compile the program, type make command in the 3-p directory.</ul>
    <ul>• Make sure the 3-P is placed in the same directory path where the MPI library is installed. Otherwise use the absolute path when u call mpiexec command. </ul>
    <ul>•	NFS (Network file system) must be configured properly in for the cluster environment and the 3-P tool should be placed in the NFS directory so that other nodes can mount the folder. The MPI library should also be installed in the NFS folder.</ul>
    <ul>•	For multicore type the following command
      <li>
          <ul>•	mpiexec -n 8 ./cluster_gridding 1 1 sortedchecked.txt 1 1</ul>
          <ul>•	Create “result” folder inside the output folder which merges the output files.</ul>
        </li>
    </ul>
  </li>

 

## Built With

* Dropwizard - Bla bla bla
* Maven - Maybe
* Atom - ergaerga

 

## Authors

* **Billie Thompson** - *Initial work* - [PurpleBooth](https://github.com/PurpleBooth)

See also the list of [contributors](https://github.com/your/project/contributors) who participated in this project.

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

## Acknowledgments

* Hat tip to anyone who's code was used
* Inspiration
* etc
