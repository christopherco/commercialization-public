---
title: SquareOrDesktopTile10
description: SquareOrDesktopTile10
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 0F87E806-8C0C-4FD1-9C0C-16AE53C27454
ms.author: alhopper
ms.date: 05/02/2017
ms.topic: article
ms.prod: windows-hardware
ms.technology: windows-oem
---

# SquareOrDesktopTile10


`SquareOrDesktopTile10` specifies which application appears as a square tile on the **Start** menu, in position SquareOrDesktopTile10. This position may vary based on the screen size, resolution, and DPI of the target device.

If the region of the current user account is among those in the Start Tile regional overrides, you can use this setting. For more information, see [RegionalOverrides](microsoft-windows-shell-setup-starttiles-regionaloverrides.md).

## Child Elements


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>[AppIdOrPath](microsoft-windows-shell-setup-starttiles-regionaloverrides-regionaloverride-squaretiles-squareordesktoptile10-appidorpath.md)</p></td>
<td><p>Specifies the <code>AppID</code> of the Windows Store apps, or the path to the desktop apps, which appear as square tiles on the <strong>Start</strong> screen.</p></td>
</tr>
<tr class="even">
<td><p>[FirstRunTask](microsoft-windows-shell-setup-starttiles-regionaloverrides-regionaloverride-squaretiles-squareordesktoptile10-firstruntask.md)</p></td>
<td><p>Specifies the background task that is active, or live, by default for a tile when a user signs in to Windows for the first time.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


specialize

auditUser

oobeSystem

## Parent Hierarchy


[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md)| [StartTiles](microsoft-windows-shell-setup-starttiles.md) | [RegionalOverrides](microsoft-windows-shell-setup-starttiles-regionaloverrides.md) | [RegionalOverride](microsoft-windows-shell-setup-starttiles-regionaloverrides-regionaloverride.md) | [SquareTiles](microsoft-windows-shell-setup-starttiles-regionaloverrides-regionaloverride-squaretiles.md)|**SquareOrDesktopTile10**

## Applies To


For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).

## XML Example


The following XML output shows how to use the `<SquareOrDesktopTile10>` component.

```
<SquareTiles>
          <SquareOrDesktopTile1>
               <AppIdOrPath>C:\programdata\microsoft\windows\start menu\programs\desktoptile1.lnk</AppIdOrPath>
               <FirstRunTask>backgroundtask.js</FirstRunTask>
          </SquareOrDesktopTile1>
          <SquareOrDesktopTile2>
               <AppIdOrPath>67890ChannelFabrikam.channel-JKL_mnop1234789!App</AppIdOrPath>
               <FirstRunTask>Fabrikam.FirstRunTask</FirstRunTask>
          </SquareOrDesktopTile2>
          <SquareOrDesktopTile3>
               <AppIdOrPath>C:\programdata\microsoft\windows\start menu\programs\desktoptile3.lnk</AppIdOrPath>
          </SquareOrDesktopTile3>
          <SquareTile1>
               <AppId>12345ChannelFabrikam.channel-ABC_defghij6789!App</AppId>
               <FirstRunTask>backgroundtask.js</FirstRunTask>
          </SquareTile1>
          <SquareTile2>
               <AppId>34567ChannelFabrikam.channel-DEF_012ghijk345!App</AppId>
               <FirstRunTask>Fabrikam.FirstRunTask</FirstRunTask>
          </SquareTile2>
          <SquareTile10>
               <AppId>56789ChannelFabrikam.channel-GHI_67890jklmno!App</AppId>
          </SquareTile10>
     </SquareTiles> 
```

## Related topics


[StartTiles](microsoft-windows-shell-setup-starttiles.md)

[RegionalOverrides](microsoft-windows-shell-setup-starttiles-regionaloverrides.md)

[SquareTiles](microsoft-windows-shell-setup-starttiles-regionaloverrides-regionaloverride-squaretiles.md)

[SquareTiles](microsoft-windows-shell-setup-starttiles-squaretiles.md)

 

 






