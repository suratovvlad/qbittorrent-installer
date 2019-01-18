# Installer for qbittorrent (Dark Theme)

## Steps

### Arch Linux
1. Use `yaourt -S qbittorrent-dark-git`

### MacOS or other Linux Distro
Not supported offically yet

### Build steps for Windows

1. Install `msys2` and `mingw64` from `msys2` packages
2. Install from `msys2` repos x86_64 versions of: `qt5`, `boost`, `openssl`, `gcc`, `cmake`, `make`, `ninja`, etc
3. Get `libtorrent-rasterbar 1.0.11`, compile it using `cmake`
4. Clone repo `https://github.com/suratovvlad/qBittorrent`
5. Compile it with `cmake`:
	- Set `LibtorrentRasterbar_INCLUDE_DIR` and `LibtorrentRasterbar_LIBRARY` `cmake` variables using previous steps
	- Set `-DQT5=ON`, add `-lws2_32` to linker (`CMAKE_CXX_STANDART_LIBRARIES` and `CMAKE_C_STANDART_LIBRARIES`)
	- Generate `ninja` build files using `-G Ninja` (or set `QtCreator` for Ninja builds)
	- Build with `ninja`
6. Get the next libraries from `msys2/mingw64/bin`:
```
	- libboost_system-mt.dll
	- libbz2-1.dll
	- libeay32.dll
	- libfreetype-6.dll
	- libgcc_s_seh-1.dll
	- libglib-2.0-0.dll
	- libgraphite2.dll
	- libharfbuzz-0.dll
	- libiconv-2.dll
	- libicudt57.dll
	- libicuin57.dll
	- libicuuc57.dll
	- libintl-8.dll
	- libpcre-1.dll
	- libpcre16-0.dll
	- libpng16-16.dll
	- libstdc++-6.dll
	- libwinpthread-1.dll
	- Qt5Core.dll
	- Qt5Gui.dll
	- Qt5Network.dll
	- Qt5Widgets.dll
	- Qt5Xml.dll
	- ssleay32.dll
	- zlib1.dll
```
7. Get the:
```
	- libtorrent-rasterbar.dll
```
8. Get the next libraries from `msys2/mingw64/share/qt5/plugins`:
```
	- platforms/qminimal.dll
	- platforms/qwindows.dll
```
9. Get the next translations from `msys2/mingw64/share/qt5`:
```
	- translations/qt_ar.qm
	- translations/qt_ca.qm
	- translations/qt_cs.qm
	- translations/qt_da.qm
	- translations/qt_de.qm
	- translations/qt_en.qm
	- translations/qt_es.qm
	- translations/qt_fa.qm
	- translations/qt_fi.qm
	- translations/qt_fr.qm
 	- translations/qt_gl.qm
	- translations/qt_he.qm
	- translations/qt_hu.qm
	- translations/qt_it.qm
	- translations/qt_ja.qm
	- translations/qt_ko.qm
	- translations/qt_lt.qm
	- translations/qt_pl.qm
	- translations/qt_pt.qm
	- translations/qt_ru.qm
	- translations/qt_sk.qm
	- translations/qt_sl.qm
	- translations/qt_sv.qm
	- translations/qt_uk.qm
	- translations/qt_zh_CN.qm
	- translations/qt_zh_TW.qm
	- translations/qtbase_ca.qm
	- translations/qtbase_cs.qm
	- translations/qtbase_de.qm
	- translations/qtbase_en.qm
	- translations/qtbase_fi.qm
	- translations/qtbase_fr.qm
	- translations/qtbase_he.qm
	- translations/qtbase_hu.qm
	- translations/qtbase_it.qm
	- translations/qtbase_ja.qm
	- translations/qtbase_ko.qm
	- translations/qtbase_lv.qm
	- translations/qtbase_pl.qm
	- translations/qtbase_ru.qm
	- translations/qtbase_sk.qm
	- translations/qtbase_uk.qm
```
9. Clone this repo
10. Put above files into `packages\org.degreeme.dark.qbittorrent\data` (keep platforms and translations folders in data)
11. Start from `mingw64 console build_installer_mingw64.sh`
12. Wait for compiling
13. Install `qBittorrentDarkInstaller.exe` or use `silent_install_mingw64.sh` for silent installation
