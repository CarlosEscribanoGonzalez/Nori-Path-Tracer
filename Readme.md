## Overview
CPU path tracer developed in C++ on top of the Nori educational rendering framework, implementing and studying Monte Carlo techniques for physically based rendering and global illumination.
The project was developed incrementally, from sampling and direct lighting to a full path tracer with next-event estimation, multiple importance sampling and microfacet materials.

## Disclaimer
The source code is not included in this repository because the project was developed on top of the Nori framework and is subject to its licensing and distribution restrictions.
This repository therefore contains the project documentation, rendered results and visual comparisons of the implemented techniques, while the implementation itself remains private.

## Sampling
* Tent distribution sampling
* Uniform hemisphere sampling
* Cosine-weighted sampling using both Malley's method and inverse transform sampling
* Statistical validation of sampling distributions using null hypothesis tests
* Area-weighted sampling of mesh triangles

## Direct Lighting
* Material sampling
* Light sampling with visibility testing through shadow rays
* Conversion from area-based PDFs to solid-angle PDFs
* Luminance and area-weighted emitter selection to reduce estimator variance

## Multiple Importance Sampling
* Multiple Importance Sampling (MIS) combining material and light sampling
* Balance, power and maximum heuristics
* Comparison of sampling strategies and their effect on estimator variance
* Improved convergence for scenes containing both diffuse and specular materials

## Path Tracing
* Recursive path tracer for global illumination
* Indirect illumination through multiple light bounces
* Next Event Estimation (NEE) for direct lighting at every bounce
* Fixed and throughput-based adaptive Russian roulette
* Support for perfect mirror materials

## Microfacet BRDF
* Cook–Torrance microfacet BRDF
* Combined diffuse and specular response
* Importance sampling of diffuse and specular lobes

## Additional Techniques

**Ambient Occlusion**
* Explicit ambient occlusion through visibility queries
* Comparison between manually applied AO and the occlusion effects naturally produced by global illumination

## Tone Mapping
* ACES-inspired tone mapping
* Luminance-based processing
* Gamma correction

## Experiments
The project includes experiments comparing:
* Convergence at different spp counts
* Material sampling vs. light sampling
* Uniform vs. luminance and area-weighted emitter sampling
* Different MIS heuristics
* Convergence times with different Russian roulette approaches
* Direct lighting vs. direct + indirect illumination
* Different bounce limits
* Explicit vs. naturally occurring ambient occlusion
* NEE with and without MIS
* Effects of MIS on a Microfacet-Based BRDF

## Technologies
* C++
* Nori