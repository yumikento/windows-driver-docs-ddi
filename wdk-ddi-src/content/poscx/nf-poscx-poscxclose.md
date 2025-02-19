---
UID: NF:poscx.PosCxClose
title: PosCxClose function (poscx.h)
description: PosCxClose is called to delete an opened PosCx library instance. This function releases the device if the caller is the owner, and cancels pending requests. It should be called from the driver's EVT_WDF_FILE_CLOSE callback.
old-location: pos\poscxclose.htm
tech.root: pos
ms.date: 02/23/2018
keywords: ["PosCxClose function"]
ms.keywords: PosCxClose, PosCxClose function, pos.poscxclose, poscx/PosCxClose
req.header: poscx.h
req.include-header: Poscx.h
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
req.typenames: 
req.product: Windows 10 or later.
f1_keywords:
 - PosCxClose
 - poscx/PosCxClose
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - poscx.h
api_name:
 - PosCxClose
---

# PosCxClose function


## -description

PosCxClose is called to delete an opened PosCx library instance. This function releases the device if the caller is the owner, and cancels pending requests. It should be called from the driver's [EVT_WDF_FILE_CLOSE](../wdfdevice/nc-wdfdevice-evt_wdf_file_close.md) callback.

## -parameters

### -param device [in]


A handle to a framework device object that represents the device.

### -param fileObject [in]


A handle to a framework file object that identifies the caller associated with the open instance.

## -returns

An appropriate NTSTATUS error code that indicates the close instance completion status.
