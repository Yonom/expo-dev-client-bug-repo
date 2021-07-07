# expo-dev-client bug report

This repository was initialized with crna and upgraded to react-native 0.64. Then, expo-dev-client was installed into the repository.

To reproduce the error:

- clone the repository
- run `yarn install`
- run `expo run:ios`

## iOS Test: failed

Running `expo run:ios` fails with the following error message:

```
❌  (node_modules/expo-dev-launcher/ios/Errors/EXDevLauncherRedBox.m:139:16)

  137 |   }
  138 |   
> 139 |   [self.logBox hide];
      |                ^ no visible @interface for 'RCTLogBox' declares the selector 'hide'
  140 |   dispatch_async(dispatch_get_main_queue(), ^{
  141 |     [[EXDevLauncherController sharedInstance].errorManager showErrorWithMessage:[self stripAnsi:message] stack:stack];
  142 |   });
```

Tested on macOS 11.4, Intel, Xcode 12.5, Cocoapods 1.10.1, node v16.4.2.

Expected behavior: build succeeds.

## Android Test: success

-