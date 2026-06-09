# _VSS_MGMT_OBJECT_PROP_Copy::destroy_::_1_::catch$4

- ea: `0x180049db3`
- end: `0x180049e0b`
- name: `_VSS_MGMT_OBJECT_PROP_Copy::destroy_::_1_::catch$4`
- size: `88`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180035360`

## string_xrefs

- `0x180049dde`: `PRPCOPYC`
- `0x180049de5`: `base\stor\vss\modules\prop\copy.cxx`
- `0x180049dd2`: `VSS_MGMT_OBJECT_PROP_Copy::destroy`

## pseudocode

```c
void __fastcall __noreturn VSS_MGMT_OBJECT_PROP_Copy::destroy_::_1_::catch_4(__int64 a1, __int64 a2)
{
  CVssFunctionTracer::HandleComException(
    (CVssFunctionTracer *)(a2 + 96),
    *(struct _com_error **)(a2 + 80),
    L"base\\stor\\vss\\modules\\prop\\copy.cxx",
    L"PRPCOPYC",
    L"VSS_MGMT_OBJECT_PROP_Copy::destroy",
    0x17Cu,
    *(_DWORD *)(a2 + 132));
}

```

## disassembly

```asm
0x180049db3  mov     [rsp+arg_8], rdx
0x180049db8  push    rbp
0x180049db9  sub     rsp, 40h
0x180049dbd  mov     rbp, rdx
0x180049dc0  mov     eax, [rbp+84h]
0x180049dc6  mov     [rsp+48h+var_18], eax; unsigned int
0x180049dca  mov     [rsp+48h+var_20], 17Ch; unsigned int
0x180049dd2  lea     rax, aVssMgmtObjectP_4; "VSS_MGMT_OBJECT_PROP_Copy::destroy"
0x180049dd9  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x180049dde  lea     r9, aPrpcopyc; "PRPCOPYC"
0x180049de5  lea     r8, aBaseStorVssMod_17; "base\\stor\\vss\\modules\\prop\\copy.cx"...
0x180049dec  mov     rdx, [rbp+50h]; struct _com_error *
0x180049df0  lea     rcx, [rbp+60h]; this
0x180049df4  call    ?HandleComException@CVssFunctionTracer@@QEAAXAEAV_com_error@@PEBG11KK@Z; CVssFunctionTracer::HandleComException(_com_error &,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x180049dfa  mov     rax, 0
0x180049e04  add     rsp, 40h
0x180049e08  pop     rbp
0x180049e09  retn
```
