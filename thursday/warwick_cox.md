# Web Notifications

What abou tif the user can't / wont use your native app? They're not getting
notifications.

250 million push notifications sent per day.

## The Hook Model

Brings people back to your product.

[image here]

## Demo

https://warwickcox.com/

## How?

Service Workers

Like a native app, it can be not-open, but still listening for events.

Things you need:

* Secure server (HTTPS)
  * Stops Man In The Middle attacks
* Google Cloud Messaging
  * Gateway between you and the customers
  * Send a message to GCM, who will then handle distributing it to all your
    users
* Register your service worker:
  ```javascript
  if ('serviceWorker' in navigator) {
    navigator.serviceWorker.register('js/service-worker.js').then(function(registration) {
      // triggers the "all push notifications" popup
      // Gives a subscription ID, which we can store (in GCM)
      allowNotifications(registration)
    }).then(...);
  }
  ```
* Listen
  ```javascript
  self.addEventListener('push', function(event) {
    fetch('/API/endpoint/getPushData?subscription_id='+subscriptionId).then(function() { })
  });
  ```

  ```
  Send message          GCM        Browser
        | -------------> | --notif--> |
        |                | <---GET--- |
        |                | -- data -> |
  ```

Chrome only today.
Firefox is coming out.
Opera is working on it.
Safari is... its own beast.

## Best Practices

* Don't spam
* Let your customers decide the types of notifications they want

## Q&A

*Customization of the alert on the device?*

Other than the text; can send an icon, but that's about it so far.

*Does it work when the page is closed?*

With the old implementation, they have to be using the browser. But with the new
implementation, it'll work like native notifications on Android.

*What decides to show/not show when opt'd out?*

Your business logic, NOT GCM.

*How do you unsubscribe?*

In settings there's "Notifications" where you can opt-out. Or, kill the service
worker.
