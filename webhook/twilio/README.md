### Send SMS from Knowi using Twilio  

Things needed:

* Knowi Account
* Twilio Account 
* ngrok (for development)

But how does Knowi see our app?

Our app needs a publicly accessible URL. To avoid having to deploy every time we make a change, 
we’ll use a nifty tool called [ngrok](https://ngrok.com) to open a tunnel to our local machine.

Ngrok generates a custom forwarding URL that we will use to tell Knowi where to 
find our application. [Download ngrok](https://ngrok.com/download) and run it in your terminal on port 5000

```shell script
./ngrok http 5000
```

Now we just need to point a Twilio phone number, `TWILIO_ACCOUNT_SID`, and `TWILIO_AUTH_TOKEN` at our app. 
For reference, you can get this from your Twilio [Account Dashboard](https://twilio.com/console)

Punch in the URL for our message route that was generated by ngrok in your Knowi Webhook. It should look something 
like `http://your-ngrok-url.ngrok.io/sms`.

![](http://g.recordit.co/s4w3gBT2IC.gif)
