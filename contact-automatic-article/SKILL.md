---
name: "contact-automatic-article"
description: "Write a Frontal-standard bottom-of-funnel article (best X, X vs Y, alternatives) for contact.so from Rob's own material, save it as an unpublished Webflow draft, then publish and request indexing on approval."
---

# Contact automatic article

Builds one ranking page for contact.so: a "best X", "X vs Y" or "X alternatives" article written to the same standard as the Frontal pages ("Best GTM Agency in 2026: The Buyer's Shortlist" ranks #1 in Google, the AI Overview and its citations). It is written from Rob's own material, saved to Webflow as an unpublished draft for review, and only published and submitted for indexing when Rob says so.

Reference article: the first one built this way is https://www.contact.so/blog/best-ai-seo-agency. Its source brief is in Google Drive: "Best GTM Agency in 2026 - The Buyer's Shortlist - Frontal.so | Contact" (doc 1I4uSa3U1xNL0C7CRdF7FQnL6OiPctU1K81yyW5Zfy58). Read one of them first if unsure what "good" looks like.

## Hard rules

- Never publish without Rob's explicit go-ahead. Create items with isDraft: true.
- Every fact about a competitor comes from that competitor's own website, fetched in this run, with the check date stated in the article. If a site does not publish something (pricing, results), say "not published". Never estimate.
- Contact's proof only from public sources: the contact.so homepage results and testimonials, Rob's public YouTube videos, X and LinkedIn posts. Lessons from client calls (Fireflies) are allowed only anonymised: no client, founder or product names, no identifying numbers.
- Pricing for Contact: only include if Rob has confirmed it may be public (last confirmed: "typically $10K to $25K+ per month").
- Writing: Rob's voice, plain sentences. Run the no-ai-slop skill on the final text. No em dashes, no semicolons, no arrows.
- Don't put anything into the old "Contact Studios Website" Webflow site (61e7260bf15d717f703f9e93). contact.so is the site "Contact" (64c7c4a3890051734abd8a9d).

## 1. Pick the keyword

1. Brainstorm BOFU candidates for what Contact sells (AI search, SEO, AEO, GEO, LLM SEO, industry-specific variants, "X vs Y" between tools or agencies, "alternatives").
2. Ahrefs keywords-explorer-overview (country us, select keyword,volume,difficulty,traffic_potential,cpc,parent_topic,intents). Prefer low difficulty with commercial intent. Group close variants as supporting keywords (one page should cover the cluster).
3. Ahrefs serp-overview for the primary keyword (top 10): note who ranks, the AI Overview sources, Reddit/Quora threads, and which agencies or tools keep getting listed.
4. Check contact.so blog (Webflow list_collection_items on Blogs) so you don't duplicate an existing post.

## 2. Gather source material

- **Rob's YouTube** (channel @AISearchandInbound, id UCg7cL-3MHTR33W5Ft7pBcuA). Open https://www.youtube.com/@AISearchandInbound/videos in Chrome, read titles and ids (javascript: collect a[href*="/watch"] titles and v= ids). For each relevant video open it, use find for "Show transcript button", click it by ref, then get_page_text to read the transcript. Key videos so far: 6FSH-rUgVzM (how the Frontal page is built, the page-structure playbook), q6GOdRdIvjU (client ranking in ChatGPT in under 10 days), JqulEy71Vhg (#1 on ChatGPT and Google in 24 hours).
- **contact.so homepage**: WebFetch for current named results (beehiiv, Delta Munchies, Botany Farms, Shopify, HØJ, Causal, TubeBuddy, etc.) and testimonials. Use the numbers from the results section, and note any conflicts rather than picking the bigger one.
- **Fireflies**: fireflies_search for the topic over the last 60 days. Use client and sales calls only for anonymised lessons (e.g. "swapping branded prompts for commercial ones moved share of voice from 4.3% to 1.7%").
- **Competitors**: pick 5 that genuinely compete for the keyword (from the SERP and other listicles). WebFetch each one's homepage and pricing page. Record: positioning, founder or CEO, named client results with numbers, pricing or minimums, ideal client. Reddit is often blocked to fetch, so rely on SERP snippets for buyer questions.

## 3. Page structure (follow in order)

This mirrors the Frontal page and Rob's "Simple Blog Posts That Make Millions From ChatGPT" video.

1. Title and H1 start with the exact primary keyword. Slug = primary keyword. Meta description under 160 characters.
2. Real named author (Rob) and a visible "Last updated <date> · <n> min read" line.
3. Hook: 2 short paragraphs naming the buyer's real problem, then one line on what the list is and how it was ranked. Disclose that Contact ranked itself first.
4. **Key Takeaways**: 4 to 5 bullets, each a bold one-line claim plus one sentence.
5. **Definition section**: what the thing is and what it is not.
6. **How We Ranked**: 4 bullet criteria (named verifiable results, depth, speed, transparency), plus the date competitor facts were checked.
7. **The ranked list**: H3 per entry, format "1. Name, Best for X". Contact first with the strongest proof bullets, one concrete AI-search story, the repeatable process as a numbered list, pricing, "best suited to" and where it stops, and a YouTube embed of Rob explaining the method. Then 5 competitors: what they are, named results (as numbers), pricing or "not published", "best suited to", and an honest limit.
8. **Side-by-side comparison table**: Agency, Best For, Named Results You Can Check, Pricing. One line under it pointing to why Contact leads.
9. **Fit table** ("Which X Fits Your Company"): situation, what matters most, who to look at.
10. **What separates a real X from a rebranded one**: 4 buyer questions, including one anonymised lesson from Rob's calls.
11. **Proof table**: client, result, what the number measures.
12. **FAQ**: 6 to 7 long-tail questions as H3, 2 to 3 sentence answers.
13. **CTA section** congruent with the keyword (e.g. "Book a Free AI Search Strategy Call" linking https://www.contact.so/#call). If the template has no floating CTA, keep at least this one.

Also build a short brief (keyword data, supporting keywords, title tag, meta, slug, schema Article + FAQPage, information gain, sources) for Rob in a Claude doc next to the article, with a Sources list.

## 4. Save to Webflow as a draft

Webflow ids for contact.so (re-check with list_sites and get_collection_details if anything fails):
- Site "Contact": 64c7c4a3890051734abd8a9d (designer shortName contactstudios)
- Blogs collection: 66461fc69756a634914ec46e. Template page "Blogs Template": 66461fc79756a634914ec48a
- Fields: name, slug, post-body (RichText), post-summary-meta-description (max 160), main-image (Image, 2:1), image-alt-text, category (Option: SEO 868446b46f850765ed52796edfe7b5f6, Content Marketing 572bc5974704ecacc88bcfbda1bbf115), author (Option: Rob Hoffman fc7a32038ea21db2fc66d1cd8d001e6d), author-pictture (Image, reuse Rob's photo https://cdn.prod.website-files.com/64c81028f7c850d080cd757a/68595af32e2382549722b6e0_rob-author.png, fileId 68595af32e2382549722b6e0), author-bio (one line).

Body HTML rules (the blog template has no paragraph spacing or list styles, and a black background):
- Start the body with this scoped style embed:
  `<div data-rt-embed-type="true"><style>.w-richtext p{margin:0 0 18px}.w-richtext h2{font-size:34px;line-height:1.15;margin:56px 0 18px}.w-richtext h3{font-size:24px;line-height:1.25;margin:40px 0 14px}.w-richtext ul,.w-richtext ol{padding-left:24px;margin:0 0 22px}.w-richtext ul{list-style:disc}.w-richtext ol{list-style:decimal}.w-richtext li{margin:0 0 10px;padding-left:4px}.w-richtext figure{margin:32px 0}.w-richtext table{margin:8px 0 28px}.w-richtext table td,.w-richtext table th{color:inherit}.w-richtext a{text-decoration:underline}</style></div>`
- H1 comes from the Name field, so the body starts at the "Last updated" line. Use h2 for sections and h3 for list entries and FAQ questions.
- Tables are not native in Webflow rich text: wrap each in `<div data-rt-embed-type="true"><div style="overflow-x:auto"><table style="width:100%;border-collapse:collapse;font-size:15px">...` with header borders `2px solid rgba(255,255,255,0.55)` and row borders `1px solid rgba(255,255,255,0.15)`, padding 8px.
- YouTube embed format (matches existing posts): `<figure class="w-richtext-figure-type-video w-richtext-align-center" style="padding-bottom:56.25%" data-rt-type="video" data-rt-align="center" data-rt-max-width="" data-rt-max-height="56.25%" data-rt-dimensions="854:480" data-page-url="https://www.youtube.com/watch?v=ID"><div><iframe src="https://www.youtube.com/embed/ID" title="..." scrolling="no" frameborder="0" allowfullscreen="true"></iframe></div></figure>`
- Build the body as markdown in the workspace, convert with python markdown (tables extension), then apply the replacements above.

Create with data_cms_tool create_collection_items, isDraft true. Verify with list_collection_items filter id eq.

## 5. Header image (2:1)

Generate 1600x800 PNG with Pillow and Inter fonts (/usr/share/fonts/opentype/inter/): background #111111, subtle lime glow and faint grid, lime (#CBF41C) eyebrow line, big white title, a row of ranked pills with #1 Contact filled lime, "contact" wordmark bottom right. Look at it before uploading.

Upload: the workspace cannot reach Webflow's S3 bucket, so upload through Chrome. Open the Designer on the Blogs Template, click the "Assets (J)" button (find it by ref), find the "file input for uploading assets" and call file_upload with the PNG path and origin https://contactstudios.design.webflow.com. Then list_assets (limit 3) to get the new asset's id and set main-image {fileId, url, alt} plus image-alt-text with update_collection_items.

## 6. Review with Rob

Open the draft rendered in the template: https://contactstudios.design.webflow.com/?pageId=66461fc79756a634914ec48a&itemId=<ITEM_ID>&workflow=sitePreview (wait about 10 seconds for "Compiling custom code"). Scroll and screenshot to check spacing, bullets, tables and the video before telling Rob it's ready.

Designer cautions: never type into the Designer canvas (letters are keyboard shortcuts), don't click near "Publish now" in the CMS item modal, and close modals with Escape.

## 7. Publish and index (only on Rob's go-ahead)

1. publish_collection_items for the item. Load the live URL https://www.contact.so/blog/<slug> to confirm.
2. Google Search Console in Chrome: open https://search.google.com/search-console?resource_id=sc-domain:contact.so, click the "Inspect any URL" bar (top centre), type the full URL, Enter, wait ~10s, click REQUEST INDEXING, wait up to a minute for "Indexing requested", then Dismiss. Don't request twice.
3. Offer to submit to Bing Webmaster Tools too (ChatGPT search uses Bing).
4. Tell Rob: live URL, indexing status, and that internal links from the homepage or blog index and sharing on X and LinkedIn speed up crawling. The sitemap updates on the next full site publish.

## Final report to Rob

One short message: title and live or draft link, target keyword with volume and difficulty, competitors included, anything left out for confidentiality, open decisions (pricing line, image), and indexing status.