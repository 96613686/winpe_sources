# _VSS_MGMT_OBJECT_PROP_Copy::init_::_1_::catch$4

- ea: `0x18004a08f`
- end: `0x18004a0e7`
- name: `_VSS_MGMT_OBJECT_PROP_Copy::init_::_1_::catch$4`
- size: `88`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180035360`

## string_xrefs

- `0x18004a0ba`: `PRPCOPYC`
- `0x18004a0c1`: `base\stor\vss\modules\prop\copy.cxx`
- `0x18004a0ae`: `VSS_MGMT_OBJECT_PROP_Copy::init`

## pseudocode

```c
void __fastcall __noreturn VSS_MGMT_OBJECT_PROP_Copy::init_::_1_::catch_4(__int64 a1, __int64 a2)
{
  CVssFunctionTracer::HandleComException(
    (CVssFunctionTracer *)(a2 + 96),
    *(struct _com_error **)(a2 + 80),
    L"base\\stor\\vss\\modules\\prop\\copy.cxx",
    L"PRPCOPYC",
    L"VSS_MGMT_OBJECT_PROP_Copy::init",
    0x157u,
    *(_DWORD *)(a2 + 132));
}

```

## disassembly

```asm
0x18004a08f  mov     [rsp+arg_8], rdx
0x18004a094  push    rbp
0x18004a095  sub     rsp, 40h
0x18004a099  mov     rbp, rdx
0x18004a09c  mov     eax, [rbp+84h]
0x18004a0a2  mov     [rsp+48h+var_18], eax; unsigned int
0x18004a0a6  mov     [rsp+48h+var_20], 157h; unsigned int
0x18004a0ae  lea     rax, aVssMgmtObjectP_6; "VSS_MGMT_OBJECT_PROP_Copy::init"
0x18004a0b5  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x18004a0ba  lea     r9, aPrpcopyc; "PRPCOPYC"
0x18004a0c1  lea     r8, aBaseStorVssMod_17; "base\\stor\\vss\\modules\\prop\\copy.cx"...
0x18004a0c8  mov     rdx, [rbp+50h]; struct _com_error *
0x18004a0cc  lea     rcx, [rbp+60h]; this
0x18004a0d0  call    ?HandleComException@CVssFunctionTracer@@QEAAXAEAV_com_error@@PEBG11KK@Z; CVssFunctionTracer::HandleComException(_com_error &,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x18004a0d6  mov     rax, 0
0x18004a0e0  add     rsp, 40h
0x18004a0e4  pop     rbp
0x18004a0e5  retn
```
