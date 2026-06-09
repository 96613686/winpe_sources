# I_MinAsn1ParseSingleAttribute

- ea: `0x18004c6f4`
- end: `0x18004c8ce`
- name: `I_MinAsn1ParseSingleAttribute`
- size: `474`
- prototype: ``
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x180044c0c`
- `0x180044c90`
- `0x180045d9c`
- `0x18004784c`
- `0x180047940`
- `0x18004d178`
- `0x18004e1f4`

## callees

- `0x18003391a`
- `0x180033980`
- `0x18004c6f4`
- `0x18004dd2c`
- `0x18004de78`

## pseudocode

```c
char __fastcall I_MinAsn1ParseSingleAttribute(__int64 a1, __int64 a2, unsigned int a3, _OWORD *a4, _OWORD *a5)
{
  int v5; // eax
  __int64 v6; // r15
  _BYTE *v7; // rbx
  char v8; // r14
  _BYTE *v9; // rdi
  char v10; // si
  unsigned int v11; // r13d
  int v12; // eax
  _BYTE *v13; // r9
  __int64 v14; // r14
  unsigned int v15; // ecx
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  __int128 v19; // xmm0
  int v20; // ebx
  char v22; // [rsp+30h] [rbp-71h]
  unsigned int v23; // [rsp+34h] [rbp-6Dh] BYREF
  _BYTE *v24; // [rsp+38h] [rbp-69h] BYREF
  unsigned int v25; // [rsp+40h] [rbp-61h]
  __int64 v26; // [rsp+48h] [rbp-59h]
  _OWORD *v27; // [rsp+50h] [rbp-51h]
  __int128 v28; // [rsp+60h] [rbp-41h] BYREF
  __int128 v29; // [rsp+70h] [rbp-31h]
  void *Buf2[2]; // [rsp+80h] [rbp-21h]
  __int128 v31; // [rsp+90h] [rbp-11h]
  __int128 v32; // [rsp+A0h] [rbp-1h]

  v5 = *(_DWORD *)a2;
  v6 = a1;
  v27 = a4;
  v25 = a3;
  v26 = a1;
  v24 = 0;
  v23 = 0;
  if ( !v5 )
    return 0;
  v7 = *(_BYTE **)(a2 + 8);
  v8 = 0;
  v22 = 0;
  if ( (int)MinAsn1ExtractContent(v7, v5, &v23, &v24) <= 0 )
    return 0;
  v9 = v24;
  v10 = 1;
  v11 = v23;
LABEL_4:
  if ( !v11 )
  {
    v20 = (_DWORD)v9 - (_DWORD)v7;
    goto LABEL_26;
  }
  v23 = 4;
  v12 = MinAsn1ExtractValues(v9, v11, &v23, (__int64)&qword_1800361A0, 5u, (__int64)&v28);
  if ( v12 > 0 )
  {
    if ( v8 )
      goto LABEL_21;
    v13 = *(_BYTE **)(v6 + 8);
    v14 = 0;
    v15 = *(_DWORD *)v6;
    v24 = v13;
    v23 = v15;
    while ( 1 )
    {
      if ( (_DWORD)v14 )
        goto LABEL_19;
      if ( v15 == LODWORD(Buf2[10 * v14]) )
      {
        if ( !memcmp_0(v13, Buf2[10 * v14 + 1], v15) )
        {
          if ( !(&v28 + 5 * v14) )
          {
LABEL_19:
            v8 = v22;
            goto LABEL_20;
          }
          if ( a5 )
          {
            v16 = v29;
            *a5 = v28;
            v17 = *(_OWORD *)Buf2;
            a5[1] = v16;
            v18 = v31;
            a5[2] = v17;
            v19 = v32;
            a5[3] = v18;
            a5[4] = v19;
          }
          if ( v27 )
            *v27 = *(&v28 + v25);
          v8 = 1;
          v22 = 1;
LABEL_20:
          v6 = v26;
LABEL_21:
          v9 += (unsigned int)v29;
          v11 -= v29;
          goto LABEL_4;
        }
        v15 = v23;
        v13 = v24;
      }
      v14 = 1;
    }
  }
  if ( !v12 )
    v12 = -1;
  v20 = v12 + (_DWORD)v7 - (_DWORD)v9;
LABEL_26:
  if ( !v8 || v20 < 0 )
    return 0;
  return v10;
}

```

## disassembly

```asm
0x18004c6f4  mov     [rsp-8+arg_0], rbx
0x18004c6f9  push    rbp
0x18004c6fa  push    rsi
0x18004c6fb  push    rdi
0x18004c6fc  push    r12
0x18004c6fe  push    r13
0x18004c700  push    r14
0x18004c702  push    r15
0x18004c704  lea     rbp, [rsp-1Fh]
0x18004c709  sub     rsp, 0C0h
0x18004c710  mov     rax, cs:__security_cookie
0x18004c717  xor     rax, rsp
0x18004c71a  mov     [rbp+4Fh+var_40], rax
0x18004c71e  mov     eax, [rdx]
0x18004c720  mov     r15, rcx
0x18004c723  mov     r12, [rbp+4Fh+arg_20]
0x18004c727  mov     [rbp+4Fh+var_A0], r9
0x18004c72b  mov     [rbp+4Fh+var_B0], r8d
0x18004c72f  mov     [rbp+4Fh+var_A8], rcx
0x18004c733  mov     [rbp+4Fh+var_B8], 0
0x18004c73b  mov     [rbp+4Fh+var_BC], 0
0x18004c742  test    eax, eax
0x18004c744  jz      loc_18004C8A0
0x18004c74a  mov     rbx, [rdx+8]
0x18004c74e  lea     r9, [rbp+4Fh+var_B8]
0x18004c752  xor     r14b, r14b
0x18004c755  lea     r8, [rbp+4Fh+var_BC]
0x18004c759  mov     rcx, rbx
0x18004c75c  mov     [rbp+4Fh+var_C0], r14b
0x18004c760  mov     edx, eax
0x18004c762  call    MinAsn1ExtractContent
0x18004c767  test    eax, eax
0x18004c769  jle     loc_18004C8A0
0x18004c76f  mov     rdi, [rbp+4Fh+var_B8]
0x18004c773  mov     esi, 1
0x18004c778  mov     r13d, [rbp+4Fh+var_BC]
0x18004c77c  test    r13d, r13d
0x18004c77f  jz      loc_18004C893
0x18004c785  lea     rax, [rbp+4Fh+var_90]
0x18004c789  mov     [rbp+4Fh+var_BC], 4
0x18004c790  mov     [rsp+0F0h+var_C8], rax
0x18004c795  lea     r9, qword_1800361A0
0x18004c79c  lea     r8, [rbp+4Fh+var_BC]
0x18004c7a0  mov     [rsp+0F0h+var_D0], 5
0x18004c7a8  mov     edx, r13d
0x18004c7ab  mov     rcx, rdi
0x18004c7ae  call    MinAsn1ExtractValues
0x18004c7b3  test    eax, eax
0x18004c7b5  jle     loc_18004C885
0x18004c7bb  test    r14b, r14b
0x18004c7be  jnz     loc_18004C876
0x18004c7c4  mov     r9, [r15+8]
0x18004c7c8  xor     r14d, r14d
0x18004c7cb  mov     ecx, [r15]
0x18004c7ce  mov     [rbp+4Fh+var_B8], r9
0x18004c7d2  mov     [rbp+4Fh+var_BC], ecx
0x18004c7d5  cmp     r14d, esi
0x18004c7d8  jnb     loc_18004C86E
0x18004c7de  lea     r15, [r14+r14*4]
0x18004c7e2  shl     r15, 4
0x18004c7e6  cmp     ecx, dword ptr [rbp+r15+4Fh+Buf2]
0x18004c7eb  jnz     short loc_18004C808
0x18004c7ed  mov     rdx, [rbp+r15+4Fh+Buf2+8]; Buf2
0x18004c7f2  mov     r8d, ecx; Size
0x18004c7f5  mov     rcx, r9; Buf1
0x18004c7f8  call    memcmp_0
0x18004c7fd  test    eax, eax
0x18004c7ff  jz      short loc_18004C80D
0x18004c801  mov     ecx, [rbp+4Fh+var_BC]
0x18004c804  mov     r9, [rbp+4Fh+var_B8]
0x18004c808  add     r14d, esi
0x18004c80b  jmp     short loc_18004C7D5
0x18004c80d  lea     rax, [rbp+4Fh+var_90]
0x18004c811  add     rax, r15
0x18004c814  jz      short loc_18004C86E
0x18004c816  test    r12, r12
0x18004c819  jz      short loc_18004C84C
0x18004c81b  movaps  xmm0, [rbp+4Fh+var_90]
0x18004c81f  movaps  xmm1, [rbp+4Fh+var_80]
0x18004c823  movaps  xmmword ptr [r12], xmm0
0x18004c828  movaps  xmm0, xmmword ptr [rbp+4Fh+Buf2]
0x18004c82c  movaps  xmmword ptr [r12+10h], xmm1
0x18004c832  movaps  xmm1, [rbp+4Fh+var_60]
0x18004c836  movaps  xmmword ptr [r12+20h], xmm0
0x18004c83c  movaps  xmm0, [rbp+4Fh+var_50]
0x18004c840  movaps  xmmword ptr [r12+30h], xmm1
0x18004c846  movaps  xmmword ptr [r12+40h], xmm0
0x18004c84c  mov     r15, [rbp+4Fh+var_A0]
0x18004c850  test    r15, r15
0x18004c853  jz      short loc_18004C865
0x18004c855  mov     eax, [rbp+4Fh+var_B0]
0x18004c858  add     rax, rax
0x18004c85b  movups  xmm0, [rbp+rax*8+4Fh+var_90]
0x18004c860  movdqu  xmmword ptr [r15], xmm0
0x18004c865  mov     r14b, sil
0x18004c868  mov     [rbp+4Fh+var_C0], sil
0x18004c86c  jmp     short loc_18004C872
0x18004c86e  mov     r14b, [rbp+4Fh+var_C0]
0x18004c872  mov     r15, [rbp+4Fh+var_A8]
0x18004c876  mov     eax, dword ptr [rbp+4Fh+var_80]
0x18004c879  add     rdi, rax
0x18004c87c  sub     r13d, dword ptr [rbp+4Fh+var_80]
0x18004c880  jmp     loc_18004C77C
0x18004c885  or      ecx, 0FFFFFFFFh
0x18004c888  test    eax, eax
0x18004c88a  cmovz   eax, ecx
0x18004c88d  sub     ebx, edi
0x18004c88f  add     ebx, eax
0x18004c891  jmp     short loc_18004C897
0x18004c893  sub     edi, ebx
0x18004c895  mov     ebx, edi
0x18004c897  test    r14b, r14b
0x18004c89a  jz      short loc_18004C8A0
0x18004c89c  test    ebx, ebx
0x18004c89e  jns     short loc_18004C8A3
0x18004c8a0  xor     sil, sil
0x18004c8a3  mov     al, sil
0x18004c8a6  mov     rcx, [rbp+4Fh+var_40]
0x18004c8aa  xor     rcx, rsp; StackCookie
0x18004c8ad  call    __security_check_cookie
0x18004c8b2  mov     rbx, [rsp+0F0h+arg_0]
0x18004c8ba  add     rsp, 0C0h
0x18004c8c1  pop     r15
0x18004c8c3  pop     r14
0x18004c8c5  pop     r13
0x18004c8c7  pop     r12
0x18004c8c9  pop     rdi
0x18004c8ca  pop     rsi
0x18004c8cb  pop     rbp
0x18004c8cc  retn
```
