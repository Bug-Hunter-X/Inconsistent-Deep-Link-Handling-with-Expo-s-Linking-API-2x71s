# Inconsistent Deep Link Handling with Expo's Linking API

This repository demonstrates a common, yet difficult-to-debug issue with Expo's `Linking` API.  The `Linking.addEventListener` method, used to listen for incoming deep links, can exhibit inconsistent behavior, particularly when the app is in the background or has been terminated by the OS. This leads to deep links being missed, causing unexpected application behavior.

## Problem

The core problem lies in the reliability of `Linking.addEventListener`.  While generally working in simple scenarios, this method's behavior can be unreliable under certain conditions, making deep link handling unpredictable.

## Solution

The provided solution attempts to mitigate the inconsistency by implementing a more robust approach to deep link handling, primarily relying on checking for initial URLs on app launch and using a background task to ensure the app can handle incoming deep links regardless of its current state.