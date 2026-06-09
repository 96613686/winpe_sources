# _CFciPropertiesShellExt::ThreadProcStatic__CFciPropertiesShellExt::InitializeThreadProc_0__32768__::_1_::catch$6

- ea: `0x18001bc3a`
- end: `0x18001bc95`
- name: `_CFciPropertiesShellExt::ThreadProcStatic__CFciPropertiesShellExt::InitializeThreadProc_0__32768__::_1_::catch$6`
- size: `91`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180017ce8`

## string_xrefs

- `0x18001bc59`: `CFciPropertiesShellExt::ThreadProcStatic`

## pseudocode

```c
void __fastcall __noreturn CFciPropertiesShellExt::ThreadProcStatic__CFciPropertiesShellExt::InitializeThreadProc_0__32768__::_1_::catch_6(
        __int64 a1,
        __int64 a2)
{
  CSrmFunctionTracer::HandleStdGenericException(
    (CSrmFunctionTracer *)(a2 + 272),
    *(const struct exception **)(a2 + 112),
    L"base\\fs\\fsrm\\clients\\srmshell\\fciprops.h",
    L"FCIPROPH",
    L"CFciPropertiesShellExt::ThreadProcStatic",
    0x42Du,
    *(_DWORD *)(a2 + 316));
}

```

## disassembly

```asm
0x18001bc3a  mov     [rsp+arg_8], rdx
0x18001bc3f  push    rbp
0x18001bc40  sub     rsp, 40h
0x18001bc44  mov     rbp, rdx
0x18001bc47  mov     eax, [rbp+13Ch]
0x18001bc4d  mov     [rsp+48h+var_18], eax; unsigned int
0x18001bc51  mov     [rsp+48h+var_20], 42Dh; unsigned int
0x18001bc59  lea     rax, aCfciproperties_0; "CFciPropertiesShellExt::ThreadProcStati"...
0x18001bc60  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x18001bc65  lea     r9, aFciproph; "FCIPROPH"
0x18001bc6c  lea     r8, aBaseFsFsrmClie_0; "base\\fs\\fsrm\\clients\\srmshell\\fcip"...
0x18001bc73  mov     rdx, [rbp+70h]; struct exception *
0x18001bc77  lea     rcx, [rbp+110h]; this
0x18001bc7e  call    ?HandleStdGenericException@CSrmFunctionTracer@@QEAAXAEBVexception@@PEBG11KK@Z; CSrmFunctionTracer::HandleStdGenericException(exception const &,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x18001bc84  mov     rax, 0
0x18001bc8e  add     rsp, 40h
0x18001bc92  pop     rbp
0x18001bc93  retn
```
