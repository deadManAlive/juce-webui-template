# JUCE + WebUI Audio Plugin Template

## Build command

For example, building VST3 with Visual Studio 2022, configure with:

```
  cmake -Bbuild -G"Visual Studio 17 2022" --preset default
```
and build with:

```
  cmake --build build --target juce_webui_VST3 --config Release  
```

## TO DO

- [x] Integrate vcpkg
- [ ] Working webview2
- [ ] Working interface
