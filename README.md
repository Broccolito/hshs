# hshs skill

**Beauty comes first. Retouching follows.**

hshs (绘事后素) is a Codex plugin for quiet, natural portrait editing. In this plugin's interpretation, the person and the original photograph already carry the beauty, and edditing offers a finishing touch; it does not take the credit.

## What it does

- Light cleanup of pimples, shaving residuals, patchy tone and temple texture while retaining pores.

- Requested small hairline adjustments and fuller hair near the temples.

- Requested gentle definition of the jaw, lower abdomen and overall silhouette.

- Tooth cleanup that removes unwanted spots or debris while preserving natural enamel color, spacing and alignment—no artificial whitening or veneers.
- Natural lips and relaxed mouth closure; careful, slight eye and facial symmetry adjustments that preserve expression and perspective.

- Optional restrained cinematic lighting and removal of specifically named background objects.

- Non-destructive image conversion and versioned exports.

A simple invocation applies very light skin cleanup. Hairline, jaw, body and symmetry changes require a request, or an explicit request for the full treatment. There is no beauty score or numerical strength scale. Say “lighter,” “only the chin,” or “a little more definition.”

## Requirements

Use a Codex environment with image viewing and image editing tools enabled. This plugin packages editorial instructions; it does not bundle a model, grant image-generation access, or guarantee availability on every account. The built-in tool does not require this plugin to store an API key. Image processing follows the host tool's data handling and usage limits; it is not guaranteed to run entirely on your device.

## Install this plugin

Unzip the shared folder. In Codex, provide the folder and ask:

> Use plugin-creator to register this existing hshs plugin in my personal marketplace without replacing other entries, then install it. The plugin folder is [insert its full path].

For a manual installation:

1. Copy the complete `hshs` folder, including its hidden `.codex-plugin` directory, to `~/plugins/hshs` (on Windows, use the equivalent folder beneath your user profile).

2. Add the following entry to the `plugins` array in `~/.agents/plugins/marketplace.json`. Preserve all existing entries and the existing marketplace name.

```json
{
  "name": "hshs",
  "source": { "source": "local", "path": "./plugins/hshs" },
  "policy": { "installation": "AVAILABLE", "authentication": "ON_INSTALL" },
  "category": "Productivity"
}
```

If that file does not exist, create it with this complete catalog:

```json
{
  "name": "personal",
  "interface": { "displayName": "Personal" },
  "plugins": [{
    "name": "hshs",
    "source": { "source": "local", "path": "./plugins/hshs" },
    "policy": { "installation": "AVAILABLE", "authentication": "ON_INSTALL" },
    "category": "Productivity"
  }]
}
```

3. Install from the local Plugins directory in the app, or use `codex plugin add hshs@personal` on a CLI version that supports it. Substitute the actual catalog name if it is not `personal`.

4. Start a new chat so the installed skill is available. Restart the app if the local catalog has not appeared.

Do not overwrite an existing hshs installation without reviewing it. This package does not register itself in a public directory. Anyone receiving the folder can use the installation procedure, subject to their Codex capabilities and workspace policies.

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
├── .codex-plugin/plugin.json
├── skills/hshs/SKILL.md
├── skills/hshs/agents/openai.yaml
└── README.md
```

No portraits, account credentials, external servers, hooks or background services are bundled. You may share this instruction package; sharing it does not share the photos used to develop it.

## Development and verification

The plugin manifest and skill can be validated with the plugin-creator and skill-creator validators bundled with Codex. Structural validation does not prove visual quality; inspect actual outputs. Useful smoke checks include conversion-only (no retouch), skin-only (no reshaping), requested symmetry (retain head perspective), and a follow-up hair edit (retain earlier accepted changes).

When editing an installed copy's source, follow plugin-creator's cachebuster and reinstall workflow, then start a new chat. Keep the distributable folder free of personal photographs.

Installation and invocation references: [OpenAI plugin packaging](https://developers.openai.com/plugins/build/plugins) and [Codex skills](https://developers.openai.com/codex/skills). Local CLI installation syntax was also checked with `codex plugin add --help` during authoring.
