---
author: joshbax-msft
title: Ratetest (WoW64)
description: Ratetest (WoW64)
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 5e7924a2-e992-4b8e-b5a0-dbad10eea75c
---

# Ratetest (WoW64)


This automated test verifies that the video card hardware supports a resolution of 800 × 600 pixels, a color depth of 16 bits per pixel (bpp), a 16-bit Z buffer, double frame buffering, and a 75-Hertz (Hz) refresh rate in full-screen 3-D graphics mode.

The test switches to all enumerated Graphics Device Interface (GDI) display modes, all available low-resolution GDI modes (less than 640 × 480 pixels), and enumerated Microsoft® DirectDraw full-screen modes. The test then intersects these two sets of modes and validates that the set of Microsoft DirectX® enumerated modes exists in the set of GDI enumerated modes.

The test switches to these modes and validates that the refresh rate actually produced by the card matches the refresh rate that the driver indicates. The test validates the refresh rate by using **IDirectDraw::GetVerticalBlankStatus**. After each mode is set, the test displays an MS-DOS window to make sure that virtualization of VGA hardware works correctly for each mode.

## Test details


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Associated requirements</strong></p></td>
<td><p>Device.Graphics.AdapterRender.D3D10Core.D3D10CorePrimary</p>
<p>[See the device hardware requirements.](http://go.microsoft.com/fwlink/p/?linkid=254483)</p></td>
</tr>
<tr class="even">
<td><p><strong>Platforms</strong></p></td>
<td><p>Windows 7 (x64) Windows 8 (x64) Windows Server 2012 (x64) Windows Server 2008 R2 (x64) Windows 8.1 x64 Windows Server 2012 R2</p></td>
</tr>
<tr class="odd">
<td><p><strong>Expected run time</strong></p></td>
<td><p>~60 minutes</p></td>
</tr>
<tr class="even">
<td><p><strong>Categories</strong></p></td>
<td><p>Certification</p></td>
</tr>
<tr class="odd">
<td><p><strong>Type</strong></p></td>
<td><p>Automated</p></td>
</tr>
</tbody>
</table>

 

## Running the test


Before you run the test, complete the test setup as described in the test requirements: [Graphic Adapter or Chipset Testing Prerequisites](graphic-adapter-or-chipset-testing-prerequisites.md).

**Warning**  
The Super VGA (SVGA)–compatible monitor that is attached to the system that you are testing must support the minimum display resolution and refresh rate that were specified earlier.

 

## Troubleshooting


For troubleshooting information, see [Troubleshooting Device.Graphics Testing](troubleshooting-devicegraphics-testing.md).

## More information


The test first verifies the requirements in software by querying the DirectDraw capabilities. Then, it verifies the requirements in hardware by selecting the specified settings and displaying a predefined scene. The following steps describe the process in detail:

1.  The test creates a **DirectDraw** object with the **DirectDrawCreate** function by using the **DDCREATE\_HARDWAREONLY** option. This action forces a HAL device to be used, instead of a HEL device.

2.  By using the DirectDraw **IDirectDraw4:EnumDisplayModes** function, the test verifies the following values in the **DDSURFACEDESC2** structure as valid choices:

    -   **dwWidth** = 800 (**dwWidth** = 640 for mobile systems)

    -   **dwHeight** = 600 (**dwHeight** = 480 for mobile systems)

    -   **dwRefreshRate** = 75 (or 0 for drivers that do not report this value)

3.  The **DDPIXELFORMAT** structure verifies that the following are valid choices:

    -   **dwRGBBitCount** = 16

    -   **dwZBufferBitDepth** = 16

4.  The **SetCooperativeLevel** function selects the **DDSCL\_EXCLUSIVE** and **DDSCL\_FULLSCREEN** options.

5.  The test calls **SetDisplayMode** to set the display to 800 × 600 × 16 and the refresh rate to 75 Hz. If the 75-Hz value fails, the test uses a refresh-rate value of 0 (default).

6.  The test calls **CreateSurface** for the primary surface, the back buffer, and the Z buffer.

7.  The test calls the Direct3D **CreateDevice** function by using the **IID\_IDirect3DHALDevice** class identifier to allow access to the 3-D graphics hardware device.

8.  All other 3-D graphics tests that are specified use a double-buffered surface to verify compliance with the requirement for double frame buffering.

The test application displays and logs a pass-or-fail indication of compliance with this requirement. Any of the device setup steps in the preceding list can generate failures. Any detected failure generates additional information that clearly identifies the noncompliant issue.

### Command Syntax

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Command option</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Ratetest</strong></p></td>
<td><p>Runs the test job.</p></td>
</tr>
</tbody>
</table>

 

**Note**  
For command-line help for this test binary, type **/h**.

 

### File List

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>File</th>
<th>Location</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Configdisplay.exe</p></td>
<td><p><em>&lt;[testbinroot]&gt;</em>\nttest\windowstest\tools\</p></td>
</tr>
<tr class="even">
<td><p>Dxgfilterua.dll</p></td>
<td><p><em>&lt;[testbinroot]&gt;</em>\nttest\windowstest\graphics\tests\gdi\</p></td>
</tr>
<tr class="odd">
<td><p>Ntlog.dll</p></td>
<td><p><em>&lt;[testbinroot]&gt;</em>\nttest\Commontest\ntlog</p></td>
</tr>
<tr class="even">
<td><p>Ratetest.exe</p></td>
<td><p><em>&lt;[testbinroot]&gt;</em>\nttest\windowstest\graphics\tests\gdi</p></td>
</tr>
<tr class="odd">
<td><p>TDRWatch.exe</p></td>
<td><p><em>&lt;[testbinroot]&gt;</em>\nttest\windowstest\graphics\</p></td>
</tr>
</tbody>
</table>

 

 

 





