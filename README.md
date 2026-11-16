# What the Minister Was Prepared to Say

[Open the live explorer](https://coolcode.ca/ministersays/)

Search the English and French question-period packages that federal institutions prepared for ministers. Filter by publishing institution and year. Open the full published text, including redactions as supplied, and select any two notes to compare their questions, prepared responses, and background.

The [official Question Period Notes catalogue](https://open.canada.ca/data/en/dataset/ecd1a913-47da-47fc-8f96-2432be420986) describes which sitting-day packages are covered. Prepared notes are not a transcript. The published dates and ministry codes are source fields, and the interface preserves missing values.

## Build and preview

```sh
python3 scripts/build.py
python3 -m http.server 8000 --directory dist
```

Open http://localhost:8000/. Use a current browser with Web Worker and gzip decompression support. Python 3.10 or later is needed only to build the site. Set `--csv /path/to/qpnotes.csv` to rebuild from a previously downloaded government export. The first visit loads the compressed bilingual search index. Full note text loads when you open a note or a comparison.

GitHub Actions builds and publishes this site on a daily schedule, app changes, and manual workflow runs. The build downloads the official CSV documented in `dataset.json`. Generated browser files live in the Pages artifact. Download or schema failures stop deployment and retain the last successfully published snapshot.

Contains information licensed under the [Open Government Licence – Canada](https://open.canada.ca/en/open-government-licence-canada). Publisher: Treasury Board of Canada Secretariat.
