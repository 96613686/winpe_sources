# _VSS_MGMT_OBJECT_PROP_Copy::copyVolume_::_1_::catch$5

- ea: `0x180049ca2`
- end: `0x180049cfa`
- name: `_VSS_MGMT_OBJECT_PROP_Copy::copyVolume_::_1_::catch$5`
- size: `88`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180035564`

## string_xrefs

- `0x180049ccd`: `PRPCOPYC`
- `0x180049cd4`: `base\stor\vss\modules\prop\copy.cxx`
- `0x180049cc1`: `VSS_MGMT_OBJECT_PROP_Copy::copyVolume`

## pseudocode

```c
void __fastcall __noreturn VSS_MGMT_OBJECT_PROP_Copy::copyVolume_::_1_::catch_5(__int64 a1, __int64 a2)
{
  CVssFunctionTracer::HandleStdGenericException(
    (CVssFunctionTracer *)(a2 + 96),
    *(const struct std::exception **)(a2 + 80),
    L"base\\stor\\vss\\modules\\prop\\copy.cxx",
    L"PRPCOPYC",
    L"VSS_MGMT_OBJECT_PROP_Copy::copyVolume",
    0xE9u,
    *(_DWORD *)(a2 + 132));
}

```

## disassembly

```asm
0x180049ca2  mov     [rsp+arg_8], rdx
0x180049ca7  push    rbp
0x180049ca8  sub     rsp, 40h
0x180049cac  mov     rbp, rdx
0x180049caf  mov     eax, [rbp+84h]
0x180049cb5  mov     [rsp+48h+var_18], eax; unsigned int
0x180049cb9  mov     [rsp+48h+var_20], 0E9h; unsigned int
0x180049cc1  lea     rax, aVssMgmtObjectP_2; "VSS_MGMT_OBJECT_PROP_Copy::copyVolume"
0x180049cc8  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x180049ccd  lea     r9, aPrpcopyc; "PRPCOPYC"
0x180049cd4  lea     r8, aBaseStorVssMod_17; "base\\stor\\vss\\modules\\prop\\copy.cx"...
0x180049cdb  mov     rdx, [rbp+50h]; struct std::exception *
0x180049cdf  lea     rcx, [rbp+60h]; this
0x180049ce3  call    ?HandleStdGenericException@CVssFunctionTracer@@QEAAXAEBVexception@std@@PEBG11KK@Z; CVssFunctionTracer::HandleStdGenericException(std::exception const &,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x180049ce9  mov     rax, 0
0x180049cf3  add     rsp, 40h
0x180049cf7  pop     rbp
0x180049cf8  retn
```
