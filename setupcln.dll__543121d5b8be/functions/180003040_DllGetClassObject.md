# DllGetClassObject

- ea: `0x180003040`
- end: `0x180003045`
- name: `DllGetClassObject`
- size: `5`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800048f0`

## pseudocode

```c
// attributes: thunk
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  return CreateSetupClnClassFactory(rclsid, riid, ppv);
}

```

## disassembly

```asm
0x180003040  jmp     ?CreateSetupClnClassFactory@@YAJAEBU_GUID@@0PEAPEAX@Z; CreateSetupClnClassFactory(_GUID const &,_GUID const &,void * *)
```
