# _VSS_MGMT_OBJECT_PROP_Copy::copyDiffArea_::_1_::catch$4

- ea: `0x18004969b`
- end: `0x1800496ea`
- name: `_VSS_MGMT_OBJECT_PROP_Copy::copyDiffArea_::_1_::catch$4`
- size: `79`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x1800354e0`

## string_xrefs

- `0x1800496c1`: `PRPCOPYC`
- `0x1800496c8`: `base\stor\vss\modules\prop\copy.cxx`
- `0x1800496ba`: `VSS_MGMT_OBJECT_PROP_Copy::copyDiffArea`

## pseudocode

```c
__int64 __fastcall VSS_MGMT_OBJECT_PROP_Copy::copyDiffArea_::_1_::catch_4(__int64 a1, __int64 a2)
{
  CVssFunctionTracer::HandleStdBadAllocException(
    (CVssFunctionTracer *)(a2 + 96),
    L"base\\stor\\vss\\modules\\prop\\copy.cxx",
    L"PRPCOPYC",
    L"VSS_MGMT_OBJECT_PROP_Copy::copyDiffArea",
    0x11Cu,
    *(_DWORD *)(a2 + 132));
  return 0;
}

```

## disassembly

```asm
0x18004969b  mov     [rsp+arg_8], rdx
0x1800496a0  push    rbp
0x1800496a1  sub     rsp, 40h
0x1800496a5  mov     rbp, rdx
0x1800496a8  mov     eax, [rbp+84h]
0x1800496ae  mov     [rsp+48h+var_20], eax; unsigned int
0x1800496b2  mov     [rsp+48h+var_28], 11Ch; unsigned int
0x1800496ba  lea     r9, aVssMgmtObjectP_0; "VSS_MGMT_OBJECT_PROP_Copy::copyDiffArea"
0x1800496c1  lea     r8, aPrpcopyc; "PRPCOPYC"
0x1800496c8  lea     rdx, aBaseStorVssMod_17; "base\\stor\\vss\\modules\\prop\\copy.cx"...
0x1800496cf  lea     rcx, [rbp+60h]; this
0x1800496d3  call    ?HandleStdBadAllocException@CVssFunctionTracer@@QEAAXPEBG00KK@Z; CVssFunctionTracer::HandleStdBadAllocException(ushort const *,ushort const *,ushort const *,ulong,ulong)
0x1800496d8  nop
0x1800496d9  mov     rax, 0
0x1800496e3  add     rsp, 40h
0x1800496e7  pop     rbp
0x1800496e8  retn
```
