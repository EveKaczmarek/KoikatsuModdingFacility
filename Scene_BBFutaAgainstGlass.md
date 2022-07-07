# Description of scene composition 

Please, refer to the Twitter post for for a reference image.



* The effect of skin pressed on glass was done by clipping some parts of body outside the window frame.

* Another window frame is masking this clipping

* Breast physics is controlled by the game, "Against the Wall" pose creates a virtual collider that automatically set the chest to a collided state.

* Penis physics is controlled manually by the collider that is set to inversed state. Character replacement will require you to edit collider settings or delete it entirely, otherwise all physical objects on scene will be dragged in some sort of black hole.

* Penis position is controlled manually.

* Ejaculation props looks different. I've manually added motion blur in Krita so I'll provide a .KRA file for reference. (link)

* Hard transitions between clipped and non-clipped parts was softened manually in Krita, please refer to a .KRA file.

* Following filters of a PostProcessingEffects plugin has been applied:
1. Ambient Occlusion

        Sample Count: Ultra

        Downsampling: 1.00

        Intensity: 6.02

        Radius: 0.18

        Distance: 0.10

        Bias: 0.25

        Lighting Contribution: 1.00

        Color: 0, 0, 0 

        Blur Type: High Quality Bilateral

        Blur Passes: 2.00

        Blur Threshold: 10.00

        Max Distance: 150.00

        Falloff: 50.00

2. Anti-aliasing 

        AA Mode: SMAA

        Quality: High

3. Bloom

        Intensity: 4.03

        Threshold: 1.10

        Soft Knee: 0.50

        Clamp: 65472.00

        Diffusion: 10.00

        Anamorphic Ratio: 0.00

        Color: 255, 137, 0

4. Chromatic Aberration 

        Intensity: 0.04

5. Color Grading

        Mode: Low Definition Range

        Tonemapping: ACES

        Temperature: 0.00

        Tint: 10.97

        Post Exposure: 0.00

        Color: 255, 255, 255

        Hue Shift: 0.00

        Saturation: 10.60

        Contrast: 0.00

6. Depth of Field

        Focus Distance: 50.00 (this thing is broken anyways)

        Aperture: 7.40

        Focal Length: 50.00

        Max Blur Size: Very Large

        Auto Focus: Selected Character
