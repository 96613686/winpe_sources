# _VSS_MGMT_OBJECT_PROP_Copy::init_::_1_::catch$2

- ea: `0x180049fdc`
- end: `0x18004a034`
- name: `_VSS_MGMT_OBJECT_PROP_Copy::init_::_1_::catch$2`
- size: `88`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180035564`

## string_xrefs

- `0x18004a007`: `PRPCOPYC`
- `0x18004a00e`: `base\stor\vss\modules\prop\copy.cxx`
- `0x180049ffb`: `VSS_MGMT_OBJECT_PROP_Copy::init`

## pseudocode

```c
void __fastcall __noreturn VSS_MGMT_OBJECT_PROP_Copy::init_::_1_::catch_2(__int64 a1, __int64 a2)
{
  CVssFunctionTracer::HandleStdGenericException(
    (CVssFunctionTracer *)(a2 + 96),
    *(const struct std::exception **)(a2 + 72),
    L"base\\stor\\vss\\modules\\prop\\copy.cxx",
    L"PRPCOPYC",
    L"VSS_MGMT_OBJECT_PROP_Copy::init",
    0x157u,
    *(_DWORD *)(a2 + 132));
}

```

## disassembly

```asm
0x180049fdc  mov     [rsp+arg_8], rdx
0x180049fe1  push    rbp
0x180049fe2  sub     rsp, 40h
0x180049fe6  mov     rbp, rdx
0x180049fe9  mov     eax, [rbp+84h]
0x180049fef  mov     [rsp+48h+var_18], eax; unsigned int
0x180049ff3  mov     [rsp+48h+var_20], 157h; unsigned int
0x180049ffb  lea     rax, aVssMgmtObjectP_6; "VSS_MGMT_OBJECT_PROP_Copy::init"
0x18004a002  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x18004a007  lea     r9, aPrpcopyc; "PRPCOPYC"
0x18004a00e  lea     r8, aBaseStorVssMod_17; "base\\stor\\vss\\modules\\prop\\copy.cx"...
0x18004a015  mov     rdx, [rbp+48h]; struct std::exception *
0x18004a019  lea     rcx, [rbp+60h]; this
0x18004a01d  call    ?HandleStdGenericException@CVssFunctionTracer@@QEAAXAEBVexception@std@@PEBG11KK@Z; CVssFunctionTracer::HandleStdGenericException(std::exception const &,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x18004a023  mov     rax, 0
0x18004a02d  add     rsp, 40h
0x18004a031  pop     rbp
0x18004a032  retn
```
