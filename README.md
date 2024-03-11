# FotoToon Activity Flatpak

FotoToon allows you to create everything from a simple “comic” strip to a long elaborate illustrated document. You will be able to import many kinds of images into the panes of your project and add text bubbles to help tell the story.

To know more refer https://github.com/sugarlabs/fototoon-activity

## How To Build

To build this run the following command in terminal

```
git clone https://github.com/flathub/org.sugarlabs.FotoToon.git
cd org.sugarlabs.FotoToon
flatpak --user remote-add --if-not-exists flathub-beta https://flathub.org/beta-repo/flathub-beta.flatpakrepo
flatpak --user install flathub-beta org.gnome.{Platform,Sdk}//46beta
flatpak -y --user install org.sugarlabs.BaseApp//24.04
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