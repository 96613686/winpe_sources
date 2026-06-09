# WPP_SF_Dd

- ea: `0x1800053ec`
- end: `0x180005431`
- name: `WPP_SF_Dd`
- size: `69`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `10`
- callee_count: `0`
- tags: ``

## callers

- `0x180002e64`
- `0x180003ef8`
- `0x180005060`
- `0x180005260`
- `0x180005a30`
- `0x180006d80`
- `0x180006f60`
- `0x180008690`
- `0x180008810`
- `0x18000a8ac`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x180005426`
- `ADVAPI32!TraceMessage` at `0x180005426`

## pseudocode

```c
ULONG WPP_SF_Dd(TRACEHANDLE a1, USHORT a2, const GUID *a3, int a4, ...)
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
0x1800053ec  mov     r11, rsp
0x1800053ef  mov     [r11+20h], r9d
0x1800053f3  sub     rsp, 58h
0x1800053f7  mov     qword ptr [r11-18h], 0
0x1800053ff  lea     rax, [r11+28h]
0x180005403  mov     r9d, 4
0x180005409  mov     [r11-20h], r9
0x18000540d  mov     [r11-28h], rax
0x180005411  lea     rax, [r11+20h]
0x180005415  mov     [r11-30h], r9
0x180005419  movzx   r9d, dx; MessageNumber
0x18000541d  mov     edx, 2Bh ; '+'; MessageFlags
0x180005422  mov     [r11-38h], rax
0x180005426  call    cs:__imp_TraceMessage
0x18000542c  add     rsp, 58h
0x180005430  retn
```
