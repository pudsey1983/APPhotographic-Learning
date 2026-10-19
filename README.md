# A.P Photographic — Depth of Field Simulator

Free, responsive depth-of-field calculator and illustrative focus preview. Built as plain HTML, CSS and JavaScript. No Node.js, build tools, database, analytics or external libraries are required.

## Features

- Nikon D850, D7200, Z8, Z50; Canon EOS R5, R6 II, 5D IV, R7, 90D; Sony A7 IV, A7R V, A9 III, A6700, A6400, plus generic sensor types
- Controls for aperture, focal length and focusing distance
- Near focus limit, far focus limit, total depth of field and hyperfocal distance
- Metric and imperial distance displays
- Scenario presets: portrait, sports, landscape, close-up
- Shareable camera settings via URL parameters
- A.P Photographic branding and mobile-responsive design
- **Flash Learning Studio:** four real-world lighting scenarios, manual flash power from 1/1 to 1/128, guide number, distance, direct/bounce flash, aperture, ISO, shutter speed and ambient light
- Estimated flash exposure, ambient exposure and flash range; interactive illustrative lighting preview and beginner lessons
- Calculations all happen locally in the browser

## Deploy free using GitHub Pages

1. Create a **public** repository on GitHub, for example `depth-of-field`.
2. Select **Add file → Upload files**, and upload **index.html** and **logo.png** into the repository root (not a nested folder). Commit the changes. You may optionally upload this README file. Do **not** upload the ZIP as the only file: GitHub Pages cannot serve it as a website.
3. In the repository select **Settings → Pages**.
4. Under **Build and deployment**, choose **Deploy from a branch**, with branch **main** and folder **/(root)**. Save.
5. Wait for Pages to publish. Visit `https://YOUR-USERNAME.github.io/depth-of-field/`.
6. Optional: in **Settings → Pages → Custom domain**, enter `dof.apphotographic.co.uk` and save.
7. At your domain DNS provider create a **CNAME** record for host `dof` pointing to `YOUR-USERNAME.github.io` (without `https://` or the repository name). Once DNS and certificate are ready, enable **Enforce HTTPS** in GitHub Pages settings.
8. Consider verifying the domain on GitHub before making DNS changes. DNS changes can take up to 24 hours.

**Important:** A free GitHub account requires the Pages repository to be **public**. GitHub Pages is for static projects, and GitHub restricts using it as hosting for websites primarily used to run an online business, conduct ecommerce or sell SaaS. This project is designed as a free educational tool, not a shop. GitHub Pages has a published-site size limit of 1 GB and a soft bandwidth limit of 100 GB/month.

## Run on your computer

Open `index.html` in your browser. The share link works as intended once published at an HTTPS website.

## Technical notes

- Hyperfocal distance: `H = f²/(N × c) + f` in millimetres.
- Near limit: `H × s / (H + s − f)`; far limit: `H × s / (H − s + f)` or infinity when `s − f >= H`.
- For the chosen sensor format, conventional circle-of-confusion values are used (0.030 mm FX, 0.020 mm Nikon DX, 0.019 mm Canon APS-C, 0.015 mm MFT).
- These are thin-lens approximations; real lenses, focus breathing, magnification and expectations of sharpness can affect real-world results.
- Focus preview and bar graph are conceptual visualisations, **not** a physically accurate simulator or a proportional distance diagram.
- Flash approximation uses `GN_effective = GN_full × sqrt(relative_flash_power) × sqrt(ISO/100) × bounce_factor`, with bounce factor 0.5 (illustrative two-stop loss). Estimate f-number as `GN_effective / distance`; relative flash EV as `2 log2(f_number_estimate / aperture)`.
- Ambient exposure uses `EV100_camera = log2(aperture² / shutter_seconds) − log2(ISO/100)` compared to representative scene EV. Camera flashes have differing synchronization limits. Model does not include HSS, TTL, flash zoom changes, modifiers, subject reflectance or bounce-surface geometry.
- Calculations and lighting previews are **educational estimates**. Validate with test exposures before relying on them.

Copyright © 2026 A.P Photographic. Original implementation written for A.P Photographic.
