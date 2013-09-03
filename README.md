LCSR rosinstalls
================

A collection of rosinstall files for quickly downloading LCSR ROS packages.

### Conventions

These rosinstall files assume that you're using wstool to manage ***multiple***
Catkin workspaces (subspaces): one for normal catkin packages, called `underlay`
and one for pure-CMake packages which provide package.xml files, called
`underlay_isolated`. 

In other words, your wstool workspace contains a structure like the following:

```sh
tree -L 2
```
```sh
.
├── underlay
│   ├── build
│   ├── devel
│   └── src
└── underlay_isolated
    ├── build_isolated
    ├── devel_isolated
    ├── install_isolated
    └── src
```

Once creating this workspace, you can build it in the following manner
(this will create a pair of chained Catkin subspaces):

```sh
unset CMAKE_PREFIX_PATH
source /opt/ros/$ROS_DISTRO/setup.sh
cd underlay_isolated
catkin_make_isolated --install
source install_isolated/setup.sh
cd ../underlay
catkin_make
source devel/setup.sh
```

To load any rosinstall files from this repository into your workspace:

```bash
curl https://raw.github.com/jhu-lcsr/rosinstalls/master/FILE.rosinstall | wstool merge -
```

### Sections

* [*applications*](applications) - Application-specific rosinstall files (ROS and non-ROS packages)
* [*isolated*](isolated) - Catkin isolated workspaces (non-ROS packages in `underlay_isolated`)
* [*catkin*](catkin) - Catkin normal workspaces (ROS packages in `underlay`)
* [*deprecated*](deprecated) - Nobody cares about these. *Ignore them.*
