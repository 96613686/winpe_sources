# ApplyDefaultExts_0

- ea: `0x180017d50`
- end: `0x180018000`
- name: `ApplyDefaultExts_0`
- size: `688`
- prototype: `__int64 __fastcall(LPCSTR lpFileName)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180018d28`

## callees

- `0x180012550`
- `0x180013066`
- `0x180017344`
- `0x180017d50`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180017f22`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180017f22`
- `api-ms-win-core-file-l1-1-0!FindFirstFileA` at `0x180017e24`
- `api-ms-win-core-file-l1-1-0!FindFirstFileA` at `0x180017e24`
- `api-ms-win-core-file-l1-1-0!FindNextFileA` at `0x180017f11`
- `api-ms-win-core-file-l1-1-0!FindNextFileA` at `0x180017f11`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameA` at `0x180017dc5`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameA` at `0x180017dc5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiA` at `0x180017e65`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiA` at `0x180017e65`

## pseudocode

```c
__int64 __fastcall ApplyDefaultExts_0(LPCSTR lpFileName, __int64 a2, unsigned int a3, void *a4)
{
  unsigned __int64 v6; // rdi
  const CHAR *v7; // r15
  unsigned int v8; // ebp
  HANDLE FirstFileA; // r12
  __int64 v10; // r14
  unsigned int v11; // esi
  __int64 v12; // rdi
  _OWORD *v13; // rax
  _WIN32_FIND_DATAA *p_FindFileData; // rcx
  __int64 v15; // rdx
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  __int128 v19; // xmm0
  __int128 v20; // xmm1
  __int128 v21; // xmm0
  __int128 v22; // xmm1
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  _OWORD *v26; // rbx
  _OWORD *v27; // rcx
  __int128 v28; // xmm1
  __int128 v29; // xmm0
  __int128 v30; // xmm1
  __int128 v31; // xmm0
  __int128 v32; // xmm1
  __int128 v33; // xmm0
  __int128 v34; // xmm1
  __int128 v35; // xmm1
  __int128 v36; // xmm0
  __int128 v37; // xmm1
  int v39; // [rsp+20h] [rbp-2E8h]
  char *pszDest; // [rsp+30h] [rbp-2D8h]
  size_t cchDest; // [rsp+38h] [rbp-2D0h]
  _BYTE v43[320]; // [rsp+40h] [rbp-2C8h] BYREF
  _WIN32_FIND_DATAA FindFileData; // [rsp+180h] [rbp-188h] BYREF

  if ( a4 )
    memset_0(a4, 0, 0x140u);
  v6 = -1;
  do
    ++v6;
  while ( lpFileName[v6] );
  if ( v6 > 0xFF )
    return 0;
  v7 = &lpFileName[v6];
  pszDest = (char *)&lpFileName[v6];
  v39 = v6 + (_DWORD)lpFileName - (unsigned int)PathFindFileNameA(lpFileName);
  v8 = 7;
  memset_0(v43, 0, sizeof(v43));
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  cchDest = 260 - v6;
  StringCchCopyA((STRSAFE_LPSTR)&lpFileName[v6], 260 - v6, ".*");
  FirstFileA = FindFirstFileA(lpFileName, &FindFileData);
  if ( FirstFileA == (HANDLE)-1LL )
    goto LABEL_24;
  v10 = 2;
  do
  {
    v11 = a3;
    v12 = 0;
    do
    {
      if ( ((v11 & 1) != 0 || (_DWORD)v12 == 6)
        && !lstrcmpiA(&FindFileData.cFileName[v39], (LPCSTR)(&c_aDefExtList)[v12]) )
      {
        break;
      }
      v12 = (unsigned int)(v12 + 1);
      v11 >>= 1;
    }
    while ( (unsigned int)v12 < 7 );
    if ( (unsigned int)v12 < v8 )
    {
      v8 = v12;
      v13 = v43;
      p_FindFileData = &FindFileData;
      v15 = 2;
      do
      {
        v16 = *(_OWORD *)&p_FindFileData->ftLastAccessTime.dwHighDateTime;
        *v13 = *(_OWORD *)&p_FindFileData->dwFileAttributes;
        v17 = *(_OWORD *)&p_FindFileData->nFileSizeLow;
        v13[1] = v16;
        v18 = *(_OWORD *)&p_FindFileData->cFileName[4];
        v13[2] = v17;
        v19 = *(_OWORD *)&p_FindFileData->cFileName[20];
        v13[3] = v18;
        v20 = *(_OWORD *)&p_FindFileData->cFileName[36];
        v13[4] = v19;
        v21 = *(_OWORD *)&p_FindFileData->cFileName[52];
        v13[5] = v20;
        v22 = *(_OWORD *)&p_FindFileData->cFileName[68];
        p_FindFileData = (_WIN32_FIND_DATAA *)((char *)p_FindFileData + 128);
        v13[6] = v21;
        v13[7] = v22;
        v13 += 8;
        --v15;
      }
      while ( v15 );
      v23 = *(_OWORD *)&p_FindFileData->ftLastAccessTime.dwHighDateTime;
      *v13 = *(_OWORD *)&p_FindFileData->dwFileAttributes;
      v24 = *(_OWORD *)&p_FindFileData->nFileSizeLow;
      v13[1] = v23;
      v25 = *(_OWORD *)&p_FindFileData->cFileName[4];
      v13[2] = v24;
      v13[3] = v25;
    }
  }
  while ( FindNextFileA(FirstFileA, &FindFileData) );
  FindClose(FirstFileA);
  v26 = a4;
  v7 = pszDest;
  if ( v8 >= 7 )
  {
LABEL_24:
    *v7 = 0;
    return 0;
  }
  StringCchCopyA(pszDest, cchDest, (STRSAFE_LPCSTR)(&c_aDefExtList)[v8]);
  if ( a4 )
  {
    v27 = v43;
    do
    {
      v28 = v27[1];
      *v26 = *v27;
      v29 = v27[2];
      v26[1] = v28;
      v30 = v27[3];
      v26[2] = v29;
      v31 = v27[4];
      v26[3] = v30;
      v32 = v27[5];
      v26[4] = v31;
      v33 = v27[6];
      v26[5] = v32;
      v34 = v27[7];
      v27 += 8;
      v26[6] = v33;
      v26[7] = v34;
      v26 += 8;
      --v10;
    }
    while ( v10 );
    v35 = v27[1];
    *v26 = *v27;
    v36 = v27[2];
    v26[1] = v35;
    v37 = v27[3];
    v26[2] = v36;
    v26[3] = v37;
  }
  return 1;
}

```

## disassembly

```asm
0x180017d50  mov     [rsp+arg_8], rbx
0x180017d55  push    rbp
0x180017d56  push    rsi
0x180017d57  push    rdi
0x180017d58  push    r12
0x180017d5a  push    r13
0x180017d5c  push    r14
0x180017d5e  push    r15
0x180017d60  sub     rsp, 2D0h
0x180017d67  mov     rax, cs:__security_cookie
0x180017d6e  xor     rax, rsp
0x180017d71  mov     [rsp+308h+var_48], rax
0x180017d79  mov     rbx, r9
0x180017d7c  mov     r13d, r8d
0x180017d7f  mov     [rsp+308h+var_2E0], rbx
0x180017d84  mov     rsi, rcx
0x180017d87  mov     r14d, 140h
0x180017d8d  test    r9, r9
0x180017d90  jz      short loc_180017D9F
0x180017d92  mov     r8d, r14d; Size
0x180017d95  xor     edx, edx; Val
0x180017d97  mov     rcx, rbx; void *
0x180017d9a  call    memset_0
0x180017d9f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180017da3  inc     rdi
0x180017da6  cmp     byte ptr [rsi+rdi], 0
0x180017daa  jnz     short loc_180017DA3
0x180017dac  cmp     rdi, 0FFh
0x180017db3  ja      loc_180017FD3
0x180017db9  lea     r15, [rdi+rsi]
0x180017dbd  mov     rcx, rsi; pszPath
0x180017dc0  mov     [rsp+308h+pszDest], r15
0x180017dc5  call    cs:__imp_PathFindFileNameA
0x180017dcb  mov     ecx, r15d
0x180017dce  mov     r8, r14; Size
0x180017dd1  sub     ecx, eax
0x180017dd3  xor     edx, edx; Val
0x180017dd5  mov     [rsp+308h+var_2E8], ecx
0x180017dd9  mov     ebp, 7
0x180017dde  lea     rcx, [rsp+308h+var_2C8]; void *
0x180017de3  call    memset_0
0x180017de8  mov     r8, r14; Size
0x180017deb  lea     rcx, [rsp+308h+FindFileData]; void *
0x180017df3  xor     edx, edx; Val
0x180017df5  call    memset_0
0x180017dfa  mov     eax, 104h
0x180017dff  lea     r8, pszSrc; ".*"
0x180017e06  sub     rax, rdi
0x180017e09  mov     rcx, r15; pszDest
0x180017e0c  mov     rdx, rax; cchDest
0x180017e0f  mov     [rsp+308h+cchDest], rax
0x180017e14  call    StringCchCopyA
0x180017e19  lea     rdx, [rsp+308h+FindFileData]; lpFindFileData
0x180017e21  mov     rcx, rsi; lpFileName
0x180017e24  call    cs:__imp_FindFirstFileA
0x180017e2a  mov     r12, rax
0x180017e2d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180017e31  jz      loc_180017FCF
0x180017e37  mov     ebx, [rsp+308h+var_2E8]
0x180017e3b  lea     r15, ?c_aDefExtList@@3QBQEBDB; char const * const near * const c_aDefExtList
0x180017e42  lea     r14d, [rbp-5]
0x180017e46  mov     esi, r13d
0x180017e49  xor     edi, edi
0x180017e4b  test    sil, 1
0x180017e4f  jnz     short loc_180017E56
0x180017e51  cmp     edi, 6
0x180017e54  jnz     short loc_180017E6F
0x180017e56  mov     rdx, [r15+rdi*8]; lpString2
0x180017e5a  lea     rcx, [rsp+308h+FindFileData.cFileName]
0x180017e62  add     rcx, rbx; lpString1
0x180017e65  call    cs:__imp_lstrcmpiA
0x180017e6b  test    eax, eax
0x180017e6d  jz      short loc_180017E78
0x180017e6f  inc     edi
0x180017e71  shr     esi, 1
0x180017e73  cmp     edi, 7
0x180017e76  jb      short loc_180017E4B
0x180017e78  cmp     edi, ebp
0x180017e7a  jnb     loc_180017F01
0x180017e80  mov     ebp, edi
0x180017e82  lea     rax, [rsp+308h+var_2C8]
0x180017e87  mov     edi, 80h
0x180017e8c  lea     rcx, [rsp+308h+FindFileData]
0x180017e94  mov     rdx, r14
0x180017e97  movups  xmm0, xmmword ptr [rcx]
0x180017e9a  movups  xmm1, xmmword ptr [rcx+10h]
0x180017e9e  movups  xmmword ptr [rax], xmm0
0x180017ea1  movups  xmm0, xmmword ptr [rcx+20h]
0x180017ea5  movups  xmmword ptr [rax+10h], xmm1
0x180017ea9  movups  xmm1, xmmword ptr [rcx+30h]
0x180017ead  movups  xmmword ptr [rax+20h], xmm0
0x180017eb1  movups  xmm0, xmmword ptr [rcx+40h]
0x180017eb5  movups  xmmword ptr [rax+30h], xmm1
0x180017eb9  movups  xmm1, xmmword ptr [rcx+50h]
0x180017ebd  movups  xmmword ptr [rax+40h], xmm0
0x180017ec1  movups  xmm0, xmmword ptr [rcx+60h]
0x180017ec5  movups  xmmword ptr [rax+50h], xmm1
0x180017ec9  movups  xmm1, xmmword ptr [rcx+70h]
0x180017ecd  add     rcx, rdi
0x180017ed0  movups  xmmword ptr [rax+60h], xmm0
0x180017ed4  movups  xmmword ptr [rax+70h], xmm1
0x180017ed8  add     rax, rdi
0x180017edb  sub     rdx, 1
0x180017edf  jnz     short loc_180017E97
0x180017ee1  movups  xmm0, xmmword ptr [rcx]
0x180017ee4  movups  xmm1, xmmword ptr [rcx+10h]
0x180017ee8  movups  xmmword ptr [rax], xmm0
0x180017eeb  movups  xmm0, xmmword ptr [rcx+20h]
0x180017eef  movups  xmmword ptr [rax+10h], xmm1
0x180017ef3  movups  xmm1, xmmword ptr [rcx+30h]
0x180017ef7  movups  xmmword ptr [rax+20h], xmm0
0x180017efb  movups  xmmword ptr [rax+30h], xmm1
0x180017eff  jmp     short loc_180017F06
0x180017f01  mov     edi, 80h
0x180017f06  lea     rdx, [rsp+308h+FindFileData]; lpFindFileData
0x180017f0e  mov     rcx, r12; hFindFile
0x180017f11  call    cs:__imp_FindNextFileA
0x180017f17  test    eax, eax
0x180017f19  jnz     loc_180017E46
0x180017f1f  mov     rcx, r12; hFindFile
0x180017f22  call    cs:__imp_FindClose
0x180017f28  mov     rbx, [rsp+308h+var_2E0]
0x180017f2d  mov     r15, [rsp+308h+pszDest]
0x180017f32  cmp     ebp, 7
0x180017f35  jnb     loc_180017FCF
0x180017f3b  mov     rdx, [rsp+308h+cchDest]; cchDest
0x180017f40  lea     rax, ?c_aDefExtList@@3QBQEBDB; char const * const near * const c_aDefExtList
0x180017f47  mov     r8d, ebp
0x180017f4a  mov     rcx, r15; pszDest
0x180017f4d  mov     r8, [rax+r8*8]; pszSrc
0x180017f51  call    StringCchCopyA
0x180017f56  test    rbx, rbx
0x180017f59  jz      short loc_180017FC8
0x180017f5b  lea     rcx, [rsp+308h+var_2C8]
0x180017f60  movups  xmm0, xmmword ptr [rcx]
0x180017f63  movups  xmm1, xmmword ptr [rcx+10h]
0x180017f67  movups  xmmword ptr [rbx], xmm0
0x180017f6a  movups  xmm0, xmmword ptr [rcx+20h]
0x180017f6e  movups  xmmword ptr [rbx+10h], xmm1
0x180017f72  movups  xmm1, xmmword ptr [rcx+30h]
0x180017f76  movups  xmmword ptr [rbx+20h], xmm0
0x180017f7a  movups  xmm0, xmmword ptr [rcx+40h]
0x180017f7e  movups  xmmword ptr [rbx+30h], xmm1
0x180017f82  movups  xmm1, xmmword ptr [rcx+50h]
0x180017f86  movups  xmmword ptr [rbx+40h], xmm0
0x180017f8a  movups  xmm0, xmmword ptr [rcx+60h]
0x180017f8e  movups  xmmword ptr [rbx+50h], xmm1
0x180017f92  movups  xmm1, xmmword ptr [rcx+70h]
0x180017f96  add     rcx, rdi
0x180017f99  movups  xmmword ptr [rbx+60h], xmm0
0x180017f9d  movups  xmmword ptr [rbx+70h], xmm1
0x180017fa1  add     rbx, rdi
0x180017fa4  sub     r14, 1
0x180017fa8  jnz     short loc_180017F60
0x180017faa  movups  xmm0, xmmword ptr [rcx]
0x180017fad  movups  xmm1, xmmword ptr [rcx+10h]
0x180017fb1  movups  xmmword ptr [rbx], xmm0
0x180017fb4  movups  xmm0, xmmword ptr [rcx+20h]
0x180017fb8  movups  xmmword ptr [rbx+10h], xmm1
0x180017fbc  movups  xmm1, xmmword ptr [rcx+30h]
0x180017fc0  movups  xmmword ptr [rbx+20h], xmm0
0x180017fc4  movups  xmmword ptr [rbx+30h], xmm1
0x180017fc8  mov     eax, 1
0x180017fcd  jmp     short loc_180017FD5
0x180017fcf  mov     byte ptr [r15], 0
0x180017fd3  xor     eax, eax
0x180017fd5  mov     rcx, [rsp+308h+var_48]
0x180017fdd  xor     rcx, rsp; StackCookie
0x180017fe0  call    __security_check_cookie
0x180017fe5  mov     rbx, [rsp+308h+arg_8]
0x180017fed  add     rsp, 2D0h
0x180017ff4  pop     r15
0x180017ff6  pop     r14
0x180017ff8  pop     r13
0x180017ffa  pop     r12
0x180017ffc  pop     rdi
0x180017ffd  pop     rsi
0x180017ffe  pop     rbp
0x180017fff  retn
```
