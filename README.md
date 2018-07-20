 Udacity-RoboND-Project2-Pick-and-Place

Project Goals:

 1. Set Up Environment
 2. Explore forward kinematics with Kuka KR210 to learn more about the robot's geometry.
 3. Derive Modified DH parameters.
 4. Run Pick & Place in demo mode
 5. Perform kinematic analysis of robot and derive equations for individual joint angles.
 6. Write inverse kinematics code inside IK_server.py
 7. Make brief write up.

Provide a Writeup / README that includes all the rubric points and how you addressed each one. You can submit your writeup as markdown or pdf. Here is a template writeup for this project you can use as a guide and a starting point.  The writeup / README should include a statement and supporting figures / images that explain how each rubric item was addressed, and specifically where in the code each step was handled. 

Kinematic Analysis

<font color="red">
<strong>
Run the forward_kinematics demo and evaluate the kr210.urdf.xacro file to perform kinematic analysis of Kuka KR210 robot and derive its DH parameters.

Your writeup should contain a DH parameter table with proper notations and description about how you obtained the table. Make sure to use the modified DH parameters discussed in this lesson. Please add an annotated figure of the robot with proper link assignments and joint rotations (Example figure provided in the writeup template). It is strongly recommended that you use pen and paper to create this figure to get a better understanding of the robot kinematics.
</strong>

Insert KR210 graph ("zero configuration" - alll joint angles are assumed = 0.


Insert hand-drawn labeling of joints, joint axes, links, positive and x axes(common normals between <strong>z<sub>i-1</sub> z<sub>i</sub></strong>), and reference frame origins (intersection of x<sub>i</sub> and z<sub>i</sub>) on graph, add gripper frame
Insert hand-drawn labeling of each non-zero link lengths (a values), link offsets (d values) and alpha (z twist angle), q values
  a<sub>i-1</sub> = distance from z<sub>i-1</sub>-z<sub>i</sub> measured along x<sub>i-1</sub> axis
  d<sub>i</sub> = signed distance x<sub>i-1</sub>-xi meaured along the z<sub>i</sub> axis
  alphai = z<sub>i-1</sub> - zi measured along the x<sub>i-1</sub> axis according to the right hand rule
  thetai = angle between x<sub>i-1</sub> and xi measured about z<sub>i</sub> axis using right hand rule
    for i=2 there is a -90 degree constant offset between x<sub>1</sub> and x<sub>2</sub>.
    
  obtain a, d, and alphas from kr210.urdf.xacro file
Insert gripper frame, account for difference between gripper reference frame in URDF vs. DH parameters
 - rotate about z axis (180 degrees), then y axis (-90 degrees)

Insert hand drawn image of modified DH table with corresponding hand drawn calculations of each link

<strong>
Your writeup should contain individual transform matrices about each joint using the DH table and a homogeneous transform matrix from base_link to gripper_link using only the position and orientation of the gripper_link. These matrices can be created using any software of your choice or hand written. Also include an explanation on how you created these matrices.
 </strong>
Insert Translation matrixes
Insert Homogeneous transform between base link and gripper using just the end-effector pose (position + rotation)
Insert error correction

#########################################################################
#########################################################################
<strong>
Decouple Inverse Kinematics problem into Inverse Position Kinematics and inverse Orientation Kinematics; doing so derive the equations to calculate all individual joint angles.
 
Based on the geometric Inverse Kinematics method described here, breakdown the IK problem into Position and Orientation problems. Derive the equations for individual joint angles. Your writeup must contain details about the steps you took to arrive at those equations. Add figures where necessary. If any given joint has multiple solutions, select the best solution and provide explanation about your choice (Hint: Observe the active robot workspace in this project and the fact that some joints have physical limits).
</strong>
Insert equations for individual joint angles.

<strong>
Project Implementation
 
Fill in the IK_server.py file with properly commented python code for calculating Inverse Kinematics based on previously performed Kinematic Analysis. Your code must guide the robot to successfully complete 8/10 pick and place cycles. A screenshot of the completed pick and place process is included.
 
IK_server.py must contain properly commented code. The robot must track the planned trajectory and successfully complete pick and place operation. Your writeup must include explanation for the code and a discussion on the results, and a screenshot of the completed pick and place process.
</strong>

Insert code explanations
Insert discussion of results
Insert screenshot of completed process
