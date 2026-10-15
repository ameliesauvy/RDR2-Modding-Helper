# Modding Helper
Modding Helper brings asset research, archive exploration, texture tools, and LML mod management into one interface. Search game resources by recognizable item names or hashes, inspect and export assets, compare texture compression against vanilla references, and find conflicts in your LML folder.

## Features

### Asset Search & Research

- Search the vanilla texture manifest by texture name, YTD, drawable, hash, and other indexed data.
- Look up in-game item names, shop items, appearance tokens, drawable filenames, and related textures.
- Use regular expressions and filter, sort, group, copy, or export results.
- Explore resources in vanilla RPF archives, including nested RPFs, and batch-export supported files.
- Inspect texture dimensions, mipmaps, compression formats, alpha information, and related assets.

### Texture Gallery & Audio Library

- Browse indexed textures and mod-library images through a thumbnail gallery, with cached previews and full-resolution viewing.
- Find textures by name or YTD, with base and `+hi` variants grouped where appropriate.
- Browse audio resources and AWC containers from game archives; preview supported streams and export them as MP3 or WAV.
- **Audio search is still a work in progress.**

### Texture Compression Tools

- Scan DDS, YTD, and supported YTD resources within modded RPF archives.
- Compare modded textures with vanilla references for compression family, sRGB/linear color space, dimensions, mipmaps, and alpha.
- Flag differences worth inspecting, including ambiguous reference matches, without automatically treating them as errors.
- Batch-recompress selected textures and rebuild supported resources, with backups and resumable jobs.
- Optionally resize oversized textures to a maximum of 1024 px while preserving aspect ratio.
- Use a reliable vanilla match when available, otherwise apply texture-role- and alpha-aware fallback rules.
- Preserve intended appearance, transparency needs, and color-space behavior rather than blindly forcing vanilla formats.

### LML Mod Library & Conflict Detection

- Scan the LML folder for YTD, YDD, YDR, YFT, DDS, XML, META, and other supported files.
- Read `mods.xml`, `install.xml`, `FileReplacement`, `StreamingFiles`, and `DataFile` entries.
- Identify conflicts by their actual in-game destination and show which mod wins or gets overridden.
- Detect missing references and files that exist but are not currently loaded.
- Generate basic `install.xml` files and export inventories or conflict reports to CSV.

### Creator Tools

- Batch-import supported resources while retaining directory structure.
- List and export all files referenced in a YMT file exported through Ultimate YMT Helper.
- Replace DDS textures in bulk using filename, swatch, and texture-role matching.

## Requirements

- **Windows**
- **NVIDIA Texture Tools Exporter** — required for DDS compression/processing workflows.
- **Microsoft .NET 10 Runtime (x64)** — required for archive and Rockstar-resource scanning, export, and import functionality.

You do **not** need to install CodeX separately; the app already includes the components it needs.

## Getting Started

Open the app and search for a texture, YTD, drawable, item, shop-item name, appearance token, archive resource, or hash. Depending on the results, you can filter, export, open assets in the Gallery, or continue into the texture, archive, and LML tools.

Settings, caches, logs, reports, and resumable compression jobs are stored in the `RDR2ManifestTool_UserData` folder beside the application.

## Important Notes on Texture Compression

**A texture flagged by the comparison tool is not automatically incorrect.** RDR2 itself uses BC1, BC3, BC4, BC5, BC6H, BC7, uncompressed formats, and different alpha and color-space configurations. Modded textures can also have legitimate requirements that differ from their vanilla equivalents.

The tool is intended to help you **investigate** possible problems, not rate or discredit other mod creators. Changing linear/sRGB interpretation or forcing a vanilla format without considering transparency can noticeably alter the appearance of a texture in-game.

## Credits & References

- **xuruthor** — *A Brief Guide to RDR2 Texture Compression*, a major reference for the compression workflow.
- The appearance-name database draws largely on my own ASI research, supplemented with information from RDR2Mods.com and Rockstar's official online catalogue.

## Feedback & Support

Questions, bug reports, feature requests, and suggestions are welcome in the **Modding Helper** channel on Discord.
