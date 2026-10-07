# 360 to Cube Map

Convert equirectangular 360 photos into cube map faces, in your browser. Nothing is uploaded. Built for photogrammetry (Reality Capture, Metashape, COLMAP) and Gaussian splatting workflows.

## Features

- Upload one or many 2:1 equirectangular images (select or drag and drop)
- Six square faces per image (px, nx, py, ny, pz, nz), face size 256 to 4096 px, PNG or JPEG
- Face overlap: 90° (no overlap) up to 120° field of view, with the focal length shown for each image
- View each face large and paint masks over things to exclude (people, tripod, sky)
- Mask export as transparent PNG (alpha) or separate black-and-white mask files
- Batch download as ZIP: individual folders (one per image) or one combined folder (suits Reality Capture)
- Per-image layout image (horizontal cross or strip)

## Use

Open `360-to-cube-map.html` in a browser, or host it with GitHub Pages (Settings → Pages → deploy from the `main` branch, root folder). The page is then at `https://YOUR-USERNAME.github.io/REPO-NAME/360-to-cube-map.html`.

The page loads [JSZip](https://stuk.github.io/jszip/) 3.10.1 from cdnjs for ZIP downloads, so it needs an internet connection the first time. Fonts are the system font stack.

## Conventions

- The middle of the panorama becomes the front face (−Z), with +Y up.
- Face order follows OpenGL / Three.js: px, nx, py, ny, pz, nz.
- Masks: white keeps, black is ignored. Rename mask files if your software expects a different pattern.
- Changing the overlap clears masks, because the faces show different content.
- With overlap above 90°, the layout image is not a seamless cross. Use the individual faces for reconstruction.
- A layout image is skipped if it would be too large for the browser canvas (for example a cross at 4096 px faces).

## Limitations

Sampling is bilinear and runs on the CPU in the browser, so very large batches at 4096 px are slow and memory-heavy. Convert in smaller batches if the tab runs out of memory.

## License

Released under the [MIT License](LICENSE). You're free to use, copy, modify and share this tool, but it comes with no warranty.
