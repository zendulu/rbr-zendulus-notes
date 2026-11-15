# Zendulus Rally Pacenotes

Auto-generated pacenotes for Richard Burns Rally, covering 518 stages.
Each stage has a folder in `MyPacenotes/` named exactly as RBR's
MyPacenotes expects, holding one plan file
`<stage folder> Zendulus V<N>.ini`. To install: copy the stage's
folder into `<RBR install dir>\Plugins\NGPCarMenu\MyPacenotes`.
To update: overwrite it. (NGPCarMenu uses the pacenote INI with the
latest modified filestamp.)

These notes are built to ship with the [**Zendrive**](https://github.com/zendulu/zendrive)
co-driver mod, which speaks them as written. If you drive base RBR with
**Jannemod V3**, `codriver-pack/` is a compatibility shim that lets
that setup speak the same words. The shim has had minimal testing —
tell us what you find.

## The scale

![The Zendrive corner scale](codriver-pack/Scale%20Sheets/corner-scale.png)

Corner severity follows the total heading change of the turn, spoken
the way EA Sports WRC and DiRT Rally 2.0 co-drivers do it:
"six … five … four … three … two … one … square … open hairpin …
hairpin … acute hairpin". Black rays are corner calls the stock RBR
co-driver already understands. Red rays need the codriver pack (or
Zendrive) installed.

Jannemod V3 has no scale that maps cleanly to how EA Sports WRC and
DiRT Rally 2.0 use pacenotes. We attempted a best-effort alignment of
our calling style onto its system; there is no direct one-to-one
match. The pack speaks our words through Jannemod's vocabulary slots —
install it and select the Zendrive notes mode, per
`codriver-pack/INSTALL.txt`.

## How these notes are made

Every note comes from stage geometry analysis — corner sweep, sight
lines, road surface, jumps and crests, obstacles near the racing
line. We do not hand-drive the stages. A volunteer driver pass
calibrates the result, but no human has driven all 518 stages.

What that means in practice:

- Turn severity is our most trusted layer. It is calibrated against
  driven stages and is generally consistent and high quality.
- Feature notes (chicanes, water, surface calls) are newer and less
  complete. Some notes are not as good as they should be, and some
  features — chicanes above all — are missed. Our current priority
  is better detection of surface-level chicanes.
- Expect a working baseline you refine to your taste, not finished
  hand-made notes. We aim to ship calls that are reliably correct
  and stay quiet where we are unsure.

## Creating issues

Feedback is welcome — this is why the notes live in a git repository.
Open an issue on [zendulu/rbr-zendulus-notes](https://github.com/zendulu/rbr-zendulus-notes/issues)
and include:

1. **The stage**, by its exact folder name.
2. **The problem**: a note that is wrong, badly timed, or missing.
   Say what you heard (or did not hear) and what you expected.
3. **The distance** if you can: the distance marker shown in-game,
   or the `distance` value in the plan file for the note in question.
4. **Video links or screenshots help tremendously** — an onboard
   clip that shows the corner and the call lands the issue fastest.

A note that a stage feels "off" overall is useful too, even without
distances. We read everything.

## Repository layout

```
README.md
MyPacenotes/     one folder per stage, as RBR's MyPacenotes names it,
                 each holding "<stage folder> Zendulus V<N>.ini"
codriver-pack/   the Jannemod V3 compatibility shim
  INSTALL.txt    copy Plugins + Scale Sheets over your RBR install
  Plugins/       the Zendrive notes mode (config only, no binaries)
  Scale Sheets/  the corner-scale and word-family images
```
