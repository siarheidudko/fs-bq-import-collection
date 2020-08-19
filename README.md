# fs-bq-import-collection
Fork for data import script in BigQuery with support for subcollections. Original: [@firebaseextensions/fs-bq-import-collection](https://github.com/firebase/extensions/tree/master/firestore-bigquery-export/scripts/import), [npm](https://www.npmjs.com/package/@firebaseextensions/fs-bq-import-collection)

## Preparation
`export GOOGLE_APPLICATION_CREDENTIALS=<path-to-your-service-account-key>`

## Use

### Interactive
`npx github:siarheidudko/fs-bq-import-collection`
### Non interactive
`npx github:siarheidudko/fs-bq-import-collection --non-interactive --project vend-park-development --source-collection-path invites --dataset firestore_export --table-name-prefix invites --batch-size 300`

## Launch parameters

|                        Name                         |          Short name           |                                   Description                                    |
|-----------------------------------------------------|-------------------------------|----------------------------------------------------------------------------------|
|                  --non-interactive                  |              -                | Parse all input from command line flags instead of prompting the caller. Default: `false` |
|                --project `<project>`                |         -P `<project>`        | Firebase Project ID for project containing the Cloud Firestore database.|
| --source-collection-path `<source-collection-path>` | -s `<source-collection-path>` | The path of the the Cloud Firestore Collection to import from. (This may, or may not, be the same Collection for which you plan to mirror changes.) |
|                --dataset `<dataset>`                |        -d `<dataset>`         | The ID of the BigQuery dataset to import to. (A dataset will be created if it doesn't already exist.) |
|      --table-name-prefix `<table-name-prefix>`      |    -t `<table-name-prefix>`   | The identifying prefix of the BigQuery table to import to. (A table will be created if one doesn't already exist.) |
|             --batch-size `[batch-size]`             |       -b `[batch-size]`       | Number of documents to stream into BigQuery at once. Default: `300` |