# Easily create your own colormaps
Utility functions for working with colors in Python.

## Setup
If you don't have matplotlib and numpy installed with Python 3:
```shell
pip install -r requirements.txt
```

## Usage

1. Import what we need:
```python
import matplotlib.pyplot as plt
import color_utils
```

2. Define your colors with their hex codes (you can omit '#' and use 3 digit shorthand) in the order you wish them to appear:
```python
my_colors = ['#B2E4DF', '#C2C1E1']
```

3. Convert them to RGB values matplotlib can use (on [0, 1]):
```python
rgbs = color_utils.hex_to_rgb_color_list(my_colors)
```

4. Create your colormap:
```python
my_cmap = color_utils.blended_cmap(rgbs)
```

5. Visualize your colormap:
```python
cbar = color_utils.draw_cmap(my_cmap)
plt.show()
```

6. The colormap:
<img src="images/two_color_cmap.png?raw=true" align="center" width="450" alt="Two color colormap">

## Notes
You aren't limited to using just 2 colors; in fact, you can use as many as you wish:

```python
my_colors = ['#00F', '#B2E4DF', '#C2C1E1', 'C0C0C0', 'EEE', '000000']
rgbs = color_utils.hex_to_rgb_color_list(my_colors)

my_cmap = color_utils.blended_cmap(rgbs)

cbar = color_utils.draw_cmap(my_cmap)
plt.show()
```

<img src="images/blended_cmap.png?raw=true" align="center" width="450" alt="Multi-color colormap">
