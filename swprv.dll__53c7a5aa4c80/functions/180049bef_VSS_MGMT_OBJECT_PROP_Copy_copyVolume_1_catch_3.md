# _VSS_MGMT_OBJECT_PROP_Copy::copyVolume_::_1_::catch$3

- ea: `0x180049bef`
- end: `0x180049c47`
- name: `_VSS_MGMT_OBJECT_PROP_Copy::copyVolume_::_1_::catch$3`
- size: `88`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180035360`

## string_xrefs

- `0x180049c1a`: `PRPCOPYC`
- `0x180049c21`: `base\stor\vss\modules\prop\copy.cxx`
- `0x180049c0e`: `VSS_MGMT_OBJECT_PROP_Copy::copyVolume`

## pseudocode

```c
void __fastcall __noreturn VSS_MGMT_OBJECT_PROP_Copy::copyVolume_::_1_::catch_3(__int64 a1, __int64 a2)
{
  CVssFunctionTracer::HandleComException(
    (CVssFunctionTracer *)(a2 + 96),
    *(struct _com_error **)(a2 + 72),
    L"base\\stor\\vss\\modules\\prop\\copy.cxx",
    L"PRPCOPYC",
    L"VSS_MGMT_OBJECT_PROP_Copy::copyVolume",
    0xE9u,
    *(_DWORD *)(a2 + 132));
}

```

## disassembly

```asm
0x180049bef  mov     [rsp+arg_8], rdx
0x180049bf4  push    rbp
0x180049bf5  sub     rsp, 40h
0x180049bf9  mov     rbp, rdx
0x180049bfc  mov     eax, [rbp+84h]
0x180049c02  mov     [rsp+48h+var_18], eax; unsigned int
0x180049c06  mov     [rsp+48h+var_20], 0E9h; unsigned int
0x180049c0e  lea     rax, aVssMgmtObjectP_2; "VSS_MGMT_OBJECT_PROP_Copy::copyVolume"
0x180049c15  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x180049c1a  lea     r9, aPrpcopyc; "PRPCOPYC"
0x180049c21  lea     r8, aBaseStorVssMod_17; "base\\stor\\vss\\modules\\prop\\copy.cx"...
0x180049c28  mov     rdx, [rbp+48h]; struct _com_error *
0x180049c2c  lea     rcx, [rbp+60h]; this
0x180049c30  call    ?HandleComException@CVssFunctionTracer@@QEAAXAEAV_com_error@@PEBG11KK@Z; CVssFunctionTracer::HandleComException(_com_error &,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x180049c36  mov     rax, 0
0x180049c40  add     rsp, 40h
0x180049c44  pop     rbp
0x180049c45  retn
```
