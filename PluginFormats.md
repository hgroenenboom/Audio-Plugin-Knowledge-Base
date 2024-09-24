# Plugin Formats

## Table of Contents
- [Table of Contents](#table-of-contents)
- [Checklist](#checklist)
- [VST3](#vst3)
  - [Threading](#threading)
- [AU / AUv3](#au--auv3)
  - [Threading](#threading-1)
- [How does a DAW identify plugins](#how-does-a-daw-identify-plugins)

## Checklist

1. For plugin formats other than VST3, support multithreading for state loading/saving and prepare to play.
2. Choose a final manufacturer code and plugin code that won’t conflict with existing plugins.

## VST3

### Threading

The VST3 plugin format processes all calls on the main thread, except for the audio callback. This behavior is defined by the VST3 standard.

## AU / AUv3

### Threading

In the AU/AUv3 format, certain calls can originate from background threads. This is particularly relevant for:
- setStateInformation
- getStateInformation
- prepareToPlay

To pass validation tools like auval or pluginval, ensure these functions are handled in a thread-safe manner.

## How does a DAW identify plugins

For accurate state restoration, DAWs need to reliably identify your plugin, even if it’s moved or updated. This is why the manufacturer and plugin codes are crucial—they serve as unique identifiers that must remain unchanged after the plugin is released to avoid breaking user projects. However, be aware that some DAWs may use additional parameters to identify your plugin.

The manufacturer code and plugin code are limited to four characters each, so take care to avoid conflicts with existing plugins. _TODO: How can we do that?_

Details:
- FL Studio identifies a plugin by its binary name as well

______
_We're always looking to expand and improve this resource. If you have any insights or additional information, your contributions are more than welcome!_
