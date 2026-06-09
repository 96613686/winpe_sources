# CSoftDist::Logo3DownloadNext(void)

- ea: `0x1800c2bdc`
- end: `0x1800c2eb9`
- name: `?Logo3DownloadNext@CSoftDist@@QEAAJXZ`
- size: `733`
- prototype: `__int64 __fastcall(CSoftDist *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800d5860`

## callees

- `0x18001db50`
- `0x18002fee0`
- `0x18004d7f0`
- `0x18007bcc8`
- `0x1800c2964`
- `0x1800c2bdc`
- `0x1800d009c`
- `0x180128660`
- `0x180128720`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionA` at `0x1800c2dae`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionA` at `0x1800c2dae`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpW` at `0x1800c2d2a`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpW` at `0x1800c2d4f`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpW` at `0x1800c2d2a`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpW` at `0x1800c2d4f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800c2cd8`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800c2cd8`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileA` at `0x1800c2de9`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileA` at `0x1800c2de9`
- `WININET!CommitUrlCacheEntryA` at `0x1800c2e1e`
- `WININET!CommitUrlCacheEntryA` at `0x1800c2e1e`
- `WININET!CreateUrlCacheEntryA` at `0x1800c2dcf`
- `WININET!CreateUrlCacheEntryA` at `0x1800c2dcf`
- `WININET!GetUrlCacheEntryInfoA` at `0x1800c2c76`
- `WININET!GetUrlCacheEntryInfoA` at `0x1800c2d98`
- `WININET!GetUrlCacheEntryInfoA` at `0x1800c2c76`
- `WININET!GetUrlCacheEntryInfoA` at `0x1800c2d98`

## pseudocode

```c
__int64 __fastcall CSoftDist::Logo3DownloadNext(CSoftDist *this)
{
  __int64 v1; // rax
  CHAR *v3; // rdi
  LPCWCH *v4; // r15
  CHAR *v5; // r14
  int v6; // eax
  CHAR *lpszOriginalUrl; // r12
  unsigned int v8; // ebx
  __int64 v9; // rax
  size_t v10; // rbx
  char *v11; // rax
  _QWORD *v12; // rsi
  int v13; // r13d
  __int64 v14; // rdi
  const CHAR *lpszFileExtension; // rsi
  unsigned __int16 **v16; // rsi
  _QWORD *v17; // r8
  __int64 v18; // rdx
  _QWORD *v19; // r9
  DWORD cbCacheEntryInfo; // [rsp+50h] [rbp-B0h] BYREF
  LPCSTR lpszUrlName; // [rsp+58h] [rbp-A8h] BYREF
  LPCSTR pszPath; // [rsp+60h] [rbp-A0h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+68h] [rbp-98h] BYREF
  LPCWCH lpWideCharStr; // [rsp+70h] [rbp-90h] BYREF
  _QWORD *v26; // [rsp+78h] [rbp-88h]
  CSoftDist *v27; // [rsp+80h] [rbp-80h]
  CHAR szFileName[272]; // [rsp+90h] [rbp-70h] BYREF
  _INTERNET_CACHE_ENTRY_INFOA CacheEntryInfo; // [rsp+1A0h] [rbp+A0h] BYREF

  v1 = *((_QWORD *)this + 17);
  v27 = this;
  SystemTimeAsFileTime = 0;
  cbCacheEntryInfo = 0;
  v3 = 0;
  v4 = *(LPCWCH **)(v1 + 16);
  v5 = 0;
  lpWideCharStr = 0;
  lpszUrlName = 0;
  pszPath = 0;
  v6 = Unicode2Ansi(*v4, (CHAR **)&lpszUrlName);
  lpszOriginalUrl = (CHAR *)lpszUrlName;
  v8 = v6;
  if ( v6 >= 0 )
  {
    cbCacheEntryInfo = 4096;
    if ( GetUrlCacheEntryInfoA(lpszUrlName, &CacheEntryInfo, &cbCacheEntryInfo) )
    {
      v9 = -1;
      do
        ++v9;
      while ( CacheEntryInfo.lpszLocalFileName[v9] );
      v10 = (unsigned int)(v9 + 1);
      v11 = (char *)operator new(v10);
      v5 = v11;
      if ( v11 )
      {
        StringCchCopyA(v11, v10, CacheEntryInfo.lpszLocalFileName);
        GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
        v12 = (_QWORD *)*((_QWORD *)this + 11);
        v8 = 1;
        lpszUrlName = 0;
        v13 = 1;
        while ( v12 )
        {
          v26 = (_QWORD *)*v12;
          v14 = v12[2];
          if ( (*(_BYTE *)(v14 + 24) & 2) != 0 )
          {
            if ( (int)Unicode2Ansi(*(LPCWCH *)v14, (CHAR **)&pszPath) < 0 )
            {
              v3 = (CHAR *)pszPath;
              v8 = -2147467259;
              goto LABEL_27;
            }
            if ( (LPCWCH *)v14 == v4 || StrCmpW(*(PCWSTR *)(v14 + 16), v4[2]) )
              v13 = 0;
          }
          v12 = v26;
          if ( (LPCWCH *)v14 != v4 && !StrCmpW(v4[2], *(PCWSTR *)(v14 + 16)) )
            *(_DWORD *)(v14 + 24) |= 1u;
        }
        v3 = (CHAR *)pszPath;
        if ( v13 )
        {
          cbCacheEntryInfo = 4096;
          if ( !GetUrlCacheEntryInfoA(pszPath, &CacheEntryInfo, &cbCacheEntryInfo) )
          {
            lpszFileExtension = PathFindExtensionA(v3) + 1;
            if ( CreateUrlCacheEntryA(v3, 0, lpszFileExtension, szFileName, 0) )
            {
              CopyFileA(v5, szFileName, 0);
              CommitUrlCacheEntryA(
                v3,
                szFileName,
                (FILETIME)lpszUrlName,
                SystemTimeAsFileTime,
                1u,
                0,
                0,
                lpszFileExtension,
                lpszOriginalUrl);
            }
          }
        }
        v16 = (unsigned __int16 **)v27;
        v17 = (_QWORD *)*((_QWORD *)v27 + 11);
        while ( v17 )
        {
          v18 = v17[2];
          v19 = v17;
          v17 = (_QWORD *)*v17;
          if ( (*(_BYTE *)(v18 + 24) & 1) == 0 )
          {
            *((_QWORD *)v27 + 17) = v19;
            *(_DWORD *)(v18 + 24) |= 1u;
            CDLDupWStr((unsigned __int16 **)&lpWideCharStr, *(unsigned __int16 **)v18);
            v8 = CSoftDist::Logo3Download(v16, lpWideCharStr);
            break;
          }
        }
      }
      else
      {
        v8 = -2147024882;
      }
    }
    else
    {
      v8 = -2147467259;
    }
  }
LABEL_27:
  if ( lpszOriginalUrl )
    operator delete(lpszOriginalUrl);
  if ( v5 )
    operator delete(v5);
  if ( v3 )
    operator delete(v3);
  return v8;
}

```

## disassembly

```asm
0x1800c2bdc  push    rbp
0x1800c2bde  push    rbx
0x1800c2bdf  push    rsi
0x1800c2be0  push    rdi
0x1800c2be1  push    r12
0x1800c2be3  push    r13
0x1800c2be5  push    r14
0x1800c2be7  push    r15
0x1800c2be9  lea     rbp, [rsp-10B8h]
0x1800c2bf1  mov     eax, 11B8h
0x1800c2bf6  call    _alloca_probe
0x1800c2bfb  sub     rsp, rax
0x1800c2bfe  mov     rax, cs:__security_cookie
0x1800c2c05  xor     rax, rsp
0x1800c2c08  mov     [rbp+10F0h+var_50], rax
0x1800c2c0f  mov     rax, [rcx+88h]
0x1800c2c16  lea     rdx, [rsp+11F0h+lpszUrlName]
0x1800c2c1b  xor     r13d, r13d
0x1800c2c1e  mov     [rbp+10F0h+var_1170], rcx
0x1800c2c22  mov     qword ptr [rsp+11F0h+SystemTimeAsFileTime.dwLowDateTime], r13
0x1800c2c27  mov     rsi, rcx
0x1800c2c2a  mov     [rsp+11F0h+cbCacheEntryInfo], r13d
0x1800c2c2f  mov     edi, r13d
0x1800c2c32  mov     r15, [rax+10h]
0x1800c2c36  mov     r14d, r13d
0x1800c2c39  mov     [rsp+11F0h+lpWideCharStr], r13
0x1800c2c3e  mov     [rsp+11F0h+lpszUrlName], r13
0x1800c2c43  mov     [rsp+11F0h+pszPath], r13
0x1800c2c48  mov     rcx, [r15]; lpWideCharStr
0x1800c2c4b  call    Unicode2Ansi
0x1800c2c50  mov     r12, [rsp+11F0h+lpszUrlName]
0x1800c2c55  mov     ebx, eax
0x1800c2c57  test    eax, eax
0x1800c2c59  js      loc_1800C2E6C
0x1800c2c5f  lea     r8, [rsp+11F0h+cbCacheEntryInfo]; lpcbCacheEntryInfo
0x1800c2c64  mov     [rsp+11F0h+cbCacheEntryInfo], 1000h
0x1800c2c6c  lea     rdx, [rbp+10F0h+CacheEntryInfo]; lpCacheEntryInfo
0x1800c2c73  mov     rcx, r12; lpszUrlName
0x1800c2c76  call    cs:__imp_GetUrlCacheEntryInfoA
0x1800c2c7d  nop     dword ptr [rax+rax+00h]
0x1800c2c82  test    eax, eax
0x1800c2c84  jnz     short loc_1800C2C90
0x1800c2c86  mov     ebx, 80004005h
0x1800c2c8b  jmp     loc_1800C2E6C
0x1800c2c90  mov     rcx, [rbp+10F0h+CacheEntryInfo.lpszLocalFileName]
0x1800c2c97  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800c2c9b  inc     rax
0x1800c2c9e  cmp     [rcx+rax], r13b
0x1800c2ca2  jnz     short loc_1800C2C9B
0x1800c2ca4  inc     eax
0x1800c2ca6  mov     ecx, eax; Size
0x1800c2ca8  mov     ebx, eax
0x1800c2caa  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800c2caf  mov     r14, rax
0x1800c2cb2  test    rax, rax
0x1800c2cb5  jnz     short loc_1800C2CC1
0x1800c2cb7  mov     ebx, 8007000Eh
0x1800c2cbc  jmp     loc_1800C2E6C
0x1800c2cc1  mov     r8, [rbp+10F0h+CacheEntryInfo.lpszLocalFileName]; char *
0x1800c2cc8  mov     rdx, rbx; unsigned __int64
0x1800c2ccb  mov     rcx, r14; char *
0x1800c2cce  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x1800c2cd3  lea     rcx, [rsp+11F0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800c2cd8  call    cs:__imp_GetSystemTimeAsFileTime
0x1800c2cdf  nop     dword ptr [rax+rax+00h]
0x1800c2ce4  mov     rsi, [rsi+58h]
0x1800c2ce8  mov     ebx, 1
0x1800c2ced  mov     [rsp+11F0h+lpszUrlName], r13
0x1800c2cf2  mov     r13d, ebx
0x1800c2cf5  test    rsi, rsi
0x1800c2cf8  jz      short loc_1800C2D73
0x1800c2cfa  mov     rdi, [rsi]
0x1800c2cfd  mov     [rsp+11F0h+var_1178], rdi
0x1800c2d02  mov     rdi, [rsi+10h]
0x1800c2d06  test    byte ptr [rdi+18h], 2
0x1800c2d0a  jz      short loc_1800C2D3D
0x1800c2d0c  mov     rcx, [rdi]; lpWideCharStr
0x1800c2d0f  lea     rdx, [rsp+11F0h+pszPath]
0x1800c2d14  call    Unicode2Ansi
0x1800c2d19  test    eax, eax
0x1800c2d1b  js      short loc_1800C2D64
0x1800c2d1d  cmp     rdi, r15
0x1800c2d20  jz      short loc_1800C2D3A
0x1800c2d22  mov     rdx, [r15+10h]; psz2
0x1800c2d26  mov     rcx, [rdi+10h]; psz1
0x1800c2d2a  call    cs:__imp_StrCmpW
0x1800c2d31  nop     dword ptr [rax+rax+00h]
0x1800c2d36  test    eax, eax
0x1800c2d38  jz      short loc_1800C2D3D
0x1800c2d3a  xor     r13d, r13d
0x1800c2d3d  mov     rsi, [rsp+11F0h+var_1178]
0x1800c2d42  cmp     rdi, r15
0x1800c2d45  jz      short loc_1800C2CF5
0x1800c2d47  mov     rdx, [rdi+10h]; psz2
0x1800c2d4b  mov     rcx, [r15+10h]; psz1
0x1800c2d4f  call    cs:__imp_StrCmpW
0x1800c2d56  nop     dword ptr [rax+rax+00h]
0x1800c2d5b  test    eax, eax
0x1800c2d5d  jnz     short loc_1800C2CF5
0x1800c2d5f  or      [rdi+18h], ebx
0x1800c2d62  jmp     short loc_1800C2CF5
0x1800c2d64  mov     rdi, [rsp+11F0h+pszPath]
0x1800c2d69  mov     ebx, 80004005h
0x1800c2d6e  jmp     loc_1800C2E6C
0x1800c2d73  mov     rdi, [rsp+11F0h+pszPath]
0x1800c2d78  test    r13d, r13d
0x1800c2d7b  jz      loc_1800C2E2A
0x1800c2d81  lea     r8, [rsp+11F0h+cbCacheEntryInfo]; lpcbCacheEntryInfo
0x1800c2d86  mov     [rsp+11F0h+cbCacheEntryInfo], 1000h
0x1800c2d8e  lea     rdx, [rbp+10F0h+CacheEntryInfo]; lpCacheEntryInfo
0x1800c2d95  mov     rcx, rdi; lpszUrlName
0x1800c2d98  call    cs:__imp_GetUrlCacheEntryInfoA
0x1800c2d9f  nop     dword ptr [rax+rax+00h]
0x1800c2da4  xor     r13d, r13d
0x1800c2da7  test    eax, eax
0x1800c2da9  jnz     short loc_1800C2E2A
0x1800c2dab  mov     rcx, rdi; pszPath
0x1800c2dae  call    cs:__imp_PathFindExtensionA
0x1800c2db5  nop     dword ptr [rax+rax+00h]
0x1800c2dba  lea     r9, [rbp+10F0h+szFileName]; lpszFileName
0x1800c2dbe  mov     [rsp+11F0h+dwReserved], r13d; dwReserved
0x1800c2dc3  xor     edx, edx; dwExpectedFileSize
0x1800c2dc5  mov     rcx, rdi; lpszUrlName
0x1800c2dc8  lea     rsi, [rax+1]
0x1800c2dcc  mov     r8, rsi; lpszFileExtension
0x1800c2dcf  call    cs:__imp_CreateUrlCacheEntryA
0x1800c2dd6  nop     dword ptr [rax+rax+00h]
0x1800c2ddb  test    eax, eax
0x1800c2ddd  jz      short loc_1800C2E2A
0x1800c2ddf  xor     r8d, r8d; bFailIfExists
0x1800c2de2  lea     rdx, [rbp+10F0h+szFileName]; lpNewFileName
0x1800c2de6  mov     rcx, r14; lpExistingFileName
0x1800c2de9  call    cs:__imp_CopyFileA
0x1800c2df0  nop     dword ptr [rax+rax+00h]
0x1800c2df5  mov     r9, qword ptr [rsp+11F0h+SystemTimeAsFileTime.dwLowDateTime]; LastModifiedTime
0x1800c2dfa  lea     rdx, [rbp+10F0h+szFileName]; lpszLocalFileName
0x1800c2dfe  mov     r8, [rsp+11F0h+lpszUrlName]; ExpireTime
0x1800c2e03  mov     rcx, rdi; lpszUrlName
0x1800c2e06  mov     [rsp+11F0h+lpszOriginalUrl], r12; lpszOriginalUrl
0x1800c2e0b  mov     [rsp+11F0h+lpszFileExtension], rsi; lpszFileExtension
0x1800c2e10  mov     [rsp+11F0h+cchHeaderInfo], r13d; cchHeaderInfo
0x1800c2e15  mov     [rsp+11F0h+lpHeaderInfo], r13; lpHeaderInfo
0x1800c2e1a  mov     [rsp+11F0h+dwReserved], ebx; CacheEntryType
0x1800c2e1e  call    cs:__imp_CommitUrlCacheEntryA
0x1800c2e25  nop     dword ptr [rax+rax+00h]
0x1800c2e2a  mov     rsi, [rbp+10F0h+var_1170]
0x1800c2e2e  mov     r8, [rsi+58h]
0x1800c2e32  test    r8, r8
0x1800c2e35  jz      short loc_1800C2E6C
0x1800c2e37  mov     rdx, [r8+10h]
0x1800c2e3b  mov     r9, r8
0x1800c2e3e  mov     r8, [r8]
0x1800c2e41  test    [rdx+18h], bl
0x1800c2e44  jnz     short loc_1800C2E32
0x1800c2e46  mov     [rsi+88h], r9
0x1800c2e4d  lea     rcx, [rsp+11F0h+lpWideCharStr]
0x1800c2e52  or      [rdx+18h], ebx
0x1800c2e55  mov     rdx, [rdx]
0x1800c2e58  call    CDLDupWStr
0x1800c2e5d  mov     rdx, [rsp+11F0h+lpWideCharStr]; lpWideCharStr
0x1800c2e62  mov     rcx, rsi; this
0x1800c2e65  call    ?Logo3Download@CSoftDist@@QEAAJPEAG@Z; CSoftDist::Logo3Download(ushort *)
0x1800c2e6a  mov     ebx, eax
0x1800c2e6c  test    r12, r12
0x1800c2e6f  jz      short loc_1800C2E79
0x1800c2e71  mov     rcx, r12; void *
0x1800c2e74  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800c2e79  test    r14, r14
0x1800c2e7c  jz      short loc_1800C2E86
0x1800c2e7e  mov     rcx, r14; void *
0x1800c2e81  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800c2e86  test    rdi, rdi
0x1800c2e89  jz      short loc_1800C2E93
0x1800c2e8b  mov     rcx, rdi; void *
0x1800c2e8e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800c2e93  mov     eax, ebx
0x1800c2e95  mov     rcx, [rbp+10F0h+var_50]
0x1800c2e9c  xor     rcx, rsp; StackCookie
0x1800c2e9f  call    __security_check_cookie
0x1800c2ea4  add     rsp, 11B8h
0x1800c2eab  pop     r15
0x1800c2ead  pop     r14
0x1800c2eaf  pop     r13
0x1800c2eb1  pop     r12
0x1800c2eb3  pop     rdi
0x1800c2eb4  pop     rsi
0x1800c2eb5  pop     rbx
0x1800c2eb6  pop     rbp
0x1800c2eb7  retn
```
