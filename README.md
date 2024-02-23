This repository automatically deploys to the critical-editons project server using github actions.

## Deploy data to staging

- On changes to the `data` folder and its files
- On push to branch: `staging`
- To the AWS S3 bucket [](staging.editions.fortunoff.library.yale.edu)

## Deploy data to production

- On changes to the `data` folder and its files
- On push to branch: `main`
- To the AWS S3 bucket [critical-editions-prod](editions.fortunoff.library.yale.edu)

## Deploy media

- On changes to the `media` folder and its files
- On push to branch: `main`
- To the AWS S3 bucket `fortunoff-media-public`

## The `data` folder

Holds the `config.json` file where the metadata to the editions are stored
and the visibility and order of the editions are managed.

Holds the `intro-hvt-xxxx.json` editon files using the editor.js format for annotations.

The naming convention of the files is important for the website to function correctly.

## The `media` folder

Holds images, videos and pdfs relevant to the editions.

The naming convention of the paths and files is important for the website to function correctly.
