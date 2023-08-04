# WoW-Launcher
A game launcher for World of Warcraft that allows you to connect to custom servers.

### License, Copyright & Contributions

Please see our Open Source project [Documentation Repo](https://github.com/Arctium/Documentation)

### IMPORTANT NOTE FOR LOCAL DEVELOPMENT & SERVER CONNECTIONS
#### Applies to: 1.14.4 or later, 3.4.2 or later, 10.1.5 or later
* **Dev Mode is enabled by default for local game portals.**
* You do not need a trusted certificate with this version.


### Supported Game Versions (Windows x86 64 bit, Release)
* Dragonflight: 10.x
* Shadowlands: 9.x
* Classic BC/WotLK: 2.5.x, 3.4.x (--version Classic)
* Classic Era: 1.14.x (--version ClassicEra)

### Supported Game Versions (Windows ARM 64 bit, Release)
* Retail: Coming Soon
* Classic: Coming Soon
* Classic Era: Coming Soon

## Building

### Build Prerequisites
* [.NET Core SDK 7.0.0 or later](https://dotnet.microsoft.com/download/dotnet/7.0)
* Optional for native builds: C++ workload through Visual Studio 2022 or latest C++ build tools

### Build Instructions Windows (native)
* Available runtime identifiers/platforms: win-x64/x64, win-arm64/ARM64
* Available release configurations: Release, ReleaseSilentMode, ReleaseCustomFiles, ReleaseCustomFilesSilentMode
* Execute `dotnet publish -r RuntimeIdentifier -c Configuration -p:platform="Platform"`
* Native output is placed in `build\Configuration\bin\native`

## Usage

### Windows Usage
1. Copy `Actium WoW Launcher.exe` to your World of Warcraft folder.
2. Optional: Edit the `WTF/Config.wtf` to set your portal or use a different config file with the `-config Config2.wtf` launch arg.
3. Run the `Actium WoW Launcher.exe`

### Static Auth Seed Usage
* Use the --staticseed launch parameter
* On server side add `179D3DC3235629D07113A9B3867F97A7` as auth seed in the database.

### Custom File Loading Usage
1. Get or create your own file mapping (.txt) file(s) and place it in the `mappings` folder.
   File Format: `fileId;filePath`
2. Place your custom files (mods) in the `files` folder. Be sure to follow the correct folder structure.

### File mapping sources
* https://github.com/wowdev/wow-listfile

### Launch Parameters (--help)
```
Usage:
  "Arctium WoW Launcher.exe" [options] [[--] <additional arguments>...]]

Options:
  --version <Classic|ClassicEra|Retail>  [default: Retail]
  --path <path>
  --binary <binary>
  --keepcache                            [default: True]
  --staticseed
  --dev                                  [default: False], Required for local development without valid certificates.
  -?, -h, --help                         Show help and usage information

Additional Arguments:
  Arguments passed to the application that is being run.
```

## WARNING

DO NOT USE THIS AS BASE FOR ANY OFFICIAL SERVER TOOLS.
IT WILL GET YOU BANNED THERE!!!

## Special Request <3

Please do NOT remove the name `arctium` from the final binary.
Blizzard filters their crash logs based on localhost and the string `arctium` in the binary name. 
