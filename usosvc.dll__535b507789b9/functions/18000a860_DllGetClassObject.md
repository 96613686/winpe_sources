# DllGetClassObject

- ea: `0x18000a860`
- end: `0x18000a877`
- name: `DllGetClassObject`
- size: `23`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000a860`
- `0x18000f010`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  if ( g_DllGetClassObject )
    return g_DllGetClassObject(rclsid, riid, ppv);
  else
    return -2147467259;
}

```

## disassembly

```asm
0x18000a860  mov     rax, cs:?g_DllGetClassObject@@3P6AJAEBU_GUID@@0PEAPEAX@ZEA; long (*g_DllGetClassObject)(_GUID const &,_GUID const &,void * *)
0x18000a867  test    rax, rax
0x18000a86a  jnz     short loc_18000A872
0x18000a86c  mov     eax, 80004005h
0x18000a871  retn
0x18000a872  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
