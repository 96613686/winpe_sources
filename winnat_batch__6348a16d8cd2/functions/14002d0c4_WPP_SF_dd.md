# WPP_SF_dd

- ea: `0x14002d0c4`
- end: `0x14002d102`
- name: `WPP_SF_dd`
- size: `62`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x140007bb0`
- `0x1400080a8`
- `0x14000820c`
- `0x14000a680`
- `0x14001492c`
- `0x14002e220`
- `0x140033cc8`

## callees

- `0x140018408`

## pseudocode

```c
void WPP_SF_dd(__int16 a1, USHORT a2, ULONGLONG a3, int a4, ...)
{
  int v4; // [rsp+68h] [rbp+20h] BYREF
  va_list va; // [rsp+70h] [rbp+28h] BYREF

  va_start(va, a4);
  v4 = a4;
  FastWppTraceMessage(a1, a2, a3, &v4, 4, va, 4, 0);
}

```

## disassembly

```asm
0x14002d0c4  mov     r11, rsp
0x14002d0c7  mov     [r11+20h], r9d
0x14002d0cb  sub     rsp, 48h
0x14002d0cf  mov     qword ptr [r11-10h], 0
0x14002d0d7  lea     rax, [r11+28h]
0x14002d0db  mov     r9d, 4
0x14002d0e1  movzx   edx, dx
0x14002d0e4  mov     [r11-18h], r9
0x14002d0e8  mov     [r11-20h], rax
0x14002d0ec  mov     [r11-28h], r9
0x14002d0f0  lea     r9, [r11+20h]
0x14002d0f4  movzx   ecx, cx
0x14002d0f7  call    FastWppTraceMessage
0x14002d0fc  add     rsp, 48h
0x14002d100  retn
```
