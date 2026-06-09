# SclRegEnumerateValueKey

- ea: `0x18000923c`
- end: `0x180009280`
- name: `SclRegEnumerateValueKey`
- size: `68`
- prototype: `__int64 __fastcall(__int64, int, int, int, __int64, __int64)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18000548c`
- `0x180007fb0`
- `0x180008ff0`
- `0x18000b530`
- `0x18000d620`

## callees

- `0x180007ee4`

## pseudocode

```c
__int64 __fastcall SclRegEnumerateValueKey(__int64 a1, int a2, int a3, int a4, __int64 a5, __int64 a6)
{
  __int64 v7; // [rsp+30h] [rbp-18h] BYREF
  int v8; // [rsp+38h] [rbp-10h]
  int v9; // [rsp+3Ch] [rbp-Ch]

  v7 = a1;
  v8 = a2;
  v9 = a3;
  return SclEnumerateAndReallocate((unsigned int)&SclRegEnumerateValueKey_Callback, (unsigned int)&v7, a4, a5, 0, a6);
}

```

## disassembly

```asm
0x18000923c  mov     r11, rsp
0x18000923f  sub     rsp, 48h
0x180009243  mov     rax, [rsp+48h+arg_28]
0x180009248  mov     r10, r9
0x18000924b  mov     r9, [rsp+48h+arg_20]
0x180009250  mov     [r11-18h], rcx
0x180009254  lea     rcx, SclRegEnumerateValueKey_Callback
0x18000925b  mov     [rsp+48h+var_10], edx
0x18000925f  lea     rdx, [r11-18h]
0x180009263  mov     [r11-0Ch], r8d
0x180009267  mov     r8, r10
0x18000926a  mov     [r11-20h], rax
0x18000926e  mov     [rsp+48h+var_28], 0
0x180009276  call    SclEnumerateAndReallocate
0x18000927b  add     rsp, 48h
0x18000927f  retn
```
