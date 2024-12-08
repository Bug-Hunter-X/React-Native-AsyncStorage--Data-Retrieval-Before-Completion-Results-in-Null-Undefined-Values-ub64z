# React Native AsyncStorage Data Retrieval Bug

This repository demonstrates a common bug encountered when using AsyncStorage in React Native. The problem occurs when trying to access data from AsyncStorage before the asynchronous storage operation has completed, leading to unexpected null or undefined values.

## Bug Description
The bug stems from the asynchronous nature of AsyncStorage's `setItem` and `getItem` methods.  If you attempt to retrieve data using `getItem` before `setItem` has finished writing the data, you'll get an incorrect result. This is especially problematic because the error is not always consistent, making it harder to debug.

## Reproduction
The `bug.js` file provides a minimal reproducible example that showcases this behavior.

## Solution
The `bugSolution.js` file presents a solution using Promises or async/await to ensure that data retrieval happens only after the storage operation is complete. This avoids the race condition and guarantees that you'll get the correct data.

## How to Run
1. Clone this repository.
2. Run `npm install` to install dependencies.
3. Run `npx react-native run-android` (or `npx react-native run-ios`) to run the app on your device or emulator.