---
title: CrashReport

search: true
---

# CrashReport

Report crashes as they happen or shake to document bugs!

CrashReport streamlines mobile bug and crash reporting for your QA team. Begin a report automatically upon crash or shake the device to manually start a report. Reports include can include logs, annotated images, and descriptions.

## Features

CrashReport has two main features: crash reporting and bug reporting.

### Crash Report

1. Crashes are automatically detected by CrashReport.

2. When a crash is detected, the `Format Report` screen is opened. From here, a title and description can be added along with any images included via the gallery picker. These fields are all optional.

3. Tap the send icon in the top right to send crash logs and any additional information included to your endpoint.

![Crash](https://i.imgur.com/3D6vr80.png)

### Bug Report

1. When a shake is detected, CrashReport captures a logcat snapshot, takes a screenshot, and displays the screenshot in the `Edit Image` screen.

2. Screenshots can be edited with basic annotation tools. 
* Choose a tool with the FAB menu in the bottom right. 
* Delete any annotations by dragging them to the trashcan that appears in the bottom left. 
* Undo or redo annotations by tapping the corresponding toolbar icons.

3. Tap the checkmark in the top right to proceed to the `Format Report` screen. The annotated screenshot will be automatically added to the report. Optionally, a title, description, and additional images can be added here.

4. Tap the send icon in the top right to send the logcat snapshot, attached images, and any additional information included to your endpoint.

![BugReport](https://i.imgur.com/0QdChk8.png)

## Getting started

```
// Step 1.
dependencies {
    implementation 'com.github.pqalab:crashreportandroid:{latest-version}'
}
```

To use CrashReport in your Android application, you must complete these two steps:

1. List CrashReport in your build.gradle file -

2. For this step, a custom `Application` class is required. In the `onCreate()` method of your custom `Application` class, create a `Reporter` object and then `init()`:

```java
// Step 2.
public class CustomApplication extends Application {

    @Override
    public void onCreate() {
        super.onCreate();

        Reporter reporter = new Reporter(this);
        reporter.init();

    }
}
```
