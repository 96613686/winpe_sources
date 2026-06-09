# _anonymous_namespace_::PkCreateGpaRangesEx__anonymous_namespace_::MdlWrapper_

- ea: `0x1400062e0`
- end: `0x14000646f`
- name: `_anonymous_namespace_::PkCreateGpaRangesEx__anonymous_namespace_::MdlWrapper_`
- size: `399`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400042b0`

## callees

- `0x1400062e0`
- `0x140006478`

## pseudocode

```c
char *__fastcall anonymous_namespace_::PkCreateGpaRangesEx__anonymous_namespace_::MdlWrapper_(
        unsigned __int64 a1,
        __int64 *a2,
        unsigned __int64 *a3,
        unsigned int a4,
        unsigned int a5,
        char a6)
{
  unsigned __int64 v8; // r10
  unsigned int v9; // r8d
  unsigned int *v10; // r12
  unsigned int v11; // r8d
  char v12; // r14
  int v13; // r15d
  unsigned __int64 v14; // rdi
  __int16 v15; // r15
  unsigned __int64 v16; // r11
  __int64 *v17; // r9
  __int64 v18; // rbp
  __int64 *v19; // r8
  unsigned __int64 v20; // rbp
  __int64 v21; // r11
  __int64 v22; // rax
  unsigned __int64 v23; // r10
  char *result; // rax

  while ( a2 )
  {
    v8 = *a3;
    if ( *a3 < 0x10 )
      goto LABEL_30;
    v9 = *((_DWORD *)a2 + 10);
    if ( a4 >= v9 )
    {
      a4 -= v9;
      goto LABEL_28;
    }
    v10 = (unsigned int *)a3[1];
    v11 = v9 - a4;
    if ( !a5 )
      goto LABEL_9;
    if ( !a6 && a5 > v11 )
    {
      a5 -= v11;
LABEL_9:
      v12 = 0;
      goto LABEL_10;
    }
    v11 = a5;
    v12 = 1;
LABEL_10:
    v13 = *((_DWORD *)a2 + 11);
    v14 = (unsigned __int64)(a2 + 6);
    *v10 = v11;
    v15 = a4 + v13;
    v10[1] = (a4 + *((_DWORD *)a2 + 11)) & 0xFFF;
    a1 = *((_DWORD *)a2 + 11) & 0xFFFLL;
    v16 = (a1 + *((unsigned int *)a2 + 10) + 4095LL) >> 12;
    if ( a2 == (__int64 *)-48LL && v16 )
      goto LABEL_30;
    a1 = (unsigned __int64)(a4 + *((_DWORD *)a2 + 11)) >> 12;
    v17 = (__int64 *)(v14 + 8 * v16);
    if ( a1 )
    {
      if ( a2 == (__int64 *)-48LL || !v17 || v16 < a1 )
        goto LABEL_30;
    }
    v18 = v11 + 4095LL;
    v19 = (__int64 *)(v14 + 8 * a1);
    v20 = ((unsigned __int64)(v15 & 0xFFF) + v18) >> 12;
    if ( (_DWORD)v20 )
    {
      v21 = 0;
      while ( v19 != v17 )
      {
        if ( a2 == (__int64 *)-48LL || !v17 || v14 > (unsigned __int64)v19 || v19 >= v17 )
          goto LABEL_30;
        v22 = *v19++;
        *(_QWORD *)&v10[2 * v21 + 2] = v22;
        v21 = (unsigned int)(v21 + 1);
        if ( (unsigned int)v21 >= (unsigned int)v20 )
          break;
      }
    }
    a1 = 8LL * (unsigned int)(v20 - 1) + 16;
    if ( v8 < a1 || (v23 = v8 - a1, v23 == -1) )
    {
LABEL_30:
      gsl::details::terminate((gsl::details *)a1);
      __debugbreak();
    }
    *a3 = v23;
    result = (char *)v10 + a1;
    a3[1] = (unsigned __int64)v10 + a1;
    if ( v12 )
      return result;
    a4 = 0;
LABEL_28:
    a2 = (__int64 *)*a2;
  }
  return result;
}

```

## disassembly

```asm
0x1400062e0  mov     [rsp+arg_0], rcx
0x1400062e5  push    rbx
0x1400062e6  push    rbp
0x1400062e7  push    rsi
0x1400062e8  push    rdi
0x1400062e9  push    r12
0x1400062eb  push    r13
0x1400062ed  push    r14
0x1400062ef  push    r15
0x1400062f1  sub     rsp, 28h
0x1400062f5  mov     ebx, [rsp+68h+arg_20]
0x1400062fc  mov     rsi, r8
0x1400062ff  mov     r13d, 0FFFh
0x140006305  test    rdx, rdx
0x140006308  jz      loc_14000645D
0x14000630e  mov     r10, [rsi]
0x140006311  cmp     r10, 10h
0x140006315  jb      loc_140006457
0x14000631b  mov     r8d, [rdx+28h]
0x14000631f  cmp     r9d, r8d
0x140006322  jb      short loc_14000632C
0x140006324  sub     r9d, r8d
0x140006327  jmp     loc_140006444
0x14000632c  mov     r12, [rsi+8]
0x140006330  sub     r8d, r9d
0x140006333  mov     [rsp+68h+arg_0], 0
0x14000633c  test    ebx, ebx
0x14000633e  jz      short loc_14000635A
0x140006340  cmp     [rsp+68h+arg_28], 0
0x140006348  jnz     loc_14000644C
0x14000634e  cmp     ebx, r8d
0x140006351  jbe     loc_14000644C
0x140006357  sub     ebx, r8d
0x14000635a  mov     r14b, byte ptr [rsp+68h+arg_0+4]
0x14000635f  mov     r15d, [rdx+2Ch]
0x140006363  lea     rdi, [rdx+30h]
0x140006367  mov     [r12], r8d
0x14000636b  add     r15d, r9d
0x14000636e  mov     eax, [rdx+2Ch]
0x140006371  add     eax, r9d
0x140006374  and     eax, r13d
0x140006377  mov     [r12+4], eax
0x14000637c  mov     ebp, [rdx+2Ch]
0x14000637f  mov     ecx, ebp
0x140006381  mov     r11d, [rdx+28h]
0x140006385  and     rcx, r13
0x140006388  add     r11, r13
0x14000638b  add     r11, rcx
0x14000638e  shr     r11, 0Ch
0x140006392  test    rdi, rdi
0x140006395  jnz     short loc_1400063A0
0x140006397  test    r11, r11
0x14000639a  jnz     loc_140006457
0x1400063a0  lea     ecx, [r9+rbp]
0x1400063a4  shr     rcx, 0Ch
0x1400063a8  lea     r9, [rdi+r11*8]
0x1400063ac  test    rcx, rcx
0x1400063af  jz      short loc_1400063CC
0x1400063b1  test    rdi, rdi
0x1400063b4  jz      loc_140006457
0x1400063ba  test    r9, r9
0x1400063bd  jz      loc_140006457
0x1400063c3  cmp     r11, rcx
0x1400063c6  jb      loc_140006457
0x1400063cc  mov     ebp, r8d
0x1400063cf  and     r15, r13
0x1400063d2  add     rbp, 0FFFh
0x1400063d9  lea     r8, [rdi+rcx*8]
0x1400063dd  add     rbp, r15
0x1400063e0  shr     rbp, 0Ch
0x1400063e4  test    ebp, ebp
0x1400063e6  jz      short loc_140006418
0x1400063e8  xor     r11d, r11d
0x1400063eb  cmp     r8, r9
0x1400063ee  jz      short loc_140006418
0x1400063f0  test    rdi, rdi
0x1400063f3  jz      short loc_140006457
0x1400063f5  test    r9, r9
0x1400063f8  jz      short loc_140006457
0x1400063fa  cmp     rdi, r8
0x1400063fd  ja      short loc_140006457
0x1400063ff  cmp     r8, r9
0x140006402  jnb     short loc_140006457
0x140006404  mov     rax, [r8]
0x140006407  add     r8, 8
0x14000640b  mov     [r12+r11*8+8], rax
0x140006410  inc     r11d
0x140006413  cmp     r11d, ebp
0x140006416  jb      short loc_1400063EB
0x140006418  lea     eax, [rbp-1]
0x14000641b  lea     rcx, ds:10h[rax*8]; this
0x140006423  cmp     r10, rcx
0x140006426  jb      short loc_140006457
0x140006428  sub     r10, rcx
0x14000642b  cmp     r10, 0FFFFFFFFFFFFFFFFh
0x14000642f  jz      short loc_140006457
0x140006431  mov     [rsi], r10
0x140006434  lea     rax, [r12+rcx]
0x140006438  mov     [rsi+8], rax
0x14000643c  test    r14b, r14b
0x14000643f  jnz     short loc_14000645D
0x140006441  xor     r9d, r9d
0x140006444  mov     rdx, [rdx]
0x140006447  jmp     loc_140006305
0x14000644c  mov     r8d, ebx
0x14000644f  mov     r14b, 1
0x140006452  jmp     loc_14000635F
0x140006457  call    ?terminate@details@gsl@@YAXXZ; gsl::details::terminate(void)
0x14000645c  int     3; Trap to Debugger
0x14000645d  add     rsp, 28h
0x140006461  pop     r15
0x140006463  pop     r14
0x140006465  pop     r13
0x140006467  pop     r12
0x140006469  pop     rdi
0x14000646a  pop     rsi
0x14000646b  pop     rbp
0x14000646c  pop     rbx
0x14000646d  retn
```
