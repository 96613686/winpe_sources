# _VSS_OBJECT_PROP_Copy::copySnapshot_::_1_::catch$3

- ea: `0x180049a84`
- end: `0x180049adc`
- name: `_VSS_OBJECT_PROP_Copy::copySnapshot_::_1_::catch$3`
- size: `88`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180035360`

## string_xrefs

- `0x180049aa0`: `VSS_OBJECT_PROP_Copy::copySnapshot`
- `0x180049aac`: `PRPCOPYC`
- `0x180049ab3`: `base\stor\vss\modules\prop\copy.cxx`

## pseudocode

```c
void __fastcall __noreturn VSS_OBJECT_PROP_Copy::copySnapshot_::_1_::catch_3(__int64 a1, __int64 a2)
{
  CVssFunctionTracer::HandleComException(
    (CVssFunctionTracer *)(a2 + 80),
    *(struct _com_error **)(a2 + 192),
    L"base\\stor\\vss\\modules\\prop\\copy.cxx",
    L"PRPCOPYC",
    L"VSS_OBJECT_PROP_Copy::copySnapshot",
    0x5Au,
    *(_DWORD *)(a2 + 116));
}

```

## disassembly

```asm
0x180049a84  mov     [rsp+arg_8], rdx
0x180049a89  push    rbp
0x180049a8a  sub     rsp, 40h
0x180049a8e  mov     rbp, rdx
0x180049a91  mov     eax, [rbp+74h]
0x180049a94  mov     [rsp+48h+var_18], eax; unsigned int
0x180049a98  mov     [rsp+48h+var_20], 5Ah ; 'Z'; unsigned int
0x180049aa0  lea     rax, aVssObjectPropC_1; "VSS_OBJECT_PROP_Copy::copySnapshot"
0x180049aa7  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x180049aac  lea     r9, aPrpcopyc; "PRPCOPYC"
0x180049ab3  lea     r8, aBaseStorVssMod_17; "base\\stor\\vss\\modules\\prop\\copy.cx"...
0x180049aba  mov     rdx, [rbp+0C0h]; struct _com_error *
0x180049ac1  lea     rcx, [rbp+50h]; this
0x180049ac5  call    ?HandleComException@CVssFunctionTracer@@QEAAXAEAV_com_error@@PEBG11KK@Z; CVssFunctionTracer::HandleComException(_com_error &,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x180049acb  mov     rax, 0
0x180049ad5  add     rsp, 40h
0x180049ad9  pop     rbp
0x180049ada  retn
```
