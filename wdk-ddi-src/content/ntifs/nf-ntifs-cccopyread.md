---
UID: NF:ntifs.CcCopyRead
title: CcCopyRead function (ntifs.h)
description: The CcCopyRead routine copies data from a cached file to a user buffer.
old-location: ifsk\cccopyread.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["CcCopyRead function"]
ms.keywords: CcCopyRead, CcCopyRead routine [Installable File System Drivers], ccref_76dde6ff-ccd7-4d90-a744-9d2c05624b00.xml, ifsk.cccopyread, ntifs/CcCopyRead
req.header: ntifs.h
req.include-header: Ntifs.h, FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: Available on Microsoft Windows 2000 and later Windows operating systems.
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
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - CcCopyRead
 - ntifs/CcCopyRead
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - CcCopyRead
---

# CcCopyRead function


## -description

The <b>CcCopyRead</b> routine copies data from a cached file to a user buffer.

## -parameters

### -param FileObject [in]


A pointer to a file object for the cached file from which the data is to be read.

### -param FileOffset [in]


A pointer to a variable that specifies the starting byte offset within the cached file.

### -param Length [in]


The length in bytes of the data to be read.

### -param Wait [in]


Set to <b>TRUE</b> if the caller can be put into a wait state until all the data has been copied, <b>FALSE</b> otherwise.

### -param Buffer [out]


A pointer to a buffer into which the data is to be copied.

### -param IoStatus [out]


A pointer to a caller-allocated structure that receives the final completion status and information about the operation. If not all of the data is copied successfully, <i>IoStatus.Information</i> contains the actual number of bytes that were copied.

## -returns

The <b>CcCopyRead</b> routine returns <b>TRUE</b> if the data was copied successfully, <b>FALSE</b> otherwise.

## -remarks

If <i>Wait</i> is <b>TRUE</b>, <b>CcCopyRead</b> is guaranteed to complete the copy request and return <b>TRUE</b>. If the required pages of the cached file are already resident in memory, the data will be copied immediately and no blocking will occur. If any needed pages are not resident, the caller will be put in a wait state until all required pages have been made resident and the data can be copied.

If <i>Wait</i> is <b>FALSE</b>, <b>CcCopyRead</b> will refuse to block, and will return <b>FALSE</b>, if the required pages of the cached file are not already resident in memory. 

<i>FileOffset</i> plus <i>Length</i> must be less than or equal to the size of the cached file, or an assertion failure will occur.

If any failure occurs, <b>CcCopyRead</b> raises a status exception for that particular failure. For example, if a pool allocation failure occurs, <b>CcCopyRead</b> raises a STATUS_INSUFFICIENT_RESOURCES exception; if an I/O error occurs, <b>CcCopyRead</b> raises the status exception of the I/O error. Therefore, to gain control if a failure occurs, the driver should wrap the call to <b>CcCopyRead</b> in a <b>try-except</b> or <b>try-finally</b> statement.

To cache a file, use <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccinitializecachemap">CcInitializeCacheMap</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccfastcopyread">CcFastCopyRead</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccinitializecachemap">CcInitializeCacheMap</a>



<a href="/previous-versions/ff539191(v=vs.85)">CcReadAhead</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccschedulereadahead">CcScheduleReadAhead</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccsetadditionalcacheattributes">CcSetAdditionalCacheAttributes</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccsetreadaheadgranularity">CcSetReadAheadGranularity</a>
