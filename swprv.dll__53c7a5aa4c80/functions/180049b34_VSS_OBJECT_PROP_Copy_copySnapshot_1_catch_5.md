# _VSS_OBJECT_PROP_Copy::copySnapshot_::_1_::catch$5

- ea: `0x180049b34`
- end: `0x180049b8c`
- name: `_VSS_OBJECT_PROP_Copy::copySnapshot_::_1_::catch$5`
- size: `88`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180035564`

## string_xrefs

- `0x180049b50`: `VSS_OBJECT_PROP_Copy::copySnapshot`
- `0x180049b5c`: `PRPCOPYC`
- `0x180049b63`: `base\stor\vss\modules\prop\copy.cxx`

## pseudocode

```c
void __fastcall __noreturn VSS_OBJECT_PROP_Copy::copySnapshot_::_1_::catch_5(__int64 a1, __int64 a2)
{
  CVssFunctionTracer::HandleStdGenericException(
    (CVssFunctionTracer *)(a2 + 80),
    *(const struct std::exception **)(a2 + 200),
    L"base\\stor\\vss\\modules\\prop\\copy.cxx",
    L"PRPCOPYC",
    L"VSS_OBJECT_PROP_Copy::copySnapshot",
    0x5Au,
    *(_DWORD *)(a2 + 116));
}

```

## disassembly

```asm
0x180049b34  mov     [rsp+arg_8], rdx
0x180049b39  push    rbp
0x180049b3a  sub     rsp, 40h
0x180049b3e  mov     rbp, rdx
0x180049b41  mov     eax, [rbp+74h]
0x180049b44  mov     [rsp+48h+var_18], eax; unsigned int
0x180049b48  mov     [rsp+48h+var_20], 5Ah ; 'Z'; unsigned int
0x180049b50  lea     rax, aVssObjectPropC_1; "VSS_OBJECT_PROP_Copy::copySnapshot"
0x180049b57  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x180049b5c  lea     r9, aPrpcopyc; "PRPCOPYC"
0x180049b63  lea     r8, aBaseStorVssMod_17; "base\\stor\\vss\\modules\\prop\\copy.cx"...
0x180049b6a  mov     rdx, [rbp+0C8h]; struct std::exception *
0x180049b71  lea     rcx, [rbp+50h]; this
0x180049b75  call    ?HandleStdGenericException@CVssFunctionTracer@@QEAAXAEBVexception@std@@PEBG11KK@Z; CVssFunctionTracer::HandleStdGenericException(std::exception const &,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x180049b7b  mov     rax, 0
0x180049b85  add     rsp, 40h
0x180049b89  pop     rbp
0x180049b8a  retn
```
