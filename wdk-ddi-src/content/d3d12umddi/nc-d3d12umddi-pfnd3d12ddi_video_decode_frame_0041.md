---
UID: NC:d3d12umddi.PFND3D12DDI_VIDEO_DECODE_FRAME_0041
title: PFND3D12DDI_VIDEO_DECODE_FRAME_0041 (d3d12umddi.h)
description: The PFND3D12DDI_VIDEO_DECODE_FRAME_0041 callback function decodes a video frame. The function is called by a client driver.
ms.date: 10/19/2018
keywords: ["PFND3D12DDI_VIDEO_DECODE_FRAME_0041 callback function"]
req.header: d3d12umddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
tech.root: display
f1_keywords:
 - PFND3D12DDI_VIDEO_DECODE_FRAME_0041
 - d3d12umddi/PFND3D12DDI_VIDEO_DECODE_FRAME_0041
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_VIDEO_DECODE_FRAME_0041
product:
 - Windows
---

# PFND3D12DDI_VIDEO_DECODE_FRAME_0041 callback function


## -description

Implemented by the client driver to decode a video frame.

## -parameters

### -param hDrvCommandList

A handle to the driver's data for the command list. The driver uses this region of memory to store internal data structures that are related to its command list.

### -param hDrvDecoder

The video decoder that contains internal state for this decode session.  Examples include motion vectors, internal temporary allocations, etc.  See [Creating a Video Decoder](/windows-hardware/drivers/display/creating-a-video-decode-device).

### -param pOutputStreamParameters

Specifies the output surface and output parameters. See [D3D12DDI_VIDEO_DECODE_OUTPUT_STREAM_ARGUMENTS](ns-d3d12umddi-d3d12ddi_video_decode_output_stream_arguments_0021.md).

### -param pInputStreamParameters

Specifies the input bit stream, parameters, reference frames, and other input parameters for the decode operation.  See [D3D12DDI_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS](ns-d3d12umddi-d3d12ddi_video_decode_input_stream_arguments_0032.md).

## -prototype

```cpp
//Declaration

PFND3D12DDI_VIDEO_DECODE_FRAME_0041 Pfnd3d12ddiVideoDecodeFrame0041;

// Definition

VOID Pfnd3d12ddiVideoDecodeFrame0041
(
	D3D12DDI_HCOMMANDLIST hDrvCommandList
	D3D12DDI_HVIDEODECODER_0020 hDrvDecoder
	 const D3D12DDI_VIDEO_DECODE_OUTPUT_STREAM_ARGUMENTS_0041 *pOutputStreamParameters
	 const D3D12DDI_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS_0032 *pInputStreamParameters
)
{...}

PFND3D12DDI_VIDEO_DECODE_FRAME_0041


```

## -see-also
