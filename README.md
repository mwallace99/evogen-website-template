# EvoGen academic website template

A ready-to-fork academic website. Fork it, change five lines, switch it on, and you
have a real site at `https://YOURNAME.github.io` in about ten minutes. Everything
happens in a web browser — nothing to install, no command line.

This is a lightly trimmed copy of [Academic Pages][ap], prepared for a workshop where
most people had never used GitHub before. The differences are all subtractions: the
upstream project's own CI, the Docker and devcontainer tooling, and the talk-map and
publication-generator scripts are gone, the example content is cut back to one item
per section, and the placeholder social links no longer point at other people's real
profiles.

If you want the full-featured original, with all its tooling and documentation, go to
[academicpages.github.io][ap] — it is very good, and this owes everything to it.

## Getting your own copy

**1. Fork it.** Use the *Fork* button at the top of this page. In the dialog, set
**Repository name** to exactly `YOURNAME.github.io`, using your own GitHub username —
that name is what produces the web address. Tick *Copy the main branch only*.

**2. Fill in your details.** Open `_config.yml`, click the pencil icon, and change:

| Setting | Change it to |
|---|---|
| `title` | Your site's title |
| `name` | Your name — keep the `&name` part, change only the quoted text |
| `url` | `"https://YOURNAME.github.io"` |
| `repository` | `"YOURNAME/YOURNAME.github.io"` |
| `bio` | A sentence about your research |

`url` and `repository` are the two that have to be right; the rest are cosmetic. Keep
the quotes, and don't change the indentation at the start of a line.

**3. Switch it on.** Go to *Settings* → *Pages*. Under *Source*, choose **Deploy from
a branch**, set the branch to **main** and the folder to **/ (root)**, and save.

**4. Wait a couple of minutes**, then visit `https://YOURNAME.github.io`.

## Publications that update themselves

Put your ORCID iD in `_config.yml` and the Publications page fills itself in from
your ORCID record:

```yaml
author:
  orcid_id : "0000-0002-1825-0097"    # your own iD, digits only
```

That's the whole setup. The page fetches your works from ORCID's public API each
time a visitor opens it, grouped by year, with DOI links. Add a paper to ORCID and it
appears on your site immediately — there's no rebuild, no scheduled job, and nothing
that can quietly stop working in eight months' time.

Leave `orcid_id` blank and the page behaves as it always did, listing the files you
write by hand in the `_publications` folder. Use whichever you prefer.

**On Google Scholar:** you can link to your profile — set `googlescholar` in
`_config.yml` and a link appears at the top of the Publications page — but a Scholar
profile cannot be pulled in automatically. Google provides no API for it, scraping
breaks their terms of service, and the scrapers that exist get blocked quickly and
without warning. Anything promising otherwise will strand you.

ORCID is the way round this, and it's a one-off job: ORCID's *Search & Link* wizards
import from Crossref, Scopus and PubMed in a few clicks, and Scholar itself can
export BibTeX you can feed in. Do that once, keep ORCID current afterwards, and this
page stays current for free. It's also the identifier journals and funders are
increasingly asking for anyway.

## Adding your own content

Pages live in `_pages` and are written in Markdown. The sections in the top menu each
have their own folder — `_publications`, `_talks`, `_teaching`, `_posts`,
`_portfolio` — and each holds one example file to copy. Delete a folder if you don't
want that section, and remove it from the menu in `_data/navigation.yml`.

Your photo is `images/profile.png`. Replace it, keeping the filename, or point
`avatar` in `_config.yml` somewhere else.

## When it doesn't work

**A 404.** Usually just too early — first builds take a minute or two. If it persists,
check the repository name is exactly `YOURNAME.github.io`, all lowercase.

**The page loads but has no styling.** The `url` line in `_config.yml` is wrong. It
should be `"https://YOURNAME.github.io"`, with the quotes and no trailing slash.

**Nothing publishes and Settings → Pages looks fine.** Check your GitHub email address
is verified at <https://github.com/settings/emails>. Pages refuses to build for
unverified accounts and gives no warning.

**A red X on the repository.** Something in `_config.yml` has a formatting problem,
usually a missing quote. Open the file's *History* and undo your edit.

## Licence and credit

MIT, inherited from [Academic Pages][ap], which is itself built on the
[Minimal Mistakes][mm] theme by Michael Rose. `LICENSE` is unchanged. Please keep the
attribution if you pass this on.

[ap]: https://github.com/academicpages/academicpages.github.io
[mm]: https://mmistakes.github.io/minimal-mistakes/
