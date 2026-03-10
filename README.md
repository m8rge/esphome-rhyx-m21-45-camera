# ESPHome RHYX M21-45 Camera Component

Patched `esp32_camera` external component for RHYX M21-45 camera modules.

## What it changes

- Uses `RGB565` capture mode instead of native JPEG
- Converts frames to JPEG in software (`frame2jpg`)
- Keeps compatibility with `esp32_camera_web_server` snapshot/stream endpoints

## Repository layout

- `esphome/components/esp32_camera/__init__.py`
- `esphome/components/esp32_camera/esp32_camera.cpp`
- `esphome/components/esp32_camera/esp32_camera.h`

## Usage in ESPHome YAML

```yaml
external_components:
  - source:
      type: git
      url: https://github.com/m8rge/esphome-rhyx-m21-45-camera.git
      ref: main
      path: esphome/components
    components: [esp32_camera]
```

Example camera web endpoints:

- Snapshot: `http://<device-ip>:8080/`
- Stream: `http://<device-ip>:8081/`
