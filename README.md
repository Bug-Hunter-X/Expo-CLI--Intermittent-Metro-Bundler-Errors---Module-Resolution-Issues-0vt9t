# Expo CLI: Intermittent Metro Bundler Errors

This repository demonstrates a bug encountered while using the Expo CLI.  The issue involves intermittent Metro bundler errors that prevent the successful building and running of an Expo project. The errors relate to the inability of Metro to resolve dependencies that are correctly listed in `package.json` and seemingly installed correctly.

## Problem Description

The problem is characterized by inconsistent behavior. Sometimes, the project builds and runs without issues.  Other times, the Expo CLI throws an error during the build process, indicating that it cannot resolve a particular module even though the package is listed in `package.json` and `node_modules` appears to contain it.  The error messages are not very helpful in diagnosing the root cause.

## Reproduction Steps

1. Clone this repository.
2. Run `npm install` or `yarn install` to install the dependencies.
3. Run `expo start`.  Observe that the project may or may not build successfully.  Repeating this step may yield different results.

## Potential Causes

* **Caching Issues:**  Metro bundler's caching mechanism may be at fault.
* **Node Modules Corruption:** The `node_modules` directory may have become corrupted.
* **Concurrency Issues:** Concurrent operations during the build process might interfere.
* **Expo CLI Bugs:**  A bug within the Expo CLI or its interaction with the Metro bundler.

## Solution (see bugSolution.js)

The solution involves a combination of techniques to work around the issue.  These include clearing the cache, cleaning and reinstalling dependencies, and potentially restarting the system.