# _CSrmRegistryKey::Close_::_1_::catch$7

- ea: `0x18001f18a`
- end: `0x18001f1e5`
- name: `_CSrmRegistryKey::Close_::_1_::catch$7`
- size: `91`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180017ce8`

## string_xrefs

- `0x18001f1bc`: `base\fs\fsrm\utilities\registry\srmreg.cpp`
- `0x18001f1a9`: `CSrmRegistryKey::Close`

## pseudocode

```c
void __fastcall __noreturn CSrmRegistryKey::Close_::_1_::catch_7(__int64 a1, __int64 a2)
{
  CSrmFunctionTracer::HandleStdGenericException(
    (CSrmFunctionTracer *)(a2 + 384),
    *(const struct exception **)(a2 + 88),
    L"base\\fs\\fsrm\\utilities\\registry\\srmreg.cpp",
    L"SRMREGSC",
    L"CSrmRegistryKey::Close",
    0x373u,
    *(_DWORD *)(a2 + 428));
}

```

## disassembly

```asm
0x18001f18a  mov     [rsp+arg_8], rdx
0x18001f18f  push    rbp
0x18001f190  sub     rsp, 40h
0x18001f194  mov     rbp, rdx
0x18001f197  mov     eax, [rbp+1ACh]
0x18001f19d  mov     [rsp+48h+var_18], eax; unsigned int
0x18001f1a1  mov     [rsp+48h+var_20], 373h; unsigned int
0x18001f1a9  lea     rax, aCsrmregistryke_0; "CSrmRegistryKey::Close"
0x18001f1b0  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x18001f1b5  lea     r9, aSrmregsc; "SRMREGSC"
0x18001f1bc  lea     r8, aBaseFsFsrmUtil_3; "base\\fs\\fsrm\\utilities\\registry\\sr"...
0x18001f1c3  mov     rdx, [rbp+58h]; struct exception *
0x18001f1c7  lea     rcx, [rbp+180h]; this
0x18001f1ce  call    ?HandleStdGenericException@CSrmFunctionTracer@@QEAAXAEBVexception@@PEBG11KK@Z; CSrmFunctionTracer::HandleStdGenericException(exception const &,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x18001f1d4  mov     rax, 0
0x18001f1de  add     rsp, 40h
0x18001f1e2  pop     rbp
0x18001f1e3  retn
```
