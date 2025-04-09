# OpenWeatherMap-API
API to download and analyze weather data in Qt. Can be used as a library in other projects or standalone.

## Usage
- Copy your OpenWeatherMap API-Key into $PWD/bin as apikey.txt (TODO: implement QSettings)
- Run as single Project with owm-api.pro
- Or include this API into another qt project as submodule and include the .pri file
- add as git submodule: `git submodule add -b develop https://github.com/REDDY50N/OpenWeatherMap-API.git libs/owm-lib`

## OWM API Key

add your api key to your environment vars .i.e. in ~/.profile
`export OWM_API_KEY="12344567889011121314"`

## Version

change `VERSION` file

## Dependencies
- Qt 5.15.15
- Libraries `<sudo apt install mesa-common-dev libglu1-mesa-dev`

**Note:**
This lib is compatible with Qt5 and Qt6 using cmake: https://doc.qt.io/qt-6/cmake-qt5-and-qt6-compatibility.html