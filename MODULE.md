## Pixels Editor Modules

This is a simple guide to create your own modules for the app.

### File Structure
The structure of the app must be like this, all the modules at `app/modules/` and the `icon.ico` at the same path of the exe.
```
app/
        PixelsEditor.exe
        icon.ico
        /modules/
            module.py
```

### Module Structure
The module must have this:
 - def `self` that returns a object with the information.
   
   ```py
    def self():
            return {
                "name": "View Shape",
                "version": "1.0.0",
                "author": "danilppzz"
            }
   ```
 - def `load` to execute the module when people click it. the load def comes with image prop `PIL.Image` to manage it, and allways have to return `PIL.Image`
   
   ```py
    def load(image):
            img_np = np.array(image)
            inverted_image = 255 - img_np
            return Image.fromarray(inverted_image, 'RGBA')
   ```
