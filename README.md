# Lily's Place + WIC Family Resource Hub — Version 2

A static GitHub Pages website for the Lily's Place + WIC collaboration in Huntington, West Virginia.

## What this version includes

- Mobile-first participant landing page
- Interactive Leaflet/OpenStreetMap resource map
- Lily's Place NAS Center, Family Center, Children's Center and Residential Treatment Center
- Cabell County WIC / Valley Health
- Food, housing, family-support and transportation resources
- Search + resource filters
- "Use my location"
- WIC quick screening guide
- Official participant-portal QR code and direct link
- WV WIC Tableau Dashboard external link plus optional iframe embed
- TTA transportation section
- WIC opportunity map mode for Huntington ZIPs 25701–25705
- Aggregate WIC metrics from uploaded workbooks
- FY2026 Valley East/West mobile enrollment baseline
- Empty monthly Lily's Place impact tracker ready for future data

## Publish on GitHub Pages

1. Create a GitHub repository, for example `lilys-wic-resource-hub`.
2. Upload **the contents of this folder** to the root of the repository.
3. Go to **Settings > Pages**.
4. Choose **Deploy from a branch**.
5. Select `main` and `/ (root)`.
6. Save.

Do not open `index.html` directly from the Windows file system for testing; browsers commonly block `fetch()` for local JSON files. GitHub Pages will serve it correctly.

## Update community resources

Edit `data/resources.json`. Each resource can have multiple categories.

Supported categories: `lilys`, `wic`, `food`, `housing`, `health`, `family`, `transportation`.

## Update monthly Lily's Place collaboration data

Edit `data/lilys-impact.json` and add aggregate rows:

```json
{
  "months": [
    {
      "month": "2026-10",
      "events": 2,
      "hours": 6,
      "referrals": 8,
      "applications": 5,
      "certifications": 3
    }
  ]
}
```

The four tracker totals on the site update automatically.

## Data used in this build

The site uses aggregate values derived from the user's uploaded workbooks:

- `WV Map Project Data.xlsx`: Huntington ZIP source rows 25701–25705
- `County Data.xlsx`: Cabell County active WIC families
- `SA Master Month Outreach Log and Mobile Enrollment Data FY2026.xlsx`: Valley East/West mobile enrollment events/hours/share
- `Participant Portal QR Code.docx`: official QR image supplied by the user; decoded target is `https://bit.ly/3V0aC4j?r=qr`

The website does **not** contain participant-level data.

## Important verification before public launch

- Reconfirm every organization address, phone number, hours and services.
- The Residential Treatment Center pin is marked `verified:false` and should be confirmed before public launch.
- The WIC opportunity map uses approximate ZIP center points, not ZIP boundaries.
- Estimated WIC eligibility values are planning estimates, not individual eligibility determinations.
- Confirm whether the Tableau server permits iframe embedding. The external-link button works even if embedding is blocked.
- Consider having WV WIC communications/legal review the wording before statewide/public distribution.

## Suggested next upgrades

1. Add the rest of the Huntington/Cabell resource directory.
2. Add TTA GTFS stops and route lines.
3. Add actual ZIP boundary GeoJSON for 25701–25705.
4. Add a monthly impact chart after Lily's Place events begin.
5. Add privacy-conscious click analytics if desired.
6. Add a printable resource handout mode.
