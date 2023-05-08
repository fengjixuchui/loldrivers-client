# LOLDrivers-client
A client for [LOLDrivers](https://github.com/magicsword-io/LOLDrivers) (Living Off The Land Drivers). Scan your computer for known vulnerable and known malicious Windows drivers.

## Usage
```
LOLDrivers-client.exe -m [MODE] [OPTIONS]

Modes:
    online    Download the newest driver set (default)
    local     Use a local drivers.json file (requires '-f')
    internal  Use the built-in driver set (can be outdated)

Options:
    -d Directory to scan for drivers (default: Windows Default)
    -f File path to 'drivers.json' for mode 'local'
    -t Number of threads to spawn (default: 20)
    -v Print verbose messages (default: false)
    -h Shows this text
```
## Installation
### Binaries
Download the prebuilt binaries [here](https://github.com/rtfmkiesel/loldrivers-client/releases).

## Build from source
```bash
git clone https://github.com/rtfmkiesel/loldrivers-client
cd loldrivers-client
wget -q "https://www.loldrivers.io/api/drivers.json" -O pkg/loldrivers/drivers.json
go mod tidy
go build -o LOLDrivers-client.exe -ldflags="-s -w" cli/loldrivers-client/loldrivers-client.go
```

# Contributing 
Improvements in the form of PRs are always welcome, especially as this was made during my first year of using Golang. 