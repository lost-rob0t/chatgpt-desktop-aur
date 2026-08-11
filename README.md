# chatgpt-desktop-aur

Arch Linux packaging for the official ChatGPT desktop app for Linux.

## Build

```sh
git clone https://github.com/lost-rob0t/chatgpt-desktop-aur.git
cd chatgpt-desktop-aur
makepkg -si
```

The package is built from OpenAI's official Linux RPM and installs the `chatgpt` launcher, desktop entry, icons, bundled application files, and upstream AppArmor profile.
