# Curator

A personal visual archive for images, links, notes, quotes and a developing point of view. A responsive, Pinterest-inspired wall with collections, tags, search, favourites and a five-part taste journal.

## Use it

Open the website, choose **Add something**, and save an image, a link, a note or a quote. Drag several images onto the archive or paste a copied image outside an input. Create collections with the **+** beside Your collections. Open any card to edit or remove it.

The six supplied Instagram screenshots are attributed reference material from **@showcasejournals**. They are not the user's personal taste inventory. Journal prompts are adapted from that reference. Original screenshot content belongs to its respective owners.

## Data and privacy

Saves, image uploads and journal answers are stored in IndexedDB in the current browser. They are **not automatically synced**. Browser clearing, another browser, another domain or another device will not carry this data over. Use **Backup & GitHub → Export full backup** regularly. Backups include uploaded images and the supplied reference images. Import merges by entry ID and the most recent edit; deletion tombstones prevent a removed item from returning from an older backup.

**Optional GitHub backup:** Create a dedicated **private** data repository, then enter its owner/name and a fine-grained personal access token restricted to Contents read/write on that repository. The token is kept only in the page's memory and sent only to api.github.com. Save and load are manual. Saves merge the remote archive before committing, and conflicting writes are rejected. No credential is bundled with the website. Do not commit tokens to this repository. Public data repositories expose all notes and images; the app asks before writing to one.

The website source can be public while the data repository remains private. GitHub Pages is a public website in the ordinary GitHub Free configuration; do not place private archive.json files in a public website repository. The app does not auto-load an archive.json from its source repository.

## Run locally

Requires Python 3 and optionally Node.js for syntax checks.

```sh
python -m http.server 8080
```

Visit http://localhost:8080. If Node is available:

```sh
npm run check
```

No build step, package installation, backend or API key is required. Google Fonts supplies optional typography with local fallbacks. Remote image links contact their image host when displayed; uploaded files stay in browser storage until explicitly backed up to GitHub.

## Publish on GitHub Pages

In this repository's **Settings → Pages**, choose **Deploy from a branch**, select **main**, **/(root)** and save. The relative asset paths support project Pages URLs. No workflow permissions or dependencies are needed.

## Files

- `index.html` — accessible app shell and dialogs
- `style.css` — responsive layout and styles
- `app.js` — storage, CRUD, filtering, journal, import/export and optional GitHub backup
- `seed.js` — clearly labelled initial references and journal prompts
- `assets/` — the six user-provided screenshots

The `.openai/hosting.json` file is used only by the workspace preview. GitHub Pages ignores it.
