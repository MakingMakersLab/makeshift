# V2 iPad verification checklist

This package preserves the original application and the latest handoff zoom-suppression changes. It has not been verified on a physical iPad.

1. On iPad Safari in landscape, rapidly tap the empty 3D canvas twice or more. Confirm the entire webpage does not zoom.
2. Drag one finger on empty canvas; confirm the orbit directions feel correct.
3. Drag a material with one finger; confirm it moves.
4. Pinch with two fingers; confirm only the 3D camera zooms, not the webpage.
5. Pan with two fingers; confirm the model view pans.
6. Tap Drinking straw, craft stick, and cardboard; confirm inventory decrements once per tap.
7. Duplicate a whole piece; confirm it uses one remaining stock item.
8. Cut a straw; confirm all pieces remain usable and undo cannot reverse the cut.
9. Discard a piece; confirm it does not return to stock.

To run locally, keep index.html, app.js, style.css, three.js in the same folder and serve with `python -m http.server 8000`.

V2 double-tap patch: verify rapid taps INSIDE the 3D canvas no longer zoom Safari. This is not a site deployment.


## Rotation-button double-tap zoom fix
On iPad Safari, select a piece and tap the same X/Y/Z rotation button rapidly 3–5 times. Each tap should rotate 15° without zooming the webpage. Repeat on CW and CCW. Verify one-finger orbit, two-finger pan/pinch, and material inventory remain unchanged. The fix is in `style.css` and `app.js`; publish both files to test on the live site.
