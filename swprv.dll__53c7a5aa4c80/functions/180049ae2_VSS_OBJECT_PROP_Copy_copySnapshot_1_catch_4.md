# _VSS_OBJECT_PROP_Copy::copySnapshot_::_1_::catch$4

- ea: `0x180049ae2`
- end: `0x180049b2e`
- name: `_VSS_OBJECT_PROP_Copy::copySnapshot_::_1_::catch$4`
- size: `76`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x1800354e0`

## string_xrefs

- `0x180049afe`: `VSS_OBJECT_PROP_Copy::copySnapshot`
- `0x180049b05`: `PRPCOPYC`
- `0x180049b0c`: `base\stor\vss\modules\prop\copy.cxx`

## pseudocode

```c
__int64 __fastcall VSS_OBJECT_PROP_Copy::copySnapshot_::_1_::catch_4(__int64 a1, __int64 a2)
{
  CVssFunctionTracer::HandleStdBadAllocException(
    (CVssFunctionTracer *)(a2 + 80),
    L"base\\stor\\vss\\modules\\prop\\copy.cxx",
    L"PRPCOPYC",
    L"VSS_OBJECT_PROP_Copy::copySnapshot",
    0x5Au,
    *(_DWORD *)(a2 + 116));
  return 0;
}

```

## disassembly

```asm
0x180049ae2  mov     [rsp+arg_8], rdx
0x180049ae7  push    rbp
0x180049ae8  sub     rsp, 40h
0x180049aec  mov     rbp, rdx
0x180049aef  mov     eax, [rbp+74h]
0x180049af2  mov     [rsp+48h+var_20], eax; unsigned int
0x180049af6  mov     [rsp+48h+var_28], 5Ah ; 'Z'; unsigned int
0x180049afe  lea     r9, aVssObjectPropC_1; "VSS_OBJECT_PROP_Copy::copySnapshot"
0x180049b05  lea     r8, aPrpcopyc; "PRPCOPYC"
0x180049b0c  lea     rdx, aBaseStorVssMod_17; "base\\stor\\vss\\modules\\prop\\copy.cx"...
0x180049b13  lea     rcx, [rbp+50h]; this
0x180049b17  call    ?HandleStdBadAllocException@CVssFunctionTracer@@QEAAXPEBG00KK@Z; CVssFunctionTracer::HandleStdBadAllocException(ushort const *,ushort const *,ushort const *,ulong,ulong)
0x180049b1c  nop
0x180049b1d  mov     rax, 0
0x180049b27  add     rsp, 40h
0x180049b2b  pop     rbp
0x180049b2c  retn
```
