---
UID: NF:wdm.RtlxAnsiStringToUnicodeSize
title: RtlxAnsiStringToUnicodeSize function (wdm.h)
description: The RtlxAnsiStringToUnicodeSize routine returns the number of bytes that are required for a null-terminated Unicode string that is equivalent to a specified ANSI string.
old-location: kernel\rtlxansistringtounicodesize.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["RtlxAnsiStringToUnicodeSize function"]
ms.keywords: RtlxAnsiStringToUnicodeSize, RtlxAnsiStringToUnicodeSize routine [Kernel-Mode Driver Architecture], k109_9343d498-bc89-428c-8e68-53c205c58bae.xml, kernel.rtlxansistringtounicodesize, wdm/RtlxAnsiStringToUnicodeSize
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlxAnsiStringToUnicodeSize
 - wdm/RtlxAnsiStringToUnicodeSize
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - RtlxAnsiStringToUnicodeSize
---

# RtlxAnsiStringToUnicodeSize function


## -description

The <b>RtlxAnsiStringToUnicodeSize</b> routine returns the number of bytes that are required for a null-terminated Unicode string that is equivalent to a specified ANSI string.

## -parameters

### -param AnsiString [in]


Pointer to the ANSI string for which to compute the number of bytes that are required for an equivalent null-terminated Unicode string.

## -returns

<b>RtlxAnsiStringToUnicodeSize</b> returns the number of bytes that are required for an equivalent null-terminated Unicode string, if the ANSI string can be translated into a Unicode string by using the current system locale information. Otherwise, this routine returns zero.

## -remarks

The ANSI string is interpreted for the current system locale.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlansistringtounicodesize">RtlAnsiStringToUnicodeSize</a>
