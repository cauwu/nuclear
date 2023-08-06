# Nuclear
Nuclear power themed video game prototype made with Godot.
The prototype is an experiment in producing assets, textures, scripting and gameplay for a real-time rendering engine, in a time and resource-effective way.

## Directory structure
When exported from Blender as `.glb` files, which contain both model, texture, and animation data set up in Blender, assets first go into the `/import` file, with a descriptive and unique name, using underscores for spaces.
Godot works by having a `main` scene that the game runs. Everything in that scene is comprised of other scenes. The `main` scene imports scenes from `/levels`, which contains lighting and environmental information, which in sequence imports level geometry and collision information from `/assets/entities/maps`, which imports models from `/assets/entities/objects`. 
Scripting can be added to any scene where necesary, and scripts are stored in `/assets/scripts`.

## Including assets into the project
`.glb` files need to be organised into scenes to be included in Godot projects. `.glb` files are in `/import`, and Godot automatically unpacks `.material` files from them into `/import`. They are fine living there for now.
Click on the `.glb` file you need a mesh from, click `New Inherited`, and in the `ObjectGeometry` setting of each mesh, to the right of the interface, check `Bake Lightmap` to `On`. This will allow `ProbeGI` to set up shadow information for each mesh later.
Give the asset a descriptive name at the top of the object tree (no spaces and without underscores, to differenciate it from `.glb` files in case of confusion) and save the scene to `/assets/entities/objects`. The asset can then be included elsewhere in the project.

2023 Ceres Miller, Maya McCluskey
