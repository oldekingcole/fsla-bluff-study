# Bluff Face - Vegetation Quantification

**Site:** ~bluff face above Lake Austin, Austin TX (30.353 N, 97.806 W)  
**Purpose:** vegetation quantification on the bluff face for rockfall-scaling contractor scope & Critical Environmental Feature (CEF) review  
**Capture:** 2026-07-29, DJI Mavic 3E (no RTK) - Smart Oblique crest grid (70 m AGL) + over-water facade tiers  
**Facade ortho:** 38,271x5,199 px @ 2 cm/px (elevation view, local metric)  

---

## Headline numbers

Vegetation is classified as everything on the face that is **not** exposed pale limestone (rock detected in HSV; vegetation = complement - validated to capture shaded canopy that a green-index threshold misses). Two area bases are reported per the brief:

- **Projected** - vegetation footprint on the vertical face plane (well-defined, reproducible; the standard face-coverage metric).
- **True-surface** - actual 3D area of the vegetated face surface (mesh triangles), which is larger because the face + canopy have real relief.

### 604 m face section (recommended reporting extent)

| Zone | Cover | Veg projected (m2 / ft2) | Veg true-surface (m2 / ft2) |
|---|--:|--:|--:|
| crest overhang | 82.6% | 9,452 / 101,740 | 22,560 / 242,837 |
| open face | 76.0% | 22,824 / 245,675 | 54,581 / 587,501 |
| toe canopy | 91.5% | 3,242 / 34,897 | 8,948 / 96,318 |
| TOTAL | 79.2% | 35,518 / 382,312 | 86,089 / 926,656 |

**Face-rooted woody vegetation (open-face zone, the key figure): ~ 22,824 m2 projected (245,675 ft2).**

### Full surveyed corridor (~765 m)

| Zone | Cover | Veg projected (m2 / ft2) | Veg true-surface (m2 / ft2) |
|---|--:|--:|--:|
| crest overhang | 81.7% | 9,635 / 103,710 | 22,706 / 244,406 |
| open face | 75.0% | 24,316 / 261,735 | 56,438 / 607,492 |
| toe canopy | 90.1% | 3,322 / 35,758 | 9,008 / 96,965 |
| TOTAL | 78.1% | 37,273 / 401,203 | 88,152 / 948,862 |

**Face-rooted woody vegetation (open-face zone, the key figure): ~ 24,316 m2 projected (261,735 ft2).**

---

## Method

1. **Intake/QC** - 1,633 photos (130 facade + 1,503 crest); mission split verified by gimbal pitch; coverage + geotags checked; 46 soft crest frames pruned. QC caveat: ~92% of frames were shot below 1/1000 s (evening light) - usable, but effective sharpness is slightly below the 1.9 cm GSD ideal.
2. **Reconstruction** - Agisoft Metashape (photogrammetry): 1,559/1,587 photos aligned (98.2%, one block), 220 M-point dense cloud, textured mesh. Georeferenced from photo GPS (no RTK) - **2.0 m RMS fit**, so absolute position is ~2 m but relative geometry/scale is solid (~0.3%).
3. **Facade ortho** - RGB cloud orthographically projected (front-most surface) onto a vertical plane fit to the corridor strike, at 2 cm/px.
4. **Classification** - rock = pale limestone (HSV bright+desaturated); vegetation = complement, morphologically cleaned. Zones (crest overhang / open face / toe canopy) and the 604 m crop placed by the reviewer on the interactive page.
5. **Areas** - projected = veg pixels x cell area; true-surface = sum of front-face mesh-triangle 3D areas under the veg mask (5 M-face mesh).

## Caveats

- **No RTK:** ~2 m absolute position error (relative accuracy fine for this deliverable).
- **Evening-light shutter:** most frames < 1/1000 s → mild softness; did not prevent a clean 98.2% alignment.
- **True-surface is scale-dependent:** a wooded face's 3D area grows with measurement resolution; the value here is from the 5 M-face mesh (~10 cm). Projected area is the stable metric.
- **Woody vs herbaceous** (~97% woody by patch size) is an automated estimate; the dense woody canopy dominates, but a human pass is advised if the herbaceous split matters.
- **Extent:** the reconstruction covers ~765 m of flown corridor; the 604 m crop is the reviewer-selected face section.

*Generated from the reproducible pipeline in `scripts/` (see README). Capture date 2026-07-29.*
