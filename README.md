# se_ads_example

Presentation -> https://docs.google.com/presentation/d/1SWXVX0xzptQldHJDVbMN5vHuEi4Jn81O6sN8XtBgFvw/edit?usp=sharing

## Getting Started

1. Install Flutter SDK -> https://flutter.dev/docs/get-started/install
2. Install Android Studio -> https://developer.android.com/studio
3. Create an AdMob account -> https://admob.google.com/home/
4. Get Emulator to test
    * Open Android Studio
    * Click Conigure -> AVD Manager
    * Create Virtual Device
    * Start the virtual Device
5. Clone the Project from this commit--> https://github.com/Pascal798/eportfolio/tree/6eb789b1ba7fa88dc5b648c716360e22e590e319
6. Open it in IntelliJ
7. Choose in the Project Settings the Flutter SDK as Project SDK
8. run "flutter pub get"

=> If you need more help check https://flutter.dev/docs

## Task
If everything works, try to implement a bannerAd and interstitialAd. (you will not need a firebase account for testads but it is very useful to gather user data for real ads)

## Tutorial

1. Clone the project from this commit --> https://github.com/Pascal798/eportfolio/tree/6eb789b1ba7fa88dc5b648c716360e22e590e319

2. Go to Google AdMob --> https://admob.google.com/home/
	a. Add your app to AdMob by following the steps you will see when you click on add app
	![apps](https://github.com/Pascal798/eportfolio/blob/master/images/apps.png)
	![add apps](https://github.com/Pascal798/eportfolio/blob/master/images/add%20app.png)

	b. Click on create an ad unit
	![createAdUnit](https://github.com/Pascal798/eportfolio/blob/master/images/createAdUnit.png)
	
	c. Create an banner and interstitial ad unit by following the steps you will see in AdMob (this is only needed if you will use real ads not testads like in this tutorial)

	d. Save your appID (and adUnitId) for later

3. Goto to cloned project in your IDE

4. Go to the AndroidManifest.xml which you will find under android/app/src/main , add the following meta-key and insert your appId to the android:value property
![androidManifestMetaKey](https://github.com/Pascal798/eportfolio/blob/master/images/metakey.png)

5. Go to your pubspec.yaml and add the firebase_admob: dependency
![dependency](https://github.com/Pascal798/eportfolio/blob/master/images/dependency.png)

6. Run ``` flutter pub get ```

7. Go to your main.dart and import the firebaseAdMob package

8. Create a string constant testDevices with an empty string or the string "Mobile_Id"
![createTestDevice](https://github.com/Pascal798/eportfolio/blob/master/images/testDeviceConst.png)

9. Go to your State class in the main.dart and create the MobileAdTargetingInfo for your ads and add some properties for your ad (you need to add the testDevices property and give it your testDevice constant)
![MobileAdTargetingInfo](https://github.com/Pascal798/eportfolio/blob/master/images/mobileAdTargetingInfo.png)

10. Create two variables for bannerAd and interstitialAd
![createVariables](https://github.com/Pascal798/eportfolio/blob/master/images/createVariables.png)

11. Create the CreateMethods for your ads where you will return the ad with the needed properties (they need nearly the same properties apart from the size the interstitialAd doesnt need because it will always cover the whole screen)
![createBannerAd](https://github.com/Pascal798/eportfolio/blob/master/images/createBannerAd.png)
![createInterstitialAd](https://github.com/Pascal798/eportfolio/blob/master/images/createInterstitialAd.png)

(if you want to use a real ad you need to wait at least 48 hours (trust me it will take several days) and insert your adUnitId to the adUnitId property instead of the testUnitId like in the screenshot above)

12. Create the initState() method where you will initialize a FireBaseAdMob instance with your appID and the bannerAd by first loading it and then show it (interstitialAd will be initialized through a button later) 
![initState](https://github.com/Pascal798/eportfolio/blob/master/images/initState.png)

13. Dispose your ads by the dispose() method
![dispose](https://github.com/Pascal798/eportfolio/blob/master/images/dispose.png)

14. Go to the body of your page in the build() method and add a RaisedButton which will show the interstitialAd

15. Give the RaisedButton a text and an onPressed() method which will initialize the interstitialAd
![initInterstitial](https://github.com/Pascal798/eportfolio/blob/master/images/initInterstitial.png)

16. Run your app through an emulator (Android Studio) or your smartphone (enable USB-Debuggin) and watch your testAds