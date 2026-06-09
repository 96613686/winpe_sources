# ATL::AtlGetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x180020bac`
- end: `0x180020c05`
- name: `?AtlGetGITPtr@ATL@@YAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `89`
- prototype: `__int64 __fastcall(LPVOID *ppv)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180022488`
- `0x180023550`
- `0x180023e18`
- `0x180023f10`

## callees

- `0x180020bac`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180020be4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180020be4`

## pseudocode

```c
HRESULT __fastcall ATL::AtlGetGITPtr(LPVOID *ppv)
{
  if ( !ppv )
    return -2147467261;
  if ( ATL::_pAtlModule )
    return (*(__int64 (__fastcall **)(struct ATL::CAtlModule *, LPVOID *))(*(_QWORD *)ATL::_pAtlModule + 32LL))(
             ATL::_pAtlModule,
             ppv);
  return CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &GUID_00000146_0000_0000_c000_000000000046, ppv);
}

```

## disassembly

```asm
0x180020bac  sub     rsp, 38h
0x180020bb0  test    rcx, rcx
0x180020bb3  jnz     short loc_180020BBF
0x180020bb5  mov     eax, 80004003h
0x180020bba  add     rsp, 38h
0x180020bbe  retn
0x180020bbf  mov     r8, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180020bc6  test    r8, r8
0x180020bc9  jnz     short loc_180020BEF
0x180020bcb  xor     edx, edx; pUnkOuter
0x180020bcd  mov     [rsp+38h+ppv], rcx; ppv
0x180020bd2  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180020bd9  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180020be0  lea     r8d, [rdx+1]; dwClsContext
0x180020be4  call    cs:__imp_CoCreateInstance
0x180020bea  add     rsp, 38h
0x180020bee  retn
0x180020bef  mov     rax, [r8]
0x180020bf2  mov     rdx, rcx
0x180020bf5  mov     rcx, r8
0x180020bf8  mov     rax, [rax+20h]
0x180020bfc  add     rsp, 38h
0x180020c00  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
