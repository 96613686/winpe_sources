# WPP_SF_dd

- ea: `0x18000e1b8`
- end: `0x18000e1fd`
- name: `WPP_SF_dd`
- size: `69`
- prototype: `ULONG(TRACEHANDLE, USHORT, const GUID *, int, ...)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x1800018c0`
- `0x1800031b0`
- `0x1800038d0`
- `0x180004c50`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000e1f2`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000e1f2`

## pseudocode

```c
ULONG WPP_SF_dd(TRACEHANDLE a1, USHORT a2, const GUID *a3, int a4, ...)
{
  int v5; // [rsp+78h] [rbp+20h] BYREF
  va_list va; // [rsp+80h] [rbp+28h] BYREF

  va_start(va, a4);
  v5 = a4;
  return TraceMessage(a1, 0x2Bu, a3, a2, &v5, 4, va, 4, 0);
}

```

## disassembly

```asm
0x18000e1b8  mov     r11, rsp
0x18000e1bb  mov     [r11+20h], r9d
0x18000e1bf  sub     rsp, 58h
0x18000e1c3  mov     qword ptr [r11-18h], 0
0x18000e1cb  lea     rax, [r11+28h]
0x18000e1cf  mov     r9d, 4
0x18000e1d5  mov     [r11-20h], r9
0x18000e1d9  mov     [r11-28h], rax
0x18000e1dd  lea     rax, [r11+20h]
0x18000e1e1  mov     [r11-30h], r9
0x18000e1e5  movzx   r9d, dx; MessageNumber
0x18000e1e9  mov     edx, 2Bh ; '+'; MessageFlags
0x18000e1ee  mov     [r11-38h], rax
0x18000e1f2  call    cs:__imp_TraceMessage
0x18000e1f8  add     rsp, 58h
0x18000e1fc  retn
```
