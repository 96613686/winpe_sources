# _VSS_OBJECT_PROP_Copy::destroy_::_1_::catch$3

- ea: `0x180049ecc`
- end: `0x180049f1b`
- name: `_VSS_OBJECT_PROP_Copy::destroy_::_1_::catch$3`
- size: `79`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x1800354e0`

## string_xrefs

- `0x180049ef2`: `PRPCOPYC`
- `0x180049ef9`: `base\stor\vss\modules\prop\copy.cxx`
- `0x180049eeb`: `VSS_OBJECT_PROP_Copy::destroy`

## pseudocode

```c
__int64 __fastcall VSS_OBJECT_PROP_Copy::destroy_::_1_::catch_3(__int64 a1, __int64 a2)
{
  CVssFunctionTracer::HandleStdBadAllocException(
    (CVssFunctionTracer *)(a2 + 96),
    L"base\\stor\\vss\\modules\\prop\\copy.cxx",
    L"PRPCOPYC",
    L"VSS_OBJECT_PROP_Copy::destroy",
    0xD0u,
    *(_DWORD *)(a2 + 132));
  return 0;
}

```

## disassembly

```asm
0x180049ecc  mov     [rsp+arg_8], rdx
0x180049ed1  push    rbp
0x180049ed2  sub     rsp, 40h
0x180049ed6  mov     rbp, rdx
0x180049ed9  mov     eax, [rbp+84h]
0x180049edf  mov     [rsp+48h+var_20], eax; unsigned int
0x180049ee3  mov     [rsp+48h+var_28], 0D0h; unsigned int
0x180049eeb  lea     r9, aVssObjectPropC; "VSS_OBJECT_PROP_Copy::destroy"
0x180049ef2  lea     r8, aPrpcopyc; "PRPCOPYC"
0x180049ef9  lea     rdx, aBaseStorVssMod_17; "base\\stor\\vss\\modules\\prop\\copy.cx"...
0x180049f00  lea     rcx, [rbp+60h]; this
0x180049f04  call    ?HandleStdBadAllocException@CVssFunctionTracer@@QEAAXPEBG00KK@Z; CVssFunctionTracer::HandleStdBadAllocException(ushort const *,ushort const *,ushort const *,ulong,ulong)
0x180049f09  nop
0x180049f0a  mov     rax, 0
0x180049f14  add     rsp, 40h
0x180049f18  pop     rbp
0x180049f19  retn
```
