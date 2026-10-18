First follow then steps from [README.md](../README.md) in the repository root. Then install the packages from *requirements.txt* and continue the introduction in [README.dm](../README.md) in the root folder to run the code.

## Scripts description

The script [reader.py](reader.py) will automatically install the APK to the connected Oculus Quest and start program. By default it uses the APK delivered with the repository. If you decide to compile your own version of the app with the code from *app_source* folder, please adjust the `APK_path` argument when running `OculusReader.install` function.

Use script [install.py](install.py) to reinstall or uninstall the APK from the connected Oculus Quest.

## World-frame passthrough client

In the parent sim2real project, build/install `real_world/quest_teleop` and use
`OculusReader(pose_frame="world", APK_name="org.real2sim.questteleop")`. This selects
the dedicated `wE9ryWORLD` stream and launches the separate OpenXR passthrough app.
`get_snapshot()` returns an atomic pose/buttons snapshot, packet sequence, and
host monotonic receipt time; polling never refreshes that timestamp. The bundled
legacy APK remains head-relative. World mode requires an explicitly installed
new app and never installs the bundled legacy APK as a substitute.
