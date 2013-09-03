## Application-Specific rosinstall Files

These rosinstall files are meant to be used in the directory _outside_ of 
multiple Catkin isolated and non-isolated workspaces. These can be considered
"meta-workspaces" since they all create the structure for one or more workspaces.

They are meant to create the following structure:

```
.
├── underlay
│   ├── build
│   ├── devel
│   └── src
├── underlay_isolated
│   ├── build_isolated
│   ├── devel_isolated
│   ├── install_isolated
│   └── src
```

Once loading this meta-workspace, build it in the following manner:

```sh
unset CMAKE_PREFIX_PATH
source /opt/ros/$ROS_DISTRO/setup.sh
cd underlay_isolated
catkin_make_isolated --install
source install_isolated/setup.sh
cd underlay
catkin_make
source devel/setup.sh
```

To load them them into your meta-workspace:

```bash
curl https://raw.github.com/jhu-lcsr/rosinstalls/master/catkin/FILE.rosinstall | wstool merge -
```

### Workspaces

* [*lcsr_wam.rosinstall*](https://raw.github.com/jhu-lcsr/rosinstalls/master/applications/orocos_barrett.rosinstall) - Orocos-libbarrett integration packages 
