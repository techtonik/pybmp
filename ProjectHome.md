Bitmap loading and writing utilities in pure Python. Supports drawing many shapes and text. This project was created to add support for image drawing capabilities for Google Appengine.

To write text onto bitmaps, you first need to create proper python module with make\_font.py.

For example:
```
python make_font.py -f /usr/share/fonts/truetype/msttcorefonts/arialbd.ttf -s 12
```

The python code would look like this:

```
import bmp
import bmpfont_arialbd_12

img = bmp.BitMap( 500, 40, bmp.Color.TEAL.lighten() )
img.setFont(bmpfont_arialbd_12.font_data)
img.setPenColor( bmp.Color.BLUE )
img.drawText('abcdefghijklmnoprstuvxyz!@#$^%&^**()_}{\",.?<>', 10, 10)
img.drawLine( 0, 0, 10, 10)
  
# save the file
img.saveFile( "test.bmp" )
# or get the bitmap as string
bitmap = img.getBitmap()

```