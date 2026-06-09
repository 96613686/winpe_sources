# CMapPathToSpecialDirHelper::Init(void)

- ea: `0x180059a0c`
- end: `0x180059cb0`
- name: `?Init@CMapPathToSpecialDirHelper@@QEAAJXZ`
- size: `676`
- prototype: `__int64 __fastcall(CMapPathToSpecialDirHelper *__hidden this)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180059084`
- `0x180059320`
- `0x180059740`

## callees

- `0x18001db50`
- `0x180024ea0`
- `0x18005919c`
- `0x180059a0c`
- `0x180108710`
- `0x1801285fe`
- `0x180128660`

## import_xrefs

- `iertutil!__imp_GetValue` at `0x180059ab8`
- `iertutil!__imp_GetValue` at `0x180059ab8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180059c07`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180059c07`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180059a7a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180059a7a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x180059b8e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x180059be0`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x180059b8e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x180059be0`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrDupW` at `0x180059b76`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrDupW` at `0x180059bc9`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrDupW` at `0x180059b76`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrDupW` at `0x180059bc9`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180059b38`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180059b38`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetFolderPathW` at `0x180059b16`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetFolderPathW` at `0x180059b16`
- `WININET!GetUrlCacheConfigInfoW` at `0x180059c3b`
- `WININET!GetUrlCacheConfigInfoW` at `0x180059c3b`

## pseudocode

```c
__int64 __fastcall CMapPathToSpecialDirHelper::Init(CMapPathToSpecialDirHelper *this)
{
  unsigned int Error; // ebx
  __int64 v4; // rsi
  void *v5; // rax
  const WCHAR *v6; // rax
  CMapPathToSpecialDirHelper *v7; // rcx
  const WCHAR *v8; // rax
  BOOL IsUNCW; // eax
  WCHAR *i; // rcx
  LPWSTR pszPath; // [rsp+20h] [rbp-E0h]
  struct _INTERNET_CACHE_CONFIG_INFOW CacheConfigInfo; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR pszSrch[264]; // [rsp+270h] [rbp+170h] BYREF

  Error = 0;
  if ( !*((_BYTE *)this + 24) )
  {
    EnterCriticalSection(&CMapPathToSpecialDirHelper::s_csPathToSpecialDirHelper);
    if ( *((_BYTE *)this + 24) )
      goto LABEL_14;
    GetValue(SettingStore::IEVALUE_urlmon_SpecialFoldersCacheSize, 1, 1, (char *)this + 20, 4, 0, 0);
    v4 = -1;
    v5 = operator new(saturated_mul(*((unsigned int *)this + 5), 8u));
    *((_QWORD *)this + 4) = v5;
    if ( !v5 )
      goto LABEL_13;
    memset_0(v5, 0, 8LL * *((unsigned int *)this + 5));
    Error = SHGetFolderPathW(0, 32, 0, 0, pszSrch);
    InitOnceExecuteOnce(&stru_18016BB00, InitOnceDeviceFamily, 0, 0);
    if ( byte_18016AF34 )
      goto LABEL_15;
    if ( Error )
      goto LABEL_14;
    if ( !pszSrch[0] )
    {
LABEL_15:
      memset_0(&CacheConfigInfo, 0, sizeof(CacheConfigInfo));
      CacheConfigInfo.dwStructSize = 560;
      if ( GetUrlCacheConfigInfoW(&CacheConfigInfo, 0, 0x40u) && CacheConfigInfo.CachePath[0] )
      {
        do
          ++v4;
        while ( CacheConfigInfo.CachePath[v4] );
        for ( i = (WCHAR *)&CacheConfigInfo.dwNumCachePaths + v4; i >= CacheConfigInfo.CachePath && *i != 92; --i )
          ;
        i[1] = 0;
        StringCchCopyW(pszSrch, 0x104u, CacheConfigInfo.CachePath);
LABEL_9:
        v6 = StrDupW(pszSrch);
        *((_QWORD *)this + 1) = v6;
        if ( !v6 )
          goto LABEL_13;
        *((_BYTE *)this + 25) = PathIsUNCW(v6);
        Error = CMapPathToSpecialDirHelper::ConstructFolderPath(v7, 33, 512, pszSrch, (unsigned __int64)pszPath);
        if ( !Error )
        {
          v8 = StrDupW(pszSrch);
          *(_QWORD *)this = v8;
          if ( v8 )
          {
            IsUNCW = PathIsUNCW(v8);
            *((_BYTE *)this + 24) = 1;
            *((_BYTE *)this + 26) = IsUNCW;
            goto LABEL_14;
          }
LABEL_13:
          Error = -2147024882;
        }
LABEL_14:
        LeaveCriticalSection(&CMapPathToSpecialDirHelper::s_csPathToSpecialDirHelper);
        return Error;
      }
      Error = ResultFromLastError();
    }
    if ( Error )
      goto LABEL_14;
    goto LABEL_9;
  }
  return Error;
}

```

## disassembly

```asm
0x180059a0c  mov     [rsp-8+arg_8], rbx
0x180059a11  mov     [rsp-8+arg_10], rsi
0x180059a16  push    rbp
0x180059a17  push    rdi
0x180059a18  push    r14
0x180059a1a  lea     rbp, [rsp-390h]
0x180059a22  sub     rsp, 490h
0x180059a29  mov     rax, cs:__security_cookie
0x180059a30  xor     rax, rsp
0x180059a33  mov     [rbp+3A0h+var_20], rax
0x180059a3a  xor     r14d, r14d
0x180059a3d  mov     rdi, rcx
0x180059a40  mov     ebx, r14d
0x180059a43  cmp     [rcx+18h], r14b
0x180059a47  jz      short loc_180059A73
0x180059a49  mov     eax, ebx
0x180059a4b  mov     rcx, [rbp+3A0h+var_20]
0x180059a52  xor     rcx, rsp; StackCookie
0x180059a55  call    __security_check_cookie
0x180059a5a  lea     r11, [rsp+4A0h+var_10]
0x180059a62  mov     rbx, [r11+28h]
0x180059a66  mov     rsi, [r11+30h]
0x180059a6a  mov     rsp, r11
0x180059a6d  pop     r14
0x180059a6f  pop     rdi
0x180059a70  pop     rbp
0x180059a71  retn
0x180059a73  lea     rcx, ?s_csPathToSpecialDirHelper@CMapPathToSpecialDirHelper@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180059a7a  call    cs:__imp_EnterCriticalSection
0x180059a81  nop     dword ptr [rax+rax+00h]
0x180059a86  cmp     [rdi+18h], r14b
0x180059a8a  jnz     loc_180059C00
0x180059a90  mov     rcx, cs:?IEVALUE_urlmon_SpecialFoldersCacheSize@SettingStore@@3U?$VALUEID@K@1@B; SettingStore::VALUEID<ulong> const SettingStore::IEVALUE_urlmon_SpecialFoldersCacheSize
0x180059a97  lea     rbx, [rdi+14h]
0x180059a9b  mov     edx, 1
0x180059aa0  mov     [rsp+4A0h+var_470], r14
0x180059aa5  mov     r9, rbx
0x180059aa8  mov     [rsp+4A0h+var_478], r14
0x180059aad  mov     r8d, edx
0x180059ab0  mov     dword ptr [rsp+4A0h+pszPath], 4
0x180059ab8  call    cs:__imp_GetValue
0x180059abf  nop     dword ptr [rax+rax+00h]
0x180059ac4  mov     ecx, [rbx]
0x180059ac6  mov     eax, 8
0x180059acb  mul     rcx
0x180059ace  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180059ad5  cmovb   rax, rsi
0x180059ad9  mov     rcx, rax; Size
0x180059adc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180059ae1  mov     [rdi+20h], rax
0x180059ae5  test    rax, rax
0x180059ae8  jz      loc_180059BFB
0x180059aee  mov     r8d, [rbx]
0x180059af1  xor     edx, edx; Val
0x180059af3  shl     r8, 3; Size
0x180059af7  mov     rcx, rax; void *
0x180059afa  call    memset_0
0x180059aff  lea     rax, [rbp+3A0h+pszSrch]
0x180059b06  xor     r9d, r9d; dwFlags
0x180059b09  xor     r8d, r8d; hToken
0x180059b0c  mov     [rsp+4A0h+pszPath], rax; unsigned __int64
0x180059b11  lea     edx, [rsi+21h]; csidl
0x180059b14  xor     ecx, ecx; hwnd
0x180059b16  call    cs:__imp_SHGetFolderPathW
0x180059b1d  nop     dword ptr [rax+rax+00h]
0x180059b22  xor     r9d, r9d; Context
0x180059b25  lea     rdx, ?InitOnceDeviceFamily@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180059b2c  xor     r8d, r8d; Parameter
0x180059b2f  lea     rcx, stru_18016BB00; InitOnce
0x180059b36  mov     ebx, eax
0x180059b38  call    cs:__imp_InitOnceExecuteOnce
0x180059b3f  nop     dword ptr [rax+rax+00h]
0x180059b44  cmp     cs:byte_18016AF34, r14b
0x180059b4b  jnz     loc_180059C18
0x180059b51  test    ebx, ebx
0x180059b53  jnz     loc_180059C00
0x180059b59  cmp     [rbp+3A0h+pszSrch], r14w
0x180059b61  jz      loc_180059C18
0x180059b67  test    ebx, ebx
0x180059b69  jnz     loc_180059C00
0x180059b6f  lea     rcx, [rbp+3A0h+pszSrch]; pszSrch
0x180059b76  call    cs:__imp_StrDupW
0x180059b7d  nop     dword ptr [rax+rax+00h]
0x180059b82  mov     [rdi+8], rax
0x180059b86  test    rax, rax
0x180059b89  jz      short loc_180059BFB
0x180059b8b  mov     rcx, rax; pszPath
0x180059b8e  call    cs:__imp_PathIsUNCW
0x180059b95  nop     dword ptr [rax+rax+00h]
0x180059b9a  cmp     eax, 1
0x180059b9d  setz    al
0x180059ba0  mov     [rdi+19h], al
0x180059ba3  test    ebx, ebx
0x180059ba5  jnz     short loc_180059C00
0x180059ba7  lea     r9, [rbp+3A0h+pszSrch]; unsigned __int16 *
0x180059bae  mov     r8d, 200h; int
0x180059bb4  lea     edx, [rbx+21h]; int
0x180059bb7  call    ?ConstructFolderPath@CMapPathToSpecialDirHelper@@AEAAJHHPEAG_K@Z; CMapPathToSpecialDirHelper::ConstructFolderPath(int,int,ushort *,unsigned __int64)
0x180059bbc  mov     ebx, eax
0x180059bbe  test    eax, eax
0x180059bc0  jnz     short loc_180059C00
0x180059bc2  lea     rcx, [rbp+3A0h+pszSrch]; pszSrch
0x180059bc9  call    cs:__imp_StrDupW
0x180059bd0  nop     dword ptr [rax+rax+00h]
0x180059bd5  mov     [rdi], rax
0x180059bd8  test    rax, rax
0x180059bdb  jz      short loc_180059BFB
0x180059bdd  mov     rcx, rax; pszPath
0x180059be0  call    cs:__imp_PathIsUNCW
0x180059be7  nop     dword ptr [rax+rax+00h]
0x180059bec  cmp     eax, 1
0x180059bef  mov     byte ptr [rdi+18h], 1
0x180059bf3  setz    al
0x180059bf6  mov     [rdi+1Ah], al
0x180059bf9  jmp     short loc_180059C00
0x180059bfb  mov     ebx, 8007000Eh
0x180059c00  lea     rcx, ?s_csPathToSpecialDirHelper@CMapPathToSpecialDirHelper@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180059c07  call    cs:__imp_LeaveCriticalSection
0x180059c0e  nop     dword ptr [rax+rax+00h]
0x180059c13  jmp     loc_180059A49
0x180059c18  mov     ebx, 230h
0x180059c1d  lea     rcx, [rsp+4A0h+CacheConfigInfo]; void *
0x180059c22  mov     r8d, ebx; Size
0x180059c25  xor     edx, edx; Val
0x180059c27  call    memset_0
0x180059c2c  xor     edx, edx; lpcbCacheConfigInfo
0x180059c2e  mov     [rsp+4A0h+CacheConfigInfo.dwStructSize], ebx
0x180059c32  lea     rcx, [rsp+4A0h+CacheConfigInfo]; lpCacheConfigInfo
0x180059c37  lea     r8d, [rdx+40h]; dwFieldControl
0x180059c3b  call    cs:__imp_GetUrlCacheConfigInfoW
0x180059c42  nop     dword ptr [rax+rax+00h]
0x180059c47  test    eax, eax
0x180059c49  jz      short loc_180059CA4
0x180059c4b  cmp     word ptr [rsp+4A0h+CacheConfigInfo.1Ch], r14w
0x180059c51  jz      short loc_180059CA4
0x180059c53  lea     rax, [rsp+4A0h+CacheConfigInfo.1Ch]
0x180059c58  inc     rsi
0x180059c5b  cmp     [rax+rsi*2], r14w
0x180059c60  jnz     short loc_180059C58
0x180059c62  lea     rcx, [rsp+4A0h+CacheConfigInfo.dwNumCachePaths]
0x180059c67  lea     rcx, [rcx+rsi*2]
0x180059c6b  jmp     short loc_180059C77
0x180059c6d  cmp     word ptr [rcx], 5Ch ; '\'
0x180059c71  jz      short loc_180059C81
0x180059c73  sub     rcx, 2
0x180059c77  lea     rax, [rsp+4A0h+CacheConfigInfo.1Ch]
0x180059c7c  cmp     rcx, rax
0x180059c7f  jnb     short loc_180059C6D
0x180059c81  mov     [rcx+2], r14w
0x180059c86  lea     r8, [rsp+4A0h+CacheConfigInfo.1Ch]; unsigned __int16 *
0x180059c8b  lea     rcx, [rbp+3A0h+pszSrch]; unsigned __int16 *
0x180059c92  mov     edx, 104h; unsigned __int64
0x180059c97  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180059c9c  mov     ebx, r14d
0x180059c9f  jmp     loc_180059B6F
0x180059ca4  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180059ca9  mov     ebx, eax
0x180059cab  jmp     loc_180059B67
```
