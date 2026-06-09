# _VSS_MGMT_OBJECT_PROP_Copy::copyDiffArea_::_1_::catch$2

- ea: `0x1800495e0`
- end: `0x180049637`
- name: `_VSS_MGMT_OBJECT_PROP_Copy::copyDiffArea_::_1_::catch$2`
- size: `87`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x18003544c`

## string_xrefs

- `0x18004960b`: `PRPCOPYC`
- `0x180049612`: `base\stor\vss\modules\prop\copy.cxx`
- `0x1800495ff`: `VSS_MGMT_OBJECT_PROP_Copy::copyDiffArea`

## pseudocode

```c
__int64 __fastcall VSS_MGMT_OBJECT_PROP_Copy::copyDiffArea_::_1_::catch_2(__int64 a1, unsigned int *a2)
{
  CVssFunctionTracer::HandleHresultException(
    (CVssFunctionTracer *)(a2 + 24),
    a2[16],
    L"base\\stor\\vss\\modules\\prop\\copy.cxx",
    L"PRPCOPYC",
    L"VSS_MGMT_OBJECT_PROP_Copy::copyDiffArea",
    0x11Cu,
    a2[33]);
  return 0;
}

```

## disassembly

```asm
0x1800495e0  mov     [rsp+arg_8], rdx
0x1800495e5  push    rbp
0x1800495e6  sub     rsp, 40h
0x1800495ea  mov     rbp, rdx
0x1800495ed  mov     eax, [rbp+84h]
0x1800495f3  mov     [rsp+48h+var_18], eax; unsigned int
0x1800495f7  mov     [rsp+48h+var_20], 11Ch; unsigned int
0x1800495ff  lea     rax, aVssMgmtObjectP_0; "VSS_MGMT_OBJECT_PROP_Copy::copyDiffArea"
0x180049606  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x18004960b  lea     r9, aPrpcopyc; "PRPCOPYC"
0x180049612  lea     r8, aBaseStorVssMod_17; "base\\stor\\vss\\modules\\prop\\copy.cx"...
0x180049619  mov     edx, [rbp+40h]; int
0x18004961c  lea     rcx, [rbp+60h]; this
0x180049620  call    ?HandleHresultException@CVssFunctionTracer@@QEAAXJPEBG00KK@Z; CVssFunctionTracer::HandleHresultException(long,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x180049625  nop
0x180049626  mov     rax, 0
0x180049630  add     rsp, 40h
0x180049634  pop     rbp
0x180049635  retn
```
