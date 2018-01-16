# rEFInd theme Regular-Black

A simplistic clean and minimal theme for rEFInd


![Screenshot 01](https://i.imgur.com/o0woNwY.png)
**press F10 to take screenshot


### Installation:

1. Clone git repository to your $HOME directory.
   ```
   git clone https://github.com/htower/refind-theme-regular-black.git
   ```

2. Locate refind directory under EFI partition. For most Linux based system is commonly `/boot/efi/EFI/refind/`. Copy theme directory to it.

   **Important:** Delete older installed versions of this theme before you proceed any further.

   ```
   sudo rm -rf /boot/efi/EFI/refind/refind-theme-regular-black
   ```
   ```
   sudo cp -r refind-theme-regular-black /boot/efi/EFI/refind/
   ```
3. Remove unused directory.
   ```
   sudo rm -rf /boot/efi/EFI/refind/refind-theme-regular-black/{src,.git,.gitignore}
   ```

4. To adjust icon size and font size edit `theme.conf`.
   ```
   sudo nano /boot/efi/EFI/refind/refind-theme-regular-black/theme.conf
   ```

5. To enable the theme add `include refind-theme-regular-black/theme.conf` at the end of `refind.conf`.
   ```
   sudo nano /boot/efi/EFI/refind/refind.conf
   ```

### Contribute new icons:

0. fork this repository on github and then git clone your fork of this repository in your Linux system

1. The icons must be in svg format to allow easy generation of icons at any scale, canvas size must have width and height 128 px for OS icons, or 48 px for tool icons. The actual icon in the svg file should roughly fit in a square with a side of 96 px or 20 px (for OS and tool icons, respectively). Inkscape is a good program to create and work with svg files.

2. Copy the svg file in /src/svg/big or /src/svg/small (depending on what is more appropriate) and rename them to be consistent with others.

3. Install inkskape and optipng in your linux system as they will be needed to process the icons by the next step.

4. run the script /src/render_bitmap.sh that will process the svg files and generate the png files at various sizes.

5. copy the png icons you generated from their /src/bitmap subfolder into the appropriate /icons subfolder for their size

6. commit your changes, upload to your fork and then open a PR.

**More information**

[rEFInd](http://www.rodsbooks.com/refind/) An official rEFInd website
