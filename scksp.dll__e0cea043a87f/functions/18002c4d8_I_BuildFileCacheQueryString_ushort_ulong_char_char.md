# I_BuildFileCacheQueryString(ushort *,ulong,char *,char *)

- ea: `0x18002c4d8`
- end: `0x18002c674`
- name: `?I_BuildFileCacheQueryString@@YAKPEAGKPEAD1@Z`
- size: `412`
- prototype: `unsigned int __fastcall(unsigned __int16 *, unsigned int, char *, char *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18002d61c`
- `0x18002de34`
- `0x18002e3bc`

## callees

- `0x18000d9d0`
- `0x18002b140`
- `0x18002c4d8`
- `0x18002ccf8`
- `0x18002cda8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c541`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c57f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c5ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c62d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c541`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c57f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c5ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c62d`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002c532`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002c575`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002c5e0`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002c623`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002c532`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002c575`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002c5e0`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002c623`

## string_xrefs

- `0x18002c4f5`: `Cached_GeneralFile`

## pseudocode

```c
__int64 __fastcall I_BuildFileCacheQueryString(unsigned __int16 *a1, __int64 a2, char *a3, char *a4)
{
  unsigned int v7; // eax
  int cchWideChar; // ebx
  WCHAR *v9; // rdi
  DWORD LastError; // ebx
  WCHAR *lpWideCharStr; // rax
  __int64 v12; // rax
  unsigned int v13; // eax
  int v14; // ebx
  unsigned __int64 v15; // rdx
  WCHAR *v16; // rax
  const unsigned __int16 *v17; // rdi

  StringCbPrintfW(a1, 0x104u, L"%s/", L"Cached_GeneralFile");
  if ( a3 )
  {
    v7 = MultiByteToWideChar(0, 0, a3, -1, 0, 0);
    cchWideChar = v7;
    if ( v7 )
    {
      lpWideCharStr = (WCHAR *)MIDL_user_allocate(2LL * v7);
      v9 = lpWideCharStr;
      if ( !lpWideCharStr )
        return 8;
      if ( MultiByteToWideChar(0, 0, a3, -1, lpWideCharStr, cchWideChar) )
        goto LABEL_8;
      LastError = GetLastError();
      CspFreeH(v9);
      v9 = 0;
    }
    else
    {
      v9 = 0;
      LastError = GetLastError();
    }
    if ( LastError )
      return LastError;
LABEL_8:
    v12 = -1;
    do
      ++v12;
    while ( a1[v12] );
    StringCbPrintfW(&a1[v12], 260 - 2 * v12, L"%s/", v9);
    CspFreeH(v9);
  }
  v13 = MultiByteToWideChar(0, 0, a4, -1, 0, 0);
  v14 = v13;
  if ( !v13 )
  {
    LastError = GetLastError();
    goto LABEL_17;
  }
  v16 = (WCHAR *)MIDL_user_allocate(2LL * v13);
  v17 = v16;
  if ( !v16 )
    return 8;
  if ( !MultiByteToWideChar(0, 0, a4, -1, v16, v14) )
  {
    LastError = GetLastError();
    CspFreeH(v17);
LABEL_17:
    v17 = 0;
    if ( LastError )
      return LastError;
    goto LABEL_20;
  }
  LastError = 0;
LABEL_20:
  StringCbCatW(a1, v15, v17);
  if ( v17 )
    CspFreeH(v17);
  return LastError;
}

```

## disassembly

```asm
0x18002c4d8  push    rbx
0x18002c4da  push    rbp
0x18002c4db  push    rsi
0x18002c4dc  push    rdi
0x18002c4dd  push    r12
0x18002c4df  push    r13
0x18002c4e1  push    r14
0x18002c4e3  push    r15
0x18002c4e5  sub     rsp, 38h
0x18002c4e9  mov     r15, r9
0x18002c4ec  mov     rsi, r8
0x18002c4ef  mov     r14d, 104h
0x18002c4f5  lea     r9, aCachedGeneralf; "Cached_GeneralFile"
0x18002c4fc  mov     edx, r14d; unsigned __int64
0x18002c4ff  lea     r8, aS_0; "%s/"
0x18002c506  mov     rbp, rcx
0x18002c509  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002c50e  or      r13, 0FFFFFFFFFFFFFFFFh
0x18002c512  xor     r12d, r12d
0x18002c515  test    rsi, rsi
0x18002c518  jz      loc_18002C5CC
0x18002c51e  mov     [rsp+78h+cchWideChar], r12d; cchWideChar
0x18002c523  mov     r9d, r13d; cbMultiByte
0x18002c526  mov     r8, rsi; lpMultiByteStr
0x18002c529  mov     [rsp+78h+lpWideCharStr], r12; lpWideCharStr
0x18002c52e  xor     edx, edx; dwFlags
0x18002c530  xor     ecx, ecx; CodePage
0x18002c532  call    cs:__imp_MultiByteToWideChar
0x18002c538  mov     ebx, eax
0x18002c53a  test    eax, eax
0x18002c53c  jnz     short loc_18002C54B
0x18002c53e  mov     edi, r12d
0x18002c541  call    cs:__imp_GetLastError
0x18002c547  mov     ebx, eax
0x18002c549  jmp     short loc_18002C592
0x18002c54b  mov     rcx, rbx
0x18002c54e  add     rcx, rcx; size
0x18002c551  call    MIDL_user_allocate
0x18002c556  mov     rdi, rax
0x18002c559  test    rax, rax
0x18002c55c  jz      loc_18002C609
0x18002c562  mov     [rsp+78h+cchWideChar], ebx; cchWideChar
0x18002c566  mov     r9d, r13d; cbMultiByte
0x18002c569  mov     r8, rsi; lpMultiByteStr
0x18002c56c  mov     [rsp+78h+lpWideCharStr], rax; lpWideCharStr
0x18002c571  xor     edx, edx; dwFlags
0x18002c573  xor     ecx, ecx; CodePage
0x18002c575  call    cs:__imp_MultiByteToWideChar
0x18002c57b  test    eax, eax
0x18002c57d  jnz     short loc_18002C59A
0x18002c57f  call    cs:__imp_GetLastError
0x18002c585  mov     rcx, rdi
0x18002c588  mov     ebx, eax
0x18002c58a  call    CspFreeH
0x18002c58f  mov     rdi, r12
0x18002c592  test    ebx, ebx
0x18002c594  jnz     loc_18002C661
0x18002c59a  mov     rax, r13
0x18002c59d  inc     rax
0x18002c5a0  cmp     [rbp+rax*2+0], r12w
0x18002c5a6  jnz     short loc_18002C59D
0x18002c5a8  add     rax, rax
0x18002c5ab  lea     r8, aS_0; "%s/"
0x18002c5b2  sub     r14, rax
0x18002c5b5  mov     r9, rdi
0x18002c5b8  mov     rdx, r14; unsigned __int64
0x18002c5bb  lea     rcx, [rax+rbp]; unsigned __int16 *
0x18002c5bf  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002c5c4  mov     rcx, rdi
0x18002c5c7  call    CspFreeH
0x18002c5cc  mov     [rsp+78h+cchWideChar], r12d; cchWideChar
0x18002c5d1  mov     r9d, r13d; cbMultiByte
0x18002c5d4  mov     r8, r15; lpMultiByteStr
0x18002c5d7  mov     [rsp+78h+lpWideCharStr], r12; lpWideCharStr
0x18002c5dc  xor     edx, edx; dwFlags
0x18002c5de  xor     ecx, ecx; CodePage
0x18002c5e0  call    cs:__imp_MultiByteToWideChar
0x18002c5e6  mov     ebx, eax
0x18002c5e8  test    eax, eax
0x18002c5ea  jnz     short loc_18002C5F6
0x18002c5ec  call    cs:__imp_GetLastError
0x18002c5f2  mov     ebx, eax
0x18002c5f4  jmp     short loc_18002C63D
0x18002c5f6  mov     rcx, rbx
0x18002c5f9  add     rcx, rcx; size
0x18002c5fc  call    MIDL_user_allocate
0x18002c601  mov     rdi, rax
0x18002c604  test    rax, rax
0x18002c607  jnz     short loc_18002C610
0x18002c609  mov     ebx, 8
0x18002c60e  jmp     short loc_18002C661
0x18002c610  mov     [rsp+78h+cchWideChar], ebx; cchWideChar
0x18002c614  mov     r9d, r13d; cbMultiByte
0x18002c617  mov     r8, r15; lpMultiByteStr
0x18002c61a  mov     [rsp+78h+lpWideCharStr], rdi; lpWideCharStr
0x18002c61f  xor     edx, edx; dwFlags
0x18002c621  xor     ecx, ecx; CodePage
0x18002c623  call    cs:__imp_MultiByteToWideChar
0x18002c629  test    eax, eax
0x18002c62b  jnz     short loc_18002C646
0x18002c62d  call    cs:__imp_GetLastError
0x18002c633  mov     rcx, rdi
0x18002c636  mov     ebx, eax
0x18002c638  call    CspFreeH
0x18002c63d  mov     rdi, r12
0x18002c640  test    ebx, ebx
0x18002c642  jnz     short loc_18002C661
0x18002c644  jmp     short loc_18002C649
0x18002c646  mov     ebx, r12d
0x18002c649  mov     r8, rdi; unsigned __int16 *
0x18002c64c  mov     rcx, rbp; unsigned __int16 *
0x18002c64f  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x18002c654  test    rdi, rdi
0x18002c657  jz      short loc_18002C661
0x18002c659  mov     rcx, rdi
0x18002c65c  call    CspFreeH
0x18002c661  mov     eax, ebx
0x18002c663  add     rsp, 38h
0x18002c667  pop     r15
0x18002c669  pop     r14
0x18002c66b  pop     r13
0x18002c66d  pop     r12
0x18002c66f  pop     rdi
0x18002c670  pop     rsi
0x18002c671  pop     rbp
0x18002c672  pop     rbx
0x18002c673  retn
```
