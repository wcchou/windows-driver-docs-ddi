---
UID: NS:ntifs._SYSTEM_RESOURCE_ATTRIBUTE_ACE
title: _SYSTEM_RESOURCE_ATTRIBUTE_ACE (ntifs.h)
description: The SYSTEM_RESOURCE_ATTRIBUTE_ACE structure defines an access-control entry (ACE) for the system access-control list (ACL) specifying what rights a particular claim has to a resource.
old-location: ifsk\system_resource_attribute_ace.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["SYSTEM_RESOURCE_ATTRIBUTE_ACE structure"]
ms.keywords: "*PSYSTEM_RESOURCE_ATTRIBUTE_ACE, PSYSTEM_RESOURCE_ATTRIBUTE_ACE, PSYSTEM_RESOURCE_ATTRIBUTE_ACE structure pointer [Installable File System Drivers], SYSTEM_RESOURCE_ATTRIBUTE_ACE, SYSTEM_RESOURCE_ATTRIBUTE_ACE structure [Installable File System Drivers], _SYSTEM_RESOURCE_ATTRIBUTE_ACE, ifsk.system_resource_attribute_ace, ntifs/PSYSTEM_RESOURCE_ATTRIBUTE_ACE, ntifs/SYSTEM_RESOURCE_ATTRIBUTE_ACE"
req.header: ntifs.h
req.include-header: Ntifs.h
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
req.typenames: SYSTEM_RESOURCE_ATTRIBUTE_ACE, *PSYSTEM_RESOURCE_ATTRIBUTE_ACE
f1_keywords:
 - _SYSTEM_RESOURCE_ATTRIBUTE_ACE
 - ntifs/_SYSTEM_RESOURCE_ATTRIBUTE_ACE
 - PSYSTEM_RESOURCE_ATTRIBUTE_ACE
 - ntifs/PSYSTEM_RESOURCE_ATTRIBUTE_ACE
 - SYSTEM_RESOURCE_ATTRIBUTE_ACE
 - ntifs/SYSTEM_RESOURCE_ATTRIBUTE_ACE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _SYSTEM_RESOURCE_ATTRIBUTE_ACE
 - PSYSTEM_RESOURCE_ATTRIBUTE_ACE
 - SYSTEM_RESOURCE_ATTRIBUTE_ACE
---

# _SYSTEM_RESOURCE_ATTRIBUTE_ACE structure


## -description

The SYSTEM_RESOURCE_ATTRIBUTE_ACE structure defines an access-control entry (ACE) for the system access-control list (ACL) specifying what rights a particular claim has to a resource. A resource attribute ACE causes an audit message to be logged when an attempt to gain access to resource based on a supported claim occurs.

## -struct-fields

### -field Header

Specifies an ACE_HEADER structure.

### -field Mask

Specifies an ACCESS_MASK structure that specifies access rights for a claim to a resource.

### -field SidStart

Specifies a SID. This is set to the Everyone, or S-1-1-0, SID.

## -remarks

Following the <b>SidStart</b> member begins a <b>CLAIM_SECURITY_ATTRIBUTE_RELATIVE_V1</b> structure which describes a supported claim.

## -see-also

<a href="/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a>



<a href="/windows-hardware/drivers/ifs/ace">ACE</a>



<a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_ace_header">ACE_HEADER</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_acl">ACL</a>



<a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_sid">SID</a>

