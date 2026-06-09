# _WriteHitLogging(_MY_LOGGING_INFO *)

- ea: `0x1800fd250`
- end: `0x1800fd469`
- name: `?_WriteHitLogging@@YAHPEAU_MY_LOGGING_INFO@@@Z`
- size: `537`
- prototype: `__int64 __fastcall(struct _MY_LOGGING_INFO *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800fca50`

## callees

- `0x1800fcbec`
- `0x1800fcc94`
- `0x1800fcd88`
- `0x1800fcfa8`
- `0x1800fd250`
- `0x180128660`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800fd2a9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800fd2a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800fd375`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800fd3b9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800fd375`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800fd3b9`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800fd2cf`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800fd2fa`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800fd357`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800fd366`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800fd3c8`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800fd423`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800fd432`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800fd2cf`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800fd2fa`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800fd357`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800fd366`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800fd3c8`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800fd423`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800fd432`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800fd3a8`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800fd3a8`
- `WININET!CommitUrlCacheEntryA` at `0x1800fd412`
- `WININET!CommitUrlCacheEntryA` at `0x1800fd412`
- `WININET!GetUrlCacheEntryInfoExA` at `0x1800fd334`
- `WININET!GetUrlCacheEntryInfoExA` at `0x1800fd334`

## pseudocode

```c
__int64 __fastcall _WriteHitLogging(struct _MY_LOGGING_INFO *a1)
{
  __int64 v2; // rcx
  char *v3; // rbx
  DWORD v4; // ecx
  struct _INTERNET_CACHE_ENTRY_INFOA *CacheEntry; // rax
  struct _INTERNET_CACHE_ENTRY_INFOA *v7; // rdi
  char *v8; // rcx
  void *LogFile; // rsi
  char *LogString; // rax
  char *v11; // r14
  __int64 v12; // r8
  unsigned int v13; // ebp
  DWORD NumberOfBytesWritten; // [rsp+50h] [rbp-148h] BYREF
  HGLOBAL hMem; // [rsp+58h] [rbp-140h] BYREF
  CHAR szLocalFileName[272]; // [rsp+60h] [rbp-138h] BYREF

  NumberOfBytesWritten = 0;
  v2 = *(_QWORD *)a1;
  hMem = 0;
  ConvertToPrefixedURL(*(const char **)(v2 + 8), (char **)&hMem);
  v3 = (char *)hMem;
  if ( !hMem )
  {
    v4 = 8;
LABEL_3:
    SetLastError(v4);
    return 0;
  }
  CacheEntry = QueryCacheEntry((LPCSTR)hMem);
  v7 = CacheEntry;
  v8 = v3;
  if ( !CacheEntry )
  {
LABEL_6:
    GlobalFree(v8);
    v4 = 2;
    goto LABEL_3;
  }
  LogFile = GetLogFile(v3, CacheEntry, szLocalFileName);
  if ( !LogFile )
  {
    GlobalFree(v3);
    v8 = (char *)v7;
    goto LABEL_6;
  }
  *((_DWORD *)a1 + 2) = GetUrlCacheEntryInfoExA(*(LPCSTR *)(*(_QWORD *)a1 + 8LL), 0, 0, 0, 0, 0, 0);
  LogString = GetLogString((const SYSTEMTIME **)a1);
  v11 = LogString;
  if ( !LogString )
  {
    GlobalFree(v3);
    GlobalFree(v7);
    CloseHandle(LogFile);
    return 0;
  }
  v12 = -1;
  do
    ++v12;
  while ( LogString[v12] );
  v13 = WriteFile(LogFile, LogString, v12, &NumberOfBytesWritten, 0);
  CloseHandle(LogFile);
  GlobalFree(v11);
  if ( v13 )
    v13 = CommitUrlCacheEntryA(
            v3,
            szLocalFileName,
            v7->ExpireTime,
            v7->LastModifiedTime,
            v7->CacheEntryType,
            0,
            0,
            0,
            0);
  GlobalFree(v7);
  GlobalFree(v3);
  return v13;
}

```

## disassembly

```asm
0x1800fd250  mov     [rsp+arg_8], rbx
0x1800fd255  mov     [rsp+arg_10], rbp
0x1800fd25a  push    rsi
0x1800fd25b  push    rdi
0x1800fd25c  push    r14
0x1800fd25e  sub     rsp, 180h
0x1800fd265  mov     rax, cs:__security_cookie
0x1800fd26c  xor     rax, rsp
0x1800fd26f  mov     [rsp+198h+var_28], rax
0x1800fd277  mov     r14, rcx
0x1800fd27a  mov     [rsp+198h+NumberOfBytesWritten], 0
0x1800fd282  mov     rcx, [rcx]
0x1800fd285  lea     rdx, [rsp+198h+hMem]; char **
0x1800fd28a  mov     [rsp+198h+hMem], 0
0x1800fd293  mov     rcx, [rcx+8]; char *
0x1800fd297  call    ?ConvertToPrefixedURL@@YAHPEBDPEAPEAD@Z; ConvertToPrefixedURL(char const *,char * *)
0x1800fd29c  mov     rbx, [rsp+198h+hMem]
0x1800fd2a1  test    rbx, rbx
0x1800fd2a4  jnz     short loc_1800FD2BC
0x1800fd2a6  lea     ecx, [rbx+8]; dwErrCode
0x1800fd2a9  call    cs:__imp_SetLastError
0x1800fd2b0  nop     dword ptr [rax+rax+00h]
0x1800fd2b5  xor     eax, eax
0x1800fd2b7  jmp     loc_1800FD440
0x1800fd2bc  mov     rcx, rbx; lpszUrlName
0x1800fd2bf  call    ?QueryCacheEntry@@YAPEAU_INTERNET_CACHE_ENTRY_INFOA@@PEBD@Z; QueryCacheEntry(char const *)
0x1800fd2c4  mov     rdi, rax
0x1800fd2c7  mov     rcx, rbx; char *
0x1800fd2ca  test    rax, rax
0x1800fd2cd  jnz     short loc_1800FD2E2
0x1800fd2cf  call    cs:__imp_GlobalFree
0x1800fd2d6  nop     dword ptr [rax+rax+00h]
0x1800fd2db  mov     ecx, 2
0x1800fd2e0  jmp     short loc_1800FD2A9
0x1800fd2e2  lea     r8, [rsp+198h+szLocalFileName]; char *
0x1800fd2e7  mov     rdx, rdi; struct _INTERNET_CACHE_ENTRY_INFOA *
0x1800fd2ea  call    ?GetLogFile@@YAPEAXPEBDPEAU_INTERNET_CACHE_ENTRY_INFOA@@PEAD@Z; GetLogFile(char const *,_INTERNET_CACHE_ENTRY_INFOA *,char *)
0x1800fd2ef  mov     rsi, rax
0x1800fd2f2  test    rax, rax
0x1800fd2f5  jnz     short loc_1800FD30B
0x1800fd2f7  mov     rcx, rbx; hMem
0x1800fd2fa  call    cs:__imp_GlobalFree
0x1800fd301  nop     dword ptr [rax+rax+00h]
0x1800fd306  mov     rcx, rdi
0x1800fd309  jmp     short loc_1800FD2CF
0x1800fd30b  mov     rcx, [r14]
0x1800fd30e  xor     r9d, r9d; lpszRedirectUrl
0x1800fd311  mov     [rsp+198h+dwFlags], 0; dwFlags
0x1800fd319  xor     r8d, r8d; lpcbCacheEntryInfo
0x1800fd31c  mov     [rsp+198h+lpReserved], 0; lpReserved
0x1800fd325  xor     edx, edx; lpCacheEntryInfo
0x1800fd327  mov     [rsp+198h+lpcbRedirectUrl], 0; lpcbRedirectUrl
0x1800fd330  mov     rcx, [rcx+8]; lpszUrl
0x1800fd334  call    cs:__imp_GetUrlCacheEntryInfoExA
0x1800fd33b  nop     dword ptr [rax+rax+00h]
0x1800fd340  mov     rcx, r14; struct _MY_LOGGING_INFO *
0x1800fd343  mov     [r14+8], eax
0x1800fd347  call    ?GetLogString@@YAPEADPEAU_MY_LOGGING_INFO@@@Z; GetLogString(_MY_LOGGING_INFO *)
0x1800fd34c  mov     r14, rax
0x1800fd34f  test    rax, rax
0x1800fd352  jnz     short loc_1800FD386
0x1800fd354  mov     rcx, rbx; hMem
0x1800fd357  call    cs:__imp_GlobalFree
0x1800fd35e  nop     dword ptr [rax+rax+00h]
0x1800fd363  mov     rcx, rdi; hMem
0x1800fd366  call    cs:__imp_GlobalFree
0x1800fd36d  nop     dword ptr [rax+rax+00h]
0x1800fd372  mov     rcx, rsi; hObject
0x1800fd375  call    cs:__imp_CloseHandle
0x1800fd37c  nop     dword ptr [rax+rax+00h]
0x1800fd381  jmp     loc_1800FD2B5
0x1800fd386  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800fd38a  inc     r8; nNumberOfBytesToWrite
0x1800fd38d  cmp     byte ptr [rax+r8], 0
0x1800fd392  jnz     short loc_1800FD38A
0x1800fd394  lea     r9, [rsp+198h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800fd399  mov     [rsp+198h+lpcbRedirectUrl], 0; lpOverlapped
0x1800fd3a2  mov     rdx, r14; lpBuffer
0x1800fd3a5  mov     rcx, rsi; hFile
0x1800fd3a8  call    cs:__imp_WriteFile
0x1800fd3af  nop     dword ptr [rax+rax+00h]
0x1800fd3b4  mov     rcx, rsi; hObject
0x1800fd3b7  mov     ebp, eax
0x1800fd3b9  call    cs:__imp_CloseHandle
0x1800fd3c0  nop     dword ptr [rax+rax+00h]
0x1800fd3c5  mov     rcx, r14; hMem
0x1800fd3c8  call    cs:__imp_GlobalFree
0x1800fd3cf  nop     dword ptr [rax+rax+00h]
0x1800fd3d4  test    ebp, ebp
0x1800fd3d6  jz      short loc_1800FD420
0x1800fd3d8  mov     eax, [rdi+18h]
0x1800fd3db  lea     rdx, [rsp+198h+szLocalFileName]; lpszLocalFileName
0x1800fd3e0  mov     r9, [rdi+2Ch]; LastModifiedTime
0x1800fd3e4  mov     rcx, rbx; lpszUrlName
0x1800fd3e7  mov     r8, [rdi+34h]; ExpireTime
0x1800fd3eb  mov     [rsp+198h+lpszOriginalUrl], 0; lpszOriginalUrl
0x1800fd3f4  mov     [rsp+198h+lpszFileExtension], 0; lpszFileExtension
0x1800fd3fd  mov     [rsp+198h+dwFlags], 0; cchHeaderInfo
0x1800fd405  mov     [rsp+198h+lpReserved], 0; lpHeaderInfo
0x1800fd40e  mov     dword ptr [rsp+198h+lpcbRedirectUrl], eax; CacheEntryType
0x1800fd412  call    cs:__imp_CommitUrlCacheEntryA
0x1800fd419  nop     dword ptr [rax+rax+00h]
0x1800fd41e  mov     ebp, eax
0x1800fd420  mov     rcx, rdi; hMem
0x1800fd423  call    cs:__imp_GlobalFree
0x1800fd42a  nop     dword ptr [rax+rax+00h]
0x1800fd42f  mov     rcx, rbx; hMem
0x1800fd432  call    cs:__imp_GlobalFree
0x1800fd439  nop     dword ptr [rax+rax+00h]
0x1800fd43e  mov     eax, ebp
0x1800fd440  mov     rcx, [rsp+198h+var_28]
0x1800fd448  xor     rcx, rsp; StackCookie
0x1800fd44b  call    __security_check_cookie
0x1800fd450  lea     r11, [rsp+198h+var_18]
0x1800fd458  mov     rbx, [r11+28h]
0x1800fd45c  mov     rbp, [r11+30h]
0x1800fd460  mov     rsp, r11
0x1800fd463  pop     r14
0x1800fd465  pop     rdi
0x1800fd466  pop     rsi
0x1800fd467  retn
```
