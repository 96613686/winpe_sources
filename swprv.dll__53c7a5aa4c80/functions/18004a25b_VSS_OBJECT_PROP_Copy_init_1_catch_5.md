# _VSS_OBJECT_PROP_Copy::init_::_1_::catch$5

- ea: `0x18004a25b`
- end: `0x18004a2b2`
- name: `_VSS_OBJECT_PROP_Copy::init_::_1_::catch$5`
- size: `87`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x18003544c`

## string_xrefs

- `0x18004a286`: `PRPCOPYC`
- `0x18004a28d`: `base\stor\vss\modules\prop\copy.cxx`
- `0x18004a27a`: `VSS_OBJECT_PROP_Copy::init`

## pseudocode

```c
__int64 __fastcall VSS_OBJECT_PROP_Copy::init_::_1_::catch_5(__int64 a1, unsigned int *a2)
{
  CVssFunctionTracer::HandleHresultException(
    (CVssFunctionTracer *)(a2 + 24),
    a2[16],
    L"base\\stor\\vss\\modules\\prop\\copy.cxx",
    L"PRPCOPYC",
    L"VSS_OBJECT_PROP_Copy::init",
    0xACu,
    a2[33]);
  return 0;
}

```

## disassembly

```asm
0x18004a25b  mov     [rsp+arg_8], rdx
0x18004a260  push    rbp
0x18004a261  sub     rsp, 40h
0x18004a265  mov     rbp, rdx
0x18004a268  mov     eax, [rbp+84h]
0x18004a26e  mov     [rsp+48h+var_18], eax; unsigned int
0x18004a272  mov     [rsp+48h+var_20], 0ACh; unsigned int
0x18004a27a  lea     rax, aVssObjectPropC_0; "VSS_OBJECT_PROP_Copy::init"
0x18004a281  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x18004a286  lea     r9, aPrpcopyc; "PRPCOPYC"
0x18004a28d  lea     r8, aBaseStorVssMod_17; "base\\stor\\vss\\modules\\prop\\copy.cx"...
0x18004a294  mov     edx, [rbp+40h]; int
0x18004a297  lea     rcx, [rbp+60h]; this
0x18004a29b  call    ?HandleHresultException@CVssFunctionTracer@@QEAAXJPEBG00KK@Z; CVssFunctionTracer::HandleHresultException(long,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x18004a2a0  nop
0x18004a2a1  mov     rax, 0
0x18004a2ab  add     rsp, 40h
0x18004a2af  pop     rbp
0x18004a2b0  retn
```
