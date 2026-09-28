# hshs replacement woman

## Observed visual QA

- Both images are clean single portraits without visible text, logos, watermarks, characters or UI. The new fictional face is clearly different from the supplied social screenshot.
- The edited result visibly reduces scattered small cheek/chin marks and patchy redness, with more even skin tone. Fine pores remain visible, though cheek texture is slightly smoother.
- Shallow lower-chin creases and small smile-adjacent folds are softened. Characteristic cheek dimples and deeper smile folds remain.
- Eye balance change is subtle; both eyes retain plausible lids, gaze and reflections. No obvious enlargement or mathematical symmetry is apparent.
- Full-frame comparison shows recognizable same identity, smile, head tilt, hair silhouette, top, textured wall and natural light. This is visual preservation, not a claim of pixel identity. Fine hair/clothing rendering has minor generative differences.
- No correction pass was needed. Two image tool calls were used: generation, then edit of generated original.

Tool: built-in image_gen. The social screenshot was inspected for broad composition only and was never passed as an image-generation input. The before image is a newly generated fictional adult; the after image is a genuine edit using before.png as its sole image reference.

## Generation prompt

Use case: photorealistic-natural.
Create an entirely NEW fictional East Asian adult woman, age 33, as a candid cafe portrait. Do not reproduce any person from previous conversation images; create a distinctly new face, with a softly rounded face, gently full cheeks, softly arched eyebrows, a broad friendly closed-mouth smile and warm brown eyes.
Portrait aspect ratio 3:4. Head and upper torso fill frame, cropped just below bust. Long black hair loosely parted near center, simple teal sleeveless top with broad straps, seated at a textured mottled gray cafe plaster wall, a tiny dark chair edge at bottom. Casual relaxed posture, looking at camera, subtle head tilt. Soft natural window daylight from left, realistic warm medium natural complexion. Appealing ordinary candid photograph, not fashion advertising. Already good-looking original, showing several modest small temporary blemishes on cheeks and chin, mildly uneven patchy cheek tone, a little natural eyelid asymmetry, fine smile lines and shallow smile-related chin creases. These are subtle real skin details, never exaggerated flaws. Preserve visible pores and fine facial hair, healthy appearance, true age.
Photorealistic camera rendering, tactile skin texture, understated color and natural shadows. No beauty filter, no airbrushing, no heavy makeup. Absolutely no text, letters, Chinese characters, logos, watermarks, UI, borders, screen elements or collage. One single clean photograph.

## Edit prompt

Use case: identity-preserve. Edit ONLY the provided generated original portrait with restrained hshs natural portrait retouching.
Requested local changes: spot-heal the small temporary blemishes on cheeks and chin; gently even the mild patchy redness and uneven tone of cheeks and chin, without whitening or changing the underlying warm natural complexion. Gently reduce the contrast of shallow smile-related lower chin creases/puckering, retaining chin contour, lower-lip-to-chin fold, natural dimples and believable skin compression. Ease fine smile folds modestly; keep the characteristic deeper smile creases and cheek dimples visibly present. Make a very small local eyelid balance adjustment respecting the head tilt and perspective, preserving eye size, gaze and original eyelid character; never mirror eyes.
Preserve the EXACT same woman's identity, age, round cheeks, facial proportions, broad closed-mouth smile, gaze, pose, head tilt, lip shape/color/texture, natural asymmetry and anatomy. Preserve skin pores and fine facial hair: no blur or painted texture, no skin whitening, no age reduction. Retain individual hair strands, hairline, body contours, teal ribbed top weave and seams, chair and mottled gray wall geometry, light direction, highlights, exposure, color palette, contrast, photographic character, composition and framing. Match source dimensions and aspect ratio. The full frame outside the local face edit should stay visually unchanged.
Avoid waxy skin, excessive smoothing, eye enlargement, altered smile or lips, invented teeth, distorted pupils, duplicated catchlights, changed hair, warped clothing/background or new lighting. There is no visible text; generate no text, letters, characters, logos, watermarks or UI.
