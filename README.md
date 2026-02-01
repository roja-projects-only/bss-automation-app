# BSS Automation App

Android application for automating kick/ban commands in Bee Swarm Simulator on mobile devices.

## Requirements

- Android Studio Arctic Fox or later
- Android SDK 29+ (Android 10+)
- Kotlin 1.9.0+

## Setup

1. Open project in Android Studio
2. Sync Gradle dependencies
3. Build and run on device or emulator

## Configuration

The app requires configuration before use:

1. **Server URL**: Bridge server endpoint (e.g., `https://your-app.vercel.app`)
2. **API Key**: Authentication key for bridge server
3. **Chat Coordinates**: Screen coordinates for chat input field
4. **Send Coordinates**: Screen coordinates for send button
5. **Polling Interval**: How often to check for commands (default: 3 seconds)

## Permissions

The app requires the following permissions:

- **INTERNET**: Network communication with bridge server
- **SYSTEM_ALERT_WINDOW**: Display coordinate capture overlay
- **FOREGROUND_SERVICE**: Run automation service in background
- **POST_NOTIFICATIONS**: Display service status notifications
- **BIND_ACCESSIBILITY_SERVICE**: Execute tap automation

## Usage

1. Launch app and go to Settings
2. Configure server URL and API key
3. Capture chat input and send button coordinates
4. Return to main screen
5. Enable accessibility service in Android settings
6. Start automation service
7. App will poll server and execute commands automatically

## Project Structure

```
bss-automation-app/
├── app/
│   ├── src/
│   │   ├── main/
│   │   │   ├── java/com/bss/automation/
│   │   │   │   ├── MainActivity.kt
│   │   │   │   ├── SettingsActivity.kt
│   │   │   │   ├── AutomationService.kt
│   │   │   │   ├── CoordinateCaptureOverlay.kt
│   │   │   │   ├── api/
│   │   │   │   │   ├── BridgeApi.kt
│   │   │   │   │   ├── ApiClient.kt
│   │   │   │   │   └── models/
│   │   │   │   ├── storage/
│   │   │   │   │   └── ConfigStorage.kt
│   │   │   │   └── utils/
│   │   │   │       └── Logger.kt
│   │   │   ├── res/
│   │   │   └── AndroidManifest.xml
│   │   └── test/
│   └── build.gradle
├── gradle/
├── build.gradle
├── settings.gradle
└── README.md
```

## Building Release APK

1. Update version in `app/build.gradle`
2. Configure signing in `app/build.gradle`
3. Build → Generate Signed Bundle/APK
4. Select APK and release variant
5. Sign with keystore
6. Install on LDCloud

## Testing

Run unit tests:
```bash
./gradlew test
```

Run instrumented tests:
```bash
./gradlew connectedAndroidTest
```

## LDCloud Installation

1. Build release APK
2. Upload APK to cloud storage or GitHub releases
3. Download in LDCloud browser
4. Install APK
5. Grant all required permissions
6. Configure coordinates for your screen resolution
7. Start service
