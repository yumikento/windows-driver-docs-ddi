---
UID: NF:ursdevice.UrsReportHardwareEvent
title: UrsReportHardwareEvent function (ursdevice.h)
description: Notifies the USB dual-role class extension about a new hardware event.
old-location: buses\ursreporthardwareevent.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["UrsReportHardwareEvent function"]
ms.keywords: UrsReportHardwareEvent, UrsReportHardwareEvent function [Buses], buses.ursreporthardwareevent, ursdevice/UrsReportHardwareEvent
req.header: ursdevice.h
req.include-header: Urscx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Urscxstub.lib
req.dll: 
req.irql: HIGH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - UrsReportHardwareEvent
 - ursdevice/UrsReportHardwareEvent
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Urscxstub.lib
 - Urscxstub.dll
api_name:
 - UrsReportHardwareEvent
---

# UrsReportHardwareEvent function


## -description

Notifies the USB dual-role class extension about a new hardware event.

## -parameters

### -param Device [in]


A handle to the framework device object that the client driver retrieved in the previous call to <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a>.

### -param HardwareEvent [in]


A <a href="/windows-hardware/drivers/ddi/urstypes/ne-urstypes-_urs_hardware_event">URS_HARDWARE_EVENT</a>-type value that indicates the type of event that occurred.

## -returns

The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return an appropriate <a href="/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> error code.

## -remarks

Before reporting any hardware events, the client driver for the dual-role controller must indicate to the class extension that the driver supports hardware events by calling <a href="/windows-hardware/drivers/ddi/ursdevice/nf-ursdevice-urssethardwareeventsupport">UrsSetHardwareEventSupport</a>.

The client driver cannot pass <b>UrsHardwareEventNone</b> as the <i>HardwareEvent</i> parameter value. That value is reserved for internal use.

The client driver must call this method to report any hardware event, such as ID-pin interrupts. Typically, in the driver's implementation of the <a href="/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_isr">EvtInterruptIsr</a> callback, the driver reads the  ID-pin state and reports the event to the class extension by calling this method.

## -see-also

<a href="/windows-hardware/drivers/ddi/ursdevice/nf-ursdevice-urssethardwareeventsupport">UrsSetHardwareEventSupport</a>
