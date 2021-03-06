---
published: true
layout: default
title: Please title this page. (SuggestDeltas.html in FontForge)
---


After you have generated truetype instructions to grid fit a glyph it
might to useful to look at places where those instructions yield
questionable results. In truetype a pixel is turned on if the center
point of that pixel is within the curve. If the curve is extremely close
to the center point then results are questionable

1.  You might want it on the other side
2.  Another rasterizer might round things differently and place the
    curve on the wrong side.

![](img/QGDlg.png)So it might be helpful to have a command which would
search the glyph for places and pixelsizes where splines are close to
the center points of pixels.

TrueType has an instruction called DELTA which allows you to move points
only at certain pixelsizes.

The dialog opposite will check the glyph at pointsizes 7-40, 72, 80, ...
where the screen resolution is 100 for places where a spline comes
within .01 (in pixel units) of the center of a pixel.

![](img/QGList.png)The results will look like those at right. Clicking on an
entry will toggle whether that entry is open (and its children visible)
or not.

![](img/JustOutside.png)If you click on one of the bottom level entries then
fontforge will open a glyph view on that glyph, rasterize it at the
current pointsize and resolution, and indicate the offending pixel by
drawing a red box around it. As you can see, the pixel center point lies
almost exactly on the spline. The closest real point is the control
point \#8.

It is possible to reorder the list... depending on what is most
important. At right data are organized by glyph, size and point. It
might also be useful to see which points in a glyph are close to
problems.
