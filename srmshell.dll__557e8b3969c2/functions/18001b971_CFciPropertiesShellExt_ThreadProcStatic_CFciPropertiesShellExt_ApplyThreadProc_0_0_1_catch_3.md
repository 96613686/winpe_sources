# _CFciPropertiesShellExt::ThreadProcStatic__CFciPropertiesShellExt::ApplyThreadProc_0__0__::_1_::catch$3

- ea: `0x18001b971`
- end: `0x18001b9cb`
- name: `_CFciPropertiesShellExt::ThreadProcStatic__CFciPropertiesShellExt::ApplyThreadProc_0__0__::_1_::catch$3`
- size: `90`
- prototype: `__int64 __fastcall(__int64, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180017bc8`

## string_xrefs

- `0x18001b990`: `CFciPropertiesShellExt::ThreadProcStatic`

## pseudocode

```c
__int64 __fastcall CFciPropertiesShellExt::ThreadProcStatic__CFciPropertiesShellExt::ApplyThreadProc_0__0__::_1_::catch_3(
        __int64 a1,
        unsigned int *a2)
{
  CSrmFunctionTracer::HandleHresultException(
    (CSrmFunctionTracer *)(a2 + 64),
    a2[17],
    L"base\\fs\\fsrm\\clients\\srmshell\\fciprops.h",
    L"FCIPROPH",
    L"CFciPropertiesShellExt::ThreadProcStatic",
    0x42Du,
    a2[75]);
  return 0;
}

```

## disassembly

```asm
0x18001b971  mov     [rsp+arg_8], rdx
0x18001b976  push    rbp
0x18001b977  sub     rsp, 40h
0x18001b97b  mov     rbp, rdx
0x18001b97e  mov     eax, [rbp+12Ch]
0x18001b984  mov     [rsp+48h+var_18], eax; unsigned int
0x18001b988  mov     [rsp+48h+var_20], 42Dh; unsigned int
0x18001b990  lea     rax, aCfciproperties_0; "CFciPropertiesShellExt::ThreadProcStati"...
0x18001b997  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x18001b99c  lea     r9, aFciproph; "FCIPROPH"
0x18001b9a3  lea     r8, aBaseFsFsrmClie_0; "base\\fs\\fsrm\\clients\\srmshell\\fcip"...
0x18001b9aa  mov     edx, [rbp+44h]; int
0x18001b9ad  lea     rcx, [rbp+100h]; this
0x18001b9b4  call    ?HandleHresultException@CSrmFunctionTracer@@QEAAXJPEBG00KK@Z; CSrmFunctionTracer::HandleHresultException(long,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x18001b9b9  nop
0x18001b9ba  mov     rax, 0
0x18001b9c4  add     rsp, 40h
0x18001b9c8  pop     rbp
0x18001b9c9  retn
```
