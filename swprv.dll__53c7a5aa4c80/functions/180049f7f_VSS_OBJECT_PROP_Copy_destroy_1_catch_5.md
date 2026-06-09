# _VSS_OBJECT_PROP_Copy::destroy_::_1_::catch$5

- ea: `0x180049f7f`
- end: `0x180049fd6`
- name: `_VSS_OBJECT_PROP_Copy::destroy_::_1_::catch$5`
- size: `87`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x18003544c`

## string_xrefs

- `0x180049faa`: `PRPCOPYC`
- `0x180049fb1`: `base\stor\vss\modules\prop\copy.cxx`
- `0x180049f9e`: `VSS_OBJECT_PROP_Copy::destroy`

## pseudocode

```c
__int64 __fastcall VSS_OBJECT_PROP_Copy::destroy_::_1_::catch_5(__int64 a1, unsigned int *a2)
{
  CVssFunctionTracer::HandleHresultException(
    (CVssFunctionTracer *)(a2 + 24),
    a2[16],
    L"base\\stor\\vss\\modules\\prop\\copy.cxx",
    L"PRPCOPYC",
    L"VSS_OBJECT_PROP_Copy::destroy",
    0xD0u,
    a2[33]);
  return 0;
}

```

## disassembly

```asm
0x180049f7f  mov     [rsp+arg_8], rdx
0x180049f84  push    rbp
0x180049f85  sub     rsp, 40h
0x180049f89  mov     rbp, rdx
0x180049f8c  mov     eax, [rbp+84h]
0x180049f92  mov     [rsp+48h+var_18], eax; unsigned int
0x180049f96  mov     [rsp+48h+var_20], 0D0h; unsigned int
0x180049f9e  lea     rax, aVssObjectPropC; "VSS_OBJECT_PROP_Copy::destroy"
0x180049fa5  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x180049faa  lea     r9, aPrpcopyc; "PRPCOPYC"
0x180049fb1  lea     r8, aBaseStorVssMod_17; "base\\stor\\vss\\modules\\prop\\copy.cx"...
0x180049fb8  mov     edx, [rbp+40h]; int
0x180049fbb  lea     rcx, [rbp+60h]; this
0x180049fbf  call    ?HandleHresultException@CVssFunctionTracer@@QEAAXJPEBG00KK@Z; CVssFunctionTracer::HandleHresultException(long,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x180049fc4  nop
0x180049fc5  mov     rax, 0
0x180049fcf  add     rsp, 40h
0x180049fd3  pop     rbp
0x180049fd4  retn
```
