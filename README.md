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

> **_NOTE:_** The folder `/critical-editions-content/media/media/hvt-xxxx/` holds images that can be referenced via `Image` blocks in the editor by filename.

## AWS Cloudfront Cache Invalidation

Needs to be done manually due to the folder structure of the S3 bucket not working well with the invalidation system.
The following invalidation list would invalidate the complete public media but exceed the wildcard invalidation limit.
Therefore we need to pick the ones that need invalidation manually.

```
/0170/*
/0237/*
/0536/*
/0574/*
/0764/*
/2033/*
/2348/*
/2570/*
/3038/*
/3164/*
/3169/*
/3171/*
/3178/*
/3280/*
/3384/*
/4103/*
/8008/*
/pdf/*
/media/hvt-0237/*
/media/hvt-0574/*
/media/hvt-2033/*
/media/hvt-2348/*
/media/hvt-3178/*
```
