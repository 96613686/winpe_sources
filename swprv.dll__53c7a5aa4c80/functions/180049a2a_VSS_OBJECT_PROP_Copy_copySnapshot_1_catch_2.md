# _VSS_OBJECT_PROP_Copy::copySnapshot_::_1_::catch$2

- ea: `0x180049a2a`
- end: `0x180049a7e`
- name: `_VSS_OBJECT_PROP_Copy::copySnapshot_::_1_::catch$2`
- size: `84`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x18003544c`

## string_xrefs

- `0x180049a46`: `VSS_OBJECT_PROP_Copy::copySnapshot`
- `0x180049a52`: `PRPCOPYC`
- `0x180049a59`: `base\stor\vss\modules\prop\copy.cxx`

## pseudocode

```c
__int64 __fastcall VSS_OBJECT_PROP_Copy::copySnapshot_::_1_::catch_2(__int64 a1, unsigned int *a2)
{
  CVssFunctionTracer::HandleHresultException(
    (CVssFunctionTracer *)(a2 + 20),
    a2[16],
    L"base\\stor\\vss\\modules\\prop\\copy.cxx",
    L"PRPCOPYC",
    L"VSS_OBJECT_PROP_Copy::copySnapshot",
    0x5Au,
    a2[29]);
  return 0;
}

```

## disassembly

```asm
0x180049a2a  mov     [rsp+arg_8], rdx
0x180049a2f  push    rbp
0x180049a30  sub     rsp, 40h
0x180049a34  mov     rbp, rdx
0x180049a37  mov     eax, [rbp+74h]
0x180049a3a  mov     [rsp+48h+var_18], eax; unsigned int
0x180049a3e  mov     [rsp+48h+var_20], 5Ah ; 'Z'; unsigned int
0x180049a46  lea     rax, aVssObjectPropC_1; "VSS_OBJECT_PROP_Copy::copySnapshot"
0x180049a4d  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x180049a52  lea     r9, aPrpcopyc; "PRPCOPYC"
0x180049a59  lea     r8, aBaseStorVssMod_17; "base\\stor\\vss\\modules\\prop\\copy.cx"...
0x180049a60  mov     edx, [rbp+40h]; int
0x180049a63  lea     rcx, [rbp+50h]; this
0x180049a67  call    ?HandleHresultException@CVssFunctionTracer@@QEAAXJPEBG00KK@Z; CVssFunctionTracer::HandleHresultException(long,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x180049a6c  nop
0x180049a6d  mov     rax, 0
0x180049a77  add     rsp, 40h
0x180049a7b  pop     rbp
0x180049a7c  retn
```
