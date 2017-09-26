# debrochure-pdf

This is a Bash script that takes a PDF formatted for double-printed brochure pages (where the left side of the first page is the back cover, the right side of the first page is the front cover, the left side of the second page is the inside front cover, the right side of the second page is the inside back cover, the left of the third page is the back of the last inside page, the right of the third page is the front of the first inside page, and so on) and reformats it as a document where each in-book page has its own in-PDF page.

It makes use of two separate tools to accomplish this:

- `mutool` (avalable in the `mupdf-tools` package on Ubuntu), for splitting the pages in half
- `pdftk` (avalable in the `pdftk` package on Ubuntu), for splitting and re-merging the individual pages into separate files for re-numbering

Ideally, this would all be put into one GhostScript script (maybe using [this StackOverflow answer](https://stackoverflow.com/a/14497102/34799) as a base), rather than calling out to tools from *two separate PDF manipulation packages* to accomplish what is, all things considered, a pretty simple task. However, figuring out just how to do that would require more time learning about PDF manipulation toolchains than I really care to spend.

## Usage

```sh
./debrochure-pdf brochure.pdf
```

This will create a new file called `brochure-sp.pdf`.
