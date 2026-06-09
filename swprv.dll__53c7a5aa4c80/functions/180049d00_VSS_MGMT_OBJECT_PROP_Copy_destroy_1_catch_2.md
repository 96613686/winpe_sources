# _VSS_MGMT_OBJECT_PROP_Copy::destroy_::_1_::catch$2

- ea: `0x180049d00`
- end: `0x180049d58`
- name: `_VSS_MGMT_OBJECT_PROP_Copy::destroy_::_1_::catch$2`
- size: `88`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180035564`

## string_xrefs

- `0x180049d2b`: `PRPCOPYC`
- `0x180049d32`: `base\stor\vss\modules\prop\copy.cxx`
- `0x180049d1f`: `VSS_MGMT_OBJECT_PROP_Copy::destroy`

## pseudocode

```c
void __fastcall __noreturn VSS_MGMT_OBJECT_PROP_Copy::destroy_::_1_::catch_2(__int64 a1, __int64 a2)
{
  CVssFunctionTracer::HandleStdGenericException(
    (CVssFunctionTracer *)(a2 + 96),
    *(const struct std::exception **)(a2 + 72),
    L"base\\stor\\vss\\modules\\prop\\copy.cxx",
    L"PRPCOPYC",
    L"VSS_MGMT_OBJECT_PROP_Copy::destroy",
    0x17Cu,
    *(_DWORD *)(a2 + 132));
}

```

## disassembly

```asm
0x180049d00  mov     [rsp+arg_8], rdx
0x180049d05  push    rbp
0x180049d06  sub     rsp, 40h
0x180049d0a  mov     rbp, rdx
0x180049d0d  mov     eax, [rbp+84h]
0x180049d13  mov     [rsp+48h+var_18], eax; unsigned int
0x180049d17  mov     [rsp+48h+var_20], 17Ch; unsigned int
0x180049d1f  lea     rax, aVssMgmtObjectP_4; "VSS_MGMT_OBJECT_PROP_Copy::destroy"
0x180049d26  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x180049d2b  lea     r9, aPrpcopyc; "PRPCOPYC"
0x180049d32  lea     r8, aBaseStorVssMod_17; "base\\stor\\vss\\modules\\prop\\copy.cx"...
0x180049d39  mov     rdx, [rbp+48h]; struct std::exception *
0x180049d3d  lea     rcx, [rbp+60h]; this
0x180049d41  call    ?HandleStdGenericException@CVssFunctionTracer@@QEAAXAEBVexception@std@@PEBG11KK@Z; CVssFunctionTracer::HandleStdGenericException(std::exception const &,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x180049d47  mov     rax, 0
0x180049d51  add     rsp, 40h
0x180049d55  pop     rbp
0x180049d56  retn
```
