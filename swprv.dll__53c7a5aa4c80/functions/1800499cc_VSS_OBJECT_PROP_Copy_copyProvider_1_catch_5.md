# _VSS_OBJECT_PROP_Copy::copyProvider_::_1_::catch$5

- ea: `0x1800499cc`
- end: `0x180049a24`
- name: `_VSS_OBJECT_PROP_Copy::copyProvider_::_1_::catch$5`
- size: `88`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180035564`

## string_xrefs

- `0x1800499f7`: `PRPCOPYC`
- `0x1800499fe`: `base\stor\vss\modules\prop\copy.cxx`
- `0x1800499eb`: `VSS_OBJECT_PROP_Copy::copyProvider`

## pseudocode

```c
void __fastcall __noreturn VSS_OBJECT_PROP_Copy::copyProvider_::_1_::catch_5(__int64 a1, __int64 a2)
{
  CVssFunctionTracer::HandleStdGenericException(
    (CVssFunctionTracer *)(a2 + 96),
    *(const struct std::exception **)(a2 + 80),
    L"base\\stor\\vss\\modules\\prop\\copy.cxx",
    L"PRPCOPYC",
    L"VSS_OBJECT_PROP_Copy::copyProvider",
    0x75u,
    *(_DWORD *)(a2 + 132));
}

```

## disassembly

```asm
0x1800499cc  mov     [rsp+arg_8], rdx
0x1800499d1  push    rbp
0x1800499d2  sub     rsp, 40h
0x1800499d6  mov     rbp, rdx
0x1800499d9  mov     eax, [rbp+84h]
0x1800499df  mov     [rsp+48h+var_18], eax; unsigned int
0x1800499e3  mov     [rsp+48h+var_20], 75h ; 'u'; unsigned int
0x1800499eb  lea     rax, aVssObjectPropC_2; "VSS_OBJECT_PROP_Copy::copyProvider"
0x1800499f2  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x1800499f7  lea     r9, aPrpcopyc; "PRPCOPYC"
0x1800499fe  lea     r8, aBaseStorVssMod_17; "base\\stor\\vss\\modules\\prop\\copy.cx"...
0x180049a05  mov     rdx, [rbp+50h]; struct std::exception *
0x180049a09  lea     rcx, [rbp+60h]; this
0x180049a0d  call    ?HandleStdGenericException@CVssFunctionTracer@@QEAAXAEBVexception@std@@PEBG11KK@Z; CVssFunctionTracer::HandleStdGenericException(std::exception const &,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x180049a13  mov     rax, 0
0x180049a1d  add     rsp, 40h
0x180049a21  pop     rbp
0x180049a22  retn
```
