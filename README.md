# STM32CUBEMX-VSCODE-CMAKE

[中文](https://duanyll.com/2024/03/01/STM32-CMake/)

This template repository contains a `CMakeLists.txt` and Visual Studio Code configuration for building STM32 projects with STM32CubeMX. The `CMakeLists.txt` loads config from `Makefile` generated by STM32CubeMX, providing most device-related parameters. Also utilizes CMake to generate Clangd and OpenOCD configs.

## Prequisties

Please install these tools and add them to `path`. On Windows, it is suggested to install them via Scoop.

- `gcc-arm-none-eabi`
- `openocd`
- `cmake`
- `llvm` (For `clangd` and `clang-format`)
- `ninja` (For faster build speed)

Install these software from st.com:

- STM32CubeMX
- STM32CubeProgrammer (For ST-LINK drivers and utilties)

Also install these VSCode extensions:

- `ms-vscode.cpptools`
- `llvm-vs-code-extensions.vscode-clangd`
- `ms-vscode.cmake-tools`
- `marus25.cortex-debug`

## Usage

1. Create the STM32CubeMX project, configure the device, and select `Makefile` in Project Manager > Project > Toolchain / IDE
2. Click "Generate Code" and open the project folder.
3. Put the `CMakeLists.txt` and `.vscode` folder beside the `ioc` file.
4. Open the project folder with VSCode.
5. Configure the CMake project with the CMakeTools extension. Select `[Unspecfied]` when prompted to select a kit.
6. Add custom options, source files and libraries into `CMakeLists.txt`. These changes will be preserved when regenerating project with STM32CubeMX.
7. To flash your device with ST-LINK, use the `Flash STM32` command in VSCode.
8. Debug your device in vscode with the `Debug STM32` debug profile.

Please notice that common `.gitignore` for C/C++ will exclude binary libraries, causing linking failure after pulling from GitHub. You can retrieve these libraries by regenerating the project with STM32CubeMX.