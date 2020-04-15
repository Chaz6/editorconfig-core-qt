# EditorConfig Qt5 Core

EditorConfig Qt5 core bindings. Does not require any external dependencies.

## EditorConfig Project

EditorConfig makes it easy to maintain the correct coding style when switching
between different text editors and between different projects.  The
EditorConfig project maintains a file format and plugins for various text
editors which allow this file format to be read and used by those editors.  For
information on the file format and supported text editors, see the
[EditorConfig website](http://editorconfig.org).

## How to use EditorConfig Qt5 Core

A basic example:

```c++
#include "EditorConfig.h"

QMap<QString, QString> settings = EditorConfig::getFileSettings("path/to/myfile.txt");
for(auto setting : settings.toStdMap()) {
    std::cout << qUtf8Printable(setting.first) << "=" << qUtf8Printable(setting.second) << std::endl;
}
```

## Development

This has been developed with Qt 5.14, however previous versions *may* work. This has only been tested on Windows.

1. Open `src/EditorConfig.pro` with Qt Creator
1. Build the release version (this will place the exe in a `build` directory in the root of this source code repository)
1. Using (cmd|powershell), navigate to the `build` directory
1. Execute `cmake ..`
1. Execute `ctest -C Release` (no clue why it needs the `-C Release`)
1. The majority of tests should pass
