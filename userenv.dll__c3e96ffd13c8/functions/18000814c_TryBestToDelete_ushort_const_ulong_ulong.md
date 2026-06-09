# _TryBestToDelete(ushort const *,ulong,ulong)

- ea: `0x18000814c`
- end: `0x1800082c9`
- name: `?_TryBestToDelete@@YAJPEBGKK@Z`
- size: `381`
- prototype: `__int64 __fastcall(WCHAR *lpFileName, DWORD, char)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180007a7c`
- `0x180018ff4`

## callees

- `0x18000814c`
- `0x18000cfe4`
- `0x1800192c0`
- `0x18001992c`
- `0x18001995c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008185`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800081d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000822d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008185`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800081d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000822d`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180008178`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800081aa`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180008178`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800081aa`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800081c7`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000821f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800081c7`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000821f`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1800081bf`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180008217`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1800081bf`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180008217`

## string_xrefs

- `0x18000824f`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`
- `0x18000826f`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`
- `0x1800082a4`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`

## pseudocode

```c
__int64 __fastcall _TryBestToDelete(WCHAR *lpFileName, DWORD a2, char a3)
{
  int v3; // r12d
  DWORD v5; // ebp
  BOOL v7; // r14d
  unsigned int v8; // ebx
  BOOL v9; // eax
  signed int LastError; // eax
  BOOL v11; // eax
  signed int v12; // eax
  int v15; // [rsp+20h] [rbp-48h]
  char *v16; // [rsp+28h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v3 = 0;
  v5 = a2;
  v7 = 1;
  if ( (a2 & 5) != 0 )
  {
    v5 = a2 & 0xFFFFFFFA;
    if ( !SetFileAttributesW(lpFileName, a2 & 0xFFFFFFFA) )
    {
      v7 = 0;
      if ( GetLastError() == 5 && (a3 & 2) != 0 && (int)_TakeOwnerAndAddAccess(lpFileName) >= 0 )
      {
        v3 = 1;
        v7 = SetFileAttributesW(lpFileName, v5);
      }
    }
  }
  v8 = 0;
  if ( (v5 & 0x10) != 0 )
    v9 = RemoveDirectoryW(lpFileName);
  else
    v9 = DeleteFileW(lpFileName);
  if ( v9 )
    return v8;
  LastError = GetLastError();
  v8 = LastError;
  if ( LastError != 5 )
  {
    if ( LastError <= 0 )
      goto LABEL_27;
    goto LABEL_26;
  }
  if ( !v7 || v3 || (a3 & 2) == 0 )
  {
LABEL_26:
    v8 = (unsigned __int16)LastError | 0x80070000;
LABEL_27:
    if ( v8 != -2147024864 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xC91,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\lib\\copydir.cpp",
        (const char *)v8,
        v15);
    return v8;
  }
  if ( (int)_TakeOwnerAndAddAccess(lpFileName) < 0 )
    return (unsigned int)wil::details::in1diag3::Log_Hr(
                           retaddr,
                           (void *)0xC8B,
                           (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\lib\\copydir.cpp",
                           (const char *)0x80070005LL,
                           v15);
  v8 = 0;
  if ( (v5 & 0x10) != 0 )
    v11 = RemoveDirectoryW(lpFileName);
  else
    v11 = DeleteFileW(lpFileName);
  if ( !v11 )
  {
    v12 = GetLastError();
    if ( v12 > 0 )
      v12 = (unsigned __int16)v12 | 0x80070000;
    LODWORD(v16) = v5;
    return (unsigned int)wil::details::in1diag3::Log_HrMsg(
                           retaddr,
                           (void *)0xC86,
                           (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\lib\\copydir.cpp",
                           (const char *)(unsigned int)v12,
                           (int)"dwAttributes= %ul",
                           v16);
  }
  return v8;
}

```

## disassembly

```asm
0x18000814c  push    rbx
0x18000814e  push    rbp
0x18000814f  push    rsi
0x180008150  push    rdi
0x180008151  push    r12
0x180008153  push    r14
0x180008155  push    r15
0x180008157  sub     rsp, 30h
0x18000815b  xor     r12d, r12d
0x18000815e  mov     r15d, r8d
0x180008161  mov     ebp, edx
0x180008163  mov     rdi, rcx
0x180008166  lea     ebx, [r12+1]
0x18000816b  mov     r14d, ebx
0x18000816e  test    dl, 5
0x180008171  jz      short loc_1800081B3
0x180008173  and     ebp, 0FFFFFFFAh
0x180008176  mov     edx, ebp; dwFileAttributes
0x180008178  call    cs:__imp_SetFileAttributesW
0x18000817e  test    eax, eax
0x180008180  jnz     short loc_1800081B3
0x180008182  xor     r14d, r14d
0x180008185  call    cs:__imp_GetLastError
0x18000818b  cmp     eax, 5
0x18000818e  jnz     short loc_1800081B3
0x180008190  test    r15b, 2
0x180008194  jz      short loc_1800081B3
0x180008196  mov     rcx, rdi; pObjectName
0x180008199  call    ?_TakeOwnerAndAddAccess@@YAJPEBG@Z; _TakeOwnerAndAddAccess(ushort const *)
0x18000819e  test    eax, eax
0x1800081a0  js      short loc_1800081B3
0x1800081a2  mov     edx, ebp; dwFileAttributes
0x1800081a4  mov     rcx, rdi; lpFileName
0x1800081a7  mov     r12d, ebx
0x1800081aa  call    cs:__imp_SetFileAttributesW
0x1800081b0  mov     r14d, eax
0x1800081b3  xor     ebx, ebx
0x1800081b5  mov     esi, ebp
0x1800081b7  mov     rcx, rdi; lpFileName
0x1800081ba  and     esi, 10h
0x1800081bd  jz      short loc_1800081C7
0x1800081bf  call    cs:__imp_RemoveDirectoryW
0x1800081c5  jmp     short loc_1800081CD
0x1800081c7  call    cs:__imp_DeleteFileW
0x1800081cd  test    eax, eax
0x1800081cf  jnz     loc_1800082B8
0x1800081d5  call    cs:__imp_GetLastError
0x1800081db  mov     ebx, eax
0x1800081dd  cmp     eax, 5
0x1800081e0  jnz     loc_18000828A
0x1800081e6  test    r14d, r14d
0x1800081e9  jz      loc_18000828E
0x1800081ef  test    r12d, r12d
0x1800081f2  jnz     loc_18000828E
0x1800081f8  test    r15b, 2
0x1800081fc  jz      loc_18000828E
0x180008202  mov     rcx, rdi; pObjectName
0x180008205  call    ?_TakeOwnerAndAddAccess@@YAJPEBG@Z; _TakeOwnerAndAddAccess(ushort const *)
0x18000820a  test    eax, eax
0x18000820c  js      short loc_18000826A
0x18000820e  xor     ebx, ebx
0x180008210  mov     rcx, rdi; lpFileName
0x180008213  test    esi, esi
0x180008215  jz      short loc_18000821F
0x180008217  call    cs:__imp_RemoveDirectoryW
0x18000821d  jmp     short loc_180008225
0x18000821f  call    cs:__imp_DeleteFileW
0x180008225  test    eax, eax
0x180008227  jnz     loc_1800082B8
0x18000822d  call    cs:__imp_GetLastError
0x180008233  test    eax, eax
0x180008235  jle     short loc_18000823F
0x180008237  movzx   eax, ax
0x18000823a  or      eax, 80070000h
0x18000823f  mov     rcx, [rsp+68h]; this
0x180008244  lea     rdx, aDwattributesUl; "dwAttributes= %ul"
0x18000824b  mov     dword ptr [rsp+68h+var_40], ebp; char *
0x18000824f  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x180008256  mov     qword ptr [rsp+68h+var_48], rdx; int
0x18000825b  mov     r9d, eax; char *
0x18000825e  mov     edx, 0C86h; void *
0x180008263  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180008268  jmp     short loc_180008286
0x18000826a  mov     rcx, [rsp+68h]; this
0x18000826f  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x180008276  mov     r9d, 80070005h; char *
0x18000827c  mov     edx, 0C8Bh; void *
0x180008281  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180008286  mov     ebx, eax
0x180008288  jmp     short loc_1800082B8
0x18000828a  test    eax, eax
0x18000828c  jle     short loc_180008297
0x18000828e  movzx   ebx, ax
0x180008291  or      ebx, 80070000h
0x180008297  cmp     ebx, 80070020h
0x18000829d  jz      short loc_1800082B8
0x18000829f  mov     rcx, [rsp+68h]; this
0x1800082a4  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x1800082ab  mov     r9d, ebx; char *
0x1800082ae  mov     edx, 0C91h; void *
0x1800082b3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800082b8  mov     eax, ebx
0x1800082ba  add     rsp, 30h
0x1800082be  pop     r15
0x1800082c0  pop     r14
0x1800082c2  pop     r12
0x1800082c4  pop     rdi
0x1800082c5  pop     rsi
0x1800082c6  pop     rbp
0x1800082c7  pop     rbx
0x1800082c8  retn
```
