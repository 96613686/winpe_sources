# _anonymous_namespace_::PkCreateGpaRangesEx__anonymous_namespace_::MdlWrapper_

- ea: `0x140014ce0`
- end: `0x140014e6f`
- name: `_anonymous_namespace_::PkCreateGpaRangesEx__anonymous_namespace_::MdlWrapper_`
- size: `399`
- prototype: `__int64(unsigned __int64, __int64 *, unsigned __int64 *, unsigned int, unsigned int, char, ...)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400033e0`
- `0x140014e78`

## callees

- `0x140014ce0`
- `0x140014ffc`

## pseudocode

```c
__int64 anonymous_namespace_::PkCreateGpaRangesEx__anonymous_namespace_::MdlWrapper_(
        unsigned __int64 a1,
        __int64 *a2,
        unsigned __int64 *a3,
        unsigned int a4,
        unsigned int a5,
        char a6,
        ...)
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
  __int64 result; // rax

  while ( a2 )
  {
    v8 = *a3;
    if ( *a3 < 0x10 )
      goto LABEL_31;
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
      goto LABEL_31;
    a1 = (unsigned __int64)(a4 + *((_DWORD *)a2 + 11)) >> 12;
    v17 = (__int64 *)(v14 + 8 * v16);
    if ( a1 )
    {
      if ( a2 == (__int64 *)-48LL || !v17 || v16 < a1 )
        goto LABEL_31;
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
          goto LABEL_31;
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
LABEL_31:
      gsl::details::terminate((gsl::details *)a1);
      JUMPOUT(0x140014E6ELL);
    }
    *a3 = v23;
    result = (__int64)v10 + a1;
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
0x140014ce0  mov     [rsp+arg_0], rcx
0x140014ce5  push    rbx
0x140014ce6  push    rbp
0x140014ce7  push    rsi
0x140014ce8  push    rdi
0x140014ce9  push    r12
0x140014ceb  push    r13
0x140014ced  push    r14
0x140014cef  push    r15
0x140014cf1  sub     rsp, 28h
0x140014cf5  mov     ebx, [rsp+68h+arg_20]
0x140014cfc  mov     rsi, r8
0x140014cff  mov     r13d, 0FFFh
0x140014d05  test    rdx, rdx
0x140014d08  jz      loc_140014E57
0x140014d0e  mov     r10, [rsi]
0x140014d11  cmp     r10, 10h
0x140014d15  jb      loc_140014E69
0x140014d1b  mov     r8d, [rdx+28h]
0x140014d1f  cmp     r9d, r8d
0x140014d22  jb      short loc_140014D2C
0x140014d24  sub     r9d, r8d
0x140014d27  jmp     loc_140014E44
0x140014d2c  mov     r12, [rsi+8]
0x140014d30  sub     r8d, r9d
0x140014d33  mov     [rsp+68h+arg_0], 0
0x140014d3c  test    ebx, ebx
0x140014d3e  jz      short loc_140014D5A
0x140014d40  cmp     [rsp+68h+arg_28], 0
0x140014d48  jnz     loc_140014E4C
0x140014d4e  cmp     ebx, r8d
0x140014d51  jbe     loc_140014E4C
0x140014d57  sub     ebx, r8d
0x140014d5a  mov     r14b, byte ptr [rsp+68h+arg_0+4]
0x140014d5f  mov     r15d, [rdx+2Ch]
0x140014d63  lea     rdi, [rdx+30h]
0x140014d67  mov     [r12], r8d
0x140014d6b  add     r15d, r9d
0x140014d6e  mov     eax, [rdx+2Ch]
0x140014d71  add     eax, r9d
0x140014d74  and     eax, r13d
0x140014d77  mov     [r12+4], eax
0x140014d7c  mov     ebp, [rdx+2Ch]
0x140014d7f  mov     ecx, ebp
0x140014d81  mov     r11d, [rdx+28h]
0x140014d85  and     rcx, r13
0x140014d88  add     r11, r13
0x140014d8b  add     r11, rcx
0x140014d8e  shr     r11, 0Ch
0x140014d92  test    rdi, rdi
0x140014d95  jnz     short loc_140014DA0
0x140014d97  test    r11, r11
0x140014d9a  jnz     loc_140014E69
0x140014da0  lea     ecx, [r9+rbp]
0x140014da4  shr     rcx, 0Ch
0x140014da8  lea     r9, [rdi+r11*8]
0x140014dac  test    rcx, rcx
0x140014daf  jz      short loc_140014DCC
0x140014db1  test    rdi, rdi
0x140014db4  jz      loc_140014E69
0x140014dba  test    r9, r9
0x140014dbd  jz      loc_140014E69
0x140014dc3  cmp     r11, rcx
0x140014dc6  jb      loc_140014E69
0x140014dcc  mov     ebp, r8d
0x140014dcf  and     r15, r13
0x140014dd2  add     rbp, 0FFFh
0x140014dd9  lea     r8, [rdi+rcx*8]
0x140014ddd  add     rbp, r15
0x140014de0  shr     rbp, 0Ch
0x140014de4  test    ebp, ebp
0x140014de6  jz      short loc_140014E18
0x140014de8  xor     r11d, r11d
0x140014deb  cmp     r8, r9
0x140014dee  jz      short loc_140014E18
0x140014df0  test    rdi, rdi
0x140014df3  jz      short loc_140014E69
0x140014df5  test    r9, r9
0x140014df8  jz      short loc_140014E69
0x140014dfa  cmp     rdi, r8
0x140014dfd  ja      short loc_140014E69
0x140014dff  cmp     r8, r9
0x140014e02  jnb     short loc_140014E69
0x140014e04  mov     rax, [r8]
0x140014e07  add     r8, 8
0x140014e0b  mov     [r12+r11*8+8], rax
0x140014e10  inc     r11d
0x140014e13  cmp     r11d, ebp
0x140014e16  jb      short loc_140014DEB
0x140014e18  lea     eax, [rbp-1]
0x140014e1b  lea     rcx, ds:10h[rax*8]; this
0x140014e23  cmp     r10, rcx
0x140014e26  jb      short loc_140014E69
0x140014e28  sub     r10, rcx
0x140014e2b  cmp     r10, 0FFFFFFFFFFFFFFFFh
0x140014e2f  jz      short loc_140014E69
0x140014e31  mov     [rsi], r10
0x140014e34  lea     rax, [r12+rcx]
0x140014e38  mov     [rsi+8], rax
0x140014e3c  test    r14b, r14b
0x140014e3f  jnz     short loc_140014E57
0x140014e41  xor     r9d, r9d
0x140014e44  mov     rdx, [rdx]
0x140014e47  jmp     loc_140014D05
0x140014e4c  mov     r8d, ebx
0x140014e4f  mov     r14b, 1
0x140014e52  jmp     loc_140014D5F
0x140014e57  add     rsp, 28h
0x140014e5b  pop     r15
0x140014e5d  pop     r14
0x140014e5f  pop     r13
0x140014e61  pop     r12
0x140014e63  pop     rdi
0x140014e64  pop     rsi
0x140014e65  pop     rbp
0x140014e66  pop     rbx
0x140014e67  retn
0x140014e69  call    ?terminate@details@gsl@@YAXXZ; gsl::details::terminate(void)
```
