# Batch web push test

Upload every file in this folder to the **root** of a GitHub repository named exactly:

`<github-username>.github.io`

Enable GitHub Pages on the `main` branch, folder `/ (root)`. The site is then:

`https://<github-username>.github.io/`

The SDK requests the service worker at `/batchsdk-worker-loader.js` on the domain root. A project site such as `https://<user>.github.io/<some-repo>/` will not work, and the files must not sit in a subfolder.

The dashboard website URL is currently `https://migo-test.github.io/sdk/`. `index.html` now has the SDK Auth Key generated for that URL. Re-upload `index.html`. The copy already on GitHub still has the previous key, so Batch keeps rejecting it.

The SDK loads the service worker from `https://migo-test.github.io/batchsdk-worker-loader.js` (the domain root). That URL is 404. The file under `/sdk/` is not the one the SDK requests. Publish the same files from a repository named `migo-test.github.io` so the site and the worker are both on `https://migo-test.github.io/`, then set that URL in Batch and paste the new auth key again.

The subdomain name `oastify38` is only used for the old HTTP / multi-domain mode. Changing it does not update the auth key or the worker path.

Do not add the VAPID private key to this repository. It is not required on the page.
