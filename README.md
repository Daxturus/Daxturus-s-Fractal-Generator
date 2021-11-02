# Daxturus's Fractal Generator
Edit: This is a classic example of an attractor, and I didn't even realize until practically yesterday. I pushed out an update a couple days ago that literally shows a representation of the differential equation of each point at each spot, and even then I failed to realize. So, because this is a kind of an attractor, this actually may have been done before, but I'm still doing research to find out if this is original or not. Either way, I do think the tool is very interesting, and I am gaining a sudden interest and appreciation for attractors now.

A JavaScript tool that automatically generates a fractal when opened using a custom fractal generator I wrote. I'm not sure if anyone has used this method of fractal generation yet; I may very well have created an entirely new kind of fractal set. Inspired by 3Blue1Brown's "Newton fractal" video, this fractal generator works by first generating a list of "attractor" points with randomly-generated colors (which I have nicknamed POIs/points of interest), then repeatedly moving points located at each pixel on the canvas at an angle relative to the center as well as the closest attractor point. After a predefined number of steps of this process, pixels are colored based on the color of the attractor point they are closest to. This process is stable and mostly continuous; points will tend to certain attractor points and will continue getting closer as time goes on.

This tool runs in O(N) time (4x pixels generated = 4x generation time), and this method of generation is easily parallelizeable (though it currently is not run in parallel in this Javascript implementation.) I had created a parallelized C# version with a decimal library, but it was not as good, harder to use, and maybe only slightly faster.

At the moment, it's a bit buggy. It often gives undefined values as outputs, causing a noticeable slowdown in generation time, and loss of colored pixels in certain regions (Fractal boundaries remain, in the grand majority of cases, completely unaffected). But, on the bright side, it works, and I'm finally free from this horrible curse of nonstop working on this project. I can go do my homework now.

Controls:
WASD: Move up and down.
+/-: Zoom in or out.
M/N: Increase or decrease the simulation steps per pixel accordingly.
I/K: Increase or decrease the canvas size accordingly.
O: Download fractal data.
P: Capture image of canvas.
L: Load generated fractal data.
R: Switch between Colored and Angle-Colored view.
Z: In Angle View, switch between coloring points based on distance from start and coloring points based on angle from start.
C/V: In Angle View, hold down or rapidly click to adjust coloring.
X: Currently not intended to be a control; but is still useable. Will change coloring slightly.
