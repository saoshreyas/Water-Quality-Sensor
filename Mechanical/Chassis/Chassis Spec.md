# Mechanical Chassis Specification — River/Lake Water Quality Buoy 

**Version:** 1.0 

**Covers:** V1 (near-shore, fixed/tethered) and V2 (open-water, propeller-equipped) 

**Owner:** Mechanical Engineering 

**Dependencies:** Electrical BOM (Section 3, main project spec) for component dimensions/weights; Power Budget (pending, from EE) for battery sizing which drives hull volume 

--- 

## 1. Design Philosophy 

V1 and V2 share a common design language and, where possible, common parts — but they are treated as **two distinct chassis**, not one chassis with an optional add-on. Propulsion changes buoyancy, stability, waterproofing surface area, and internal volume requirements enough that retrofitting a V1 hull with a motor after the fact is not the intended path. Shared components (electronics enclosure, sensor mounting hardware, antenna mast) should use common part numbers across both versions wherever the added V2 requirements don't force a change. 

--- 

## 2. V1 Chassis — Near-Shore Fixed Buoy 

# ### 2.1 Overview 

A moored, non-propelled buoy designed to sit near-shore in flowing water, fully hand-retrievable without a boat, and secured against both drift and theft. 

### 2.2 Hull 

| Attribute | Spec | 

|---|---| 

| Hull type | Catamaran-style dual-pontoon | 

| Material | HDPE (preferred) or fiberglass | 

| Material rationale | HDPE: UV-resistant, cheap, easy to machine/drill, naturally buoyant, chemically inert in freshwater. Fiberglass: alternative if a more rigid/custom-molded shape is desired; higher cost and labor. | 

| Target overall length | 40–60 cm (tentative — confirm against final electronics + battery volume) | 

| Target overall beam (width) | 30–40 cm (dual-pontoon spacing for stability) | | Draft (submerged depth) | Shallow — enough to keep sensor probes submerged at low flow, without excessive drag in current | 

| Color/finish | Matte, non-reflective, muted tone (not bright safety colors) — deliberately lowvisibility to reduce theft appeal (see Section 4.5 of main spec) | 

# ### 2.3 Buoyancy & Stability 

- **Ballast:** low-mounted weight (sealed compartment, sand/gravel/lead shot options) beneath the pontoons to keep center of gravity low and electronics enclosure upright. 

- **Buoyancy margin:** hull displacement must exceed total system weight (electronics + battery + sensors + solar panel + ballast + hull itself) by a safety margin — target minimum 30–50% reserve buoyancy to handle wave action, debris accumulation, and biofouling weight growth over the 30-day deployment. 

- **Stability requirement:** dual-pontoon spacing sized so the unit resists tipping from wind, wake from passing boats, or someone bumping it during maintenance. 

- **Action item:** once electronics + battery weight is finalized (post power-budget meeting), calculate actual displacement/ballast requirement — current dimensions above are placeholders pending that number. 

### 2.4 Electronics Enclosure Mounting 

- Mounted on top of/between pontoons, **above splash line**, isolated from the wet sensor section below. 

- IP67/68 rated box (per main spec Section 4.2), secured with a lockable hasp/latch (theft mitigation) and tamper-resistant fasteners. 

- Mounting: through-bolted to hull deck with marine-grade stainless hardware and sealed washers/gaskets at each penetration — avoid adhesive-only mounting given month-long unattended exposure. 

### 2.5 Sensor Probe Mounting 

- Probes (temp, turbidity, pH, DO) mounted on a **fixed bracket** extending down from the hull into continuous flow — no moving parts (per corrected design; see main spec Changelog item 1). 

- Bracket material: HDPE or 316 stainless, corrosion-resistant, rigid enough to avoid probe vibration/damage in current. 

- Probe spacing: sufficient separation between probes to avoid one probe's wake/turbulence affecting another (particularly turbidity, which is flow-sensitive). 

- Cable routing: sealed conduit or waterproof cable gland from each probe up into the electronics enclosure; service loop (slack) at each connection to allow probe removal for cleaning without disconnecting at the enclosure wall. 

- Guard: simple perimeter guard/cage around the probe cluster to prevent debris strikes and reduce accidental damage during handling/maintenance. 

### 2.6 Solar Panel Mounting 

- Top-mounted, angled for maximum sun exposure at deployment latitude/orientation. 

- Mounting hardware: corrosion-resistant standoffs, sealed cable entry into enclosure. 

- Panel sized per finalized power budget (pending EE input). 

### 2.7 Mooring & Anchor Hardware 

- **Tether:** vinyl-coated steel cable (bike-lock or marine-grade stainless), doubling as both mooring and anti-theft security line. 

- **Lock:** weatherproof padlock at the shore-anchor end. 

- **Shore anchor point:** bolted/chained to a fixed structure (post, tree, dock cleat) — not a loose or movable object. 

- **Tether length:** sized so the unit can be pulled fully onto the bank by hand for maintenance, without requiring the maintainer to wade into current. 

- **Secondary safety line:** optional slightly-slack backup line in case primary tether is damaged (e.g., by flood debris), without relying on a breakaway mechanism that would compromise the anti-theft cable. 

# ### 2.8 Signage 

- Small weatherproof placard: project name, "research equipment" notice, contact info — deters both theft and well-meaning "rescue" removal. 

--- 

## 3. V2 Chassis — Open-Water Propeller-Equipped Buoy 

# ### 3.1 Overview 

Builds on the V1 design language but is a **separate hull**, sized and shaped to accommodate propulsion hardware, larger battery capacity, and the buoyancy/stability implications of both. Intended for lake deployment where reach beyond shore/tether range is the goal — propulsion is for positioning, not emergency drift recovery (main spec Section 11). 

# ### 3.2 Hull 

| Attribute | Spec | 

|---|---| 

| Hull type | Modified catamaran, or single-hull "boat-like" form — **open decision, pending Section 3.6 discussion** | 

| Material | HDPE or fiberglass (same rationale as V1); fiberglass may be favored if hull shape complexity increases for hydrodynamic efficiency | 

| Target overall length | Larger than V1 — exact dimension pending motor/battery volume (see 3.4) | 

| Draft | Slightly deeper than V1 to accommodate submerged thruster(s) | 

| Color/finish | Same low-visibility approach as V1, though open-water deployment may reduce theft risk relative to near-shore V1 — reassess based on actual lake access/visibility | 

# ### 3.3 Buoyancy & Stability 

- Same reserve buoyancy margin target as V1 (30–50%), recalculated for V2's higher total system weight (larger battery, motor, propeller hardware, potentially reinforced hull). 

- Stability consideration specific to V2: thrust from the propeller(s) introduces a moment/torque not present in V1 — hull and ballast design must account for resisting roll/pitch during active propulsion, not just static floating conditions. 

- Weight distribution: motor/battery placement should keep center of gravity low and centered to avoid destabilizing the hull during motion. 

# ### 3.4 Propulsion Integration 

| Element | Spec / Open Question | 

|---|---| 

| Motor type | Brushed DC (per initial concept) — confirm against EE's current draw analysis; brushless may be worth evaluating for efficiency/lifespan if budget allows | 

| Motor count/placement | Open decision: single stern-mounted thruster (simpler, less maneuverable) vs. dual side-mounted (better maneuverability, more complexity/cost/power draw) | 

| Propeller guard | Required — cage/shroud around propeller to prevent fouling from weeds/debris/fishing line, and to reduce risk to wildlife or people nearby | 

| Shaft seal / waterproofing | **Flagged as highest mechanical risk item.** Motor shaft penetrating the hull to the propeller is a continuous-duty moving seal — must use a marinegrade shaft seal (lip seal or mechanical seal rated for continuous submersion), not a static gasket. Recommend sourcing a proven marine/RC-boat shaft seal component rather than custom-designing one. | 

| Motor compartment | Should be a separately sealed sub-enclosure from the main electronics bay, so a shaft seal failure floods only the motor compartment, not the sensor/compute electronics | 

| Battery capacity | Larger than V1 — sized once EE characterizes motor current draw and the team defines propulsion duty cycle (constant position-holding vs. scheduled trips vs. manualonly) | 

# ### 3.5 Electronics Enclosure 

- Same IP67/68 approach as V1, but confirm whether motor driver electronics live in the same enclosure as the ESP32/sensor stack or a separate compartment — **recommend separate power rail/compartment** to avoid electrical noise from motor switching affecting analog sensor readings (flagged in main spec Section 11). 

- Same locking/tamper hardware as V1, though re-evaluate necessity based on actual openwater accessibility/theft risk. 

# ### 3.6 Open Mechanical Design Questions (for team working session) 

- Hull form: modified catamaran vs. single boat-like hull — tradeoff between build simplicity (catamaran, reuses V1 tooling/knowledge) vs. hydrodynamic efficiency (single hull, likely better for sustained propulsion). 

- Thruster configuration: single vs. dual, and mount type (fixed stern vs. azimuth/steerable). 

- Whether V2 needs a rudder or relies solely on differential thrust (if dual motors) for steering. 

- Sensor probe mounting on a moving hull: confirm probes remain effective/representative while the unit is under way, or whether readings should only be taken while stationary (software/firmware decision with mechanical implications for probe placement relative to motor wake). 

### 3.7 Sensor Probe Mounting 

- Same fixed, continuous-submersion approach as V1 — no dip mechanism. 

- Placement must avoid motor wake/turbulence interfering with turbidity and DO readings — mount probes forward of or laterally offset from the propeller wake path. 

# ### 3.8 Solar Panel Mounting 

- Larger panel likely required given propulsion power draw (pending power budget) — confirm hull top surface area accommodates the needed panel size without excessive top-heaviness. 

# ### 3.9 Mooring (Secondary, Not Primary) 

- V2 is not intended to rely on a fixed short tether the way V1 does, but should still have a mooring/anchor option available for when it's not actively being repositioned, plus the same GPS/tamper telemetry as V1 for position monitoring. 

--- 

## 4. Shared Components Across V1 and V2 

| Component | Shared? | Notes | 

|---|---|---| 

- | Electronics enclosure (IP67/68 box) | Yes, same part | Same core box housing ESP32/modem/ADC | 

- | Sensor probes + mounting bracket concept | Yes, same design | Fixed continuous-submersion approach applies to both | 

- | Solar panel | Same part family, different size | V2 likely needs a larger panel | 

- | Locking hardware | Same part | Padlock/hasp approach applies to both if V2 retains theftmitigation needs | 

- | Antenna mounting | Same part | SMA LTE + GPS antenna mounting approach shared | 

| Hull material | Same material choice (HDPE or fiberglass) | Different hull geometry/size, same base material decision | 

--- 

## 5. Deliverables & Next Steps 

1. Finalize V1 hull dimensions once electronics + battery weight is confirmed (post powerbudget meeting). 

2. Produce V1 buoyancy/ballast calculation (displacement vs. total system weight). 

3. Source and bench-test a marine-grade motor shaft seal candidate for V2 before committing to final motor compartment design. 

4. Resolve V2 hull form decision (Section 3.6) as a team working session — feeds directly into V2 dimension/material finalization. 

5. Produce CAD models for both chassis once dimensions are locked, for review before fabrication/purchase of hull material. 

6. Build physical V1 prototype first; validate mounting, buoyancy, and waterproofing in bench/pool testing before field deployment. 

7. Use V1 build/test learnings to inform V2 fabrication approach. 

Below are the probes that need to be mounted to the chassis 

<u>pH Sensor</u> 

<mark>supports</mark> **7/24-hour monitoring** <mark>with a lifespan exceeding</mark> **4380 hours** 



<!-- Start of picture text -->
22 | 90 22.<br>ce| |=<br>| a 161 22.6<br>NPT3/4 NPT3/4<br><!-- End of picture text -->



<!-- Start of picture text -->
Hi op<br>. Sy p Ly<br>iked mre i bed<br>Joy is ial<br>| A<br><!-- End of picture text -->



<!-- Start of picture text -->
Jf Fail<br>|<br>“h<br>‘<br>renctiacaausti: §=6 LAN<br>= = = = | =e y<br>Co == Sit +<br>= = = - < — a<br>on ht hs iP be 8 bonintue<br>Gp SIL IEMILteels: om<br>|<br><!-- End of picture text -->



