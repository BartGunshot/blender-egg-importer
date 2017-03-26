This is an importer for Blender that can import .egg files.  It is designed to
be interoperable with YABEE and other Blender to Panda3D exporters, and aims
to preserve the hierarchical structure of the models.

In combination with the improved version of bam2egg available in development
builds of Panda3D, this also provides a reliable path to import .bam files
that are generated by egg2bam.

## Installation

This is a Blender addon that does not require a Panda3D installation.

Clone this repository in your GitHub addons directory, or download as a .zip
file and use "Install from File" in the Blender User Preferences window.

## Animations

Skeletal animations are supported, experimentally.  A model needs to be loaded
with all of its animations in the same import run.  If the animation exists in
a separate egg file, this means that the model file and all of its animation
files will need to be selected in the file selector dialog.

Animations are not automatically bound to their corresponding armature.  To
see an imported animation, you will need to select the armature, go to the
Dope Sheet window, bring up the Action Editor, and select the appropriate
action.

## Features

Most features supported by bam2egg are implemented.  In particular, however,
animation support is not yet finished.  Many other features still need to be
tested.

Supported features:
- .egg.pz and .egg.gz files
- Basic geometry, incl. tristrips and trifans
- All transform types
- Materials
- Textures
- Tags (as game properties)
- Collide and ObjectType (as game properties)
- Collision masks (as game properties)
- Coordinate system conversion
- Custom normals
- Multiple UV coordinate sets
- Armatures, skinning
- Bone animations

Yet to do:
- Improve performance of parser
- Lines, patches
- NURBS surfaces and curves
- Morph targets
- Read default pose
- Vertex colors
- Level of detail
- Don't import normals as custom normals if not necessary

## Limitations

Panda3D does not have a concept of "bone length"; the importer does some
clever tricks to guess what the original bone length might have been, but some
bones may look wrong.  This should not negatively affect skinning, however.

Shear animations are not supported at present.  If you have a file that
contains shear animations, please send it to me.

If you find any bugs, please open a bug report on the issue tracker, and
include the egg file that loaded incorrectly.
