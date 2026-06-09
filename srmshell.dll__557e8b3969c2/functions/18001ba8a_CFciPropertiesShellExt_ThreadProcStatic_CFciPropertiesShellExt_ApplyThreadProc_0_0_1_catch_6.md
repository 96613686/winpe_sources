# _CFciPropertiesShellExt::ThreadProcStatic__CFciPropertiesShellExt::ApplyThreadProc_0__0__::_1_::catch$6

- ea: `0x18001ba8a`
- end: `0x18001bae5`
- name: `_CFciPropertiesShellExt::ThreadProcStatic__CFciPropertiesShellExt::ApplyThreadProc_0__0__::_1_::catch$6`
- size: `91`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180017ce8`

## string_xrefs

- `0x18001baa9`: `CFciPropertiesShellExt::ThreadProcStatic`

## pseudocode

```c
void __fastcall __noreturn CFciPropertiesShellExt::ThreadProcStatic__CFciPropertiesShellExt::ApplyThreadProc_0__0__::_1_::catch_6(
        __int64 a1,
        __int64 a2)
{
  CSrmFunctionTracer::HandleStdGenericException(
    (CSrmFunctionTracer *)(a2 + 256),
    *(const struct exception **)(a2 + 104),
    L"base\\fs\\fsrm\\clients\\srmshell\\fciprops.h",
    L"FCIPROPH",
    L"CFciPropertiesShellExt::ThreadProcStatic",
    0x42Du,
    *(_DWORD *)(a2 + 300));
}

```

## disassembly

```asm
0x18001ba8a  mov     [rsp+arg_8], rdx
0x18001ba8f  push    rbp
0x18001ba90  sub     rsp, 40h
0x18001ba94  mov     rbp, rdx
0x18001ba97  mov     eax, [rbp+12Ch]
0x18001ba9d  mov     [rsp+48h+var_18], eax; unsigned int
0x18001baa1  mov     [rsp+48h+var_20], 42Dh; unsigned int
0x18001baa9  lea     rax, aCfciproperties_0; "CFciPropertiesShellExt::ThreadProcStati"...
0x18001bab0  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x18001bab5  lea     r9, aFciproph; "FCIPROPH"
0x18001babc  lea     r8, aBaseFsFsrmClie_0; "base\\fs\\fsrm\\clients\\srmshell\\fcip"...
0x18001bac3  mov     rdx, [rbp+68h]; struct exception *
0x18001bac7  lea     rcx, [rbp+100h]; this
0x18001bace  call    ?HandleStdGenericException@CSrmFunctionTracer@@QEAAXAEBVexception@@PEBG11KK@Z; CSrmFunctionTracer::HandleStdGenericException(exception const &,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x18001bad4  mov     rax, 0
0x18001bade  add     rsp, 40h
0x18001bae2  pop     rbp
0x18001bae3  retn
```
