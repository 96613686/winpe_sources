# _VSS_MGMT_OBJECT_PROP_Copy::copyDiffArea_::_1_::catch$5

- ea: `0x1800496f0`
- end: `0x180049748`
- name: `_VSS_MGMT_OBJECT_PROP_Copy::copyDiffArea_::_1_::catch$5`
- size: `88`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180035564`

## string_xrefs

- `0x18004971b`: `PRPCOPYC`
- `0x180049722`: `base\stor\vss\modules\prop\copy.cxx`
- `0x18004970f`: `VSS_MGMT_OBJECT_PROP_Copy::copyDiffArea`

## pseudocode

```c
void __fastcall __noreturn VSS_MGMT_OBJECT_PROP_Copy::copyDiffArea_::_1_::catch_5(__int64 a1, __int64 a2)
{
  CVssFunctionTracer::HandleStdGenericException(
    (CVssFunctionTracer *)(a2 + 96),
    *(const struct std::exception **)(a2 + 80),
    L"base\\stor\\vss\\modules\\prop\\copy.cxx",
    L"PRPCOPYC",
    L"VSS_MGMT_OBJECT_PROP_Copy::copyDiffArea",
    0x11Cu,
    *(_DWORD *)(a2 + 132));
}

```

## disassembly

```asm
0x1800496f0  mov     [rsp+arg_8], rdx
0x1800496f5  push    rbp
0x1800496f6  sub     rsp, 40h
0x1800496fa  mov     rbp, rdx
0x1800496fd  mov     eax, [rbp+84h]
0x180049703  mov     [rsp+48h+var_18], eax; unsigned int
0x180049707  mov     [rsp+48h+var_20], 11Ch; unsigned int
0x18004970f  lea     rax, aVssMgmtObjectP_0; "VSS_MGMT_OBJECT_PROP_Copy::copyDiffArea"
0x180049716  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x18004971b  lea     r9, aPrpcopyc; "PRPCOPYC"
0x180049722  lea     r8, aBaseStorVssMod_17; "base\\stor\\vss\\modules\\prop\\copy.cx"...
0x180049729  mov     rdx, [rbp+50h]; struct std::exception *
0x18004972d  lea     rcx, [rbp+60h]; this
0x180049731  call    ?HandleStdGenericException@CVssFunctionTracer@@QEAAXAEBVexception@std@@PEBG11KK@Z; CVssFunctionTracer::HandleStdGenericException(std::exception const &,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x180049737  mov     rax, 0
0x180049741  add     rsp, 40h
0x180049745  pop     rbp
0x180049746  retn
```
