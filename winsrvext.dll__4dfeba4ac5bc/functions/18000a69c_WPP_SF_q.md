# WPP_SF_q

- ea: `0x18000a69c`
- end: `0x18000a6da`
- name: `WPP_SF_q`
- size: `62`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180006660`
- `0x180010db0`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000a6c8`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000a6c8`

## pseudocode

```c
ULONG WPP_SF_q(TRACEHANDLE a1, USHORT a2, const GUID *a3, ...)
{
  va_list va; // [rsp+68h] [rbp+20h] BYREF

  va_start(va, a3);
  return TraceMessage(a1, 0x2Bu, a3, a2, va, 8, 0);
}

```

## disassembly

```asm
0x18000a69c  mov     r11, rsp
0x18000a69f  mov     [r11+20h], r9
0x18000a6a3  sub     rsp, 48h
0x18000a6a7  mov     qword ptr [r11-18h], 0
0x18000a6af  lea     rax, [r11+20h]
0x18000a6b3  movzx   r9d, dx; MessageNumber
0x18000a6b7  mov     edx, 2Bh ; '+'; MessageFlags
0x18000a6bc  mov     qword ptr [r11-20h], 8
0x18000a6c4  mov     [r11-28h], rax
0x18000a6c8  call    cs:__imp_TraceMessage
0x18000a6cf  nop     dword ptr [rax+rax+00h]
0x18000a6d4  add     rsp, 48h
0x18000a6d8  retn
```
