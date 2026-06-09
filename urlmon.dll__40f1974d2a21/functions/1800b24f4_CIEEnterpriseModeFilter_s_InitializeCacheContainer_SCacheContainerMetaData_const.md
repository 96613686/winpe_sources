# CIEEnterpriseModeFilter::_s_InitializeCacheContainer(SCacheContainerMetaData const *)

- ea: `0x1800b24f4`
- end: `0x1800b26fc`
- name: `?_s_InitializeCacheContainer@CIEEnterpriseModeFilter@@CAJPEBUSCacheContainerMetaData@@@Z`
- size: `520`
- prototype: `__int64 __fastcall(const struct SCacheContainerMetaData *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800b0d18`

## callees

- `0x18001c470`
- `0x18003b538`
- `0x18008a620`
- `0x1800ae500`
- `0x1800b24f4`
- `0x18011ba3e`
- `0x18011baa0`
- `0x18011c010`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800b2530`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800b2542`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800b25bd`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800b262a`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800b2639`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800b2692`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800b2530`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800b2542`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800b25bd`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800b262a`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800b2639`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800b2692`
- `iertutil!__imp_?IEConfiguration_GetString@@YAPEBGW4IEConfigurationID@@@Z` at `0x1800b258b`
- `iertutil!__imp_?IEConfiguration_GetString@@YAPEBGW4IEConfigurationID@@@Z` at `0x1800b258b`
- `iertutil!__imp_GetBrowserProfileDataFilePath` at `0x1800b2574`
- `iertutil!__imp_GetBrowserProfileDataFilePath` at `0x1800b2574`
- `iertutil!__imp_?GetBrowserBrokerInterface@@YAJPEAPEAUIBrowserBrokerFactory@@@Z` at `0x1800b264d`
- `iertutil!__imp_?GetBrowserBrokerInterface@@YAJPEAPEAUIBrowserBrokerFactory@@@Z` at `0x1800b264d`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1800b257c`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1800b257c`
- `WININET!DeleteUrlCacheContainerW` at `0x1800b26a2`
- `WININET!DeleteUrlCacheContainerW` at `0x1800b26ad`
- `WININET!DeleteUrlCacheContainerW` at `0x1800b26a2`
- `WININET!DeleteUrlCacheContainerW` at `0x1800b26ad`
- `WININET!UrlCacheCreateContainer` at `0x1800b25fc`
- `WININET!UrlCacheCreateContainer` at `0x1800b26c5`
- `WININET!UrlCacheCreateContainer` at `0x1800b25fc`
- `WININET!UrlCacheCreateContainer` at `0x1800b26c5`

## pseudocode

```c
__int64 __fastcall CIEEnterpriseModeFilter::_s_InitializeCacheContainer(const struct SCacheContainerMetaData *a1)
{
  unsigned int IEBrowserModeFilterSpartanMediumILPath; // eax
  unsigned int BrowserProfileDataFilePath; // ebx
  const unsigned __int16 *String; // rax
  DWORD dwOptions; // ebp
  const WCHAR *v6; // rsi
  const WCHAR *v7; // r14
  signed int Container; // eax
  signed int v9; // eax
  struct IBrowserBrokerFactory *v11[2]; // [rsp+40h] [rbp-268h] BYREF
  WCHAR pwszDirectory[264]; // [rsp+50h] [rbp-258h] BYREF

  memset_0(pwszDirectory, 0, 0x208u);
  if ( (unsigned __int8)IEConfiguration_GetBool(268435519) && (unsigned __int8)IEConfiguration_GetBool(536870923) )
  {
    IEBrowserModeFilterSpartanMediumILPath = GetIEBrowserModeFilterSpartanMediumILPath(
                                               0,
                                               *((_QWORD *)a1 + 1),
                                               pwszDirectory,
                                               260);
LABEL_8:
    BrowserProfileDataFilePath = IEBrowserModeFilterSpartanMediumILPath;
    goto LABEL_9;
  }
  BrowserProfileDataFilePath = GetBrowserProfileDataFilePath(*(_QWORD *)a1, 0, pwszDirectory, 260);
  if ( IsDualEngineProcess() )
  {
    String = (const unsigned __int16 *)IEConfiguration_GetString(268435540);
    if ( String )
    {
      if ( *String )
      {
        IEBrowserModeFilterSpartanMediumILPath = StringCchCatW(pwszDirectory, 0x104u, String);
        goto LABEL_8;
      }
    }
  }
LABEL_9:
  if ( !BrowserProfileDataFilePath )
  {
    dwOptions = (((unsigned __int8)IEConfiguration_GetBool(268435519) ^ 1) << 9) + 256;
    v6 = (const WCHAR *)EMIECacheContainerString(*((_QWORD *)a1 + 1));
    v7 = (const WCHAR *)EMIECacheContainerString(*((_QWORD *)a1 + 2));
    Container = UrlCacheCreateContainer(v6, v7, pwszDirectory, 0, dwOptions);
    BrowserProfileDataFilePath = Container;
    if ( Container > 0 )
      BrowserProfileDataFilePath = (unsigned __int16)Container | 0x80070000;
    if ( BrowserProfileDataFilePath == -2147024713 || BrowserProfileDataFilePath == -2147024891 )
    {
      if ( (unsigned __int8)IEConfiguration_GetBool(268435519) )
      {
        if ( (unsigned __int8)IEConfiguration_GetBool(536870913) )
        {
          v11[0] = 0;
          if ( (int)GetBrowserBrokerInterface(v11) >= 0 )
            (*(void (__fastcall **)(struct IBrowserBrokerFactory *, const WCHAR *, const WCHAR *, const OLECHAR *, _QWORD, DWORD, _DWORD))(*(_QWORD *)v11[0] + 120LL))(
              v11[0],
              v6,
              v7,
              &pszFormat,
              0,
              dwOptions,
              0);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)v11);
        }
        if ( (unsigned __int8)IEConfiguration_GetBool(536870915) )
          DeleteUrlCacheContainerW(*((LPCWSTR *)a1 + 1), 0);
      }
      DeleteUrlCacheContainerW(v6, 0);
      v9 = UrlCacheCreateContainer(v6, v7, pwszDirectory, 0, dwOptions);
      BrowserProfileDataFilePath = v9;
      if ( v9 > 0 )
        return (unsigned __int16)v9 | 0x80070000;
    }
  }
  return BrowserProfileDataFilePath;
}

```

## disassembly

```asm
0x1800b24f4  push    rbx
0x1800b24f6  push    rbp
0x1800b24f7  push    rsi
0x1800b24f8  push    rdi
0x1800b24f9  push    r14
0x1800b24fb  push    r15
0x1800b24fd  sub     rsp, 278h
0x1800b2504  mov     rax, cs:__security_cookie
0x1800b250b  xor     rax, rsp
0x1800b250e  mov     [rsp+2A8h+var_48], rax
0x1800b2516  mov     rdi, rcx
0x1800b2519  xor     edx, edx; Val
0x1800b251b  lea     rcx, [rsp+2A8h+pwszDirectory]; void *
0x1800b2520  mov     r8d, 208h; Size
0x1800b2526  call    memset_0
0x1800b252b  mov     ecx, 1000003Fh
0x1800b2530  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1800b2536  xor     r15d, r15d
0x1800b2539  test    al, al
0x1800b253b  jz      short loc_1800B2564
0x1800b253d  mov     ecx, 2000000Bh
0x1800b2542  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1800b2548  test    al, al
0x1800b254a  jz      short loc_1800B2564
0x1800b254c  mov     rdx, [rdi+8]
0x1800b2550  lea     r8, [rsp+2A8h+pwszDirectory]
0x1800b2555  mov     r9d, 104h
0x1800b255b  xor     ecx, ecx
0x1800b255d  call    GetIEBrowserModeFilterSpartanMediumILPath
0x1800b2562  jmp     short loc_1800B25AE
0x1800b2564  mov     rcx, [rdi]
0x1800b2567  lea     r8, [rsp+2A8h+pwszDirectory]
0x1800b256c  mov     r9d, 104h
0x1800b2572  xor     edx, edx
0x1800b2574  call    cs:__imp_GetBrowserProfileDataFilePath
0x1800b257a  mov     ebx, eax
0x1800b257c  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x1800b2582  test    al, al
0x1800b2584  jz      short loc_1800B25B0
0x1800b2586  mov     ecx, 10000054h
0x1800b258b  call    cs:__imp_?IEConfiguration_GetString@@YAPEBGW4IEConfigurationID@@@Z; IEConfiguration_GetString(IEConfigurationID)
0x1800b2591  test    rax, rax
0x1800b2594  jz      short loc_1800B25B0
0x1800b2596  cmp     [rax], r15w
0x1800b259a  jz      short loc_1800B25B0
0x1800b259c  mov     r8, rax; unsigned __int16 *
0x1800b259f  lea     rcx, [rsp+2A8h+pwszDirectory]; unsigned __int16 *
0x1800b25a4  mov     edx, 104h; unsigned __int64
0x1800b25a9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800b25ae  mov     ebx, eax
0x1800b25b0  test    ebx, ebx
0x1800b25b2  jnz     loc_1800B26DA
0x1800b25b8  mov     ecx, 1000003Fh
0x1800b25bd  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1800b25c3  mov     rcx, [rdi+8]
0x1800b25c7  movzx   ebp, al
0x1800b25ca  xor     ebp, 1
0x1800b25cd  shl     ebp, 9
0x1800b25d0  add     ebp, 100h
0x1800b25d6  call    EMIECacheContainerString
0x1800b25db  mov     rcx, [rdi+10h]
0x1800b25df  mov     rsi, rax
0x1800b25e2  call    EMIECacheContainerString
0x1800b25e7  xor     r9d, r9d; ullLimit
0x1800b25ea  mov     [rsp+2A8h+dwOptions], ebp; dwOptions
0x1800b25ee  lea     r8, [rsp+2A8h+pwszDirectory]; pwszDirectory
0x1800b25f3  mov     rdx, rax; pwszPrefix
0x1800b25f6  mov     rcx, rsi; pwszName
0x1800b25f9  mov     r14, rax
0x1800b25fc  call    cs:__imp_UrlCacheCreateContainer
0x1800b2602  mov     ebx, eax
0x1800b2604  test    eax, eax
0x1800b2606  jle     short loc_1800B2611
0x1800b2608  movzx   ebx, ax
0x1800b260b  or      ebx, 80070000h
0x1800b2611  cmp     ebx, 800700B7h
0x1800b2617  jz      short loc_1800B2625
0x1800b2619  cmp     ebx, 80070005h
0x1800b261f  jnz     loc_1800B26DA
0x1800b2625  mov     ecx, 1000003Fh
0x1800b262a  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1800b2630  test    al, al
0x1800b2632  jz      short loc_1800B26A8
0x1800b2634  mov     ecx, 20000001h
0x1800b2639  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1800b263f  test    al, al
0x1800b2641  jz      short loc_1800B268D
0x1800b2643  lea     rcx, [rsp+2A8h+var_268]
0x1800b2648  mov     [rsp+2A8h+var_268], r15
0x1800b264d  call    cs:__imp_?GetBrowserBrokerInterface@@YAJPEAPEAUIBrowserBrokerFactory@@@Z; GetBrowserBrokerInterface(IBrowserBrokerFactory * *)
0x1800b2653  test    eax, eax
0x1800b2655  js      short loc_1800B2683
0x1800b2657  mov     rcx, [rsp+2A8h+var_268]
0x1800b265c  lea     r9, pszFormat
0x1800b2663  mov     [rsp+2A8h+var_278], r15d
0x1800b2668  mov     r8, r14
0x1800b266b  mov     [rsp+2A8h+var_280], ebp
0x1800b266f  mov     rdx, rsi
0x1800b2672  mov     qword ptr [rsp+2A8h+dwOptions], r15
0x1800b2677  mov     rax, [rcx]
0x1800b267a  mov     rax, [rax+78h]
0x1800b267e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2683  lea     rcx, [rsp+2A8h+var_268]
0x1800b2688  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800b268d  mov     ecx, 20000003h
0x1800b2692  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1800b2698  test    al, al
0x1800b269a  jz      short loc_1800B26A8
0x1800b269c  mov     rcx, [rdi+8]; Name
0x1800b26a0  xor     edx, edx; dwOptions
0x1800b26a2  call    cs:__imp_DeleteUrlCacheContainerW
0x1800b26a8  xor     edx, edx; dwOptions
0x1800b26aa  mov     rcx, rsi; Name
0x1800b26ad  call    cs:__imp_DeleteUrlCacheContainerW
0x1800b26b3  xor     r9d, r9d; ullLimit
0x1800b26b6  mov     [rsp+2A8h+dwOptions], ebp; dwOptions
0x1800b26ba  lea     r8, [rsp+2A8h+pwszDirectory]; pwszDirectory
0x1800b26bf  mov     rdx, r14; pwszPrefix
0x1800b26c2  mov     rcx, rsi; pwszName
0x1800b26c5  call    cs:__imp_UrlCacheCreateContainer
0x1800b26cb  mov     ebx, eax
0x1800b26cd  test    eax, eax
0x1800b26cf  jle     short loc_1800B26DA
0x1800b26d1  movzx   ebx, ax
0x1800b26d4  or      ebx, 80070000h
0x1800b26da  mov     eax, ebx
0x1800b26dc  mov     rcx, [rsp+2A8h+var_48]
0x1800b26e4  xor     rcx, rsp; StackCookie
0x1800b26e7  call    __security_check_cookie
0x1800b26ec  add     rsp, 278h
0x1800b26f3  pop     r15
0x1800b26f5  pop     r14
0x1800b26f7  pop     rdi
0x1800b26f8  pop     rsi
0x1800b26f9  pop     rbp
0x1800b26fa  pop     rbx
0x1800b26fb  retn
```
