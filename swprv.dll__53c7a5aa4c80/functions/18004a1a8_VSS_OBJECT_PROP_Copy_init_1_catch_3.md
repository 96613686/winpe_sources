# _VSS_OBJECT_PROP_Copy::init_::_1_::catch$3

- ea: `0x18004a1a8`
- end: `0x18004a1f7`
- name: `_VSS_OBJECT_PROP_Copy::init_::_1_::catch$3`
- size: `79`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x1800354e0`

## string_xrefs

- `0x18004a1ce`: `PRPCOPYC`
- `0x18004a1d5`: `base\stor\vss\modules\prop\copy.cxx`
- `0x18004a1c7`: `VSS_OBJECT_PROP_Copy::init`

## pseudocode

```c
__int64 __fastcall VSS_OBJECT_PROP_Copy::init_::_1_::catch_3(__int64 a1, __int64 a2)
{
  CVssFunctionTracer::HandleStdBadAllocException(
    (CVssFunctionTracer *)(a2 + 96),
    L"base\\stor\\vss\\modules\\prop\\copy.cxx",
    L"PRPCOPYC",
    L"VSS_OBJECT_PROP_Copy::init",
    0xACu,
    *(_DWORD *)(a2 + 132));
  return 0;
}

```

## disassembly

```asm
0x18004a1a8  mov     [rsp+arg_8], rdx
0x18004a1ad  push    rbp
0x18004a1ae  sub     rsp, 40h
0x18004a1b2  mov     rbp, rdx
0x18004a1b5  mov     eax, [rbp+84h]
0x18004a1bb  mov     [rsp+48h+var_20], eax; unsigned int
0x18004a1bf  mov     [rsp+48h+var_28], 0ACh; unsigned int
0x18004a1c7  lea     r9, aVssObjectPropC_0; "VSS_OBJECT_PROP_Copy::init"
0x18004a1ce  lea     r8, aPrpcopyc; "PRPCOPYC"
0x18004a1d5  lea     rdx, aBaseStorVssMod_17; "base\\stor\\vss\\modules\\prop\\copy.cx"...
0x18004a1dc  lea     rcx, [rbp+60h]; this
0x18004a1e0  call    ?HandleStdBadAllocException@CVssFunctionTracer@@QEAAXPEBG00KK@Z; CVssFunctionTracer::HandleStdBadAllocException(ushort const *,ushort const *,ushort const *,ulong,ulong)
0x18004a1e5  nop
0x18004a1e6  mov     rax, 0
0x18004a1f0  add     rsp, 40h
0x18004a1f4  pop     rbp
0x18004a1f5  retn
```
