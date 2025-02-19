---
UID: NS:ntddk._PCI_EXPRESS_ROOT_CONTROL_REGISTER
title: _PCI_EXPRESS_ROOT_CONTROL_REGISTER (ntddk.h)
description: The _PCI_EXPRESS_ROOT_CONTROL_REGISTER structure (ntddk.h) describes a PCI Express (PCIe) root control register of a PCIe capability structure.
old-location: pci\pci_express_root_control_register.htm
tech.root: PCI
ms.date: 02/24/2018
keywords: ["PCI_EXPRESS_ROOT_CONTROL_REGISTER structure"]
ms.keywords: "*PPCI_EXPRESS_ROOT_CONTROL_REGISTER, PCI.pci_express_root_control_register, PCI_EXPRESS_ROOT_CONTROL_REGISTER, PCI_EXPRESS_ROOT_CONTROL_REGISTER union [Buses], PPCI_EXPRESS_ROOT_CONTROL_REGISTER, PPCI_EXPRESS_ROOT_CONTROL_REGISTER union pointer [Buses], _PCI_EXPRESS_ROOT_CONTROL_REGISTER, ntddk/PCI_EXPRESS_ROOT_CONTROL_REGISTER, ntddk/PPCI_EXPRESS_ROOT_CONTROL_REGISTER, pci_struct_ef335e30-c046-4066-8411-27bf96cbcd08.xml"
req.header: ntddk.h
req.include-header: Ntddk.h, Miniport.h
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: PCI_EXPRESS_ROOT_CONTROL_REGISTER, *PPCI_EXPRESS_ROOT_CONTROL_REGISTER
f1_keywords:
 - _PCI_EXPRESS_ROOT_CONTROL_REGISTER
 - ntddk/_PCI_EXPRESS_ROOT_CONTROL_REGISTER
 - PPCI_EXPRESS_ROOT_CONTROL_REGISTER
 - ntddk/PPCI_EXPRESS_ROOT_CONTROL_REGISTER
 - PCI_EXPRESS_ROOT_CONTROL_REGISTER
 - ntddk/PCI_EXPRESS_ROOT_CONTROL_REGISTER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - _PCI_EXPRESS_ROOT_CONTROL_REGISTER
 - PPCI_EXPRESS_ROOT_CONTROL_REGISTER
 - PCI_EXPRESS_ROOT_CONTROL_REGISTER
---

# _PCI_EXPRESS_ROOT_CONTROL_REGISTER structure (ntddk.h)


## -description

The PCI_EXPRESS_ROOT_CONTROL_REGISTER structure describes a PCI Express (PCIe) root control register of a PCIe capability structure.

## -struct-fields

### -field DUMMYSTRUCTNAME

### -field AsUSHORT

A USHORT representation of the contents of the PCI_EXPRESS_ROOT_CONTROL_REGISTER structure.


### -field CRSSoftwareVisibilityEnable

A single bit that indicates that the root port is enabled to return configuration request retry status (CRS) completion status to software.


### -field CorrectableSerrEnable

A single bit that indicates that a system error should be generated if a correctable error is reported by any of the devices in the hierarchy that are associated with this root port or by the root port itself.


### -field FatalSerrEnable

A single bit that indicates that a system error should be generated if a non-fatal error is reported by any of the devices in the hierarchy that are associated with this root port or by the root port itself.


### -field NonFatalSerrEnable

A single bit that indicates that a system error should be generated if a non-fatal error is reported by any of the devices in the hierarchy that are associated with this root port or by the root port itself.


### -field PMEInterruptEnable

A single bit that indicates that interrupts are enabled for power management events.


### -field Rsvd

Reserved.

## -syntax

```cpp
typedef union _PCI_EXPRESS_ROOT_CONTROL_REGISTER {
  struct {
    USHORT CorrectableSerrEnable  :1;
    USHORT NonFatalSerrEnable  :1;
    USHORT FatalSerrEnable  :1;
    USHORT PMEInterruptEnable  :1;
    USHORT CRSSoftwareVisibilityEnable  :1;
    USHORT Rsvd  :11;
  };
  USHORT AsUSHORT;
} PCI_EXPRESS_ROOT_CONTROL_REGISTER, *PPCI_EXPRESS_ROOT_CONTROL_REGISTER;
```

## -remarks

The PCI_EXPRESS_ROOT_CONTROL_REGISTER structure is available in Windows Server 2008 and later versions of Windows.

A PCI_EXPRESS_ROOT_CONTROL_REGISTER structure is contained in the <a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_pci_express_capability">PCI_EXPRESS_CAPABILITY</a> structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_pci_express_capability">PCI_EXPRESS_CAPABILITY</a>

