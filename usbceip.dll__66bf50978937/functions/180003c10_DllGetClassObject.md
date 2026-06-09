# DllGetClassObject

- ea: `0x180003c10`
- end: `0x180003c1e`
- name: `DllGetClassObject`
- size: `14`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180003360`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  return CWinTaskModuleT<CUsbCeipTask,&_GUID const CLSID_UsbCeipTask>::DllGetClassObject(
           (__int64)rclsid,
           rclsid,
           (__int64)riid,
           ppv);
}

```

## disassembly

```asm
0x180003c10  mov     r9, r8
0x180003c13  mov     r8, rdx
0x180003c16  mov     rdx, rcx
0x180003c19  jmp     ?DllGetClassObject@?$CWinTaskModuleT@VCUsbCeipTask@@$1?CLSID_UsbCeipTask@@3U_GUID@@B@@QEAAJAEBU_GUID@@0PEAPEAX@Z; CWinTaskModuleT<CUsbCeipTask,&_GUID const CLSID_UsbCeipTask>::DllGetClassObject(_GUID const &,_GUID const &,void * *)
```
