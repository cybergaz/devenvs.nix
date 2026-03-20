# Flutter Flakes

## Troubleshooting

### Android SDK not found at `ANDROID_HOME`

`flutter doctor` may report something like this:

```
[✗] Android toolchain - develop for Android devices
    ✗ ANDROID_HOME = /nix/store/.../android-sdk-env/share/android-sdk
      but Android SDK not found at this location.
```

Don't worry — your SDK is there. This is a Flutter/Nix quirk.

What's happening: Flutter is looking for the Android SDK at the path set in `$ANDROID_HOME`, but it can't find it — even though the SDK *is* actually installed there (platform-tools, build-tools and all). Flutter just hasn't been told that this Nix store path is the right one yet.

The fix is simple — just tell Flutter where to look:

```bash
flutter config --android-sdk $ANDROID_HOME
```

That's it. Flutter will remember this path and `flutter run` on physical Android devices should work as expected.
