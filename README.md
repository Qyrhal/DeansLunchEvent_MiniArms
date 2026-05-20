# Dean's Lunch Event - Mini Arms Project

Alright fellas, buckle your seatbelts cuz Ekam's gonna take you on a journey through the wild world of ESP32s, screens, and robot arms. Let's get this party started! :)

## What Even Is This?

So this is basically the code for the mini robot arms demo at the Dean's Lunch Event. We've got ESP32s talking to each other over ESP-NOW like they're in some kind of secret club (because they are). Each screen controls a corresponding mini ESP32 that makes the robot arm do its thing.

**Good news:** Most of the work is already done for you. We're cool like that. ;) Each screen has been mapped to a specific ESP32 already—you can spot them by the tape and numbers we sloppily stuck on them. If yours is already labeled, just **skip straight to Step 4**.

## Step 1: Check If Your ESP32/Screen Has Been Tagged

Look at the ESP32s and screens. Do you see tape with numbers on them? If yes, you're in luck—someone already did the hard part. Skip to Step 4.

If you don't see any labels... well, buckle up, we're doing this the manual way.

## Step 2: Get Those MAC Addresses (The Boring But Necessary Part)

1. Open the `final_mac_addr` folder (aka the `get_mac_addr` folder... yeah, we know, we're working on the naming).
2. Flash the code to **both** your ESP screen AND the receiving ESP32.
3. Open the Serial Monitor (you might need to hit the restart button after flashing—don't be shy, press it).
4. Copy down those MAC addresses. Write them somewhere. Or text yourself. Whatever works. Just **don't lose them**. (Sorry, them's the rules.)

## Step 3: Flash the Final Code to the Screens

1. Open the `final` folder (yes, the folder with all the pretty UI stuff).
2. Open `final.ino`.
3. **Important:** Find the broadcast address in the code and change it to the MAC address of the **receiving** ESP32 that you just wrote down. This tells the screen "hey, send your messages to THIS guy."
4. **Flash it.** Watch the magic happen. (Or watch it fail, in which case... check the MAC addresses again. It's always the MAC addresses.)

## Step 4: Flash the Receiver Code

1. Open the `receiving_test` folder.
2. Open `receiving_test.ino`.
3. **Change the receiving address** to the MAC address of the **screen** (the one you got in Step 2).
4. **DO NOT touch the master address.** It's already configured correctly. Mess with it and you'll break the whole thing. We mean it. :P

## Step 5: Test It Out

Hit the first two buttons on the screen. They should toggle the light on and off like the world's most satisfying light switch.

If the light turns on/off, you're officially a genius. If not, well... blame the MAC addresses. It's always the MAC addresses.

## What's Next?

If Eshal has been kind enough to bless us with the new code, she'll update it in this repo. When that happens, `receiving_test` gets replaced with the real deal—the code that'll actually communicate with the robot arm and make it move. So long, little test light. Hello, actual robot arm movement! :D

## Troubleshooting

- **Double-check your MAC addresses.** They are case-sensitive.
- If the Serial Monitor is showing gibberish, try a different baud rate (115200 typically works).
- If communication fails, press the reset button on the ESP32.

That's it! You're basically a ESP32 whisperer now. Go show everyone how cooooool you are by making lights blink and robots move. You got this! :D

If anything breaks... it's probably Eshal's fault. (IM KIDDING DONT KILL ME ESHAL)
