# Pitch decks (public)

These files are mirrored to [Skyocean-International/decks](https://github.com/Skyocean-International/decks) and served via [jsDelivr](https://www.jsdelivr.com/) so skyocean.io/pitch-deck and skyocean.io/commercial-pitch-deck can load them in the browser (CORS-enabled).

- **commercial-pitch-deck.pdf** — commercial deck (English). **Current: 17 slides, 6 August 2026.**
  This one has no `.pptx`. It is authored as a Claude Design artifact and exported to PDF, so the
  editable source is the artifact, not a file in this folder. Edit the artifact, re-export, replace
  the PDF here.
- **pitch-deck.pptx** — full pitch deck (PowerPoint source)
- **commercial-pitch-deck-es.pptx** — commercial deck (Spanish / Latin America), June 2026, one
  content generation behind the English PDF
  - PDF: commercial-pitch-deck-es.pdf → served at https://skyocean.io/commercial-pitch-deck-es/  

**Do not add plain-text extractions of a deck to this folder.** Two lived here
(`commercial-pages.txt`, `pitch-deck.txt`), both extracted in June 2026 from March 2026 decks, and
both stayed behind while the decks moved on. On 11 September 2026 an assistant read
`commercial-pages.txt`, took it for the live deck, and was about to report a list of problems that
had been fixed two months earlier: crypto vocabulary, gold as settlement, retail participation
offered as live, "Port Sudan under SAF control". None of that is in the August deck. A stale
extraction of a document is worse than no extraction, because it reads as authoritative. To read the
current deck, read the PDF.

## Workflow (single source of truth: this folder in skyocean-docs)

1. **Edit here** — Replace or update the deck file(s) in this folder. For the English commercial
   deck that means re-exporting the PDF from its Design artifact; for the others, the `.pptx`.
2. **Commit in skyocean-docs** — `git add decks/` then `git commit -m "Update pitch deck(s)"`.
3. **Push skyocean-docs** — `git push origin main` (so the private repo has the latest).
4. **Mirror to public decks repo** — From skyocean-docs root:  
   `git subtree push --prefix=decks decks main`  
   This updates [Skyocean-International/decks](https://github.com/Skyocean-International/decks); jsDelivr will serve the new files (cache may take a few minutes).
5. **Re-sync cPanel** if you changed only the HTML in `private/cpanel/skyocean.io/`; the .pptx is loaded from the CDN, so no need to upload the file to cPanel.
