# Pitch decks (public)

These files are mirrored to [Skyocean-International/decks](https://github.com/Skyocean-International/decks)
so skyocean.io/commercial-pitch-deck can load the PDF in the browser. The page loads it from
`raw.githubusercontent.com/Skyocean-International/decks/main/commercial-pitch-deck.pdf`.

- **commercial-pitch-deck.pdf** — commercial deck (English). **Current: 18 slides, September 2026.**
  This one has no `.pptx`. It is authored as a Claude Design artifact and exported to PDF, so the
  editable source is the artifact, not a file in this folder. Edit the artifact, re-export, replace
  the PDF here.

The Spanish deck (`commercial-pitch-deck-es.pdf` and its `.pptx`) was retired on 13 September 2026.
It was last updated in June 2026, two content generations behind the English deck, and still carried
the retired yield range and wording. Its page, skyocean.io/commercial-pitch-deck-es/, was removed with it.

**Do not add plain-text extractions of a deck to this folder.** Two lived here
(`commercial-pages.txt`, `pitch-deck.txt`), both extracted in June 2026 from March 2026 decks, and
both stayed behind while the decks moved on. On 11 September 2026 an assistant read
`commercial-pages.txt`, took it for the live deck, and was about to report a list of problems that
had been fixed two months earlier: crypto vocabulary, gold as settlement, retail participation
offered as live, "Port Sudan under SAF control". None of that is in the current deck. A stale
extraction of a document is worse than no extraction, because it reads as authoritative. To read the
current deck, read the PDF.

## Workflow (single source of truth: this folder in skyocean-docs)

1. **Edit** — re-export the PDF from its Claude Design artifact and replace
   `commercial-pitch-deck.pdf` here.
2. **Commit in skyocean-docs** — `git add decks/` then `git commit -m "Update commercial deck"`.
3. **Push skyocean-docs** — `git push origin main` (so the private repo has the latest).
4. **Mirror to the public decks repo** — from the skyocean-docs root:
   `git subtree push --prefix=decks decks main`
5. **Clear the CDN caches** — `raw.githubusercontent.com` refreshes within a few minutes on its own.
   jsDelivr holds files longer, so purge it:
   `curl https://purge.jsdelivr.net/gh/Skyocean-International/decks@main/commercial-pitch-deck.pdf`
6. **Check** — fetch the raw URL above and compare its md5 with the local PDF.

The skyocean.io page itself is built and published by `internal/cpanel/deploy-toolchain/deploy-site.sh`
to Cloudflare Pages. It only needs a redeploy when the page HTML changes, not when the PDF does.
