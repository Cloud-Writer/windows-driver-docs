---
title: SpinLockSafe rule (wdm)
description: The SpinLockSafe rule specifies that IoStartNextPacket and IoCompleteRequest are not called while holding a spin lock.
ms.assetid: 64a18cb0-80a3-4830-a5b0-131fc1ebdf60
ms.author: windowsdriverdev
ms.date: 05/21/2018
ms.topic: article
ms.prod: windows-hardware
ms.technology: windows-devices
keywords: ["SpinLockSafe rule (wdm)"]
topic_type:
- apiref
api_name:
- SpinLockSafe
api_type:
- NA
---

# SpinLockSafe rule (wdm)


The **SpinLockSafe** rule specifies that [**IoStartNextPacket**](https://msdn.microsoft.com/library/windows/hardware/ff550358) and [**IoCompleteRequest**](https://msdn.microsoft.com/library/windows/hardware/ff548343) are not called while holding a spin lock.

This rule also specifies that the driver calls [**KeAcquireSpinLock**](https://msdn.microsoft.com/library/windows/hardware/ff551917) or [**KeAcquireSpinLockAtDpcLevel**](https://msdn.microsoft.com/library/windows/hardware/ff551921) before calling [**KeReleaseSpinLockFromDpcLevel**](https://msdn.microsoft.com/library/windows/hardware/ff553150) or [**KeReleaseSpinLock**](https://msdn.microsoft.com/library/windows/hardware/ff553145), and that it calls [**IoAcquireCancelSpinLock**](https://msdn.microsoft.com/library/windows/hardware/ff548196) before calling [**IoReleaseCancelSpinLock**](https://msdn.microsoft.com/library/windows/hardware/ff549550).

Static Driver Verifier can report false violations of this rule if the driver includes nested SpinLocks, even if those spin locks are acquired and released correctly.

|              |     |
|--------------|-----|
| Driver model | WDM |

How to test
-----------

<table>
<colgroup>
<col width="100%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">At compile time</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Run [Static Driver Verifier](https://msdn.microsoft.com/library/windows/hardware/ff552808) and specify the <strong>SpinLockSafe</strong> rule.</p>
Use the following steps to run an analysis of your code:
<ol>
<li>[Prepare your code (use role type declarations).](https://msdn.microsoft.com/library/windows/hardware/hh454281#preparing-your-source-code)</li>
<li>[Run Static Driver Verifier.](https://msdn.microsoft.com/library/windows/hardware/hh454281#running-static-driver-verifier)</li>
<li>[View and analyze the results.](https://msdn.microsoft.com/library/windows/hardware/hh454281#viewing-and-analyzing-the-results)</li>
</ol>
<p>For more information, see [Using Static Driver Verifier to Find Defects in Drivers](https://msdn.microsoft.com/library/windows/hardware/hh454281).</p></td>
</tr>
</tbody>
</table>

Applies to
----------

[**IoAcquireCancelSpinLock**](https://msdn.microsoft.com/library/windows/hardware/ff548196)
[**IoCompleteRequest**](https://msdn.microsoft.com/library/windows/hardware/ff548343)
[**IoReleaseCancelSpinLock**](https://msdn.microsoft.com/library/windows/hardware/ff549550)
[**IoStartNextPacket**](https://msdn.microsoft.com/library/windows/hardware/ff550358)
[**KeAcquireSpinLock**](https://msdn.microsoft.com/library/windows/hardware/ff551917)
[**KeAcquireSpinLockRaiseToDpc**](https://msdn.microsoft.com/library/windows/hardware/ff551928)
[**KeReleaseSpinLock**](https://msdn.microsoft.com/library/windows/hardware/ff553145)
 

 





