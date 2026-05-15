# dstudio-design-tests

Sandbox de tests visuels pour les agents D-Studio (DESIGNER, OpenDesign).

Chaque test est une page autoportée (`tests/<id>-<topic>/index.html`) avec :
- Composant React inliné (Babel standalone TS+JSX)
- Tailwind via CDN
- Aucune dépendance build, ouvrable telle quelle

## Tests actifs

| # | Test | URL preview | Status |
|---|------|-------------|--------|
| 01 | PricingCard D-Studio premium (3 tiers, gradient borders, AA) | [index.html](./index.html) | DESIGNER · audit slop ABSENT |

## URL preview (GitHub Pages)

https://keiy78120.github.io/dstudio-design-tests/

## Stack runtime

- Composants pulled depuis `/tmp/designer-test-output/*.tsx` (sorties DESIGNER tmux)
- Conversion automatique TSX → HTML standalone via Babel preset `react,typescript`
- Babel standalone transpile en browser, pas de build

## Anti-slop checklist appliquée à chaque test

1. Gradient borders via `mask-composite` (jamais solid)
2. `min-h-svh` mobile (jamais `100vh` / `h-screen`)
3. Contrast AA min 4.5:1 texte, 3:1 large
4. Zero placeholder URL (lorem ipsum, picsum.photos, etc.)
5. Aria labels sur tous CTAs + structure sémantique
6. Features contextuelles produit (jamais génériques "Boost your X")
