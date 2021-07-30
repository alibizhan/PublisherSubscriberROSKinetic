# Publisher and Subscriber (C++) Ros Kinetic
#### Making a workspace
$ mkdir -p ~/catkin_ws/src
$ cd ~/catkin_ws/
$ catkin_make
#### catkin_make, Creates CmakeLists.txt file inside src folder
now we go to $ cd ~/catkin_ws/src and create the beginner_tutorials package
$ catkin_create_pkg beginner_tutorials std_msgs rospy roscpp

It creates the beginner_tutorials folder and it has a package.xml and a CmakeLists.tx in it, now open the package.xml file, if the package format is “2” then <package format="2"> and if there is a <run_depend> tag, cut <exec_depend> we need to change it because <run_depend> belongs to old version.

#### Now to write a publisher talker node:
$ roscd beginner_tutorials
$ mkdir -p src

We create the src/talker.cpp file in the beginner_tutorials directory and put the publisher's c++ codes in it.
We follow the same steps for the subscriber.

#### Create msg:

$ roscd beginner_tutorials
$ mkdir msg
$ echo "int64 num" > msg/Num.msg

#### Create srv:
$ roscd beginner_tutorials
$ mkdir srv
$ roscp rospy_tutorials AddTwoInts.srv srv/AddTwoInts.srv

#### Then we add the following lines in package.xml and CmakeLists.txt file.
generate_messages(DEPENDENCIES std_msgs)

findg_package(catkin REQUIRED COMPONENTS
roscpp
rospy
std_msgs
message_generation
genmsg
)

#### In your catkin workspace
$ roscd beginner_tutorials
$ cd ../..
$ catkin_make install
$ cd -

![](https://github.com/alibizhan/PublisherSubscriberROSKinetic/blob/master/Outputs/1.png?raw=true)


