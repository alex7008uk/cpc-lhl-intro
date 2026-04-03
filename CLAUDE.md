# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project

Personal introduction website for 林夏蘭 (Lin Xia-lan), Assistant Manager at CPC Tainan Service Center. The site displays her personal introduction (bio, contact info) at the top and links to related CPC staff introduction pages below. Deployed to Cloudflare Pages.

See `requirements.md` for the full bio text and contact details (do not paraphrase — use the exact Chinese text verbatim).

## Reference Sites

Five similar CPC intro sites exist for design reference. Match their layout and style:
- https://hch-intro.pages.dev/
- https://cpc-cjy-intro.pages.dev/
- https://cpc-engineering-intro.pages.dev/
- https://cpc-training-intro.pages.dev/
- https://cpc-common-intro.pages.dev/

## Architecture

Static site (HTML/CSS/JS or equivalent), deployed via Cloudflare Pages. No backend. All content is static Chinese text.

## Key Constraints

- All user-facing text must be Traditional Chinese (繁體中文).
- Contact info: (06)2134413 ext 03307, email 03307@cpc.tw.
- The five reference URLs above should all appear as navigable links at the bottom of the page.
