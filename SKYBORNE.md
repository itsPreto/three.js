# Skyborne's three.js

This is Skyborne's copy of [mrdoob/three.js](https://github.com/mrdoob/three.js). The `skyborne` branch holds an upstream release plus the renderer changes Skyborne needs.

- **Base:** upstream tag `r186`, commit `148ef33ecb6d2502ff796d4554abd1549c95d519`. The tree is trimmed to what the npm package and its build use (`src`, `build`, `examples/jsm`, `utils`, `tsl`, `test`). The examples' assets, the docs and the editor were dropped, so installing from git stays small.
- **Our changes:** each is its own commit on top of the base, with the reason and the measurement in its message. Every change to `src/` is followed by `npm run build`, so `build/` stays in step, because Skyborne imports the prebuilt `three/webgpu` bundle.
- **Upgrading:**
  1. Fetch the next upstream tag.
  2. Make a new trimmed base commit from it.
  3. Cherry-pick our commits onto it.
  4. Rebuild.
  5. Point Skyborne's `package.json` at the new commit.
- **Consumed as:** `"three": "github:itsPreto/three.js#<commit>"` in Skyborne's `package.json`.
