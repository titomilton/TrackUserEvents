
TrackUserEvents
========
The TrackUserEvents is a library Android project to allow the developer track the user events in his application. Those events are sent to a Events REST API.

User Stories
--------
* As an app developer, I want to initialise the SDK with my API key.
* As an app developer, I want to track events with a custom name.
* As an app developer, I want to optionally add a list of key/value parameters to each event.
* As an app developer, I want any events which were tracked while the app was offline to be delivered when again online.
* As an app developer, I want to have a sample app that can be used to demonstrate the SDK functionality.

Setup
--------
1. Download the TrackUserEvents project.
2. Open the project in which you want to use the TrackUserEvents.
3. Import the TrackUserEvents module. Go to File -> New -> Import Module.
4. Choose the source directory of the TrackUserEvents. Uncheck the ":sample" project, leave only the ":library" checked.
5. In the gradle.build of your app project include this library.
```groovy
dependencies {
    ...
    compile project(':library')
}
```

Usage
--------
* To track a event:
```java
new TrackUserEvents(apiKey, context)
    .createEventByName(eventName)
    .addParameter("Param1", 1)
    .addParameter("Param2", "test")
    .addParameter("Param3", 18.39)
    .addParameter("Param4", true)
    .addParameter("YourObj", obj)
    .send();
```
* To deal with the tracked events while the app was offline
```java
// From time to time, check and dispatch the pending tracked events 
trackEvents.setAlarm(); 
```
```java
// to turn on this alarm
 trackEvents.cancelAlarm(); 
```