---
title: Diagnostics
description: Diagnostics
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: abe9889c-5b3e-4b60-9667-b7afc9957634
ms.mktglfcycl: deploy
ms.sitesec: msdn
ms.author: alhopper
ms.date: 05/02/2017
ms.topic: article
ms.prod: windows-hardware
ms.technology: windows-oem
---

# Diagnostics


`Diagnostics` specifies whether installation statistics, such as status reports and failures, are sent to Microsoft.

## Child Elements


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>[OptIn](microsoft-windows-setup-diagnostics-optin.md)</p></td>
<td><p>Specifies whether to send installation statistic information to Microsoft.</p></td>
</tr>
</tbody>
</table>

 

## Valid Passes


windowsPE

## Parent Hierarchy


[microsoft-windows-setup-](microsoft-windows-setup.md) | **Diagnostics**

## Applies To


For the list of the supported Windows editions and architectures that this component supports, see [microsoft-windows-setup-](microsoft-windows-setup.md).

## XML Example


The following XML output shows how to change this setting so that no information is sent.

```
<Diagnostics>
   <OptIn>false</OptIn>
</Diagnostics>
```

## Related topics


[microsoft-windows-setup-](microsoft-windows-setup.md)

 

 






