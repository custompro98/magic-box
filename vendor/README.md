# Vendored assets

`tailwind.min.css` is prebuilt with Tailwind CSS **3.4.17**, the version previously
served by `https://cdn.tailwindcss.com`. It includes the reset and utility styles
used in `index.html`, including responsive, hover, focus, and active states.
Tailwind is distributed under the MIT license; see `LICENSE.tailwindcss`.

## Running offline

Open `index.html` directly in a browser. Keep the `vendor` directory alongside it.
No server, package installation, build step, or internet connection is required.
The page's JavaScript is inline, and its fonts use the local system font stack.
There are no third-party JavaScript dependencies at runtime.

## Updating the stylesheet

If you add or change Tailwind classes in `index.html`, regenerate the stylesheet
from the project directory:

```sh
npm exec --yes --package=tailwindcss@3.4.17 -- tailwindcss \
  --input ./vendor/tailwind.input.css \
  --content ./index.html \
  --output ./vendor/tailwind.min.css \
  --minify
```

Regeneration requires Node.js and access to the pinned npm package (internet on
the first run). The generated CSS is included in the project for offline use.
