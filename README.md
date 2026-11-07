# Playback-button validation captures

For blixvip/html-anime issue #4. The existing production CSS hides the legacy `.preview` component. The test server reveals that component with a test-only `.preview { display: block !important; }` override to exercise pointer interaction and inspect the accessibility tree. Production CSS is unchanged.

The wide capture is 1440x1000; the narrow capture is 390x844. Both show the paused Play action. Pointer clicks changed Play to Hold and advanced frames, then changed Hold to Play and stopped frame advancement. Explicit `?frame=12`, reduced-motion startup and normal startup states were checked at both widths. The accessibility tree exposes an ordinary named button without a pressed property; the original visible fixture exposed Play with pressed=true.

These are isolated component checks, alongside a separate served-site check that confirmed the component remains hidden in production CSS. Actual screen-reader speech and full-film rendering were not tested.
