# Expo Linking API Android Background Deep Link Issue

This repository demonstrates a bug in Expo's `Linking` API on Android. When the app is in the background, the `Linking.addEventListener` function for handling deep links does not always fire reliably. This results in the app missing deep link events and not executing the expected behavior.

## Bug Description:
The `Linking.addEventListener` is intended to listen for deep links, even when the application is in the background on Android. However, in practice, this listener often fails to trigger, leading to inconsistent functionality.

## Reproduction Steps:
1. Clone this repository.
2. Run the app on an Android device or emulator.
3. Send a deep link to the app while it's in the background.
4. Observe that the `onReceiveDeepLink` function (within `bug.js`) is not called as expected.

## Solution:
The solution involves using a combination of approaches, such as checking for initial URLs upon app launch and employing a more robust event listening mechanism (as demonstrated in `bugSolution.js`)