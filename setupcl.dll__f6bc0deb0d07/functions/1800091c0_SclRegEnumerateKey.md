# SclRegEnumerateKey

- ea: `0x1800091c0`
- end: `0x180009208`
- name: `SclRegEnumerateKey`
- size: `72`
- prototype: `__int64 __fastcall(__int64, int, __int64, int, __int64, int, __int64)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180007fb0`
- `0x180008e40`
- `0x18000b21c`
- `0x18000bc68`
- `0x18000d620`

## callees

- `0x180007ee4`

## pseudocode

```c
__int64 __fastcall SclRegEnumerateKey(__int64 a1, int a2, __int64 a3, int a4, __int64 a5, int a6, __int64 a7)
{
  __int64 v8; // [rsp+30h] [rbp-18h] BYREF
  int v9; // [rsp+38h] [rbp-10h]
  int v10; // [rsp+3Ch] [rbp-Ch]

  v8 = a1;
  v9 = a2;
  v10 = 0;
  return SclEnumerateAndReallocate((unsigned int)&SclRegEnumerateKey_Callback, (unsigned int)&v8, a4, a5, a6, a7);
}

```

## disassembly

```asm
0x1800091c0  sub     rsp, 48h
0x1800091c4  mov     rax, [rsp+48h+arg_30]
0x1800091cc  mov     r8, r9
0x1800091cf  mov     r9, [rsp+48h+arg_20]
0x1800091d4  mov     [rsp+48h+var_20], rax
0x1800091d9  mov     eax, [rsp+48h+arg_28]
0x1800091dd  mov     [rsp+48h+var_18], rcx
0x1800091e2  lea     rcx, SclRegEnumerateKey_Callback
0x1800091e9  mov     [rsp+48h+var_10], edx
0x1800091ed  lea     rdx, [rsp+48h+var_18]
0x1800091f2  mov     [rsp+48h+var_28], eax
0x1800091f6  mov     [rsp+48h+var_C], 0
0x1800091fe  call    SclEnumerateAndReallocate
0x180009203  add     rsp, 48h
0x180009207  retn
```
