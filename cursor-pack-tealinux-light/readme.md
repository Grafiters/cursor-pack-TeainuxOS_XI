## TEA CURSORS PACK

![](../update.PNG)

x-cursor theme ini terinspirasi dari cursor pack Captaine Cursors
-> (https://github.com/ChrisP4/captain-frank-cursors/tree/master/src/svg)
semua resource yang ada dibuat denga menggunakan ```Inkscape```

## Installation
untuk menginstall Tea Cursors Pack ini cukup mudah hanya perlu mengcopy cursors theme ini ke dalam directory ./icons
```
cp -pr dist/ ~/icons/Tea-Cursors-Light
```

atau ke directory /usr/share/icons/Tea-Cursors-Light

```
cp -pr dist/ /usr/share/icons/Tea-Cursor-Light
```

setelah itu coba di switch dengan menggunakan desktop tool atau dengan menggunakan terminal

pertama
```
sudo update-alternatives --install /usr/share/icons/default/index.theme x-cursor-theme /usr/share/icons/Tea-Cursor-Light/cursor.theme 65
```
atau
```
gsettings set org.gnome.desktop.interface cursor-theme "Tea-Cursor-Light" & sudo ln -fs /usr/share/icons/Tea-Cursor-Light/cursor.theme /etc/alternatives/x-cursor-theme
```
setelah itu tinggal di update dengan
```
sudo update-alternatives --config x-cursor-theme
```
kemudian edit default yang berada di `/etc/alternatives/x-cursor-theme` ubah isinya menjadi `Inherits=Tea-Cursor-Light`

setelah itu jalankan `sudo reboot`

## Build From Source
apabila anda ingin mengganti atau mengedit cursor ini , anda bisa compile cursor sendiri dengan source yang ada
pertama edit source `.svg` yang berlokasi di `src/svg`
setelah itu jalan kan
```
sh build.sh
```
semua source yang berformat `.svg` akan tergenerate dengan menggunakan pixmaps dan appropriate alliases.
semua hasi generate tadi akan secara otomatis berada di `dist/`.

## Error
Apabila terjadi error saat proses generate yang bertuliskan
```
unknown cursor config
```
error tersebut karena file yang berada pada `/config` kosong atau file yang digunakan untuk config cursor tidak sama dengan source cursor.
dan usahakan dalam generate cursor ukuran `DPI` gambar tidak ada yang menggunakan ukuran semisal `96,22 dpi` ukuran tersebut sangat tidak dianjurkan karna file tersebut tidak di anggap oleh generator `xcursorgen` usahakan ukuran display adalah ukuran fix sebagai contoh `96 dpi` / `120 dpi`