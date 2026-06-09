# _VSS_OBJECT_PROP_Copy::copyProvider_::_1_::catch$3

- ea: `0x180049919`
- end: `0x180049971`
- name: `_VSS_OBJECT_PROP_Copy::copyProvider_::_1_::catch$3`
- size: `88`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180035360`

## string_xrefs

- `0x180049944`: `PRPCOPYC`
- `0x18004994b`: `base\stor\vss\modules\prop\copy.cxx`
- `0x180049938`: `VSS_OBJECT_PROP_Copy::copyProvider`

## pseudocode

```c
void __fastcall __noreturn VSS_OBJECT_PROP_Copy::copyProvider_::_1_::catch_3(__int64 a1, __int64 a2)
{
  CVssFunctionTracer::HandleComException(
    (CVssFunctionTracer *)(a2 + 96),
    *(struct _com_error **)(a2 + 72),
    L"base\\stor\\vss\\modules\\prop\\copy.cxx",
    L"PRPCOPYC",
    L"VSS_OBJECT_PROP_Copy::copyProvider",
    0x75u,
    *(_DWORD *)(a2 + 132));
}

```

## disassembly

```asm
0x180049919  mov     [rsp+arg_8], rdx
0x18004991e  push    rbp
0x18004991f  sub     rsp, 40h
0x180049923  mov     rbp, rdx
0x180049926  mov     eax, [rbp+84h]
0x18004992c  mov     [rsp+48h+var_18], eax; unsigned int
0x180049930  mov     [rsp+48h+var_20], 75h ; 'u'; unsigned int
0x180049938  lea     rax, aVssObjectPropC_2; "VSS_OBJECT_PROP_Copy::copyProvider"
0x18004993f  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x180049944  lea     r9, aPrpcopyc; "PRPCOPYC"
0x18004994b  lea     r8, aBaseStorVssMod_17; "base\\stor\\vss\\modules\\prop\\copy.cx"...
0x180049952  mov     rdx, [rbp+48h]; struct _com_error *
0x180049956  lea     rcx, [rbp+60h]; this
0x18004995a  call    ?HandleComException@CVssFunctionTracer@@QEAAXAEAV_com_error@@PEBG11KK@Z; CVssFunctionTracer::HandleComException(_com_error &,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x180049960  mov     rax, 0
0x18004996a  add     rsp, 40h
0x18004996e  pop     rbp
0x18004996f  retn
```
