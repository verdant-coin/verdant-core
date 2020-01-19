# Verdant

Verdant is a cryptocurrency aimed at accessibility and adoption

## Build

### Linux

```bash
sudo apt update
sudo apt upgrade
sudo apt install aptitude build-essential git cmake
sudo aptitude install libboost-all-dev
git clone https://github.com/verdant-coin/verdant-core verdant
cd verdant
make -j
```
If the build fails with `c++: fatal error: Killed signal terminated program cc1plus` try running `make` again with a specified amount of cores: `make -j2`

### Windows

- Download the [Build Tools for Visual Studio 2019](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16=) installer
- Select C++ build tools, it automatically select the needed parts.
- Install Boost:
	- [Boost 64-bit](https://bintray.com/boostorg/release/download_file?file_path=1.69.0%2Fbinaries%2Fboost_1_69_0-msvc-14.1-64.exe)
	- [Boost 32-bit](https://bintray.com/boostorg/release/download_file?file_path=1.69.0%2Fbinaries%2Fboost_1_69_0-msvc-14.1-32.exe)
- Install OpenSSL:
	- [OpenSSL 64-bit](https://slproweb.com/download/Win64OpenSSL-1_1_1d.exe)
	- [OpenSSL 32-bit](https://slproweb.com/download/Win32OpenSSL-1_1_1d.exe)

- For 64-bit:
	- From the start menu, open x64 Native Tools Command Prompt for VS 2019.
	- `cd <verdant directory>`
	- `mkdir build`
	- `cd build`
	- `cmake -G "Visual Studio 16 2019" -A x64 .. -DBOOST_ROOT=C:/local/boost_1_69_0`
	- `MSBuild Verdant.sln /p:Configuration=Release /m` or `MSBuild src\cli.vcxproj /p:Configuration=Release /m`

- For 32-bit:
	- From the start menu, open x86 Native Tools Command Prompt for VS 2019.
	- `cd <your_turtlecoin_directory>`
	- `mkdir build`
	- `cd build`
	- `cmake -G "Visual Studio 16 2019" -A Win32 .. -DBOOST_ROOT=C:/local/boost_1_69_0`
	- `MSBuild Verdant.sln /p:Configuration=Release /p:Platform=Win32 /m`
	The binaries will be in the src/Release folder when you are complete.

	cd src
	cd Release
	TurtleCoind.exe --version


## Coin fundamentals

```
   Total Supply : 50 Million
         Ticker : VRDT
 Emission speed : 24 (50% released after 17 years)
     Block time : 45 seconds
	   P2P Port : 9012
	   RPC Port : 9013
	   Min. Fee : 0.05
 Address Prefix : Vrdt
```
