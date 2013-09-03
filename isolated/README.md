## Isolated Workspace rosinstall Files

These rosinstall files are meant to be used in _isolated_ catkin underlays. These are _plain_ cmake projects which cannot
be built in a "normal" catkin workspace, and must be built with `catkin_make_isolated --install`.

To load them them into your workspace:

```bash
curl https://raw.github.com/jhu-lcsr/rosinstalls/master/isolated/FILE.rosinstall | wstool merge -
```

### Workspaces

* [*barrett.rosinstall*](barrett.rosinstall) - For running hardware from Barrett Technologies
* [*orocos.rosinstall*](orocos.rosinstall) - For building the [orocos toolchain](orocos.org) from source
