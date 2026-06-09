# _VSS_MGMT_OBJECT_PROP_Copy::copyVolume_::_1_::catch$2

- ea: `0x180049b92`
- end: `0x180049be9`
- name: `_VSS_MGMT_OBJECT_PROP_Copy::copyVolume_::_1_::catch$2`
- size: `87`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x18003544c`

## string_xrefs

- `0x180049bbd`: `PRPCOPYC`
- `0x180049bc4`: `base\stor\vss\modules\prop\copy.cxx`
- `0x180049bb1`: `VSS_MGMT_OBJECT_PROP_Copy::copyVolume`

## pseudocode

```c
__int64 __fastcall VSS_MGMT_OBJECT_PROP_Copy::copyVolume_::_1_::catch_2(__int64 a1, unsigned int *a2)
{
  CVssFunctionTracer::HandleHresultException(
    (CVssFunctionTracer *)(a2 + 24),
    a2[16],
    L"base\\stor\\vss\\modules\\prop\\copy.cxx",
    L"PRPCOPYC",
    L"VSS_MGMT_OBJECT_PROP_Copy::copyVolume",
    0xE9u,
    a2[33]);
  return 0;
}

```

## disassembly

```asm
0x180049b92  mov     [rsp+arg_8], rdx
0x180049b97  push    rbp
0x180049b98  sub     rsp, 40h
0x180049b9c  mov     rbp, rdx
0x180049b9f  mov     eax, [rbp+84h]
0x180049ba5  mov     [rsp+48h+var_18], eax; unsigned int
0x180049ba9  mov     [rsp+48h+var_20], 0E9h; unsigned int
0x180049bb1  lea     rax, aVssMgmtObjectP_2; "VSS_MGMT_OBJECT_PROP_Copy::copyVolume"
0x180049bb8  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x180049bbd  lea     r9, aPrpcopyc; "PRPCOPYC"
0x180049bc4  lea     r8, aBaseStorVssMod_17; "base\\stor\\vss\\modules\\prop\\copy.cx"...
0x180049bcb  mov     edx, [rbp+40h]; int
0x180049bce  lea     rcx, [rbp+60h]; this
0x180049bd2  call    ?HandleHresultException@CVssFunctionTracer@@QEAAXJPEBG00KK@Z; CVssFunctionTracer::HandleHresultException(long,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x180049bd7  nop
0x180049bd8  mov     rax, 0
0x180049be2  add     rsp, 40h
0x180049be6  pop     rbp
0x180049be7  retn
```
