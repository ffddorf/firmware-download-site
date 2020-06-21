# Freifunk Düsseldorf Firmware Download Site

Site made to show people download links to the firmware for their device.

## Develop

### Requirements

- [NodeJS/NPM](https://nodejs.org/)
- [Hugo](https://gohugo.io/getting-started/installing/)

### Run locally

```
npm i
hugo serve
```

## Deployment

The `main` branch is automatically deployed to the website. It's running on [Netlify](https://www.netlify.com/).

All pull-requests will get a preview built. Open it via the status checks on the PR.

## Common actions

### Adding a new brand or model

Edit the file `data/downloads.json`. This file keeps the filenames of the firmware on our image server.

Add the new entry to the `images` array.

**If there is only one hardware revision, structure it like this:**
```json
{
  "brand": "8devices",
  "models": [
    {
      "name": "Jalapeno",
      "image": "8devices-jalapeno.ubi"
    }
  ]
},
```

**If there are multiple hardware revisions, structure it like this:**
```json
{
  "brand": "D-Link",
  "models": [
    {
      "name": "DIR-505",
      "image": {
        "Revision A1": "d-link-dir-505-rev-a1.bin",
        "Revision A2": "d-link-dir-505-rev-a2.bin"
      }
    }
  ]
},
```

### Changing the copy of the page

Edit the file `content/_index.md`. It's regular markdown.

### Changing styles

Styling is based on [Bootstrap](https://getbootstrap.com/docs/4.5/getting-started/introduction/) (installed via NPM).

Edit the file `assets/style.scss` to update styles or include additional bootstrap components.
