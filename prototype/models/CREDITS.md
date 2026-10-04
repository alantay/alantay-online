# Model credits

| File | Model | Author | License | Source |
|---|---|---|---|---|
| adventurer.glb | Adventurer | Quaternius | CC0 | https://poly.pizza/m/5EGWBMpuXq |
| shiba.glb | Shiba Inu | Quaternius | CC0 | https://poly.pizza/m/y4wdQpg767 |
| bicycle.glb | Bicycle | Poly by Google | CC-BY 3.0 | https://poly.pizza/m/b6USSQA731J |
| camping.glb | Camping Asset Collection | Alex Safayan | CC-BY | https://poly.pizza/m/3nj59_uuCbM |

CC-BY models need visible attribution on the site (footer credits line).

adventurer, shiba and camping are optimised with gltf-transform: unused animations and meshes pruned (adventurer: no clips, no backpack; shiba: `Idle` only; camping: only the node indices `index.html` uses, kept in place), then meshopt-compressed. bicycle is the original file, since `mountRider` reads its raw vertex positions.
