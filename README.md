# Liquid Glass Wallpaper Studio – Android App

An authentic iPhone-inspired **Liquid Glass clock wallpaper studio** for Android featuring physical refraction, frosted glass customization, two-image Depth Effect layering, and direct Android `WallpaperManager` integration (`FLAG_LOCK` and `FLAG_SYSTEM`).

---

## Automatic APK Building via GitHub Actions (No Android Studio Required!)

You do **not** need Android Studio or any developer tools installed on your computer. You can upload this project to GitHub using your web browser, and GitHub's cloud servers will compile and deliver your working `.apk` file for free.

---

### Step-by-Step Beginner Guide (Browser Only)

#### Step 1: Create a New GitHub Repository
1. Open [github.com](https://github.com) and sign in.
2. Click the **`+`** icon in the top-right corner and select **New repository**.
3. Name your repository (for example: `liquid-glass-studio`).
4. Set the visibility to **Public** (or Private).
5. Leave "Add a README file" unchecked (you will upload this project's files).
6. Click **Create repository**.

#### Step 2: Upload Project Files to GitHub
1. Download the complete project archive (`LiquidGlassWallpaperStudio_GitHub_Project.zip`) from the web studio.
2. Unzip it on your computer.
3. On your new GitHub repository page, click **uploading an existing file** (or drag and drop).
4. Drag all the files and folders from the unzipped folder into GitHub:
   - `.github/` (contains the `build-apk.yml` workflow)
   - `app/` (contains Android Kotlin code, shaders, resources)
   - `gradle/`
   - `build.gradle.kts`
   - `settings.gradle.kts`
   - `gradlew`, `gradlew.bat`
   - `README.md`
5. Click **Commit changes** at the bottom.

#### Step 3: Automatic APK Build Runs
- Once committed, GitHub automatically detects `.github/workflows/build-apk.yml` and starts building the APK.
- You can also trigger it manually anytime:
  1. Go to the **Actions** tab at the top of your GitHub repository.
  2. In the left sidebar, click **Build Liquid Glass Android APK**.
  3. Click **Run workflow** -> **Run workflow**.

#### Step 4: Check Build Status
- In the **Actions** tab, you will see a workflow run in progress (with a yellow spinning circle).
- Click on the run name (`Build Liquid Glass Android APK`) to watch the live compilation logs:
  - Setting up Java 17...
  - Setting up Android SDK...
  - Compiling Kotlin & Compose code...
  - Packaging `app-debug.apk`...
- The process takes around **2 to 3 minutes**. When finished, a green checkmark will appear.

#### Step 5: Download Your APK Artifact
1. Click on the completed workflow run.
2. Scroll down to the **Artifacts** section at the bottom of the page.
3. Click on **`LiquidGlassWallpaperStudio-APK`** to download your ready-to-install `.zip` file containing `app-debug.apk`.

#### Step 6: Install on Your Android Phone
1. Transfer `app-debug.apk` to your Android phone (via Google Drive, USB, WhatsApp, email, or direct download in Chrome).
2. Tap the `.apk` file on your phone.
3. If prompted with *"For your security, your phone is not allowed to install unknown apps from this source"*:
   - Tap **Settings**.
   - Enable **Allow from this source**.
   - Tap **Back** and select **Install**.
4. Open **Liquid Glass Wallpaper Studio** on your phone!

---

## Application Features

- **Realistic Liquid Glass Clock**: Direct digit refraction, Fresnel reflections, and specular caustics via OpenGL ES 3.0 shaders.
- **Clock Readability Slider (0% to 100%)**: Independent control with intelligent ambient contrast analysis for both bright and dark backgrounds.
- **Frosted Glass Strength (0% to 100%)**: Custom frosted intensity applied strictly to glass digits without rectangular panels.
- **Six Clock Styles**: Classic Digital, Stacked Clock, Minimal Digital, Large Typography, Thin Elegant, and Compact.
- **Independent Width & Height**: Stretch height or widen digits without locked aspect ratios.
- **Two-Image Depth Effect**: Automatic coordinate alignment, shared resizing, AI subject segmentation, and brush mask refinement.
- **Direct Wallpaper Setting**:
  - `WallpaperManager.FLAG_LOCK` applies directly to Android Lock Screen.
  - `WallpaperManager.FLAG_SYSTEM` applies directly to Android Home Screen.
- **Live Wallpaper Engine**: `LiquidGlassLiveWallpaperService` for continuous real-time clock rendering.

---

## Local Building with Android Studio (Optional)

If you decide to install Android Studio:
1. Open Android Studio -> **File -> Open...** -> select this project folder.
2. Wait for Gradle sync to complete.
3. Select **Build -> Build Bundle(s) / APK(s) -> Build APK(s)**.
4. The output APK will be at `app/build/outputs/apk/debug/app-debug.apk`.
5. Run on device via `adb install -r app/build/outputs/apk/debug/app-debug.apk`.
