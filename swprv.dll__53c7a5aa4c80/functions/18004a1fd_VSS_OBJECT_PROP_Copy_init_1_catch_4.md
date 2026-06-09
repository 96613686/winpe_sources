# _VSS_OBJECT_PROP_Copy::init_::_1_::catch$4

- ea: `0x18004a1fd`
- end: `0x18004a255`
- name: `_VSS_OBJECT_PROP_Copy::init_::_1_::catch$4`
- size: `88`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180035360`

## string_xrefs

- `0x18004a228`: `PRPCOPYC`
- `0x18004a22f`: `base\stor\vss\modules\prop\copy.cxx`
- `0x18004a21c`: `VSS_OBJECT_PROP_Copy::init`

## pseudocode

```c
void __fastcall __noreturn VSS_OBJECT_PROP_Copy::init_::_1_::catch_4(__int64 a1, __int64 a2)
{
  CVssFunctionTracer::HandleComException(
    (CVssFunctionTracer *)(a2 + 96),
    *(struct _com_error **)(a2 + 80),
    L"base\\stor\\vss\\modules\\prop\\copy.cxx",
    L"PRPCOPYC",
    L"VSS_OBJECT_PROP_Copy::init",
    0xACu,
    *(_DWORD *)(a2 + 132));
}

```

## disassembly

```asm
0x18004a1fd  mov     [rsp+arg_8], rdx
0x18004a202  push    rbp
0x18004a203  sub     rsp, 40h
0x18004a207  mov     rbp, rdx
0x18004a20a  mov     eax, [rbp+84h]
0x18004a210  mov     [rsp+48h+var_18], eax; unsigned int
0x18004a214  mov     [rsp+48h+var_20], 0ACh; unsigned int
0x18004a21c  lea     rax, aVssObjectPropC_0; "VSS_OBJECT_PROP_Copy::init"
0x18004a223  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x18004a228  lea     r9, aPrpcopyc; "PRPCOPYC"
0x18004a22f  lea     r8, aBaseStorVssMod_17; "base\\stor\\vss\\modules\\prop\\copy.cx"...
0x18004a236  mov     rdx, [rbp+50h]; struct _com_error *
0x18004a23a  lea     rcx, [rbp+60h]; this
0x18004a23e  call    ?HandleComException@CVssFunctionTracer@@QEAAXAEAV_com_error@@PEBG11KK@Z; CVssFunctionTracer::HandleComException(_com_error &,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x18004a244  mov     rax, 0
0x18004a24e  add     rsp, 40h
0x18004a252  pop     rbp
0x18004a253  retn
```
