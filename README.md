# dev.goats.testing.xivlauncher
Flatpak build files

It's pretty simple. First install flatpak builder. You can even install it via flatpak (from flathub):
`flatpak install flathub org.flatpak.Builder`

Once that's done, clone this git repo. 

```
git clone https://github.com/rankynbass/dev.goats.testing.xivlauncher.git
mkdir -p flatpaks/xivlauncher
cd dev.goats.testing.xivlauncher
```
Then finish the build with

```
flatpak-builder --force-clean ../flatpaks/xivlauncher dev.goats.testing.xivlauncher.yml
```

Assuming there were no errors, you can install it with

```
flatpak-builder --user --install --force-clean ../flatpaks/xivlauncher dev.goats.testing.xivlauncher.yml
```

After that, you can run it just like the normal flatpak: `flatpak run dev.goats.testing.xivlauncher`. There will also be a .desktop file, but if you have XIVLauncher already installed, it might have the exact same name. For steam, you can set the launch options to `XL_SECRET_PROVIDER=FILE %command% run --parent-expose-pids --parent-share-pids --parent-pid=1 --branch=stable --arch=x86_64 --command=xivlauncher dev.goats.testing.xivlauncher`
