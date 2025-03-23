# BLITTER_signed_distance_field

## Contributors

- Roberto De Ioris, Blitter S.r.l.

## Status

Proposal

## Dependencies

Written against the glTF 2.0 spec.

## Overview

Lot of rendering engines make use of simplified representation of meshes to speed up potentially expensive (for real time) computations like
lighting, shadowing, global illumination or ambient occlusion.

One of the most common techniques is to use signed distance fields (https://en.wikipedia.org/wiki/Signed_distance_function) representation of meshes.

This extension introduces the ability to include those voxel-like simplified representations in each primitive using volumetric/3d textures.

Given that the PNG and JPEG formats are not suitable for single channel 3d textures, it is recommended to use extensions like KHR_texture_basisu or MSFT_texture_dds to store
the distance fields data.

The usage of formats like ktx2 and dds will allow easy support for mip maps (to have various levels of simplified representations)

### Minimal Example:

```json
"meshes": [
    {
        "primitives": [
            {
                "attributes": {
                    "POSITION": 0,
                    "NORMAL": 1,
                },
                "indices": 2,
                "material": 0,
                "mode": 4,
                "extensions": {
                    "BLITTER_signed_distance_field": {
                        "texture": 17
                    }
                }
            }
        ]
    }
]
```

## glTF Schema Updates

This extension consists of a new `"BLITTER_signed_distance_field"` string which can be added to the glTF's `"extensionsUsed"` array and because it is optional, it does not need to be added to the `"extensionsRequired"` array.


### JSON Schema

## Known Implementations

## Resources:
