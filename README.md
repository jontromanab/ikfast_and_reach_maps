## Repository for ikfast files and reachability maps
==============

## How to test ikfast file

in the ikfast_Test, ikfastdemo is provided. Build the demo by

**g++ ikfastdemo.cpp -lstdc++ -llapack -o compute -lrt**

run **./compute**

=======================
### Test fk and ik
run an arbitary fk

**./compute fk 0.1 0.2 0.3 0.4 0.5 0.6**

see the results. It will show fk solution with Translation and Rotation of the ee link. Put them back in the ik to see the same fk results. An example result of fk:

Found fk solution for end frame: 

  Translation:  x: 1.009253  y: 0.347347  z: -0.375207  

     Rotation     0.208915   0.047396   -0.976785  
       Matrix:    0.902950   -0.392918   0.174058  
                  -0.375547   -0.918351   -0.124882  

 Euler angles: 
       Yaw:   -1.697957    (1st: rotation around vertical blue Z-axis in ROS Rviz) 
       Pitch: 1.981232  
       Roll:  0.174949  

  Quaternion:  -0.415666   0.657023   0.361611   -0.514568   
               -0.415666 + 0.657023i + 0.361611j - 0.514568k   (alternate convention) 

**./compute ik 1.009253 0.347347 -0.375207 -0.415666 0.657023 0.361611 -0.514568**


It will return couple of ik solutions. One of the results should be close to your provided fk


