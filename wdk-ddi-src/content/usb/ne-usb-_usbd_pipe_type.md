---
UID: NE:usb._USBD_PIPE_TYPE
title: _USBD_PIPE_TYPE (usb.h)
description: The USBD_PIPE_TYPE enumerator indicates the type of pipe.
old-location: buses\usbd_pipe_type.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["USBD_PIPE_TYPE enumeration"]
ms.keywords: USBD_PIPE_TYPE, USBD_PIPE_TYPE enumeration [Buses], UsbdPipeTypeBulk, UsbdPipeTypeControl, UsbdPipeTypeInterrupt, UsbdPipeTypeIsochronous, _USBD_PIPE_TYPE, buses.usbd_pipe_type, usb/USBD_PIPE_TYPE, usb/UsbdPipeTypeBulk, usb/UsbdPipeTypeControl, usb/UsbdPipeTypeInterrupt, usb/UsbdPipeTypeIsochronous, usbstrct_a1fda372-f509-4667-a615-b68936b0a42b.xml
req.header: usb.h
req.include-header: Usb.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: USBD_PIPE_TYPE
f1_keywords:
 - _USBD_PIPE_TYPE
 - usb/_USBD_PIPE_TYPE
 - USBD_PIPE_TYPE
 - usb/USBD_PIPE_TYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - usb.h
api_name:
 - _USBD_PIPE_TYPE
 - USBD_PIPE_TYPE
---

# _USBD_PIPE_TYPE enumeration


## -description

The <b>USBD_PIPE_TYPE</b> enumerator indicates the type of pipe.

## -enum-fields

### -field UsbdPipeTypeControl

Indicates that the pipe is a control pipe.

### -field UsbdPipeTypeIsochronous

Indicates that the pipe is an isochronous transfer pipe.

### -field UsbdPipeTypeBulk

Indicates that the pipe is a bulk transfer pipe.

### -field UsbdPipeTypeInterrupt

Indicates that the pipe is an interrupt pipe.

## -see-also

<a href="/windows-hardware/drivers/ddi/_usbref/#enumerations">USB Constants and Enumerations</a>

