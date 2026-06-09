# SerializeDisplayPhrase(SPDISPLAYPHRASE const *,SPSERIALIZEDDISPLAYPHRASE * *)

- ea: `0x180008b08`
- end: `0x180008d7e`
- name: `?SerializeDisplayPhrase@@YAJPEBUSPDISPLAYPHRASE@@PEAPEAUSPSERIALIZEDDISPLAYPHRASE@@@Z`
- size: `630`
- prototype: `__int64 __fastcall(const struct SPDISPLAYPHRASE *, struct SPSERIALIZEDDISPLAYPHRASE **)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800040f0`

## callees

- `0x1800031c8`
- `0x180008b08`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008c0e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008c0e`

## pseudocode

```c
__int64 __fastcall SerializeDisplayPhrase(const struct SPDISPLAYPHRASE *a1, struct SPSERIALIZEDDISPLAYPHRASE **a2)
{
  __int64 ulNumTokens; // r9
  unsigned int v4; // eax
  unsigned int v5; // ebx
  unsigned int v6; // ebp
  SPDISPLAYTOKEN *pTokens; // rdi
  unsigned int i; // r11d
  const WCHAR *pszLexical; // rax
  __int64 v10; // rcx
  unsigned __int64 v11; // rcx
  const WCHAR *pszDisplay; // r10
  signed __int64 v13; // r8
  int v14; // ecx
  int v15; // edx
  __int64 v16; // rax
  unsigned __int64 v17; // rax
  struct SPSERIALIZEDDISPLAYPHRASE *v18; // rax
  struct SPSERIALIZEDDISPLAYPHRASE *v19; // rdi
  unsigned int v21; // r13d
  ULONG v22; // r12d
  _WORD *v23; // r9
  SPDISPLAYTOKEN *v24; // rax
  const WCHAR *v25; // rsi
  __int64 v26; // r8
  const WCHAR *v27; // r15
  __int64 v28; // rbx
  unsigned int v29; // ebx
  signed __int64 v30; // rdx
  int v31; // eax
  int v32; // ecx
  __int64 v33; // rbx
  unsigned int v34; // ebx
  __int64 v35; // [rsp+20h] [rbp-48h]
  _WORD *j; // [rsp+88h] [rbp+20h]

  ulNumTokens = a1->ulNumTokens;
  v4 = 12 * ulNumTokens;
  if ( (unsigned __int64)(12 * ulNumTokens) > 0xFFFFFFFF )
    return 2147500037LL;
  v5 = v4 + 10;
  if ( v4 + 10 < v4 )
    return 2147500037LL;
  v6 = 0;
  if ( (_DWORD)ulNumTokens )
  {
    pTokens = a1->pTokens;
    for ( i = 0; i < (unsigned int)ulNumTokens; ++i )
    {
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
  }
  v18 = (struct SPSERIALIZEDDISPLAYPHRASE *)CoTaskMemAlloc(v5);
  v19 = v18;
  if ( !v18 )
    return 2147942414LL;
  *(_DWORD *)v18 = v5;
  v21 = 2;
  v22 = 0;
  *((_DWORD *)v18 + 1) = a1->ulNumTokens;
  v23 = (_WORD *)((char *)v18 + 8 * a1->ulNumTokens + 4 * a1->ulNumTokens + 8);
  *v23 = 0;
  for ( j = v23; v22 < a1->ulNumTokens; *((_BYTE *)v19 + 4 * v26 + 16) = *(&a1->pTokens->bDisplayAttributes + 8 * v35) )
  {
    v24 = a1->pTokens;
    v25 = v24[v22].pszLexical;
    v26 = 3LL * v22;
    v27 = v24[v22].pszDisplay;
    v35 = v26;
    if ( v25 )
    {
      v28 = -1;
      do
        ++v28;
      while ( v25[v28] );
      v29 = 2 * v28 + 2;
      memcpy_0((char *)v23 + v21, v25, v29);
      v26 = 3LL * v22;
      v6 = v21;
      v23 = j;
      v21 += v29;
    }
    *((_DWORD *)v19 + v26 + 2) = v6;
    if ( v27 )
    {
      if ( !v25 )
        goto LABEL_39;
      v30 = (char *)v27 - (char *)v25;
      do
      {
        v31 = *(const WCHAR *)((char *)v25 + v30);
        v32 = *v25 - v31;
        if ( v32 )
          break;
        ++v25;
      }
      while ( v31 );
      if ( v32 )
      {
LABEL_39:
        v6 = v21;
        v33 = -1;
        do
          ++v33;
        while ( v27[v33] );
        v34 = 2 * v33 + 2;
        memcpy_0((char *)v23 + v21, v27, v34);
        v26 = 3LL * v22;
        v21 += v34;
      }
    }
    else
    {
      v6 = 0;
    }
    ++v22;
    v23 = j;
    *((_DWORD *)v19 + v26 + 3) = v6;
    v6 = 0;
  }
  *a2 = v19;
  return 0;
}

```

## disassembly

```asm
0x180008b08  mov     [rsp+arg_0], rbx
0x180008b0d  mov     [rsp+arg_8], rdx
0x180008b12  push    rbp
0x180008b13  push    rsi
0x180008b14  push    rdi
0x180008b15  push    r12
0x180008b17  push    r13
0x180008b19  push    r14
0x180008b1b  push    r15
0x180008b1d  sub     rsp, 30h
0x180008b21  mov     r9d, [rcx]
0x180008b24  mov     esi, 0FFFFFFFFh
0x180008b29  mov     r14, rcx
0x180008b2c  lea     rax, [r9+r9*2]
0x180008b30  shl     rax, 2
0x180008b34  cmp     rax, rsi
0x180008b37  ja      loc_180008D64
0x180008b3d  lea     ebx, [rax+0Ah]
0x180008b40  cmp     ebx, eax
0x180008b42  jb      loc_180008D64
0x180008b48  or      r15, 0FFFFFFFFFFFFFFFFh
0x180008b4c  xor     ebp, ebp
0x180008b4e  test    r9d, r9d
0x180008b51  jz      loc_180008C0C
0x180008b57  mov     rdi, [rcx+8]
0x180008b5b  mov     r11d, ebp
0x180008b5e  mov     eax, r11d
0x180008b61  lea     r10, [rax+rax*2]
0x180008b65  mov     rax, [rdi+r10*8]
0x180008b69  test    rax, rax
0x180008b6c  jz      short loc_180008BA0
0x180008b6e  mov     rcx, r15
0x180008b71  inc     rcx
0x180008b74  cmp     [rax+rcx*2], bp
0x180008b78  jnz     short loc_180008B71
0x180008b7a  lea     edx, [rcx+1]
0x180008b7d  cmp     edx, ecx
0x180008b7f  jb      loc_180008D64
0x180008b85  mov     ecx, edx
0x180008b87  add     rcx, rcx
0x180008b8a  cmp     rcx, rsi
0x180008b8d  ja      loc_180008D64
0x180008b93  lea     edx, [rcx+rbx]
0x180008b96  cmp     edx, ebx
0x180008b98  jb      loc_180008D64
0x180008b9e  mov     ebx, edx
0x180008ba0  mov     r10, [rdi+r10*8+8]
0x180008ba5  test    r10, r10
0x180008ba8  jz      short loc_180008C00
0x180008baa  test    rax, rax
0x180008bad  jz      short loc_180008BCD
0x180008baf  mov     r8, r10
0x180008bb2  sub     r8, rax
0x180008bb5  movzx   edx, word ptr [rax]
0x180008bb8  movzx   ecx, word ptr [rax+r8]
0x180008bbd  sub     edx, ecx
0x180008bbf  jnz     short loc_180008BC9
0x180008bc1  add     rax, 2
0x180008bc5  test    ecx, ecx
0x180008bc7  jnz     short loc_180008BB5
0x180008bc9  test    edx, edx
0x180008bcb  jz      short loc_180008C00
0x180008bcd  mov     rax, r15
0x180008bd0  inc     rax
0x180008bd3  cmp     [r10+rax*2], bp
0x180008bd8  jnz     short loc_180008BD0
0x180008bda  lea     ecx, [rax+1]
0x180008bdd  cmp     ecx, eax
0x180008bdf  jb      loc_180008D64
0x180008be5  mov     eax, ecx
0x180008be7  add     rax, rax
0x180008bea  cmp     rax, rsi
0x180008bed  ja      loc_180008D64
0x180008bf3  lea     ecx, [rax+rbx]
0x180008bf6  cmp     ecx, ebx
0x180008bf8  jb      loc_180008D64
0x180008bfe  mov     ebx, ecx
0x180008c00  inc     r11d
0x180008c03  cmp     r11d, r9d
0x180008c06  jb      loc_180008B5E
0x180008c0c  mov     ecx, ebx; cb
0x180008c0e  call    cs:__imp_CoTaskMemAlloc
0x180008c14  mov     rdi, rax
0x180008c17  test    rax, rax
0x180008c1a  jnz     short loc_180008C26
0x180008c1c  mov     eax, 8007000Eh
0x180008c21  jmp     loc_180008D69
0x180008c26  mov     [rax], ebx
0x180008c28  mov     r13d, 2
0x180008c2e  mov     eax, [r14]
0x180008c31  mov     r12d, ebp
0x180008c34  mov     [rdi+4], eax
0x180008c37  mov     eax, [r14]
0x180008c3a  lea     r9, [rax+1]
0x180008c3e  lea     r9, [rax+r9*2]
0x180008c42  lea     r9, [rdi+r9*4]
0x180008c46  mov     [r9], bp
0x180008c4a  mov     [rsp+68h+arg_18], r9
0x180008c52  cmp     [r14], ebp
0x180008c55  jbe     loc_180008D58
0x180008c5b  mov     rax, [r14+8]
0x180008c5f  mov     ecx, r12d
0x180008c62  lea     rdx, [rcx+rcx*2]
0x180008c66  mov     rsi, [rax+rdx*8]
0x180008c6a  lea     r8, [rcx+rcx*2]
0x180008c6e  mov     r15, [rax+rdx*8+8]
0x180008c73  mov     [rsp+68h+var_48], rdx
0x180008c78  mov     [rsp+68h+arg_10], r8
0x180008c80  test    rsi, rsi
0x180008c83  jz      short loc_180008CC0
0x180008c85  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180008c89  inc     rbx
0x180008c8c  cmp     [rsi+rbx*2], bp
0x180008c90  jnz     short loc_180008C89
0x180008c92  lea     ebx, ds:2[rbx*2]
0x180008c99  mov     ecx, r13d
0x180008c9c  mov     r8d, ebx; Size
0x180008c9f  add     rcx, r9; void *
0x180008ca2  mov     rdx, rsi; Src
0x180008ca5  call    memcpy_0
0x180008caa  mov     r8, [rsp+68h+arg_10]
0x180008cb2  mov     ebp, r13d
0x180008cb5  mov     r9, [rsp+68h+arg_18]
0x180008cbd  add     r13d, ebx
0x180008cc0  xor     r10d, r10d
0x180008cc3  mov     [rdi+r8*4+8], ebp
0x180008cc8  test    r15, r15
0x180008ccb  jnz     short loc_180008CD2
0x180008ccd  mov     ebp, r10d
0x180008cd0  jmp     short loc_180008D28
0x180008cd2  test    rsi, rsi
0x180008cd5  jz      short loc_180008CF4
0x180008cd7  mov     rdx, r15
0x180008cda  sub     rdx, rsi
0x180008cdd  movzx   ecx, word ptr [rsi]
0x180008ce0  movzx   eax, word ptr [rsi+rdx]
0x180008ce4  sub     ecx, eax
0x180008ce6  jnz     short loc_180008CF0
0x180008ce8  add     rsi, 2
0x180008cec  test    eax, eax
0x180008cee  jnz     short loc_180008CDD
0x180008cf0  test    ecx, ecx
0x180008cf2  jz      short loc_180008D28
0x180008cf4  mov     ebp, r13d
0x180008cf7  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180008cfb  inc     rbx
0x180008cfe  cmp     [r15+rbx*2], r10w
0x180008d03  jnz     short loc_180008CFB
0x180008d05  lea     ebx, ds:2[rbx*2]
0x180008d0c  mov     ecx, r13d
0x180008d0f  mov     r8d, ebx; Size
0x180008d12  add     rcx, r9; void *
0x180008d15  mov     rdx, r15; Src
0x180008d18  call    memcpy_0
0x180008d1d  mov     r8, [rsp+68h+arg_10]
0x180008d25  add     r13d, ebx
0x180008d28  mov     rcx, [rsp+68h+var_48]
0x180008d2d  inc     r12d
0x180008d30  mov     r9, [rsp+68h+arg_18]
0x180008d38  mov     [rdi+r8*4+0Ch], ebp
0x180008d3d  mov     ebp, 0
0x180008d42  mov     rax, [r14+8]
0x180008d46  mov     cl, [rax+rcx*8+10h]
0x180008d4a  mov     [rdi+r8*4+10h], cl
0x180008d4f  cmp     r12d, [r14]
0x180008d52  jb      loc_180008C5B
0x180008d58  mov     rax, [rsp+68h+arg_8]
0x180008d5d  mov     [rax], rdi
0x180008d60  xor     eax, eax
0x180008d62  jmp     short loc_180008D69
0x180008d64  mov     eax, 80004005h
0x180008d69  mov     rbx, [rsp+68h+arg_0]
0x180008d6e  add     rsp, 30h
0x180008d72  pop     r15
0x180008d74  pop     r14
0x180008d76  pop     r13
0x180008d78  pop     r12
0x180008d7a  pop     rdi
0x180008d7b  pop     rsi
0x180008d7c  pop     rbp
0x180008d7d  retn
```
