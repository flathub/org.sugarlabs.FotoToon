# FotoToon Activity Flatpak

FotoToon allows you to create everything from a simple “comic” strip to a long elaborate illustrated document. You will be able to import many kinds of images into the panes of your project and add text bubbles to help tell the story.

To know more refer https://github.com/sugarlabs/fototoon-activity

## How To Build

To build this run the following command in terminal

Install the latest version of BaseApp
```
flatpak -y --user install org.sugarlabs.BaseApp
```

```
git clone https://github.com/flathub/org.sugarlabs.FotoToon.git
cd org.sugarlabs.FotoToon
flatpak -y --user install org.gnome.{Platform,Sdk}//45
flatpak-builder --user --force-clean --install build org.sugarlabs.FotoToon.json
```

## Check For Updates

Install the flatpak external data checker
```
flatpak --user install org.flathub.flatpak-external-data-checker
```

Now to update every single module to the latest stable version use
```
cd org.sugarlabs.FotoToon
flatpak run --filesystem=$PWD org.flathub.flatpak-external-data-checker org.sugarlabs.FotoToon.json
```