<img alt="Liminala-logo" src="./assets/images/logo.png" style="margin-left:auto; margin-right:auto; display:block; width:200px;"/>

# Liminala

**Liminala** is a lightweight, browser-based metadata explorer and editor for images and audio. It lets you inspect, modify, and export hidden data layers directly within your browser — no servers, installs, or uploads required.

[**View Live Demo**](nqrlabs.com/Liminala/)

## Overview

Liminala reads and writes metadata across common media formats, including **JPEG, PNG, WebP, TIFF, MP3, FLAC, OGG, WAV,** and **M4A**.  
It provides a clear visual interface for examining embedded information such as EXIF, ID3, XMP, and textual chunks. You can edit existing fields, add custom entries, and save the modified file or export its metadata to a human-readable text file.

Every operation is handled locally using Web APIs for file access, parsing, and saving. Nothing is transmitted or stored remotely, making the process fully private and deterministic.

## Features

- **Cross-format support:** Reads metadata from multiple image and audio formats using format-specific parsers.  
- **Editable fields:** Modify or add new metadata entries across EXIF, ID3v2, XMP, and PNG text blocks.  
- **Category filtering:** A dropdown menu filters displayed fields by metadata family, such as `[EXIF]`, `[ID3v2]`, `[PNG-tEXt]`, `[Vorbis]`, or `[RIFF]`.  
- **Custom fields:** Add your own descriptive or hidden tags for creative or archival purposes.  
- **Save metadata as TXT:** Exports all visible metadata in a clean text format for documentation or puzzle design.  
- **Offline operation:** No internet connection required; everything runs in the browser.  
- **Human-readable feedback:** Status messages and structured layouts make metadata manipulation intuitive and transparent.  

## Technical Notes

### Processing Framework

Liminala uses specialized libraries for each format:

- `piexifjs` — reads and writes EXIF data in JPEGs.  
- `png-chunks-extract`, `png-chunks-encode`, and `png-chunk-text` — parse and rebuild PNG metadata and header chunks.  
- `exifreader` — extracts EXIF, XMP, IPTC, and ICC data from WebP and TIFF images.  
- `music-metadata-browser` — reads ID3, Vorbis, and RIFF tags from audio formats.  
- `browser-id3-writer` — writes ID3v2 frames for MP3 tag editing.

### Saving Behavior

- **Images:** Updated EXIF or PNG text data is embedded into a new file.  
- **Audio:** MP3 files are rewritten with updated ID3v2 tags.  
- **TXT Export:** Metadata is sorted by category and field name, then written as plain text using the format `Field: Value`.

## Intended Users

Liminala was created for artists, ARG designers, and digital storytellers who use metadata as a creative layer.  
It is equally useful to photographers, archivists, and developers who need a trustworthy tool for exploring and editing embedded media information without specialized software.

The tool encourages experimentation with the boundaries between visible and invisible data — the liminal space where structure becomes meaning.

## Usage

1. Open the app in your browser.  
2. Drag a file into the upload area or click to select one.  
3. Explore the detected metadata categories.  
4. Edit fields directly or add new ones.  
5. Filter the view by metadata family if needed.  
6. Save the modified file or export metadata to a `.txt` file.  

## License

MIT License — free for modification and use. Attribution appreciated if used publicly.

### Third-Party Components

Liminala includes the following open-source libraries, each distributed under the MIT License:

- [piexifjs](https://www.npmjs.com/package/piexifjs) © hMatoba  
- [png-chunks-extract](https://www.npmjs.com/package/png-chunks-extract) © Lovell  
- [png-chunks-encode](https://www.npmjs.com/package/png-chunks-encode) © Lovell  
- [png-chunk-text](https://www.npmjs.com/package/png-chunk-text) © Lovell  
- [music-metadata-browser](https://www.npmjs.com/package/music-metadata-browser) © Borewit  
- [browser-id3-writer](https://www.npmjs.com/package/browser-id3-writer) © Eric Vidal  
- [exifreader](https://www.npmjs.com/package/exifreader) © Jesper Palm  

All third-party software components are MIT-licensed and fully compatible with this project’s license.

## Credit

Created by **NQR** for creators, puzzlemakers, and curious thinkers who look for meaning in what hides beneath the surface.  
If you use *Liminala* in a project, ARG, or artwork, I’d love to hear about it.
