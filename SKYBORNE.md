# Skyborne's three.js

This is Skyborne's copy of [mrdoob/three.js](https://github.com/mrdoob/three.js). The `skyborne` branch holds an upstream release plus the renderer changes Skyborne needs.

- **Base:** upstream tag `r185`, commit `2431a09f46f34c560bc8e44b33be0e567723d5b9`. The tree is trimmed to what the npm package and its build use (`src`, `build`, `examples/jsm`, `utils`, `test`). The examples' assets, the docs and the editor were dropped, so installing from git stays small.
- **Our changes:** each is its own commit on top of the base, with the reason and the measurement in its message. Every change to `src/` is followed by `npm run build`, so `build/` stays in step, because Skyborne imports the prebuilt `three/webgpu` bundle.
- **Upgrading:**
  1. Fetch the next upstream tag.
  2. Make a new trimmed base commit from it.
  3. Cherry-pick our commits onto it.
  4. Rebuild.
  5. Point Skyborne's `package.json` at the new commit.
- **Consumed as:** `"three": "github:itsPreto/three.js#<commit>"` in Skyborne's `package.json`.

## Why r185

On the `skyborne` branch (r186), Skyborne's GPU-skinned zombie horde renders as exploded shards. The same scene renders correctly on r185, and the cause inside r186 has not been identified yet. Skyborne stays on this branch (`skyborne-r185`) until it is. Check the horde before moving to r186 or later.
