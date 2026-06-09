# WinHvSetPartitionProperty

- ea: `0x14001b010`
- end: `0x14001b07d`
- name: `WinHvSetPartitionProperty`
- size: `109`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1400048f0`
- `0x140009190`
- `0x1400252a0`

## callees

- `0x140001ef0`
- `0x140009c50`

## pseudocode

```c
__int64 __fastcall WinHvSetPartitionProperty(__int64 a1, int a2, __int64 a3)
{
  __int64 v4; // [rsp+40h] [rbp-28h] BYREF
  int v5; // [rsp+48h] [rbp-20h]
  int v6; // [rsp+4Ch] [rbp-1Ch]
  __int64 v7; // [rsp+50h] [rbp-18h]

  v6 = 0;
  v4 = a1;
  v5 = a2;
  v7 = a3;
  return WinHvpAllocatingHypercall(a1, 0x8000FFFF, 69, a2 == 327692, &v4, 0x18u, 0, 0);
}

```

## disassembly

```asm
0x14001b010  mov     r11, rsp
0x14001b013  sub     rsp, 68h
0x14001b017  mov     rax, cs:__security_cookie
0x14001b01e  xor     rax, rsp
0x14001b021  mov     [rsp+68h+var_10], rax
0x14001b026  xor     eax, eax
0x14001b028  mov     [r11-30h], rax
0x14001b02c  cmp     edx, 5000Ch
0x14001b032  mov     [rsp+68h+var_1C], eax
0x14001b036  mov     [r11-38h], rax
0x14001b03a  setz    r9b; int
0x14001b03e  mov     [r11-28h], rcx
0x14001b042  lea     rax, [r11-28h]
0x14001b046  mov     [rsp+68h+var_20], edx
0x14001b04a  mov     edx, 8000FFFFh; int
0x14001b04f  mov     [r11-18h], r8
0x14001b053  mov     r8d, 45h ; 'E'; int
0x14001b059  mov     qword ptr [r11-40h], 18h
0x14001b061  mov     [r11-48h], rax
0x14001b065  call    WinHvpAllocatingHypercall
0x14001b06a  mov     rcx, [rsp+68h+var_10]
0x14001b06f  xor     rcx, rsp; StackCookie
0x14001b072  call    __security_check_cookie
0x14001b077  add     rsp, 68h
0x14001b07b  retn
```
