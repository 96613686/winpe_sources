# _VSS_OBJECT_PROP_Copy::destroy_::_1_::catch$4

- ea: `0x180049f21`
- end: `0x180049f79`
- name: `_VSS_OBJECT_PROP_Copy::destroy_::_1_::catch$4`
- size: `88`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180035360`

## string_xrefs

- `0x180049f4c`: `PRPCOPYC`
- `0x180049f53`: `base\stor\vss\modules\prop\copy.cxx`
- `0x180049f40`: `VSS_OBJECT_PROP_Copy::destroy`

## pseudocode

```c
void __fastcall __noreturn VSS_OBJECT_PROP_Copy::destroy_::_1_::catch_4(__int64 a1, __int64 a2)
{
  CVssFunctionTracer::HandleComException(
    (CVssFunctionTracer *)(a2 + 96),
    *(struct _com_error **)(a2 + 80),
    L"base\\stor\\vss\\modules\\prop\\copy.cxx",
    L"PRPCOPYC",
    L"VSS_OBJECT_PROP_Copy::destroy",
    0xD0u,
    *(_DWORD *)(a2 + 132));
}

```

## disassembly

```asm
0x180049f21  mov     [rsp+arg_8], rdx
0x180049f26  push    rbp
0x180049f27  sub     rsp, 40h
0x180049f2b  mov     rbp, rdx
0x180049f2e  mov     eax, [rbp+84h]
0x180049f34  mov     [rsp+48h+var_18], eax; unsigned int
0x180049f38  mov     [rsp+48h+var_20], 0D0h; unsigned int
0x180049f40  lea     rax, aVssObjectPropC; "VSS_OBJECT_PROP_Copy::destroy"
0x180049f47  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x180049f4c  lea     r9, aPrpcopyc; "PRPCOPYC"
0x180049f53  lea     r8, aBaseStorVssMod_17; "base\\stor\\vss\\modules\\prop\\copy.cx"...
0x180049f5a  mov     rdx, [rbp+50h]; struct _com_error *
0x180049f5e  lea     rcx, [rbp+60h]; this
0x180049f62  call    ?HandleComException@CVssFunctionTracer@@QEAAXAEAV_com_error@@PEBG11KK@Z; CVssFunctionTracer::HandleComException(_com_error &,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x180049f68  mov     rax, 0
0x180049f72  add     rsp, 40h
0x180049f76  pop     rbp
0x180049f77  retn
```
