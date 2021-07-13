# AriaCore Architecture

AriaCore is a Ren'Py framework for creating complex, map-oriented visual novels. AriaCore is divided into a few main elements:

- Scenes
- Characters
  - Character Stats
  - Character Properties
  - Tell-Me-Abouts
- Augmentations
- Items
  - Recpies
- Effects
- Predicates
- Notifications

# Scenes

Vanilla ren'py games put all of the game's dialogue into the `script.rpy` file. In AriaCore, dialogue is divided into "Scenes." Each scene has its own file, located in the ./script/ folder.

In order to make a scene available in your game, it must be added to `scenes.rpy`. For example, if you have two scene files `./script/opening_scene.rpy` and `./script/my_scene.rpy`, your `scenes.rpy` will look something like this:

```py
init python in aria:
  scenes = {
    'opening_scene': {
      'text': 'Hello world!',
      'icon': None,
      'predicates': []
    },
    'my_scene': {
      'text': 'My Scene',
      'icon': None,
      'predicates': []
    },
  }
```

Scenes have a few properties:
- A **Title**: given by the `"text"` field in `scenes.rpy`.
- An **Icon**: given by the `"icon"` field in `scenes.rpy`. If you don't want to specify an icon for a scene, set the `"icon"` field to `None`.
- A set of **predicates**: These predicates decide when AriaCore will allow the user to access the scene. More detail on predicates will come later.
