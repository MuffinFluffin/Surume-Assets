# Surume-Assets

Remote assets for the [Surume](https://github.com/MuffinFluffin/Surume) PlayStation 2 emulator for iOS.

## Structure

```
music/          — Background music tracks (MP3/WAV)
sfx/            — UI sound effects (WAV)
catalog.json    — Live music catalog manifest
```

## Music

Menu music files downloaded on-demand by the app. Tracks listed in `catalog.json` are discovered automatically on app launch.

### Adding new tracks

1. Drop the audio file into `music/`.
2. Add an entry to `catalog.json`:
   ```json
   {
     "slug": "unique-slug",
     "title": "Track Title",
     "artist": "Artist Name",
     "filename": "filename.mp3"
   }
   ```
3. Commit and push. The app will pick up the new track on next launch.

### Current tracks

| Track | Artist | Source | License |
|-------|--------|--------|---------|
| Butterflow Menu Music Theme | Nomagician | Freesound.org | CC BY 4.0 |
| Video Game Menu Music | magmadiverrr | Freesound.org | CC0 1.0 |
| Piano Loops 188 Octave Down | josefpres | Freesound.org | CC0 1.0 |
| Piano Loops 198 Octave Down | josefpres | Freesound.org | CC0 1.0 |
| Piano Loops 201 Octave Short | josefpres | Freesound.org | CC0 1.0 |
| Piano Loops 207 Efect 2 Octave | josefpres | Freesound.org | CC0 1.0 |
| Sergio's Magic Dustbin | Kevin MacLeod | incompetech.com | CC BY 4.0 |
| Mesmerizing Galaxy | Kevin MacLeod | incompetech.com | CC BY 4.0 |
| Adventures in Adventureland | Kevin MacLeod | incompetech.com | CC BY 4.0 |

## SFX

UI click/navigation sounds. Auto-downloaded silently on first app launch.

| File | Source | License |
|------|--------|---------|
| sfx_confirm.wav | Christopherderp — Freesound | CC0 1.0 |
| sfx_navigate.wav | Foxfire- — Freesound | CC0 1.0 |
| sfx_back.wav | sfx_navigate reversed | CC0 1.0 |
| sfx_toggle.wav | mellau — Freesound | CC0 1.0 |
| sfx_error.wav | (placeholder) | — |

## catalog.json

The app fetches this file on every launch to discover new tracks without requiring an app update.

```json
{
  "tracks": [
    {
      "slug": "butterflow-menu-music-theme",
      "title": "Butterflow Menu Music Theme",
      "artist": "Nomagician",
      "filename": "butterflow-menu-music-theme.mp3"
    }
  ]
}
```

## License

Audio files retain their original licenses (CC BY 4.0, CC0 1.0, etc.) as noted above. This repository structure and tooling is GPL-3.0+.

## Neural (Core ML scalers — Sakura iOS)

Optional Real‑ESRGAN RRDB bundles for on-device download. Files:

- `neural/Sakura-RealSR_x2_tile128.zip`
- `neural/Sakura-RealSR_x2_tile256.zip`
- `neural/Sakura-RealSR_x4_tile128.zip`

CDN (same raw host as music manifests):

`https://raw.githubusercontent.com/MuffinFluffin/Shared-Assets/main/neural/<filename>.zip`

Weights lineage: xinntao/Real‑ESRGAN (BSD‑3‑Clause).

