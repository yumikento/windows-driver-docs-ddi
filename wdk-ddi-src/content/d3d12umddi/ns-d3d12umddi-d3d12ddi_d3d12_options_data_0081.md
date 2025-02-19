---
UID: NS:d3d12umddi.D3D12DDI_D3D12_OPTIONS_DATA_0081
tech.root: display
title: D3D12DDI_D3D12_OPTIONS_DATA_0081
ms.date: 05/13/2021
targetos: Windows
description: The D3D12DDI_D3D12_OPTIONS_DATA_0081 structure contains display options data supported by the driver/hardware.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3d12umddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: D3D12DDI_D3D12_OPTIONS_DATA_0081
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_D3D12_OPTIONS_DATA_0081
f1_keywords:
 - D3D12DDI_D3D12_OPTIONS_DATA_0081
 - d3d12umddi/D3D12DDI_D3D12_OPTIONS_DATA_0081
dev_langs:
 - c++
---

## -description

The D3D12DDI_D3D12_OPTIONS_DATA_0081 structure contains display options data supported by the driver/hardware.

## -struct-fields

### -field ResourceBindingTier

The [**D3D12DDI_RESOURCE_BINDING_TIER**](./ne-d3d12umddi-d3d12ddi_resource_binding_tier.md
) value.

### -field ConservativeRasterizationTier

The [**D3D12_CONSERVATIVE_RASTERIZATION_TIER**](/windows/win32/api/d3d12/ne-d3d12-d3d12_conservative_rasterization_tier) value.

### -field TiledResourcesTier

The [**D3D12DDI_TILED_RESOURCES_TIER**](/windows/win32/api/d3d12/ne-d3d12-d3d12_tiled_resources_tier) value.

### -field CrossNodeSharingTier

The [**D3D12DDI_CROSS_NODE_SHARING_TIER**](./ne-d3d12umddi-d3d12ddi_cross_node_sharing_tier.md
) value indicating the level of sharing across nodes of a display adapter.

### -field VPAndRTArrayIndexFromAnyShaderFeedingRasterizerSupportedWithoutGSEmulation

Set TRUE when VP and RT array index from any shader feeding rasterizer supported without GS emulation; otherwise, set FALSE.

### -field OutputMergerLogicOp

Set TRUE when output merger logic operations are supported; otherwise, set FALSE.

### -field ResourceHeapTier

The [**D3D12DDI_RESOURCE_HEAP_TIER**](./ne-d3d12umddi-d3d12ddi_resource_heap_tier.md) value.

### -field DepthBoundsTestSupported

Set TRUE when depth bounds testing is supported; otherwise, set FALSE.

### -field ProgrammableSamplePositionsTier

The **D3D12DDI_PROGRAMMABLE_SAMPLE_POSITIONS_TIER** value indicating the supported programmable sample positions tier.

### -field CopyQueueTimestampQueriesSupported

Set TRUE when queue timestamp queries are supported; otherwise, set FALSE.

### -field WriteBufferImmediateQueueFlags

The [**D3D12DDI_COMMAND_QUEUE_FLAGS**](./ne-d3d12umddi-d3d12ddi_command_queue_flags.md) value for the video command queue.

### -field ViewInstancingTier

The [**D3D12DDI_VIEW_INSTANCING_TIER**](./ne-d3d12umddi-d3d12ddi_view_instancing_tier.md) value.

### -field BarycentricsSupported

Set TRUE when Barycentric coordinates are supported; otherwise, set FALSE.

### -field ReservedBufferPlacementSupported

Set TRUE when buffer placement is supported (only 64KB aligned MSAA support); otherwise, set FALSE.

### -field Deterministic64KBUndefinedSwizzle

Set TRUE when deterministic 64KB undefined swizzle is supported; otherwise, set FALSE.

### -field SRVOnlyTiledResourceTier3

Set TRUE when the hardware supports SRV-only sparse volume textures; otherwise, set FALSE.

### -field RenderPassTier

The [**D3D12DDI_RENDER_PASS_TIER**](ne-d3d12umddi-d3d12ddi_render_pass_tier.md) that the hardware supports.

### -field RaytracingTier

The [**D3D12DDI_RAYTRACING_TIER**](ne-d3d12umddi-d3d12ddi_raytracing_tier.md) that the hardware supports.

### -field VariableShadingRateTier

The [**D3D12DDI_VARIABLE_SHADING_RATE_TIER**](ne-d3d12umddi-d3d12ddi_variable_shading_rate_tier.md) that the hardware supports.

### -field PerPrimitiveShadingRateSupportedWithViewportIndexing

Set TRUE when per primitive shading rate is supported with viewport indexing; otherwise, set FALSE.

### -field AdditionalShadingRatesSupported

Set TRUE if additional shading rates are supported; otherwise, set FALSE.

### -field ShadingRateImageTileSize

The tile size of the screen-space image.

### -field BackgroundProcessingSupported

Set TRUE when the driver supports background processing; otherwise, set FALSE.

### -field MeshShaderTier

The [**D3D12DDI_MESH_SHADER_TIER**](./ne-d3d12umddi-d3d12ddi_mesh_shader_tier.md) that the device supports.

### -field SamplerFeedbackTier

The [**D3D12DDI_SAMPLER_FEEDBACK_TIER**](./ne-d3d12umddi-d3d12ddi_mesh_shader_tier.md) that the device supports.

### -field DriverManagedShaderCachePresent

Set TRUE when the driver supports shader cache  management. When set TRUE, the driver must provide a non-NULL [**PFND3D12DDI_IMPLICITSHADERCACHECONTROL_0080**](nc-d3d12umddi-pfnd3d12ddi_implicitshadercachecontrol_0080.md) callback function.

### -field MeshShaderSupportsFullRangeRenderTargetArrayIndex

Set TRUE when the driver supports full render target array indexing.
