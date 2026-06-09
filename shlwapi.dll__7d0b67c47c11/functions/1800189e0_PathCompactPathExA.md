# PathCompactPathExA

- ea: `0x1800189e0`
- end: `0x180018bbf`
- name: `PathCompactPathExA`
- size: `479`
- prototype: `BOOL __stdcall(LPSTR pszOut, LPCSTR pszSrc, UINT cchMax, DWORD dwFlags)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180013066`
- `0x180017344`
- `0x1800181ac`
- `0x180018204`
- `0x1800189e0`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameA` at `0x180018a76`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameA` at `0x180018a76`
- `api-ms-win-core-stringansi-l1-1-0!CharNextA` at `0x180018a64`
- `api-ms-win-core-stringansi-l1-1-0!CharNextA` at `0x180018a64`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x180018a25`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x180018a82`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x180018b50`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x180018a25`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x180018a82`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x180018b50`

## pseudocode

```c
BOOL __stdcall PathCompactPathExA(LPSTR pszOut, LPCSTR pszSrc, UINT cchMax, DWORD dwFlags)
{
  __int64 v4; // rsi
  unsigned __int64 v7; // r15
  CHAR v9; // al
  CHAR v10; // r12
  const CHAR *v11; // rcx
  const CHAR *FileNameA; // rbp
  int v13; // r13d
  __int64 v14; // r8
  unsigned int v15; // esi
  CHAR v16; // cl
  int v17; // r14d
  int v18; // esi

  v4 = cchMax;
  if ( !pszSrc || !pszOut || !cchMax )
    return 0;
  v7 = cchMax;
  memset_0(pszOut, 0, cchMax);
  if ( lstrlenA(pszSrc) + 1 < (unsigned int)v4 )
  {
    StringCchCopyA(pszOut, (unsigned int)v4, pszSrc);
    return 1;
  }
  v9 = *pszSrc;
  v10 = 92;
  if ( *pszSrc )
  {
    v11 = pszSrc;
    do
    {
      if ( v9 == 47 || v9 == 92 )
        v10 = v9;
      v11 = CharNextA(v11);
      v9 = *v11;
    }
    while ( *v11 );
  }
  FileNameA = PathFindFileNameA(pszSrc);
  v13 = lstrlenA(FileNameA);
  if ( FileNameA == pszSrc && (unsigned int)v4 > 3 )
  {
    StringCchCopyA(pszOut, (unsigned int)(v4 - 3), pszSrc);
    if ( (unsigned int)IsTrailByte(pszSrc, &pszSrc[(unsigned int)v4 - 4]) )
      pszOut[v4 - 5] = 0;
    StringCchCatA(pszOut, (unsigned int)v4, "...");
    return 1;
  }
  if ( (unsigned int)v4 < 7 )
  {
    v14 = 0;
    v15 = v4 - 1;
    if ( v15 )
    {
      do
      {
        v16 = 46;
        if ( (_DWORD)v14 == 3 )
          v16 = v10;
        pszOut[v14] = v16;
        v14 = (unsigned int)(v14 + 1);
      }
      while ( (unsigned int)v14 < v15 );
    }
    return 1;
  }
  v17 = 0;
  if ( (int)v4 - v13 - 4 >= 0 )
    v17 = v4 - v13 - 4;
  if ( v17 > 0 && (unsigned int)IsTrailByte(pszSrc, &pszSrc[v17]) )
    --v17;
  StringCchCopyA(pszOut, v17, pszSrc);
  StringCchCatA(pszOut, (unsigned int)v4, ".../");
  pszOut[lstrlenA(pszOut) - 1] = v10;
  if ( (unsigned int)v4 <= v13 + 4 )
  {
    v18 = v4 - 7;
    if ( v18 > 0 && (unsigned int)IsTrailByte(FileNameA, &FileNameA[v18]) )
      --v18;
    StringCchCopyA(pszOut + 4, v18, FileNameA);
    FileNameA = "...";
  }
  StringCchCatA(pszOut, v7, FileNameA);
  return 1;
}

```

## disassembly

```asm
0x1800189e0  push    rbx
0x1800189e2  push    rbp
0x1800189e3  push    rsi
0x1800189e4  push    rdi
0x1800189e5  push    r12
0x1800189e7  push    r13
0x1800189e9  push    r14
0x1800189eb  push    r15
0x1800189ed  sub     rsp, 28h
0x1800189f1  mov     esi, r8d
0x1800189f4  mov     rbx, rdx
0x1800189f7  mov     rdi, rcx
0x1800189fa  test    rdx, rdx
0x1800189fd  jz      loc_180018BAC
0x180018a03  test    rcx, rcx
0x180018a06  jz      loc_180018BAC
0x180018a0c  test    r8d, r8d
0x180018a0f  jz      loc_180018BAC
0x180018a15  mov     r8d, esi; Size
0x180018a18  xor     edx, edx; Val
0x180018a1a  mov     r15d, esi
0x180018a1d  call    memset_0
0x180018a22  mov     rcx, rbx; lpString
0x180018a25  call    cs:__imp_lstrlenA
0x180018a2b  mov     r14d, 1
0x180018a31  add     eax, r14d
0x180018a34  cmp     eax, esi
0x180018a36  jnb     short loc_180018A4D
0x180018a38  mov     r8, rbx; pszSrc
0x180018a3b  mov     edx, esi; cchDest
0x180018a3d  mov     rcx, rdi; pszDest
0x180018a40  call    StringCchCopyA
0x180018a45  mov     eax, r14d
0x180018a48  jmp     loc_180018BAE
0x180018a4d  mov     al, [rbx]
0x180018a4f  mov     r12b, 5Ch ; '\'
0x180018a52  test    al, al
0x180018a54  jz      short loc_180018A73
0x180018a56  mov     rcx, rbx; lpsz
0x180018a59  cmp     al, 2Fh ; '/'
0x180018a5b  jz      short loc_180018A61
0x180018a5d  cmp     al, 5Ch ; '\'
0x180018a5f  jnz     short loc_180018A64
0x180018a61  mov     r12b, al
0x180018a64  call    cs:__imp_CharNextA
0x180018a6a  mov     rcx, rax
0x180018a6d  mov     al, [rax]
0x180018a6f  test    al, al
0x180018a71  jnz     short loc_180018A59
0x180018a73  mov     rcx, rbx; pszPath
0x180018a76  call    cs:__imp_PathFindFileNameA
0x180018a7c  mov     rcx, rax; lpString
0x180018a7f  mov     rbp, rax
0x180018a82  call    cs:__imp_lstrlenA
0x180018a88  mov     r13d, eax
0x180018a8b  cmp     rbp, rbx
0x180018a8e  jnz     short loc_180018AD2
0x180018a90  cmp     esi, 3
0x180018a93  jbe     short loc_180018AD2
0x180018a95  lea     edx, [rsi-3]; cchDest
0x180018a98  mov     r8, rbx; pszSrc
0x180018a9b  mov     rcx, rdi; pszDest
0x180018a9e  call    StringCchCopyA
0x180018aa3  lea     rdx, [rbx-4]
0x180018aa7  mov     rcx, rbx; char *
0x180018aaa  add     rdx, r15; char *
0x180018aad  call    ?IsTrailByte@@YAHPEBD0@Z; IsTrailByte(char const *,char const *)
0x180018ab2  test    eax, eax
0x180018ab4  jz      short loc_180018ABB
0x180018ab6  mov     byte ptr [rsi+rdi-5], 0
0x180018abb  lea     r8, asc_18003D9EC; "..."
0x180018ac2  mov     rdx, r15; unsigned __int64
0x180018ac5  mov     rcx, rdi; char *
0x180018ac8  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x180018acd  jmp     loc_180018A45
0x180018ad2  cmp     esi, 7
0x180018ad5  jnb     short loc_180018B04
0x180018ad7  xor     r8d, r8d
0x180018ada  sub     esi, r14d
0x180018add  jz      loc_180018A45
0x180018ae3  cmp     r8d, 3
0x180018ae7  movzx   eax, r12b
0x180018aeb  mov     ecx, 2Eh ; '.'
0x180018af0  cmovz   ecx, eax
0x180018af3  mov     [r8+rdi], cl
0x180018af7  add     r8d, r14d
0x180018afa  cmp     r8d, esi
0x180018afd  jb      short loc_180018AE3
0x180018aff  jmp     loc_180018A45
0x180018b04  xor     r14d, r14d
0x180018b07  mov     eax, esi
0x180018b09  sub     eax, r13d
0x180018b0c  add     eax, 0FFFFFFFCh
0x180018b0f  cmovns  r14d, eax
0x180018b13  test    r14d, r14d
0x180018b16  jle     short loc_180018B2D
0x180018b18  movsxd  rdx, r14d
0x180018b1b  mov     rcx, rbx; char *
0x180018b1e  add     rdx, rbx; char *
0x180018b21  call    ?IsTrailByte@@YAHPEBD0@Z; IsTrailByte(char const *,char const *)
0x180018b26  test    eax, eax
0x180018b28  jz      short loc_180018B2D
0x180018b2a  dec     r14d
0x180018b2d  movsxd  rdx, r14d; cchDest
0x180018b30  mov     r8, rbx; pszSrc
0x180018b33  mov     rcx, rdi; pszDest
0x180018b36  call    StringCchCopyA
0x180018b3b  lea     r8, asc_18003D9F0; ".../"
0x180018b42  mov     rdx, r15; unsigned __int64
0x180018b45  mov     rcx, rdi; char *
0x180018b48  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x180018b4d  mov     rcx, rdi; lpString
0x180018b50  call    cs:__imp_lstrlenA
0x180018b56  movsxd  rcx, eax
0x180018b59  lea     eax, [r13+4]
0x180018b5d  mov     [rcx+rdi-1], r12b
0x180018b62  cmp     esi, eax
0x180018b64  ja      short loc_180018B97
0x180018b66  add     esi, 0FFFFFFF9h
0x180018b69  test    esi, esi
0x180018b6b  jle     short loc_180018B81
0x180018b6d  movsxd  rdx, esi
0x180018b70  mov     rcx, rbp; char *
0x180018b73  add     rdx, rbp; char *
0x180018b76  call    ?IsTrailByte@@YAHPEBD0@Z; IsTrailByte(char const *,char const *)
0x180018b7b  test    eax, eax
0x180018b7d  jz      short loc_180018B81
0x180018b7f  dec     esi
0x180018b81  movsxd  rdx, esi; cchDest
0x180018b84  lea     rcx, [rdi+4]; pszDest
0x180018b88  mov     r8, rbp; pszSrc
0x180018b8b  call    StringCchCopyA
0x180018b90  lea     rbp, asc_18003D9EC; "..."
0x180018b97  mov     r8, rbp; char *
0x180018b9a  mov     rdx, r15; unsigned __int64
0x180018b9d  mov     rcx, rdi; char *
0x180018ba0  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x180018ba5  mov     eax, 1
0x180018baa  jmp     short loc_180018BAE
0x180018bac  xor     eax, eax
0x180018bae  add     rsp, 28h
0x180018bb2  pop     r15
0x180018bb4  pop     r14
0x180018bb6  pop     r13
0x180018bb8  pop     r12
0x180018bba  pop     rdi
0x180018bbb  pop     rsi
0x180018bbc  pop     rbp
0x180018bbd  pop     rbx
0x180018bbe  retn
```
