# _VSS_MGMT_OBJECT_PROP_Copy::init_::_1_::catch$3

- ea: `0x18004a03a`
- end: `0x18004a089`
- name: `_VSS_MGMT_OBJECT_PROP_Copy::init_::_1_::catch$3`
- size: `79`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x1800354e0`

## string_xrefs

- `0x18004a060`: `PRPCOPYC`
- `0x18004a067`: `base\stor\vss\modules\prop\copy.cxx`
- `0x18004a059`: `VSS_MGMT_OBJECT_PROP_Copy::init`

## pseudocode

```c
__int64 __fastcall VSS_MGMT_OBJECT_PROP_Copy::init_::_1_::catch_3(__int64 a1, __int64 a2)
{
  CVssFunctionTracer::HandleStdBadAllocException(
    (CVssFunctionTracer *)(a2 + 96),
    L"base\\stor\\vss\\modules\\prop\\copy.cxx",
    L"PRPCOPYC",
    L"VSS_MGMT_OBJECT_PROP_Copy::init",
    0x157u,
    *(_DWORD *)(a2 + 132));
  return 0;
}

```

## disassembly

```asm
0x18004a03a  mov     [rsp+arg_8], rdx
0x18004a03f  push    rbp
0x18004a040  sub     rsp, 40h
0x18004a044  mov     rbp, rdx
0x18004a047  mov     eax, [rbp+84h]
0x18004a04d  mov     [rsp+48h+var_20], eax; unsigned int
0x18004a051  mov     [rsp+48h+var_28], 157h; unsigned int
0x18004a059  lea     r9, aVssMgmtObjectP_6; "VSS_MGMT_OBJECT_PROP_Copy::init"
0x18004a060  lea     r8, aPrpcopyc; "PRPCOPYC"
0x18004a067  lea     rdx, aBaseStorVssMod_17; "base\\stor\\vss\\modules\\prop\\copy.cx"...
0x18004a06e  lea     rcx, [rbp+60h]; this
0x18004a072  call    ?HandleStdBadAllocException@CVssFunctionTracer@@QEAAXPEBG00KK@Z; CVssFunctionTracer::HandleStdBadAllocException(ushort const *,ushort const *,ushort const *,ulong,ulong)
0x18004a077  nop
0x18004a078  mov     rax, 0
0x18004a082  add     rsp, 40h
0x18004a086  pop     rbp
0x18004a087  retn
```
