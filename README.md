# IJACMI — website

Static site for the *International Journal of Advanced Computing and Machine
Intelligence*, published by WhiteField Academic Press, Jabalpur.

No build step, no dependencies, no hosting cost. Plain HTML and CSS.

---

## Files

| File | Purpose |
|---|---|
| `index.html` | Home — masthead, call band, publication record |
| `cfp.html` | Call for Papers, Volume 1 Issue 1 |
| `about.html` | Aims and scope, article types, publisher |
| `board.html` | Editorial board and advisory panel |
| `authors.html` | Manuscript requirements and submission |
| `review.html` | Peer review process, conflicts, appeals |
| `policies.html` | Charges, copyright, licensing, archiving |
| `archives.html` | Published issues |
| `contact.html` | Publisher and editorial office |
| `404.html` | Not-found page |
| `style.css` | All styling |
| `logo/` | Logo family and favicons |
| `CNAME` | Custom domain for GitHub Pages |
| `robots.txt`, `sitemap.xml` | Search engine directives |

Everything sits in the repository root. `logo/` is the only subfolder. Do not
move files into other folders — the links between pages are relative.

---

## Deploying to GitHub Pages

1. Create a public repository and upload every file, keeping `logo/` as a
   folder and everything else at the root.
2. **Settings → Pages → Source:** Deploy from a branch → `main` → `/ (root)`.
3. In GoDaddy DNS, first **delete any existing parked-page records** on `@` and
   `www`, then add:

   | Type | Name | Value |
   |---|---|---|
   | CNAME | www | `USERNAME.github.io` |
   | A | @ | 185.199.108.153 |
   | A | @ | 185.199.109.153 |
   | A | @ | 185.199.110.153 |
   | A | @ | 185.199.111.153 |

   Replace `USERNAME` with the GitHub account name.
4. Wait for DNS to propagate (30 minutes to a few hours), then return to
   **Settings → Pages** and tick **Enforce HTTPS**.

The `CNAME` file already contains `www.ijacmi.org`.

---

## Placeholders to fill

Placeholders appear in the page source as `<span class="ph">[...]</span>` and
render as small gold-highlighted tokens, so they are easy to spot in a browser.
Search the source for `class="ph"` to find them all.

### Blocking — needed before the site goes public

- **Publisher postal address and PIN** — `contact.html`, and the imprint line
- **`editor@ijacmi.org` and `submissions@ijacmi.org`** — every page that names
  an address
- **Board members' institutional emails** — `board.html`, five still missing
- **Board members' full postal addresses with PIN** — `board.html`; the ISSN
  National Centre of India asks for these
- **Publishing Manager's name** — `board.html`

### Needed before the call for papers goes out

- **Submission deadline and the three dates that follow** — `cfp.html`
- **Closing date in the gold call band** — `index.html`

### Fill when known

- **First issue month and year** — `index.html`, publication record
- **International board member** — `board.html`, one slot held open
- **Pranay Saraf's PIN code** — `board.html`
- **Telephone** — `contact.html`

---

## Editing

Every page is plain HTML with no templating. To change the navigation or the
footer, the same block has to be edited in all ten pages — a find-and-replace
across the folder is the quickest way.

Colours, type and spacing are all defined as custom properties at the top of
`style.css`. Changing `--oxblood` or `--brass` there updates the whole site.

---

## Things to keep true

The site states plainly that the journal holds no indexing in Scopus, Web of
Science or UGC-CARE. That statement appears on the home page, the call for
papers, and in the emails sent to the editorial board.

If indexing status changes, update it. If it does not, leave it as it stands.
The ISSN National Centre of India declines applications that display misleading
information about indexing, and can revoke an assignment later if it emerges.
More to the point, the honesty is the only real advantage a new journal has.
