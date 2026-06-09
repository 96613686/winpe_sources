# SerializeDisplayPhrase(SPDISPLAYPHRASE const *,SPSERIALIZEDDISPLAYPHRASE * *)

- ea: `0x180095c08`
- end: `0x180095e81`
- name: `?SerializeDisplayPhrase@@YAJPEBUSPDISPLAYPHRASE@@PEAPEAUSPSERIALIZEDDISPLAYPHRASE@@@Z`
- size: `633`
- prototype: `__int64 __fastcall(const struct SPDISPLAYPHRASE *, struct SPSERIALIZEDDISPLAYPHRASE **)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000af64`

## callees

- `0x180004312`
- `0x180095c08`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180095d0a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180095d0a`

## pseudocode

```c
__int64 __fastcall SerializeDisplayPhrase(const struct SPDISPLAYPHRASE *a1, struct SPSERIALIZEDDISPLAYPHRASE **a2)
{
  __int64 ulNumTokens; // r11
  unsigned int v4; // eax
  unsigned int v5; // ebx
  unsigned int v6; // ebp
  unsigned int i; // r10d
  SPDISPLAYTOKEN *pTokens; // r8
  const WCHAR *pszLexical; // rax
  __int64 v10; // rcx
  unsigned __int64 v11; // rcx
  const WCHAR *pszDisplay; // r9
  signed __int64 v13; // r8
  int v14; // ecx
  int v15; // edx
  __int64 v16; // rax
  unsigned __int64 v17; // rax
  struct SPSERIALIZEDDISPLAYPHRASE *v18; // rax
  struct SPSERIALIZEDDISPLAYPHRASE *v19; // rdi
  __int64 v21; // r14
  _WORD *v22; // r9
  SPDISPLAYTOKEN *v23; // rax
  unsigned int v24; // r13d
  __int64 v25; // r15
  const WCHAR *v26; // rsi
  __int64 v27; // r8
  const WCHAR *v28; // r12
  __int64 v29; // rbx
  unsigned int v30; // ebx
  signed __int64 v31; // rdx
  int v32; // eax
  int v33; // ecx
  __int64 v34; // rbx
  unsigned int v35; // ebx
  __int64 v36; // rcx
  _WORD *v37; // [rsp+20h] [rbp-48h]
  unsigned int v39; // [rsp+80h] [rbp+18h]
  SPDISPLAYTOKEN *v40; // [rsp+88h] [rbp+20h]

  ulNumTokens = a1->ulNumTokens;
  v4 = 12 * ulNumTokens;
  if ( (unsigned __int64)(12 * ulNumTokens) > 0xFFFFFFFF )
    return 2147500037LL;
  v5 = v4 + 10;
  if ( v4 + 10 < v4 )
    return 2147500037LL;
  v6 = 0;
  for ( i = 0; i < (unsigned int)ulNumTokens; ++i )
  {
    pTokens = a1->pTokens;
    pszLexical = pTokens[i].pszLexical;
    if ( pszLexical )
    {
      v10 = -1;
      do
        ++v10;
      while ( pszLexical[v10] );
      if ( (int)v10 + 1 < (unsigned int)v10 )
        return 2147500037LL;
      v11 = 2LL * (unsigned int)(v10 + 1);
      if ( v11 > 0xFFFFFFFF || (unsigned int)v11 + v5 < v5 )
        return 2147500037LL;
      v5 += v11;
    }
    pszDisplay = pTokens[i].pszDisplay;
    if ( pszDisplay )
    {
      if ( !pszLexical )
        goto LABEL_18;
      v13 = (char *)pszDisplay - (char *)pszLexical;
      do
      {
        v14 = *(const WCHAR *)((char *)pszLexical + v13);
        v15 = *pszLexical - v14;
        if ( v15 )
          break;
        ++pszLexical;
      }
      while ( v14 );
      if ( v15 )
      {
LABEL_18:
        v16 = -1;
        do
          ++v16;
        while ( pszDisplay[v16] );
        if ( (int)v16 + 1 < (unsigned int)v16 )
          return 2147500037LL;
        v17 = 2LL * (unsigned int)(v16 + 1);
        if ( v17 > 0xFFFFFFFF || (unsigned int)v17 + v5 < v5 )
          return 2147500037LL;
        v5 += v17;
      }
    }
  }
  v18 = (struct SPSERIALIZEDDISPLAYPHRASE *)CoTaskMemAlloc(v5);
  v19 = v18;
  if ( !v18 )
    return 2147942414LL;
  v21 = a1->ulNumTokens;
  *(_DWORD *)v18 = v5;
  *((_DWORD *)v18 + 1) = v21;
  v22 = (_WORD *)((char *)v18 + 8 * v21 + 4 * v21 + 8);
  v37 = v22;
  *v22 = 0;
  if ( (_DWORD)v21 )
  {
    v23 = a1->pTokens;
    v24 = 2;
    v40 = v23;
    v25 = 0;
    v39 = 0;
    do
    {
      v26 = v23[v25].pszLexical;
      v27 = 3 * v25;
      v28 = v23[v25].pszDisplay;
      if ( v26 )
      {
        v29 = -1;
        do
          ++v29;
        while ( v26[v29] );
        v30 = 2 * v29 + 2;
        memcpy_0((char *)v22 + v24, v23[v25].pszLexical, v30);
        v22 = v37;
        v27 = 3 * v25;
        v6 = v24;
        v24 += v30;
      }
      *((_DWORD *)v19 + v27 + 2) = v6;
      if ( v28 )
      {
        if ( !v26 )
          goto LABEL_40;
        v31 = (char *)v28 - (char *)v26;
        do
        {
          v32 = *(const WCHAR *)((char *)v26 + v31);
          v33 = *v26 - v32;
          if ( v33 )
            break;
          ++v26;
        }
        while ( v32 );
        if ( v33 )
        {
LABEL_40:
          v6 = v24;
          v34 = -1;
          do
            ++v34;
          while ( v28[v34] );
          v35 = 2 * v34 + 2;
          memcpy_0((char *)v22 + v24, v28, v35);
          v24 += v35;
          v27 = 3 * v25;
        }
      }
      else
      {
        v6 = 0;
      }
      v36 = v25;
      v22 = v37;
      ++v25;
      *((_DWORD *)v19 + v27 + 3) = v6;
      v6 = 0;
      *((_BYTE *)v19 + 4 * v27 + 16) = v40[v36].bDisplayAttributes;
      ++v39;
      v23 = v40;
    }
    while ( v39 < (unsigned int)v21 );
  }
  *a2 = v19;
  return 0;
}

```

## disassembly

```asm
0x180095c08  mov     [rsp+arg_0], rbx
0x180095c0d  mov     [rsp+arg_8], rdx
0x180095c12  push    rbp
0x180095c13  push    rsi
0x180095c14  push    rdi
0x180095c15  push    r12
0x180095c17  push    r13
0x180095c19  push    r14
0x180095c1b  push    r15
0x180095c1d  sub     rsp, 30h
0x180095c21  mov     r11d, [rcx]
0x180095c24  mov     edi, 0FFFFFFFFh
0x180095c29  mov     rsi, rcx
0x180095c2c  lea     rax, [r11+r11*2]
0x180095c30  shl     rax, 2
0x180095c34  cmp     rax, rdi
0x180095c37  ja      loc_180095E67
0x180095c3d  lea     ebx, [rax+0Ah]
0x180095c40  cmp     ebx, eax
0x180095c42  jb      loc_180095E67
0x180095c48  xor     ebp, ebp
0x180095c4a  mov     r10d, ebp
0x180095c4d  or      r14, 0FFFFFFFFFFFFFFFFh
0x180095c51  cmp     r10d, r11d
0x180095c54  jnb     loc_180095D08
0x180095c5a  mov     r8, [rsi+8]
0x180095c5e  mov     eax, r10d
0x180095c61  lea     r9, [rax+rax*2]
0x180095c65  mov     rax, [r8+r9*8]
0x180095c69  test    rax, rax
0x180095c6c  jz      short loc_180095CA0
0x180095c6e  mov     rcx, r14
0x180095c71  inc     rcx
0x180095c74  cmp     [rax+rcx*2], bp
0x180095c78  jnz     short loc_180095C71
0x180095c7a  lea     edx, [rcx+1]
0x180095c7d  cmp     edx, ecx
0x180095c7f  jb      loc_180095E67
0x180095c85  mov     ecx, edx
0x180095c87  add     rcx, rcx
0x180095c8a  cmp     rcx, rdi
0x180095c8d  ja      loc_180095E67
0x180095c93  lea     edx, [rcx+rbx]
0x180095c96  cmp     edx, ebx
0x180095c98  jb      loc_180095E67
0x180095c9e  mov     ebx, edx
0x180095ca0  mov     r9, [r8+r9*8+8]
0x180095ca5  test    r9, r9
0x180095ca8  jz      short loc_180095D00
0x180095caa  test    rax, rax
0x180095cad  jz      short loc_180095CCD
0x180095caf  mov     r8, r9
0x180095cb2  sub     r8, rax
0x180095cb5  movzx   edx, word ptr [rax]
0x180095cb8  movzx   ecx, word ptr [rax+r8]
0x180095cbd  sub     edx, ecx
0x180095cbf  jnz     short loc_180095CC9
0x180095cc1  add     rax, 2
0x180095cc5  test    ecx, ecx
0x180095cc7  jnz     short loc_180095CB5
0x180095cc9  test    edx, edx
0x180095ccb  jz      short loc_180095D00
0x180095ccd  mov     rax, r14
0x180095cd0  inc     rax
0x180095cd3  cmp     [r9+rax*2], bp
0x180095cd8  jnz     short loc_180095CD0
0x180095cda  lea     ecx, [rax+1]
0x180095cdd  cmp     ecx, eax
0x180095cdf  jb      loc_180095E67
0x180095ce5  mov     eax, ecx
0x180095ce7  add     rax, rax
0x180095cea  cmp     rax, rdi
0x180095ced  ja      loc_180095E67
0x180095cf3  lea     ecx, [rax+rbx]
0x180095cf6  cmp     ecx, ebx
0x180095cf8  jb      loc_180095E67
0x180095cfe  mov     ebx, ecx
0x180095d00  inc     r10d
0x180095d03  jmp     loc_180095C51
0x180095d08  mov     ecx, ebx; cb
0x180095d0a  call    cs:__imp_CoTaskMemAlloc
0x180095d10  mov     rdi, rax
0x180095d13  test    rax, rax
0x180095d16  jnz     short loc_180095D22
0x180095d18  mov     eax, 8007000Eh
0x180095d1d  jmp     loc_180095E6C
0x180095d22  mov     r14d, [rsi]
0x180095d25  mov     [rax], ebx
0x180095d27  mov     [rax+4], r14d
0x180095d2b  lea     r9, [r14+1]
0x180095d2f  lea     r9, [r14+r9*2]
0x180095d33  lea     r9, [rax+r9*4]
0x180095d37  mov     [rsp+68h+var_48], r9
0x180095d3c  mov     [r9], bp
0x180095d40  test    r14d, r14d
0x180095d43  jz      loc_180095E5B
0x180095d49  mov     rax, [rsi+8]
0x180095d4d  mov     r13d, 2
0x180095d53  mov     [rsp+68h+arg_18], rax
0x180095d5b  mov     r15, rbp
0x180095d5e  mov     [rsp+68h+arg_10], ebp
0x180095d65  lea     rcx, [r15+r15*2]
0x180095d69  mov     rsi, [rax+rcx*8]
0x180095d6d  lea     r8, [r15+r15*2]
0x180095d71  mov     r12, [rax+rcx*8+8]
0x180095d76  test    rsi, rsi
0x180095d79  jz      short loc_180095DAF
0x180095d7b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180095d7f  inc     rbx
0x180095d82  cmp     [rsi+rbx*2], bp
0x180095d86  jnz     short loc_180095D7F
0x180095d88  lea     ebx, ds:2[rbx*2]
0x180095d8f  mov     ecx, r13d
0x180095d92  mov     r8d, ebx; Size
0x180095d95  add     rcx, r9; void *
0x180095d98  mov     rdx, rsi; Src
0x180095d9b  call    memcpy_0
0x180095da0  mov     r9, [rsp+68h+var_48]
0x180095da5  lea     r8, [r15+r15*2]
0x180095da9  mov     ebp, r13d
0x180095dac  add     r13d, ebx
0x180095daf  xor     r10d, r10d
0x180095db2  mov     [rdi+r8*4+8], ebp
0x180095db7  test    r12, r12
0x180095dba  jnz     short loc_180095DC1
0x180095dbc  mov     ebp, r10d
0x180095dbf  jmp     short loc_180095E13
0x180095dc1  test    rsi, rsi
0x180095dc4  jz      short loc_180095DE3
0x180095dc6  mov     rdx, r12
0x180095dc9  sub     rdx, rsi
0x180095dcc  movzx   ecx, word ptr [rsi]
0x180095dcf  movzx   eax, word ptr [rsi+rdx]
0x180095dd3  sub     ecx, eax
0x180095dd5  jnz     short loc_180095DDF
0x180095dd7  add     rsi, 2
0x180095ddb  test    eax, eax
0x180095ddd  jnz     short loc_180095DCC
0x180095ddf  test    ecx, ecx
0x180095de1  jz      short loc_180095E13
0x180095de3  mov     ebp, r13d
0x180095de6  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180095dea  inc     rbx
0x180095ded  cmp     [r12+rbx*2], r10w
0x180095df2  jnz     short loc_180095DEA
0x180095df4  lea     ebx, ds:2[rbx*2]
0x180095dfb  mov     ecx, r13d
0x180095dfe  mov     r8d, ebx; Size
0x180095e01  add     rcx, r9; void *
0x180095e04  mov     rdx, r12; Src
0x180095e07  call    memcpy_0
0x180095e0c  add     r13d, ebx
0x180095e0f  lea     r8, [r15+r15*2]
0x180095e13  mov     rax, [rsp+68h+arg_18]
0x180095e1b  lea     rcx, [r15+r15*2]
0x180095e1f  mov     r9, [rsp+68h+var_48]
0x180095e24  inc     r15
0x180095e27  mov     [rdi+r8*4+0Ch], ebp
0x180095e2c  mov     ebp, 0
0x180095e31  mov     al, [rax+rcx*8+10h]
0x180095e35  mov     [rdi+r8*4+10h], al
0x180095e3a  mov     eax, [rsp+68h+arg_10]
0x180095e41  inc     eax
0x180095e43  mov     [rsp+68h+arg_10], eax
0x180095e4a  cmp     eax, r14d
0x180095e4d  mov     rax, [rsp+68h+arg_18]
0x180095e55  jb      loc_180095D65
0x180095e5b  mov     rax, [rsp+68h+arg_8]
0x180095e60  mov     [rax], rdi
0x180095e63  xor     eax, eax
0x180095e65  jmp     short loc_180095E6C
0x180095e67  mov     eax, 80004005h
0x180095e6c  mov     rbx, [rsp+68h+arg_0]
0x180095e71  add     rsp, 30h
0x180095e75  pop     r15
0x180095e77  pop     r14
0x180095e79  pop     r13
0x180095e7b  pop     r12
0x180095e7d  pop     rdi
0x180095e7e  pop     rsi
0x180095e7f  pop     rbp
0x180095e80  retn
```
