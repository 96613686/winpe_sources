# DllGetClassObject

- ea: `0x1800066a0`
- end: `0x1800066d8`
- name: `DllGetClassObject`
- size: `56`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000478c`
- `0x1800066a0`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  if ( !ppv )
    return -2147024809;
  *ppv = 0;
  if ( qword_18001E3A8 )
    return ATL::CComModule::GetClassObject((ATL::CComModule *)&_Module, rclsid, riid, ppv);
  else
    return -2147467259;
}

```

## disassembly

```asm
0x1800066a0  test    r8, r8
0x1800066a3  jnz     short loc_1800066AC
0x1800066a5  mov     eax, 80070057h
0x1800066aa  jmp     short locret_1800066D7
0x1800066ac  mov     qword ptr [r8], 0
0x1800066b3  cmp     cs:qword_18001E3A8, 0
0x1800066bb  jz      short loc_1800066D2
0x1800066bd  mov     r9, r8; void **
0x1800066c0  mov     r8, rdx; struct _GUID *
0x1800066c3  mov     rdx, rcx; struct _GUID *
0x1800066c6  lea     rcx, ?_Module@@3VCComModule@ATL@@A; this
0x1800066cd  jmp     ?GetClassObject@CComModule@ATL@@QEAAJAEBU_GUID@@0PEAPEAX@Z; ATL::CComModule::GetClassObject(_GUID const &,_GUID const &,void * *)
0x1800066d2  mov     eax, 80004005h
0x1800066d7  retn
```
