# _CFciPropertiesShellExt::ThreadProcStatic__CFciPropertiesShellExt::ApplyThreadProc_0__0__::_1_::catch$5

- ea: `0x18001ba32`
- end: `0x18001ba84`
- name: `_CFciPropertiesShellExt::ThreadProcStatic__CFciPropertiesShellExt::ApplyThreadProc_0__0__::_1_::catch$5`
- size: `82`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180017c5c`

## string_xrefs

- `0x18001ba51`: `CFciPropertiesShellExt::ThreadProcStatic`

## pseudocode

```c
__int64 __fastcall CFciPropertiesShellExt::ThreadProcStatic__CFciPropertiesShellExt::ApplyThreadProc_0__0__::_1_::catch_5(
        __int64 a1,
        __int64 a2)
{
  CSrmFunctionTracer::HandleStdBadAllocException(
    (CSrmFunctionTracer *)(a2 + 256),
    L"base\\fs\\fsrm\\clients\\srmshell\\fciprops.h",
    L"FCIPROPH",
    L"CFciPropertiesShellExt::ThreadProcStatic",
    0x42Du,
    *(_DWORD *)(a2 + 300));
  return 0;
}

```

## disassembly

```asm
0x18001ba32  mov     [rsp+arg_8], rdx
0x18001ba37  push    rbp
0x18001ba38  sub     rsp, 40h
0x18001ba3c  mov     rbp, rdx
0x18001ba3f  mov     eax, [rbp+12Ch]
0x18001ba45  mov     [rsp+48h+var_20], eax; unsigned int
0x18001ba49  mov     [rsp+48h+var_28], 42Dh; unsigned int
0x18001ba51  lea     r9, aCfciproperties_0; "CFciPropertiesShellExt::ThreadProcStati"...
0x18001ba58  lea     r8, aFciproph; "FCIPROPH"
0x18001ba5f  lea     rdx, aBaseFsFsrmClie_0; "base\\fs\\fsrm\\clients\\srmshell\\fcip"...
0x18001ba66  lea     rcx, [rbp+100h]; this
0x18001ba6d  call    ?HandleStdBadAllocException@CSrmFunctionTracer@@QEAAXPEBG00KK@Z; CSrmFunctionTracer::HandleStdBadAllocException(ushort const *,ushort const *,ushort const *,ulong,ulong)
0x18001ba72  nop
0x18001ba73  mov     rax, 0
0x18001ba7d  add     rsp, 40h
0x18001ba81  pop     rbp
0x18001ba82  retn
```
