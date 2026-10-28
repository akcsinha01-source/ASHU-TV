# ASHU TV — Google TV APK project

This project packages the existing `ASHU TV` HTML player into a simple Android WebView app for Android TV / Google TV. GitHub Actions builds a debug APK and publishes it as a workflow artifact.

## Build APK using GitHub Actions

1. Create a new GitHub repository, for example `ashu-tv`.
2. Upload all files and folders in this project to the repository root (do not upload only the ZIP).
3. Open the repository's **Actions** tab.
4. Select **Build ASHU TV APK** and press **Run workflow**. A push to `main` also starts the workflow.
5. Wait for the run to finish successfully.
6. Open the completed run and download the **ASHU-TV-debug-apk** artifact.
7. Extract the downloaded ZIP; it contains `app-debug.apk`.
8. Transfer the APK to Google TV and install it. You may need to allow installation from unknown sources for the file manager used.

## Important notes

- This is a starter project and has not been built/tested on a physical Google TV in this environment.
- The app uses Android WebView and loads `app/src/main/assets/index.html` locally.
- The HTML player still depends on the playlist/source configuration it already uses and on network access.
- Some remote-control actions, autoplay, HLS formats, DRM streams, and quality variants depend on the stream and Android WebView support. Test with your own permitted stream sources.
- The workflow creates a **debug APK**, not a Play Store-signed release APK.
- To update the player, replace `app/src/main/assets/index.html` with the latest HTML file, commit/push to `main`, then download the new artifact from Actions.
