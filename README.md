# ShareMyRevenue
*Share a percentage of your revenue among your users, grow your company!* 

*By simply logging their interactions.*

<b> Add ShareMyRevenue to your project</b>

```
allprojects {
    repositories {
        ...
        maven { url 'https://jitpack.io' }
    }
}
	
dependencies {
    compile 'com.github.sayemkcn:ShareMyRevenue:v0.6-beta'
}

```

<b>Register</b>


*You have to register our website to get client_id and client_secret for your app*

[Register Here](https://smr.toracode.net)

Click 'Show' button to copy your client id and secret.

![Alt text](https://i.imgur.com/apsUw6h.jpg "ShareMyRevenue")

<b>Initialize ShareMyRevenue</b>

```
    // On your application class
    User user = new User("Name", "username", "email", "password");
    SMR.initialize(getApplicationContext(), "client_id", "client_secret", user);
```

###Now you just have to log user interactions

<b>Create Events</b>

```
    EventFactory.getInstance().createEvent(Event.Type.USER_EVENT, "event_code", "event_tag", Event.Weight.NORMAL):
```

You can create as much events as you want for future use. All of the events will be registered to <b>EventRegistry</b>.

You can find any specific event by tag or event code. (You should always get events from the registry instead of creating one every time)

```
    Event e = EventRegistry.getInstance().getEventByTag("event_tag");
```

<b>Log User Interactions</b>

```
    SMR.logOnline(MainActivity.this, e);
```


Whoolala you're a sperstar now!!!
But it's not all over yet, We've a dashboard for you on our [Website](https://smr.toracode.net) to manage your users, Share your revenues, resolving payment requests and so on!
If you find any trouble integrating our api, Please contact me by [email](email@rimon.xyz) at any time. I'm looking forward to help you with my best efforts.

God Bless you.
