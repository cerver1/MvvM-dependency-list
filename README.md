# MvvM-dependency-list
List of dependencies for MvvM Architecture

viewBinding

    android {
        ...
       buildFeatures {
            viewBinding true
        }
    }
  
dataBinding

    android {
        ...
            buildFeatures {
                dataBinding true
            }
        }

        compileOptions {
            sourceCompatibility JavaVersion.VERSION_1_8
            targetCompatibility JavaVersion.VERSION_1_8
        }

        kotlinOptions {
            jvmTarget = JavaVersion.VERSION_1_8.toString()
    }
    
viewModel and LiveData commonly used

    dependencies {
        ...
        def lifecycle_version = "2.2.0"

        // ViewModel
        implementation "androidx.lifecycle:lifecycle-viewmodel-ktx:$lifecycle_version"
        // LiveData
        implementation "androidx.lifecycle:lifecycle-livedata-ktx:$lifecycle_version"
        }
        
viewModel and liveData

    dependencies {
            ...
        def lifecycle_version = "2.2.0"
        def arch_version = "2.1.0"

        // ViewModel
        implementation "androidx.lifecycle:lifecycle-viewmodel-ktx:$lifecycle_version"
        // LiveData
        implementation "androidx.lifecycle:lifecycle-livedata-ktx:$lifecycle_version"
        // Lifecycles only (without ViewModel or LiveData)
        implementation "androidx.lifecycle:lifecycle-runtime-ktx:$lifecycle_version"

        // Saved state module for ViewModel
        implementation "androidx.lifecycle:lifecycle-viewmodel-savedstate:$lifecycle_version"

        // Annotation processor
        kapt "androidx.lifecycle:lifecycle-compiler:$lifecycle_version"
        // alternately - if using Java8, use the following instead of lifecycle-compiler
        implementation "androidx.lifecycle:lifecycle-common-java8:$lifecycle_version"

        // optional - helpers for implementing LifecycleOwner in a Service
        implementation "androidx.lifecycle:lifecycle-service:$lifecycle_version"

        // optional - ProcessLifecycleOwner provides a lifecycle for the whole application process
        implementation "androidx.lifecycle:lifecycle-process:$lifecycle_version"

        // optional - ReactiveStreams support for LiveData
        implementation "androidx.lifecycle:lifecycle-reactivestreams-ktx:$lifecycle_version"

        // optional - Test helpers for LiveData
        testImplementation "androidx.arch.core:core-testing:$arch_version"
    }
    
Room
     
     // add the line below to the top of your build.Gradle(Module:app) screen
     apply plugin: 'kotlin-kapt'
    
    dependencies {
        ...
          def room_version = "2.2.5"
          implementation "androidx.room:room-runtime:$room_version"      
          implementation "androidx.room:room-ktx:$room_version"
          kapt "androidx.room:room-compiler:$room_version"

          // optional - RxJava support for Room
          implementation "androidx.room:room-rxjava2:$room_version"

          // optional - Guava support for Room, including Optional and ListenableFuture
          implementation "androidx.room:room-guava:$room_version"

          // Test helpers
          testImplementation "androidx.room:room-testing:$room_version"
    }
    
Coroutines 
    
    dependencies {
        ...
            //Coroutines
            def coroutines_version = '1.3.7'
            implementation "org.jetbrains.kotlinx:kotlinx-coroutines-core:$coroutines_version"
            implementation "org.jetbrains.kotlinx:kotlinx-coroutines-android:$coroutines_version"
            implementation "org.jetbrains.kotlinx:kotlinx-coroutines-play-services:1.1.1"
    }
    
Navigation

    //(Project:AppName)
    dependencies {
            ...
        def navigation_version = "2.3.0"
        classpath "androidx.navigation:navigation-safe-args-gradle-plugin:$navigation_version"
        }
        
    //(Module:app)
    dependencies {
            ...
      def nav_version = "2.3.0"
      
      implementation "androidx.navigation:navigation-fragment-ktx:$nav_version"
      implementation "androidx.navigation:navigation-ui-ktx:$nav_version"

      // Dynamic Feature Module Support
      implementation "androidx.navigation:navigation-dynamic-features-fragment:$nav_version"

      // Testing Navigation
      androidTestImplementation "androidx.navigation:navigation-testing:$nav_version"
    }
    
workManager

    dependencies {
            ...
        def work_version = "2.3.4"

        // Kotlin + coroutines
        implementation "androidx.work:work-runtime-ktx:$work_version"

        // optional - RxJava2 support
        implementation "androidx.work:work-rxjava2:$work_version"

        // optional - GCMNetworkManager support
        implementation "androidx.work:work-gcm:$work_version"

        // optional - Test helpers
        androidTestImplementation "androidx.work:work-testing:$work_version"
      }

paging 

    dependencies {
            ...
          def paging_version = "2.1.2"

          implementation "androidx.paging:paging-runtime:$paging_version" // For Kotlin use paging-runtime-ktx

          // alternatively - without Android dependencies for testing
          testImplementation "androidx.paging:paging-common:$paging_version" // For Kotlin use paging-common-ktx

          // optional - RxJava support
          implementation "androidx.paging:paging-rxjava2:$paging_version" // For Kotlin use paging-rxjava2-ktx
        }

preference

    dependencies {
            ...
        def preference_version = "1.1.1"
        
        implementation "androidx.preference:preference-ktx:$preference_version"
}

koin

    dependencies {
            ...
def kodein_version = '7.0.0'
    implementation "org.kodein.di:kodein-di-framework-android-x:$kodein_version"

}


