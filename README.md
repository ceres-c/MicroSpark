# µcode FI
Glitching microcode for fun and no profit. See the [paper](docs/MicroSpark.pdf).

## Repo Structure
```py
.
├── docs/          # PDF documents used for development
├── firmware/
│   ├── coreboot/  # Goes on the UP2 board, runs the victim
│   └── picocoder/ # Goes on the Pico, runs the glitcher
├── hardware/
│   ├── pico/      # Pico mod for PMBus message injection
│   └── UPSquared/ # UP2 board mod
└── notebooks/
    ├── imgs/              # Screenshots from previous campaigns
    ├── picocoder_client/  # Lib to connect to the Pico from laptop
    ├── base.ipynb         # Connect to pico/try simple glitches
    ├── plot_from_db.ipynb # Draw glitch campaign plots from db
    └── data_collector.py  # Collect glitch datapoints into a db
```

## Software Setup
```sh
git clone --recurse-submodules https://github.com/ceres-c/MicroSpark.git
pip install matplotlib pyserial
```

You'll be asked for a git password when cloning the coreboot submodule. Just
press enter and skip those submodules: they're for different hardware.

### coreboot
This project requires the target board to run a custom version of coreboot.
After cloning the repo with `--recurse-submodules`, you'll find it in
`firmware/coreboot/`. You can also check it out [here](https://github.com/ceres-c/coreboot).

See `firmware/coreboot/README.md` for instructions on how to build with red
unlock enabled and flash the board.

## Hardware Setup
Both the Pico and UP2 board require hardware modifications. You can read more
about it in the paper.

### Pico
See `hardware/pico/README.md`

### UP2
See `hardware/UPSquared/README.md`

### Power supply
You'll need a Korad KA3005P power supply to power on and reset the UP2 board.
If you have another kind of programmable power supply, make changes in
`notebooks/picocoder_client/power_supply.py`.

## Usage
Glitch data is acquired through the `data_collector.py` script in the
`notebooks/` folder. See `notebooks/README.md` for instructions.

Plotting is done through `notebooks/plot_from_db.ipynb`.

## Citing
```
@inproceedings{cerutti_microspark_2026,
	title = {{MicroSpark}: {Testing} {Voltage} {Glitches} on {Intel} {Microcode}},
	url = {Paper=https://download.vusec.net/papers/microspark_uasc26.pdf Code=https://github.com/ceres-c/coreboot},
	booktitle = {{uASC}},
	author = {Cerutti, Federico and de Faveri Tron, Alvise and Giuffrida, Cristiano},
	month = feb,
	year = {2026},
	keywords = {class\_fi, proj\_ictprize, proj\_intersect, proj\_rescale, type\_conf, type\_paper},
}
```
