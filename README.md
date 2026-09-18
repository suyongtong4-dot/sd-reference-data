# Stable Diffusion Reference Data

Reference tables for prompt weight syntax, sampler selection, and VRAM behaviour on consumer hardware, compiled from hands-on testing runs.

## What is in here

| File | What it covers |
|---|---|
| `weight-syntax.md` | Prompt weighting marks for AUTOMATIC1111 WebUI and NovelAI, with the numeric multipliers and the range that actually works |
| `samplers.csv` | Sampler choice by use case, with step counts and convergence notes |
| `vram-3060-12gb.csv` | Measured VRAM usage on a 12 GB card across three configurations |
| `image-measurement-dimensions.md` | What an image-to-prompt tool can genuinely measure from pixels, and what it can only infer |

## Where the numbers come from

These figures were compiled from the testing notes published at <https://visualtoprompt.com/prompt-to-image/>. They are observations from real runs, not synthetic benchmarks.

Where a value could not be pinned down — for example the specific replacement upscaler used in the VRAM table — it is marked `unknown` rather than guessed. Anything marked `unknown` is an honest gap, not an oversight.

## Two caveats worth reading before you use this

1. **Weight syntax is per-interface.** The parentheses-and-brackets syntax and the curly-brace syntax belong to different tools and use different multipliers per level. Do not carry a number from one to the other.
2. **VRAM figures are card-specific.** The table was measured on one 12 GB card. Your card, your drivers and your installed extensions will shift these numbers.

## Going the other way

If you want to take an existing image and get a written prompt out of it, the measurements described in `image-measurement-dimensions.md` are what the browser-based tool at <https://visualtoprompt.com> produces. It runs entirely client-side — no upload, no account, no quota.

## Contributing

Corrections are welcome, especially from anyone who can fill in the values marked `unknown`.

## License

MIT. See `LICENSE`.
