---
title: "Ray Tracing/Physics"
date: 2018-11-12T20:55:46-06:00
description: "Notes about light, physics and ray tracing"
type: "notes"
draft: false
---
[Mirrors](http://scienceline.ucsb.edu/getkey.php?key=3903
)
# Why do mirrors reflect:
## Nature of the metal
* Electrons are loosely attached to metals and are able to
* For visible light (low frequency), the electrons can match the speed
and reflect the light. For UV, it is too high so it doesn't reflect

* Different metals reflect different wavelengths
The highest frequency light reflected is called _plasma frequency_
* This differs between metals, steel is high

## "Mirrors reflect mainly bc they are electrically conductive"
* When it hits a mirror the metal cancels out the electric field parallel to the mirror, so it changes directions and reflects away.

# Ray Tracing Notes

https://cs.stanford.edu/people/eroberts/courses/soco/projects/1997-98/ray-tracing/implementation.html

Pseudocode:
```
for(each pixel (sample) on the viewing area)
{
   for(each primitive in the world model)
   {
      if(ray-pixel intersection)
      {
          select the frontmost intersection;
          recursively trace the relection and refraction rays;
          calculate color;
      }
   }
}
```
