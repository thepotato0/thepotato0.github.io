---
title: Customize the Favicon
author: cotes
date: 2019-08-11 00:34:00 +0800
categories: [blogging, tutorial]
tags: [favicon]
---
since the original tutorial the favicon replacement method has changed so heres an updated version:

## Generate the favicon

Prepare a square image (PNG, JPG, or SVG) with a size of 512x512 or more, and then go to the online tool [**Real Favicon Generator**](https://realfavicongenerator.net/) and click the button <kbd>Select your Favicon image</kbd> to upload your image file.

In the next step, the webpage will show all usage scenarios. You can keep the default options, scroll to the bottom of the page, and click the button <kbd>Generate your Favicons and HTML code</kbd> to generate the favicon.

## Download & Replace

Download the generated package, unzip and delete the following two from the extracted files:

- `browserconfig.xml`{: .filepath}
- `site.webmanifest`{: .filepath}

it seems that it's due to the favicon generator listed in the instruction is now missing some png files, and so the default favicon are used in those situations. I used [**this**](https://favicon.io/favicon-converter/)  generator in addition to the generator listed above to generate favicon .png files, and moved all resulting files from generator listed in instruction (excluding the 2 mentioned in instruction) together with favicon-16x16.png, favicon-32x32.png, android-chrome-192x192.png, android-chrome-512x512.png files from generator I mentioned into the assets/img/favicons/ and it works. Example: https://github.com/sherrywang31/sherrywang31.github.io

And then copy the remaining image files (`.PNG`{: .filepath} and `.ICO`{: .filepath}) to cover the original files in the directory `assets/img/favicons/`{: .filepath} of your Jekyll site. If your Jekyll site doesn't have this directory yet, just create one.

The following table will help you understand the changes to the favicon files:

| File(s)             | From Online Tool                  | From Chirpy |
|---------------------|:---------------------------------:|:-----------:|
| `*.PNG`             | ✓                                 | ✗           |
| `*.ICO`             | ✓                                 | ✗           |


<!-- markdownlint-disable-next-line -->
>  ✓ means keep, ✗ means delete.
{: .prompt-info }

The next time you build the site, the favicon will be replaced with a customized edition.
