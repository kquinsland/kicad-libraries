# All the LCSC components that I use

Everything here was generated using the [`easyeda2kicad`](https://github.com/uPesy/easyeda2kicad.py) tool.

## Usage

I use [this cheap RJ45 connector (LCSC: `C385834`)](https://www.lcsc.com/product-detail/Ethernet-Connectors-Modular-Connectors-RJ45-RJ11_Ckmtw-Shenzhen-Cankemeng-R-RJ45R08P-A004_C385834.html) for simple projects.

Creating both the symbol / footprint / 3D model is as simple as running the following command:

```shell
❯ easyeda2kicad --full --lcsc_id=C385834 --output $PWD/connectors
-- easyeda2kicad.py v0.8.0 --
[INFO] Create connectors.pretty footprint folder in /home/karl/Projects/kicad/libraries/LCSC
[INFO] Create connectors.3dshapes 3D model folder in /home/karl/Projects/kicad/libraries/LCSC
[INFO] Create connectors.kicad_sym symbol lib in /home/karl/Projects/kicad/libraries/LCSC
[INFO] Created Kicad symbol for ID : C385834
       Symbol name : R-RJ45R08P-A004
       Library path : /home/karl/Projects/kicad/libraries/LCSC/connectors.kicad_sym
[INFO] Created Kicad footprint for ID: C385834
       Footprint name: RJ45-TH_R-RJ45R08P-A004
       Footprint path: /home/karl/Projects/kicad/libraries/LCSC/connectors.pretty/RJ45-TH_R-RJ45R08P-A004.kicad_mod
[INFO] Created 3D model for ID: C385834
       3D model name: RJ45-TH_L15.9-W15.1-H12.6
       3D model path (wrl): /home/karl/Projects/kicad/libraries/LCSC/connectors.3dshapes/RJ45-TH_L15.9-W15.1-H12.6.wrl
       3D model path (step): /home/karl/Projects/kicad/libraries/LCSC/connectors.3dshapes/RJ45-TH_L15.9-W15.1-H12.6.step
```

Note that the tool defaults to v6 format which is no longer current.
Fortunately, it's easy to update to the latest format:

```shell
❯ kicad-cli sym upgrade connectors.kicad_sym
Saving symbol library in updated format
```

I have some super crude notes on exporting images for the footprint/symbol/3D model in [`LCSC/_docs/Notes on auto generating images.md`](./_docs/Notes%20on%20auto%20generating%20images.md)
