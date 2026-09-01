# quibble-h3
AI animation case study using ComfyUI + MiniMax H3 for persistent characters, reference-driven shots, cinematic continuity, and episodic storytelling.

# Quibble — MiniMax H3 × ComfyUI

**An AI-assisted animated short exploring persistent characters, controlled performance, and cinematic continuity using MiniMax H3 inside ComfyUI.**

Quibble is an experiment in building something closer to a repeatable animation production pipeline than a collection of isolated AI-generated shots.

The goal was simple:

**Can the same character survive across multiple generated shots while still being directed like a character?**

Rather than relying entirely on text-to-video generation, I used reference-driven generation to maintain Quibble's identity, costume, environment, composition, and performance across the sequence.

## Episode 01

Quibble is a would-be supervillain operating from an unnecessarily elaborate headquarters, assisted by GPT-2.0 — an extremely literal AI.

The project combines character comedy with a deliberately cinematic visual language inspired by stylized 3D animation, retro-futurist control rooms, and theatrical villain imagery.

Episode 01 is a short proof of concept for a potentially episodic format.

## Workflow

The animation was generated locally in **ComfyUI** using **MiniMax H3 Reference-to-Video**.

Instead of asking the model to reinvent the character for every shot, I used multiple reference images to establish:

- character identity
- costume and silhouette
- environment
- composition
- start/end performance states
- shot continuity

Prompts explicitly assign roles to the references using H3's `<Picture>` system.

For example, a performance shot can define one image as the neutral opening state and another as the intended final expression, while instructing H3 to preserve the character, lighting, costume, framing, and environment.

The resulting generation is therefore treated less like:

> "Generate a character doing something."

and more like:

> "Preserve this character and this shot. Change only this performance."

That distinction became one of the most useful parts of the experiment.

## Example: Controlled Performance

One workflow included in this repository tests a deliberately small animation:

**neutral expression → restrained smirk**

The prompt locks:

- facial identity
- hair
- costume
- head position
- background
- lighting
- camera position

while allowing only a minimal change in the mouth and eyes.

This kind of constrained generation was useful for avoiding unnecessary AI motion and keeping Quibble's performance intentional.

## ComfyUI / MiniMax H3

The included workflow uses:

- **MiniMax H3 Reference-to-Video**
- multiple image references
- MiniMax H3 video VAE
- MiniMax H3 audio VAE
- Qwen3-VL MiniMax text encoder
- `res_multistep` sampler
- 24 fps output
- reference-driven prompt conditioning

The workflow JSON is included in this repository.

## Files

`Quibble.json`  
ComfyUI / MiniMax H3 reference-to-video workflow used during production.

## Why Quibble?

AI video is already very capable at producing individual images and shots.

The more interesting problem for me is what happens **between those shots**:

Can a character persist?

Can a performance remain restrained?

Can composition and visual language survive from shot to shot?

Can generative video become part of an actual directing workflow rather than simply producing isolated clips?

Quibble is my ongoing experiment around those questions.

## Tools

**ComfyUI**  
**MiniMax H3**  
AI-assisted image development  
Traditional editing and sound/post-production

## Status

**Experimental / Work in Progress**

Episode 01 is the first proof of concept. The workflow and character system will continue to evolve as I test longer scenes, stronger continuity, dialogue, performance, and multi-shot storytelling.

---

**Created and directed by Mohannad Khamra**

3D / AI / Motion Design / Generative Video


 https://mkhamra.myportfolio.com/quibble
