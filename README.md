# Zine flipbook — GitHub Pages + Readymag

## Publish
1. Create a public GitHub repository called `zine-flipbook`.
2. Unzip this package. Upload the CONTENTS of the flipbook folder into the repository, including `index.html`, `pages`, `vendor`, and `magazine.pdf`. Do not upload the ZIP itself. The index.html must be at the repository root.
3. Commit the upload to `main`.
4. Open Settings → Pages. Set Source to Deploy from a branch, choose main and / (root), then Save.
5. Wait for the deployment to finish. Copy the live URL shown in Pages settings.

## Readymag
Paste this into your Embed/Code widget, replacing YOUR-USERNAME with your GitHub username (and repository name if different):

```html
<iframe
  src="https://YOUR-USERNAME.github.io/zine-flipbook/"
  title="Aristella's zine flipbook"
  style="width:100%;height:700px;border:0;background:transparent;"
  allow="fullscreen"
  allowfullscreen>
</iframe>
```

Set the widget width to suit your layout. On mobile, use roughly 500–600px height. Publish and test the actual page, including its mobile layout.

## Features
Paper page flips, dragging, swiping, arrow keys, responsive single-page mobile view, separate cover, enlarged page view, PDF link, and fullscreen where supported. Surroundings are transparent to show the Readymag background.

## Page structure
The PDF contains square covers and landscape spreads. The interior spreads have been split into individual square pages (20 pages total) so page turning follows the printed zine.

## Updating the zine
The original PDF is provided as magazine.pdf. The viewer uses high-resolution JPEG pages rendered from it for fast loading; replacing the PDF alone does not change the flipbook. Render and split landscape spreads into left and right images; name all individual pages consecutively as page-01.jpg, page-02.jpg, etc. Then update the total in index.html if the page count changes. To render the source with Poppler before splitting:
`pdftoppm -jpeg -scale-to 1600 -jpegopt quality=90 magazine.pdf pages/page`

## Credits
Page turn engine: StPageFlip 2.0.7 by Nodlik (MIT). Vendored locally so the viewer does not rely on a CDN. The accompanying license is in vendor/LICENSE.
