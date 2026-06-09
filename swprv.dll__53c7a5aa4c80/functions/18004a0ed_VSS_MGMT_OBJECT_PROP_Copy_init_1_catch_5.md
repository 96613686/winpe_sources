# _VSS_MGMT_OBJECT_PROP_Copy::init_::_1_::catch$5

- ea: `0x18004a0ed`
- end: `0x18004a144`
- name: `_VSS_MGMT_OBJECT_PROP_Copy::init_::_1_::catch$5`
- size: `87`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x18003544c`

## string_xrefs

- `0x18004a118`: `PRPCOPYC`
- `0x18004a11f`: `base\stor\vss\modules\prop\copy.cxx`
- `0x18004a10c`: `VSS_MGMT_OBJECT_PROP_Copy::init`

## pseudocode

```c
__int64 __fastcall VSS_MGMT_OBJECT_PROP_Copy::init_::_1_::catch_5(__int64 a1, unsigned int *a2)
{
  CVssFunctionTracer::HandleHresultException(
    (CVssFunctionTracer *)(a2 + 24),
    a2[16],
    L"base\\stor\\vss\\modules\\prop\\copy.cxx",
    L"PRPCOPYC",
    L"VSS_MGMT_OBJECT_PROP_Copy::init",
    0x157u,
    a2[33]);
  return 0;
}

```

## disassembly

```asm
0x18004a0ed  mov     [rsp+arg_8], rdx
0x18004a0f2  push    rbp
0x18004a0f3  sub     rsp, 40h
0x18004a0f7  mov     rbp, rdx
0x18004a0fa  mov     eax, [rbp+84h]
0x18004a100  mov     [rsp+48h+var_18], eax; unsigned int
0x18004a104  mov     [rsp+48h+var_20], 157h; unsigned int
0x18004a10c  lea     rax, aVssMgmtObjectP_6; "VSS_MGMT_OBJECT_PROP_Copy::init"
0x18004a113  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x18004a118  lea     r9, aPrpcopyc; "PRPCOPYC"
0x18004a11f  lea     r8, aBaseStorVssMod_17; "base\\stor\\vss\\modules\\prop\\copy.cx"...
0x18004a126  mov     edx, [rbp+40h]; int
0x18004a129  lea     rcx, [rbp+60h]; this
0x18004a12d  call    ?HandleHresultException@CVssFunctionTracer@@QEAAXJPEBG00KK@Z; CVssFunctionTracer::HandleHresultException(long,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x18004a132  nop
0x18004a133  mov     rax, 0
0x18004a13d  add     rsp, 40h
0x18004a141  pop     rbp
0x18004a142  retn
```
