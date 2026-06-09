# WPP_SF_qd

- ea: `0x18000ea08`
- end: `0x18000ea4f`
- name: `WPP_SF_qd`
- size: `71`
- prototype: `ULONG(TRACEHANDLE, USHORT, const GUID *, ...)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x1800031b0`
- `0x180003ad0`
- `0x180005dc0`
- `0x1800060b0`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000ea44`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000ea44`

## pseudocode

```c
ULONG WPP_SF_qd(TRACEHANDLE a1, USHORT a2, const GUID *a3, ...)
{
  __int64 v4; // [rsp+78h] [rbp+20h] BYREF
  va_list va; // [rsp+78h] [rbp+20h]
  va_list va1; // [rsp+80h] [rbp+28h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v4 = va_arg(va1, _QWORD);
  return TraceMessage(a1, 0x2Bu, a3, a2, va, 8, va1, 4, 0);
}

```

## disassembly

```asm
0x18000ea08  mov     r11, rsp
0x18000ea0b  mov     [r11+20h], r9
0x18000ea0f  sub     rsp, 58h
0x18000ea13  mov     qword ptr [r11-18h], 0
0x18000ea1b  lea     rax, [r11+28h]
0x18000ea1f  mov     qword ptr [r11-20h], 4
0x18000ea27  mov     [r11-28h], rax
0x18000ea2b  lea     rax, [r11+20h]
0x18000ea2f  movzx   r9d, dx; MessageNumber
0x18000ea33  mov     edx, 2Bh ; '+'; MessageFlags
0x18000ea38  mov     qword ptr [r11-30h], 8
0x18000ea40  mov     [r11-38h], rax
0x18000ea44  call    cs:__imp_TraceMessage
0x18000ea4a  add     rsp, 58h
0x18000ea4e  retn
```
