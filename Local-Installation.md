Testing has been done only on Python 3.7 and 3.8 on Linux and Windows. Dependencies must be installed by running:

```shell
pip install -r requirements.txt
```

If there are issues installing dependencies try:

```shell
pip install -r requirements.txt --ignore-installed
```

To run the script in an interactive terminal run:

```shell
python plex_meta_manager.py
```

### Commands

| Name | Shell Command | Environmental<br>Variable | Allowed Values | Default Value |
| :--- | :--- | :--- | :--- | :--- |
| [Config](#config) | `-c` or `--config` | `PMM_CONFIG` | Path to YAML config file | `config/config.yml` alongside<br>`plex_meta_manager.py` |
| [Time to Run](#time-to-run) | `-t` or `--time` | `PMM_TIME` | comma-separated list of times to update each day<br>**Format:** HH:MM | `03:00` |
| [Run](#run) | `-r` or `--run` | `PMM_RUN` | Run without the scheduler | `False` |
| [Run Tests](#run-tests) | `-rt`, `--tests`, or `--run-tests` | `PMM_TEST` | Run in debug mode with only collections that have `test: true` | `False` |
| [Run Collections Only](#collections-only) | `-co` or `--collections-only` | `PMM_COLLECTIONS_ONLY` | Process only collections during the run | `False` |
| [Run Libraries Only](#libraries-only) | `-lo` or `--libraries-only` | `PMM_LIBRARIES_ONLY` | Process everything but collections during the run | `False` |
| [Run Collections](#run-collections) | `-rc` or `--run-collections` | `PMM_COLLECTIONS` | comma-separated list of collection names to process | All Collections |
| [Run Libraries](#run-libraries) | `-rl` or `--run-libraries` | `PMM_LIBRARIES` | comma-separated list of library names to process | All libraries |
| [Resume Run](#resume-run) | `-re` or `--resume` | `PMM_RESUME` | Name of the Collection you want to resume the run at | ` ` |
| [No Countdown](#no-countdown) | `-nc` or `--no-countdown` | `PMM_NO_COUNTDOWN` | Run without displaying the countdown | `False` |
| [No Missing](#no-missing) | `-nm` or `--no-missing` | `PMM_NO_MISSING` | Run without any of the missing movie/show functions | `False` |
| [Divider Character](#divider-character--screen-width) | `-d` or `--divider` | `PMM_DIVIDER` | Character that divides the sections | `=` |
| [Screen Width](#divider-character--screen-width) | `-w` or `--width` | `PMM_WIDTH` | Integer between 90 and 300 | `100` |

* Environmental Variable values are used over Shell Command values 

## Config
To choose the location of the YAML config file use the `--config` option

```shell
python plex_meta_manager.py --config <path_to_config>
```

## Time to Run
To choose the times when the script will run each day use a comma-separated list with the `--time` option

```shell
python plex_meta_manager.py --config /configs/config.yml --time 22:00,03:00
```

## Run
To just run the script without having it continuously run use the `--run` option

```shell
python plex_meta_manager.py --config /configs/config.yml --run
```

## Run Tests
To run the script in debug mode while only running collections that have `test: true` use the `--run-tests` option

```shell
python plex_meta_manager.py --config /configs/config.yml --run-tests
```

## Collections Only
To have the script run only collections and not any library operations use the `--collections-only` option

```shell
python plex_meta_manager.py --config /configs/config.yml --collections-only
```

## Libraries Only
To have the script run only library operations and not any collections use the `--libraries-only` option

```shell
python plex_meta_manager.py --config /configs/config.yml --libraries-only
```

## Run Collections
To have the script run only using the collections in the comma-separated list use the `--run-collections` option

```shell
python plex_meta_manager.py --config /configs/config.yml --run-collections "Harry Potter, Star Wars"
```

## Run Libraries
To have the script run only the libraries in the comma-separated list use the `--run-libraries` option

```shell
python plex_meta_manager.py --config /configs/config.yml --run-libraries "TV Shows"
```

## Resume Run
To have the script resume a run from a specific collection use the `--resume` option

```shell
python plex_meta_manager.py --config /configs/config.yml --resume "Star Wars"
```

## No Countdown 
To have the script run without displaying a countdown use the `--no-countdown` option

```shell
python plex_meta_manager.py --config /configs/config.yml --no-countdown
```

## No Missing 
To have the script run without any of the missing movie/show functions use the `--no-missing` option

```shell
python plex_meta_manager.py --config /configs/config.yml --no-missing
```

## Divider Character & Screen Width
To change the terminal output divider character or width use `--divider` and `--width`

```shell
python plex_meta_manager.py --divider * --width 200
```