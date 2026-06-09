# _VSS_MGMT_OBJECT_PROP_Copy::copyDiffVolume_::_1_::catch$3

- ea: `0x1800497ab`
- end: `0x180049803`
- name: `_VSS_MGMT_OBJECT_PROP_Copy::copyDiffVolume_::_1_::catch$3`
- size: `88`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180035360`

## string_xrefs

- `0x1800497d6`: `PRPCOPYC`
- `0x1800497dd`: `base\stor\vss\modules\prop\copy.cxx`
- `0x1800497ca`: `VSS_MGMT_OBJECT_PROP_Copy::copyDiffVolume`

## pseudocode

```c
void __fastcall __noreturn VSS_MGMT_OBJECT_PROP_Copy::copyDiffVolume_::_1_::catch_3(__int64 a1, __int64 a2)
{
  CVssFunctionTracer::HandleComException(
    (CVssFunctionTracer *)(a2 + 96),
    *(struct _com_error **)(a2 + 72),
    L"base\\stor\\vss\\modules\\prop\\copy.cxx",
    L"PRPCOPYC",
    L"VSS_MGMT_OBJECT_PROP_Copy::copyDiffVolume",
    0x102u,
    *(_DWORD *)(a2 + 132));
}

```

## disassembly

```asm
0x1800497ab  mov     [rsp+arg_8], rdx
0x1800497b0  push    rbp
0x1800497b1  sub     rsp, 40h
0x1800497b5  mov     rbp, rdx
0x1800497b8  mov     eax, [rbp+84h]
0x1800497be  mov     [rsp+48h+var_18], eax; unsigned int
0x1800497c2  mov     [rsp+48h+var_20], 102h; unsigned int
0x1800497ca  lea     rax, aVssMgmtObjectP_1; "VSS_MGMT_OBJECT_PROP_Copy::copyDiffVolu"...
0x1800497d1  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x1800497d6  lea     r9, aPrpcopyc; "PRPCOPYC"
0x1800497dd  lea     r8, aBaseStorVssMod_17; "base\\stor\\vss\\modules\\prop\\copy.cx"...
0x1800497e4  mov     rdx, [rbp+48h]; struct _com_error *
0x1800497e8  lea     rcx, [rbp+60h]; this
0x1800497ec  call    ?HandleComException@CVssFunctionTracer@@QEAAXAEAV_com_error@@PEBG11KK@Z; CVssFunctionTracer::HandleComException(_com_error &,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x1800497f2  mov     rax, 0
0x1800497fc  add     rsp, 40h
0x180049800  pop     rbp
0x180049801  retn
```
