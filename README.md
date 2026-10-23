# Flipbook with support for GIFs and videos overlayed onto a static PDF. 

If you created your pictorial in PowerPoint, this can automatically extract and place your media from the .pptx file.
Otherwise, you will have to manually prepare your animated media files and draw boxes for them (see below).

Remember to keep media short and well compressed (each page must not exceed 100MB of media or GitHub gets mad)

## Folder layout:
```
index.html
document.pdf
media.json	 (Made with the editor, see below)
media/		   (Can also be made with the editor if your pictorial is made in PowerPoint)
  mediafile1.mp4
  mediafile2.gif
```

## Adding media from PowerPoint
1. Export your pictorial PDF as `document.pdf`
2. Create a folder with `index.html` and `document.pdf`
3. From that folder, start a local web server (requires Python): `python -m http.server 8000`
4. In a browser, open `http://localhost:8000/?edit`, click **Import .pptx...**, and choose the same file you used to make the pdf
5. Click **Download media files (.zip)** and unzip in the folder with `index.html` and `document.pdf`
6. Click **Download media.json** and put it in the same place
7. Check everything looks right on `http://localhost:8000`, then put everything in a repo and publish it as a GitHub page

## Adding media by hand
1. Export your pictorial PDF as `document.pdf`
2. Create a folder with `index.html`, `document.pdf` and a `media/` folder
3. Put all your animated media in the `media/` folder
4. From the folder containing `index.html`, start a local web server (requires Python): `python -m http.server 8000`
5. In a browser, open `http://localhost:8000/?edit`
6. Go to a page that should contain animated media and drag a box where it should sit. Type the path to the media file (e.g. `media/file.mp4`) or use **Pick file...**
7. When you've drawn all media boxes, click **Download media.json** and put it next to `index.html`
8. Check everything looks right on `http://localhost:8000`, then put everything in a repo and publish it as a GitHub page

## Labels
If your pictorial has labels over your animated media, these can also be shown. Rectangles, rounded rectangles and ellipses can be automatically extracted from .pptx and drawn over the animated media. Otherwise, you can drag a box like normal, and set its Type to **Redraw page area...**, to cover any part of your animated clips with the static pdf. 
