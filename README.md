# µcode FI

Glitching microcode for fun and no profit.

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

You'll be asked for password when cloning coreboot repo, just press enter and
skip those submodules.

## Hardware Setup

### Pico

See `hardware/pico/REEADME.md`

### UP2

See `hardware/UPSquared/README.md`
