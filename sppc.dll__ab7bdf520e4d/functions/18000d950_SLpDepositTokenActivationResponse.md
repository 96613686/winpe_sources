# SLpDepositTokenActivationResponse

- ea: `0x18000d950`
- end: `0x18000dad4`
- name: `SLpDepositTokenActivationResponse`
- size: `388`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, unsigned int, __int64)`
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x180001760`
- `0x180001ec0`
- `0x180002bf0`
- `0x1800044dc`
- `0x180004f44`
- `0x180004f80`
- `0x180005208`
- `0x180006844`
- `0x18000a8d0`
- `0x18000d950`
- `0x18000f114`

## pseudocode

```c
__int64 __fastcall SLpDepositTokenActivationResponse(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        unsigned int a5,
        __int64 a6)
{
  unsigned int v10; // ebx
  __int64 v11; // rcx
  int v12; // eax
  int v13; // eax
  __int64 v15[2]; // [rsp+30h] [rbp-20h] BYREF
  __int128 v16; // [rsp+40h] [rbp-10h] BYREF
  unsigned int v17; // [rsp+80h] [rbp+30h] BYREF

  v17 = a3;
  v15[0] = (__int64)&v16 + 8;
  v15[1] = (__int64)&v16;
  v16 = 0;
  if ( !a1 )
  {
    v10 = -2147024809;
    sub_180001760(qword_180018AE8, byte_18001ED20);
LABEL_3:
    v11 = 2147942487LL;
LABEL_18:
    sub_180006844(v11);
    goto LABEL_19;
  }
  sub_180002BF0(byte_180018738, &dword_18001E8FC);
  if ( !a2 || !a3 || !a4 || !a5 || !a6 )
  {
    v10 = -2147024809;
    goto LABEL_3;
  }
  v12 = sub_180004F44(v15, 1, a2);
  v10 = v12;
  if ( v12 < 0 )
    goto LABEL_17;
  v13 = sub_180004F80(v15, 2, &v17);
  v10 = v13;
  if ( v13 < 0 )
  {
    sub_180006844((unsigned int)v13);
    sub_180001EC0(&dword_180018BE4, qword_18001E828);
    goto LABEL_19;
  }
  v12 = sub_18000F114(v15, 3, v17, a4);
  v10 = v12;
  if ( v12 < 0
    || (v12 = sub_180004F80(v15, 4, &a5), v10 = v12, v12 < 0)
    || (v12 = sub_18000F114(v15, 5, a5, a6), v10 = v12, v12 < 0)
    || (v12 = sub_1800044DC(v15, a1, 0x2Eu, 0, 1), v10 = v12, v12 < 0) )
  {
LABEL_17:
    v11 = (unsigned int)v12;
    goto LABEL_18;
  }
LABEL_19:
  sub_18000A8D0(v10);
  sub_180005208(v15);
  return v10;
}

```

## disassembly

```asm
0x18000d950  mov     [rsp-18h+arg_0], rbx
0x18000d955  mov     [rsp-18h+arg_8], rsi
0x18000d95a  mov     [rsp-18h+arg_10], r8d
0x18000d95f  push    rbp
0x18000d960  push    r14
0x18000d962  push    r15
0x18000d964  mov     rbp, rsp
0x18000d967  sub     rsp, 50h
0x18000d96b  lea     rax, [rbp+var_10+8]
0x18000d96f  xorps   xmm0, xmm0
0x18000d972  mov     [rbp+var_20], rax
0x18000d976  lea     rax, [rbp+var_10]
0x18000d97a  mov     [rbp+var_18], rax
0x18000d97e  mov     rsi, r9
0x18000d981  mov     ebx, r8d
0x18000d984  mov     r14, rdx
0x18000d987  mov     r15, rcx
0x18000d98a  movdqu  [rbp+var_10], xmm0
0x18000d98f  test    rcx, rcx
0x18000d992  jnz     short loc_18000D9B3
0x18000d994  lea     rdx, byte_18001ED20
0x18000d99b  mov     ebx, 80070057h
0x18000d9a0  lea     rcx, qword_180018AE8
0x18000d9a7  call    sub_180001760
0x18000d9ac  mov     ecx, ebx
0x18000d9ae  jmp     loc_18000DAA9
0x18000d9b3  lea     rdx, dword_18001E8FC
0x18000d9ba  lea     rcx, byte_180018738
0x18000d9c1  call    sub_180002BF0
0x18000d9c6  test    r14, r14
0x18000d9c9  jnz     short loc_18000D9D2
0x18000d9cb  mov     ebx, 80070057h
0x18000d9d0  jmp     short loc_18000D9AC
0x18000d9d2  test    ebx, ebx
0x18000d9d4  jz      short loc_18000D9CB
0x18000d9d6  test    rsi, rsi
0x18000d9d9  jz      short loc_18000D9CB
0x18000d9db  cmp     [rbp+arg_20], 0
0x18000d9df  jz      short loc_18000D9CB
0x18000d9e1  cmp     [rbp+arg_28], 0
0x18000d9e6  jz      short loc_18000D9CB
0x18000d9e8  mov     r8, r14
0x18000d9eb  lea     rcx, [rbp+var_20]
0x18000d9ef  mov     r14d, 1
0x18000d9f5  mov     edx, r14d
0x18000d9f8  call    sub_180004F44
0x18000d9fd  mov     ebx, eax
0x18000d9ff  test    eax, eax
0x18000da01  js      loc_18000DAA7
0x18000da07  lea     r8, [rbp+arg_10]
0x18000da0b  lea     edx, [r14+1]
0x18000da0f  lea     rcx, [rbp+var_20]
0x18000da13  call    sub_180004F80
0x18000da18  mov     ebx, eax
0x18000da1a  test    eax, eax
0x18000da1c  jns     short loc_18000DA3A
0x18000da1e  mov     ecx, eax
0x18000da20  call    sub_180006844
0x18000da25  lea     rdx, qword_18001E828
0x18000da2c  lea     rcx, dword_180018BE4
0x18000da33  call    sub_180001EC0
0x18000da38  jmp     short loc_18000DAAE
0x18000da3a  mov     r8d, [rbp+arg_10]
0x18000da3e  lea     rcx, [rbp+var_20]
0x18000da42  mov     r9, rsi
0x18000da45  mov     edx, 3
0x18000da4a  call    sub_18000F114
0x18000da4f  mov     ebx, eax
0x18000da51  test    eax, eax
0x18000da53  js      short loc_18000DAA7
0x18000da55  lea     r8, [rbp+arg_20]
0x18000da59  mov     edx, 4
0x18000da5e  lea     rcx, [rbp+var_20]
0x18000da62  call    sub_180004F80
0x18000da67  mov     ebx, eax
0x18000da69  test    eax, eax
0x18000da6b  js      short loc_18000DAA7
0x18000da6d  mov     r9, [rbp+arg_28]
0x18000da71  lea     rcx, [rbp+var_20]
0x18000da75  mov     r8d, [rbp+arg_20]
0x18000da79  mov     edx, 5
0x18000da7e  call    sub_18000F114
0x18000da83  mov     ebx, eax
0x18000da85  test    eax, eax
0x18000da87  js      short loc_18000DAA7
0x18000da89  xor     r9d, r9d
0x18000da8c  mov     [rsp+50h+var_30], r14d
0x18000da91  mov     rdx, r15
0x18000da94  lea     rcx, [rbp+var_20]
0x18000da98  lea     r8d, [r9+2Eh]
0x18000da9c  call    sub_1800044DC
0x18000daa1  mov     ebx, eax
0x18000daa3  test    eax, eax
0x18000daa5  jns     short loc_18000DAAE
0x18000daa7  mov     ecx, eax
0x18000daa9  call    sub_180006844
0x18000daae  mov     ecx, ebx
0x18000dab0  call    sub_18000A8D0
0x18000dab5  lea     rcx, [rbp+var_20]
0x18000dab9  call    sub_180005208
0x18000dabe  mov     rsi, [rsp+50h+arg_8]
0x18000dac3  mov     eax, ebx
0x18000dac5  mov     rbx, [rsp+50h+arg_0]
0x18000daca  add     rsp, 50h
0x18000dace  pop     r15
0x18000dad0  pop     r14
0x18000dad2  pop     rbp
0x18000dad3  retn
```
