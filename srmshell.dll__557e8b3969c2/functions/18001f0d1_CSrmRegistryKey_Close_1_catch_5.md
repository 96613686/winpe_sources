# _CSrmRegistryKey::Close_::_1_::catch$5

- ea: `0x18001f0d1`
- end: `0x18001f12c`
- name: `_CSrmRegistryKey::Close_::_1_::catch$5`
- size: `91`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180017ad0`

## string_xrefs

- `0x18001f103`: `base\fs\fsrm\utilities\registry\srmreg.cpp`
- `0x18001f0f0`: `CSrmRegistryKey::Close`

## pseudocode

```c
void __fastcall __noreturn CSrmRegistryKey::Close_::_1_::catch_5(__int64 a1, __int64 a2)
{
  CSrmFunctionTracer::HandleComException(
    (CSrmFunctionTracer *)(a2 + 384),
    *(struct _com_error **)(a2 + 80),
    L"base\\fs\\fsrm\\utilities\\registry\\srmreg.cpp",
    L"SRMREGSC",
    L"CSrmRegistryKey::Close",
    0x373u,
    *(_DWORD *)(a2 + 428));
}

```

## disassembly

```asm
0x18001f0d1  mov     [rsp+arg_8], rdx
0x18001f0d6  push    rbp
0x18001f0d7  sub     rsp, 40h
0x18001f0db  mov     rbp, rdx
0x18001f0de  mov     eax, [rbp+1ACh]
0x18001f0e4  mov     [rsp+48h+var_18], eax; unsigned int
0x18001f0e8  mov     [rsp+48h+var_20], 373h; unsigned int
0x18001f0f0  lea     rax, aCsrmregistryke_0; "CSrmRegistryKey::Close"
0x18001f0f7  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x18001f0fc  lea     r9, aSrmregsc; "SRMREGSC"
0x18001f103  lea     r8, aBaseFsFsrmUtil_3; "base\\fs\\fsrm\\utilities\\registry\\sr"...
0x18001f10a  mov     rdx, [rbp+50h]; struct _com_error *
0x18001f10e  lea     rcx, [rbp+180h]; this
0x18001f115  call    ?HandleComException@CSrmFunctionTracer@@QEAAXAEAV_com_error@@PEBG11KK@Z; CSrmFunctionTracer::HandleComException(_com_error &,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x18001f11b  mov     rax, 0
0x18001f125  add     rsp, 40h
0x18001f129  pop     rbp
0x18001f12a  retn
```
