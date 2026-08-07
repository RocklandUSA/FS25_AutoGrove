# Auto Grove — Official Wiki

**Version:** 1.0.0.0
**Author:** RocklandUSA Gaming
**Platform:** Farming Simulator 25
**Distribution:** Official GIANTS ModHub (pending approval)

---

## Table of Contents

1. [Overview](#section-1--overview)
2. [Features](#section-2--features)
3. [Requirements](#section-3--requirements)
4. [Installation](#section-4--installation)
5. [The Panel](#section-5--the-panel)
6. [Planting a Grove](#section-6--planting-a-grove)
7. [Removing a Grove](#section-7--removing-a-grove)
8. [Cost & Pricing](#section-8--cost--pricing)
9. [Permissions](#section-9--permissions)
10. [Server Settings](#section-10--server-settings)
11. [Multiplayer](#section-11--multiplayer)
12. [Guidance Steering & AI Helpers](#section-12--guidance-steering--ai-helpers)
13. [Troubleshooting](#section-13--troubleshooting)
14. [FAQ](#section-14--faq)
15. [Changelog](#section-15--changelog)
16. [Credits & License](#section-16--credits--license)

---

## Section 1 — Overview

Auto Grove plants an entire vineyard or olive grove on one of your fields in a single action.

<p align="center">
  <img src="../screenshots/screenshot0.png" width="800" alt="Auto Grove settings panel on the GROVE tab showing crop OLIVE, row heading 47 degrees, Direction NE marked BEST, 28 rows, 1064 sections at $35 each, total cost $37,240">
</p>

In the base game, building a vineyard means placing trellis sections one at a time in the construction screen. A medium field is several hundred sections. Auto Grove replaces that with: pick the field, pick the crop, set the direction, confirm the cost.

### What it builds

The grove is made from the game's **own orchard placeables** — the same grape and olive objects the construction screen places — at the game's own native spacing. Nothing about the finished grove is custom. It is exactly what you would have built by hand, laid out in seconds instead of an hour.

This matters beyond convenience: because the result is native, everything that works with a hand-built vineyard works here too. Harvesting, pruning, spraying, guidance steering, other mods reading the field — none of them can tell the difference.

### What it does not do

- It does not invent new crops, new placeables, or new farming mechanics.
- It does not bypass the game's rules on where things can be placed.
- It does not make groves cheaper than building them by hand (unless a server admin chooses to).
- It does not enable AI helpers in vineyards — see [Section 12](#section-12--guidance-steering--ai-helpers).

### Design philosophy

Three principles shaped the mod:

**The server is the authority.** Every request from a client is re-validated on the server — field ownership, Farm Manager rights, affordability, and whether the field is already busy. A client asks; it never instructs.

**No console commands.** Everything lives in one panel on F6. A feature a player can't find is a feature that doesn't exist.

**Vanilla pricing stays vanilla.** Ordering a grove costs exactly what building it by hand costs. Making it cheaper would turn a convenience mod into a cheat; making it more expensive would punish players for using it.

---

## Section 2 — Features

### Planting

| Feature | Description |
|---|---|
| Whole-field planting | Grapes or olives across any field your farm owns, in one action |
| Row heading | Set the direction rows run, 0–359° in 5° steps, with a live compass readout |
| Best-heading recommendation | The mod works out the most efficient angle for the field's shape and offers it as a one-tap **BEST** button |
| Live preview | Row count, section count, and total cost update as you change the heading |
| Boundary-following layout | Rows fit the actual field shape, including irregular and concave fields |
| Concave field handling | A row crossing a notch is split into separate spans rather than bridged across the gap |
| Native spacing | Row and plant spacing are read from the game's own orchard placeable at spawn time |
| Automatic field clearing | Fruit, weeds, and stones removed and the ground tilled to cultivated soil before the first row |
| Engine-paced building | Rows are fed to the game at a rate it can render, with an adjustable speed |
| On-screen progress | A progress bar tracks the job whether or not the panel is open |

### Cost & permissions

| Feature | Description |
|---|---|
| Vanilla pricing | $25 per grape section, $35 per olive section — the same as the construction screen |
| Charged on completion | The farm pays for what actually went in; a cancelled or failed job costs nothing |
| Affordability check | The panel refuses to start a job the farm can't pay for, and says so |
| Server discount | Admins can set 0–100% off, applied server-wide |
| Farm Manager requirement | Farm hands cannot plant or demolish |

### Removal

| Feature | Description |
|---|---|
| One-action demolition | Removes the entire grove from a field |
| Hand-built groves | Removes groves you built yourself, not only ones this mod planted |
| Cross-field trimming | A grove running onto other fields is trimmed back to the selected field, leaving the neighbours' rows standing |
| Ground restoration | Tills the rows back to bare field |
| Two-tap confirmation | The first tap arms it, the second performs it |

### General

| Feature | Description |
|---|---|
| Multiplayer | Fully supported, server-authoritative throughout |
| Dedicated server | Fully supported |
| Shared F6 panel | The same settings key across all RocklandUSA Gaming mods |
| Dependencies | None |
| FSCore | Optional — integrates automatically if installed |

---

## Section 3 — Requirements

| | |
|---|---|
| **Game** | Farming Simulator 25 |
| **Game version** | Current retail version |
| **DLC** | None required |
| **Other mods** | None required |
| **Map** | Any map with the standard orchard placeables — effectively all maps, including all stock maps |
| **Permissions** | Farm Manager rights to plant or demolish |
| **Owned land** | At least one field owned by your farm |

### A note on grapes and olives

In Farming Simulator 25, grapes and olives are **fence-style placeables**, not trees. They live at `data/placeables/orchards/` and are built as pole-to-pole panel sections, the same way a fence is built.

This is worth knowing because it explains several things about the mod: why groves are priced per *section*, why row spacing isn't adjustable (the placeable dictates it), and why the game builds them progressively rather than instantly.

---

## Section 4 — Installation

Auto Grove is distributed exclusively through the official **GIANTS ModHub**.

### From in-game (recommended)

1. Open the **Mod Hub** menu in Farming Simulator 25.
2. Search for **Auto Grove**.
3. Subscribe / download.
4. Enable the mod in the mod menu when starting or loading a savegame.

### Manual

1. Download the mod zip from the Auto Grove ModHub page.
2. Place the zip — **do not extract it** — into `Documents\My Games\FarmingSimulator2025\mods\`.
3. Enable the mod in the mod menu.

### On a dedicated server

Install the mod on the **server** as well as on each client. Both sides need it. The server performs all validation and planting; clients need it to see the panel and to receive the rows.

After uploading a new version to a dedicated server, **restart the server** — Farming Simulator reads mod zips at startup and will keep running the old version until it does.

### Verifying it loaded

Load a savegame and press **F6**. If the panel opens, you're set.

To confirm from the log, open `Documents\My Games\FarmingSimulator2025\log.txt` and look for lines beginning with `[AutoGrove]`. You should see the version, the persistence backend, and a registration line.

---

## Section 5 — The Panel

Press **F6** to open Auto Grove.

**F6 is the shared settings key across all RocklandUSA Gaming mods.** If you have more than one of our mods installed, F6 opens a directory and you pick which one to configure. With only Auto Grove installed, F6 opens Auto Grove directly. The key is rebindable in **Options → Controls**.

The panel has two tabs, plus a third that appears only for admins and the host.

### FIELD tab

Where you choose what you're working on.

| Row | Control | What it does |
|---|---|---|
| **Field** | Cycle | Steps through every field your farm owns. Selecting a field automatically snaps the heading to that field's best angle. |
| **Field Area** | Read-only | Size of the selected field in hectares |
| **Use Field I'm Standing On** | `SET` | Selects whichever field you're currently standing in — faster than cycling on a big map |
| **Refresh Field List** | `REFRESH` | Re-scans your owned fields. Use this after buying land without reloading. |
| **Demolish This Grove** | `DEMO` | Removes the grove on this field. Two taps — see [Section 7](#section-7--removing-a-grove). |

If your farm owns no fields, the tab says **NO OWNED FIELDS** and prompts you to buy farmland.

### GROVE tab

Where you set up what gets planted.

| Row | Control | What it does |
|---|---|---|
| **Crop** | Cycle | Grapes or olives |
| **Row Heading** | Slider | The compass direction rows run, 0–359° in 5° steps |
| **Direction** | Info / `BEST` | Shows the current bearing as a compass label. When you're on the optimal angle it displays **(BEST)**; when you aren't, it becomes a one-tap **BEST** button that snaps you there. |
| **Row Spacing** | Read-only | The game's native orchard spacing (3 m on stock maps) |
| **Plant Spacing** | `NATIVE` | Set by the game's own orchard placeable |
| **Rows** | Read-only | How many rows will be built |
| **Sections** | Read-only | How many sections in total |
| **Cost Per Section** | Read-only | The vanilla rate — $25 grapes, $35 olives |
| **Discount** | Read-only | Shown only when a server has set one |
| **Total Cost** | Read-only | What the farm pays. Turns red with a warning if it can't afford it. |
| **Plantable Now** | Read-only | Whether the crop can be planted at the current time of year |

The **Direction** row is deliberately always present, whether or not you're on the best angle, so the layout never shifts under your cursor. The recommendation only appears as something to *act on* when there's actually something to do.

### ADMIN tab

Visible only to admins and the host. See [Section 10](#section-10--server-settings).

---

## Section 6 — Planting a Grove

### Step by step

1. Press **F6**.
2. On the **FIELD** tab, select the field — either cycle to it, or stand in it and press `SET`.
3. Switch to the **GROVE** tab.
4. Choose **grapes** or **olives**.
5. Set the **Row Heading**, or press **BEST** to use the recommended angle.
6. Check the **Rows**, **Sections**, and **Cost** readouts.
7. Confirm.

### What happens next

Planting runs in stages, and each is visible in the log:

**Clearing.** The field is stripped of fruit, weeds, and stones, and the ground is tilled to cultivated soil. This happens before a single row is placed — planting into a standing crop would leave the old growth poking through the new rows. The clear is given a moment to settle so its ground writes land before the grove is painted over them.

**Layout.** The mod resolves the game's orchard placeable for your crop, reads its native spacing off the placeable itself, and re-lays the rows to match. Long rows are split into shorter end-to-end segments — the engine builds a whole segment in one step, and a 400-metre row is too much for one step to finish cleanly.

**Building.** Rows are fed to the engine one at a time, paced to the rate it can render them. Progress is reported in the panel and in the log.

**Charging.** The farm is charged on completion, for the sections that actually went in.

### Choosing a heading

The **BEST** recommendation minimises the number of rows needed to cover the field, which generally means running rows along the field's longest axis. Fewer, longer rows means fewer turns when you come to work the grove.

You are free to ignore it. If you want rows running a particular way for aesthetic reasons, or to line up with a neighbouring field, set the heading yourself — the mod will lay the grove out exactly as asked.

### Limits

There is a ceiling on how many objects a single job may place, and a maximum field size. These exist to stop a single request from spawning tens of thousands of objects and hanging a server. If you hit one, the panel tells you.

---

## Section 7 — Removing a Grove

The **Demolish This Grove** button on the FIELD tab removes the entire grove from the selected field and tills the rows back to bare field.

### Two-tap confirmation

The first tap **arms** the button: it turns red and changes to *"Remove this grove — are you sure?"* with a `CONFIRM` button. The second tap performs the removal. A stray click can never wipe a grove.

### What gets removed

Everything the mod planted on that field, plus any other orchard placeables belonging to your farm inside the field boundary — including groves you built by hand in the construction screen. The ground is then tilled back to bare, cultivated soil.

### Groves that cross field boundaries

One hand-built placeable often carries rows across several fields. Deleting it whole — which is the only way a placeable *can* be deleted — would destroy the rows standing on the neighbours too.

Auto Grove will not do that. A grove that runs onto other fields is **trimmed** instead: only the sections standing on the field you selected are removed, one at a time, exactly as the game's own delete tool would. The rows on the neighbouring fields are left standing. This takes noticeably longer than removing a self-contained grove, and the progress bar shows it running.

### Why it's always offered

The button is shown even when the mod has no local record of having planted there. In multiplayer, the planting record lives on the server, so hiding the button behind a client-side record would hide it in exactly the situation where it's most needed. If there's nothing to remove, the server simply says so.

---

## Section 8 — Cost & Pricing

### Rates

| Crop | Price per section |
|---|---|
| Grapes | $25 |
| Olives | $35 |

These are the vanilla construction-screen rates. A grove ordered through Auto Grove costs exactly what the same grove costs built by hand.

### What a "section" is

One pole-to-pole span of the orchard placeable — **3 metres** on stock maps. A 30-metre row is 10 sections. A field with 68 rows averaging 28 metres is roughly 630 sections.

This is why groves are expensive: a medium field is several hundred sections, and always was. The construction screen just charged you gradually, one placement at a time, rather than in one number.

### When you're charged

**On completion, for what was actually placed.** If a job is cancelled, fails, or is interrupted, the farm pays nothing. The quote shown in the GROVE tab is calculated from the same row layout the job will build.

### Affordability

If the total exceeds your farm's balance, the panel shows the cost in red with *"Your farm cannot afford this"* and the job won't start.

### Discounts

Server admins can set a discount from **0% to 100%** on the ADMIN tab. The discount applies server-wide to everyone. At 100%, groves are free.

This exists for role-play and community servers that want to run grove installation as a subsidised service, without the mod deciding on their behalf that groves should be cheap.

---

## Section 9 — Permissions

### Farm Manager required

Both planting and demolishing require **Farm Manager** rights on your farm.

This is deliberate. Creating a grove permanently reshapes a field and spends a large amount of the farm's money; removing one destroys work that someone paid for. Neither is something a farm hand should be able to do unilaterally.

Farm Manager is a standard Farming Simulator farm role — the farm owner assigns it in the farm management screen. It is **not** the same as server admin, and Auto Grove does not require admin rights to plant.

### What admins additionally get

Admins and the host see the **ADMIN** tab, which controls server-wide settings. That's the only difference.

### Ownership

You can only plant on fields your own farm owns. Owned fields are the only ones listed, and the server re-checks ownership before acting on any request — a client cannot ask for a field it doesn't own by editing what it sends.

---

## Section 10 — Server Settings

The **ADMIN** tab is visible to admins and the host. Settings are stored on the server and apply to every player.

| Setting | Default | Range | Description |
|---|---|---|---|
| **Cost Discount** | 0% | 0–100 | Percentage off the vanilla grove price |
| **Respect Planting Season** | On | On / Off | When on, grapes can only be planted during the game's plantable period. Turn off to allow planting year-round. |
| **Build Speed** | NORMAL | FAST / NORMAL / SLOW / VERY SLOW | How gently rows are fed to the engine |

### Build Speed in detail

Farming Simulator builds trellis and fence sections from an internal queue that it drains at a fixed rate — one section per frame. Every client rebuilds each section locally as it arrives, and each client's queue drains at that same rate.

Feed the queue faster than it drains and it backs up. The result is rows that have **collision but no visible mesh** — an invisible wall you can't walk through. It looks like a rendering bug; it's actually a pacing problem.

Auto Grove paces itself to the engine deliberately. The settings map to the interval between sections:

| Setting | Interval | When to use |
|---|---|---|
| **FAST** | 60 ms | Verified good, but less headroom on slow clients |
| **NORMAL** | 100 ms | Default. Verified good in multiplayer with comfortable margin. |
| **SLOW** | 160 ms | If any client is seeing invisible rows |
| **VERY SLOW** | 250 ms | Last resort for very low-end clients |

If a player reports invisible rows, drop the speed one step, demolish the affected grove, and replant.

---

## Section 11 — Multiplayer

Auto Grove was built multiplayer-first, not adapted to it afterwards.

### Server authority

Every action is validated and performed on the server:

- **Field ownership** is re-checked server-side on every request.
- **Farm Manager rights** are re-checked server-side.
- **Affordability** is re-checked server-side.
- **Field busy state** is tracked server-side, so two players can't start jobs on the same field at once.

A client-supplied field number is treated as a request, never as an instruction. Nothing a client asserts is trusted.

### Replication

Rows replicate to every client through the game's own placeable networking, which is the same mechanism the construction screen uses. Section building is paced with every client's rendering queue in mind, not just the host's.

### Settings

Server settings (discount, planting season, build speed) live on the server and apply to everyone. A client changing its local view of them changes nothing.

### Supported configurations

| Configuration | Supported |
|---|---|
| Single-player | Yes |
| Multiplayer, listen server (host playing) | Yes |
| Multiplayer, dedicated server | Yes |
| Dedicated server, headless | Yes |

### Installing on a dedicated server

The mod must be installed on **both** the server and every client. After uploading a new version, restart the server — Farming Simulator reads mod zips at startup.

---

## Section 12 — Guidance Steering & AI Helpers

Because Auto Grove builds groves from the game's own orchard placeables, a finished grove is indistinguishable from a hand-built one to the rest of the game. That cuts both ways.

### Guidance steering works

Vanilla **steering assist** works in Auto Grove groves with no additional setup. The game reads the vine areas your grove registers and generates a course from them.

Where the line falls depends entirely on the **implement**, because Farming Simulator classifies vineyard tools into two kinds:

**Straddle the row — line sits on the plants (correct for these machines):**

| Implement | Type |
|---|---|
| ERO Grapeliner 7000 | Harvester |
| Gregoire GL86 | Harvester |
| New Holland Braud 9070L | Harvester |
| New Holland Braud 9090X | Harvester |

**Drive between rows — line sits in the alley centre:**

| Implement | Type | Working width |
|---|---|---|
| Berthoud WinAir 1000 | Sprayer | 9.5 m |
| Hardi Mercury 4000L | Sprayer | 4.0 m |
| Provitis MP 122 OCEA | Pruner | — |
| Agrisem Disc-O-Vigne V | Cultivator | 1.5 m |
| TMC Cancela TPN140 | Mulcher | — |

If your guidance lines are running over the plants and you're using a **harvester**, that's correct — the machine straddles the vine row and drives over it.

If you're using a sprayer and the lines still run over the plants, check that it's a vineyard sprayer. All the between-row tools above are in the **`grapeTools`** store category. An ordinary field sprayer carries no vineyard classification at all, so the game generates a plain field course spaced by boom width, with no knowledge of where your rows are.

**The tractor doesn't matter.** A narrow vineyard tractor such as the Fendt 200 V Vario is the right power unit, but it contributes nothing to how the guidance line is placed. Only the attached implement does.

**One gotcha:** a sprayer reports a real working width, so the course holds until you leave the field. If you swap implements mid-field, drive off the field and back on to force a fresh course.

### AI helpers do not work in vineyards

**This is a base-game limitation, not an Auto Grove one.**

Farming Simulator 25 generates the vineyard course perfectly well, then refuses to let a hired worker drive it, stopping the job with its own built-in "vineyard not supported" message. The game ships a dedicated error message for exactly this case — it is a deliberate design decision by the developers, not an oversight or a bug.

This applies to **any** vineyard, including one you build entirely by hand in the construction screen. Auto Grove changes nothing about it in either direction.

No mod can lift this restriction without replacing the game's field-work AI wholesale, including writing row-aware turning logic from scratch. Your vine rows are physical objects with collision; an AI that misjudges a row-end turn drives through them.

Steering assist is unaffected. You can drive the rows yourself with guidance, which is how vineyards are worked in the base game.

---

## Section 13 — Troubleshooting

### The panel won't open

- Confirm the mod is enabled in the mod menu for this savegame.
- Check whether **F6** has been rebound, or is bound by another mod, under **Options → Controls**.
- If you have several RocklandUSA Gaming mods installed, F6 opens a directory first — select Auto Grove from it.

### No fields are listed

The FIELD tab shows **NO OWNED FIELDS** when your farm doesn't own any farmland. Buy a field first.

If you've just bought one and it isn't listed, press **REFRESH** on the FIELD tab.

### The plant button does nothing

Check, in order:

1. **Do you have Farm Manager rights?** Farm hands cannot plant.
2. **Can your farm afford it?** The Cost row turns red if not.
3. **Is the crop plantable now?** If **Respect Planting Season** is on, grapes are restricted to the game's plantable period. An admin can turn this off.
4. **Is a job already running on that field?** Only one at a time.

### Some rows are invisible but block movement

Rows were fed to the engine faster than it could render them. Lower the **Build Speed** on the ADMIN tab, demolish the grove, and replant.

This is more likely on lower-end machines and on multiplayer clients, since every client rebuilds each section locally.

### Residual crop left at the field edges

The field clear should strip the previous crop before planting. If you see remnants, capture the `[AutoGrove]` log lines from the job — the clear stage logs its own line with a duration, and its absence is diagnostic.

### Reading the log

`Documents\My Games\FarmingSimulator2025\log.txt`, lines prefixed `[AutoGrove]`. A healthy job looks roughly like:

```
[AutoGrove] clearing field before planting...
[AutoGrove] job started: field 4, olive, 17 units, heading 0 deg
[AutoGrove] field 4 cleared in 611ms — planting now
[AutoGrove] olive grove placeable: data/placeables/orchards/olive/oliveSingleton.xml
[AutoGrove] placeable geometry: snapDistance=3 panelLength=3
[AutoGrove] segments laid: spacing 3.00m, quantum 3, max seg 48m -> 68 segments
[AutoGrove] field 4: 6 / 68 planted...
[AutoGrove] charged $22,015 to farm 1 (grove on field 4)
[AutoGrove] job complete: field 4 — Planted 68 — $22,015
```

On a dedicated server, pull the **server's** log rather than your client's — the server is where planting happens.

---

## Section 14 — FAQ

**Does this work on modded maps?**
Yes, on any map that ships the standard orchard placeables — effectively all of them, since the mod uses the base-game grape and olive placeables rather than map-specific ones.

**Can I plant on a field I don't own?**
No. Only owned fields are listed, and the server re-checks ownership before acting.

**What happens to the crop already growing there?**
It's cleared. Fruit, weeds, and stones are removed and the ground is tilled to cultivated soil before the first row goes in.

**Can I undo a grove?**
Yes — **Demolish This Grove** on the FIELD tab. It removes the grove and tills the rows back to bare field. Two taps to confirm.

**Will it work with CoursePlay and other field mods?**
The grove is built from the game's own orchard placeables at native spacing, so it's indistinguishable from a hand-built grove to any other mod.

**Why can't I change the row spacing?**
Because the orchard placeable dictates it. The game overwrites whatever spacing is requested with its own `snapDistance` and `panelLength`, so an editable slider would be showing you a number the game ignores.

**Why is it so expensive?**
It's priced at exactly the vanilla rate. A full field is several hundred sections, and always was — the construction screen simply charged you one placement at a time. Server admins can apply a discount.

**Can I plant a partial field?**
Not in this version. A job covers the whole field polygon.

**Does it work in single-player?**
Yes, fully. Single-player, listen server, and dedicated server are all supported.

**Do I need FSCore?**
No. Auto Grove is completely standalone. If FSCore is installed it integrates automatically, but nothing is required.

**Are there console commands?**
No, by design. Everything is in the F6 panel.

**Why do AI helpers refuse to work my vineyard?**
Because Farming Simulator 25 doesn't support AI helpers in vineyards at all — see [Section 12](#section-12--guidance-steering--ai-helpers). This applies to hand-built vineyards too.

**Can I use this on someone else's farm in multiplayer?**
No. You can only plant on fields owned by your own farm, and only with Farm Manager rights on that farm.

---

## Section 15 — Changelog

### 1.0.0.0 — Initial public release

- Whole-field vineyard and olive grove planting on any field your farm owns
- Row heading in degrees with a live compass readout and a best-angle recommendation
- Live preview of row count, section count, and total cost before committing
- Boundary-following row layout, including irregular and concave fields
- Native orchard spacing read from the game's own placeables at spawn time
- Automatic field clearing to cultivated ground before planting
- Vanilla pricing, charged on completion for what was actually placed
- Server-set cost discount, 0–100%
- Farm Manager permission requirement for planting and demolition
- One-action grove demolition with two-tap confirmation, tilling the field back to bare soil
- Admin-adjustable build speed for lower-end systems
- Planting-season toggle
- Full multiplayer support, server-authoritative throughout
- Shared **F6** settings panel across all RocklandUSA Gaming mods
- Optional FSCore integration

---

## Section 16 — Credits & License

**Author:** RocklandUSA Gaming

- **YouTube:** [@rocklandusa](https://www.youtube.com/@rocklandusa)
- **Twitch:** [rocklandusa](https://www.twitch.tv/rocklandusa)
- **Discord:** [Join the community](https://discord.gg/ahWDGanNP5)
- **Website:** [rocklandusa.com](https://rocklandusa.com)

Auto Grove is proprietary software distributed exclusively through the official GIANTS ModHub. See [LICENSE](../LICENSE) for full terms.

This documentation is licensed under CC BY-NC-ND 4.0.

"Farming Simulator" is a trademark of GIANTS Software GmbH. Auto Grove and its documentation are not affiliated with or endorsed by GIANTS Software.
