# Ionic Angular Photostore

App to take, store and display photos using the [Ionic 5 framework](https://ionicframework.com/docs).

## Table of contents

* [General info](#general-info)
* [Screenshots](#screenshots)
* [Technologies](#technologies)
* [Setup](#setup)
* [Features](#features)
* [Status](#status)
* [Inspiration](#inspiration)
* [Contact](#contact)

## General info

## Screenshots

![Home Page](./img/home-page.png)

## Technologies

* [Ionic/angular v5.7.0](https://www.npmjs.com/package/@ionic/angular)

* [Ionic v5.7.0](https://ionicframework.com/)

* [Angular v8.0.0](https://angular.io/)

* Ionic DevApp, to allow app to run on an iOS or Android device.

* [Cordova-sqlite-storage v3.2.0](https://www.npmjs.com/package/cordova-plugin-sqlite), an Ionic Cordova Storage Plugin.

## Setup

* To start the server on _localhost://8100_ type: 'ionic serve'

* The Ionic DevApp was installed on an Android device from the Google Play app store.

## Code Examples

```typescript
* takePicture() {
    const options: CameraOptions = {
      quality: 100,
      destinationType: this.camera.DestinationType.DATA_URL,
      encodingType: this.camera.EncodingType.JPEG,
      mediaType: this.camera.MediaType.PICTURE
    };

    this.camera.getPicture(options).then((imageData) => {
      // Add new photo to gallery
      this.photos.unshift({
        data: 'data:image/jpeg;base64,' + imageData
      });

      // Save all photos for later viewing
      this.storage.set('photos', this.photos);
    }, (err) => {
     // Handle error
     console.log('The is a camera error: ' + err);
    });

  }

  loadSaved() {
    this.storage.get('photos').then((photos) => {
      this.photos = photos || [];
    });
  }

```

## Features

* Displays photos taken.

## Status & To-do list

* Status: Working app. Tab 2 has access to a phone camera and it stores & displays the photos taken. There are still tabs 1 and 3 to develop.

* To-do: Add a lot more detail/styling to front page.

## Inspiration

* [ionic Docs](https://ionicframework.com/docs/)

* ['Your First Ionic App - Framework v4'](https://ionicframework.com/docs/developer-resources/guides/first-app-v4/intro).

## Contact

Repo created by [ABateman](https://www.andrewbateman.org) - feel free to contact me!
