# CacheManager::GetCachePath(ushort *,ulong *)

- ea: `0x1800372f8`
- end: `0x18003759e`
- name: `?GetCachePath@CacheManager@@AEAAJPEAGPEAK@Z`
- size: `678`
- prototype: `int(CacheManager *__hidden this, unsigned __int16 *, unsigned int *)`
- caller_count: `2`
- callee_count: `10`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x180037074`
- `0x1800f7904`

## callees

- `0x18002e5d0`
- `0x18002ee38`
- `0x1800372f8`
- `0x18003a184`
- `0x180060bc0`
- `0x1800a61dc`
- `0x1800af0a4`
- `0x1800b99f0`
- `0x1800ba574`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180037403`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180037403`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037570`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037570`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003743e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003743e`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180037468`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180037468`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18003748a`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18003748a`

## string_xrefs

- `0x18003736d`: `\CacheManager`
- `0x180037393`: `onecoreuap\base\diagnosis\platform\notifications\platform\ui\cachemanager.cpp`
- `0x1800374fe`: `onecoreuap\base\diagnosis\platform\notifications\platform\ui\cachemanager.cpp`
- `0x18003741c`: `ImageCachePath`
- `0x1800374af`: `CacheManager::GetCachePath`
- `0x180037549`: `CacheManager::GetCachePath`
- `0x1800374ba`: `onecoreuap\base\diagnosis\platform\notifications\platform\ui\cachemanager.cpp`
- `0x18003755a`: `onecoreuap\base\diagnosis\platform\notifications\platform\ui\cachemanager.cpp`

## pseudocode

```c
__int64 __fastcall CacheManager::GetCachePath(CacheManager *this, unsigned __int16 *a2, unsigned int *a3)
{
  __int64 v6; // rax
  int v7; // eax
  HRESULT v8; // ebx
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  WCHAR *v11; // rcx
  DWORD v12; // eax
  const WCHAR *v13; // r9
  int v14; // ecx
  int v15; // eax
  unsigned int v16; // ecx
  int v17; // eax
  int phkResult; // [rsp+20h] [rbp-E0h]
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int64 v22; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  hkey = 0;
  pcbData = 260;
  memset_0(SubKey, 0, 0x208u);
  v6 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 24LL))(*((_QWORD *)this + 3));
  v7 = StringCchPrintfW(SubKey, 0x104u, L"%s%s", v6);
  v8 = v7;
  if ( v7 >= 0 )
  {
    if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hkey)
      || RegGetValueW(hkey, 0, L"ImageCachePath", 6u, 0, SubKey, &pcbData) )
    {
      v11 = (WCHAR *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 40LL))(*((_QWORD *)this + 3));
    }
    else
    {
      v11 = SubKey;
    }
    v12 = ExpandEnvironmentStringsW(v11, a2, 0x104u);
    v13 = (const WCHAR *)((char *)this + 56);
    *a3 = v12;
    if ( *((_QWORD *)this + 10) > 7u )
      v13 = *(const WCHAR **)v13;
    v8 = PathCchCombine(a2, 0x104u, a2, v13);
    if ( v8 >= 0 )
    {
      v22 = *a3;
      v15 = StringCchLengthW(a2, 0x104u, &v22);
      v8 = v15;
      if ( v15 >= 0 )
      {
        v17 = v22;
        *a3 = v22;
        if ( (unsigned int)(v17 - 1) > 0x103 )
        {
          v8 = -2147467259;
          WpnDebugInitTrace(
            v16,
            L"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\cachemanager.cpp",
            L"CacheManager::GetCachePath",
            240,
            -2147467259);
        }
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xE9,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\cachemanager.cpp",
          (const char *)(unsigned int)v15,
          phkResult);
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
        {
          v10 = 17;
          goto LABEL_5;
        }
      }
    }
    else if ( (Microsoft_Windows_PushNotifications_PlatformEnableBits & 0x20) != 0 )
    {
      McTemplateU0zzdqz_EventWriteTransfer(
        v14,
        (unsigned int)WPNCORE_EVENT_DEBUG_INIT,
        (unsigned int)L"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\cachemanager.cpp",
        (unsigned int)L"CacheManager::GetCachePath",
        228,
        v8,
        (__int64)&word_180124798);
    }
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xC7,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\cachemanager.cpp",
      (const char *)(unsigned int)v7,
      (int)L"\\CacheManager");
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v10 = 15;
LABEL_5:
      WPP_SF_d(v9[2], v10, WPP_54d166b4b7773830bae608bc87214534_Traceguids, (unsigned int)v8);
    }
  }
  if ( hkey )
    RegCloseKey(hkey);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800372f8  mov     [rsp-8+arg_18], rbx
0x1800372fd  push    rbp
0x1800372fe  push    rsi
0x1800372ff  push    rdi
0x180037300  push    r14
0x180037302  push    r15
0x180037304  lea     rbp, [rsp-180h]
0x18003730c  sub     rsp, 280h
0x180037313  mov     rax, cs:__security_cookie
0x18003731a  xor     rax, rsp
0x18003731d  mov     [rbp+1A0h+var_30], rax
0x180037324  mov     rsi, r8
0x180037327  mov     [rsp+2A0h+hkey], 0
0x180037330  mov     rdi, rdx
0x180037333  mov     r14, rcx
0x180037336  mov     r15d, 104h
0x18003733c  lea     rcx, [rsp+2A0h+SubKey]; void *
0x180037341  xor     edx, edx; Val
0x180037343  mov     [rsp+2A0h+var_260], r15d
0x180037348  mov     r8d, 208h; Size
0x18003734e  call    memset_0
0x180037353  mov     rcx, [r14+18h]
0x180037357  mov     rax, [rcx]
0x18003735a  mov     rax, [rax+18h]
0x18003735e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037363  mov     r9, rax
0x180037366  lea     r8, aSS_1; "%s%s"
0x18003736d  lea     rax, aCachemanager; "\\CacheManager"
0x180037374  mov     edx, r15d; unsigned __int64
0x180037377  lea     rcx, [rsp+2A0h+SubKey]; unsigned __int16 *
0x18003737c  mov     [rsp+2A0h+phkResult], rax; int
0x180037381  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180037386  mov     ebx, eax
0x180037388  test    eax, eax
0x18003738a  jns     short loc_1800373E4
0x18003738c  mov     rcx, [rbp+1A8h]; this
0x180037393  lea     r8, aOnecoreuapBase_64; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18003739a  mov     r9d, eax; char *
0x18003739d  lea     edx, [r15-3Dh]; void *
0x1800373a1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800373a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800373ad  lea     rax, WPP_GLOBAL_Control
0x1800373b4  cmp     rcx, rax
0x1800373b7  jz      loc_180037566
0x1800373bd  test    byte ptr [rcx+1Ch], 80h
0x1800373c1  jz      loc_180037566
0x1800373c7  mov     edx, 0Fh
0x1800373cc  mov     rcx, [rcx+10h]
0x1800373d0  lea     r8, WPP_54d166b4b7773830bae608bc87214534_Traceguids
0x1800373d7  mov     r9d, ebx
0x1800373da  call    WPP_SF_d
0x1800373df  jmp     loc_180037566
0x1800373e4  lea     rax, [rsp+2A0h+hkey]
0x1800373e9  mov     r9d, 20019h; samDesired
0x1800373ef  xor     r8d, r8d; ulOptions
0x1800373f2  mov     [rsp+2A0h+phkResult], rax; int
0x1800373f7  lea     rdx, [rsp+2A0h+SubKey]; lpSubKey
0x1800373fc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180037403  call    cs:__imp_RegOpenKeyExW
0x180037409  test    eax, eax
0x18003740b  jnz     short loc_18003744F
0x18003740d  mov     rcx, [rsp+2A0h+hkey]; hkey
0x180037412  lea     rax, [rsp+2A0h+var_260]
0x180037417  mov     [rsp+2A0h+pcbData], rax; pcbData
0x18003741c  lea     r8, aImagecachepath; "ImageCachePath"
0x180037423  lea     rax, [rsp+2A0h+SubKey]
0x180037428  mov     r9d, 6; dwFlags
0x18003742e  mov     [rsp+2A0h+pvData], rax; pvData
0x180037433  xor     edx, edx; lpSubKey
0x180037435  mov     [rsp+2A0h+phkResult], 0; pdwType
0x18003743e  call    cs:__imp_RegGetValueW
0x180037444  test    eax, eax
0x180037446  jnz     short loc_18003744F
0x180037448  lea     rcx, [rsp+2A0h+SubKey]
0x18003744d  jmp     short loc_180037462
0x18003744f  mov     rcx, [r14+18h]
0x180037453  mov     rax, [rcx]
0x180037456  mov     rax, [rax+28h]
0x18003745a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003745f  mov     rcx, rax; lpSrc
0x180037462  mov     r8d, r15d; nSize
0x180037465  mov     rdx, rdi; lpDst
0x180037468  call    cs:__imp_ExpandEnvironmentStringsW
0x18003746e  mov     rcx, rsi
0x180037471  lea     r9, [r14+38h]
0x180037475  mov     [rcx], eax
0x180037477  cmp     qword ptr [r9+18h], 7
0x18003747c  jbe     short loc_180037481
0x18003747e  mov     r9, [r9]; pszMore
0x180037481  mov     r8, rdi; pszPathIn
0x180037484  mov     rdx, r15; cchPathOut
0x180037487  mov     rcx, rdi; pszPathOut
0x18003748a  call    cs:__imp_PathCchCombine
0x180037490  mov     ebx, eax
0x180037492  test    eax, eax
0x180037494  jns     short loc_1800374DA
0x180037496  test    cs:Microsoft_Windows_PushNotifications_PlatformEnableBits, 20h
0x18003749d  jz      loc_180037566
0x1800374a3  lea     rax, word_180124798
0x1800374aa  mov     [rsp+2A0h+pcbData], rax
0x1800374af  lea     r9, aCachemanagerGe; "CacheManager::GetCachePath"
0x1800374b6  mov     dword ptr [rsp+2A0h+pvData], ebx
0x1800374ba  lea     r8, aOnecoreuapBase_132; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800374c1  lea     rdx, WPNCORE_EVENT_DEBUG_INIT
0x1800374c8  mov     dword ptr [rsp+2A0h+phkResult], 0E4h
0x1800374d0  call    McTemplateU0zzdqz_EventWriteTransfer
0x1800374d5  jmp     loc_180037566
0x1800374da  mov     eax, [rsi]
0x1800374dc  lea     r8, [rsp+2A0h+var_250]; unsigned __int64 *
0x1800374e1  mov     rdx, r15; unsigned __int64
0x1800374e4  mov     [rsp+2A0h+var_250], rax
0x1800374e9  mov     rcx, rdi; unsigned __int16 *
0x1800374ec  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800374f1  mov     ebx, eax
0x1800374f3  test    eax, eax
0x1800374f5  jns     short loc_180037535
0x1800374f7  mov     rcx, [rbp+1A8h]; this
0x1800374fe  lea     r8, aOnecoreuapBase_64; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180037505  mov     r9d, eax; char *
0x180037508  mov     edx, 0E9h; void *
0x18003750d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180037512  mov     rcx, cs:WPP_GLOBAL_Control
0x180037519  lea     rax, WPP_GLOBAL_Control
0x180037520  cmp     rcx, rax
0x180037523  jz      short loc_180037566
0x180037525  test    byte ptr [rcx+1Ch], 80h
0x180037529  jz      short loc_180037566
0x18003752b  mov     edx, 11h
0x180037530  jmp     loc_1800373CC
0x180037535  mov     eax, dword ptr [rsp+2A0h+var_250]
0x180037539  mov     [rsi], eax
0x18003753b  dec     eax
0x18003753d  cmp     eax, 103h
0x180037542  jbe     short loc_180037566
0x180037544  mov     ebx, 80004005h
0x180037549  lea     r8, aCachemanagerGe; "CacheManager::GetCachePath"
0x180037550  mov     r9d, 0F0h; int
0x180037556  mov     dword ptr [rsp+2A0h+phkResult], ebx; int
0x18003755a  lea     rdx, aOnecoreuapBase_132; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180037561  call    ?WpnDebugInitTrace@@YAXKPEBG0HJ@Z; WpnDebugInitTrace(ulong,ushort const *,ushort const *,int,long)
0x180037566  mov     rcx, [rsp+2A0h+hkey]; hKey
0x18003756b  test    rcx, rcx
0x18003756e  jz      short loc_180037576
0x180037570  call    cs:__imp_RegCloseKey
0x180037576  mov     eax, ebx
0x180037578  mov     rcx, [rbp+1A0h+var_30]
0x18003757f  xor     rcx, rsp; StackCookie
0x180037582  call    __security_check_cookie
0x180037587  mov     rbx, [rsp+2A0h+arg_18]
0x18003758f  add     rsp, 280h
0x180037596  pop     r15
0x180037598  pop     r14
0x18003759a  pop     rdi
0x18003759b  pop     rsi
0x18003759c  pop     rbp
0x18003759d  retn
```
