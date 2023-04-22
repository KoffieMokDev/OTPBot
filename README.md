# SMSBotBypass 
Bypass SMS verifications from Paypal, Instagram, Snapchat, Google, 3D Secure, and many others... using a python Bot or the private API.

It's really simple. Imagine that your friend got a Snapchat account, you try to reset his password using the sms system : 
- he's gonna receive the sms confirmation code.

Then, you use the bot (```OTP call 33612345678 snapchat```). The bot is gonna call him, using the snapchat service, ask for the code received. If he send the code using the numpad, then your gonna receive the code and be able to reset the password. It's like an automatic system for SE. 
    
# cmds

All the Admin commands :
  - ```OTP user add @user``` : allow someone to use the bot & the calls
  - ```OTP delete @user``` : remove someone or an admin from the bot
  - ```OTP info @user``` : get infos from a user

All the Users commands :
  - ```OTP secret yoursecretpassword @user```
  - ```OTP call phonenumber service``` or for example ```OTP call 33612345678 paypal``` : call the phonenumber using the bot and get the sms code

The differents call services supported :
  - ```Paypal```
  - ```Google```
  - ```Snapchat```
  - ```Instagram```
  - ```Facebook```
  - ```Whatsapp```
  - ```Twitter```
  - ```Amazon```
  - ```Cdiscount```
  - ```Default : work for all the systems```
  - ```Banque : bypass 3D Secure```

# How it works ?

1. When you do a ```OTP call 3312345678 paypal```, the Python Bot sends a post request to our private api, who is gonna save the call into our sqlite DB and send the call to our twilio API.
2. The Twilio API use our ```OTP status``` route to know what to do in the call, the status route returns **TwiML** code to Twilio.
3. The ```OTP status``` route returns the self hosted service song using the ```/stream/service route```. 
4. If the user enter the digit code using the numpad, the song stops, it thanks him for the code, and end the call.
5. The ```OTP status``` is **Status**.

# Prerequisite
- Python v3+ & NPM from the last version.
- git installed (not necessarily)
- Open your ports
- A twilio account
- Knowledge of Python

# Install

Install the dependencies

Start Install 

Start pot.py in cmd

```py bot.py```

Modify the config.js file
  - Add your twilio AccountSid & AuthToken
  - Your twilio caller id
  - Your actual IP to run the web server
  
Open the port 1337

To check if everything works fine, I did a full test system. If your Twilio account is not upgrade, before the test, go to the /test/call.js file and modify the phone number line 122 with your phone numer.

```npm test```

Download it by (https://www.#)

![image](https://user-images.githubusercontent.com/45340378/103482419-1f1e6c80-4de1-11eb-929b-6f34ca28499a.png)

Your private API now **works** !

Be carefull, you also need to change the TTS Language, go to https://www.twilio.com/console/voice/twiml/text-to-speech and change the TTS Language from English to French with the Lea voice.

# Disclaimer

Do not use it illegally. You could been arrested to use badly this code. Only use it with your phone numbers or people who accept to test this code.

# Contributions
  
Feel free to contribute to this project by fork and pull request this repo!
