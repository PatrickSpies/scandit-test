# Reproduction for build-error with scandit-cordova-plugins v6.18.0
Reproduction is based on scandit-sample [BarcodeCaptureSimpleSample](https://github.com/Scandit/datacapture-cordova-samples/tree/master/BarcodeCaptureSimpleSample) with additional plugin `cordova-plugin-camera`.

To reproduce:
- Run `npm install`
- Run `cordova platform add android`
- Run `cordova build android`  
Build will error with
```
> Task :app:checkDebugAarMetadata FAILED
FAILURE: Build failed with an exception.
* What went wrong:
Execution failed for task ':app:checkDebugAarMetadata'.
> Could not resolve all files for configuration ':app:debugRuntimeClasspath'.
   > Could not resolve androidx.core:core:1.6.+.
     Required by:
         project :app
      > Failed to list versions for androidx.core:core.
         > Unable to load Maven meta-data from https://gitlab.scandit.com/api/v4/projects/1306/packages/maven/androidx/core/core/maven-metadata.xml.
            > Could not GET 'https://gitlab.scandit.com/api/v4/projects/1306/packages/maven/androidx/core/core/maven-metadata.xml'.
               > Connect to gitlab.scandit.com:443 [gitlab.scandit.com/85.195.222.114] failed: connect timed out
   > Could not resolve com.google.android.gms:play-services-location:16.+.
     Required by:
         project :app
      > Skipped due to earlier error
      > Failed to list versions for com.google.android.gms:play-services-location.
         > Unable to load Maven meta-data from https://gitlab.scandit.com/api/v4/projects/131/packages/maven/com/google/android/gms/play-services-location/maven-metadata.xml.
            > Could not GET 'https://gitlab.scandit.com/api/v4/projects/131/packages/maven/com/google/android/gms/play-services-location/maven-metadata.xml'.
               > Connect to gitlab.scandit.com:443 [gitlab.scandit.com/85.195.222.114] failed: connect timed out
```