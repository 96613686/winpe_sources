# SchannelInit(int)

- ea: `0x180025c38`
- end: `0x180025ee0`
- name: `?SchannelInit@@YAHH@Z`
- size: `680`
- prototype: `__int64 __fastcall(int)`
- caller_count: `17`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x180025ad0`
- `0x18002b800`
- `0x180040e00`
- `0x180041f50`
- `0x18004dd80`
- `0x1800537e0`
- `0x18005fb20`
- `0x180068f60`
- `0x180069230`
- `0x18006d090`
- `0x18006de90`
- `0x18006e020`
- `0x18006e130`
- `0x18006e6b0`
- `0x18006e7b0`
- `0x18006ee80`
- `0x18006f1b0`

## callees

- `0x180021da8`
- `0x180021eb0`
- `0x180025c38`
- `0x180043f78`
- `0x1800473dc`
- `0x180047a5c`
- `0x18004cf18`
- `0x18004e2ac`
- `0x18004e3f0`
- `0x1800539f4`
- `0x180053bec`
- `0x180054884`
- `0x180055730`
- `0x18005eef0`
- `0x18005f1e4`
- `0x18005f91c`
- `0x18007179c`
- `0x18007198c`
- `0x180073938`
- `0x180077854`
- `0x180077ff4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025d50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025d50`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180025c83`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180025c83`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x180025ead`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x180025ead`
- `ntdll!RtlEnterCriticalSection` at `0x180025c63`
- `ntdll!RtlEnterCriticalSection` at `0x180025c63`
- `ntdll!RtlLeaveCriticalSection` at `0x180025ec8`
- `ntdll!RtlLeaveCriticalSection` at `0x180025ec8`
- `CRYPT32!I_CertWnfEnableFlushCache` at `0x180025e3b`
- `CRYPT32!I_CertWnfEnableFlushCache` at `0x180025e3b`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180025caf`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180025cd4`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180025cf2`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180025d10`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180025caf`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180025cd4`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180025cf2`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180025d10`
- `CRYPTSP!CryptAcquireContextW` at `0x180025d3b`
- `CRYPTSP!CryptAcquireContextW` at `0x180025d3b`

## pseudocode

```c
__int64 __fastcall SchannelInit(int a1)
{
  unsigned int v3; // ebx
  CCipherMill *v4; // rcx
  DWORD LastError; // edi
  unsigned __int16 *v6; // rcx
  CSessionCacheManager *CacheManager; // rax
  CSslCredManager *v8; // rax

  if ( CSslGlobals::m_bSchannelInitialized )
    return 1;
  RtlEnterCriticalSection(&CSslGlobals::m_InitCriticalSection);
  if ( !CSslGlobals::m_bSchannelInitialized )
  {
    DisableThreadLibraryCalls(CSslGlobals::m_hInstance);
    SafeAllocaInitialize();
    v3 = 1;
    if ( a1 )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Schannel_SslCopyTlsExtensions>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Schannel_SslCopyTlsExtensions>::GetImpl'::`2'::impl)
        && !(unsigned int)LoadSslRegistryOptions() )
      {
        goto LABEL_7;
      }
    }
    else
    {
      if ( BCryptOpenAlgorithmProvider(&g_hSHAProvider, L"SHA1", 0, 0)
        || BCryptOpenAlgorithmProvider(&g_hMD5Provider, L"MD5", 0, 0)
        || BCryptOpenAlgorithmProvider(&g_hDSAProvider, L"DSA", 0, 0)
        || BCryptOpenAlgorithmProvider(&g_hRSAProvider, L"RSA", 0, 0)
        || CCipherMill::BuildCipherMill(v4) )
      {
        goto LABEL_7;
      }
      if ( !CryptAcquireContextW(&g_hDhSchannelProv, 0, 0, 0x12u, 0xF0000000) )
      {
        g_hDhSchannelProv = 0;
        LastError = GetLastError();
        v6 = (unsigned __int16 *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_b032270e2095315efa9e144016cb8858_Traceguids, LastError);
        LogGlobalAcquireContextFailedEvent(v6, LastError);
      }
      if ( !(unsigned int)LoadSslRegistryOptions() )
        goto LABEL_7;
      SchInitializeEvents();
      CacheManager = CSessionCacheManager::CreateCacheManager();
      if ( !CacheManager || CSessionCacheManager::InitializeSessionCache(CacheManager) || InitializeIssuerCache() )
        goto LABEL_7;
      v8 = CSslCredManager::m_pCredManager;
      if ( !CSslCredManager::m_pCredManager )
      {
        v8 = (CSslCredManager *)SPExternalAlloc(0x60u);
        if ( v8 )
          *(_QWORD *)v8 = &CSslCredManager::`vftable';
        CSslCredManager::m_pCredManager = v8;
        if ( !v8 )
          goto LABEL_7;
      }
      if ( !CSslCredManager::InitCredentialManager(v8) )
        goto LABEL_7;
      SslInitSystemMapper();
      if ( InitializeSslMemoryOptions()
        || CSslGlobals::InitializePeriodicCleanupHandler()
        || CSslGlobals::InitializeCryptLocatorEvents() )
      {
        goto LABEL_7;
      }
      I_CertWnfEnableFlushCache();
    }
    if ( !(unsigned int)InitializeClientSideSslProvCache() )
    {
      CSslGlobals::m_bSchannelInitialized = 1;
      if ( !a1 && (g_dwEventLogging & 4) != 0 )
        SchEventWrite(&SSLEVENT_SCHANNEL_STARTED, 0);
      if ( !CTelemetryContext::s_IsTelemetryGloballyInitialized && !(unsigned int)TlgRegisterAggregateProviderEx() )
      {
        CTelemetryContext::s_IsTelemetryGloballyInitialized = 1;
        QueryPerformanceFrequency(&CTelemetryContext::s_PerfCtrFreq);
      }
      goto LABEL_39;
    }
LABEL_7:
    v3 = 0;
LABEL_39:
    if ( !CSslGlobals::m_bSchannelInitialized )
      SchannelShutdown();
    goto LABEL_41;
  }
  v3 = 1;
LABEL_41:
  RtlLeaveCriticalSection(&CSslGlobals::m_InitCriticalSection);
  return v3;
}

```

## disassembly

```asm
0x180025c38  mov     [rsp+arg_0], rbx
0x180025c3d  mov     [rsp+arg_8], rsi
0x180025c42  push    rdi
0x180025c43  sub     rsp, 30h
0x180025c47  cmp     cs:?m_bSchannelInitialized@CSslGlobals@@2HA, 0; int CSslGlobals::m_bSchannelInitialized
0x180025c4e  mov     esi, ecx
0x180025c50  jz      short loc_180025C5C
0x180025c52  mov     eax, 1
0x180025c57  jmp     loc_180025ED0
0x180025c5c  lea     rcx, ?m_InitCriticalSection@CSslGlobals@@2U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180025c63  call    cs:__imp_RtlEnterCriticalSection
0x180025c69  cmp     cs:?m_bSchannelInitialized@CSslGlobals@@2HA, 0; int CSslGlobals::m_bSchannelInitialized
0x180025c70  jz      short loc_180025C7C
0x180025c72  mov     ebx, 1
0x180025c77  jmp     loc_180025EC1
0x180025c7c  mov     rcx, cs:?m_hInstance@CSslGlobals@@2PEAUHINSTANCE__@@EA; hLibModule
0x180025c83  call    cs:__imp_DisableThreadLibraryCalls
0x180025c89  call    SafeAllocaInitialize
0x180025c8e  mov     ebx, 1
0x180025c93  test    esi, esi
0x180025c95  jnz     loc_180025E43
0x180025c9b  xor     r9d, r9d; dwFlags
0x180025c9e  lea     rdx, aSha1; "SHA1"
0x180025ca5  xor     r8d, r8d; pszImplementation
0x180025ca8  lea     rcx, ?g_hSHAProvider@@3PEAXEA; phAlgorithm
0x180025caf  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180025cb5  test    eax, eax
0x180025cb7  jz      short loc_180025CC0
0x180025cb9  xor     ebx, ebx
0x180025cbb  jmp     loc_180025EB3
0x180025cc0  xor     r9d, r9d; dwFlags
0x180025cc3  lea     rdx, aMd5_0; "MD5"
0x180025cca  xor     r8d, r8d; pszImplementation
0x180025ccd  lea     rcx, ?g_hMD5Provider@@3PEAXEA; phAlgorithm
0x180025cd4  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180025cda  test    eax, eax
0x180025cdc  jnz     short loc_180025CB9
0x180025cde  xor     r9d, r9d; dwFlags
0x180025ce1  lea     rdx, aDsa; "DSA"
0x180025ce8  xor     r8d, r8d; pszImplementation
0x180025ceb  lea     rcx, ?g_hDSAProvider@@3PEAXEA; phAlgorithm
0x180025cf2  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180025cf8  test    eax, eax
0x180025cfa  jnz     short loc_180025CB9
0x180025cfc  xor     r9d, r9d; dwFlags
0x180025cff  lea     rdx, aRsa; "RSA"
0x180025d06  xor     r8d, r8d; pszImplementation
0x180025d09  lea     rcx, ?g_hRSAProvider@@3PEAXEA; phAlgorithm
0x180025d10  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180025d16  test    eax, eax
0x180025d18  jnz     short loc_180025CB9
0x180025d1a  call    ?BuildCipherMill@CCipherMill@@QEAAKXZ; CCipherMill::BuildCipherMill(void)
0x180025d1f  test    eax, eax
0x180025d21  jnz     short loc_180025CB9
0x180025d23  lea     r9d, [rax+12h]; dwProvType
0x180025d27  mov     [rsp+38h+dwFlags], 0F0000000h; dwFlags
0x180025d2f  xor     r8d, r8d; szProvider
0x180025d32  lea     rcx, ?g_hDhSchannelProv@@3_KA; phProv
0x180025d39  xor     edx, edx; szContainer
0x180025d3b  call    cs:__imp_CryptAcquireContextW
0x180025d41  test    eax, eax
0x180025d43  jnz     short loc_180025D8F
0x180025d45  mov     cs:?g_hDhSchannelProv@@3_KA, 0; unsigned __int64 g_hDhSchannelProv
0x180025d50  call    cs:__imp_GetLastError
0x180025d56  mov     edi, eax
0x180025d58  mov     rcx, cs:WPP_GLOBAL_Control
0x180025d5f  lea     rax, WPP_GLOBAL_Control
0x180025d66  cmp     rcx, rax
0x180025d69  jz      short loc_180025D88
0x180025d6b  test    [rcx+1Ch], bl
0x180025d6e  jz      short loc_180025D88
0x180025d70  mov     rcx, [rcx+10h]
0x180025d74  lea     r8, WPP_b032270e2095315efa9e144016cb8858_Traceguids
0x180025d7b  mov     edx, 0Ch
0x180025d80  mov     r9d, edi
0x180025d83  call    WPP_SF_d
0x180025d88  mov     edx, edi; unsigned int
0x180025d8a  call    ?LogGlobalAcquireContextFailedEvent@@YAXPEAGK@Z; LogGlobalAcquireContextFailedEvent(ushort *,ulong)
0x180025d8f  call    ?LoadSslRegistryOptions@@YAHXZ; LoadSslRegistryOptions(void)
0x180025d94  test    eax, eax
0x180025d96  jz      loc_180025CB9
0x180025d9c  call    ?SchInitializeEvents@@YAKXZ; SchInitializeEvents(void)
0x180025da1  call    ?CreateCacheManager@CSessionCacheManager@@SAPEAV1@XZ; CSessionCacheManager::CreateCacheManager(void)
0x180025da6  test    rax, rax
0x180025da9  jz      loc_180025CB9
0x180025daf  mov     rcx, rax; this
0x180025db2  call    ?InitializeSessionCache@CSessionCacheManager@@QEAAKXZ; CSessionCacheManager::InitializeSessionCache(void)
0x180025db7  test    eax, eax
0x180025db9  jnz     loc_180025CB9
0x180025dbf  call    ?InitializeIssuerCache@@YAKXZ; InitializeIssuerCache(void)
0x180025dc4  test    eax, eax
0x180025dc6  jnz     loc_180025CB9
0x180025dcc  mov     rax, cs:?m_pCredManager@CSslCredManager@@0PEAV1@EA; CSslCredManager * CSslCredManager::m_pCredManager
0x180025dd3  test    rax, rax
0x180025dd6  jnz     short loc_180025DFF
0x180025dd8  lea     ecx, [rax+60h]; uBytes
0x180025ddb  call    ?SPExternalAlloc@@YAPEAXK@Z; SPExternalAlloc(ulong)
0x180025de0  test    rax, rax
0x180025de3  jz      short loc_180025DEF
0x180025de5  lea     rcx, ??_7CSslCredManager@@6B@; const CSslCredManager::`vftable'
0x180025dec  mov     [rax], rcx
0x180025def  mov     cs:?m_pCredManager@CSslCredManager@@0PEAV1@EA, rax; CSslCredManager * CSslCredManager::m_pCredManager
0x180025df6  test    rax, rax
0x180025df9  jz      loc_180025CB9
0x180025dff  mov     rcx, rax; this
0x180025e02  call    ?InitCredentialManager@CSslCredManager@@QEAAEXZ; CSslCredManager::InitCredentialManager(void)
0x180025e07  test    al, al
0x180025e09  jz      loc_180025CB9
0x180025e0f  call    ?SslInitSystemMapper@@YAKXZ; SslInitSystemMapper(void)
0x180025e14  call    ?InitializeSslMemoryOptions@@YAKXZ; InitializeSslMemoryOptions(void)
0x180025e19  test    eax, eax
0x180025e1b  jnz     loc_180025CB9
0x180025e21  call    ?InitializePeriodicCleanupHandler@CSslGlobals@@SAKXZ; CSslGlobals::InitializePeriodicCleanupHandler(void)
0x180025e26  test    eax, eax
0x180025e28  jnz     loc_180025CB9
0x180025e2e  call    ?InitializeCryptLocatorEvents@CSslGlobals@@SAKXZ; CSslGlobals::InitializeCryptLocatorEvents(void)
0x180025e33  test    eax, eax
0x180025e35  jnz     loc_180025CB9
0x180025e3b  call    cs:__imp_I_CertWnfEnableFlushCache
0x180025e41  jmp     short loc_180025E60
0x180025e43  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Schannel_SslCopyTlsExtensions@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Schannel_SslCopyTlsExtensions@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Schannel_SslCopyTlsExtensions> `wil::Feature<__WilFeatureTraits_Feature_Schannel_SslCopyTlsExtensions>::GetImpl(void)'::`2'::impl
0x180025e4a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Schannel_SslCopyTlsExtensions@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Schannel_SslCopyTlsExtensions>::__private_IsEnabled(void)
0x180025e4f  test    al, al
0x180025e51  jz      short loc_180025E60
0x180025e53  call    ?LoadSslRegistryOptions@@YAHXZ; LoadSslRegistryOptions(void)
0x180025e58  test    eax, eax
0x180025e5a  jz      loc_180025CB9
0x180025e60  call    ?InitializeClientSideSslProvCache@@YAJXZ; InitializeClientSideSslProvCache(void)
0x180025e65  test    eax, eax
0x180025e67  jnz     loc_180025CB9
0x180025e6d  mov     cs:?m_bSchannelInitialized@CSslGlobals@@2HA, ebx; int CSslGlobals::m_bSchannelInitialized
0x180025e73  test    esi, esi
0x180025e75  jnz     short loc_180025E8E
0x180025e77  test    cs:?g_dwEventLogging@@3KA, 4; ulong g_dwEventLogging
0x180025e7e  jz      short loc_180025E8E
0x180025e80  xor     edx, edx; unsigned __int16 *
0x180025e82  lea     rcx, SSLEVENT_SCHANNEL_STARTED; struct _EVENT_DESCRIPTOR *
0x180025e89  call    ?SchEventWrite@@YAKPEBU_EVENT_DESCRIPTOR@@PEAGZZ; SchEventWrite(_EVENT_DESCRIPTOR const *,ushort *,...)
0x180025e8e  cmp     cs:?s_IsTelemetryGloballyInitialized@CTelemetryContext@@1_NA, 0; bool CTelemetryContext::s_IsTelemetryGloballyInitialized
0x180025e95  jnz     short loc_180025EB3
0x180025e97  call    TlgRegisterAggregateProviderEx
0x180025e9c  test    eax, eax
0x180025e9e  jnz     short loc_180025EB3
0x180025ea0  lea     rcx, ?s_PerfCtrFreq@CTelemetryContext@@1T_LARGE_INTEGER@@A; lpFrequency
0x180025ea7  mov     cs:?s_IsTelemetryGloballyInitialized@CTelemetryContext@@1_NA, bl; bool CTelemetryContext::s_IsTelemetryGloballyInitialized
0x180025ead  call    cs:__imp_QueryPerformanceFrequency
0x180025eb3  cmp     cs:?m_bSchannelInitialized@CSslGlobals@@2HA, 0; int CSslGlobals::m_bSchannelInitialized
0x180025eba  jnz     short loc_180025EC1
0x180025ebc  call    ?SchannelShutdown@@YAHXZ; SchannelShutdown(void)
0x180025ec1  lea     rcx, ?m_InitCriticalSection@CSslGlobals@@2U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180025ec8  call    cs:__imp_RtlLeaveCriticalSection
0x180025ece  mov     eax, ebx
0x180025ed0  mov     rbx, [rsp+38h+arg_0]
0x180025ed5  mov     rsi, [rsp+38h+arg_8]
0x180025eda  add     rsp, 30h
0x180025ede  pop     rdi
0x180025edf  retn
```
