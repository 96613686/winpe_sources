# _VSS_OBJECT_PROP_Copy::destroy_::_1_::catch$2

- ea: `0x180049e6e`
- end: `0x180049ec6`
- name: `_VSS_OBJECT_PROP_Copy::destroy_::_1_::catch$2`
- size: `88`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180035564`

## string_xrefs

- `0x180049e99`: `PRPCOPYC`
- `0x180049ea0`: `base\stor\vss\modules\prop\copy.cxx`
- `0x180049e8d`: `VSS_OBJECT_PROP_Copy::destroy`

## pseudocode

```c
void __fastcall __noreturn VSS_OBJECT_PROP_Copy::destroy_::_1_::catch_2(__int64 a1, __int64 a2)
{
  CVssFunctionTracer::HandleStdGenericException(
    (CVssFunctionTracer *)(a2 + 96),
    *(const struct std::exception **)(a2 + 72),
    L"base\\stor\\vss\\modules\\prop\\copy.cxx",
    L"PRPCOPYC",
    L"VSS_OBJECT_PROP_Copy::destroy",
    0xD0u,
    *(_DWORD *)(a2 + 132));
}

```

## disassembly

```asm
0x180049e6e  mov     [rsp+arg_8], rdx
0x180049e73  push    rbp
0x180049e74  sub     rsp, 40h
0x180049e78  mov     rbp, rdx
0x180049e7b  mov     eax, [rbp+84h]
0x180049e81  mov     [rsp+48h+var_18], eax; unsigned int
0x180049e85  mov     [rsp+48h+var_20], 0D0h; unsigned int
0x180049e8d  lea     rax, aVssObjectPropC; "VSS_OBJECT_PROP_Copy::destroy"
0x180049e94  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x180049e99  lea     r9, aPrpcopyc; "PRPCOPYC"
0x180049ea0  lea     r8, aBaseStorVssMod_17; "base\\stor\\vss\\modules\\prop\\copy.cx"...
0x180049ea7  mov     rdx, [rbp+48h]; struct std::exception *
0x180049eab  lea     rcx, [rbp+60h]; this
0x180049eaf  call    ?HandleStdGenericException@CVssFunctionTracer@@QEAAXAEBVexception@std@@PEBG11KK@Z; CVssFunctionTracer::HandleStdGenericException(std::exception const &,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x180049eb5  mov     rax, 0
0x180049ebf  add     rsp, 40h
0x180049ec3  pop     rbp
0x180049ec4  retn
```
