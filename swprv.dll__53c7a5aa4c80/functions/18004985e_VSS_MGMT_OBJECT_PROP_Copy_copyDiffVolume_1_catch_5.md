# _VSS_MGMT_OBJECT_PROP_Copy::copyDiffVolume_::_1_::catch$5

- ea: `0x18004985e`
- end: `0x1800498b6`
- name: `_VSS_MGMT_OBJECT_PROP_Copy::copyDiffVolume_::_1_::catch$5`
- size: `88`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180035564`

## string_xrefs

- `0x180049889`: `PRPCOPYC`
- `0x180049890`: `base\stor\vss\modules\prop\copy.cxx`
- `0x18004987d`: `VSS_MGMT_OBJECT_PROP_Copy::copyDiffVolume`

## pseudocode

```c
void __fastcall __noreturn VSS_MGMT_OBJECT_PROP_Copy::copyDiffVolume_::_1_::catch_5(__int64 a1, __int64 a2)
{
  CVssFunctionTracer::HandleStdGenericException(
    (CVssFunctionTracer *)(a2 + 96),
    *(const struct std::exception **)(a2 + 80),
    L"base\\stor\\vss\\modules\\prop\\copy.cxx",
    L"PRPCOPYC",
    L"VSS_MGMT_OBJECT_PROP_Copy::copyDiffVolume",
    0x102u,
    *(_DWORD *)(a2 + 132));
}

```

## disassembly

```asm
0x18004985e  mov     [rsp+arg_8], rdx
0x180049863  push    rbp
0x180049864  sub     rsp, 40h
0x180049868  mov     rbp, rdx
0x18004986b  mov     eax, [rbp+84h]
0x180049871  mov     [rsp+48h+var_18], eax; unsigned int
0x180049875  mov     [rsp+48h+var_20], 102h; unsigned int
0x18004987d  lea     rax, aVssMgmtObjectP_1; "VSS_MGMT_OBJECT_PROP_Copy::copyDiffVolu"...
0x180049884  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x180049889  lea     r9, aPrpcopyc; "PRPCOPYC"
0x180049890  lea     r8, aBaseStorVssMod_17; "base\\stor\\vss\\modules\\prop\\copy.cx"...
0x180049897  mov     rdx, [rbp+50h]; struct std::exception *
0x18004989b  lea     rcx, [rbp+60h]; this
0x18004989f  call    ?HandleStdGenericException@CVssFunctionTracer@@QEAAXAEBVexception@std@@PEBG11KK@Z; CVssFunctionTracer::HandleStdGenericException(std::exception const &,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x1800498a5  mov     rax, 0
0x1800498af  add     rsp, 40h
0x1800498b3  pop     rbp
0x1800498b4  retn
```
