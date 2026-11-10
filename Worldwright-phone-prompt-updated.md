Written on 10 November 2026 by the build session (Claude Code, on the owner's Mac) for a second assistant that the owner will talk to on his phone.

------------------------------------------------------------------------

## Part 1. What I am asking you to do

You are about to talk with **Sebastiano, the owner of a game called Worldwright**. I am the assistant that builds the game on his Mac. I have the code and can run the game; you cannot see either. Everything you know about the game is in this document, so treat it as the whole truth about what exists today and do not assume anything it does not say.

**Your job is an interview, then a rewrite.**

1.  Read all of this document first.
2.  Ask the owner questions to find out what he wants changed, added, dropped or done sooner. Part 7 lists the questions that are already waiting for him; Part 6 lists choices I made without him that he may want to overturn. Start with whatever he brings up himself, then work through those.
3.  When he says he is done, give him back **this whole document, updated**, with Part 8 ("The owner's direction") filled in. He will send that back to me and I will build from it.

**How to talk with him.**

- He is **not a programmer**. Use plain words and short questions. One or two questions at a time, never a long list.
- He answers briefly and casually. When an answer could mean two different things, say back what you understood in one sentence and ask if that is right.
- He cares most about **how the game looks**, and above all that it **does not look AI-made**: no generic, generated-looking art or text. He dislikes visual clutter (see his own words in Part 5).
- He cannot show you the game unless he attaches screenshots. If he can attach pictures from `Docs/Screens` or a photo of his screen, ask for them when you discuss looks; otherwise rely on the descriptions here.
- Do not explain how things are programmed. Do not promise dates or times. You may say whether something is a small, medium or large piece of work, using the guide below.
- If he asks for something that is already planned for a later phase (Part 3), tell him which phase it is in and ask whether he wants it **sooner**, and if so what can wait.
- If he asks for something that conflicts with a decision in Part 4, say so plainly and ask whether he really wants to change that decision. He is allowed to; it is his game.
- Do not invent features, numbers or names. If he asks something this document does not answer, write it down as a question for me in Part 8.

**Rough size guide, so you can be honest about cost.**


| Kind of request                                                                                                                         | Size                                                    |
|-----------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------|
| Change colours, redraw one kind of thing (as I did with the mountains), change a number such as how fast fire spreads, rename something | Small: within one working session                       |
| A new screen or window, a new animal or people with its drawings, a new power, sound for one kind of thing                              | Medium                                                  |
| A whole new system (seasons, hunger and breeding, towns, religion, war, rewinding time)                                                 | Large: these are what the phases are made of            |
| Redesigning the whole interface                                                                                                         | Medium to large, and it needs his eye at several points |


**What to give back.** The full text of this document with these changes only:

- **Part 8 filled in**, following the template there. This is the part I will act on.
- In Parts 2 to 7, change nothing unless the owner tells you a statement is **wrong** (for example "no, that is not what I meant by cluttered"). Mark any such change with the word **CORRECTED:** at the start of the sentence so I can find it.
- Keep his exact words wherever he states a like or a dislike. Add them to Part 5.

------------------------------------------------------------------------

## Part 2. The game as it is today

### 2.1 What it is

Worldwright is a **god game seen from above, in pixel art**. You look down on a small world of land and sea. You can reshape the land, set fires, pour water and lava, and put creatures on it, and the world carries on by itself while you watch. The finished game is meant to be a "living history" simulator: peoples with needs, families, cultures, languages, religions, kingdoms and wars that arise without the player directing them, with the player as a god who can leave them alone, nudge them with miracles, or wreck everything. **Today only the first layer of that exists:** the world, the tools to shape it, fire and water and lava, and animals that move about.

It is built in the Unity engine (version 6.3) and all of its pictures are drawn by code I write; no art is downloaded.

### 2.2 Where the project stands

The work is divided into six phases. Each ends with a checkpoint where the owner looks and approves before the next begins.


| Phase                                          | What it adds                                                                                                                                                           | State                                                                                                                                                                        |
|------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Style test                                     | One sheet showing the art style                                                                                                                                        | **Approved** by the owner                                                                                                                                                    |
| 1\. Foundation and the living world            | The world, tools, fire/water/lava, moving creatures, saving                                                                                                            | **Approved** by the owner on 10 Nov 2026, after the mountains were redrawn at his request                                                                                    |
| 2\. Life, genetics, ecology, needs             | Seasons, weather, plants that grow, animals and people that eat, breed, age and die, the first four peoples, about twelve animals, disease, a history log, first sound | **Just started.** Step 1 of 14 is done. Step 2 is written but not yet tested. Nothing from Phase 2 is visible to the owner yet. Work is paused until he says "restart work". |
| 3\. Settlements, economy, technology           | Villages and towns, jobs, food, trade, tools                                                                                                                           | Not started                                                                                                                                                                  |
| 4\. Culture, language, religion, politics, war | The systems that make histories                                                                                                                                        | Not started                                                                                                                                                                  |
| 5\. The god                                    | The full set of powers, faith, prophets, rival gods, rewinding time                                                                                                    | Not started                                                                                                                                                                  |
| 6\. Modding, polish, release candidate         | Mods, settings, balance, final builds                                                                                                                                  | Not started                                                                                                                                                                  |


### 2.3 The machine, and the limits it sets

The game is being built and tested on the owner's **MacBook Air (M2, 8 GB of memory)**. Because of that the game currently runs in a reduced-size setting:

- Worlds are **256 by 256 tiles**.
- At most **4,000 creatures** alive at once.

These are settings, not design limits: the same game is meant to run at up to 1024 by 1024 tiles and 30,000 or more creatures on a gaming PC later. Release order is PC first, then Mac and Linux, then phones much later.

### 2.4 What you see when you open it

The game opens straight into a world. There is no title screen and no menu.

- **Top bar**, a dark strip across the top.
  - Left: the date, for example "Year 1, month 1, day 16".
  - Centre: five speed buttons reading **II, 1x, 5x, 25x, 100x**. The one in use is outlined in gold.
  - Right: the world's size, "256 x 256". When the simulation cannot keep up with the chosen speed, the words "Sim-limited" appear beside it in red.
- **Minimap**, a small square picture of the whole world in the top-left corner, with a gold rectangle showing which part is on screen. Clicking it jumps the view there.
- **The world**, filling the rest of the screen.
- **Bottom bar**, a dark strip across the bottom.
  - A row of five tabs: **Terrain, Nature, Life, Tools, World**. The open tab is underlined in gold.
  - Under the tabs, a row of small square buttons, each with a little picture. Hovering over a button shows its name and one line about what it does.
  - At the right end: the word "Brush", three shape buttons (circle, square, diamond), and a size control with minus and plus (it starts at 5).

The interface is dark blue-black with pale text and gold highlights, and all its lettering is a small pixel typeface I drew. It grows with the size of the screen. **The owner does not like it** (Part 5). It has had no polish and is to be redesigned with him.

### 2.5 The world

A world is made in about a tenth of a second from a number (the "seed"); the same seed always gives the same world. It has continents or islands with beaches, lakes and a few rivers, forests where it is wet, yellow savanna and pale desert where it is dry, grey mountains, and tundra and snow toward the top and bottom edges of the map.

**Twenty kinds of ground:** deep ocean, shallow water, beach, desert, scorched earth (what fire leaves), savanna, grassland, meadow (with small flowers), swamp, temperate forest, jungle, taiga (pine forest), tundra, snow, glacier, volcanic rock, lava, hills, mountains, peaks.

**Things standing on the ground:** oaks, small oaks, pines, jungle trees, dead trees, cacti, bushes, boulders, small rocks, reeds at the water's edge, and grassy mounds on the hills.

**Eleven kinds of world** can be made: Continents (the default), Islands, Pangaea (one big landmass), Inland sea, Ice, Desert, Jungle, Volcanic, Maze (mountain walls), Blank (all sea), Plains.

**How it is drawn.** Tiles are 16 pixels square. The whole game uses one palette of 42 colours. Light always comes from the top-left. Where two kinds of ground meet, the edge is an uneven hand-drawn line, never a straight tile edge; coasts have a line of foam and paler water. Higher ground has a dark lip on its lower side and a light rim on its upper side. Flat ground is plain colour with a few small marks (tufts, pebbles, ripples) placed from hand-made layouts. There are no gradients, blur or noise anywhere. The owner approved this style.

The view can be zoomed to seven levels, from a quarter size to six times size. The two zoomed-out levels are rough: fine detail can flicker while the view moves.

### 2.6 Mountains (changed today at the owner's request)

**Before:** every mountain tile had its own small triangular rock, so a mountain range looked like a field of little stones. The highest ground was a pale sandy patch covered in the same small rocks with white tops.

**Now:** a range is **a few large mountains standing on bare grey rock**. Each mountain is two to three tiles wide with a lit left face, a shaded right face and a ragged foot. They are bigger in the middle of a range and smaller at its edges; a strip of mountain ground only one tile wide gets small crags. The highest ground ("peaks") is the same grey rock with the same mountains, but with snow on their upper slopes and a few small patches of snow on the ground. The rock between the mountains has very few marks, and only an occasional loose boulder.

The owner approved Phase 1 after seeing this. He has not yet said anything more specific about the new mountains.

### 2.7 Creatures

Four kinds exist, all placeholders for what Phase 2 will build:


| Name in the game | What it looks like                                                                    | What it does                                                                                            |
|------------------|---------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| Strider          | A small person in a red tunic with brown hair. A stand-in for the real peoples.       | Wanders from place to place, up to about 40 tiles at a time, finding its way round lakes and mountains. |
| Grazer           | A tan deer-like animal with antlers. Lives in herds on grassland, meadow and savanna. | Wanders close to where it is. Bolts when a hunter comes within sight.                                   |
| Hare             | A very small grey animal.                                                             | The same as the grazer.                                                                                 |
| Pack Hunter      | A grey wolf-like animal. Lives in packs in forest, taiga, grassland and tundra.       | Wanders. Chases grazers and hares it can see.                                                           |


A new world starts with a little over a hundred wild animals in small herds and packs, and no people. The player can add more of any kind.

**What creatures cannot do yet:** eat, drink, sleep, breed, grow old, die, fight, or be clicked on to learn anything about them. A hunter that catches its prey just stands beside it. This is all Phase 2.

**Where they can go.** Dry land, slowly over hills and the lower mountains. Shallow water only within two tiles of a shore, so rivers can be crossed but open water cannot. Never the deep sea, lava, or (since today) the snowy peaks. There are no boats.

They have a two-frame walking animation. Up to 4,000 can be alive at once and the game stays smooth.

### 2.8 The powers (everything the player can do)

**Terrain tab**

- **Raise Land:** hold the mouse to lift the ground. The sea floor rises into shallows, then dry land, then hills and mountains.
- **Lower Land:** the opposite. Low enough, and the sea comes in.
- **Paint** one of eighteen kinds of ground directly: Deep Ocean, Shallow Water, Beach, Desert, Savanna, Grassland, Meadow, Swamp, Temperate Forest, Jungle, Taiga, Tundra, Snow, Glacier, Volcanic Rock, Hills, Mountains, Peaks. Each button shows a real piece of that ground.

**Nature tab**

- **Spring:** pours water where you point. It runs downhill and pools.
- **Rain:** wets a wide area and puts out fires.
- **Lava:** molten rock that creeps, burns what it touches and cools to stone.
- **Wildfire:** sets things alight.
- **Plant:** puts an oak wherever there is soil.
- **Clear:** removes plants, rocks, fire, water and lava.

**Life tab**

- **Spawn Strider, Spawn Grazer, Spawn Hare, Spawn Pack Hunter.** The brush size sets how many appear.

**Tools tab**

- **Undo** and **Redo** for anything done to the land.
- **Lens:** colours the map by heat, then by rainfall, then by height, then back to normal.

**World tab**

- Eleven buttons, one per kind of world. Pressing one throws away the current world and makes a new one of that kind at once. There is no "are you sure?".

All powers work while the game is paused. The brush has three shapes (circle, square, diamond) and an adjustable size. An outline on the ground shows where it will act.

### 2.9 Fire, water and lava

- **Fire** spreads across anything that burns. Dry grassland and savanna go fast, forest burns longer, desert and rock do not burn. It burns out and leaves black scorched earth with the plants gone. Water puts it out.
- **Water** poured on land runs to lower ground, levels out in hollows, is swallowed by the sea, and slowly dries.
- **Lava** creeps downhill, sets fire to what it touches, boils water away, cools, and sets as dark volcanic rock. Where it sets in the sea it makes new land.

None of the three is animated yet: they are still pictures that change as the world changes.

### 2.10 Time

- A day lasts a little over one second at normal speed; a year is 12 months of 30 days and takes about seven minutes at normal speed.
- Speeds: pause, half, 1x, 2x, 5x, 10x, 25x, 100x. The bar shows five of them; the number keys 1 to 8 give all eight.
- With a world full of creatures the game cannot yet reach its highest speeds. It runs as fast as it can and shows "Sim-limited". (My estimate is about twenty times normal speed with 4,000 creatures; making fast-forward truly fast is part of Phase 2.)
- Nothing yet changes with the date. Seasons are being built now (2.17).

### 2.11 Controls


| To do this                                 | Use                                                                 |
|--------------------------------------------|---------------------------------------------------------------------|
| Move the view                              | W A S D or the arrow keys, or hold the middle mouse button and drag |
| Zoom                                       | Mouse wheel                                                         |
| Pause and resume                           | Space                                                               |
| Change speed                               | Keys 1 to 8, or the buttons at the top                              |
| Choose a power                             | Click it on the bottom bar                                          |
| Use a power                                | Left mouse button on the world                                      |
| Put a power down                           | Right mouse button or Esc                                           |
| Brush size                                 | Q and E                                                             |
| Undo and redo                              | Z and Y                                                             |
| Map lenses                                 | Tab                                                                 |
| Quick save and quick load                  | F5 and F9                                                           |
| Technical read-out (frame times and so on) | F3                                                                  |
| Quit                                       | Cmd+Q. There is no quit button.                                     |


The keys cannot be changed yet.

### 2.12 Saving

Quick save and quick load work, and the game saves by itself every ten minutes. A loaded world is exactly the world that was saved. There is no screen for choosing between saves.

### 2.13 How well it runs (measured on his Mac)

- 60 frames a second with 4,000 creatures, both in a window and full screen.
- If the Mac is in **Low Power Mode**, macOS itself holds any full-screen game to 30 frames a second. This is the system's doing, not the game's, and switching Low Power Mode off cures it.
- Making a world takes about a tenth of a second. Saving takes about a fiftieth of a second.
- Memory use is about 1.1 GB.
- 110 automated tests check the game, including that the same world always plays out the same way.

### 2.14 How he opens it

A built copy of the game sits in the project folder on his Mac and opens full screen like any app. It is rebuilt whenever something he should see changes.

### 2.15 What is not in the game yet

So that nobody assumes otherwise:

- No title screen, no main menu, no world-setup screen (size, seed, sea level and so on), no settings, no quit button.
- **No sound at all.**
- No animation of water, lava, fire or grass.
- No day and night.
- No real peoples, no houses, villages, farms, roads, boats or any building.
- Creatures do not eat, breed, age or die, and cannot be inspected.
- No history log, no notifications, no graphs.
- No weather or seasons that the player can see.
- No faith, miracles, prophets, religions, languages, cultures, kingdoms or wars.
- No rewinding time.
- No mods.
- No Windows version (only the Mac version is built so far).

### 2.16 Known rough spots in what does exist

- **The interface**, which the owner dislikes.
- **Creatures walk across the lower mountains** and are drawn on top of the mountain pictures, as if climbing over them.
- **Creatures in shallow water look as if they stand on it.** There is no wading picture. About three in a hundred are in the shallows at any moment.
- **Far zoom** is rough.
- **Nobody has properly play-tested it by hand.** Everything was checked by automated tests and by running the game unattended and looking at pictures it took of itself. Mouse clicks on the buttons are the least-tested part.

### 2.17 What is being built right now and not yet visible

Phase 2, step 2: **seasons and weather.** Written, not yet tested or approved, so it may change:

- Four seasons of 90 days. It is warmer in summer and colder in winter, more so toward the top and bottom of the map.
- Rain, storms and droughts, region by region. Rain damps fires; a drought feeds them. Lightning in a storm sometimes starts a fire.
- **Snow** falls where it is cold enough, lies on the ground through winter and melts in spring. Snow-covered land is drawn white; snow on the mountains turns them into snowy peaks.
- **Grass grows back.** Every piece of land carries a certain amount of grazing that regrows in warm wet weather and not in the cold. (Nothing eats it yet.)
- **Trees live:** they grow from saplings, drop seeds into gaps nearby, grow old and die, and a burnt wood grows back over decades.

------------------------------------------------------------------------

## Part 3. The plan from here

### 3.1 The rest of Phase 2, in order

1.  *(Done)* Groundwork for births and deaths; snowy peaks cannot be walked; far fewer creatures standing in water.
2.  *(In progress)* Calendar, seasons, weather, snow, grass that regrows, trees that live and die.
3.  The first **four peoples** and about **twelve animals**, with their drawings. An art sheet goes to the owner for approval before more is built on it.
4.  Bodies: age, sex, health, hunger, thirst, tiredness, cold. Eating, drinking, sleeping. Starving and freezing.
5.  Inheritance: every creature carries genes from its parents that affect its looks and strengths. Courtship, pregnancy or eggs, birth, childhood, old age, death.
6.  Herds and bands, hunting and fighting, scavengers, seasonal migration, species dying out.
7.  Making fast-forward genuinely fast, by simulating far-off creatures in less detail than the ones the player is watching.
8.  Disease.
9.  Minds for the peoples: personality, mood, traits, skills, memories, relationships, names.
10. A history log ("chronicle") of births, deaths, extinctions and disasters; the game noticing and naming new sub-kinds of a species.
11. Windows: click a creature, a species or a tile to see everything about it; graphs of populations; the chronicle; the season shown at the top; a pause menu with a quit button.
12. First sound: background sound that follows what is on screen, and sounds for the interface. All made by code.
13. Pictures: shimmering water, wading, snow, rain, sleeping and young creatures, better far zoom.
14. Long tests (centuries of game time), performance numbers, a Mac build, a report, and the Phase 2 checkpoint.

### 3.2 The eight peoples

The design fixes eight peoples. The names are placeholders the owner may change. The first four arrive in Phase 2.

1.  **Verran, the generalists.** Adaptable, quick to change, the best traders and the least stable empires. Medium size. (The red-tunic "Strider" is a first sketch of them.)
2.  **Ysmeri, the canopy-keepers.** Tall, slender, live for centuries in forests in partnership with trees, have few children. Fire is their terror.
3.  **Mogren, the tunnel-folk.** Small, short-lived, fast-breeding burrowers whose towns are mostly underground. Prone to epidemics and to sudden mass migrations.
4.  **Sethari, the sun-bound.** Cold-blooded, lay eggs, worship the sun. Strong in summer, sluggish in winter, and cold can kill them.
5.  **Nerei, the shore-singers.** Amphibious coast-dwellers and sea traders who must stay near water.
6.  **Orrun, the herd-walkers.** Large nomads who move with the seasons in camps of tents and wagons.
7.  **Karrak, the stone-kin.** Broad, long-lived mountain folk, miners and builders, slow to change and slow to forgive.
8.  **Myrrhu, the web-bound.** Small mushroom-capped folk linked by a shared fungal network that spreads knowledge among them.

### 3.3 The animals I intend to make in Phase 2

This list is my proposal, not a fixed decision: plains grazer, forest deer, mountain goat, a giant slow browser, hare, tortoise, pack hunter (wolf-like), big solitary cat, bear-like omnivore, crocodile-like river predator, carrion bird, bird of prey. Fish, insect swarms, tame animals and five rare mythic beasts (a wyrm, a stormhawk, glimmer-stags, a deep leviathan, an ashbeast) come later.

------------------------------------------------------------------------

## Part 4. What is already decided

The owner settled these before building began. Do not re-open them unless he raises them himself.

- The name **Worldwright**.
- A living-history simulation **and** a full sandbox of destructive powers.
- The player is a hands-off god who can also work miracles.
- Top-down pixel art, 16-pixel tiles, with all art made by code and approved by him.
- All eight peoples above; species can be added by mods.
- Deep individuals: personality, needs, relationships.
- Cultures, languages and religions that change by themselves over time; politics and war; economy; ecology; disease.
- A faith economy, prophets, rival gods, fate and artifacts.
- Time control with rewinding and branching histories.
- Player-made automatic rules for the god.
- Optional scenarios and achievements; both a free "Sandbox" mode and a "Divine" mode where powers cost faith.
- Mods and Steam Workshop.
- Sound made by code that reacts to what is happening.
- The six phases.
- **Nothing is to be copied** from the game that inspired it or from any other game: no names, pictures, numbers or code.
- **I must ask him first** before downloading anything, before sending or publishing anything anywhere, and before touching anything outside the project folder. I do not create accounts, accept terms or enter passwords.

------------------------------------------------------------------------

## Part 5. What the owner has said so far, in his words

- On the art style sheet: **"Approve the look"**.
- At the Phase 1 checkpoint: **"Changes first"**, and then: \> "i dont like how like mountains are a lot of small rock anjd like the models should be built on the grey area like idk it looks too cluttered, trees and rest is fine, Ui kinda sucks but well work on that latee"
- After the mountains were redrawn: **"Approve Phase 1"**.

What I take from this:

- He dislikes **clutter**: many small repeated things. He prefers a few clear shapes on calm ground.
- **Trees and the rest of the world are fine** as they are.
- **The interface "kinda sucks"**, and he wants to work on it later, not now. I do not know yet what he dislikes about it.

- On the interface, from the choices he ticked: he dislikes the **colours**, the **layout and button pictures**, and **too much on screen**. He did not tick the lettering or any other cause. He named no game whose interface he likes ("No idea yet").
- On powers, in his words: **"i want a LOT of things i can drop or do"**
- On how detailed each power should be: **"even more and i want them detailed not just big bomg small bomb this applies to every single one"**
- On where to look for ideas: **"do research on all the powers world box has as that's the inspiration, so like lighting bombs etc even when the erra doesn't jave them"**
- On how he wants to be interviewed about powers: **"i wwntee you to ask me questions about all the itens wnd powers and things the player can do"**
- On the creature inspector: **"shows stats too"**
- On Low Power Mode: **"no never the game will be finalized on my pc"**

*(Add anything new he says here, in his exact words.)*

------------------------------------------------------------------------

## Part 6. Choices I made without him

He approved the phases without answering these, so I took the defaults shown. Any of them can be changed.


| Choice                                                | What I did                                                                                                                                                                       |
|-------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Should mountains stop creatures?                      | The snowy peaks stop them. The lower mountains only slow them, so creatures still walk over those.                                                                               |
| How far can creatures wade?                           | Two tiles from shore. Open water is closed to them.                                                                                                                              |
| Are the four placeholder animals good enough to keep? | Yes. New animals will follow the same style.                                                                                                                                     |
| Should the Verran (the first people) look unusual?    | No. They stay plain, and the other peoples carry the stranger shapes.                                                                                                            |
| Do people get a dark outline?                         | No.                                                                                                                                                                              |
| Interface colours                                     | Dark ink for controls, parchment for story text. (Not yet built beyond the dark bars.)                                                                                           |
| Lettering                                             | My small pixel typeface for everything, long text included. A smoother typeface for long reading would have to be downloaded, which needs his permission.                        |
| Which animals to make in Phase 2                      | The list in 3.3.                                                                                                                                                                 |
| The interface in Phase 2                              | Phase 2 needs new windows (click-to-inspect, graphs, the history log). I plan to build them plainly in the current style and leave the real redesign for when he wants to do it. |
| Unity's "hardware report"                             | Unity can make a game send an anonymous report about the computer to Unity. I switched that off; the game sends nothing anywhere.                                                |
| The default world                                     | Continents, 256 by 256, the same seed each time, so he always sees the same starting world.                                                                                      |


------------------------------------------------------------------------

## Part 7. Questions waiting for him

1.  **The new mountains:** right as they are, or should anything change (size, how many, the snow, the grey ground)?
2.  **Mountains and walking:** should the lower mountains also stop creatures, or is slowing them enough?
3.  **The interface:** what exactly does he dislike? Useful things to find out: is it the size, the lettering, the colours, where things are, the little pictures on the buttons, too much or too little on screen? Is there a game whose interface he likes? Does he want it dealt with at a particular point (before peoples arrive, at the end of Phase 2, later)?
4.  **Creatures in water:** is a wading picture enough, or should they stay out of water altogether?
5.  **The animals and the first people:** keep the current drawings as the base, or redraw before making more?
6.  **The four peoples coming next (3.2):** any wishes for how they look? Any names he wants changed?
7.  **The animal list (3.3):** anything to add or drop?
8.  **Order within Phase 2:** is there something in 3.1 he wants to see first? For example a title screen and a quit button early, or sound early.
9.  **How often to show him things:** only at the end of each phase, or shorter stops with pictures along the way (for example each new people's drawings)?
10. **Sound:** any taste to steer by (quiet and natural, musical, retro)?
11. **A studio name.** The game is currently filed under Unity's placeholder name. It decides where save files are kept, so it is best set before saves matter.
12. **Folding the work into the main project folder.** All work so far sits on a side branch. May I merge it into the main copy?
13. **A Windows version.** Building one on this Mac needs a large download. Wait until the project moves to a PC, or get it now?
14. **Low Power Mode:** does he usually play on battery with it on? If so I should make the game say on screen when the system is holding it to 30 frames a second.

------------------------------------------------------------------------

## Part 8. The owner's direction

*Filled in by the phone assistant on 10 November 2026 after interviewing the owner. Most answers were picked from multiple-choice cards, so where he picked something without giving his own words I have said so. Where two of his answers disagreed I asked again and used the second answer.*

### 8.1 Answers to the questions in Part 7

1. [decided] Keep the new mountains exactly as drawn. (He picked "Keep as they are" for size, number, snow and grey ground.)
2. [decided] Make the lower mountains stop creatures completely, not just slow them. He first picked "Stop them completely", and when I asked about enclosed valleys and Maze worlds he picked "Leave natural gaps": world generation should always leave a few passes so creatures are never trapped.
3. [decided] Draw a wading picture for creatures in shallow water. He did not choose to keep them out of water.
4. [decided] The interface: he dislikes the colours, the layout and button pictures, and too much on screen. He has no game in mind as an example ("No idea yet"). Redesign it at the **end of Phase 2**, not before. Until then, build the Phase 2 windows plainly in the current style, as Part 6 planned.
5. [decided] Animals and first people: he picked "Show me first". Send screenshots of the four placeholder animals and the Strider and let him decide whether to keep or redraw them before more are made.
6. [decided] The four peoples coming next: keep all four and their names as written in 3.2 (Verran, Ysmeri, Mogren, Sethari). He had no wishes about how they look.
7. [decided] Animal list: keep the twelve in 3.3 and **add** fish, insect swarms, tame animals and the mythic beasts, all in Phase 2. When I asked what else, he ticked sea creatures (whales, sharks, turtles, crabs, jellyfish), birds (songbirds, flocks, owls), farm and pet animals (sheep, cattle, horses, dogs, cats) and reptiles and monsters (snakes, lizards, giant worms, spiders). The exact species still need his approval on an art sheet.
8. [decided] Order within Phase 2: he wants all four of these early: a title screen and quit button, sound, click-to-inspect windows, and truly fast fast-forward. If only one can come first, it is **click a creature to inspect it**, and it should "show stats too". He wants the inspector to cover needs (hunger, thirst, tiredness, cold, health), body and genes (age, sex, inherited traits), mind and relationships (personality, mood, skills, memories, family, for peoples), and species totals and graphs. He gave no order for the other three.
9. [decided] How often to show him things: only at the end of each phase, with one exception: stop for his approval on each **art sheet** (new animals, new peoples) before more is built on it.
10. [decided] Sound: a mix of natural and musical. Natural ambience with gentle music over it.
11. [decided] Studio name: **Worldwright**. He said "Use Worldwright", which I took to mean the studio name is the same as the game's name.
12. [decided] Do **not** merge the side branch into the main project folder yet. Merge it **after Phase 2 is approved**.
13. [decided] Windows version: wait until the project moves to his PC. Do not do the large download now.
14. [decided] Low Power Mode: he never plays with it on. No on-screen notice needed.

### 8.2 Changes to choices in Part 6

1. [decided] Overturn "Should mountains stop creatures?". The lower mountains now stop creatures completely, as well as the snowy peaks.
2. [decided] Overturn "How far can creatures wade?" in part: creatures still wade in the shallows, but they get a proper wading picture. The two-tile limit was not changed.
3. [keep] He chose to overturn none of the other choices: the Verran stay plain, people get no dark outline, the pixel typeface stays for all lettering, and the default world stays the same.

### 8.3 Changes to what exists now

1. [change] Make lower mountains block creatures. They must route around, as with the snowy peaks. World generation must leave a few natural gaps so no area is sealed off, including in the Maze world.
2. [change] Draw creatures wading in shallow water instead of standing on it.
3. [change] The World tab buttons must ask "are you sure?" before throwing the current world away. ("Ask 'are you sure?'")
4. [change] Reduce the speeds to **pause, 1x, 5x, 25x and 100x**, on both the top bar and the number keys.
5. [change] Make Clear selective, so he can choose what it removes: plants only, fire only, water and lava only, or rocks and boulders only. He first ticked "Fine as they are" and also "Clear should be selective"; when I asked again he said "Make it selective".
6. [change] Make Plant offer more than the oak: pine, jungle tree and small oak, bush and cactus, reeds and flowers, and an automatic mode that plants what suits the ground.
7. [change] Add a legend to the map lens that explains the colours, and add lenses for population, food and grazing, and species. Lenses for borders, faith and language come later, when those systems exist. He also ticked "Fine as it is", which I took to mean the three existing lenses stay.
8. [change] Add a help screen that lists the controls, and a way to rebind the keys.
9. [change] Redesign the interface at the end of Phase 2: colours, layout, button pictures, and less on screen.
10. [change] Make the Phase 2 inspector show the four groups of stats listed in 8.1, number 8, as bars, with exact numbers when he hovers over a bar.

### 8.4 New things he wants

1. [new] An **erase creatures** tool, to remove creatures in the brush area.
2. [new] A **big list of things to drop or do**. He wants many powers, and each one should be detailed, not just a generic big and small version. The kinds he picked are below. **The names and behaviours are my proposals, drawn from the general kinds of powers such games have, with original names. He has not reviewed the behaviours one by one, so treat them as a first draft for him to react to.** Please send him the list with pictures or short descriptions before building.

**Disasters (all of these he chose)**
- Lightning Strike: hits one spot, sets dry ground alight, shatters a tree, and can chain to nearby tall things in a storm.
- Tornado: a funnel that wanders for a while, uproots trees, throws creatures, and fades.
- Earthquake: shakes a wide area, cracks open fissures in the ground, and drops hills.
- Meteor: a falling rock with a trail, a crater at the impact point, fire around the rim, and a burst of dust.
- Firestorm: a wide rain of burning fragments that starts many fires at once.
- Eruption: turns a spot into a vent that throws out lava, ash and fire for a long time.
- Tidal Wave: a wall of water from the sea that runs inland, then drains away.
- Sinkhole: the ground collapses into a hole that may fill with water.
- Ice Age Snap: a sudden freeze that spreads outward, turning water to ice and land to snow.
- Blight: spreads across plants and kills them, thinning the grazing.
- Locust Swarm: a cloud that strips plants as it moves.

**Bombs (he chose all eight I offered and wants "even more", each one distinct)**
- Pebble Charge: tiny, cracks the ground and scatters creatures without killing.
- Small Bomb: a small crater and a few thrown rocks.
- Big Blast: a wide crater, a flattened rim, a shockwave that kills in the centre and hurts further out.
- Cluster Bomb: bursts into many small bombs across an area.
- Delay Bomb: you set a fuse, and it goes off after that many seconds.
- Fire Bomb: scatters flames across a ring around the impact.
- Sticky Fire Bomb: flames that cling to ground, even bare rock, for a long time.
- Frost Bomb: freezes water into ice and covers land in snow; kills plants.
- Heat Bomb: melts snow and ice and dries out wet ground.
- Water Bomb: a burst of water that floods the area, then drains.
- Poison Cloud: a drifting cloud that harms creatures and wilts plants for a while.
- Seed Bomb: a burst of plants fitting the ground it lands on.
- Sinking Bomb: a crater that floods.
- Lightning Bomb: a thunderclap and several strikes at once.
- Shockwave Bomb: a ring of force that knocks creatures and objects outward without breaking the ground.
- Smoke Bomb: a thick cloud that hides the area for a while.
- Stone Bomb: pushes up a ring of rock and a new hill.
- Lava Bomb: a pool of molten rock at the impact.
- Spore Bomb: a patch of fungus that spreads slowly.
- Plague Bomb: a burst of disease around the impact.

**Weather (he chose all of these)**: Storm, Blizzard, Heat Wave, Drought, Fog, Acid Rain.
- Storm: a dark cloud that moves, with rain and lightning.
- Blizzard: snow and wind with low sight and slowed creatures.
- Heat Wave: dries plants and water and raises the fire risk.
- Drought: stops rain and regrowth in a region for a long time.
- Fog: lowers sight, which affects hunters and prey.
- Acid Rain: a rain that burns plants and slowly eats at terrain.

**Life powers (he chose all of these)**: Heal, Bless, Curse, Cure, Grow Giant, Shrink, Age, Plague.
- Heal and Cure: restore health or remove disease.
- Bless and Curse: give or take a lucky or unlucky streak, and a trait.
- Grow Giant and Shrink: change a creature's size, strength and needs.
- Age: moves a creature forward or backward in life.
- Plague: starts a disease in a herd or people.

**Creatures and terrain (he chose all of these)**: Mythic beasts and Dragon, Grow Volcano, Raise Island, Make River, Dig Canyon, Flatten, Smooth, Freeze, Melt.
- Mythic beasts and Dragon: summon any of the five mythic beasts (wyrm, stormhawk, glimmer-stags, deep leviathan, ashbeast) and a dragon. He decided the dragon is a **sixth mythic beast**, added to the list.
- Grow Volcano: builds a cone that erupts from time to time.
- Raise Island: lifts a new island out of the sea.
- Make River: a lasting stream that cuts its way to the sea.
- Dig Canyon: a deep, long gash in the land.
- Flatten and Smooth: level the ground to one height, or soften sharp changes.
- Freeze and Melt: turn water to ice and back, or snow to water.

3. [sooner] Build **all the powers that need no peoples** (disasters, bombs, weather, terrain, life powers on animals) **in Phase 2**, after the seasons work. Review them with him **in small groups** (disasters first, then bombs, and so on), each with pictures, before building. He wants every power to have a big visual effect, its own sound, a lasting mark on the world (scorches, craters, cracked ground), and creatures that react (panic, flee, mourn, pray).
4. [new] **Miracles** (Phase 5) work **both ways**: he can aim a miracle at a person or a place himself, and he can answer prayers that peoples send him.
5. [decided] **Sandbox** (everything free) is the main way to play. Divine mode, where powers cost faith, is the optional one.
6. [later] Rewinding time and branching histories stay in Phase 5 as planned. He wants all three kinds eventually (a few minutes, years or centuries, and branching alternate worlds) but calls it low priority.
7. [sooner] **Rules for the god** (powers that act on their own, like "when a fire starts, send rain") are important to him. He first said "Very, I want them early" and then, when asked how early, picked "Before the god phase", meaning in Phase 3 or 4 rather than Phase 5.

8. [new] **Animation everywhere.** He wants animation for fire, water, lava, grass, every power, animals doing things, and people mining and doing their jobs. He picked "Lots of actions": each activity gets its own animation. (This is a large piece of work and grows with each system.)
9. [new] **Visual touches:** day and night, season looks (autumn leaves, snow, blossoms), and weather effects (rain drops, snow flakes, lightning flashes, fog).
10. [new] **Extra player tools:** follow a creature with the camera, a screenshot or photo mode that hides the interface, notifications when something big happens (an extinction, a big fire), and a world setup screen (kind, size, seed, sea level).
11. [new] **Game features:** a save and load screen for several worlds, a pause menu with settings and quit, a tutorial or hints, and achievements and scenarios.
12. [new] **Reaching many powers without clutter:** use both categories with sub-menus, and a search box with pinned favourites. ("Both")
13. [new] **Names:** peoples' languages generate names automatically, and he can rename any creature, village or species himself. ("Both")
14. [new] **Doing things to peoples** (Phases 3 to 5): give gifts (tools, crops, animals, knowledge), start wars or peace, spawn a prophet or hero, drop artifacts, put fate marks on creatures, and nudge a people's culture, beliefs, language or customs. He did **not** ask for placing buildings for them.
15. [decided] **How peoples react to disasters and wrecking:** they worship or fear him, they rebuild, they flee or migrate, and the chronicle writes it into history. All four.
16. [decided] **Rival gods** stay as already planned in Part 4. He did not tick them as an extra.

### 8.5 What to do first, in his order of importance

He gave one clear first item (**click a creature to inspect it**) and an order for three more. The rest is my reading, for the build session to check with him at the first checkpoint:

1. Finish the seasons and weather work in progress.
2. The click-to-inspect windows with stats.
3. The small fixes: lower mountains block creatures (with natural gaps), wading picture, "are you sure?" on new worlds.
4. Title screen and quit button, then sound, then truly fast fast-forward. (His order.)
5. The first four peoples and the larger animal list, starting with **sea creatures** on the first art sheet, with his approval before more is built.
6. The no-people powers in 8.4, in small reviewed groups.
7. The interface redesign at the end of Phase 2 (or the last part of it, if Phase 2 is split).

**Phases.** He told me Phase 2 holds too much: **split the work among the later phases, adding new phases if needed, but never more than 10 phases in total.** There are six today, so up to four more can be added. [change] The build session should propose a new phase list to him, and he must approve it.

### 8.6 Things to leave alone

1. [keep] The mountains as drawn. ("Keep as they are")
2. [keep] Trees and the rest of the world. (His earlier words: "trees and rest is fine")
3. [keep] The four chosen peoples and their names.
4. [keep] Raise Land, Lower Land, the eighteen paint-ground buttons, Spring, Rain, Lava, Wildfire, the four Spawn buttons, the brush, and the land-only Undo and Redo. He said each of these is fine as it is.
5. [keep] The pixel typeface for all lettering. He did not overturn it.
6. [keep] Verran plain, no dark outline on people, and the default world.
7. [keep] Everything in Part 4.

### 8.7 Open questions for the build session

1. [ask] Part 4 says nothing is to be copied from the game that inspired Worldwright. He told me to research that game's powers. I only used its general categories and every name and behaviour above is my own, but he should confirm that this is what he means, and tell the build session if he wants it closer.
2. [ask] After you propose the new phase list (up to 10 phases), which of the items in 8.4 and 8.5 go in which phase? He asked to spread Phase 2 across later phases and did not say where each item goes.
3. [ask] Animation: he wants "lots of actions" per creature. This is large, so show him what it would cost and let him choose what to cut if needed.
4. [decided, not a question] Rules for the god: Phase 3 or Phase 4, whichever is easier. He also first said he wants them early, so do not leave them until Phase 5.
5. [decided, not a question] Rewinding stays in Phase 5. He wants all three kinds eventually.

### 8.8 Anything else he said

1. He wants to be asked questions about every item and power the player can do, so the list of powers and tools should be reviewed with him one by one before it is built. ("i wwntee you to ask me questions about all the itens wnd powers and things the player can do")
2. He cares about the game not looking AI-made. This matters for every new picture, and is why art sheets should come to him first.
3. The game will be finalised on his PC, so the Mac is a test machine.
