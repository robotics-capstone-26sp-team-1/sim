# Lab 5

If you are using distrobox, create the container using:
```bash
distrobox assemble create
```

Then enter using:
```bash
distrobox enter --root lab5
```

## Don't run ROS 2 workspace setup with `sudo`.

```bash
curl -sL https://raw.githubusercontent.com/hello-robot/stretch_ros2/refs/heads/humble/stretch_simulation/stretch_create_ament_workspace.sh > /tmp/stretch_create_ament_workspace.sh && bash /tmp/stretch_create_ament_workspace.sh
```

After adding the workspace source to `.bashrc`, source it:

```bash
source ~/.bashrc
```

## Set up Mujoco simulation fixes.

Ignore `source not found` error. It won't matter since you will source after.


## Web Interface Control

### export_urdf.sh fixes.

Patch the `cp` line for `controller_calibration_default.yaml`:

```bash
cp `ros2 pkg prefix stretch_core`/share/stretch_core/config/controller_calibration_head_factory_default.yaml ./exported_urdf/
```

### Copy/rename the cert files.

```bash
cd ~/ament_ws/src/stretch_web_teleop/certificates
cp stretch-se3-local+6.pem server.crt
cp stretch-se3-local+6-key.pem server.key
```

Make sure to run all commands in a rooted environment (like natively on the computer or in a rooted container).
