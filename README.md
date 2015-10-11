# GradleBintray
Simple scripts for publishing to local Maven repository and to Bintray

## build.gradle

	ext {
	    // Where you will see your artifact in Bintray's web interface
	    // The "bintrayName" should match the name of the Bintray repro.
	    bintrayRepo         = 'maven'
	    bintrayName         = 'circularprogressview'
	    // Maven metadata
	    publishedGroupId    = 'momentum.modules'
	    // Save yourself a head ache, and set this equal to the name of the Android Studio library
	    // module. The artifact name needs to match the name of the library.
	    artifact            = bintrayName
	    // Library information
	    libraryName         = 'CircularProgressView'
	    libraryDescription  = 'A circular progressview for Android'
	    libraryVersion      = genVersionName()
	    librarylabels       = ['Android', 'view', 'progress']
	    // Developer stuff
	    developerId         = 'mlostek'
	    developerName       = 'Martin Mlostek'
	    developerEmail      = 'mlostek@gmail.com'
	    // Web stuff
	    siteUrl             = 'https://github.com/momentummodules/CircularProgressView'
	    gitUrl              = 'https://github.com/momentummodules/CircularProgressView.git'
	    issuesUrl           = 'https://github.com/momentummodules/CircularProgressView/issues'
	    // License stuff
	    licenseName         = 'The Apache Software License, Version 2.0'
	    licenseUrl          = 'http://www.apache.org/licenses/LICENSE-2.0.txt'
	    licenseShort        = 'Apache-2.0'
	}

	apply from: 'https://raw.githubusercontent.com/momentummodules/GradleBintray/master/maven.gradle'
	apply from: 'https://raw.githubusercontent.com/momentummodules/GradleBintray/master/bintray.gradle'


## local.properties

	bintray.user=<yourBintrayUser>
	bintray.apikey=<yourApiKey>
	bintray.gpg.password=<yourGpgPassword>

##  build.grade

	// Top-level build file where you can add configuration options common to all sub-projects/modules.
	buildscript {
	    repositories {
	        jcenter()
	    }
	    dependencies {
	        ...
	        classpath 'com.github.dcendents:android-maven-gradle-plugin:1.3'
	        classpath 'com.jfrog.bintray.gradle:gradle-bintray-plugin:1.2'
	        ...
	    }
	}

	allprojects {
	    repositories {
	        jcenter()
	        mavenLocal()
	    }
	}
