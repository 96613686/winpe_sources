# _CFciPropertiesShellExt::ThreadProcStatic__CFciPropertiesShellExt::InitializeThreadProc_0__32768__::_1_::catch$5

- ea: `0x18001bbe2`
- end: `0x18001bc34`
- name: `_CFciPropertiesShellExt::ThreadProcStatic__CFciPropertiesShellExt::InitializeThreadProc_0__32768__::_1_::catch$5`
- size: `82`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180017c5c`

## string_xrefs

- `0x18001bc01`: `CFciPropertiesShellExt::ThreadProcStatic`

## pseudocode

```c
__int64 __fastcall CFciPropertiesShellExt::ThreadProcStatic__CFciPropertiesShellExt::InitializeThreadProc_0__32768__::_1_::catch_5(
        __int64 a1,
        __int64 a2)
{
  CSrmFunctionTracer::HandleStdBadAllocException(
    (CSrmFunctionTracer *)(a2 + 272),
    L"base\\fs\\fsrm\\clients\\srmshell\\fciprops.h",
    L"FCIPROPH",
    L"CFciPropertiesShellExt::ThreadProcStatic",
    0x42Du,
    *(_DWORD *)(a2 + 316));
  return 0;
}

```

## disassembly

```asm
0x18001bbe2  mov     [rsp+arg_8], rdx
0x18001bbe7  push    rbp
0x18001bbe8  sub     rsp, 40h
0x18001bbec  mov     rbp, rdx
0x18001bbef  mov     eax, [rbp+13Ch]
0x18001bbf5  mov     [rsp+48h+var_20], eax; unsigned int
0x18001bbf9  mov     [rsp+48h+var_28], 42Dh; unsigned int
0x18001bc01  lea     r9, aCfciproperties_0; "CFciPropertiesShellExt::ThreadProcStati"...
0x18001bc08  lea     r8, aFciproph; "FCIPROPH"
0x18001bc0f  lea     rdx, aBaseFsFsrmClie_0; "base\\fs\\fsrm\\clients\\srmshell\\fcip"...
0x18001bc16  lea     rcx, [rbp+110h]; this
0x18001bc1d  call    ?HandleStdBadAllocException@CSrmFunctionTracer@@QEAAXPEBG00KK@Z; CSrmFunctionTracer::HandleStdBadAllocException(ushort const *,ushort const *,ushort const *,ulong,ulong)
0x18001bc22  nop
0x18001bc23  mov     rax, 0
0x18001bc2d  add     rsp, 40h
0x18001bc31  pop     rbp
0x18001bc32  retn
```
