# _CFciPropertiesShellExt::ThreadProcStatic__CFciPropertiesShellExt::InitializeThreadProc_0__32768__::_1_::catch$4

- ea: `0x18001bb81`
- end: `0x18001bbdc`
- name: `_CFciPropertiesShellExt::ThreadProcStatic__CFciPropertiesShellExt::InitializeThreadProc_0__32768__::_1_::catch$4`
- size: `91`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180017ad0`

## string_xrefs

- `0x18001bba0`: `CFciPropertiesShellExt::ThreadProcStatic`

## pseudocode

```c
void __fastcall __noreturn CFciPropertiesShellExt::ThreadProcStatic__CFciPropertiesShellExt::InitializeThreadProc_0__32768__::_1_::catch_4(
        __int64 a1,
        __int64 a2)
{
  CSrmFunctionTracer::HandleComException(
    (CSrmFunctionTracer *)(a2 + 272),
    *(struct _com_error **)(a2 + 104),
    L"base\\fs\\fsrm\\clients\\srmshell\\fciprops.h",
    L"FCIPROPH",
    L"CFciPropertiesShellExt::ThreadProcStatic",
    0x42Du,
    *(_DWORD *)(a2 + 316));
}

```

## disassembly

```asm
0x18001bb81  mov     [rsp+arg_8], rdx
0x18001bb86  push    rbp
0x18001bb87  sub     rsp, 40h
0x18001bb8b  mov     rbp, rdx
0x18001bb8e  mov     eax, [rbp+13Ch]
0x18001bb94  mov     [rsp+48h+var_18], eax; unsigned int
0x18001bb98  mov     [rsp+48h+var_20], 42Dh; unsigned int
0x18001bba0  lea     rax, aCfciproperties_0; "CFciPropertiesShellExt::ThreadProcStati"...
0x18001bba7  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x18001bbac  lea     r9, aFciproph; "FCIPROPH"
0x18001bbb3  lea     r8, aBaseFsFsrmClie_0; "base\\fs\\fsrm\\clients\\srmshell\\fcip"...
0x18001bbba  mov     rdx, [rbp+68h]; struct _com_error *
0x18001bbbe  lea     rcx, [rbp+110h]; this
0x18001bbc5  call    ?HandleComException@CSrmFunctionTracer@@QEAAXAEAV_com_error@@PEBG11KK@Z; CSrmFunctionTracer::HandleComException(_com_error &,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x18001bbcb  mov     rax, 0
0x18001bbd5  add     rsp, 40h
0x18001bbd9  pop     rbp
0x18001bbda  retn
```
