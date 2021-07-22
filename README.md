# sofle
Tracking my adventures in split-keyboard land with the Sofle V2

## About Me (Context)

I haven't soldered anything for over a decade, I've never had a split keyboard, and I've never even used a keyboard with layers, let alone worked with QMK. I'm very excited to be doing all of it simultaneously for this project... but I want to warn folks that you should probably take whatever you find here as entertainment more than guidance, at least until I post something that actually works.

Additionally, I'm drawing heavy inspiration from [tomsaleeba/ergoslab](https://github.com/tomsaleeba/ergoslab) as well as the original [josefadamicik/SofleKeyboard](https://github.com/josefadamcik/SofleKeyboard) projects, as well as other layouts I find as I look around.

## Goals

1. Design must support the way I game
    - I'd prefer WASD being shifted to the right, instead of me having to shift my hand to the left.
    - I need modifiers/hotkeys/numbers accessible from that standard position
    - I need to be able to quickly type trash talk, and moving my hands around is annoying
2. Design must support the way I code
    - Obviously, this means easy/fast access to backspace/delete/ctrl-z... you get the idea
    - I use VIM (shut up, I like it), so modifier keys need to be accessible
    - I really like how the [Ergoslab](https://github.com/tomsaleeba/ergoslab) treates brackets, keeping them clustered
3. Design can't force me to learn too much simultaneously (I'm not a smrt person)
    - I feel like I'd benefit from Dvorak or another key layout, but if I'm being honest it'll be hard enough to re-learn where backspace and escape have gone.

## Story so far

It took ~1m for my order to arrive from Vietnam, but everything in the pack [looked
great](https://photos.google.com/share/AF1QipPytwYjRgQrpOThUrlPG6qWIp5S8OndPnbsrqexxPabXPODnWopA66ABG0FQe4cjA/photo/AF1QipOLf71KHD0AHQfH8aAGOZoiONlIs6fTBdzb7Oof?key=UEFEb0ZQUkVDN1NiWVA3SVlDRjFIbkpuM2VZZ2d3).

I didn't take build pictures (my excuse was that the [Build
Guide](https://josefadamcik.github.io/SofleKeyboard/build_guide.html) is great and I didn't really
have more to offer, but honestly I was just super excited to get going), but my n00b learnings are:

- Set your iron to ~600°F to start (if you can adjust the temp)
- Don't be afraid to hold the iron to the PCB solder points for a bit; once they get hot enough the
    solder will literally flow from your iron into the joint.
- If the solder flows, but still makes a ball, you need more flux. I started with [Pen
    flux](https://www.amazon.com/gp/product/B07B53LNGX/ref=ppx_yo_dt_b_asin_title_o05_s00?ie=UTF8&psc=1),
    but I never felt like it was helping. Very possible that the problem was user-related, so
    I ordered some [Paste
    Flux](https://www.amazon.com/gp/product/B008ZIV85A/ref=ppx_yo_dt_b_asin_title_o02_s01?ie=UTF8&psc=1)
    to see if my monkey brain had better luck.
- If you have to use desoldering wick (I really, really hope you don't):
  - Always use the tip of the wick to start; if a lot is coming off the joint, try to move up the
      wick
  - Trim it between uses
  - **CAUTION: I DON'T KNOW FOR SURE THAT THIS IS GOOD ADVICE** Try to get the thing you're
      desoldering flat - desolder around pins, clip them, then finish desoldering while pushing the
      pin through the hole.
  - NEVER FORCE A PIN THROUGH
    - If it doesn't slip through easily, trim the wick and try again. Forcing a pin can rip out the
        contacts from the board - iz bad

I started on the right-hand side and my first dozen joints were diodes and were slow and awful
anyway. I didn't realize at the time, but I wasn't holding the iron to the board long enough to heat
the contact, so I ended up with [diodes doing
wheelies](https://photos.google.com/share/AF1QipPytwYjRgQrpOThUrlPG6qWIp5S8OndPnbsrqexxPabXPODnWopA66ABG0FQe4cjA/photo/AF1QipOyuV-xTKoda2hnScNfeE0UPADTrEcmlmQ0OBOs?key=UEFEb0ZQUkVDN1NiWVA3SVlDRjFIbkpuM2VZZ2d3).

After a few mistakes and getting the hang of it a bit, I circled back around to fix them... don't do
that. Mark the bad ones with tape or something, finish the step your on (in my case, do the rest of
the diodes) and THEN come back - when you think you have enough experience to fix something, get 50%
more experience and then try.

Anyway, next was the hot swap switch sockets, which is where I first saw the "solder flow" thing I
mentioned above; that was when the process really clicked for me... which is good because when I
ultimately got to soldering the MCU on it wasn't _as_ terrifying.

I tried to flash the right side, but none of the switches worked; I figured it was because it wasn't
the "master" side, so I kept soldiering on.

The left-side went quickly and smoothly, and flashing it worked immediately... but the right never
worked.

Thanks to the kind people on Reddit's [olkb subreddit](https://www.reddit.com/r/olkb), I got enough
info to believe that the MCU was either broken or incompatible. I later determined that, based on
the unit not updating its name on flash, there was something borked with the MCU.

I desoldered the MCU ([wow did
that](https://photos.google.com/share/AF1QipPytwYjRgQrpOThUrlPG6qWIp5S8OndPnbsrqexxPabXPODnWopA66ABG0FQe4cjA/photo/AF1QipNo28zbPFFA4ndrwGKWFcjzPhja6jrx9gsR8F8W?key=UEFEb0ZQUkVDN1NiWVA3SVlDRjFIbkpuM2VZZ2d3)
suck a [whole
lot](https://photos.google.com/share/AF1QipPytwYjRgQrpOThUrlPG6qWIp5S8OndPnbsrqexxPabXPODnWopA66ABG0FQe4cjA/photo/AF1QipMF6_peTZqLH6qSf1AQFrIG8laHn6n3-_RGKQ2F?key=UEFEb0ZQUkVDN1NiWVA3SVlDRjFIbkpuM2VZZ2d3)
and make [my PCB super
sad](https://photos.google.com/share/AF1QipPytwYjRgQrpOThUrlPG6qWIp5S8OndPnbsrqexxPabXPODnWopA66ABG0FQe4cjA/photo/AF1QipPE_pQJLTUqZGqHJGuis652Qns9bDk8m1QzN9C5?key=UEFEb0ZQUkVDN1NiWVA3SVlDRjFIbkpuM2VZZ2d3)),
and mounted some [round header
sockets](https://www.amazon.com/gp/product/B07BRYLMK8/ref=ppx_yo_dt_b_asin_title_o00_s00?ie=UTF8&psc=1).
I linked to the things I SHOULD have bought the first time, but didn't. No, the first time I just
bought the "female" round sockets, not realizing that the PINS ARE ROUND, TOO, so all the
square-pegged male connectors I have won't work.

This is where I'm at as of 2021/07/13. To Be Continued.

## 2021/7/19
I'm actually (slowly) typing this from the Sofle!

The pins that I mentioned in the last update arrived and I discovered that some projects use a _pin
pitch_ (distance between the pins) of 2.54mm (like most Arduino/Pro-Micro projects), and others use
2.0. As you might imagine, they are not compatible. And yes, I had ordered the wrong pins, so I
ordered the correct pins and told my brother about my HILARIOUS escapades.

I also told him that, knowing myself, I'd likely also give in to the urge to make the halves
symmetric by removing the ProMicro from the Left side, too, and socketing it. He offered to save me
from myself and remove the board for me.

In retrospect, it was probably the decision that saved the largest amount of time in the whole
project. He picked up the board in the morning, and had it back to me at the exact same time as the
correct pins.

I deftly soldered the sockets into the PCB, the headers onto the ProMicros, and put it all together to
FINALLY see the right-half SEND KEYSTROKES!

You know, only when connected via USB. When connected via TRRS nothing would be sent. [Heading back
to reddit](https://www.reddit.com/r/olkb/comments/om5bds/sofle_v2_trrs_troubleshooting_help/) got me
pointed in the right direction and I was able to figure out that while I was desoldering the
ProMicro from the right side I destroyed the trace for the D2/Rx pin on the PCB. The bright side of
this as a failure point is that solution was simply soldering a wire from the TRRS pad to the pin
itself. TODO PUT IMAGE HERE

And now everything works! TODO: PUT IMAGE HERE!

## Observations

### Hurdles

I learned to type wrong, I think. I frequently used my right index finger to press `b`, but with the
sofle that'd be quite a reach :)

That's a pretty small issue, though, when compared to the fact that I've ALWAYS used my left pointer
finger to push `c`. This dramatically throws off `c`, `v`, and `b` in an Ortho layout. That'll be
the largest learning curve in this process.

Other complications are remembering that my left thumb can't hit `space` (resulting in a lot of
prematurely sent messages), and attempting to hit the old locations for `ESC` and `BACKSPACE`.

I'd really like to be able to flash both sides of the keyboard without flipping cords around.

### Victories

The biggest wins so far are mostly on the **MOUSE** layer, which is a bit surprising considering how
busy that layer ended up being. Controlling the mouse with `WASD`-type controls (`ESDF`,
technically) is incredibly useful, and having `HJKL` as arrow keys is everything I'd hoped it would
be.

Also, flashing the firmware quickly means that I don't ingrain any bad habits by using the wrong
keys for too long. I do wish I could flash both keyboards without having to play musical chairs with
cords, but ¯\\_(ツ)\_\/¯.

And good goat do my back and neck feel better already. Like, **__WAY__** better.

## First layout

## First layout - DRAFT

I created this layout while planning the build; see if you can spot the differences!
#nerdSpotTheDifference

After working with [Keyboard Layout Editor](http://www.keyboard-layout-editor.com) and [QMK Configurator](https://config.qmk.fm) to try things out, I've made a few decisions/discoveries:

1. Shifting the alpha keys up to the top row like the [Ergoslab](https://github.com/tomsaleeba/ergoslab) ended up being too much for me to grok as a first layout - I couldn't figure out how to utilize 2 bottom rows of modifiers, plus an extra set of keys (5x5+1 vs 6x4+5) in a way that I thought I could adapt to. Additionally, not having a number row above wouldn't work for gaming without significant retraining, and shifting my hands for the two modes goes against Goal 1.
2. I'm going to have some repetition in my design - There will end up being multiple ways to type numbers, symbols, etc. - I'm just not aware yet of what will work well for me.
3. I have a lot of baggage I'm carrying with me; my first design kept backspace and Esc in their standard pinky-positions, for example. I've needed to adopt the "Demote the Pinkies, promote the Thumbs" mantra.

So, here's where I'm at, and thoughts on why:

## Keycaps

![image](https://user-images.githubusercontent.com/15177870/121795611-f1cbbb00-cbd7-11eb-853f-a9d51dadce1c.png)

[Key caps from kbdfans](https://kbdfans.com/products/pbt-sa-control-code-keycaps-set)

NOTE: After receiving them I found that they don't have a homing mark on `F` and `J`. After looking
around I found two options: [Ball Bearing
Mods](https://blog.techotom.com/post/2018-02-03-ball-bearing-homing-bumps-on-keycaps/) (which seem
like an awesome-but-more-destructive-than-I-want for these caps) and [Just use a piece of
tape](https://superuser.com/questions/212968/what-is-the-best-way-to-create-tactile-bumps-on-your-keyboardhttps://superuser.com/questions/212968/what-is-the-best-way-to-create-tactile-bumps-on-your-keyboardhttps://superuser.com/questions/212968/what-is-the-best-way-to-create-tactile-bumps-on-your-keyboardhttps://superuser.com/questions/212968/what-is-the-best-way-to-create-tactile-bumps-on-your-keyboardv).

I'm going with the tape option for now, but that ball-bearing idea is intriguing.

21/07/21 - Tape came off while playing games. Only used scotch tape, so maybe another type would
work.

### Layer 0 (ALL YOUR BASE ARE BELONG TO KEEB)

![image](https://user-images.githubusercontent.com/15177870/121794591-2e46e900-cbcf-11eb-8522-e57fb509029f.png)

1. Top left will take you to the very lightly populated "Media" layer, followed by standard numerics without "+/="
1. On my current layout, CAPS is mapped to Alt for use in tmux; the (T:Tab, H:Alt) key is to support that usage and get me used to Tap/Hold. Rest of row is pretty standard
1. No surprises here
1. Again, nothing shocking
1. I don't have the keyboard in-hand yet, so I'm working off approximations on how these keys will feel to reach for; The outside keys will, I'm assuming, be a bit awkward to hit without changing wrist position, so these are straight toggles to the NUMPAD layer (left) and GAME layer (right). 
  - Left Side: The OS and Alt keys are pretty close to where they normaly are, then we have (T:Esc,H:SymbolLayer) and a big Space for Thumb Promotions
  - Right Side: (T:Enter,H:GUI-Layer), Backspace, and Delete are three more Thumb Promotions. The [Alt+Tab] Combo key is because I **THINK** the GUI layer is going to end up too much for me to process, so I might need another layer toggle. Until then, though - Window flipper

### Layer 1 (GUI - Or "What if a full keyboard vomitted on a split keyboard....")

![image](https://user-images.githubusercontent.com/15177870/121795671-89c9a480-cbd8-11eb-8cf0-38b818c13cb5.png)

I know, there's a lot on this layer... STOP YELLING AT ME I KNOW.

TL;DR - This layer is for parens while coding, arrows when using web forms or whatever, and mouse controls if I can learn them. Fn keys are an easy win, and the brown keys are for changing machines via KVM. The red keys are ¯\\_(ツ)_/¯.

- Purple: These two map directly to the angle braces from Layer 0: each different set of "braces" are in this position on different layers
- Green+Orange: This layer started out as a Fn-key layer (orange is KVM controls), but my ape brain said it they looked lonely...
- Blue: So, I added somthing I've been thinking about for a while: Arrow keys where VIM arrows go! But then I looked around the arrow keys...
- Red: Probably need to put the other keys from that area somewhere, too

So, at this point I had to ask myself when I planned to use this layer - Fn keys were easy to remember, and keyboard swap made sense with them. Parens were part of a larger system for coding, and the arrow keys I've been thinkin about for a while; none of those seemed too bad. The red keys... well, they're kinda filler (heck, the dial on the left will be page up/down)... But my WASD section is wide open... and a few on the right...

Yellow: PERFECT PLACE FOR MOUSE CONTROLS!

### Layer 2 (Symbols - Or "Soft-delete the top row")

![image](https://user-images.githubusercontent.com/15177870/121795436-6f8ec700-cbd6-11eb-9e40-97e9e6836fe4.png)

You'll see the square/curly braces in their spot, and I opted to put the pipe/slash by them for easy access. The lonely underscore in the top right makes sense if you realize Base0 in that spot is "-/\_", and I thought that "+/=" made sense to be close by. Really, though, this is me trying to see if I can make use of having the symbols and numbers closer to homerow.

### Layer 3 (Media - Or "Top-left is a long reach")

![image](https://user-images.githubusercontent.com/15177870/121795473-edeb6900-cbd6-11eb-9084-ee9c86576105.png)

Volume, Play, and Next should all be handled by the right knob, but I don't know if the one I'm getting in the set pushes in, so this layer is insurance. It also has the reset button.

### Layer 4 (NumPad - Or "Career change to be an accountant")

![image](https://user-images.githubusercontent.com/15177870/121795510-3014aa80-cbd7-11eb-8e25-3a009a62e0d4.png)

This is the first of the two toggle layers; I don't foresee myself using it a lot, but after a few years of not having a number pad, I thought I'd see if I miss it enough to use it

### Layer 5 (Game - Or "You're not getting back into MMO's, are you?")

![image](https://user-images.githubusercontent.com/15177870/121795540-694d1a80-cbd7-11eb-81b6-f9f876c80b33.png)

WASD shifted to the right, Letters wrapped around, and modifiers keys moved as well. ESC back in "standard" location for now, might move to a thumb button, and I'm not sure if the number keys will shift like the letter keys or not yet. But it's a start. Hitting the right-most bottom buttom flips between layers for chat/typing.
