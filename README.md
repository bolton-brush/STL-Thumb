# STL Thumb

STL Thumb is a simple rust binary to generate thumbnails from STL Files in a fast and simple manner. It was originally designed as an internal project for the BFD9000 server to generate simple thumbnails for previews. We utilize WGPU under the hood, which supports any mesa/vulkan backend, including non-GPU backends for headless environments.

STL Thumb is extremely simple and lacking any extraneous features:

- No custom shaders
- No changing orientation without a recompile
- Only supports PNGs and WEBPs due to transparency
- Does support streaming in and out files by omitting the input and output flags

STL Thumb is built with nix and also provides an AppImage at the flake uri `#appimage`

## Usage

```
Headless WGPU STL Thumbnail Generator

Usage: stl-thumb [OPTIONS]

Options:
  -i, --input <INPUT>    Path to input STL file (Omitting reads from STDIN)
  -o, --output <OUTPUT>  Path to output image file (Omitting writes to STDOUT)
  -w, --width <WIDTH>    Width of the output thumbnail [default: 256]
      --height <HEIGHT>  Height of the output thumbnail [default: 256]
  -f, --format <FORMAT>  Target encoding compression format [default: png] [possible values: png, webp]
  -h, --help             Print help
  -V, --version          Print version
  ```
