# pyfpdf-transparent

Add transparency support to [PyFPDF](https://github.com/reingart/pyfpdf).

You can set the alpha channel from 0 (fully transparent) to 1 (fully opaque). It applies to all elements (text, drawings, images).

Straight port of http://www.fpdf.org/en/script/script74.php

Example usage:

```python

from alphafpdf import AlphaFPDF


pdf = AlphaFPDF()

pdf.add_page()
pdf.set_line_width(1.5)

# draw opaque red square
pdf.set_fill_color(255,0,0)
pdf.rect(10,10,40,40,'DF')

# set alpha to semi-transparency
pdf.set_alpha(0.5)

# draw green square
pdf.set_fill_color(0,255,0)
pdf.rect(20,20,40,40,'DF')

# draw jpeg image
pdf.image('lena.jpg',30,30,40)

# restore full opacity
pdf.set_alpha(1)

# print name
pdf.set_font('Arial', '', 12);
pdf.text(46,68,'Lena');

pdf.output(name = 'example.pdf', dest = 'F')

```

View the result [here](https://github.com/blueCat1301/pyfpdf-transparent/blob/master/example.pdf)
