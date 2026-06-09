# WPP_SF_sSSd

- ea: `0x180047c64`
- end: `0x180047cd8`
- name: `WPP_SF_sSSd`
- size: `116`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, loader_planting`

## callers

- `0x180047a60`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x180047ccd`
- `ADVAPI32!TraceMessage` at `0x180047ccd`

## string_xrefs

- `0x180047ca3`: `iasmigplugin.dll`
- `0x180047c98`: `IDR_NAPPROPSMIG_XML_RES_XML`

## pseudocode

```c
ULONG WPP_SF_sSSd(TRACEHANDLE a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5, __int64 a6, ...)
{
  va_list va; // [rsp+B0h] [rbp+38h] BYREF

  va_start(va, a6);
  return TraceMessage(
           a1,
           0x2Bu,
           &WPP_a89d8cb01d6b390d91c3212b6347ecab_Traceguids,
           0x13u,
           "NPSDS",
           6,
           L"iasmigplugin.dll",
           34,
           L"IDR_NAPPROPSMIG_XML_RES_XML",
           56,
           va,
           4,
           0);
}

```

## disassembly

```asm
0x180047c64  mov     r11, rsp
0x180047c67  sub     rsp, 78h
0x180047c6b  mov     qword ptr [r11-18h], 0
0x180047c73  lea     rax, [r11+38h]
0x180047c77  mov     qword ptr [r11-20h], 4
0x180047c7f  lea     r8, WPP_a89d8cb01d6b390d91c3212b6347ecab_Traceguids; MessageGuid
0x180047c86  mov     [r11-28h], rax
0x180047c8a  mov     r9d, 13h; MessageNumber
0x180047c90  mov     qword ptr [r11-30h], 38h ; '8'
0x180047c98  lea     rax, aIdrNappropsmig; "IDR_NAPPROPSMIG_XML_RES_XML"
0x180047c9f  mov     [r11-38h], rax
0x180047ca3  lea     rax, aIasmigpluginDl; "iasmigplugin.dll"
0x180047caa  mov     qword ptr [r11-40h], 22h ; '"'
0x180047cb2  mov     [r11-48h], rax
0x180047cb6  lea     edx, [r9+18h]; MessageFlags
0x180047cba  lea     rax, aNpsds; "NPSDS"
0x180047cc1  mov     qword ptr [r11-50h], 6
0x180047cc9  mov     [r11-58h], rax
0x180047ccd  call    cs:__imp_TraceMessage
0x180047cd3  add     rsp, 78h
0x180047cd7  retn
```
