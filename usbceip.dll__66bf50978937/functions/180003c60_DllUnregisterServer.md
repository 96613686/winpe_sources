# DllUnregisterServer

- ea: `0x180003c60`
- end: `0x180003c65`
- name: `DllUnregisterServer`
- size: `5`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180003600`

## pseudocode

```c
// attributes: thunk
HRESULT __stdcall DllUnregisterServer()
{
  return CWinTaskModuleT<CUsbCeipTask,&_GUID const CLSID_UsbCeipTask>::DllUnregisterServer();
}

```

## disassembly

```asm
0x180003c60  jmp     ?DllUnregisterServer@?$CWinTaskModuleT@VCUsbCeipTask@@$1?CLSID_UsbCeipTask@@3U_GUID@@B@@QEAAJXZ; CWinTaskModuleT<CUsbCeipTask,&_GUID const CLSID_UsbCeipTask>::DllUnregisterServer(void)
```
