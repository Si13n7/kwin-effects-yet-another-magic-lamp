# Yet Another Magic Lamp (Plasma 6.6+)

![Screenshot](doc/Screenshot.png)

[Demo](https://www.youtube.com/watch?v=BR4bUwFZDS8)

Yet Another Magic Lamp is a window minimization effect for KWin. Whenever a window
is minimized, it'll get sucked down into the dock/panel. Compared to the Magic Lamp
effect shipped with KWin, this effect features a smoother, more "curvy" animation,
improved multi-monitor support (including correct behavior when the panel is on a
secondary screen or positioned between displays), and more configuration options.

This project was originally created by [zzag](https://github.com/zzag/kwin-effects-yet-another-magic-lamp),
who maintained it through Plasma 5.27. Since the original repository has not been updated in
several years, this fork continues development independently, focusing exclusively on Wayland
under Plasma 6. X11 is no longer supported.

### Installation

#### Build from source

You will need the following dependencies to build this effect:
* CMake
* any C++20 enabled compiler
* Qt 6: Core, DBus, Gui, Widgets
* KWin (Plasma 6.6 or later)
* KDE Frameworks 6:
    - Config
    - ConfigWidgets
    - CoreAddons
    - Extra CMake Modules
    - KCMUtils
    - WindowSystem
* libdrm

On Arch Linux → Manjaro, EndeavourOS, Garuda Linux, CachyOS

```yaml
sudo pacman -S \
    base-devel \
    cmake \
    extra-cmake-modules \
    kwin \
    kconfig \
    kconfigwidgets \
    kcmutils \
    kcoreaddons \
    kwindowsystem \
    qt6-base \
    libdrm
```

On Fedora → Kinoite, Bazzite, Nobara

```yaml
sudo dnf install \
    cmake \
    extra-cmake-modules \
    kwin-devel \
    kf6-kconfig-devel \
    kf6-kconfigwidgets-devel \
    kf6-kcmutils-devel \
    kf6-kcoreaddons-devel \
    kf6-kwindowsystem-devel \
    qt6-qtbase-devel \
    libdrm-devel \
    libepoxy-devel
```

On openSUSE Tumbleweed

```yaml
sudo zypper install \
    gcc-c++ \
    cmake \
    kf6-extra-cmake-modules \
    kwin6-devel \
    kf6-kconfig-devel \
    kf6-kconfigwidgets-devel \
    kf6-kcmutils-devel \
    kf6-kcoreaddons-devel \
    kf6-kwindowsystem-devel \
    qt6-base-devel \
    qt6-declarative-devel \
    libdrm-devel \
    libepoxy-devel
```

On Debian → Kubuntu, KDE neon, MX Linux, Nitrux

> **Note:** This effect requires KWin 6.6 or later. Building on Debian-based distributions may
> fail if the KWin version available in the repositories does not meet this requirement.

```yaml
sudo apt install \
    build-essential \
    cmake \
    extra-cmake-modules \
    kwin-dev \
    libkf6config-dev \
    libkf6configwidgets-dev \
    libkf6coreaddons-dev \
    libkf6kcmutils-dev \
    libkf6windowsystem-dev \
    qt6-base-dev \
    libdrm-dev
```

After you installed all the required dependencies, you can build
the effect:

```yaml
git clone https://github.com/Si13n7/kwin-effects-yet-another-magic-lamp-reloaded.git
cd kwin-effects-yet-another-magic-lamp-reloaded
mkdir build && cd build
cmake .. \
    -DCMAKE_BUILD_TYPE=Release \
    -DCMAKE_INSTALL_PREFIX=/usr
make
sudo make install
```


#### Building the effect against older Plasma versions

If you want to build this effect against an older Plasma (5.x) release, checkout
the corresponding `Plasma/x.yz` branch, for example

```yaml
git clone https://github.com/zzag/kwin-effects-yet-another-magic-lamp.git
cd kwin-effects-yet-another-magic-lamp
git checkout Plasma/5.23
```


### Using the effect

Open **System Settings** and navigate to:

**Animations** → **Window minimize**

Select **"Yet Another Magic Lamp"** and click **Apply**.

> **Note:** After changing effect-specific settings (e.g. via the configuration
> dialog), the changes may not take effect immediately. As a temporary workaround,
> switch to a different minimize effect, click Apply, then switch back and click
> Apply again. This behavior will be improved in a future update.

### Contributing

Any help is welcome. If you have suggestions how to improve this effect(e.g.
different duration for each stage of the animation, etc), please create a new
issue. If you'd like to contribute by implementing some feature, make sure
you've run clang-format before creating a PR.
