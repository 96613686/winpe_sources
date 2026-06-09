# LocalCredUnmarshalCredentialW(ushort const *,_CRED_MARSHAL_TYPE *,void * *)

- ea: `0x180015068`
- end: `0x1800152b7`
- name: `?LocalCredUnmarshalCredentialW@@YAKPEBGPEAW4_CRED_MARSHAL_TYPE@@PEAPEAX@Z`
- size: `591`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, enum _CRED_MARSHAL_TYPE *, void **)`
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x18000fae0`
- `0x1800110f0`
- `0x1800113a0`
- `0x180017970`
- `0x180017e40`
- `0x18001fe8c`

## callees

- `0x18000ba8c`
- `0x18000c2fc`
- `0x180015068`
- `0x180018600`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001511c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800151b6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001523b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001511c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800151b6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001523b`

## pseudocode

```c
__int64 __fastcall LocalCredUnmarshalCredentialW(const unsigned __int16 *a1, enum _CRED_MARSHAL_TYPE *a2, char **a3)
{
  unsigned __int64 v4; // r10
  const unsigned __int16 *v5; // r14
  _DWORD *v6; // r8
  int v7; // r10d
  UINT v8; // r11d
  char *v9; // rsi
  __int64 v10; // r9
  __int64 v11; // rbx
  char *v12; // r15
  int i; // edx
  unsigned int v14; // ebx
  char *v15; // rax
  _QWORD v17[2]; // [rsp+20h] [rbp-10h] BYREF
  unsigned int v18; // [rsp+60h] [rbp+30h] BYREF
  unsigned int v19; // [rsp+78h] [rbp+48h] BYREF

  v19 = 0;
  v18 = 0;
  if ( !a1 )
    goto LABEL_36;
  v4 = -1;
  do
    ++v4;
  while ( a1[v4] );
  if ( v4 <= 2 )
    goto LABEL_36;
  if ( *a1 != 64 )
    goto LABEL_36;
  if ( a1[1] != 64 )
    goto LABEL_36;
  v5 = &a1[v4];
  v17[0] = a1 + 2;
  if ( !(unsigned int)CredpUnmarshalChar(v17, v5, a2) )
    goto LABEL_36;
  if ( *v6 != 1 )
  {
    switch ( *v6 )
    {
      case 2:
        goto LABEL_12;
      case 3:
        for ( i = 0; i < 5; ++i )
        {
          if ( asc_1800336B0[i] != *(_WORD *)(v17[0] + 2LL * i) )
            goto LABEL_36;
        }
        v17[0] += 10LL;
        v9 = (char *)LocalAlloc(v8, (unsigned int)(2 * v7 + 18) + 2LL);
        if ( v9 )
        {
          if ( !(unsigned int)CredpUnmarshalBytes(v17, v5, &v18, 4) )
            goto LABEL_24;
          v10 = v18;
          v11 = v18;
          if ( v18 != ((v18 + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) || !v18 )
            goto LABEL_24;
          v12 = v9 + 16;
          *(_DWORD *)v9 = v18;
          *((_QWORD *)v9 + 1) = v9 + 16;
LABEL_28:
          if ( (unsigned int)CredpUnmarshalBytes(v17, v5, v12, v10) )
          {
            *(_WORD *)&v12[v11] = 0;
            goto LABEL_32;
          }
LABEL_24:
          v14 = 87;
          *a3 = 0;
LABEL_34:
          SspiLocalFree(v9);
          return v14;
        }
        goto LABEL_22;
      case 4:
LABEL_12:
        v9 = (char *)LocalAlloc(v8, (unsigned int)(2 * v7 + 10) + 2LL);
        if ( v9 )
        {
          if ( !(unsigned int)CredpUnmarshalBytes(v17, v5, &v19, 4) )
            goto LABEL_24;
          v10 = v19;
          v11 = v19;
          if ( v19 != ((v19 + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) || !v19 )
            goto LABEL_24;
          v12 = v9 + 8;
          *(_QWORD *)v9 = v9 + 8;
          goto LABEL_28;
        }
        goto LABEL_22;
    }
LABEL_36:
    v14 = 87;
    goto LABEL_37;
  }
  v15 = (char *)LocalAlloc(v8, 0x1Au);
  v9 = v15;
  if ( !v15 )
  {
LABEL_22:
    v14 = 8;
LABEL_37:
    *a3 = 0;
    return v14;
  }
  *(_DWORD *)v15 = 24;
  if ( !(unsigned int)CredpUnmarshalBytes(v17, v5, v15 + 4, 20) )
    goto LABEL_24;
LABEL_32:
  if ( (const unsigned __int16 *)v17[0] == v5 )
  {
    v14 = 0;
    *a3 = v9;
    return v14;
  }
  *a3 = 0;
  v14 = 87;
  if ( v9 )
    goto LABEL_34;
  return v14;
}

```

## disassembly

```asm
0x180015068  mov     [rsp-28h+arg_8], rbx
0x18001506d  mov     [rsp-28h+arg_10], rsi
0x180015072  push    rbp
0x180015073  push    rdi
0x180015074  push    r12
0x180015076  push    r14
0x180015078  push    r15
0x18001507a  mov     rbp, rsp
0x18001507d  sub     rsp, 30h
0x180015081  xor     r12d, r12d
0x180015084  mov     rdi, r8
0x180015087  mov     [rbp+arg_18], r12d
0x18001508b  mov     r8, rdx
0x18001508e  mov     [rbp+arg_0], r12d
0x180015092  test    rcx, rcx
0x180015095  jz      loc_180015296
0x18001509b  or      r10, 0FFFFFFFFFFFFFFFFh
0x18001509f  inc     r10
0x1800150a2  cmp     [rcx+r10*2], r12w
0x1800150a7  jnz     short loc_18001509F
0x1800150a9  cmp     r10, 2
0x1800150ad  jbe     loc_180015296
0x1800150b3  mov     r11d, 40h ; '@'
0x1800150b9  cmp     [rcx], r11w
0x1800150bd  jnz     loc_180015296
0x1800150c3  cmp     [rcx+2], r11w
0x1800150c8  jnz     loc_180015296
0x1800150ce  lea     r14, [rcx+r10*2]
0x1800150d2  lea     rax, [rcx+4]
0x1800150d6  mov     rdx, r14
0x1800150d9  lea     rcx, [rbp+var_10]
0x1800150dd  mov     [rbp+var_10], rax
0x1800150e1  call    CredpUnmarshalChar
0x1800150e6  test    eax, eax
0x1800150e8  jz      loc_180015296
0x1800150ee  mov     ecx, [r8]
0x1800150f1  sub     ecx, 1
0x1800150f4  jz      loc_180015233
0x1800150fa  sub     ecx, 1
0x1800150fd  jz      short loc_18001510D
0x1800150ff  sub     ecx, 1
0x180015102  jz      short loc_180015175
0x180015104  cmp     ecx, 1
0x180015107  jnz     loc_180015296
0x18001510d  lea     edx, ds:0Ah[r10*2]
0x180015115  mov     ecx, r11d; uFlags
0x180015118  add     rdx, 2; uBytes
0x18001511c  call    cs:__imp_LocalAlloc
0x180015122  mov     rsi, rax
0x180015125  test    rax, rax
0x180015128  jz      loc_1800151C4
0x18001512e  mov     r9d, 4
0x180015134  lea     r8, [rbp+arg_18]
0x180015138  mov     rdx, r14
0x18001513b  lea     rcx, [rbp+var_10]
0x18001513f  call    CredpUnmarshalBytes
0x180015144  test    eax, eax
0x180015146  jz      loc_1800151E8
0x18001514c  mov     r9d, [rbp+arg_18]
0x180015150  mov     ebx, r9d
0x180015153  lea     rax, [r9+1]
0x180015157  and     rax, 0FFFFFFFFFFFFFFFEh
0x18001515b  cmp     r9, rax
0x18001515e  jnz     loc_1800151E8
0x180015164  test    r9d, r9d
0x180015167  jz      short loc_1800151E8
0x180015169  lea     r15, [rsi+8]
0x18001516d  mov     [rsi], r15
0x180015170  jmp     loc_180015219
0x180015175  mov     r8, [rbp+var_10]
0x180015179  mov     edx, r12d
0x18001517c  cmp     edx, 5
0x18001517f  jge     short loc_18001519F
0x180015181  movsxd  rcx, edx
0x180015184  lea     r9, asc_1800336B0; "\a\b"
0x18001518b  movzx   eax, word ptr [r8+rcx*2]
0x180015190  cmp     [r9+rcx*2], ax
0x180015195  jnz     loc_180015296
0x18001519b  inc     edx
0x18001519d  jmp     short loc_18001517C
0x18001519f  lea     edx, ds:12h[r10*2]
0x1800151a7  add     r8, 0Ah
0x1800151ab  add     rdx, 2; uBytes
0x1800151af  mov     [rbp+var_10], r8
0x1800151b3  mov     ecx, r11d; uFlags
0x1800151b6  call    cs:__imp_LocalAlloc
0x1800151bc  mov     rsi, rax
0x1800151bf  test    rax, rax
0x1800151c2  jnz     short loc_1800151CE
0x1800151c4  mov     ebx, 8
0x1800151c9  jmp     loc_18001529B
0x1800151ce  mov     r9d, 4
0x1800151d4  lea     r8, [rbp+arg_0]
0x1800151d8  mov     rdx, r14
0x1800151db  lea     rcx, [rbp+var_10]
0x1800151df  call    CredpUnmarshalBytes
0x1800151e4  test    eax, eax
0x1800151e6  jnz     short loc_1800151F5
0x1800151e8  mov     ebx, 57h ; 'W'
0x1800151ed  mov     [rdi], r12
0x1800151f0  jmp     loc_180015284
0x1800151f5  mov     r9d, [rbp+arg_0]
0x1800151f9  mov     ebx, r9d
0x1800151fc  lea     rax, [r9+1]
0x180015200  and     rax, 0FFFFFFFFFFFFFFFEh
0x180015204  cmp     r9, rax
0x180015207  jnz     short loc_1800151E8
0x180015209  test    r9d, r9d
0x18001520c  jz      short loc_1800151E8
0x18001520e  lea     r15, [rsi+10h]
0x180015212  mov     [rsi], r9d
0x180015215  mov     [rsi+8], r15
0x180015219  mov     r8, r15
0x18001521c  lea     rcx, [rbp+var_10]
0x180015220  mov     rdx, r14
0x180015223  call    CredpUnmarshalBytes
0x180015228  test    eax, eax
0x18001522a  jz      short loc_1800151E8
0x18001522c  mov     [r15+rbx], r12w
0x180015231  jmp     short loc_180015271
0x180015233  mov     edx, 1Ah; uBytes
0x180015238  mov     ecx, r11d; uFlags
0x18001523b  call    cs:__imp_LocalAlloc
0x180015241  mov     rsi, rax
0x180015244  test    rax, rax
0x180015247  jz      loc_1800151C4
0x18001524d  lea     r8, [rax+4]
0x180015251  mov     dword ptr [rax], 18h
0x180015257  mov     r9d, 14h
0x18001525d  lea     rcx, [rbp+var_10]
0x180015261  mov     rdx, r14
0x180015264  call    CredpUnmarshalBytes
0x180015269  test    eax, eax
0x18001526b  jz      loc_1800151E8
0x180015271  cmp     [rbp+var_10], r14
0x180015275  jz      short loc_18001528E
0x180015277  mov     [rdi], r12
0x18001527a  mov     ebx, 57h ; 'W'
0x18001527f  test    rsi, rsi
0x180015282  jz      short loc_18001529E
0x180015284  mov     rcx, rsi; DataBuffer
0x180015287  call    SspiLocalFree
0x18001528c  jmp     short loc_18001529E
0x18001528e  mov     ebx, r12d
0x180015291  mov     [rdi], rsi
0x180015294  jmp     short loc_18001529E
0x180015296  mov     ebx, 57h ; 'W'
0x18001529b  mov     [rdi], r12
0x18001529e  mov     rsi, [rsp+30h+arg_10]
0x1800152a3  mov     eax, ebx
0x1800152a5  mov     rbx, [rsp+30h+arg_8]
0x1800152aa  add     rsp, 30h
0x1800152ae  pop     r15
0x1800152b0  pop     r14
0x1800152b2  pop     r12
0x1800152b4  pop     rdi
0x1800152b5  pop     rbp
0x1800152b6  retn
```
