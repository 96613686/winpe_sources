# _CSrmRegistryKey::Close_::_1_::catch$6

- ea: `0x18001f132`
- end: `0x18001f184`
- name: `_CSrmRegistryKey::Close_::_1_::catch$6`
- size: `82`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180017c5c`

## string_xrefs

- `0x18001f15f`: `base\fs\fsrm\utilities\registry\srmreg.cpp`
- `0x18001f151`: `CSrmRegistryKey::Close`

## pseudocode

```c
__int64 __fastcall CSrmRegistryKey::Close_::_1_::catch_6(__int64 a1, __int64 a2)
{
  CSrmFunctionTracer::HandleStdBadAllocException(
    (CSrmFunctionTracer *)(a2 + 384),
    L"base\\fs\\fsrm\\utilities\\registry\\srmreg.cpp",
    L"SRMREGSC",
    L"CSrmRegistryKey::Close",
    0x373u,
    *(_DWORD *)(a2 + 428));
  return 0;
}

```

## disassembly

```asm
0x18001f132  mov     [rsp+arg_8], rdx
0x18001f137  push    rbp
0x18001f138  sub     rsp, 40h
0x18001f13c  mov     rbp, rdx
0x18001f13f  mov     eax, [rbp+1ACh]
0x18001f145  mov     [rsp+48h+var_20], eax; unsigned int
0x18001f149  mov     [rsp+48h+var_28], 373h; unsigned int
0x18001f151  lea     r9, aCsrmregistryke_0; "CSrmRegistryKey::Close"
0x18001f158  lea     r8, aSrmregsc; "SRMREGSC"
0x18001f15f  lea     rdx, aBaseFsFsrmUtil_3; "base\\fs\\fsrm\\utilities\\registry\\sr"...
0x18001f166  lea     rcx, [rbp+180h]; this
0x18001f16d  call    ?HandleStdBadAllocException@CSrmFunctionTracer@@QEAAXPEBG00KK@Z; CSrmFunctionTracer::HandleStdBadAllocException(ushort const *,ushort const *,ushort const *,ulong,ulong)
0x18001f172  nop
0x18001f173  mov     rax, 0
0x18001f17d  add     rsp, 40h
0x18001f181  pop     rbp
0x18001f182  retn
```
