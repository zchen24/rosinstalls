## Isolated Workspace Rosinstall Files

These rosinstall files are meant to be used in _isolated_ catkin underlays. 

To combine them:

```bash
wget URL | wstool merge -
```

To build them, use `catkin_make_isolated`.

## Workspaces

* [*barrett.rosinstall*](barrett.rosinstall) - For running hardware from Barrett Technologies
* [*orocos.rosinstall*](orocos.rosinstall) - For building the [orocos toolchain](orocos.org) from source
