# WPP_SF_Dd

- ea: `0x18000b89c`
- end: `0x18000b8e1`
- name: `WPP_SF_Dd`
- size: `69`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `34`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180005310`
- `0x180005a38`
- `0x180006670`
- `0x180006a90`
- `0x180006d20`
- `0x180007b50`
- `0x180008f00`
- `0x180009480`
- `0x1800099d0`
- `0x18000a370`
- `0x18000ca80`
- `0x18000ce10`
- `0x180010028`
- `0x180010770`
- `0x1800113c8`
- `0x18001171c`
- `0x1800134d8`
- `0x18001507c`
- `0x180017624`
- `0x18001ca70`
- `0x18001db70`
- `0x18001dcb4`
- `0x18002097c`
- `0x1800229b0`
- `0x180023960`
- `0x180023cd4`
- `0x180026b70`
- `0x180027aa0`
- `0x180027f30`
- `0x180028584`
- `0x180028680`
- `0x180029134`
- `0x180029310`
- `0x1800297e4`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x18000b8d6`
- `ntdll!EtwTraceMessage` at `0x18000b8d6`

## pseudocode

```c
__int64 __fastcall WPP_SF_Dd(__int64 a1, unsigned __int16 a2, __int64 a3, int a4)
{
  int v5; // [rsp+78h] [rbp+20h] BYREF

  v5 = a4;
  return EtwTraceMessage(a1, 43, a3, a2, &v5);
}

```

## disassembly

```asm
0x18000b89c  mov     r11, rsp
0x18000b89f  mov     [r11+20h], r9d
0x18000b8a3  sub     rsp, 58h
0x18000b8a7  mov     qword ptr [r11-18h], 0
0x18000b8af  lea     rax, [r11+28h]
0x18000b8b3  mov     r9d, 4
0x18000b8b9  mov     [r11-20h], r9
0x18000b8bd  mov     [r11-28h], rax
0x18000b8c1  lea     rax, [r11+20h]
0x18000b8c5  mov     [r11-30h], r9
0x18000b8c9  movzx   r9d, dx
0x18000b8cd  mov     edx, 2Bh ; '+'
0x18000b8d2  mov     [r11-38h], rax
0x18000b8d6  call    cs:__imp_EtwTraceMessage
0x18000b8dc  add     rsp, 58h
0x18000b8e0  retn
```
