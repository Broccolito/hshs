# hshs skill

**Beauty comes first. Retouching follows.**

[Explore the before-and-after demonstrations →](https://broccolito.github.io/hshs/)

The minimal landing page and fictional East Asian portrait examples live in [`landing/`](landing/).

hshs (绘事后素) is a Codex plugin for quiet, natural portrait editing. In this plugin's interpretation, the person and the original photograph already carry the beauty, and edditing offers a finishing touch; it does not take the credit.

## What it does

- Light cleanup of pimples, shaving residuals, patchy tone and temple texture while retaining pores.

- Requested gentle softening of crow’s feet (鱼尾纹), nasolabial folds (法令纹) and fine lines, retaining pronounced folds, expression and natural age.
- Requested small hairline adjustments and fuller hair near the temples.

- Requested gentle definition of the jaw, lower abdomen and overall silhouette.

- Tooth cleanup that removes unwanted spots or debris while preserving natural enamel color, spacing and alignment—no artificial whitening or veneers.
- Natural lips and relaxed mouth closure; careful, slight eye and facial symmetry adjustments that preserve expression and perspective.

- Optional restrained cinematic lighting and removal of specifically named background objects.

- Non-destructive image conversion and versioned exports.

A simple invocation applies very light skin cleanup. Hairline, jaw, body and symmetry changes require a request, or an explicit request for the full treatment. There is no beauty score or numerical strength scale. Say “lighter,” “only the chin,” or “a little more definition.”

## Requirements

Use a Codex environment with image viewing and image editing tools enabled. This plugin packages editorial instructions; it does not bundle a model, grant image-generation access, or guarantee availability on every account. The built-in tool does not require this plugin to store an API key. Image processing follows the host tool's data handling and usage limits; it is not guaranteed to run entirely on your device.

## Install from GitHub — ask Codex

Copy and paste this into Codex:

> Install the hshs plugin from https://github.com/Broccolito/hshs. Read its README, add its GitHub marketplace, install hshs@hshs-marketplace, and verify that the plugin is installed and its hshs skill is available. Preserve my other plugins and settings. Tell me if I need to open a new chat.

The repository is public. No repository invitation or GitHub token is required to read it. Installation still requires a Codex version with plugin support and permission to install plugins. Image editing additionally requires image tools in your Codex session; installing this instruction package does not grant those tools.

### Exact installation commands

Codex can run these for you, or you can run them in a terminal:

```sh
codex plugin marketplace add https://github.com/Broccolito/hshs.git
codex plugin add hshs@hshs-marketplace
codex plugin list
```

The catalog is `.agents/plugins/marketplace.json`; it points to `plugins/hshs`. No manual copying or configuration-file editing is needed. If the marketplace is already registered, refresh it with `codex plugin marketplace upgrade hshs-marketplace` before reinstalling the plugin.

After installation, open a **new Codex chat**, attach a portrait, and invoke **$hshs** (or select **hshs:hshs** from the skill picker). In the CLI, `/skills` opens that picker. If the plugin is absent, restart Codex and check `codex plugin list` for `hshs@hshs-marketplace`. The package does not guarantee a bare `/hshs` command on every client.

If your environment lacks the `codex` command, use a Codex desktop installation with plugin support and ask Codex to install from the URL above. If plugin installation is unavailable or blocked by workspace policy, report that limitation instead of claiming installation succeeded.

### Verify setup

Ask in a new chat:

> Use $hshs. Before editing, confirm you can load its instructions and access an image editing tool. Summarize its rules for natural teeth, background text, lighting, and preserving the original. Do not generate an image yet.

Then attach a photo and ask for a light edit. The original should remain available, and the response should show a separate output and summarize the checks actually performed. A successful plugin installation alone does not prove image-tool access or visual editing quality.

### Update or remove

```sh
codex plugin marketplace upgrade hshs-marketplace
codex plugin add hshs@hshs-marketplace
```

Start a new chat after updates. To uninstall, run `codex plugin remove hshs@hshs-marketplace`.

### Install from a downloaded copy

Unzip or clone the repository, then run `codex plugin marketplace add /absolute/path/to/hshs` followed by `codex plugin add hshs@hshs-marketplace`. The path must be the repository root containing `.agents/plugins/marketplace.json`, not the nested plugin folder. This uses the same catalog name; do not register both local and GitHub sources with that name at once.

## Invoke it

In Codex CLI or IDE, use the documented slash entry point **`/skills`**, select **hshs**, and attach the image. Or invoke it directly with **`$hshs`**. A plugin skill may be displayed under its namespace as `hshs:hshs`; select that entry if shown. In a UI with a plugin/skill mention picker, search for hshs there.

A universal bare `/hshs` alias is not guaranteed by Codex's documented skill interface. The plugin provides one reusable hshs workflow without relying on an unsupported custom-command mechanism.

Examples after selecting the skill:

> Lightly clean up this portrait. Keep the skin texture and everything else natural.

> Slightly lower the hairline, thicken the temple hair, define the lower jaw a little, and tighten the lower abdomen. Keep my proportions and the original photo's character.

> Make the lips look relaxed and naturally closed, and very slightly balance the eyes. Preserve the head angle, gaze and natural asymmetry.

> Use the full hshs treatment with very restrained cinematic lighting. Keep the result recognizable and photographic.

> Only convert this HEIC to JPEG. No retouching.

## How it protects the photograph

The workflow inspects the source, edits only the requested areas, compares the result, and retains the original. It asks for visible pores, individual hair strands, plausible anatomy and natural clothing folds. Follow-up edits apply the new change instead of repeatedly processing every feature.

Generative editing can change unintended details or output a smaller image. The workflow checks for these issues and reports material limitations; it cannot guarantee unchanged pixels, full source resolution, perfect identity preservation or undetectable editing. It does not remove provenance metadata to conceal edits.

## Quality checks in the updated workflow

Short checklists cover the edit brief, face and body, background text, lighting, and before/after comparison. Each revision is checked against both the untouched original and the last accepted version.

- **Teeth and eyes:** Keep natural enamel shade and tooth spacing. Preserve eye anatomy, gaze, perspective and characteristic asymmetry; repair introduced eye artifacts.
- **Text:** Preserve signs, logos and lettering. Scrambled or invented characters fail review and trigger a targeted retry. Exclude text from editing; do not delete the text or its sign.
- **Light:** Keep the person integrated with the scene. Check light direction, color, exposure and shadows, and reject halos or a separate studio-lit subject effect.
- **Drift:** Compare untouched regions and overall tone, texture and sharpness. Minor encoding differences are acceptable; broad unintended changes are not. Use aligned difference views when available, without promising unchanged pixels.

Correction passes are bounded to avoid repeated degradation. If preservation still fails, the workflow reports the limitation rather than declaring the image finished. Checks describe what was actually inspected; they do not guarantee tool behavior.

## Package contents

```text
hshs/
├── .agents/plugins/marketplace.json
├── plugins/hshs/.codex-plugin/plugin.json
├── plugins/hshs/skills/hshs/SKILL.md
├── plugins/hshs/skills/hshs/agents/openai.yaml
└── README.md
```

No portraits, account credentials, external servers, hooks or background services are bundled. You may share this instruction package; sharing it does not share the photos used to develop it.

## Development and verification

On September 28, 2026, installation from this public GitHub marketplace succeeded with Codex CLI 0.157.0. A fresh Codex session loaded the installed hshs skill, correctly summarized the teeth, symmetry, text, lighting and drift rules, and confirmed an image editing tool was available. Plugin and skill structural validators passed. This was an installation and instruction-loading smoke test; it did not generate a new portrait or certify visual output quality.

The plugin manifest and skill can be validated with the plugin-creator and skill-creator validators bundled with Codex. Structural validation does not prove visual quality; inspect actual outputs. Useful smoke checks include conversion-only (no retouch), skin-only (no reshaping), requested symmetry (retain head perspective), and a follow-up hair edit (retain earlier accepted changes).

When editing an installed copy's source, follow plugin-creator's cachebuster and reinstall workflow, then start a new chat. Keep the distributable folder free of personal photographs.

Installation and invocation references: [OpenAI plugin packaging](https://developers.openai.com/plugins/build/plugins) and [Codex skills](https://developers.openai.com/codex/skills). Local CLI installation syntax was also checked with `codex plugin add --help` during authoring.
