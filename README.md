Video to Markdown
=================

[![Build Status](https://travis-ci.org/marcomontalbano/video-to-markdown.svg?branch=main)](https://travis-ci.org/marcomontalbano/video-to-markdown)
[![Cloudinary](https://shields.io/badge/-Cloudinary-3448c5)](https://cloudinary.com/invites/lpov9zyyucivvxsnalc5/nfvt85kdqleszdah0hxq)
[![PayPal.me](https://img.shields.io/badge/paypal-donate-119fde.svg)](https://www.paypal.me/marcomontalbano)
[![Sponsor](https://img.shields.io/badge/-Sponsor-fafbfc?logo=GitHub%20Sponsors)](https://github.com/sponsors/marcomontalbano)

[![Netlify Status](https://api.netlify.com/api/v1/badges/545bbce5-8f34-4834-9e16-685a9990c987/deploy-status)](https://app.netlify.com/sites/video-to-markdown/deploys)

Add videos to your markdown files easier [starting from here](https://video-to-markdown.marcomontalbano.com/)!


## Why?

How often did you find yourself googling _¨How to embed a video in markdown?¨_

While its not possible to embed a video in markdown, the best and easiest way is to extract a frame from the video, add a layer with a play icon and link the video url on the image.

Speaking HTMLese, this is what you would do:

```html
<a href="{video-url}" title="Link Title"><img src="{image-url}" alt="Alternate Text" /></a>
```

that translates into markdown as:

```md
[![Alternate Text]({image-url})]({video-url} "Link Title")
```

To speed up the process I developped this tool that will do it for you.

You just need to paste the video url in the field above and you will get the markdown you need.


## Features

List of supported video providers:

- [x] Asciinema
- [x] CleanShot Cloud
- [x] Dailymotion
- [x] Facebook (low-quality)
- [x] Google Drive
- [x] Imgur
- [x] Loom
- [x] OneDrive
- [x] PeerTube
- [x] Streamable
- [x] TikTok
- [x] Vimeo
- [x] Wistia
- [x] Youtube


## Hosting

First of all you need to create a [Cloudinary] account (I'm using this service to generate and host images) so that you can copy your personal `CLOUDINARY_URL` from your dashboard. The url is something similar to `cloudinary://my_key:my_secret@my_cloud_name`.

Now you can easily deploy your own copy on Netlify.

[![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/marcomontalbano/video-to-markdown)


## Development stuff

To run the project locally, here’s what you’ll need:

### Requirements

* [Cloudinary] account
* [Node.js](https://nodejs.org/) 18 or greater

### Setup

`cd` into your local copy of the repository and run `pnpm install`

```sh
cd video-to-markdown
pnpm install
```

```sh
cp .env.sample .env
# update the .env with proper values
```

* `CLOUDINARY_URL` ( **required** ) - this is the `API Environment variable` that you can get from your Cloudinary dashboard inside the **Account Details** section.
* `GA_TRACKING_ID` ( _optional_ ) - this is a Google Analytics Tracking ID. Can be used if you need to track page views and events.
* `NETLIFY_ACCESS_TOKEN` ( _optional_ ) - this a Netlify Access Token. In combination with the `SITE_ID` can be used to display the **API Usage** in the website.
* `SITE_ID` ( _optional_ ) - this the Netlify Site ID. In combination with the `NETLIFY_ACCESS_TOKEN` can be used to display the **API Usage** in the website.
* `USE_HIGH_QUALITY` ( _optional_ ) - this is a boolean flag. If `true`, the generated images will be stored in Contenful with hi-res quality (default to `false`)

```sh
pnpm dev

# http://localhost:8888
```

## Privacy

Google Analytics is used to record the following:

* [Basic visit data](https://support.google.com/analytics/answer/6004245?ref_topic=2919631).
* `referer` or `video url` to track api usage.

All images are generated via [Cloudinary] and stored in it.
In this way the generated images are cached so we can avoid to call Netlify functions again thus reducing the quota consumption.

By clicking on `convert to markdown` or consuming api you accept this terms & condition; no additional data is sent to the server.

[Cloudinary]: https://cloudinary.com/invites/lpov9zyyucivvxsnalc5/nfvt85kdqleszdah0hxq
