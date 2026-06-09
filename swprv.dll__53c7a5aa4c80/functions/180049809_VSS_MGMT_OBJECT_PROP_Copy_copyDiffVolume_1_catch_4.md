# _VSS_MGMT_OBJECT_PROP_Copy::copyDiffVolume_::_1_::catch$4

- ea: `0x180049809`
- end: `0x180049858`
- name: `_VSS_MGMT_OBJECT_PROP_Copy::copyDiffVolume_::_1_::catch$4`
- size: `79`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x1800354e0`

## string_xrefs

- `0x18004982f`: `PRPCOPYC`
- `0x180049836`: `base\stor\vss\modules\prop\copy.cxx`
- `0x180049828`: `VSS_MGMT_OBJECT_PROP_Copy::copyDiffVolume`

## pseudocode

```c
__int64 __fastcall VSS_MGMT_OBJECT_PROP_Copy::copyDiffVolume_::_1_::catch_4(__int64 a1, __int64 a2)
{
  CVssFunctionTracer::HandleStdBadAllocException(
    (CVssFunctionTracer *)(a2 + 96),
    L"base\\stor\\vss\\modules\\prop\\copy.cxx",
    L"PRPCOPYC",
    L"VSS_MGMT_OBJECT_PROP_Copy::copyDiffVolume",
    0x102u,
    *(_DWORD *)(a2 + 132));
  return 0;
}

```

## disassembly

```asm
0x180049809  mov     [rsp+arg_8], rdx
0x18004980e  push    rbp
0x18004980f  sub     rsp, 40h
0x180049813  mov     rbp, rdx
0x180049816  mov     eax, [rbp+84h]
0x18004981c  mov     [rsp+48h+var_20], eax; unsigned int
0x180049820  mov     [rsp+48h+var_28], 102h; unsigned int
0x180049828  lea     r9, aVssMgmtObjectP_1; "VSS_MGMT_OBJECT_PROP_Copy::copyDiffVolu"...
0x18004982f  lea     r8, aPrpcopyc; "PRPCOPYC"
0x180049836  lea     rdx, aBaseStorVssMod_17; "base\\stor\\vss\\modules\\prop\\copy.cx"...
0x18004983d  lea     rcx, [rbp+60h]; this
0x180049841  call    ?HandleStdBadAllocException@CVssFunctionTracer@@QEAAXPEBG00KK@Z; CVssFunctionTracer::HandleStdBadAllocException(ushort const *,ushort const *,ushort const *,ulong,ulong)
0x180049846  nop
0x180049847  mov     rax, 0
0x180049851  add     rsp, 40h
0x180049855  pop     rbp
0x180049856  retn
```
