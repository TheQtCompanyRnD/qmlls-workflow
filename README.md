# qmlls-workflow

This repo builds the standalone qmlls binaries, for use by LSP clients that want to download qmlls.
For documentation on qmlls itself, see [here](https://doc.qt.io/qt-6/qtqml-tooling-qmlls.html).

Standalone qmlls refers to a static build of qmlls that can be shipped independently from the Qt release cycle. The
standalone qmlls and the qmlls shipped with Qt offer more or less the same functionality, up to some differences:

| Feature | qmlls shipped with Qt | standalone qmlls | 
| --- | --- | --- |
| Can be downloaded from Github | ❌ | ✅
| Can be released outside of the Qt release schedule | ❌ | ✅
| Can be run without installing Qt | ❌ | ✅
| Is built from qtdeclarative's | release branch | dev branch |

## Supported platforms

| Platform | Is supported? | 
| --- | --- |
| macOS universal | ✅
| windows x64 | ⚠️ binary signing WIP
| windows arm64 | ⚠️ almost done
| linux x64 | ✅
| linux arm64 | ⚠️ almost done

## Download

### Download URLs
You can download the latest standalone qmlls from https://qtccache.qt.io/QMLLS/LatestRelease and all other releases
from https://github.com/TheQtCompanyRnD/qmlls-workflow/releases.

### Archive name
Release 0.6 and later name their archive as following:
* qmlls-windows-x64-X.Y.zip
* qmlls-windows-arm64-X.Y.zip
* qmlls-macos-universal-X.Y.zip
* qmlls-linux-x64-X.Y.zip
* qmlls-linux-arm64-X.Y.zip

Releases should happen every 1-3 months and nightly releases every week. Nightly releases follow a different
versioning pattern "year.weeknumber".