# SHGetFileDescriptionA

- ea: `0x18001cbd0`
- end: `0x18001cfe2`
- name: `SHGetFileDescriptionA`
- size: `1042`
- prototype: `__int64 __fastcall(LPCSTR pszPath, STRSAFE_LPCSTR pszSrc, char *, STRSAFE_LPSTR pszDest, __int64)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting`

## callees

- `0x180012550`
- `0x180013066`
- `0x180017344`
- `0x180018bd0`
- `0x18001af68`
- `0x18001bbfc`
- `0x18001be50`
- `0x18001cbd0`
- `0x180021b00`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001cca4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001cca4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001cfb4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001cfb4`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameA` at `0x18001cf45`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameA` at `0x18001cf45`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerA` at `0x18001cc5b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerA` at `0x18001cc5b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerShareA` at `0x18001cc6c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerShareA` at `0x18001cc6c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x18001cf83`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x18001cf83`
- `api-ms-win-core-versionansi-l1-1-0!GetFileVersionInfoExA` at `0x18001cccf`
- `api-ms-win-core-versionansi-l1-1-0!GetFileVersionInfoExA` at `0x18001cccf`
- `api-ms-win-core-versionansi-l1-1-0!VerQueryValueA` at `0x18001cd12`
- `api-ms-win-core-versionansi-l1-1-0!VerQueryValueA` at `0x18001cd3c`
- `api-ms-win-core-versionansi-l1-1-0!VerQueryValueA` at `0x18001cd8b`
- `api-ms-win-core-versionansi-l1-1-0!VerQueryValueA` at `0x18001cdc3`
- `api-ms-win-core-versionansi-l1-1-0!VerQueryValueA` at `0x18001cdfb`
- `api-ms-win-core-versionansi-l1-1-0!VerQueryValueA` at `0x18001cd12`
- `api-ms-win-core-versionansi-l1-1-0!VerQueryValueA` at `0x18001cd3c`
- `api-ms-win-core-versionansi-l1-1-0!VerQueryValueA` at `0x18001cd8b`
- `api-ms-win-core-versionansi-l1-1-0!VerQueryValueA` at `0x18001cdc3`
- `api-ms-win-core-versionansi-l1-1-0!VerQueryValueA` at `0x18001cdfb`
- `api-ms-win-core-versionansi-l1-1-0!GetFileVersionInfoSizeExA` at `0x18001cc8d`
- `api-ms-win-core-versionansi-l1-1-0!GetFileVersionInfoSizeExA` at `0x18001cc8d`
- `SHELL32!SHBindToParent` at `0x18001ce90`
- `SHELL32!SHBindToParent` at `0x18001ce90`
- `SHELL32!SHParseDisplayName` at `0x18001ce62`
- `SHELL32!SHParseDisplayName` at `0x18001ce62`
- `SHELL32!__imp_ILFree` at `0x18001cf1d`
- `SHELL32!__imp_ILFree` at `0x18001cf1d`
- `api-ms-win-shcore-unicodeansi-l1-1-0!SHAnsiToUnicode` at `0x18001ce43`
- `api-ms-win-shcore-unicodeansi-l1-1-0!SHAnsiToUnicode` at `0x18001ce43`

## pseudocode

```c
__int64 __fastcall SHGetFileDescriptionA(
        LPCSTR pszPath,
        STRSAFE_LPCSTR pszSrc,
        char *a3,
        STRSAFE_LPSTR pszDest,
        unsigned int *a5)
{
  __int64 result; // rax
  void *v10; // rdi
  DWORD FileVersionInfoSize; // eax
  DWORD v12; // ebx
  HLOCAL lpData; // rax
  const CHAR *v14; // rcx
  const ITEMIDLIST *v15; // r14
  void *v16; // rbx
  const char *FileNameA; // rax
  unsigned int v18; // eax
  size_t v19; // rdx
  const char *v20; // r8
  LPVOID lpBuffer; // [rsp+30h] [rbp-D0h] BYREF
  void *ppv; // [rsp+38h] [rbp-C8h] BYREF
  LPITEMIDLIST ppidl; // [rsp+40h] [rbp-C0h] BYREF
  IBindCtx *pbc; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID v25; // [rsp+50h] [rbp-B0h] BYREF
  LPCITEMIDLIST ppidlLast; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int puLen; // [rsp+60h] [rbp-A0h] BYREF
  DWORD dwHandle[3]; // [rsp+64h] [rbp-9Ch] BYREF
  STRRET pstr; // [rsp+70h] [rbp-90h] BYREF
  CHAR SubBlock[64]; // [rsp+180h] [rbp+80h] BYREF
  CHAR pszBuf[272]; // [rsp+1C0h] [rbp+C0h] BYREF
  char pszDesta[272]; // [rsp+2D0h] [rbp+1D0h] BYREF
  WCHAR pwszDst[264]; // [rsp+3E0h] [rbp+2E0h] BYREF

  puLen = 0;
  lpBuffer = 0;
  v25 = 0;
  LODWORD(ppv) = 0;
  result = PathFileExistsAndAttributesA(pszPath);
  if ( (_DWORD)result )
  {
    v10 = 0;
    StringCchCopyA(pszDesta, 0x104u, pszPath);
    if ( !PathIsUNCServerA(pszPath) && !PathIsUNCServerShareA(pszPath) )
    {
      dwHandle[0] = 0;
      FileVersionInfoSize = GetFileVersionInfoSizeExA(1u, pszDesta, dwHandle);
      v12 = FileVersionInfoSize;
      if ( FileVersionInfoSize )
      {
        lpData = LocalAlloc(0x40u, FileVersionInfoSize);
        v10 = lpData;
        if ( lpData )
        {
          if ( GetFileVersionInfoExA(3u, pszDesta, dwHandle[0], v12, lpData)
            && (!pszSrc
             || StringCchCopyA(SubBlock, 0x3Cu, pszSrc) < 0
             || !VerQueryValueA(v10, SubBlock, &lpBuffer, &puLen))
            && (!VerQueryValueA(v10, "\\VarFileInfo\\Translation", &v25, &puLen)
             || !puLen
             || (int)StringCchPrintfA(
                       SubBlock,
                       0x3Cu,
                       "\\StringFileInfo\\%04X%04X\\FileDescription",
                       *(unsigned __int16 *)v25,
                       *((unsigned __int16 *)v25 + 1)) < 0
             || !VerQueryValueA(v10, SubBlock, &lpBuffer, &puLen))
            && (StringCchCopyA(SubBlock, 0x3Cu, "\\StringFileInfo\\040904E4\\FileDescription") < 0
             || !VerQueryValueA(v10, SubBlock, &lpBuffer, &puLen))
            && StringCchCopyA(SubBlock, 0x3Cu, "\\StringFileInfo\\04090000\\FileDescription") >= 0 )
          {
            VerQueryValueA(v10, SubBlock, &lpBuffer, &puLen);
          }
        }
      }
    }
    v14 = (const CHAR *)lpBuffer;
    if ( !lpBuffer || !*(_BYTE *)lpBuffer )
    {
      pbc = 0;
      if ( (int)SHCreateSkipBindCtx((struct IUnknown *)lpBuffer, &pbc) >= 0 )
      {
        ppidl = 0;
        SHAnsiToUnicode(pszPath, pwszDst, 260);
        if ( SHParseDisplayName(pwszDst, pbc, &ppidl, 0, 0) >= 0 )
        {
          ppv = 0;
          ppidlLast = 0;
          if ( SHBindToParent(ppidl, &GUID_000214e6_0000_0000_c000_000000000046, &ppv, &ppidlLast) >= 0 )
          {
            v15 = ppidlLast;
            v16 = ppv;
            pszBuf[0] = 0;
            memset_0(&pstr, 0, sizeof(pstr));
            if ( (*(int (__fastcall **)(void *, const ITEMIDLIST *, _QWORD, STRRET *))(*(_QWORD *)v16 + 88LL))(
                   v16,
                   v15,
                   0,
                   &pstr) >= 0
              && StrRetToBufA(&pstr, v15, pszBuf, 0x104u) >= 0 )
            {
              lpBuffer = pszBuf;
            }
            (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
          }
          ILFree(ppidl);
        }
        ((void (__fastcall *)(IBindCtx *))pbc->lpVtbl->Release)(pbc);
      }
      v14 = (const CHAR *)lpBuffer;
    }
    if ( !v14 || !*v14 )
    {
      FileNameA = PathFindFileNameA(pszPath);
      if ( StringCchCopyA(pszBuf, 0x104u, FileNameA) < 0 )
      {
        v14 = (const CHAR *)lpBuffer;
      }
      else
      {
        v14 = pszBuf;
        lpBuffer = pszBuf;
      }
    }
    PrettifyFileDescription(v14, a3);
    v18 = lstrlenA((LPCSTR)lpBuffer) + 1;
    puLen = v18;
    if ( pszDest )
    {
      v19 = *a5;
      v20 = (const char *)lpBuffer;
      if ( (unsigned int)v19 >= v18 )
        v19 = v18;
      *a5 = v19;
      StringCchCopyA(pszDest, v19, v20);
    }
    else
    {
      *a5 = v18;
    }
    LocalFree(v10);
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x18001cbd0  push    rbp
0x18001cbd2  push    rbx
0x18001cbd3  push    rsi
0x18001cbd4  push    rdi
0x18001cbd5  push    r12
0x18001cbd7  push    r13
0x18001cbd9  push    r14
0x18001cbdb  push    r15
0x18001cbdd  lea     rbp, [rsp-508h]
0x18001cbe5  sub     rsp, 608h
0x18001cbec  mov     rax, cs:__security_cookie
0x18001cbf3  xor     rax, rsp
0x18001cbf6  mov     [rbp+540h+var_50], rax
0x18001cbfd  mov     r15, [rbp+540h+arg_20]
0x18001cc04  xor     ebx, ebx
0x18001cc06  mov     r14, rdx
0x18001cc09  mov     [rsp+640h+puLen], ebx
0x18001cc0d  lea     rdx, [rsp+640h+ppv]
0x18001cc12  mov     [rsp+640h+lpBuffer], rbx
0x18001cc17  mov     [rsp+640h+var_5F0], rbx
0x18001cc1c  mov     r12, r9
0x18001cc1f  mov     dword ptr [rsp+640h+ppv], ebx
0x18001cc23  mov     r13, r8
0x18001cc26  mov     rsi, rcx
0x18001cc29  call    PathFileExistsAndAttributesA
0x18001cc2e  test    eax, eax
0x18001cc30  jz      loc_18001CFBF
0x18001cc36  mov     r8, rsi; pszSrc
0x18001cc39  lea     rcx, [rbp+540h+pszDest]; pszDest
0x18001cc40  mov     edx, 104h; cchDest
0x18001cc45  mov     rdi, rbx
0x18001cc48  call    StringCchCopyA
0x18001cc4d  test    byte ptr [rsp+640h+ppv], 10h
0x18001cc52  jnz     loc_18001CE05
0x18001cc58  mov     rcx, rsi; pszPath
0x18001cc5b  call    cs:__imp_PathIsUNCServerA
0x18001cc61  test    eax, eax
0x18001cc63  jnz     loc_18001CE05
0x18001cc69  mov     rcx, rsi; pszPath
0x18001cc6c  call    cs:__imp_PathIsUNCServerShareA
0x18001cc72  test    eax, eax
0x18001cc74  jnz     loc_18001CE05
0x18001cc7a  lea     r8, [rsp+640h+dwHandle]; lpdwHandle
0x18001cc7f  mov     [rsp+640h+dwHandle], ebx
0x18001cc83  lea     rdx, [rbp+540h+pszDest]; lpwstrFilename
0x18001cc8a  lea     ecx, [rax+1]; dwFlags
0x18001cc8d  call    cs:__imp_GetFileVersionInfoSizeExA
0x18001cc93  mov     ebx, eax
0x18001cc95  test    eax, eax
0x18001cc97  jz      loc_18001CE03
0x18001cc9d  mov     edx, ebx; uBytes
0x18001cc9f  mov     ecx, 40h ; '@'; uFlags
0x18001cca4  call    cs:__imp_LocalAlloc
0x18001ccaa  mov     rdi, rax
0x18001ccad  test    rax, rax
0x18001ccb0  jz      loc_18001CE03
0x18001ccb6  mov     r8d, [rsp+640h+dwHandle]; dwHandle
0x18001ccbb  lea     rdx, [rbp+540h+pszDest]; lpwstrFilename
0x18001ccc2  mov     r9d, ebx; dwLen
0x18001ccc5  mov     [rsp+640h+lpData], rax; lpData
0x18001ccca  mov     ecx, 3; dwFlags
0x18001cccf  call    cs:__imp_GetFileVersionInfoExA
0x18001ccd5  xor     ebx, ebx
0x18001ccd7  test    eax, eax
0x18001ccd9  jz      loc_18001CE05
0x18001ccdf  test    r14, r14
0x18001cce2  jz      short loc_18001CD22
0x18001cce4  mov     r8, r14; pszSrc
0x18001cce7  lea     rcx, [rbp+540h+SubBlock]; pszDest
0x18001ccee  lea     r14d, [rbx+3Ch]
0x18001ccf2  mov     edx, r14d; cchDest
0x18001ccf5  call    StringCchCopyA
0x18001ccfa  test    eax, eax
0x18001ccfc  js      short loc_18001CD28
0x18001ccfe  lea     r9, [rsp+640h+puLen]; puLen
0x18001cd03  mov     rcx, rdi; pBlock
0x18001cd06  lea     r8, [rsp+640h+lpBuffer]; lplpBuffer
0x18001cd0b  lea     rdx, [rbp+540h+SubBlock]; lpSubBlock
0x18001cd12  call    cs:__imp_VerQueryValueA
0x18001cd18  test    eax, eax
0x18001cd1a  jnz     loc_18001CE05
0x18001cd20  jmp     short loc_18001CD28
0x18001cd22  mov     r14d, 3Ch ; '<'
0x18001cd28  lea     r9, [rsp+640h+puLen]; puLen
0x18001cd2d  mov     rcx, rdi; pBlock
0x18001cd30  lea     r8, [rsp+640h+var_5F0]; lplpBuffer
0x18001cd35  lea     rdx, aVarfileinfoTra_0; "\\VarFileInfo\\Translation"
0x18001cd3c  call    cs:__imp_VerQueryValueA
0x18001cd42  test    eax, eax
0x18001cd44  jz      short loc_18001CD95
0x18001cd46  cmp     [rsp+640h+puLen], ebx
0x18001cd4a  jz      short loc_18001CD95
0x18001cd4c  mov     rax, [rsp+640h+var_5F0]
0x18001cd51  lea     r8, aStringfileinfo_1; "\\StringFileInfo\\%04X%04X\\FileDescrip"...
0x18001cd58  mov     rdx, r14; unsigned __int64
0x18001cd5b  movzx   ecx, word ptr [rax+2]
0x18001cd5f  movzx   r9d, word ptr [rax]
0x18001cd63  mov     dword ptr [rsp+640h+lpData], ecx
0x18001cd67  lea     rcx, [rbp+540h+SubBlock]; char *
0x18001cd6e  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001cd73  test    eax, eax
0x18001cd75  js      short loc_18001CD95
0x18001cd77  lea     r9, [rsp+640h+puLen]; puLen
0x18001cd7c  mov     rcx, rdi; pBlock
0x18001cd7f  lea     r8, [rsp+640h+lpBuffer]; lplpBuffer
0x18001cd84  lea     rdx, [rbp+540h+SubBlock]; lpSubBlock
0x18001cd8b  call    cs:__imp_VerQueryValueA
0x18001cd91  test    eax, eax
0x18001cd93  jnz     short loc_18001CE05
0x18001cd95  lea     r8, aStringfileinfo_6; "\\StringFileInfo\\040904E4\\FileDescrip"...
0x18001cd9c  mov     rdx, r14; cchDest
0x18001cd9f  lea     rcx, [rbp+540h+SubBlock]; pszDest
0x18001cda6  call    StringCchCopyA
0x18001cdab  test    eax, eax
0x18001cdad  js      short loc_18001CDCD
0x18001cdaf  lea     r9, [rsp+640h+puLen]; puLen
0x18001cdb4  mov     rcx, rdi; pBlock
0x18001cdb7  lea     r8, [rsp+640h+lpBuffer]; lplpBuffer
0x18001cdbc  lea     rdx, [rbp+540h+SubBlock]; lpSubBlock
0x18001cdc3  call    cs:__imp_VerQueryValueA
0x18001cdc9  test    eax, eax
0x18001cdcb  jnz     short loc_18001CE05
0x18001cdcd  lea     r8, aStringfileinfo_2; "\\StringFileInfo\\04090000\\FileDescrip"...
0x18001cdd4  mov     rdx, r14; cchDest
0x18001cdd7  lea     rcx, [rbp+540h+SubBlock]; pszDest
0x18001cdde  call    StringCchCopyA
0x18001cde3  test    eax, eax
0x18001cde5  js      short loc_18001CE05
0x18001cde7  lea     r9, [rsp+640h+puLen]; puLen
0x18001cdec  mov     rcx, rdi; pBlock
0x18001cdef  lea     r8, [rsp+640h+lpBuffer]; lplpBuffer
0x18001cdf4  lea     rdx, [rbp+540h+SubBlock]; lpSubBlock
0x18001cdfb  call    cs:__imp_VerQueryValueA
0x18001ce01  jmp     short loc_18001CE05
0x18001ce03  xor     ebx, ebx
0x18001ce05  mov     rcx, [rsp+640h+lpBuffer]; struct IUnknown *
0x18001ce0a  test    rcx, rcx
0x18001ce0d  jz      short loc_18001CE17
0x18001ce0f  cmp     [rcx], bl
0x18001ce11  jnz     loc_18001CF39
0x18001ce17  lea     rdx, [rsp+640h+pbc]; struct IBindCtx **
0x18001ce1c  mov     [rsp+640h+pbc], rbx
0x18001ce21  call    ?SHCreateSkipBindCtx@@YAJPEAUIUnknown@@PEAPEAUIBindCtx@@@Z; SHCreateSkipBindCtx(IUnknown *,IBindCtx * *)
0x18001ce26  test    eax, eax
0x18001ce28  js      loc_18001CF34
0x18001ce2e  mov     r8d, 104h; cwchBuf
0x18001ce34  mov     [rsp+640h+ppidl], rbx
0x18001ce39  lea     rdx, [rbp+540h+pwszDst]; pwszDst
0x18001ce40  mov     rcx, rsi; pszSrc
0x18001ce43  call    cs:__imp_SHAnsiToUnicode
0x18001ce49  mov     rdx, [rsp+640h+pbc]; pbc
0x18001ce4e  lea     r8, [rsp+640h+ppidl]; ppidl
0x18001ce53  xor     r9d, r9d; sfgaoIn
0x18001ce56  mov     [rsp+640h+lpData], rbx; psfgaoOut
0x18001ce5b  lea     rcx, [rbp+540h+pwszDst]; pszName
0x18001ce62  call    cs:__imp_SHParseDisplayName
0x18001ce68  test    eax, eax
0x18001ce6a  js      loc_18001CF23
0x18001ce70  mov     rcx, [rsp+640h+ppidl]; pidl
0x18001ce75  lea     r9, [rsp+640h+ppidlLast]; ppidlLast
0x18001ce7a  lea     r8, [rsp+640h+ppv]; ppv
0x18001ce7f  mov     [rsp+640h+ppv], rbx
0x18001ce84  lea     rdx, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x18001ce8b  mov     [rsp+640h+ppidlLast], rbx
0x18001ce90  call    cs:__imp_SHBindToParent
0x18001ce96  test    eax, eax
0x18001ce98  js      short loc_18001CF18
0x18001ce9a  mov     r14, [rsp+640h+ppidlLast]
0x18001ce9f  lea     rcx, [rsp+640h+pstr]; void *
0x18001cea4  mov     rbx, [rsp+640h+ppv]
0x18001cea9  xor     edx, edx; Val
0x18001ceab  mov     r8d, 110h; Size
0x18001ceb1  mov     [rbp+540h+pszBuf], 0
0x18001ceb8  call    memset_0
0x18001cebd  mov     rax, [rbx]
0x18001cec0  lea     r9, [rsp+640h+pstr]
0x18001cec5  xor     r8d, r8d
0x18001cec8  mov     rdx, r14
0x18001cecb  mov     rcx, rbx
0x18001cece  mov     rax, [rax+58h]
0x18001ced2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ced7  xor     ebx, ebx
0x18001ced9  test    eax, eax
0x18001cedb  js      short loc_18001CF07
0x18001cedd  mov     r9d, 104h; cchBuf
0x18001cee3  lea     r8, [rbp+540h+pszBuf]; pszBuf
0x18001ceea  mov     rdx, r14; pidl
0x18001ceed  lea     rcx, [rsp+640h+pstr]; pstr
0x18001cef2  call    StrRetToBufA
0x18001cef7  test    eax, eax
0x18001cef9  js      short loc_18001CF07
0x18001cefb  lea     rax, [rbp+540h+pszBuf]
0x18001cf02  mov     [rsp+640h+lpBuffer], rax
0x18001cf07  mov     rcx, [rsp+640h+ppv]
0x18001cf0c  mov     rax, [rcx]
0x18001cf0f  mov     rax, [rax+10h]
0x18001cf13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf18  mov     rcx, [rsp+640h+ppidl]; pidl
0x18001cf1d  call    cs:__imp_ILFree
0x18001cf23  mov     rcx, [rsp+640h+pbc]
0x18001cf28  mov     rax, [rcx]
0x18001cf2b  mov     rax, [rax+10h]
0x18001cf2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf34  mov     rcx, [rsp+640h+lpBuffer]
0x18001cf39  test    rcx, rcx
0x18001cf3c  jz      short loc_18001CF42
0x18001cf3e  cmp     [rcx], bl
0x18001cf40  jnz     short loc_18001CF76
0x18001cf42  mov     rcx, rsi; pszPath
0x18001cf45  call    cs:__imp_PathFindFileNameA
0x18001cf4b  mov     edx, 104h; cchDest
0x18001cf50  lea     rcx, [rbp+540h+pszBuf]; pszDest
0x18001cf57  mov     r8, rax; pszSrc
0x18001cf5a  call    StringCchCopyA
0x18001cf5f  test    eax, eax
0x18001cf61  js      short loc_18001CF71
0x18001cf63  lea     rcx, [rbp+540h+pszBuf]
0x18001cf6a  mov     [rsp+640h+lpBuffer], rcx
0x18001cf6f  jmp     short loc_18001CF76
0x18001cf71  mov     rcx, [rsp+640h+lpBuffer]; pszSource
0x18001cf76  mov     rdx, r13; char *
0x18001cf79  call    ?PrettifyFileDescription@@YAXPEADPEBD@Z; PrettifyFileDescription(char *,char const *)
0x18001cf7e  mov     rcx, [rsp+640h+lpBuffer]; lpString
0x18001cf83  call    cs:__imp_lstrlenA
0x18001cf89  inc     eax
0x18001cf8b  mov     [rsp+640h+puLen], eax
0x18001cf8f  test    r12, r12
0x18001cf92  jnz     short loc_18001CF99
0x18001cf94  mov     [r15], eax
0x18001cf97  jmp     short loc_18001CFB1
0x18001cf99  mov     edx, [r15]
0x18001cf9c  mov     rcx, r12; pszDest
0x18001cf9f  mov     r8, [rsp+640h+lpBuffer]; pszSrc
0x18001cfa4  cmp     edx, eax
0x18001cfa6  cmovnb  edx, eax; cchDest
0x18001cfa9  mov     [r15], edx
0x18001cfac  call    StringCchCopyA
0x18001cfb1  mov     rcx, rdi; hMem
0x18001cfb4  call    cs:__imp_LocalFree
0x18001cfba  mov     eax, 1
0x18001cfbf  mov     rcx, [rbp+540h+var_50]
0x18001cfc6  xor     rcx, rsp; StackCookie
0x18001cfc9  call    __security_check_cookie
0x18001cfce  add     rsp, 608h
0x18001cfd5  pop     r15
0x18001cfd7  pop     r14
0x18001cfd9  pop     r13
0x18001cfdb  pop     r12
0x18001cfdd  pop     rdi
0x18001cfde  pop     rsi
0x18001cfdf  pop     rbx
0x18001cfe0  pop     rbp
0x18001cfe1  retn
```
