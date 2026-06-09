# WPP_SF_D

- ea: `0x180002ad4`
- end: `0x180002b19`
- name: `WPP_SF_D`
- size: `69`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180002750`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180002b0e`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180002b0e`

## pseudocode

```c
ULONG __fastcall WPP_SF_D(TRACEHANDLE a1)
{
  int v2[6]; // [rsp+40h] [rbp-18h] BYREF

  v2[0] = g_cDllRefs;
  return TraceMessage(a1, 0x2Bu, &WPP_18a2193733963c00b13dba0ff53a5177_Traceguids, 0xAu, v2, 4, 0);
}

```

## disassembly

```asm
0x180002ad4  mov     r11, rsp
0x180002ad7  sub     rsp, 58h
0x180002adb  mov     eax, cs:?g_cDllRefs@@3JA; long g_cDllRefs
0x180002ae1  lea     r8, WPP_18a2193733963c00b13dba0ff53a5177_Traceguids; MessageGuid
0x180002ae8  mov     qword ptr [r11-28h], 0
0x180002af0  mov     r9d, 0Ah; MessageNumber
0x180002af6  mov     [rsp+58h+var_18], eax
0x180002afa  lea     rax, [r11-18h]
0x180002afe  mov     qword ptr [r11-30h], 4
0x180002b06  mov     [r11-38h], rax
0x180002b0a  lea     edx, [r9+21h]; MessageFlags
0x180002b0e  call    cs:__imp_TraceMessage
0x180002b14  add     rsp, 58h
0x180002b18  retn
```
