# Cell Morphing

## Example

### Data

The segmentation can be done using masks, e.g. using GIMP. It then needs to be exported as a TIF image, with at least the following 3 pages:
- Raw histology image
- Segmentation image
- Group image

In GIMP, to apply the colour from the group layer to the black-white segmentation, see [here](https://graphicdesign.stackexchange.com/a/8943).

It also needs metadata about the image resolution. This can be added like this:
`exiftool -XResolution=2 -YResolution=2 <image_file>`

Due to an apparent [bug](https://gitlab.gnome.org/GNOME/gimp/-/issues/3740) in Windows 10, layered TIF images can crash Windows Explorer and make deleting/renaming/moving the file impossible. Therefore, the file is saved as example.tif_layered which can still be read by MATLAB but does not affect Windows.

The example image is obtained in MATLAB via `imread('coins.png')`, segmented as done in the "[Fill Holes in a Binary Image](https://www.mathworks.com/help/images/ref/imfill.html)" example, and the groups manually (arbitrarily) segmented in GIMP.

### Code

To execute `example.mlx`, the source directory `./src/` needs to be on the MATLAB path.

The paths in `example.mlx` assume you are in the same working directory as the script itself.
