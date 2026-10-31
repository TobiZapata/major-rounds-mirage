# Major rounds: Mirage

Versioned replay data used by the Major MVP CS simulator. This is a game resource bank, with 990 extracted Mirage rounds from 50 demos, sampled at 8 Hz.

## Contents

- `v1.0.0/economy-index.json`: round catalog with equipment evidence (schema 1, equipment version 2).
- `v1.0.0/index.json`: base round catalog.
- `v1.0.0/demos/<demo-sha256>/rNNN.json.gz`: compressed per-round gameplay telemetry.

Catalog references retain the application prefix `/round-bank/`. A consumer maps that prefix to this repository's versioned CDN root. Files are individual rounds; consumers load selected rounds on demand.

## Versions

Use an exact commit SHA or a fixed release tag when consuming this bank. Existing tags are not moved. A changed bank gets a new version, so saved matches can keep their original source.

Published asset root:

`https://tobizapata.github.io/major-rounds-mirage/v1.0.0/`

Version directories are immutable. Publish changed data in a new directory. GitHub Pages serves the bank; its availability and usage limits apply.

The initial bank was also tested on jsDelivr. Although its general README mentions 150 MB packages, the tested GitHub endpoint rejected round requests with `Package size exceeded the configured limit of 50 MB`. The application therefore uses GitHub Pages, not that endpoint. No repositories were split to bypass this restriction.

## Data and provenance

The catalogs retain original demo filenames, hashed demo IDs, source actor/Steam IDs, round timing and results. Round files contain positions, inventories and game events needed to replay the source action. This repository does not assert ownership of the original matches, demos or third-party identities. Attribution and redistribution terms of the source material still apply.

## Size

Initial payload: 992 bank files, 116,780,354 bytes before Git metadata. Only Mirage is included; other map banks are versioned independently.
