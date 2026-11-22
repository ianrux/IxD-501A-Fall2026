# Ioniq 9 Cockpit: unmoderated usability test

Participants open your link, take the test without signing in to anything, and every session saves into your Google Sheet.

## 1. Connect the Google Sheet (about 5 minutes)

1. Open the **Ioniq 9 Usability Test Results** sheet in your Google Drive.
2. Go to **Extensions > Apps Script**. Delete what's there and paste everything from `apps-script.gs.txt`. Click **Save**.
3. Click **Deploy > New deployment**. Choose the gear icon > **Web app**.
   - Execute as: **Me**
   - Who has access: **Anyone**
4. Click **Deploy** and approve the permissions. Google warns that the app isn't verified. That's expected for your own script: choose **Advanced > Go to (project name)**.
5. Copy the **Web app URL** (it ends in `/exec`).
6. Open `test-config.js` and paste the URL between the quotes after `sheetUrl:`.

## 2. Put it on GitHub Pages

1. Create a new **public** repository on GitHub, for example `ioniq9-test`.
2. Click **Add file > Upload files** and drag in everything in this folder (keep the `assets` and `vendor` folders), then commit.
3. Go to **Settings > Pages**. Under "Build and deployment", pick **Deploy from a branch**, branch **main**, folder **/ (root)**, and save.
4. After a minute or two, your site is at `https://YOUR-USERNAME.github.io/ioniq9-test/`.

## 3. Links

- **Send to participants:** `https://YOUR-USERNAME.github.io/ioniq9-test/?test` (the `?test` sends them straight into the test).
- **Your own prototype view:** the same link without `?test`. Use the red **Test session** button to preview.

## 4. Check it before you send it

Run one session yourself with the `?test` link. Within a few seconds of finishing the first task, the sheet should show a **Sessions** tab and a **Tasks** tab with your run. Rows update after every task, so even someone who exits early is saved. Your preview runs show `Preview = TRUE`; filter or delete them before analysis.

## Notes

- If the sheet stays empty, the URL in `test-config.js` is missing or wrong, or the deployment's access isn't set to **Anyone**. Participants still get a **Download results** button as a backup.
- If you change the Apps Script later, use **Deploy > Manage deployments > Edit > New version** so the URL stays the same.
- Anyone who finds the web-app URL could send rows to the sheet. That's fine for a class project; don't reuse it for anything sensitive.
