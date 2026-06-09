# MinAsn1ParseSingleExtensionValue

- ea: `0x18004d198`
- end: `0x18004d309`
- name: `MinAsn1ParseSingleExtensionValue`
- size: `369`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18001673c`
- `0x180016e48`
- `0x1800182c4`

## callees

- `0x18003391a`
- `0x180033980`
- `0x18004d198`
- `0x18004dd2c`
- `0x18004de78`

## pseudocode

```c
__int64 __fastcall MinAsn1ParseSingleExtensionValue(unsigned int *a1, unsigned int *a2, char *a3, _OWORD *a4)
{
  unsigned int v4; // r10d
  __int64 result; // rax
  char v6; // r15
  char *v7; // rsi
  unsigned int *v8; // rdi
  __int64 v9; // r12
  int v10; // ebx
  int v11; // r14d
  int Values; // ecx
  const void *v13; // rcx
  size_t v14; // r13
  __int64 v15; // rdi
  __int64 v16; // rsi
  int v17; // [rsp+30h] [rbp-69h] BYREF
  const void *v18; // [rsp+38h] [rbp-61h] BYREF
  unsigned int *v19; // [rsp+40h] [rbp-59h]
  char *v20; // [rsp+48h] [rbp-51h]
  _OWORD *v21; // [rsp+50h] [rbp-49h]
  _BYTE v22[16]; // [rsp+60h] [rbp-39h] BYREF
  int v23; // [rsp+70h] [rbp-29h]
  void *Buf2[3]; // [rsp+88h] [rbp-11h]
  __int128 v26; // [rsp+A0h] [rbp+7h]

  v4 = *a2;
  result = 0;
  v6 = 0;
  v21 = a4;
  v20 = a3;
  v7 = a3;
  v19 = a1;
  v8 = a1;
  v18 = 0;
  v17 = 0;
  if ( v4 )
  {
    v9 = *((_QWORD *)a2 + 1);
    if ( (int)MinAsn1ExtractContent(v9, v4, &v17, &v18) <= 0 )
    {
      result = 0xFFFFFFFFLL;
      goto LABEL_23;
    }
    v10 = (int)v18;
    v11 = v17;
LABEL_5:
    if ( !v11 )
    {
      result = (unsigned int)(v10 - v9);
      goto LABEL_22;
    }
    v17 = 4;
    Values = MinAsn1ExtractValues(v10, v11, (unsigned int)&v17, (unsigned int)&qword_180035D70, 5, (__int64)v22);
    if ( Values > 0 )
    {
      if ( v6 )
        goto LABEL_17;
      v13 = (const void *)*((_QWORD *)v8 + 1);
      v14 = *v8;
      v15 = 0;
      v18 = v13;
      while ( 1 )
      {
        if ( (_DWORD)v15 )
        {
          v8 = v19;
          goto LABEL_17;
        }
        v16 = 80 * v15;
        if ( (_DWORD)v14 == LODWORD(Buf2[10 * v15]) )
        {
          if ( !memcmp_0(v13, Buf2[10 * v15], v14) )
          {
            v8 = v19;
            if ( &v22[v16] )
            {
              v6 = 1;
              *v21 = v26;
            }
LABEL_17:
            v10 += v23;
            v11 -= v23;
            goto LABEL_5;
          }
          v13 = v18;
        }
        v15 = 1;
      }
    }
    if ( !Values )
      Values = -1;
    result = (unsigned int)(Values + v9 - v10);
LABEL_22:
    v7 = v20;
  }
LABEL_23:
  *v7 = v6;
  return result;
}

```

## disassembly

```asm
0x18004d198  mov     [rsp-8+arg_0], rbx
0x18004d19d  push    rbp
0x18004d19e  push    rsi
0x18004d19f  push    rdi
0x18004d1a0  push    r12
0x18004d1a2  push    r13
0x18004d1a4  push    r14
0x18004d1a6  push    r15
0x18004d1a8  lea     rbp, [rsp-27h]
0x18004d1ad  sub     rsp, 0C0h
0x18004d1b4  mov     rax, cs:__security_cookie
0x18004d1bb  xor     rax, rsp
0x18004d1be  mov     [rbp+57h+var_40], rax
0x18004d1c2  mov     r10d, [rdx]
0x18004d1c5  xor     eax, eax
0x18004d1c7  xor     r15b, r15b
0x18004d1ca  mov     [rbp+57h+var_A0], r9
0x18004d1ce  mov     [rbp+57h+var_A8], r8
0x18004d1d2  mov     rsi, r8
0x18004d1d5  mov     [rbp+57h+var_B0], rcx
0x18004d1d9  mov     rdi, rcx
0x18004d1dc  mov     [rbp+57h+var_B8], rax
0x18004d1e0  mov     [rbp+57h+var_C0], eax
0x18004d1e3  test    r10d, r10d
0x18004d1e6  jz      loc_18004D2DE
0x18004d1ec  mov     r12, [rdx+8]
0x18004d1f0  lea     r9, [rbp+57h+var_B8]
0x18004d1f4  mov     rcx, r12
0x18004d1f7  lea     r8, [rbp+57h+var_C0]
0x18004d1fb  mov     edx, r10d
0x18004d1fe  call    MinAsn1ExtractContent
0x18004d203  test    eax, eax
0x18004d205  jg      short loc_18004D20F
0x18004d207  or      eax, 0FFFFFFFFh
0x18004d20a  jmp     loc_18004D2DE
0x18004d20f  mov     rbx, [rbp+57h+var_B8]
0x18004d213  mov     r14d, [rbp+57h+var_C0]
0x18004d217  test    r14d, r14d
0x18004d21a  jz      loc_18004D2D5
0x18004d220  lea     rax, [rbp+57h+var_90]
0x18004d224  mov     [rbp+57h+var_C0], 4
0x18004d22b  mov     [rsp+0F0h+var_C8], rax
0x18004d230  lea     r9, qword_180035D70
0x18004d237  lea     r8, [rbp+57h+var_C0]
0x18004d23b  mov     [rsp+0F0h+var_D0], 5
0x18004d243  mov     edx, r14d
0x18004d246  mov     rcx, rbx
0x18004d249  call    MinAsn1ExtractValues
0x18004d24e  mov     ecx, eax
0x18004d250  test    eax, eax
0x18004d252  jle     short loc_18004D2C4
0x18004d254  test    r15b, r15b
0x18004d257  jnz     short loc_18004D2B5
0x18004d259  mov     rcx, [rdi+8]; Buf1
0x18004d25d  mov     r13d, [rdi]
0x18004d260  xor     edi, edi
0x18004d262  mov     [rbp+57h+var_B8], rcx
0x18004d266  cmp     edi, 1
0x18004d269  jnb     short loc_18004D2B1
0x18004d26b  lea     rsi, [rdi+rdi*4]
0x18004d26f  shl     rsi, 4
0x18004d273  cmp     r13d, [rbp+rsi+57h+var_70]
0x18004d278  jnz     short loc_18004D28F
0x18004d27a  mov     rdx, [rbp+rsi+57h+Buf2]; Buf2
0x18004d27f  mov     r8, r13; Size
0x18004d282  call    memcmp_0
0x18004d287  test    eax, eax
0x18004d289  jz      short loc_18004D293
0x18004d28b  mov     rcx, [rbp+57h+var_B8]
0x18004d28f  inc     edi
0x18004d291  jmp     short loc_18004D266
0x18004d293  mov     rdi, [rbp+57h+var_B0]
0x18004d297  lea     rax, [rbp+57h+var_90]
0x18004d29b  add     rax, rsi
0x18004d29e  jz      short loc_18004D2B5
0x18004d2a0  mov     rax, [rbp+57h+var_A0]
0x18004d2a4  mov     r15b, 1
0x18004d2a7  movaps  xmm0, [rbp+57h+var_50]
0x18004d2ab  movdqu  xmmword ptr [rax], xmm0
0x18004d2af  jmp     short loc_18004D2B5
0x18004d2b1  mov     rdi, [rbp+57h+var_B0]
0x18004d2b5  mov     eax, [rbp+57h+var_80]
0x18004d2b8  add     rbx, rax
0x18004d2bb  sub     r14d, [rbp+57h+var_80]
0x18004d2bf  jmp     loc_18004D217
0x18004d2c4  or      eax, 0FFFFFFFFh
0x18004d2c7  test    ecx, ecx
0x18004d2c9  cmovz   ecx, eax
0x18004d2cc  mov     eax, r12d
0x18004d2cf  sub     eax, ebx
0x18004d2d1  add     eax, ecx
0x18004d2d3  jmp     short loc_18004D2DA
0x18004d2d5  mov     eax, ebx
0x18004d2d7  sub     eax, r12d
0x18004d2da  mov     rsi, [rbp+57h+var_A8]
0x18004d2de  mov     [rsi], r15b
0x18004d2e1  mov     rcx, [rbp+57h+var_40]
0x18004d2e5  xor     rcx, rsp; StackCookie
0x18004d2e8  call    __security_check_cookie
0x18004d2ed  mov     rbx, [rsp+0F0h+arg_0]
0x18004d2f5  add     rsp, 0C0h
0x18004d2fc  pop     r15
0x18004d2fe  pop     r14
0x18004d300  pop     r13
0x18004d302  pop     r12
0x18004d304  pop     rdi
0x18004d305  pop     rsi
0x18004d306  pop     rbp
0x18004d307  retn
```
