# Pitch decks (public)

These files are mirrored to [Skyocean-International/decks](https://github.com/Skyocean-International/decks) and served via [jsDelivr](https://www.jsdelivr.com/) so skyocean.io/pitch-deck and skyocean.io/commercial-pitch-deck can load them in the browser (CORS-enabled).

- **pitch-deck.pptx** — full pitch deck  
- **commercial-pitch-deck.pptx** — commercial (non-blockchain) deck  

## Workflow (single source of truth: this folder in skyocean-docs)

1. **Edit here** — Replace or update the `.pptx` file(s) in this folder.
2. **Commit in skyocean-docs** — `git add decks/` then `git commit -m "Update pitch deck(s)"`.
3. **Push skyocean-docs** — `git push origin main` (so the private repo has the latest).
4. **Mirror to public decks repo** — From skyocean-docs root:  
   `git subtree push --prefix=decks decks main`  
   This updates [Skyocean-International/decks](https://github.com/Skyocean-International/decks); jsDelivr will serve the new files (cache may take a few minutes).
5. **Re-sync cPanel** if you changed only the HTML in `private/cpanel/skyocean.io/`; the .pptx is loaded from the CDN, so no need to upload the file to cPanel.
