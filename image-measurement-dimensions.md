# What Can Actually Be Measured From an Image

When a tool turns a picture into a written prompt, it is reading pixels — not understanding scenes. The distinction matters, because a prompt that confidently describes a subject that is not in the frame is worse than one that stays quiet about it.

This list separates what can be measured directly from what can only be inferred.

## Measured directly from the pixels

| Property | What is derived |
|---|---|
| Dominant colour palette | The five most common colours, named |
| Exposure | Whether the frame is bright and high-key or dark and low-key |
| Contrast range | Spread between light and dark |
| Colour temperature | Warm or cool cast |
| Detail density | How often brightness changes across the frame |
| Saturation | Including whether the image is close to monochrome |
| Framing | From the real width and height of the file |

## Inferred from those measurements

| Property | How it is inferred |
|---|---|
| Green-dominant vs blue-dominant | Foliage, or sky and water |
| Lighting character | Whether the light reads as soft, even, or directional |
| Composition | Whether there is a vignette, or the frame is lit evenly |

Inferred lines should be **tagged as inferred** in the output. A reader needs to know which lines came from a hard number and which came from a guess.

## What is out of scope entirely

An honest image-to-prompt tool does not detect:

- People or faces
- Objects
- Brands
- Scene identity or narrative

Claims that a photograph contains something that cannot be measured from its pixels are fabrications, not descriptions.

## Checkpoint settings worth publishing alongside a model

Checkpoint authors publish recommended settings, and those settings are not decoration. One widely circulated anime checkpoint recommends:

| Setting | Recommended value |
|---|---|
| VAE | `kl-f8/orangemix.vae` |
| Sampler | `DPM++ SDE Karras` or `DPM++ 2M Karras` |
| Clip skip | 1 or 2 |
| Steps | 20–30 |
| CFG scale | 6–12 |

Step outside that envelope and you are evaluating the checkpoint at settings it was never tuned for. An image that reads grey and washed out is frequently just a missing VAE.
