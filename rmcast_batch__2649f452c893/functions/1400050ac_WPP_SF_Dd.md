# WPP_SF_Dd

- ea: `0x1400050ac`
- end: `0x1400050f7`
- name: `WPP_SF_Dd`
- size: `75`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `42`
- callee_count: `1`
- tags: ``

## callers

- `0x140001030`
- `0x140001178`
- `0x140002048`
- `0x140002878`
- `0x140002a24`
- `0x140002b44`
- `0x140002cc4`
- `0x140002f28`
- `0x14000313c`
- `0x1400032c8`
- `0x140003448`
- `0x1400039b4`
- `0x140003c14`
- `0x140003dbc`
- `0x140003f10`
- `0x1400040e8`
- `0x1400042c4`
- `0x1400044b0`
- `0x140004620`
- `0x140004778`
- `0x140004b50`
- `0x140004dc0`
- `0x140006cc4`
- `0x14000b0b0`
- `0x14000c300`
- `0x14000ca08`
- `0x14000ec50`
- `0x14000f2d8`
- `0x14000fe74`
- `0x1400114e0`
- `0x1400120b4`
- `0x1400124cc`
- `0x140012efc`
- `0x140014540`
- `0x1400163e4`
- `0x140017300`
- `0x140017658`
- `0x14001a6d0`
- `0x14001ab38`
- `0x14001b8f8`
- `0x14001bcec`
- `0x140036008`

## callees

- `0x14001ce30`

## pseudocode

```c
__int64 WPP_SF_Dd(__int64 a1, unsigned __int16 a2, __int64 a3, int a4, ...)
{
  int v5; // [rsp+78h] [rbp+20h] BYREF
  va_list va; // [rsp+80h] [rbp+28h] BYREF

  va_start(va, a4);
  v5 = a4;
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD, int *, __int64, __int64 *, __int64, _QWORD))pfnWppTraceMessage)(
           a1,
           43,
           a3,
           a2,
           &v5,
           4,
           (__int64 *)va,
           4,
           0);
}

```

## disassembly

```asm
0x1400050ac  mov     r11, rsp
0x1400050af  mov     [r11+20h], r9d
0x1400050b3  sub     rsp, 58h
0x1400050b7  mov     rax, cs:pfnWppTraceMessage
0x1400050be  lea     r9, [r11+28h]
0x1400050c2  mov     qword ptr [r11-18h], 0
0x1400050ca  mov     r10d, 4
0x1400050d0  mov     [r11-20h], r10
0x1400050d4  mov     [r11-28h], r9
0x1400050d8  lea     r9, [r11+20h]
0x1400050dc  mov     [r11-30h], r10
0x1400050e0  mov     [r11-38h], r9
0x1400050e4  movzx   r9d, dx
0x1400050e8  lea     edx, [r10+27h]
0x1400050ec  call    _guard_dispatch_icall
0x1400050f1  add     rsp, 58h
0x1400050f5  retn
```
