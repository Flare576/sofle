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

## First layout

After working with [Keyboard Layout Editor](http://www.keyboard-layout-editor.com) and [QMK Configurator](https://config.qmk.fm) to try things out, I've made a few decisions/discoveries:

1. Shifting the alpha keys up to the top row like the [Ergoslab](https://github.com/tomsaleeba/ergoslab) ended up being too much for me to grok as a first layout - I couldn't figure out how to utilize 2 bottom rows of modifiers, plus an extra set of keys (5x5+1 vs 6x4+5) in a way that I thought I could adapt to. Additionally, not having a number row above wouldn't work for gaming without significant retraining, and shifting my hands for the two modes goes against Goal 1.
2. I'm going to have some repetition in my design - There will end up being multiple ways to type numbers, symbols, etc. - I'm just not aware yet of what will work well for me.
3. I have a lot of baggage I'm carrying with me; my first design kept backspace and Esc in their standard pinky-positions, for example. I've needed to adopt the "Demote the Pinkies, promote the Thumbs" mantra.

So, here's where I'm at, and thoughts on why:

## Keycaps

![image](https://user-images.githubusercontent.com/15177870/121795611-f1cbbb00-cbd7-11eb-853f-a9d51dadce1c.png)

[Key caps from kbdfans](https://kbdfans.com/products/pbt-sa-control-code-keycaps-set)

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
