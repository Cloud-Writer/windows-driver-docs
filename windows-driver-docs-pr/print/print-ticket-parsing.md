---
title: Print Ticket Parsing
author: windows-driver-content
description: Print Ticket Parsing
MS-HAID:
- 'xpsfiltpipe\_9881cd01-c9f9-4204-812a-9860763210ce.xml'
- 'print.print\_ticket\_parsing'
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 8328110a-abb4-47aa-ab1d-730e4a2ce7bd
keywords: ["XPSDrv printer drivers WDK , render modules", "render modules WDK XPSDrv , Print Tickets", "Print Tickets WDK , XPSDrv printer drivers", "parsing Print Ticket objects"]
---

# Print Ticket Parsing


After the Print Ticket has been merged for the current document part, the print driver filter must parse the contents to find the settings that apply to the filter. The methods of the [IPrintCoreHelper interface](https://msdn.microsoft.com/library/windows/hardware/ff552960) can be used in the print driver filter modules to help parse the Print Ticket elements. After the Print Ticket elements have been extracted from the Print Ticket, they can be integrated into the filter module function. The filter modules are described in the [XPS Filter Pipeline](xpsdrv-printer-driver.md) section.

 

 


--------------------
[Send comments about this topic to Microsoft](mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback%20%5Bprint\print%5D:%20Print%20Ticket%20Parsing%20%20RELEASE:%20%289/1/2016%29&body=%0A%0APRIVACY%20STATEMENT%0A%0AWe%20use%20your%20feedback%20to%20improve%20the%20documentation.%20We%20don't%20use%20your%20email%20address%20for%20any%20other%20purpose,%20and%20we'll%20remove%20your%20email%20address%20from%20our%20system%20after%20the%20issue%20that%20you're%20reporting%20is%20fixed.%20While%20we're%20working%20to%20fix%20this%20issue,%20we%20might%20send%20you%20an%20email%20message%20to%20ask%20for%20more%20info.%20Later,%20we%20might%20also%20send%20you%20an%20email%20message%20to%20let%20you%20know%20that%20we've%20addressed%20your%20feedback.%0A%0AFor%20more%20info%20about%20Microsoft's%20privacy%20policy,%20see%20http://privacy.microsoft.com/default.aspx. "Send comments about this topic to Microsoft")

