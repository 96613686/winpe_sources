# _VSS_MGMT_OBJECT_PROP_Copy::destroy_::_1_::catch$3

- ea: `0x180049d5e`
- end: `0x180049dad`
- name: `_VSS_MGMT_OBJECT_PROP_Copy::destroy_::_1_::catch$3`
- size: `79`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x1800354e0`

## string_xrefs

- `0x180049d84`: `PRPCOPYC`
- `0x180049d8b`: `base\stor\vss\modules\prop\copy.cxx`
- `0x180049d7d`: `VSS_MGMT_OBJECT_PROP_Copy::destroy`

## pseudocode

```c
__int64 __fastcall VSS_MGMT_OBJECT_PROP_Copy::destroy_::_1_::catch_3(__int64 a1, __int64 a2)
{
  CVssFunctionTracer::HandleStdBadAllocException(
    (CVssFunctionTracer *)(a2 + 96),
    L"base\\stor\\vss\\modules\\prop\\copy.cxx",
    L"PRPCOPYC",
    L"VSS_MGMT_OBJECT_PROP_Copy::destroy",
    0x17Cu,
    *(_DWORD *)(a2 + 132));
  return 0;
}

```

## disassembly

```asm
0x180049d5e  mov     [rsp+arg_8], rdx
0x180049d63  push    rbp
0x180049d64  sub     rsp, 40h
0x180049d68  mov     rbp, rdx
0x180049d6b  mov     eax, [rbp+84h]
0x180049d71  mov     [rsp+48h+var_20], eax; unsigned int
0x180049d75  mov     [rsp+48h+var_28], 17Ch; unsigned int
0x180049d7d  lea     r9, aVssMgmtObjectP_4; "VSS_MGMT_OBJECT_PROP_Copy::destroy"
0x180049d84  lea     r8, aPrpcopyc; "PRPCOPYC"
0x180049d8b  lea     rdx, aBaseStorVssMod_17; "base\\stor\\vss\\modules\\prop\\copy.cx"...
0x180049d92  lea     rcx, [rbp+60h]; this
0x180049d96  call    ?HandleStdBadAllocException@CVssFunctionTracer@@QEAAXPEBG00KK@Z; CVssFunctionTracer::HandleStdBadAllocException(ushort const *,ushort const *,ushort const *,ulong,ulong)
0x180049d9b  nop
0x180049d9c  mov     rax, 0
0x180049da6  add     rsp, 40h
0x180049daa  pop     rbp
0x180049dab  retn
```
