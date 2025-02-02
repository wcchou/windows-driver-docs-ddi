---
UID: NF:fltkernel.FltInitializePushLock
title: FltInitializePushLock function (fltkernel.h)
description: The FltInitializePushLock routine initializes a push lock variable.
old-location: ifsk\fltinitializepushlock.htm
tech.root: ifsk
ms.date: 11/29/2021
keywords: ["FltInitializePushLock function"]
ms.keywords: FltApiRef_e_to_o_348be4fc-280f-4dc3-b5fb-ada1aa037d09.xml, FltInitializePushLock, FltInitializePushLock routine [Installable File System Drivers], fltkernel/FltInitializePushLock, ifsk.fltinitializepushlock
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Microsoft Windows XP SP2, Microsoft Windows Server 2003 SP1, and later.
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
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FltInitializePushLock
 - fltkernel/FltInitializePushLock
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltInitializePushLock
---

# FltInitializePushLock function


## -description

The <b>FltInitializePushLock</b> routine initializes a push lock variable.

## -parameters

### -param PushLock [out]


Pointer to the caller-supplied storage, which must be at least the value of <b>sizeof(</b>EX_PUSH_LOCK<b>)</b>, for the push lock variable to be initialized. The storage must be 4-byte aligned on 32-bit platforms, and 8-byte aligned on 64-bit platforms.

## -returns

None

## -remarks

Push locks are rarely a good choice for file system minifilters.  As described below, some of their characteristics can be incompatible with the inherently re-entrant nature of file systems.  

Push locks are similar to <a href="/windows-hardware/drivers/kernel/eresource-structures">ERESOURCE structures</a> (also called "resources") in the following ways: 

<ul>
<li>
Push locks can be used for synchronization by a set of threads. 

</li>
<li>
Push locks can be acquired for shared or exclusive access. 

</li>
<li>
Although the caller provides the storage for the push lock variable, the EX_PUSH_LOCK structure is opaque: that is, its members are reserved for system use. 

</li>
</ul>
Push locks have the following disadvantages when compared with ERESOURCE structures: 

<ul>
<li>
The algorithm for granting exclusive access is not fair to all threads. If there is a high level of exclusive-lock contention, there is no guarantee about the order in which threads will be granted exclusive access. 

</li>
<li>
There are no support routines for determining the current owner of a push lock at run time. (Users of ERESOURCE structures can call routines such as <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-exisresourceacquiredexclusivelite">ExIsResourceAcquiredExclusiveLite</a> to determine whether the current thread has exclusive access to the resource.) 

</li>
<li>
For the same reason there are no support extensions for determining the current owner of a push lock at debug time, and thus diagnosing deadlocks.  (Users of ERESOURCE structures can use the <code>!locks</code> extension in kd or windbg to find this out.)
</li>
<li>
There is no driver verifier support to help early diagnosis of deadlocks through push locks.
</li>
<li>
Exclusive push locks cannot be acquired recursively.
</li>
</ul>
Push locks offer the following advantages over ERESOURCE structures: 

<ul>
<li>
When push locks are mostly acquired for shared access, they are more efficient than ERESOURCE structures. 

</li>
<li>
The storage for push locks can be allocated from paged or nonpaged pool. ERESOURCE structures must be allocated only from nonpaged pool. 

</li>
<li>
EX_PUSH_LOCK structures are much smaller than ERESOURCE structures. 

</li>
</ul>
Unless any of these advantages are compelling an ERESOURCE is usually the more robust and maintainable solution to the Read/Write synchronization problem.

To acquire a push lock for exclusive access, call <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltacquirepushlockexclusive">FltAcquirePushLockExclusive</a>. 

To acquire a push lock for shared access, call <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltacquirepushlockshared">FltAcquirePushLockShared</a>. 

To release a push lock, call <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreleasepushlock">FltReleasePushLock</a>. 

To delete a push lock, call <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltdeletepushlock">FltDeletePushLock</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-exisresourceacquiredexclusivelite">ExIsResourceAcquiredExclusiveLite</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltacquirepushlockexclusive">FltAcquirePushLockExclusive</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltacquirepushlockshared">FltAcquirePushLockShared</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltdeletepushlock">FltDeletePushLock</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreleasepushlock">FltReleasePushLock</a>
