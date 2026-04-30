+++
title = "MLS-MPM in Godot"
date = "2026-04-15"
portfolioCover = "img/covers/mls-mpm_cover.png"
portfolioIcons=["icon/godotengine.svg"]
weight = 2
+++

{{< link-new-tab url="https://github.com/Miotismon/mls-mpm-godot" text="Github Link" >}}

For my Bachelor's thesis I implemented the {{< link-new-tab url="https://yuanming.taichi.graphics/publication/2018-mlsmpm" text="Moving Least Squares Material Point Method (MLS-MPM)" >}} in Godot 4. This was first done just using single-threaded C# code, which I then further parallelized using C# multithreading and finally by running it all using Compute Shaders for maximum performance. This way I was able to run a 150k particle fluid sim with real-time performance. I'm sure I could've optimized it further but I had limited time for this project.

![Fluidsim Depthmap](mls-mpm_sphere_vis.png)

Additionally, to render the results of the simulation, I implemented {{< link-new-tab url="https://developer.download.nvidia.com/presentations/2010/gdc/Direct3D_Effects.pdf" text="Screen Space Fluid Rendering (SSFR)" >}} using the Godot Compositor, which let's you insert any additional logic into the rendering pipeline at various stages.

At the end, to show of that you can interact with the fluid in real-time, I added a sphere mesh and send it's position and radius to the simulation to act as a collider.

If you want to play around with it yourself, go to the {{< link-new-tab url="https://github.com/Miotismon/mls-mpm-godot/releases" text="Github Repo -> Releases" >}} and download the executable there, it should run on any decent computer.

![Fluidsim SSFR](mls-mpm_ssfr_vis.png)
![Fluidsim After I dragged the sphere through the fluid](mls-mpm_ssfr_turbulant.png)