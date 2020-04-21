#M4L Good Practices



## Patcher structure

Whenever possible encapsulate objects or use abstractions. Encapsulations/abstractions represent features or functionalities within a patch.

**subpatch(encapsulate) vs abstractions**

If some functionality will only be **used once** a **subpatch** will be enough.
On the other hand, if the functionality is **used many times** in the same patch, or its **reusable**, it is better to use an **abstraction**.

Use *Edit -> Encapsulate* to encapsulate the selected the objects.

Abstractions saved in the Max Search Path can be browsed by the File Browser system. In the Inspector Window you can set its description, tags and other data to be used by the browser system.

### DOs

- The patch must be organised in a way that the data flow is easy to follow.

- Objects must be grouped in "areas" easy to identify at a glance.

- Use Presentation Mode to provide a user interface. To make sure the patch opens in presentation open the Inspector Window and set Open in presentation to true.

- Add hints to abstractions.

- Use comments (but don't repeat the max documentation).

- Remove unused objects.

- Name abstractions using project name as a prefix and a dot. ex: project.abstraction.

- Use styles, either the one of those provided in Max or your custom one.

### DONTs
- Don't overlap connections. Doing so result in clean patches at first sight, but makes difficult to trace individual connections.
- Don't use more than needed sends/receives. Use to many makes very difficult to follow the patch data flow.


## Max Concepts

### Global

- Max uses a global namespace so data can be shared across patches.

- Prepend --- for `send`, `buffer`, `coll` objects to be local. ex: `send ---local`, `coll global`, `buffer ---local`

- Use View->Parameters to edit all parameters in the patch.

### Inspector Window

- Use the Inspector Window (⌘+i) to set object parameters.

- Set short, long and scripting names to something meaningful.

- Set Info text to show info when mouse hover a parameter.

### M4L

- Use `live.<ui-objects>` or values won't be stored/automated in the Live project.

- Enable *Parameter Visibility* in the Inspector Window to be automated from Live.

- Automation in Live work with integer values. When using floats the automation will use int values.

- MIDI mapping is only enabled for `live.<ui-objects>`.

### Distribution

- Freeze❄️ to ensure all required objects and files are collected with the m4l device. This is specially important for distribution.

- Set Initial Value(s) in the Inspector to those objects that must provide a default value when the device is used for first time in a Live project.

- Provide presets to share and showcase the device.
