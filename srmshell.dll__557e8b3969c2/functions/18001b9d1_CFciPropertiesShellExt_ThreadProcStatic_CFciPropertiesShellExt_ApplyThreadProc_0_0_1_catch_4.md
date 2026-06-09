# _CFciPropertiesShellExt::ThreadProcStatic__CFciPropertiesShellExt::ApplyThreadProc_0__0__::_1_::catch$4

- ea: `0x18001b9d1`
- end: `0x18001ba2c`
- name: `_CFciPropertiesShellExt::ThreadProcStatic__CFciPropertiesShellExt::ApplyThreadProc_0__0__::_1_::catch$4`
- size: `91`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180017ad0`

## string_xrefs

- `0x18001b9f0`: `CFciPropertiesShellExt::ThreadProcStatic`

## pseudocode

```c
void __fastcall __noreturn CFciPropertiesShellExt::ThreadProcStatic__CFciPropertiesShellExt::ApplyThreadProc_0__0__::_1_::catch_4(
        __int64 a1,
        __int64 a2)
{
  CSrmFunctionTracer::HandleComException(
    (CSrmFunctionTracer *)(a2 + 256),
    *(struct _com_error **)(a2 + 96),
    L"base\\fs\\fsrm\\clients\\srmshell\\fciprops.h",
    L"FCIPROPH",
    L"CFciPropertiesShellExt::ThreadProcStatic",
    0x42Du,
    *(_DWORD *)(a2 + 300));
}

```

## disassembly

```asm
0x18001b9d1  mov     [rsp+arg_8], rdx
0x18001b9d6  push    rbp
0x18001b9d7  sub     rsp, 40h
0x18001b9db  mov     rbp, rdx
0x18001b9de  mov     eax, [rbp+12Ch]
0x18001b9e4  mov     [rsp+48h+var_18], eax; unsigned int
0x18001b9e8  mov     [rsp+48h+var_20], 42Dh; unsigned int
0x18001b9f0  lea     rax, aCfciproperties_0; "CFciPropertiesShellExt::ThreadProcStati"...
0x18001b9f7  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x18001b9fc  lea     r9, aFciproph; "FCIPROPH"
0x18001ba03  lea     r8, aBaseFsFsrmClie_0; "base\\fs\\fsrm\\clients\\srmshell\\fcip"...
0x18001ba0a  mov     rdx, [rbp+60h]; struct _com_error *
0x18001ba0e  lea     rcx, [rbp+100h]; this
0x18001ba15  call    ?HandleComException@CSrmFunctionTracer@@QEAAXAEAV_com_error@@PEBG11KK@Z; CSrmFunctionTracer::HandleComException(_com_error &,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x18001ba1b  mov     rax, 0
0x18001ba25  add     rsp, 40h
0x18001ba29  pop     rbp
0x18001ba2a  retn
```
