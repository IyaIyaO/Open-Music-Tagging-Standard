# 🎧 Open Music Tagging Standard (OMTS)

The OMTS defines conventions for the **content structure and formatting** of music metadata (tags) in audio files to enable a consistent music experience - regardless of player or software.

The following conventions are in no way intended to restrict the artistic freedom of naming titles, albums, etc., but merely to define a consistent standard for metadata representation in audio files.

## 1. Title

- All UTF-8 characters are allowed
- Must be the clear title of the song
- The capitalization must correspond to the capitalization published by the artist
- Must contain a version supplement according to [point 8](#8-version) if available

> This title definition is not the definition for file names, for these you will find them in [this section](#10-additional-conventions).

**Examples:**

- ✅ `I Want to Hold Your Hand`
- ✅ `Who Needs Sleep Tonight (DJ Hell Remix)`

---

## 2. Artist

- The main artist is listed first
- All other artists are separated by a `;` and written after them, without spaces in between
- The artists are listed in order of importance or contribution
- No additions such as `feat.` or `ft.`

**Examples:**

- ✅ `Daft Punk`
- ✅ `Lady Gaga;Bradley Cooper`
- ❌ `Lady Gaga feat. Bradley Cooper`

---

## 3. Album

- All UTF-8 characters are allowed
- Must be the clear title of the album
- If the song is a single, the name of the album must end with `{album} - Single`
- If the album is an EP, the name of the album must end with `{album} - EP`
- Remixes may not be labeled in the album field - unless the release is a standalone remix single (in this case, the album name must end in `{title} - Single`, matching the title format)

**Examples:**

- ✅ `Let It Be`
- ✅ `Let It Be - Live`
- ✅ `Blinding Lights - Single`
- ✅ `Future Nostalgia - EP`
- ✅ `Beautiful People (Miss Monique Remix) - Single`

---

## 4. Albumartist

- The main artist of the album
- Only one artist
- No additions such as `feat.` or `ft.`

> This section is important for album sorting in music players.

**Example:**

- ✅ `Daft Punk`
- ❌ `Lady Gaga;Bradley Cooper`
- ❌ `Lady Gaga feat. Bradley Cooper`

---

## 5. Year

- The year in which the song was released for the first time
- The full year, no abbreviations
- If the track is a re-release or remaster, the original year should be used, unless the new version is substantially different

**Example:**

- ✅ `2025`
- ❌ `25`

---

## 6. Track (Track-Number)

- Must be in the format `X/Y` or `X`
- Optionally, the track number may have a leading Zero for single-digit numbers

> Leading zeros are recommended for consistency, especially for sorting in file explorers.

**Examples:**

- ✅ `2/7` or `02/07`
- ✅ `2` or `02`
- ❌ `2 of 7`

---

## 7. Genres

- Must be the clear name of a genre
- If there is more than one genre, these are listed separately with `;`
- The genres should be listed from left (higher priority) to right (lower priority)
- The specified genres should be taken from the [OMTS genres list](./omts-genres-list.md)

> For clear, uniform genres, it is advisable to take these from the [OMTS genres list](./omts-genres-list.md).

**Examples:**

- ✅ `Synthwave`
- ✅ `Dance/Electronic;House`
- ❌ `Dance/Electronic & Future Bass`

---

## 8. Version

- Must be the clear name of a version
- Versions are used in the title section, album section or in the file name
- Available version suffixes:
    - `Extended`: `{title} (Extended Mix)`
    - `Remix`: `{title} ({remix artist} Remix)`
    - `Acoustic`: `{title} (Acoustic)`
    - `Live`: `{title} (Live at Glastonbury 2022)`

---

## 9. Image

- JPEG is the preferred image format, but PNG is also permitted
- Avoid embedded text or watermarks where possible
- **Cover:**
    - The height must be equal to the width
    - Must have a mininum size of `600x600` (the standard is `640x640`)

---

## 10. Additional conventions

- **Encoding:**
    - All tags must be saved in **ID3v2.3 UTF-16** or **ID3v2.4 UTF-8** in MP3 files
    - Avoid legacy ID3v1 tagging for consistency
- **Filename:**
    - **Default:** `{main artist} - {title}.mp3`
    - **Extended:** `{main artist} - {title} (Extended Mix).mp3`
    - **Remix:** `{original main artist} - {title} ({remix artist} Remix).mp3`
    - **Live:** `{main artist} - {title} (Live at {place} {year})`

---

## Recommendations

We recommend tools such as `Mp3tag`, `Kid3`, `ExifTool (advanced)` or `eyeD3 (Python CLI)` for editing the tags.

## License

Open Music Tagging Standard (OMTS) is free to use under CC-BY 4.0. Suggestions and extensions welcome.
