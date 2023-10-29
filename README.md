# CrealityPrint-flatpak
Flatpak manifest of CrealityPrint (WIP).

Most of the manifest logic is copied from the [Cura flatpak manifest](https://github.com/flathub/com.ultimaker.cura).

# How to build and install
To build, `flatpak` and `flatpak-builder` are required. Download them with your favourite package manager.

After flatpak is installed, install Freedesktop 23.08 runtime and SDK
```
flatpak install flathub org.freedesktop.Platform//23.08 org.freedesktop.Sdk//23.08
```
Verify the build using flatpak-builder
```
flatpak-builder build/ com.creality.crealityprint.yml
```
If building is successful, install the flatpak locally
```
flatpak-builder --user --install --force-clean build/ com.creality.crealityprint.yml
```
And run it
```
flatpak run com.creality.crealityprint
```
# WIP notes
## Unable to start flatpak
Currently, the flatpak cannot be started. When running it, an error is thrown from the `AppRun`:
```
/app/crealityprint/AppRun: error while loading shared libraries: libBasicKernel.so: object file has no loadable segments
```
## Building from source vs extracting AppImage?
This flatpak is build by extracting the AppImage, similar to the [Cura Flatpak](https://github.com/flathub/com.ultimaker.cura)
