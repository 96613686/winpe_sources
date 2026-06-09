# _VSS_MGMT_OBJECT_PROP_Copy::copyDiffVolume_::_1_::catch$2

- ea: `0x18004974e`
- end: `0x1800497a5`
- name: `_VSS_MGMT_OBJECT_PROP_Copy::copyDiffVolume_::_1_::catch$2`
- size: `87`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x18003544c`

## string_xrefs

- `0x180049779`: `PRPCOPYC`
- `0x180049780`: `base\stor\vss\modules\prop\copy.cxx`
- `0x18004976d`: `VSS_MGMT_OBJECT_PROP_Copy::copyDiffVolume`

## pseudocode

```c
__int64 __fastcall VSS_MGMT_OBJECT_PROP_Copy::copyDiffVolume_::_1_::catch_2(__int64 a1, unsigned int *a2)
{
  CVssFunctionTracer::HandleHresultException(
    (CVssFunctionTracer *)(a2 + 24),
    a2[16],
    L"base\\stor\\vss\\modules\\prop\\copy.cxx",
    L"PRPCOPYC",
    L"VSS_MGMT_OBJECT_PROP_Copy::copyDiffVolume",
    0x102u,
    a2[33]);
  return 0;
}

```

## disassembly

```asm
0x18004974e  mov     [rsp+arg_8], rdx
0x180049753  push    rbp
0x180049754  sub     rsp, 40h
0x180049758  mov     rbp, rdx
0x18004975b  mov     eax, [rbp+84h]
0x180049761  mov     [rsp+48h+var_18], eax; unsigned int
0x180049765  mov     [rsp+48h+var_20], 102h; unsigned int
0x18004976d  lea     rax, aVssMgmtObjectP_1; "VSS_MGMT_OBJECT_PROP_Copy::copyDiffVolu"...
0x180049774  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x180049779  lea     r9, aPrpcopyc; "PRPCOPYC"
0x180049780  lea     r8, aBaseStorVssMod_17; "base\\stor\\vss\\modules\\prop\\copy.cx"...
0x180049787  mov     edx, [rbp+40h]; int
0x18004978a  lea     rcx, [rbp+60h]; this
0x18004978e  call    ?HandleHresultException@CVssFunctionTracer@@QEAAXJPEBG00KK@Z; CVssFunctionTracer::HandleHresultException(long,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x180049793  nop
0x180049794  mov     rax, 0
0x18004979e  add     rsp, 40h
0x1800497a2  pop     rbp
0x1800497a3  retn
```
