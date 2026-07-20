# Endpoint Management & Imaging

## An Initial Problem we Faced

With over 80 desktops and laptops across the lab, manually configuring,
updating, and re-imaging machines one at a time didn't scale. We had to find a way to manage devices across Windows, Linux, and Mac.

## What We Built

- Deployed **ManageEngine Endpoint Central** to manage software, patching, and
  configuration across our 20 Macs which saw the most student use and needed moderation.
- Created and sysprepped a fully configured, generalized Windows golden image ready to deploy
- Built a PXE-boot imaging pipeline using a locally hosted FOG server to deploy a standardized OS image
  over the network to new machines automatically
- Used this pipeline to image and deploy our new image to all our Windows desktops and laptops

## Result

- Centralized management for our most used devices (Macs) from a single console instead of individually
- 80 machines imaged and deployed via PXE with no manual installation,  a process that would otherwise have taken many hours
  per machine compressed into a repeatable, automated pipeline
