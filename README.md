# QChat

## a static android project analogous to qq

### kotlin | compose

#### project configuration

```
//build.gradle -- project
buildscript {
    ext {
        compose_version = '1.3.2'
    }
}// Top-level build file where you can add configuration options common to all sub-projects/modules.
plugins {
    id 'com.android.application' version '7.4.1' apply false
    id 'com.android.library' version '7.4.1' apply false
    id 'org.jetbrains.kotlin.android' version '1.7.20' apply false
}
```

```
//build.gradle -- module
buildscript {
    ext.kotlin_version = '1.7.20'
    repositories {
        google()
        jcenter()
    }
    dependencies {
        classpath "org.jetbrains.kotlin:kotlin-gradle-plugin:$kotlin_version"
        classpath "org.jetbrains.kotlin:kotlin-android-extensions:$kotlin_version"
    }
}
plugins {
    id 'com.android.application'
    id 'org.jetbrains.kotlin.android'
    id 'kotlin-android-extensions'
}
android {
    namespace 'com.example.work_home'
    compileSdk 33
    defaultConfig {
        applicationId "com.example.work_home"
        minSdk 24
        targetSdk 33
        versionCode 1
        versionName "1.0"
        testInstrumentationRunner "androidx.test.runner.AndroidJUnitRunner"
        vectorDrawables {
            useSupportLibrary true
        }
    }
    buildTypes {
        release {
            minifyEnabled false
            proguardFiles getDefaultProguardFile('proguard-android-optimize.txt'), 'proguard-rules.pro'
        }
    }
    compileOptions {
        sourceCompatibility JavaVersion.VERSION_1_8
        targetCompatibility JavaVersion.VERSION_1_8
    }
    kotlinOptions {
        jvmTarget = '1.8'
    }
    buildFeatures {
        compose true
    }
    composeOptions {
        kotlinCompilerExtensionVersion '1.3.2'
    }
    packagingOptions {
        resources {
            excludes += '/META-INF/{AL2.0,LGPL2.1}'
        }
    }
    androidExtensions {
        experimental = true
    }
}
dependencies {
    def composeBom = platform('androidx.compose:compose-bom:2022.12.00')
    implementation composeBom
    androidTestImplementation composeBom
    // Choose one of the following:
    // Material Design 3
    implementation 'androidx.compose.material3:material3'
    // or Material Design 2
    implementation 'androidx.compose.material:material'
    // or skip Material Design and build directly on top of foundational components
    implementation 'androidx.compose.foundation:foundation'
    // or only import the main APIs for the underlying toolkit systems,
    // such as input and measurement/layout
    implementation 'androidx.compose.ui:ui'
    // Android Studio Preview support
    implementation 'androidx.compose.ui:ui-tooling-preview'
    debugImplementation 'androidx.compose.ui:ui-tooling'
    // UI Tests
    androidTestImplementation 'androidx.compose.ui:ui-test-junit4'
    debugImplementation 'androidx.compose.ui:ui-test-manifest'
    // Optional - Included automatically by material, only add when you need
    // the icons but not the material library (e.g. when using Material3 or a
    // custom design system based on Foundation)
    implementation 'androidx.compose.material:material-icons-core'
    // Optional - Add full set of material icons
    implementation 'androidx.compose.material:material-icons-extended'
    // Optional - Add window size utils
    implementation 'androidx.compose.material3:material3-window-size-class'
    // Optional - Integration with activities
    implementation 'androidx.activity:activity-compose:1.5.1'
    // Optional - Integration with ViewModels
    implementation 'androidx.lifecycle:lifecycle-viewmodel-compose:2.5.1'
    // Optional - Integration with LiveData
    implementation 'androidx.compose.runtime:runtime-livedata'
    // Optional - Integration with RxJava
    implementation 'androidx.compose.runtime:runtime-rxjava2'
    implementation "androidx.navigation:navigation-compose:2.5.3"
    implementation("androidx.constraintlayout:constraintlayout:2.1.4")
    // To use constraintlayout in compose
    implementation("androidx.constraintlayout:constraintlayout-compose:1.0.1")
    implementation("io.coil-kt:coil-compose:2.1.0")
    implementation 'androidx.compose.material:material-icons-extended:1.3.1'
    implementation "androidx.compose.runtime:runtime-livedata:1.3.3"
    implementation "com.google.accompanist:accompanist-pager:0.21.1-beta"
}

```

#### UI display

| ![](https://mybucket-wrq-n1.oss-cn-beijing.aliyuncs.com/1.png) | ![](https://mybucket-wrq-n1.oss-cn-beijing.aliyuncs.com/2.png) |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| ![](https://mybucket-wrq-n1.oss-cn-beijing.aliyuncs.com/3.png) | ![](https://mybucket-wrq-n1.oss-cn-beijing.aliyuncs.com/4.png) |

