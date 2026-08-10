# Stimulus packaging (still image + audio → playable “video”)

How oral-item **attachments** are built for a hiring platform that only exposes **one media slot**—methodology and ops shape, not an asset dump.

Selection of what goes *into* the image/audio: [stimulus-selection.md](stimulus-selection.md).

---

## Product constraint (why “video” at all)

The item needs both:

1. a **scene image** (so the candidate instantly sees the situation), and  
2. **audio** (TTS stem / listening passage).

The runtime historically allowed **one attachment**. Putting image and audio in separately was not available—so the practical fix is to **mux a static image with the audio into a short MP4** and attach that single file.

This is **not** cinematic video: no camera motion requirement, no narrative edit. Frame-rate demand is minimal; the file is a **container for picture + sound**.

---

## Audio side (input)

- Source: **TTS**, US English orientation, about **0.9×** speed (see [stimulus-selection.md](stimulus-selection.md)).  
- Prepare and name audio files consistently before mux (e.g. stable item ids).

---

## Image side (input)

- One still that makes the **scenario legible** at a glance.  
- Not scored as “visual literacy”; it is scaffolding for the speaking task.

---

## Mux method (public shape)

Use a local encoder (e.g. **FFmpeg** on the PATH) to loop one image over the audio duration, encode a light video stream, and copy or re-encode audio as needed.

**Illustrative command shape** (paths are placeholders—not production directories):

```bash
ffmpeg -loop 1 -i scene.jpg -i stem.mp3 \
  -c:v libx264 -crf 23 -r 10 -pix_fmt yuv420p \
  -c:a copy -shortest -movflags +faststart \
  -y item.mp4
```

| Flag / choice | Intent |
| --- | --- |
| `-loop 1` + still `-i` | Hold one frame for the whole clip |
| `-r 10` (low fps) | Enough for a static picture; keeps size down |
| `-crf 23` + `yuv420p` | Ordinary compatibility / size tradeoff |
| `-shortest` | End when audio ends |
| `+faststart` | Better progressive play in browsers |

Ops goals: **acceptable picture + clear audio**, small enough for remote interview playback—not broadcast-quality motion video.

Batch work is typically scripted (e.g. PowerShell over paired `id.jpg` / `id.mp3` → `id.mp4`). Exact internal folder layouts stay private.

---

## What this is not

- Not a claim that oral scores depend on video-understanding models.  
- Not a substitute for motion-video listening exams.  
- Not publication of real item media or encoder presets beyond the shape above.

---

## One-line takeaway

> “Video” here means **one attachment slot** filled by **still + TTS audio**, muxed lightly so candidates see the scene and hear the stem together.
