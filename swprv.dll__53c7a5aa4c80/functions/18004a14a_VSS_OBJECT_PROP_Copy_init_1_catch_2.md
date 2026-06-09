# _VSS_OBJECT_PROP_Copy::init_::_1_::catch$2

- ea: `0x18004a14a`
- end: `0x18004a1a2`
- name: `_VSS_OBJECT_PROP_Copy::init_::_1_::catch$2`
- size: `88`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180035564`

## string_xrefs

- `0x18004a175`: `PRPCOPYC`
- `0x18004a17c`: `base\stor\vss\modules\prop\copy.cxx`
- `0x18004a169`: `VSS_OBJECT_PROP_Copy::init`

## pseudocode

```c
void __fastcall __noreturn VSS_OBJECT_PROP_Copy::init_::_1_::catch_2(__int64 a1, __int64 a2)
{
  CVssFunctionTracer::HandleStdGenericException(
    (CVssFunctionTracer *)(a2 + 96),
    *(const struct std::exception **)(a2 + 72),
    L"base\\stor\\vss\\modules\\prop\\copy.cxx",
    L"PRPCOPYC",
    L"VSS_OBJECT_PROP_Copy::init",
    0xACu,
    *(_DWORD *)(a2 + 132));
}

```

## disassembly

```asm
0x18004a14a  mov     [rsp+arg_8], rdx
0x18004a14f  push    rbp
0x18004a150  sub     rsp, 40h
0x18004a154  mov     rbp, rdx
0x18004a157  mov     eax, [rbp+84h]
0x18004a15d  mov     [rsp+48h+var_18], eax; unsigned int
0x18004a161  mov     [rsp+48h+var_20], 0ACh; unsigned int
0x18004a169  lea     rax, aVssObjectPropC_0; "VSS_OBJECT_PROP_Copy::init"
0x18004a170  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x18004a175  lea     r9, aPrpcopyc; "PRPCOPYC"
0x18004a17c  lea     r8, aBaseStorVssMod_17; "base\\stor\\vss\\modules\\prop\\copy.cx"...
0x18004a183  mov     rdx, [rbp+48h]; struct std::exception *
0x18004a187  lea     rcx, [rbp+60h]; this
0x18004a18b  call    ?HandleStdGenericException@CVssFunctionTracer@@QEAAXAEBVexception@std@@PEBG11KK@Z; CVssFunctionTracer::HandleStdGenericException(std::exception const &,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x18004a191  mov     rax, 0
0x18004a19b  add     rsp, 40h
0x18004a19f  pop     rbp
0x18004a1a0  retn
```
