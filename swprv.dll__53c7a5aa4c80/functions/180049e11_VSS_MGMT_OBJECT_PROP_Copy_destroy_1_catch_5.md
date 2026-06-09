# _VSS_MGMT_OBJECT_PROP_Copy::destroy_::_1_::catch$5

- ea: `0x180049e11`
- end: `0x180049e68`
- name: `_VSS_MGMT_OBJECT_PROP_Copy::destroy_::_1_::catch$5`
- size: `87`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x18003544c`

## string_xrefs

- `0x180049e3c`: `PRPCOPYC`
- `0x180049e43`: `base\stor\vss\modules\prop\copy.cxx`
- `0x180049e30`: `VSS_MGMT_OBJECT_PROP_Copy::destroy`

## pseudocode

```c
__int64 __fastcall VSS_MGMT_OBJECT_PROP_Copy::destroy_::_1_::catch_5(__int64 a1, unsigned int *a2)
{
  CVssFunctionTracer::HandleHresultException(
    (CVssFunctionTracer *)(a2 + 24),
    a2[16],
    L"base\\stor\\vss\\modules\\prop\\copy.cxx",
    L"PRPCOPYC",
    L"VSS_MGMT_OBJECT_PROP_Copy::destroy",
    0x17Cu,
    a2[33]);
  return 0;
}

```

## disassembly

```asm
0x180049e11  mov     [rsp+arg_8], rdx
0x180049e16  push    rbp
0x180049e17  sub     rsp, 40h
0x180049e1b  mov     rbp, rdx
0x180049e1e  mov     eax, [rbp+84h]
0x180049e24  mov     [rsp+48h+var_18], eax; unsigned int
0x180049e28  mov     [rsp+48h+var_20], 17Ch; unsigned int
0x180049e30  lea     rax, aVssMgmtObjectP_4; "VSS_MGMT_OBJECT_PROP_Copy::destroy"
0x180049e37  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x180049e3c  lea     r9, aPrpcopyc; "PRPCOPYC"
0x180049e43  lea     r8, aBaseStorVssMod_17; "base\\stor\\vss\\modules\\prop\\copy.cx"...
0x180049e4a  mov     edx, [rbp+40h]; int
0x180049e4d  lea     rcx, [rbp+60h]; this
0x180049e51  call    ?HandleHresultException@CVssFunctionTracer@@QEAAXJPEBG00KK@Z; CVssFunctionTracer::HandleHresultException(long,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x180049e56  nop
0x180049e57  mov     rax, 0
0x180049e61  add     rsp, 40h
0x180049e65  pop     rbp
0x180049e66  retn
```
