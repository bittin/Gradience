# AdwCustomizer
![Screenshot of the main interface](https://github.com/ArtyIF/AdwCustomizer/raw/main/pictures/main_screenshot.png)

AdwCustomizer is a tool for customizing Libadwaita applications and the adw-gtk3 theme.

<details>
  <summary>More screenshots</summary>
  
  ![Screenshot of the customized interface](https://github.com/ArtyIF/AdwCustomizer/raw/main/pictures/customized_screenshot.png)
  
  ![Screenshot of proof that this actually works](https://github.com/ArtyIF/AdwCustomizer/raw/main/pictures/proof_of_work_screenshot.png)
</details>

## Building and Installing
1. Clone this repository `git clone https://github.com/ArtyIF/AdwCustomizer.git`
2. Open the project with GNOME Builder
3. Press the Build (hammer in the header bar) button
4. Press on the status panel and click "Export Bundle" to export the app as a Flatpak bundle
5. Install the bundle with `flatpak install <path to bundle>` or through a GUI application of your choice (like GNOME Software and KDE Discover)

> **WARNING**: The project currently uses the `master` version of `org.gnome.Platform` and depends on some `Adw` classes that are not yet available in the latest stable version of `org.gnome.Platform` (42 at the time of writing). Flathub only ships stable versions of packages, so make sure you have a Flatpak repository that ships the needed dependency versions before installing.

## Setup Tutorial

### Libadwaita applications
No additional setup is required for native Libadwaita applications.

For Flatpak Libadwaita applications, you need to override their permissions by:
- Running `sudo flatpak override --filesystem=xdg-config/gtk-4.0`
- Using [Flatseal](https://github.com/tchx84/Flatseal) and adding `xdg-config/gtk-4.0` to **Other files** in the **Filesystem** section of **All Applications**

### Vanilla GTK 4 applications
Use [this guide](https://github.com/lassekongo83/adw-gtk3/blob/main/gtk4.md) to theme vanilla GTK 4 applications.

### GTK 3 applications
- Install and apply the [adw-gtk3](https://github.com/lassekongo83/adw-gtk3#readme) theme (don't forget to install the Flatpak package!)
- For Flatpak applications, you need to override their permissions by:
  - Running `sudo flatpak override --filesystem=xdg-config/gtk-3.0`
  - Using [Flatseal](https://github.com/tchx84/Flatseal) and adding `xdg-config/gtk-3.0` to **Other files** in the **Filesystem** section of **All Applications**

## Roadmap
This tool is currently in early development, but it already has a plenty of features and is very usable. Below is the roadmap, where all the checked features are already implemented:

- [x] Ability to customize named colors, either with a color picker or with text
- [x] Explanations for some named colors
- [x] Partial preview of changed variables
- [x] Built-in presets for Adwaita and Adwaita Dark (based on default libadwaita colors)
- [x] Ability to apply changes to libadwaita, GTK4 (with extracted libadwaita theme) and GTK3 (with the adw-gtk3 theme) applications
- [x] Ability to load and create custom presets
- [x] Ability to view adw-gtk3's support of variables
- [ ] Ability to customize palette colors
- [ ] Ability to add custom CSS code
- [ ] Ability to normalize color variables to hexadecimal or `rgba(r, g, b, a)` format
- [ ] Full theme preview