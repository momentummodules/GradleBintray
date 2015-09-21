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

	    libraryName         = 'CircularProgressView'
	    libraryDescription  = 'A circular progressview for Android'
	    libraryVersion      = genVersionName()
	    librarylabels       = ['Android', 'view', 'progress']

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


## local.properties

	bintray.user=<yourBintrayUser>
	bintray.apikey=<yourApiKey>
	bintray.gpg.password=<yourGpgPassword>
