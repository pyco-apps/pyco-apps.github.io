---
meta_title: 'Image Colorspace Converter - Getting Started'
description: 'Documentation for Image Colorspace Converter software.'
---
# Getting Started

## Installation

The software can be downloaded here: <https://gum.co/pycocs>.

You can extract the .zip and place it anywhere you want. The software
is self-contained and doesn't need to be "installed".

To launch it simply click on the `.exe` inside the directory.

_(you cannot move the `.exe` outside the directory to put it somewhere else)_

## Import files

You can simply drag & drop any supported file(s) or even just a folder.
You can also click on the folder icon to open files through your OS explorer.

!!! warning ""

    :material-alert: When dragging a folder all the files inside it **and** its 
    sub-directories will be added!

![Drag & Drop import demo](img/demo-import.gif)

To delete a file you can simply select it and press ++del++ or ++backspace++ .

## Set the IDT

The IDT (Input Device Transform) specifies the input file colorspace primaries,
white point and transfer-function.

!!! example ""

    For example` Utility-sRGB-Texture` specifies that the file has sRGB primaries with 
    the sRGB EOTF transfer function while `Utility-sRGB-Linear` specifies that the transfer function is Linear.

To apply an IDT to the desired files:

- Select one or multiple files in the list (shift+click)
- Select the desired IDT in the dropdown menu.
- Click on Apply to Selection / Apply to All (No selection is needed for this
  one)

![Change IDT demo](img/demo-idt.gif)

!!! tip ""

    You can also click & drag down/up to select multiple files quickly in the list.

## Change Output options

### Select the colorspace to convert file primaries to in the dropdown.

!!! tip ""

    If the IDT and Target Colorspace are the same no conversion will happen.

### Select your output format

!!! success "exr"

    The professional-grade image storage format of the motion picture industry to be used in your 3D applications for 
    input such as textures, HDRIs, etc but not for your final displayable-delivery-content.

!!! danger "jpg, png"

    Low dynamic range displayable file formats suitable for online-view , previews, thumbnails, etc.
    A Transfer-function / ODT is required to be applied.

### Select your bitdepth

_(output format dependent)_

!!! warning

    When converting HDRIs it is recommended to output a 32bit float file to not
    clip any values

### Pick your compression method

_(exr only)_

- **None:** No compression, for archive files mostly. Or if you need maximum
  reading speed.

- **PIZ:** (lossless) Same speed for decompression/compression. Best for
  scan-line based files.

- **Zip:** (lossless) faster decompression and slower compression than PIZ.
  Best for textures.

- **Zips:** (lossless) Same, but can be write/read faster in some software.

- **Dwaa:** (lossy) Produce very light files (default compression amount: 45)

- **Dwab:** (lossy) Same as above, but can generate faster result in some
  applications.

- **B44:** (lossy) Only for HALF-Float images. Best for real-time playback of
  image sequence.

Read more about this here: <https://www.exr-io.com/openexr-data-compression/>.

### Set the compression amount.

_(output format & compression method dependent)_

- **jpg:** 100 = Max Quality; 0 = Minimum quality, but light files
- **exr(dwaa/dwaab):** 0 means Max quality

### Select your output location option.

*Refer to the Functionalities page.*

## Start The Conversion

Click on the green "play" button in the toolbar to start converting.
When a file is converted, it will be removed from the list.
If you click on "Abort", the currently converted files will still be converted.

![conversion demo](img/demo-convert.gif)

## Examples

Importing a 3d render in `.exr`, rendered with ACEScg primaries and applying an
ODT for sharing on Internet:

* **IDT**: ACEScg ;

* **TargetColorSpace**: ACEScg ;

* **Output format**: .jpg ; **Compression**: 100 (max quality) ;

* **ODT**: sRGB(ACES)

---

Importing a albedo texture in `.exr` from Megascans (sRGB primaries) and
convert it to ACEScg:

* **IDT**: Utility - Linear- sRGB ;

* **TargetColorSpace**: ACEScg ;

* **Output format**: .exr; **BitDepth**: 16b Half-Float;  **Compression**: zip;



