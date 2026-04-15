# Lab 5

## Env variable fixes for updating URDF files for ROS2.
```bash
echo 'export HELLO_FLEET_PATH=$HOME/stretch_user' >> ~/.bashrc
echo 'export HELLO_FLEET_ID=stretch-se3-local' >> ~/.bashrc
source ~/.bashrc
```

## export_urdf.sh fixes.

Patch the `cp` line for `controller_calibration_default.yaml`:

```bash
cp `ros2 pkg prefix stretch_core`/share/stretch_core/config/controller_calibration_head_factory_default.yaml ./exported_urdf/
```
