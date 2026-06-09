# WPP_SF_sD

- ea: `0x14002c6e4`
- end: `0x14002c731`
- name: `WPP_SF_sD`
- size: `77`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x1400203a8`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x14002c726`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x14002c726`

## string_xrefs

- `0x14002c70a`: `ChannelConfigException`

## pseudocode

```c
ULONG WPP_SF_sD(TRACEHANDLE a1, USHORT a2, __int64 a3, __int64 a4, ...)
{
  va_list va; // [rsp+80h] [rbp+28h] BYREF

  va_start(va, a4);
  return TraceMessage(
           a1,
           0x2Bu,
           &WPP_dcf685af8c5436a5470889b599bac37f_Traceguids,
           a2,
           "ChannelConfigException",
           23,
           va,
           4,
           0);
}

```

## disassembly

```asm
0x14002c6e4  mov     r11, rsp
0x14002c6e7  sub     rsp, 58h
0x14002c6eb  mov     qword ptr [r11-18h], 0
0x14002c6f3  lea     rax, [r11+28h]
0x14002c6f7  mov     qword ptr [r11-20h], 4
0x14002c6ff  lea     r8, WPP_dcf685af8c5436a5470889b599bac37f_Traceguids; MessageGuid
0x14002c706  mov     [r11-28h], rax
0x14002c70a  lea     rax, aChannelconfige; "ChannelConfigException"
0x14002c711  movzx   r9d, dx; MessageNumber
0x14002c715  mov     edx, 2Bh ; '+'; MessageFlags
0x14002c71a  mov     qword ptr [r11-30h], 17h
0x14002c722  mov     [r11-38h], rax
0x14002c726  call    cs:__imp_TraceMessage
0x14002c72c  add     rsp, 58h
0x14002c730  retn
```
