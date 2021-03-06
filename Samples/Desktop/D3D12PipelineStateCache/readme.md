---
page_type: sample
languages:
- cpp
products:
- windows-api-win32
name: Direct3D 12 pipeline state cache sample
urlFragment: d3d12-pipeline-state-cache-sample-win32
description: This sample demonstrates the use of binary occlusion queries and predication in Direct3D 12.
extendedZipContent:
- path: LICENSE
  target: LICENSE
---

# Direct3D 12 pipeline state cache sample
This sample demonstrates the use of Direct3D 12 pipeline state object (PSO) libraries. An app can use PSO libraries to cache compiled PSOs to disk and avoid costly shader compilation during subsequent runs. Using PSO libaries can accelerate app load times and reduce rendering glitches caused by driver shader compilation. 
This sample also demonstrates the use of an "uber shader" which is a shader that can perform a variety of effects by taking advantage of dynamic branching on the GPU. The motivation behind an uber shader is to alleviate frame rate glitches caused by an app compiling a PSO it hasn't encountered before. When this happens the app can simply configure the uber shader PSO (which it can compile up front at load time) with the desired effect and use that until the faster and more specialized PSO is done compiling. This results in slightly lower GPU performance for a while but produces more consistent and smoother results.

### Optional features
This sample has been updated to build against the Windows 10 Anniversary Update SDK. In this SDK a new revision of Root Signatures is available for Direct3D 12 apps to use. Root Signature 1.1 allows for apps to declare when descriptors in a descriptor heap won't change or the data descriptors point to won't change.  This allows the option for drivers to make optimizations that might be possible knowing that something (like a descriptor or the memory it points to) is static for some period of time.