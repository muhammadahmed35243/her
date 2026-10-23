# her

A small interactive birthday site: one `index.html`, no build step.

## Flow

1. **Garden** – touch the blossom; it falls to the bottom-left and flowers grow from there.
2. **Hello** – a short clip and a sealed envelope.
3. **Card** – "Happy Birthday" card with a dedicated-song player.
4. **Album** – a two-spread scrapbook (taped photos, stickers, film strip).
5. **Why you're special** – nine flip cards.
6. **Lantern** – pull the chain and the lantern lights up.
7. **Closing wish** – "Many Happy Returns": petals fall and a warm closing note appears while the song keeps playing; this is the last screen.

A big **Next** button is fixed to the bottom of every screen, and a chain of hearts follows the cursor (or a finger).

## Files

| Path | What it is |
| --- | --- |
| `index.html` | the whole site (HTML, CSS, JS) |
| `assets/song.mp3` | the dedicated song |
| `assets/kiss.mp4`, `assets/kiss.jpg` | hero clip and its poster frame |
| `assets/avatar.png` *(optional)* | his photo for the round avatar; a monogram shows until it exists |

## Make it personal

Everything editable is in the `CONFIG` block near the top of the `<script>` in `index.html`:

- `name`, `from` – his name and yours (also via the link: `index.html?name=Rahul&from=Priya`)
- `nickname`, `message`, `songNote` – the card page text
- `age` – big number on the notebook (empty shows "HBD")
- `photos` – `[["assets/p1.jpg", "caption"], ...]`; photo 1 is the polaroid, photos 2–5 fill page 2, the film strip shows all of them. Soft placeholders show until you add some.
- `pageTextL`, `pageTextR`, `bookMessage`, `loveNote`, `photoLabel`, `photoCaption` – album text
- `reasons` – the flip cards (nine fills the 3×3 grid; `{name}` is replaced)
- `lanternHint`, `finalNote` – the lantern screen text
- `closingTitle`, `closingNote` – the closing wish text
- `video`, `videoPoster`, `catGif` – hero media

`{name}` and `{from}` are replaced everywhere in the text fields.

## Run locally

Open `index.html` in a browser. To test seeking in the song, serve the folder instead (a server with Range support), for example `npx http-server`.

## Deploy

GitHub Pages: **Settings → Pages → Deploy from branch → `main` / root**. Every push to `main` triggers a new "pages build and deployment" run, so a change can take a minute or two to appear; hard-refresh (Ctrl+Shift+R) if you still see the old version.
