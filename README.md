# maximized-impact-site

The Institute for The Study Of Humanity's homepage, `www.maximized-impact.org`: one page in the house style (the bar, the masthead, the two sentences, the links, the footer). Plain static files, no build step, no functions. Built from `HANDOFF_Production_Build_v14.md`.

| Path | What it is |
|------|------------|
| `index.html` | The page. The Institute name in the masthead is its heading. |
| `_redirects` | `/research/*` to `https://research.maximized-impact.org/:splat`, 301, so `/research/study7` and every later study path resolve on the research site. |
| `netlify.toml` | No build, publish `.`, the security headers and a content security policy that allows nothing external. |
| `assets/` | `css/site.css` and `js/site.js` are identical copies of the files in `isoh-research`: edit both. Fonts and the lotus mark. |

Netlify settings (by hand, in Janne's account, go-live step 14 in the backend repo's README): create the site from this repo, add `www.maximized-impact.org` and the bare domain with only the records Netlify asks for, make `www` the primary domain so the bare domain redirects to it, lock production deploys to the published build, keep Analytics and every add-on off.

Checked on 27 September 2026 with Playwright: the bar and footer match `mockup_v2` at 1280 and 390 px, the mobile menu works by touch, keyboard and Escape, no console errors, every link resolves, Lighthouse accessibility 95 (the one flag is the contrast of the mockup's green links on the light background), zero content-security-policy violations with the `netlify.toml` headers applied.
