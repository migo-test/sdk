# Batch web push test

Upload every file in this folder to the **root** of a GitHub repository named exactly:

`<github-username>.github.io`

Enable GitHub Pages on the `main` branch, folder `/ (root)`. The site is then:

`https://<github-username>.github.io/`

The SDK requests the service worker at `/batchsdk-worker-loader.js` on the domain root. A project site such as `https://<user>.github.io/<some-repo>/` will not work, and the files must not sit in a subfolder.

In the Batch dashboard, set the website URL to `https://<github-username>.github.io`. Changing that URL generates a new SDK Auth Key. Paste the new key into `authKey` in `index.html` before you rely on the page. The key already in the file was generated for the previous URL.

Do not add the VAPID private key to this repository. It is not required on the page.
