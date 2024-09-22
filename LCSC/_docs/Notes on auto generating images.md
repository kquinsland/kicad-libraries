# Notes on auto generating images

Ideally, I'd have a script that takes a single `lcsc` part number and drives the import tool and then exports the images.
A `toml` file could live inside each library folder to list the individual parts for moar automation.

In any case, manually exporting the symbol and footprint can be done:

```shell
# PCB symbol
❯ kicad-cli sym export svg connectors.kicad_sym
Plotting symbol 'R-RJ45R08P-A004' to 'r-rj45r08p-a004.svg'

# PCB footprint
❯ kicad-cli fp export svg connectors.pretty
Loading footprint library
Plotting footprint 'RJ45-TH_R-RJ45R08P-A004' to 'RJ45-TH_R-RJ45R08P-A004.svg'
```

At present, 3d models are exported [but the KiCad tooling doesn't support rendering just the 3D model](https://gitlab.com/kicad/code/kicad/-/issues/3691).
With some work, you could create a PCB with just the single component on it and render that... which is what has been [common practice for a while now](https://hackaday.com/2024/03/11/share-your-projects-kicad-automations-and-pretty-renders/).

I might be able to use FreeCAD or similar to do a `step` -> `png` [conversion](https://forum.freecad.org/viewtopic.php?t=58071).
