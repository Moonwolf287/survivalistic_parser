# Survivalistic Parser

## About

This script is used to automatically generate new database files for the Stardew Valley mod [Survivalistic](https://www.nexusmods.com/stardewvalley/mods/12179).

It lets you select any directory (for example your "Mods" folder) and automatically scans for all Json Assets to turn them into database files in the output directory.

## Usage

### Installer (Windows Only)

- Download the latest release [HERE](https://github.com/Moonwolf287/survivalistic_parser/releases/latest)
- Open the `.exe` file.
- Select your Stardew Valley/Mods folder
- After it is done you can find the new databases in the output folder next to the executable.

### Script

- Install python 3
- Install json5 package `pip install json5`
- Download the script
- Run the script `python survivalistic_parser.py`
- Select your Stardew Valley/Mods folder
- After it is done you can find the new databases in the output folder next to the script.

## Configuration

There are some configuration options inside the file `config.py` . You can edit them to configure handling of thirst for Food items.

```python
# How much thirst you recover from drinkable items
# Default: 60
DRINKABLE_THIRST_RECOVERY = 60

# Cooked food base thirst recovery
# Default: 10
COOKED_THIRST_RECOVERY = 10

# Cooked Foods that count as watery and give extra thirst recovery
# Default: ['Stew', 'Soup', 'Gumbo', 'Broth', 'Ramen']
WATERY_FOODS = ['Stew', 'Soup', 'Gumbo', 'Broth', 'Ramen']

# Watery cooked food thirst recovery
# Default: 30
COOKED_WATERY_THIRST_RECOVERY = 30

# List of keywords to count as potion
# Default: ['Potion', 'Elixir', 'Tincture', 'Concoction']
POTIONS = ['Potion', 'Elixir', 'Tincture', 'Concoction']

# Potion thirst recovery fixed value
# Default: 75
POTION_THIRST_RECOVERY = 75

# Add modifier to hunger value if positive
# This is applied AFTER HUNGER_MAX was taken into account e.g.:
#   Edibility = 150, Max = 100, Modifier = -20
#       Result = 80
# It will be checked against HUNGER_MAX again afterwards, so going over max value is not possible.
# Default: 0
HUNGER_POSITIVE_MODIFIER = 0

# Add modifier to hunger value if negative
# This is applied AFTER HUNGER_MIN was taken into account e.g.:
#   Edibility = -150, Min = -100, Modifier = 20
#       Result = -80
# It will be checked against HUNGER_MIN again afterwards, so going under min value is not possible.
# Default: 0
HUNGER_NEGATIVE_MODIFIER = 0

# Adjust max hunger that can be restored (<100)
# Default: 100
HUNGER_MAX = 70

# Adjust min hunger that can be taken by bad food (>-100)
# Default: -100
HUNGER_MIN = -100

# How much console output_adjusted you see (Possible values VERBOSE, DEBUG, INFO)
# Default: INFO
LOG_LEVEL = INFO
```

## Executable Creation

The executable was created with PyInstaller:  
`python -m PyInstaller -F -n "Survivalistic Parser" survivalistic_parser.py`
