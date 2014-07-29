# GLPlot

### Installation notes:
You still need to install packages manually, as the packages are not in metadata yet.
Unregistered:

Pkg.clone("https://github.com/JuliaGL/ModernGL.jl.git")

Pkg.clone("https://github.com/SimonDanisch/GLWindow.jl.git")

Pkg.clone("https://github.com/SimonDanisch/GLAbstraction.jl.git")

Pkg.clone("https://github.com/JuliaGL/GLPlot.jl.git")

The rest should be fetched by REQUIRE


### Some updates:
First of all, a few things actually got less comfortable.

That's because I stopped acting like I have a scene Graph and now fully expose the render loop. I think this offers greater flexibility for early adopters.

That means instead of display I rather expose the function toopengl, which I intend to use to build up the scene graph later on.

Also I'm not fully happy with the API, but that is to be expected, as I haven't figured out the scene graph and its interaction with React yet.

BUT, I have most of the pieces together now, to do the basic render operations, which you would expect from a 3D plotting package and most of the render attributes can be be time changing signals, which enables nice animation capabilities.

You can find examples with a few comments in GLPlot/examples

By the way, all shaders are interactive now by default.

That means you can just run the example, open a shader in a text editor, edit something, save -> et voilà =)

For example if you run example/surface.jl, GLPlot/src/shader/phongblinn.frag might be interesting.

Or volume.jl and GLPlot/src/shader/iso.frag.

 

Here are some screen-shots/videos ( Gamma values don't come out correctly when saving, so they all look a little pale):

Going through some iso-values:

https://www.youtube.com/watch?v=aDzCABwxdJI&feature=youtu.be

Tiny cubes animated with different attributes:

https://www.youtube.com/watch?v=uz-HV1AAgcI&feature=youtu.be

2D geometry projected on z-value grid:

![Iso-surface](/example/2dgeom.png?raw=true "sin(x)+sin(y)+sin(z)")

Same without seams (Surface Plot):

![Iso-surface](/example/surf.png?raw=true "sin(x)+sin(y)+sin(z)")

Iso surface:

![Iso-surface](/example/iso.png?raw=true "sin(x)+sin(y)+sin(z)")

Best,

Simon
