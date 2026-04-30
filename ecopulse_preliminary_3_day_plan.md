# EcoPulse — 3-Day Preliminary Implementation Plan

## 0. Preliminary Stage Reality Check

Based on the UM Technothon 2026 briefing slides, the preliminary stage does **not appear to require a working physical prototype**.

The preliminary deliverables are:

1. **Presentation slides**
   - Maximum 20 slides, excluding cover and thank-you slides.
   - Must be submitted as PDF.

2. **Pitching video**
   - Maximum 8 minutes.
   - Upload to YouTube as Unlisted.
   - Insert the YouTube link into the Google Form.

The event timeline separates **Preliminary Round: 25 April–3 May** from **Prototype Building: 9 May–5 June**, so the preliminary goal should be a strong concept, technical architecture, evidence-backed feasibility, and convincing video/storyboard — not a full prototype.

**Important:** Even without a physical prototype, the pitch should still show a believable demo concept using diagrams, mockups, animations, sensor-flow simulation, or dashboard mockups. Judges will still score clarity, feasibility, technical depth, and demo creativity.

---

# 1. Final Preliminary Objective

By the end of Day 3, the team should submit:

- Final pitch deck PDF.
- 8-minute YouTube unlisted pitch video.
- Evidence-backed problem framing.
- Clear EcoPulse architecture.
- Clear user journey.
- Sensor + AI + control logic explanation.
- Impact model showing RM, kWh, and CO₂ savings.
- Prototype roadmap for finalist stage.
- References/citations included in the slides.

The preliminary submission should convince judges that EcoPulse is:

> A practical, privacy-safe, retrofit energy management system for Malaysian classrooms, meeting rooms, and offices that detects room-level energy waste and triggers safe AC/lighting optimization.

---

# 2. Recommended Scope for Preliminary Pitch

## Commit to this version

**EcoPulse Lite — Privacy-Safe Room Energy Waste Detector**

A retrofit system for classrooms/offices that uses occupancy sensing, schedule awareness, and simple AI/rule-based optimization to detect unnecessary air-conditioning and lighting usage.

## What to emphasize

- Malaysian hot climate and AC-heavy spaces.
- Shared rooms where nobody feels responsible for switching things off.
- Old buildings where full Building Management Systems are expensive.
- Privacy-safe occupancy detection instead of camera surveillance.
- Room-level waste detection, not just whole-building energy dashboards.
- Safe automation with manual override.

## What to avoid overclaiming

Do **not** claim:

- Exact people identification.
- Perfect people counting.
- Fully autonomous campus-wide deployment.
- Proven real-world savings without pilot data.
- Complete AI HVAC optimization like enterprise systems.

Say instead:

> EcoPulse estimates occupancy levels and detects waste events. It recommends or triggers safe energy-saving actions using a retrofit architecture that can be validated during the prototype-building phase.

---

# 3. Team Role Delegation

## Team Composition

- 2 Software Engineering students
- 1 AI student
- 1 Electrical Engineering student
- 1 Mechanical Engineering student

## Suggested Role Assignment

| Role | Person Type | Main Responsibility | Final Output |
|---|---|---|---|
| Product + Backend Lead | Software Engineering Student 1 | System architecture, dashboard logic, data flow, slide integration | Architecture diagram, dashboard mockup logic, final deck coherence |
| UX + Frontend + Video Lead | Software Engineering Student 2 | Figma/dashboard mockups, pitch visuals, video editing/storytelling | UI mockups, storyboard, video draft, presentation polish |
| AI/Data Lead | AI Student | Occupancy estimation logic, waste prediction, impact model, simulation data | AI workflow, sample dataset, decision logic, savings calculator |
| Hardware/IoT Lead | Electrical Engineering Student | Sensor selection, ESP32/IR/relay feasibility, circuit diagram, BOM | Hardware architecture, component list, wiring diagram, feasibility risks |
| HVAC/Mechanical + Sustainability Lead | Mechanical Engineering Student | AC energy logic, thermal comfort, airflow/room model, sustainability impact | HVAC explanation, comfort constraints, energy-saving assumptions, retrofit design |

---

# 4. 3-Day Plan Overview

## Day 1 — Lock the Problem, Scope, and Evidence

**Goal:** Decide exactly what EcoPulse is, who it serves, why it matters, and what evidence supports it.

### Whole-Team Output by End of Day 1

- Final one-line pitch.
- Target user selected.
- Problem statement finalized.
- Competitor/differentiation points drafted.
- Technical architecture rough diagram.
- Slide skeleton created.
- Evidence folder started.

### Day 1 Task Breakdown

#### Software Engineering Student 1 — Product/System Lead

Tasks:

- Define final product scope:
  - Target: university classrooms + meeting rooms.
  - Core waste: AC/lights left running when room is empty or underused.
  - Solution: occupancy-aware retrofit energy control.
- Draft system architecture:
  - Sensors → ESP32/edge node → backend/database → dashboard → control output.
- Define main modules:
  - Occupancy module.
  - Waste detection module.
  - Control decision module.
  - Impact calculator.
  - Dashboard.
- Draft 20-slide outline.

Deliverables:

- `architecture_v1.png` or rough diagram.
- Slide outline.
- Product scope statement.

#### Software Engineering Student 2 — UX/Story Lead

Tasks:

- Create user persona:
  - Facility manager / classroom admin.
  - Secondary user: lecturer/student using the room.
- Draft before/after user journey:
  - Before: class ends, AC remains on, nobody notices.
  - After: EcoPulse detects empty room, sends notification/control action, logs savings.
- Start Figma/wireframe for dashboard:
  - Room status.
  - Occupancy level.
  - Waste detected.
  - Suggested action.
  - RM/kWh/CO₂ saved.
- Draft pitch hook.

Deliverables:

- Persona slide draft.
- User journey slide draft.
- Dashboard wireframe v1.

#### AI Student — AI/Data Lead

Tasks:

- Define practical AI scope:
  - Occupancy classification: empty / low / medium / high.
  - Waste-event classification: normal / warning / waste.
  - Simple prediction: likely unused after scheduled session.
- Create sample data schema:
  - timestamp
  - room_id
  - occupancy_level
  - temperature
  - humidity
  - schedule_status
  - ac_status
  - light_status
  - waste_event
  - estimated_kWh_wasted
- Draft decision rules:
  - Empty + AC on + no class = waste.
  - Low occupancy + AC too cold = recommend eco mode.
  - Scheduled empty + repeated waste = predictive shutdown recommendation.
- Identify what is real vs mocked for preliminary.

Deliverables:

- AI workflow diagram.
- Decision logic table.
- Sample dataset table.

#### Electrical Engineering Student — Hardware/IoT Lead

Tasks:

- Select realistic sensor options:
  - PIR: cheap motion detection.
  - mmWave: better seated-presence detection.
  - Thermal array: privacy-safe spatial heat map if available.
  - Temperature/humidity sensor.
  - IR LED/blaster for AC remote simulation.
  - Relay/smart plug for light/fan demo during finalist stage.
- Create preliminary BOM:
  - ESP32.
  - PIR/mmWave.
  - DHT22/SHT31.
  - IR LED module.
  - Relay module.
  - LED/fan load for demo.
- Draft hardware block diagram.
- List electrical safety boundaries:
  - Do not directly wire to real AC mains in hackathon demo.
  - Use IR control or low-voltage demo load.

Deliverables:

- Hardware component table.
- Hardware block diagram.
- Safety/risk notes.

#### Mechanical Engineering Student — HVAC/Sustainability Lead

Tasks:

- Explain why AC is the strongest focus:
  - Cooling is intuitive and Malaysia-relevant.
  - Classrooms/meeting rooms often use split ACs.
- Define comfort rules:
  - Do not shut off AC immediately when people are inside.
  - Use delay and manual override.
  - Use eco mode rather than aggressive shutdown.
- Draft impact formula:
  - Energy saved = equipment power × avoided runtime.
  - Cost saved = kWh saved × tariff.
  - CO₂ avoided = kWh saved × grid emission factor.
- Define room model:
  - Small classroom.
  - Medium seminar room.
  - Lecture hall.

Deliverables:

- HVAC logic slide.
- Sustainability impact formula.
- Comfort/safety principles.

---

## Day 2 — Build the Pitch Assets and Technical Story

**Goal:** Convert research into slides, diagrams, mockups, and a believable 8-minute pitch.

### Whole-Team Output by End of Day 2

- Slide deck draft complete.
- Dashboard mockups complete.
- Architecture diagram complete.
- Impact model table complete.
- Video storyboard complete.
- Script draft complete.

### Day 2 Task Breakdown

#### Software Engineering Student 1 — Product/System Lead

Tasks:

- Create final system architecture diagram.
- Explain data flow:
  - Sensor data collected.
  - Occupancy estimated.
  - Waste event detected.
  - Control action recommended/triggered.
  - Savings logged.
- Create backend/data model slide.
- Make the feasibility slide:
  - What can be built in finalist stage.
  - What is mocked now.
  - What is validated later.

Deliverables:

- Final architecture slide.
- Backend/data flow slide.
- Feasibility slide.

#### Software Engineering Student 2 — UX/Story Lead

Tasks:

- Finalize dashboard mockups:
  - Room overview screen.
  - Room detail screen.
  - Waste event timeline.
  - Savings summary.
- Create visual demo storyboard:
  - Empty classroom.
  - AC/lights still on.
  - EcoPulse detects waste.
  - Action taken.
  - Dashboard updates.
- Start assembling pitch video visuals.

Deliverables:

- Dashboard mockups.
- Storyboard frames.
- Video asset folder.

#### AI Student — AI/Data Lead

Tasks:

- Create AI decision diagram:
  - Sensor features + schedule + AC state → occupancy/waste state → action.
- Build a small simulated table/chart:
  - Before optimization: AC left on after class.
  - After optimization: delayed shutdown/eco mode.
- Create simple impact calculator:
  - Input: AC power, light power, wasted minutes/day, tariff, emission factor.
  - Output: kWh, RM, CO₂.
- Prepare explanation of why exact people counting is unnecessary:
  - Energy decisions only need occupancy levels.

Deliverables:

- AI logic slide.
- Simulated before/after chart.
- Impact calculator table.

#### Electrical Engineering Student — Hardware/IoT Lead

Tasks:

- Create final hardware flow:
  - Sensor node.
  - ESP32.
  - Wi-Fi/MQTT/HTTP.
  - IR control.
  - Relay/smart plug simulation.
- Create finalist prototype plan:
  - What components to buy.
  - What can be built in 1 week.
  - What backup sensors to use.
- Add risk mitigation:
  - If thermal sensor fails → use PIR/mmWave + simulated heatmap.
  - If IR fails → show LED/fan control.
  - If relay unsafe → use low-voltage LED/fan.

Deliverables:

- Hardware flow slide.
- BOM slide.
- Risk mitigation slide.

#### Mechanical Engineering Student — HVAC/Sustainability Lead

Tasks:

- Create AC control strategy:
  - Empty room → delayed shutdown.
  - Low occupancy → raise setpoint / eco mode.
  - Occupied room → maintain comfort.
  - Manual override always available.
- Create impact narrative:
  - Focus on avoided wasted runtime rather than unrealistic magic savings.
- Validate impact assumptions with references where possible.
- Help AI student check formulas.

Deliverables:

- HVAC strategy slide.
- Impact assumptions slide.
- Comfort/ethics slide.

---

## Day 3 — Polish, Record, Submit

**Goal:** Finalize slides, record a clear 8-minute pitch, upload, and submit before deadline.

### Whole-Team Output by End of Day 3

- Final PDF deck.
- Final YouTube unlisted video.
- References checked.
- Google Form ready.
- Backup copy stored.

### Day 3 Task Breakdown

#### Software Engineering Student 1 — Final Deck Owner

Tasks:

- Merge all slides.
- Make sure story flows:
  - Problem → user pain → solution → architecture → AI/control → impact → feasibility → ask/roadmap.
- Check slide count.
- Export PDF.
- Confirm citations are included.

Deliverables:

- Final PDF deck.

#### Software Engineering Student 2 — Final Video Owner

Tasks:

- Record/edit pitch video.
- Add dashboard mockup animations if possible.
- Keep video under 8 minutes.
- Upload YouTube as Unlisted.
- Verify link works.

Deliverables:

- Final YouTube unlisted link.

#### AI Student — Evidence + Technical Defense Owner

Tasks:

- Check all AI claims are realistic.
- Remove overclaims.
- Prepare Q&A backup answers:
  - Why not just PIR?
  - Why not smart plug?
  - Why not camera?
  - How accurate is counting?
  - What data is needed?
- Verify impact formulas are labelled as assumptions.

Deliverables:

- Q&A technical defense sheet.
- Final impact model.

#### Electrical Engineering Student — Hardware Defense Owner

Tasks:

- Verify component feasibility.
- Check finalist prototype roadmap.
- Prepare answer for safety questions:
  - No unsafe AC wiring.
  - IR remote simulation first.
  - Low-voltage demo load.
- Confirm hardware diagram is accurate.

Deliverables:

- Final hardware feasibility notes.
- Safety answer sheet.

#### Mechanical Engineering Student — HVAC + Sustainability Defense Owner

Tasks:

- Check AC comfort logic.
- Ensure the solution does not sacrifice user comfort.
- Prepare answer for:
  - What if the room is occupied but people are still?
  - What if shutting off AC causes discomfort?
  - What if room heats up quickly?
- Finalize sustainability wording.

Deliverables:

- Final HVAC/comfort notes.
- Sustainability defense sheet.

---

# 5. Recommended Slide Outline

Maximum 20 content slides, excluding cover and thank-you.

1. Cover — EcoPulse
2. Problem hook — Empty classrooms, AC still running
3. Malaysia/context relevance — energy waste in shared spaces
4. Target user — facility manager/classroom admin
5. Current solutions gap — smart plugs, motion sensors, dashboards, BMS
6. One-line solution — EcoPulse
7. How EcoPulse works — simple 3-step flow
8. System architecture — sensors, edge, backend, dashboard, control
9. Occupancy detection — empty/low/medium/high, not exact identity
10. AI/data logic — schedule + occupancy + device state → waste decision
11. Automation logic — safe control rules and manual override
12. Dashboard mockup — live room status
13. Impact model — kWh/RM/CO₂ formulas
14. Example scenario — before vs after class ends
15. Hardware feasibility — ESP32, sensors, IR, relay/fan demo
16. Retrofitting/scalability — no rewiring, old-building friendly
17. Ethics/privacy — no camera, local/aggregated sensing
18. Prototype roadmap — finalist-stage build plan
19. Risks + mitigations
20. Why EcoPulse should win

---

# 6. 8-Minute Pitch Video Structure

| Time | Segment | Owner |
|---|---|---|
| 0:00–0:40 | Hook: “Class ended, but the AC is still running.” | UX/Frontend Lead |
| 0:40–1:30 | Problem + target user | Product/System Lead |
| 1:30–2:20 | Existing solutions gap | Product/System Lead |
| 2:20–3:20 | EcoPulse solution overview | Product/System Lead |
| 3:20–4:20 | Sensor + hardware architecture | Electrical Lead |
| 4:20–5:20 | AI/waste detection logic | AI Lead |
| 5:20–6:10 | HVAC comfort + sustainability impact | Mechanical Lead |
| 6:10–7:10 | Dashboard/mock demo walkthrough | UX/Frontend Lead |
| 7:10–7:45 | Finalist prototype roadmap | Electrical + Software |
| 7:45–8:00 | Closing line | Whole team / best speaker |

Recommended closing line:

> EcoPulse does not wait for the electricity bill to reveal waste. It detects room-level waste as it happens and turns energy awareness into action.

---

# 7. Preliminary-Level Mock Demo Plan

Since no physical prototype appears required for preliminary, use a mock demo in the pitch video.

## Mock Demo Flow

1. Show classroom diagram.
2. Class ends at 4:00 PM.
3. AC and lights remain ON.
4. EcoPulse receives:
   - Occupancy = empty.
   - Schedule = no class.
   - AC status = ON.
5. EcoPulse flags waste event.
6. System recommends/executes:
   - Turn off lights.
   - Send IR command to AC.
7. Dashboard updates:
   - Wasted minutes avoided.
   - Estimated kWh saved.
   - Estimated RM saved.
   - Estimated CO₂ avoided.

## Visual Assets Needed

- Room layout diagram.
- Sensor node illustration.
- Dashboard mockup.
- Before/after chart.
- Savings calculator screenshot.
- Final prototype roadmap visual.

---

# 8. Technical Architecture

## Data Flow

```text
Occupancy sensor + temperature sensor + schedule data
        ↓
ESP32 / edge node
        ↓
Backend / database
        ↓
AI + rule engine
        ↓
Decision: normal / warning / waste
        ↓
Dashboard + notification + IR/control action
        ↓
Savings log: kWh, RM, CO₂
```

## Occupancy Logic

```text
0 detected presence → Empty
Small heat/presence signal → Low occupancy
Multiple zones active → Medium occupancy
Many zones active → High occupancy
```

## Waste Detection Logic

```text
IF occupancy = empty
AND AC/light = ON
AND room schedule = inactive
FOR more than X minutes
THEN waste_event = true
```

## Control Logic

```text
IF waste_event = true
THEN send notification OR trigger safe control action

IF room becomes occupied again
THEN restore comfort mode

IF user presses override
THEN pause automation
```

---

# 9. Finalist-Stage Prototype Roadmap

Although preliminary likely does not require prototype, judges should see that the team can build one later.

## Hardware MVP

- ESP32
- PIR or mmWave sensor
- Temperature/humidity sensor
- IR LED/blaster
- LED strip or desk lamp simulation
- Mini fan as AC simulation
- Optional thermal array if available

## Software MVP

- Simple web dashboard
- Firebase/Supabase/simple backend
- Sensor status stream
- Waste-event detection
- Impact calculator
- Manual override button

## AI MVP

- Rule-based classifier first
- Simple ML classifier only if time allows
- Simulated room-usage prediction
- Occupancy level classification, not exact counting

---

# 10. Brutal Risk List

| Risk | Why It Matters | Fix |
|---|---|---|
| Looks like normal motion sensor | Judges may see it as generic | Emphasize sensor fusion + schedule + cost impact + AC control |
| Thermal counting is unreliable | Low-res thermal may fail | Do not claim exact counting; use occupancy levels |
| Prototype AC control may be unsafe | Real AC wiring is dangerous | Use IR remote simulation and low-voltage demo load |
| Too much AI overclaim | Judges may doubt feasibility | Keep AI as classification/recommendation, not magic optimization |
| Impact numbers challenged | Savings are assumptions | Label assumptions clearly and show formulas |
| Dashboard looks generic | Weak demo appeal | Make dashboard event-based: “waste detected now” |
| User comfort concern | Automation may annoy users | Add manual override and delayed shutdown |
| Privacy concern | Occupancy systems can feel like surveillance | No camera, no face data, aggregated room-level detection |

---

# 11. Key Q&A Defense Answers

## Why not just use a motion sensor?

A motion sensor only detects movement. In classrooms and meeting rooms, people may sit still. EcoPulse uses occupancy level estimation, schedule context, and device-state awareness to decide whether energy is actually being wasted.

## Why not just use smart plugs?

Smart plugs control individual appliances. EcoPulse focuses on room-level waste: occupancy, schedules, AC/lights status, and estimated impact.

## Why not use cameras?

Cameras raise privacy concerns. EcoPulse is designed to use privacy-safe sensing such as thermal/mmWave/PIR and aggregates data at room level.

## Does EcoPulse count exact people?

Not in the MVP. Exact identity and exact counting are unnecessary. For energy control, empty/low/medium/high occupancy is enough.

## Is automation safe?

Yes, because the proposed control logic includes delay, manual override, fail-safe defaults, and avoids direct high-voltage AC wiring in the prototype.

---

# 12. Open Nuances / Uncertainties to Confirm

These do not block the preliminary plan, but the team should confirm them quickly:

1. Are teams allowed to show a mock/simulated demo in the preliminary video?
2. Do all pitch video materials need to be created only within the preliminary submission period?
3. Is there any hidden requirement for a prototype video, despite the briefing listing prototype building after finalist announcement?
4. Which sensor can your electrical engineering member realistically access quickly: PIR, mmWave, or thermal array?
5. Who is the strongest speaker for the 8-minute video?
6. Will the team use Figma, Canva, PowerPoint, or Google Slides for the deck?
7. Do you want the target environment to be university classrooms only, or classrooms + offices?

Recommended default answers unless contradicted:

- Use simulated/mock demo for preliminary.
- Focus on classrooms first.
- Mention offices only as expansion.
- Use PIR/mmWave as realistic MVP sensors.
- Keep thermal as optional privacy-safe enhancement.

---

# 13. Final Decision for Preliminary

## Decision: Reshape and Commit

EcoPulse is worth committing to, but only as a practical retrofit room-energy waste detector, not as an overambitious full AI HVAC optimization platform.

## Confidence

- Preliminary pitch strength: **8.5/10**
- Finalist prototype feasibility: **8/10**
- Real-world deployment readiness: **5/10 without pilot testing**

## Final Positioning

> EcoPulse is a privacy-safe retrofit system that detects real-time room energy waste in Malaysian classrooms and offices, then recommends or triggers safe AC and lighting actions while tracking kWh, RM, and CO₂ impact.

