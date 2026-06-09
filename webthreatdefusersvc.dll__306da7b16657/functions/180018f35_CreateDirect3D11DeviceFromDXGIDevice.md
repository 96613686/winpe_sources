# CreateDirect3D11DeviceFromDXGIDevice

- ea: `0x180018f35`
- end: `0x180018f3b`
- name: `CreateDirect3D11DeviceFromDXGIDevice`
- size: `6`
- prototype: `HRESULT __stdcall(IDXGIDevice *dxgiDevice, IInspectable **graphicsDevice)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180014a90`

## import_xrefs

- `d3d11!CreateDirect3D11DeviceFromDXGIDevice` at `0x180018f35`

## pseudocode

```c
// attributes: thunk
HRESULT __stdcall CreateDirect3D11DeviceFromDXGIDevice(IDXGIDevice *dxgiDevice, IInspectable **graphicsDevice)
{
  return __imp_CreateDirect3D11DeviceFromDXGIDevice(dxgiDevice, graphicsDevice);
}

```

## disassembly

```asm
0x180018f35  jmp     cs:__imp_CreateDirect3D11DeviceFromDXGIDevice
```
