# WPP_SF_ddddddddd

- ea: `0x18000a284`
- end: `0x18000a32f`
- name: `WPP_SF_ddddddddd`
- size: `171`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180002a00`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x18000a321`
- `ntdll!EtwTraceMessage` at `0x18000a321`

## pseudocode

```c
__int64 __fastcall WPP_SF_ddddddddd(__int64 a1, unsigned __int16 a2, __int64 a3, int a4)
{
  int v5; // [rsp+E8h] [rbp+20h] BYREF

  v5 = a4;
  return EtwTraceMessage(a1, 43, WPP_6bd4623f25de30d5bdcfadbe3b7ae59e_Traceguids, a2, &v5);
}

```

## disassembly

```asm
0x18000a284  mov     r11, rsp
0x18000a287  mov     [r11+20h], r9d
0x18000a28b  sub     rsp, 0C8h
0x18000a292  mov     qword ptr [r11-18h], 0
0x18000a29a  lea     rax, [r11+60h]
0x18000a29e  mov     r8d, 4
0x18000a2a4  movzx   r9d, dx
0x18000a2a8  mov     [r11-20h], r8
0x18000a2ac  mov     edx, 2Bh ; '+'
0x18000a2b1  mov     [r11-28h], rax
0x18000a2b5  lea     rax, [r11+58h]
0x18000a2b9  mov     [r11-30h], r8
0x18000a2bd  mov     [r11-38h], rax
0x18000a2c1  lea     rax, [r11+50h]
0x18000a2c5  mov     [r11-40h], r8
0x18000a2c9  mov     [r11-48h], rax
0x18000a2cd  lea     rax, [r11+48h]
0x18000a2d1  mov     [r11-50h], r8
0x18000a2d5  mov     [r11-58h], rax
0x18000a2d9  lea     rax, [r11+40h]
0x18000a2dd  mov     [r11-60h], r8
0x18000a2e1  mov     [r11-68h], rax
0x18000a2e5  lea     rax, [r11+38h]
0x18000a2e9  mov     [r11-70h], r8
0x18000a2ed  mov     [r11-78h], rax
0x18000a2f1  lea     rax, [r11+30h]
0x18000a2f5  mov     [r11-80h], r8
0x18000a2f9  mov     [rsp+0C8h+var_88], rax
0x18000a2fe  lea     rax, [r11+28h]
0x18000a302  mov     [rsp+0C8h+var_90], r8
0x18000a307  mov     [rsp+0C8h+var_98], rax
0x18000a30c  lea     rax, [r11+20h]
0x18000a310  mov     [rsp+0C8h+var_A0], r8
0x18000a315  lea     r8, WPP_6bd4623f25de30d5bdcfadbe3b7ae59e_Traceguids
0x18000a31c  mov     [rsp+0C8h+var_A8], rax
0x18000a321  call    cs:__imp_EtwTraceMessage
0x18000a327  add     rsp, 0C8h
0x18000a32e  retn
```
