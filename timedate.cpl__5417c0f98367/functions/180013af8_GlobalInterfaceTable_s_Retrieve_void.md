# GlobalInterfaceTable::s_Retrieve(void)

- ea: `0x180013af8`
- end: `0x180013b6f`
- name: `?s_Retrieve@GlobalInterfaceTable@@CAJXZ`
- size: `119`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180012f60`
- `0x180013824`
- `0x180013880`

## callees

- `0x1800130b4`
- `0x180013af8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013b36`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013b36`

## pseudocode

```c
__int64 GlobalInterfaceTable::s_Retrieve(void)
{
  HRESULT v0; // ebx
  LPVOID ppv; // [rsp+40h] [rbp+8h] BYREF

  v0 = 0;
  if ( !GlobalInterfaceTable::s_pGlobalInterfaceTable )
  {
    ppv = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
    v0 = CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &GUID_00000146_0000_0000_c000_000000000046, &ppv);
    if ( v0 >= 0
      && !_InterlockedCompareExchange64(
            (volatile signed __int64 *)&GlobalInterfaceTable::s_pGlobalInterfaceTable,
            (signed __int64)ppv,
            0) )
    {
      ppv = 0;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  }
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x180013af8  push    rbx
0x180013afa  sub     rsp, 30h
0x180013afe  xor     ebx, ebx
0x180013b00  cmp     cs:?s_pGlobalInterfaceTable@GlobalInterfaceTable@@0PEAUIGlobalInterfaceTable@@EA, rbx; IGlobalInterfaceTable * GlobalInterfaceTable::s_pGlobalInterfaceTable
0x180013b07  jnz     short loc_180013B67
0x180013b09  lea     rcx, [rsp+38h+arg_0]
0x180013b0e  mov     [rsp+38h+arg_0], rbx
0x180013b13  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013b18  lea     rax, [rsp+38h+arg_0]
0x180013b1d  xor     edx, edx; pUnkOuter
0x180013b1f  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180013b26  mov     [rsp+38h+ppv], rax; ppv
0x180013b2b  lea     r8d, [rbx+1]; dwClsContext
0x180013b2f  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180013b36  call    cs:__imp_CoCreateInstance
0x180013b3c  mov     ebx, eax
0x180013b3e  test    eax, eax
0x180013b40  js      short loc_180013B5D
0x180013b42  mov     rcx, [rsp+38h+arg_0]
0x180013b47  xor     eax, eax
0x180013b49  lock cmpxchg cs:?s_pGlobalInterfaceTable@GlobalInterfaceTable@@0PEAUIGlobalInterfaceTable@@EA, rcx; IGlobalInterfaceTable * GlobalInterfaceTable::s_pGlobalInterfaceTable
0x180013b52  jnz     short loc_180013B5D
0x180013b54  mov     [rsp+38h+arg_0], 0
0x180013b5d  lea     rcx, [rsp+38h+arg_0]
0x180013b62  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013b67  mov     eax, ebx
0x180013b69  add     rsp, 30h
0x180013b6d  pop     rbx
0x180013b6e  retn
```
