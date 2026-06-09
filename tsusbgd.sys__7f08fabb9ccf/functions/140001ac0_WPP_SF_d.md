# WPP_SF_d

- ea: `0x140001ac0`
- end: `0x140001afe`
- name: `WPP_SF_d`
- size: `62`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `17`
- callee_count: `1`
- tags: ``

## callers

- `0x140001464`
- `0x140001998`
- `0x140001b50`
- `0x140001f8c`
- `0x140002228`
- `0x140002318`
- `0x1400025bc`
- `0x1400027e4`
- `0x140002978`
- `0x140002c60`
- `0x140003118`
- `0x140003368`
- `0x140003610`
- `0x1400037d0`
- `0x14000491c`
- `0x14000c010`
- `0x14000d03c`

## callees

- `0x140006370`

## pseudocode

```c
__int64 __fastcall WPP_SF_d(__int64 a1, unsigned __int16 a2, __int64 a3, int a4)
{
  int v5; // [rsp+68h] [rbp+20h] BYREF

  v5 = a4;
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD, int *, __int64, _QWORD))pfnWppTraceMessage)(
           a1,
           43,
           a3,
           a2,
           &v5,
           4,
           0);
}

```

## disassembly

```asm
0x140001ac0  mov     r11, rsp
0x140001ac3  mov     [r11+20h], r9d
0x140001ac7  sub     rsp, 48h
0x140001acb  mov     rax, cs:pfnWppTraceMessage
0x140001ad2  lea     r9, [r11+20h]
0x140001ad6  mov     qword ptr [r11-18h], 0
0x140001ade  mov     qword ptr [r11-20h], 4
0x140001ae6  mov     [r11-28h], r9
0x140001aea  movzx   r9d, dx
0x140001aee  mov     edx, 2Bh ; '+'
0x140001af3  call    _guard_dispatch_icall
0x140001af8  add     rsp, 48h
0x140001afc  retn
```
