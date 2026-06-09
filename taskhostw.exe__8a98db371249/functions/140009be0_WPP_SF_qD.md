# WPP_SF_qD

- ea: `0x140009be0`
- end: `0x140009c27`
- name: `WPP_SF_qD`
- size: `71`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `7`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x140003f10`
- `0x140004940`
- `0x140004a30`
- `0x140004cf0`
- `0x140004ec0`
- `0x140005150`
- `0x1400067a0`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x140009c1c`
- `ntdll!EtwTraceMessage` at `0x140009c1c`

## pseudocode

```c
__int64 WPP_SF_qD(__int64 a1, unsigned __int16 a2, __int64 a3, ...)
{
  __int64 v4; // [rsp+78h] [rbp+20h] BYREF
  va_list va; // [rsp+78h] [rbp+20h]
  va_list va1; // [rsp+80h] [rbp+28h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v4 = va_arg(va1, _QWORD);
  return EtwTraceMessage(a1, 43, a3, a2, (__int64 *)va, 8, va1, 4, 0);
}

```

## disassembly

```asm
0x140009be0  mov     r11, rsp
0x140009be3  mov     [r11+20h], r9
0x140009be7  sub     rsp, 58h
0x140009beb  mov     qword ptr [r11-18h], 0
0x140009bf3  lea     rax, [r11+28h]
0x140009bf7  mov     qword ptr [r11-20h], 4
0x140009bff  mov     [r11-28h], rax
0x140009c03  lea     rax, [r11+20h]
0x140009c07  movzx   r9d, dx
0x140009c0b  mov     edx, 2Bh ; '+'
0x140009c10  mov     qword ptr [r11-30h], 8
0x140009c18  mov     [r11-38h], rax
0x140009c1c  call    cs:__imp_EtwTraceMessage
0x140009c22  add     rsp, 58h
0x140009c26  retn
```
