# WPP_SF_DD

- ea: `0x18000aa70`
- end: `0x18000aab5`
- name: `WPP_SF_DD`
- size: `69`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `10`
- callee_count: `0`
- tags: ``

## callers

- `0x180007aa8`
- `0x18000a768`
- `0x18000d294`
- `0x180011414`
- `0x180011578`
- `0x180011664`
- `0x180011710`
- `0x180011820`
- `0x180011a10`
- `0x18001250c`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000aaaa`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000aaaa`

## pseudocode

```c
ULONG WPP_SF_DD(TRACEHANDLE a1, USHORT a2, const GUID *a3, int a4, ...)
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
0x18000aa70  mov     r11, rsp
0x18000aa73  mov     [r11+20h], r9d
0x18000aa77  sub     rsp, 58h
0x18000aa7b  mov     qword ptr [r11-18h], 0
0x18000aa83  lea     rax, [r11+28h]
0x18000aa87  mov     r9d, 4
0x18000aa8d  mov     [r11-20h], r9
0x18000aa91  mov     [r11-28h], rax
0x18000aa95  lea     rax, [r11+20h]
0x18000aa99  mov     [r11-30h], r9
0x18000aa9d  movzx   r9d, dx; MessageNumber
0x18000aaa1  mov     edx, 2Bh ; '+'; MessageFlags
0x18000aaa6  mov     [r11-38h], rax
0x18000aaaa  call    cs:__imp_TraceMessage
0x18000aab0  add     rsp, 58h
0x18000aab4  retn
```
