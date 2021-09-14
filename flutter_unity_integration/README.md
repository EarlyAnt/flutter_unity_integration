# flutter_unity_integration

Demostrates how to integrate unity with flutter.

## Getting Started

[flutter_configs]
## android/app/build.gradle
dependencies {
    implementation project(':unityLibrary')     //add this line
    implementation "org.jetbrains.kotlin:kotlin-stdlib-jdk7:$kotlin_version"
}

## android/build.gradle
allprojects {
    repositories {
        flatDir {   //add this block
            dirs "${project(':unityLibrary').projectDir}/libs"
        }
        
        google()
        jcenter()
    }
}

## android/settings.gradle
//add these two lines
include ":unityLibrary" 
project(":unityLibrary").projectDir = file("./unityLibrary")
