# Animated sites + agent-swarm rebuild
Open `index.html` (or either site). Needs internet only for Google Fonts.

## The cursor animation (shared/swarm.js)
Recreates the "Rebuilt by N agents" effect from the videos:
1. Scan: a flock of tiny cursors circles a loading tile while the HUD shows "Scanning page…".
2. Build: agents claim page layers top to bottom, drag out blue wireframe boxes (handles, + mark, size chip),
   then fill them: text types in with a caret, images show a grey placeholder, numbers flicker in red, a second
   agent sometimes jumps in with stacked red boxes, red snap guides flash. The page auto-scrolls to follow.
3. Done: "Rebuilt by 48 agents in 19.2s" with Continue / Replay / close.
HUD buttons: Tour = toggle camera follow, 1x = speed (1x/2x/4x), X (or Esc) = skip.
Config (set before the script): window.SWARM_CONFIG = { maxAgents, maxActive, scan, camera, blue, red, colors }.
Replay from code: Swarm.replay(). Listen for the end: addEventListener('sw:done', ...).
To add to any page: copy the 3 head lines (inline script, style, meta swarm) from a site's index.html, then load swarm.js with defer.

## Other effects (shared/effects.js + effects.css)
Scroll progress, staggered reveal, count-up, scramble, typewriter, magnetic buttons, 3D tilt, ripple, spotlight,
parallax, marquee, glitch, nav hide. When the swarm is present, reveal/count/scramble/type are skipped (swarm builds the page).
`shared/cursors.js` is the older ambient-cursor version (unused now).
All motion is off for visitors with reduce-motion enabled.
