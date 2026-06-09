# _CSrmRegistryKey::Close_::_1_::catch$4

- ea: `0x18001f071`
- end: `0x18001f0cb`
- name: `_CSrmRegistryKey::Close_::_1_::catch$4`
- size: `90`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180017bc8`

## string_xrefs

- `0x18001f0a3`: `base\fs\fsrm\utilities\registry\srmreg.cpp`
- `0x18001f090`: `CSrmRegistryKey::Close`

## pseudocode

```c
__int64 __fastcall CSrmRegistryKey::Close_::_1_::catch_4(__int64 a1, unsigned int *a2)
{
  CSrmFunctionTracer::HandleHresultException(
    (CSrmFunctionTracer *)(a2 + 96),
    a2[17],
    L"base\\fs\\fsrm\\utilities\\registry\\srmreg.cpp",
    L"SRMREGSC",
    L"CSrmRegistryKey::Close",
    0x373u,
    a2[107]);
  return 0;
}

```

## disassembly

```asm
0x18001f071  mov     [rsp+arg_8], rdx
0x18001f076  push    rbp
0x18001f077  sub     rsp, 40h
0x18001f07b  mov     rbp, rdx
0x18001f07e  mov     eax, [rbp+1ACh]
0x18001f084  mov     [rsp+48h+var_18], eax; unsigned int
0x18001f088  mov     [rsp+48h+var_20], 373h; unsigned int
0x18001f090  lea     rax, aCsrmregistryke_0; "CSrmRegistryKey::Close"
0x18001f097  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x18001f09c  lea     r9, aSrmregsc; "SRMREGSC"
0x18001f0a3  lea     r8, aBaseFsFsrmUtil_3; "base\\fs\\fsrm\\utilities\\registry\\sr"...
0x18001f0aa  mov     edx, [rbp+44h]; int
0x18001f0ad  lea     rcx, [rbp+180h]; this
0x18001f0b4  call    ?HandleHresultException@CSrmFunctionTracer@@QEAAXJPEBG00KK@Z; CSrmFunctionTracer::HandleHresultException(long,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x18001f0b9  nop
0x18001f0ba  mov     rax, 0
0x18001f0c4  add     rsp, 40h
0x18001f0c8  pop     rbp
0x18001f0c9  retn
```
