# Pitara Plugin System

> **Status: Planned — not yet available.**
> The plugin API is under design. This page describes the intent, the first plugin types planned, and how to get involved early.

---

## What plugins will enable

Pitara's core is a fast, on-device photo search engine. Plugins will let the community extend it without touching the core — adding new ways to tag, browse, and organize photos.

The first plugin type planned is **Custom Tag Providers**.

---

## Plugin Type 1 — Custom Tag Providers *(planned)*

Today Pitara auto-tags every photo with time of day, day of week, season, location, camera, and festival data. A Custom Tag Provider plugin will let anyone add a new tagging dimension — and a new tab in the Pitara sidebar to browse by it.

**Example use cases the community could build:**
- A "Faces" tag provider that tags photos by detected people
- A "Weather" tag provider that looks up historical weather for the photo's GPS + date
- A "Project" tag provider that lets users manually assign photos to named projects
- A "Color mood" provider that tags by dominant color palette
- A "Trip" provider that groups photos into trips based on location clusters

---

## Plugin Type 2 — Custom Views / Tabs *(planned)*

Beyond tagging, plugins will eventually be able to add entirely new sidebar tabs to the Pitara UI — custom browsing experiences built on top of Pitara's index.

---

## How the plugin system will work *(design intent)*

- Plugins will be separate files or folders dropped into a `Plugins\` directory in the Pitara install
- Pitara will discover and load them at startup
- Each plugin will declare what it provides (tag provider, view, etc.) via a manifest
- Plugin code will have access to photo metadata but not to the Pitara core internals
- The `.fes` festival format is an early example of this pattern — external data files that Pitara loads and applies automatically

The full plugin specification will be published here when the API is stable.

---

## Get involved

If you have an idea for a plugin you'd want to build, **open an issue** in this repo tagged `plugin-request`. Early ideas will directly shape how the API is designed.

If you're a developer who wants early access to the plugin API when it's ready, watch this repo or leave a comment in any open `plugin-request` issue.

---

## Timeline

The plugin API will be designed once Pitara's core feature set is stable. No date is committed. Watch this repo for updates.

**[GetPitara.com](https://www.getpitara.com)**
