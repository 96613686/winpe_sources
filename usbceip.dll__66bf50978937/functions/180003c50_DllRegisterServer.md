# DllRegisterServer

- ea: `0x180003c50`
- end: `0x180003c55`
- name: `DllRegisterServer`
- size: `5`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180003414`

## pseudocode

```c
// attributes: thunk
HRESULT __stdcall DllRegisterServer()
{
  return CWinTaskModuleT<CUsbCeipTask,&_GUID const CLSID_UsbCeipTask>::DllRegisterServer();
}

```

## disassembly

```asm
0x180003c50  jmp     ?DllRegisterServer@?$CWinTaskModuleT@VCUsbCeipTask@@$1?CLSID_UsbCeipTask@@3U_GUID@@B@@QEAAJXZ; CWinTaskModuleT<CUsbCeipTask,&_GUID const CLSID_UsbCeipTask>::DllRegisterServer(void)
```
