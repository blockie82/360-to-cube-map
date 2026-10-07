# 360 to Cube Map

Convert equirectangular (2:1) 360° panoramas into six square cube-map faces, with optional masking to leave out people, tripods or sky.

Drop in one or many panoramas and each becomes six faces, ready to download per image or as a batch. The faces are suitable for photogrammetry and Gaussian splatting tools such as Reality Capture.

Everything runs in your browser. Photos are never uploaded anywhere.


## Screenshots

**1. Convert panoramas to cube faces.** Drop in one or many images. Each becomes six faces, with options for face size, overlap, format and layout.

<img width="1440" height="1080" alt="Screenshot 2026-10-07 232622" src="https://github.com/user-attachments/assets/13b97dd8-a2db-492f-b21e-24b58892bdc1" />

**2. Mask out anything you don't want.** Click a face and paint over people, tripods or sky. Masked areas are removed when you export.

<img width="1548" height="938" alt="Screenshot 2026-10-07 232927" src="https://github.com/user-attachments/assets/e1d97baa-2365-4eb8-863c-834cb03b84a5" />



## Quick start

1. Download the app. Either:
   - Select the green **Code** button, then **Download ZIP**, and unzip it; or
   - Open `360-to-cube-map.html` in this repository, select the **Download raw file** button (the download icon above the file), and save it.
2. Double-click `360-to-cube-map.html` to open it in Chrome, Edge, Firefox or Safari.

No install, server or Git knowledge is needed.

## Preparing your panoramas

- Use equirectangular images with a 2:1 shape, as exported by most 360 cameras.
- Several images can be converted in one go. Drop them all in together.
- If you plan to mask people out, set the face overlap first (see below).

## Using the app

1. **Add images.** Choose images or drop them onto the box. Each is converted to six faces automatically.
2. **Choose your settings.**
   - *Face size* sets the width and height of each square face in pixels.
   - *Face overlap* widens each face beyond 90° so neighbouring faces share image content. This helps photogrammetry and Gaussian splatting tools match features across face borders. Each card lists the field of view and focal length to enter in your software.
   - *Format* sets the file type of the exported faces.
   - *Layout image* sets the arrangement of the single combined image (for example a horizontal cross, 4×3).
   - *Mask export* sets how masked areas are saved (see below).
3. **Mask anything you want left out (optional).** Click any face to view it large, then paint over people, a tripod or the sky.
   - *Paint / Erase* edits the mask. *Undo* and *Clear face* are also available.
   - Left and right arrow keys switch between faces. Esc closes the view, or select **Done**.
   - Masked areas are removed on export: either made transparent (masked faces are saved as PNG) or written as separate black-and-white mask files named `name_px_mask.png`, where white keeps and black is ignored.
4. **Download.**
   - *Download faces (.zip)* and *Download layout image* are on each image's card.
   - *Download all faces – individual folders* gives one subfolder per image.
   - *Download all faces – one combined folder* puts every face in a single folder with unique names (`name_px`, `name_nx`...), which is what Reality Capture needs.

## Tips

- Set the overlap before you start masking. Changing it clears any masks you have painted.
- With overlap on, the layout image is no longer a seamless cross, so use the individual faces for reconstruction.
- Use the individual or combined folder download for large batches, rather than saving each image one at a time.

## Axis convention

The middle of each panorama becomes the front face (−Z) with +Y up. Face names follow the OpenGL / Three.js order: `px`, `nx`, `py`, `ny`, `pz`, `nz`.

## Known limitations

- Input must be equirectangular (2:1) images.
- Changing the overlap clears any masks.
- With overlap on, the layout image is not a seamless cross.

## Created with Claude

This tool was designed and written by [Claude](https://claude.ai), an AI assistant made by [Anthropic](https://www.anthropic.com), through a conversation with the repository owner. The owner directed the project and tested the result.

## Status

This project is shared as-is. It is not actively maintained and contributions (issues, pull requests) are not being accepted. You are free to copy the single HTML file and adapt it for your own use. It has no build step or dependencies.

Work on copies of your photos rather than your originals.


## License

Released under the [MIT License](LICENSE). You're free to use, copy, modify and share this tool, but it comes with no warranty.
