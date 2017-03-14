---
title: Components Overview
permalink: fire-app-builder-interfaces-and-components.html
sidebar: fireappbuilder
product: Fire App Builder
toc-style: kramdown
github: true
---

Fire App Builder includes a number components that implement interfaces. The interfaces define the methods and fields in Fire App Builder; the components implement the interfaces with fully developed code.

To use the components, you don't need to write your own Java code. You just need to customize various string values that have been extracted out of the code into XML files.

The main interfaces include the following:

* **Ads Interface** (`IAds`): Used for displaying ads to users
* **Analytics Interface** (`IAnalytics`): Used for implementing analytics
* **Authentication Interface** (`IAuthentication`): Used for authenticating or authorizing user access to media
* **Purchase Interface** (`IPurchase`): Used for in-app purchasing
* **UAMP** (`UAMP`): Used for playing media

If you need a component that isn't available, you can create your own component that implements one of the interfaces.

* TOC
{:toc}

## Available Components and Interfaces {#componentgroups}

In Android Studio, you won't see all the components because the Fire App Builder sample app loads only a subset of the available components from the Fire App Builder library, as defined in your app's Gradle files. Only one component from each interface is loaded.

To view the available components on disk, you can browse (using Finder or File Explorer) to the folder on your computer where you downloaded the Fire App Builder project, or just refer to the information here.

## Authentication Components {#authenticationcomponents}

Authentication components allow you to identify and authorize users before they take an action in your app. You must have at least one authentication component loaded in your app. The authentication components implement the `IAuthentication` interface, which you can view in the AuthInterface folder. The following authentication components are available:

<table>
<colgroup>
   <col width="30%" />
   <col width="70%" />
</colgroup>
  <thead>
    <tr>
      <th>Component</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td span="markdown">[AdobepassAuthComponent][fire-app-builder-adobe-pass-auth-component]</a></td>
      <td>Uses Adobe Pass to authenticate users.</td>
    </tr>
    <tr>
      <td span="markdown">[FacebookAuthComponent][fire-app-builder-facebook-auth-component]</a></td>
      <td>Uses Facebook to authenticate users.</td>
    </tr>
    <tr>
      <td span="markdown">[LoginWithAmazon Component][fire-app-builder-login-with-amazon-component]</a></td>
      <td>Uses Login with Amazon to authenticate users.</td>
    </tr>
    <tr>
      <td span="markdown">PassThroughLoginComponent</td>
      <td>Used only if you don't want to use any other authentication component. Your app must load at least one authentication component loaded. This PassThrough Login Component component satisfies the authentication component requirement without affecting the user experience in your app. This component is loaded as the default authentication component in the app.</td>
    </tr>
  </tbody>
</table>

## Analytics Components {#analyticscomponents}

Analytics components track activities within your app and provide metrics for analysis. Analytics components implement the `IAnalytics` interface in the AnalyticsInterface folder. Loading an analytics component in your app is optional.

<table>
<colgroup>
   <col width="30%" />
   <col width="70%" />
</colgroup>
  <thead>
    <tr>
      <th>Component</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td span="markdown">[FlurryAnalyticsComponent][fire-app-builder-flurry-analytics-component]</a></td>
      <td>Uses Flurry Analytics to provide analytics.  By default, this component is loaded but not configured in the Fire App Builder sample app.</td>
    </tr>
    <tr>
      <td span="markdown">[OmnitureAnalyticsComponent][fire-app-builder-omniture-analytics-component]</a></td>
      <td>Uses Omniture to provide analytics.</td>
    </tr>
    <tr>
      <td span="markdown">[CrashlyticsComponent][fire-app-builder-crashlytics-component]</td>
      <td>Uses Crashlytics to provide analytics.</td>
    </tr>
    <tr>
      <td span="markdown">[GoogleAnalyticsComponent][fire-app-builder-google-analytics-component]</td>
      <td>Uses Google Analytics to provide analytics.</td>
    </tr>
    <tr>
      <td span="markdown">LoggerAnalyticsComponent</td>
      <td>The Logger Analytics Component is not intended to be used for actual analytics. Instead, this is a dummy analytics component that inserts log messages during events. If you’re not using any other analytics component, use Logger Analytics Component because at least one analytics component must be configured in your app. You can see the log messages triggered by the LoggerAnalytics component by searching for “loggeranalytics” in Logcat.</td>
    </tr>
  </tbody>
</table>


## Ads Components {#adscomponents}

Ads components refer to any components that show advertisements in your app. Ads components implement the `IAds` interface in the AnalyticsInterface folder. Loading an ads component in your app is required. The following ads components are available.

<table>
<colgroup>
   <col width="30%" />
   <col width="70%" />
</colgroup>
  <thead>
    <tr>
      <th>Component</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td span="markdown">[FreeWheelAdsComponent][fire-app-builder-freewheel-ads-component]</td>
      <td>Used for displaying Freewheel ads in your app.</td>
    </tr>
    <tr>
      <td span="markdown">[VastAdsComponent][fire-app-builder-vast-ads-component]</td>
      <td>Used for displaying VAST ads in your app.</td>
    </tr>
    <tr>
      <td span="markdown">PassThroughAdsComponent</td>
      <td>Used only if you don’t want to use any other ads component. Your app must load at least one ads component loaded. This PassThroughAds component satisfies the ads component requirement without affecting the user experience in your app.</td>
    </tr>
  </tbody>
</table>

If you don't want to use any of the authentication components listed in the preceding table, use the PassThroughAdsComponent. Your app must have at least one ads component loaded. This dummy component satisfies the ads component requirements without affecting the user experience in your app.

## Purchasing Components {#purchasingcomponents}

Purchasing components allow users to make payments to either rent or subscribe to content in your app. The purchasing components implement the `IPurchase` interface in the PurchaseInterface folder. Loading a purchasing component is required. If you don't want this component active, however, you can

The following purchasing components are available.

<table>
<colgroup>
   <col width="30%" />
   <col width="70%" />
</colgroup>
  <thead>
    <tr>
      <th>Component</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td span="markdown">[AmazonInAppPurchasingComponent][fire-app-builder-amazon-in-app-purchase-component]</a></td>
      <td>Uses Amazon In-App Purchasing to allow users to choose Daily Pass (24-hour access) or Go Premium (subscription) to view the media in your app. This component is loaded by default but set as disabled and not configured.</td>
    </tr>
  </tbody>
</table>


## Media Player Components {#mediaplayercomponents}

Media Player components control the media player that is used for media playback in your app. The media components implement the `UAMP` interface in the UAMP folder. (UAMP stands for Universal Android Media Player.) Loading a media component is required. The following media player components are available.

<table>
  <thead>
    <tr>
      <th>Component</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>[AMZNMediaPlayerComponent][fire-app-builder-amazon-media-player-component]</td>
      <td>Uses the Amazon Media Player, which is based on ExoPlayer. This component is loaded by default in Fire App Builder.</td>
    </tr>
    <!-- <tr>
      <td>[BrightCoveMediaPlayerComponent][fire-app-builder-brightcove-media-player-component]</td>
      <td>Uses the BrightCove media player. This is useful if your media is already tightly coupled with BrightCove.</td>
    </tr> -->
  </tbody>
</table>

## UI Components

The TVUIComponent isn't an optional component, as it contains much of the user interface and functionality for the app (other than the media player features). It's created as a component to allow for potentially adding additional UI components for other devices, such as tablets.


{% include links.html %}
