# _VSS_OBJECT_PROP_Copy::copyProvider_::_1_::catch$4

- ea: `0x180049977`
- end: `0x1800499c6`
- name: `_VSS_OBJECT_PROP_Copy::copyProvider_::_1_::catch$4`
- size: `79`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x1800354e0`

## string_xrefs

- `0x18004999d`: `PRPCOPYC`
- `0x1800499a4`: `base\stor\vss\modules\prop\copy.cxx`
- `0x180049996`: `VSS_OBJECT_PROP_Copy::copyProvider`

## pseudocode

```c
__int64 __fastcall VSS_OBJECT_PROP_Copy::copyProvider_::_1_::catch_4(__int64 a1, __int64 a2)
{
  CVssFunctionTracer::HandleStdBadAllocException(
    (CVssFunctionTracer *)(a2 + 96),
    L"base\\stor\\vss\\modules\\prop\\copy.cxx",
    L"PRPCOPYC",
    L"VSS_OBJECT_PROP_Copy::copyProvider",
    0x75u,
    *(_DWORD *)(a2 + 132));
  return 0;
}

```

## disassembly

```asm
0x180049977  mov     [rsp+arg_8], rdx
0x18004997c  push    rbp
0x18004997d  sub     rsp, 40h
0x180049981  mov     rbp, rdx
0x180049984  mov     eax, [rbp+84h]
0x18004998a  mov     [rsp+48h+var_20], eax; unsigned int
0x18004998e  mov     [rsp+48h+var_28], 75h ; 'u'; unsigned int
0x180049996  lea     r9, aVssObjectPropC_2; "VSS_OBJECT_PROP_Copy::copyProvider"
0x18004999d  lea     r8, aPrpcopyc; "PRPCOPYC"
0x1800499a4  lea     rdx, aBaseStorVssMod_17; "base\\stor\\vss\\modules\\prop\\copy.cx"...
0x1800499ab  lea     rcx, [rbp+60h]; this
0x1800499af  call    ?HandleStdBadAllocException@CVssFunctionTracer@@QEAAXPEBG00KK@Z; CVssFunctionTracer::HandleStdBadAllocException(ushort const *,ushort const *,ushort const *,ulong,ulong)
0x1800499b4  nop
0x1800499b5  mov     rax, 0
0x1800499bf  add     rsp, 40h
0x1800499c3  pop     rbp
0x1800499c4  retn
```
