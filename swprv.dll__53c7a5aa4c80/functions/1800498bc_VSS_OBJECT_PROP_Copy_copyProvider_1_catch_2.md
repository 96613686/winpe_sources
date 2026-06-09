# _VSS_OBJECT_PROP_Copy::copyProvider_::_1_::catch$2

- ea: `0x1800498bc`
- end: `0x180049913`
- name: `_VSS_OBJECT_PROP_Copy::copyProvider_::_1_::catch$2`
- size: `87`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x18003544c`

## string_xrefs

- `0x1800498e7`: `PRPCOPYC`
- `0x1800498ee`: `base\stor\vss\modules\prop\copy.cxx`
- `0x1800498db`: `VSS_OBJECT_PROP_Copy::copyProvider`

## pseudocode

```c
__int64 __fastcall VSS_OBJECT_PROP_Copy::copyProvider_::_1_::catch_2(__int64 a1, unsigned int *a2)
{
  CVssFunctionTracer::HandleHresultException(
    (CVssFunctionTracer *)(a2 + 24),
    a2[16],
    L"base\\stor\\vss\\modules\\prop\\copy.cxx",
    L"PRPCOPYC",
    L"VSS_OBJECT_PROP_Copy::copyProvider",
    0x75u,
    a2[33]);
  return 0;
}

```

## disassembly

```asm
0x1800498bc  mov     [rsp+arg_8], rdx
0x1800498c1  push    rbp
0x1800498c2  sub     rsp, 40h
0x1800498c6  mov     rbp, rdx
0x1800498c9  mov     eax, [rbp+84h]
0x1800498cf  mov     [rsp+48h+var_18], eax; unsigned int
0x1800498d3  mov     [rsp+48h+var_20], 75h ; 'u'; unsigned int
0x1800498db  lea     rax, aVssObjectPropC_2; "VSS_OBJECT_PROP_Copy::copyProvider"
0x1800498e2  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x1800498e7  lea     r9, aPrpcopyc; "PRPCOPYC"
0x1800498ee  lea     r8, aBaseStorVssMod_17; "base\\stor\\vss\\modules\\prop\\copy.cx"...
0x1800498f5  mov     edx, [rbp+40h]; int
0x1800498f8  lea     rcx, [rbp+60h]; this
0x1800498fc  call    ?HandleHresultException@CVssFunctionTracer@@QEAAXJPEBG00KK@Z; CVssFunctionTracer::HandleHresultException(long,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x180049901  nop
0x180049902  mov     rax, 0
0x18004990c  add     rsp, 40h
0x180049910  pop     rbp
0x180049911  retn
```
