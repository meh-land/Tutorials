# ROS Tutorial
I will add here the useful ROS commands that I need to use regularly but for some reason keep forgetting them.

# Create a ROS workspace
```bash
mkdir -p my_ws/src

cd my_ws

catkin_make
```
Then source `my_ws/devel/setup.bash`

# Create a ROS Package

```bash
cd my_ws/src

catkin_create_pkg my_pkg_name rospy [other dependencies go here]
```

An optional but useful step is to clean up the file `my_ws/src/my_pkg/package.xml`. Then you must build the package
```bash
cd my_ws

catkin_make
```


















