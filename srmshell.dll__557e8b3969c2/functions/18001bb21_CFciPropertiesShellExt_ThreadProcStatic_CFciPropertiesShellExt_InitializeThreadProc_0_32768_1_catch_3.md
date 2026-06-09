# _CFciPropertiesShellExt::ThreadProcStatic__CFciPropertiesShellExt::InitializeThreadProc_0__32768__::_1_::catch$3

- ea: `0x18001bb21`
- end: `0x18001bb7b`
- name: `_CFciPropertiesShellExt::ThreadProcStatic__CFciPropertiesShellExt::InitializeThreadProc_0__32768__::_1_::catch$3`
- size: `90`
- prototype: `__int64 __fastcall(__int64, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180017bc8`

## string_xrefs

- `0x18001bb40`: `CFciPropertiesShellExt::ThreadProcStatic`

## pseudocode

```c
__int64 __fastcall CFciPropertiesShellExt::ThreadProcStatic__CFciPropertiesShellExt::InitializeThreadProc_0__32768__::_1_::catch_3(
        __int64 a1,
        unsigned int *a2)
{
  CSrmFunctionTracer::HandleHresultException(
    (CSrmFunctionTracer *)(a2 + 68),
    a2[20],
    L"base\\fs\\fsrm\\clients\\srmshell\\fciprops.h",
    L"FCIPROPH",
    L"CFciPropertiesShellExt::ThreadProcStatic",
    0x42Du,
    a2[79]);
  return 0;
}

```

## disassembly

```asm
0x18001bb21  mov     [rsp+arg_8], rdx
0x18001bb26  push    rbp
0x18001bb27  sub     rsp, 40h
0x18001bb2b  mov     rbp, rdx
0x18001bb2e  mov     eax, [rbp+13Ch]
0x18001bb34  mov     [rsp+48h+var_18], eax; unsigned int
0x18001bb38  mov     [rsp+48h+var_20], 42Dh; unsigned int
0x18001bb40  lea     rax, aCfciproperties_0; "CFciPropertiesShellExt::ThreadProcStati"...
0x18001bb47  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x18001bb4c  lea     r9, aFciproph; "FCIPROPH"
0x18001bb53  lea     r8, aBaseFsFsrmClie_0; "base\\fs\\fsrm\\clients\\srmshell\\fcip"...
0x18001bb5a  mov     edx, [rbp+50h]; int
0x18001bb5d  lea     rcx, [rbp+110h]; this
0x18001bb64  call    ?HandleHresultException@CSrmFunctionTracer@@QEAAXJPEBG00KK@Z; CSrmFunctionTracer::HandleHresultException(long,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x18001bb69  nop
0x18001bb6a  mov     rax, 0
0x18001bb74  add     rsp, 40h
0x18001bb78  pop     rbp
0x18001bb79  retn
```
