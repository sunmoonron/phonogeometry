# phonogeometry
Map graphemes to phonemes (via dictionary IPA), embed each phoneme as a point in a phonetic feature manifold (bounded, interpretable, 2D here but extensible), and treat a sentence as the resulting polyline — a discrete articulatory kinematic trajectory (AKT [Chartier et al. 2018]) in abstract space rather than physical vocal-tract space.

Many linguistic operations then become computational-geometry queries on a lattice-valued polyline: rhyme = suffix nearest-neighbor, alliteration = prefix clustering, tongue-twister difficulty = curvature density, sentence compression = Ramer–Douglas–Peucker simplification keeping only articulatorily salient phonemes, phonetic efficiency = straight-line / path length. The mapping is a bijection on phonemes (lossless), so this sits alongside existing IPA pipelines rather than replacing them.

# To-do (missing items)
- suprasegmental features no stress, tone, duration, intonation
- the 2D projection is lossy vs. the 7+ dim real feature space
- feature weighting is uniform but human perception isn't (Weber's law, phonotactic priors)
- G2P fallback is a toy
- coordinates are English-biased (no clicks, ejectives, retroflex series)
- we don't handle coarticulation, which AKT research shows is huge
- dictionaryapi.dev sometimes fails CORS or returns no IPA — the app falls back to a local mini-dictionary then a last-ditch letter-based approximation
- no empirical benchmark against PWESuite, TwistList, or CMU-dict rhyme gold.

