﻿---
Description: 'Returns a mesh with modifications resulting from adaptive spatial sampling. The returned mesh contains only positions, normals, and texture coordinates (if defined).'
ms.assetid: '21447733-b27b-4906-8c0e-7089dec71b5b'
title: 'ID3DXPRTEngine::GetAdaptedMesh method'
---

# ID3DXPRTEngine::GetAdaptedMesh method

Returns a mesh with modifications resulting from adaptive spatial sampling. The returned mesh contains only positions, normals, and texture coordinates (if defined).

## Syntax


```C++
HRESULT GetAdaptedMesh(
  [in]      LPDIRECT3DDEVICE9 pDevice,
  [in, out] UINT              *pFaceRemap,
  [in, out] UINT              *pVertRemap,
  [in, out] FLOAT             *pfVertWeights,
  [out]     LPD3DXMESH        *ppMesh
);
```



## Parameters

<dl> <dt>

*pDevice* \[in\]
</dt> <dd>

Type: **[**LPDIRECT3DDEVICE9**](idirect3ddevice9.md)**

Pointer to an [**IDirect3DDevice9**](idirect3ddevice9.md) device that is used to create the output mesh.

</dd> <dt>

*pFaceRemap* \[in, out\]
</dt> <dd>

Type: **[**UINT**](winprog.windows_data_types)\***

Pointer to the original mesh face that was split to generate the current face.

</dd> <dt>

*pVertRemap* \[in, out\]
</dt> <dd>

Type: **[**UINT**](winprog.windows_data_types)\***

Pointer to a destination array containing the three original mesh vertices that are the parents of the current vertex.

</dd> <dt>

*pfVertWeights* \[in, out\]
</dt> <dd>

Type: **[**FLOAT**](winprog.windows_data_types)\***

Pointer to a destination array containing blending factors for the pVertRemap vertices.

</dd> <dt>

*ppMesh* \[out\]
</dt> <dd>

Type: **[**LPD3DXMESH**](id3dxmesh.md)\***

Pointer to the output [**ID3DXMesh**](id3dxmesh.md) mesh object.

</dd> </dl>

## Return value

Type: **[**HRESULT**](455d07e9-52c3-4efb-a9dc-2955cbfd38cc)**

If the method succeeds, the return value is S\_OK. If the method fails, the following value will be returned.D3DERR\_INVALIDCALL

## Remarks

pVertRemap and pfVertWeights can be used to interpolate any per-vertex value over the mesh.

## Requirements



|                    |                                                                                        |
|--------------------|----------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>D3DX9Mesh.h</dt> </dl> |
| Library<br/> | <dl> <dt>D3dx9.lib</dt> </dl>   |



## See also

<dl> <dt>

[ID3DXPRTEngine](id3dxprtengine.md)
</dt> </dl>

 

 



