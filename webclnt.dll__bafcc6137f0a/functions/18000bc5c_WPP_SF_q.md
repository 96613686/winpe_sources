# WPP_SF_q

- ea: `0x18000bc5c`
- end: `0x18000bc93`
- name: `WPP_SF_q`
- size: `55`
- prototype: `__int64(__int64, unsigned __int16, __int64, ...)`
- caller_count: `22`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180003cbc`
- `0x180003f8c`
- `0x18000c7a4`
- `0x18000d9e4`
- `0x1800103a4`
- `0x180010478`
- `0x180010770`
- `0x180010b08`
- `0x180010c48`
- `0x1800112dc`
- `0x180012468`
- `0x180016d24`
- `0x18001832c`
- `0x1800196d0`
- `0x18001f190`
- `0x1800229b0`
- `0x180023360`
- `0x180023960`
- `0x180025330`
- `0x18002a964`
- `0x18002ae00`
- `0x18002be24`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x18000bc88`
- `ntdll!EtwTraceMessage` at `0x18000bc88`

## pseudocode

```c
__int64 WPP_SF_q(__int64 a1, unsigned __int16 a2, __int64 a3, ...)
{
  va_list va; // [rsp+68h] [rbp+20h] BYREF

  va_start(va, a3);
  return EtwTraceMessage(a1, 43, a3, a2, (__int64 *)va);
}

```

## disassembly

```asm
0x18000bc5c  mov     r11, rsp
0x18000bc5f  mov     [r11+20h], r9
0x18000bc63  sub     rsp, 48h
0x18000bc67  mov     qword ptr [r11-18h], 0
0x18000bc6f  lea     rax, [r11+20h]
0x18000bc73  movzx   r9d, dx
0x18000bc77  mov     edx, 2Bh ; '+'
0x18000bc7c  mov     qword ptr [r11-20h], 8
0x18000bc84  mov     [r11-28h], rax
0x18000bc88  call    cs:__imp_EtwTraceMessage
0x18000bc8e  add     rsp, 48h
0x18000bc92  retn
```
