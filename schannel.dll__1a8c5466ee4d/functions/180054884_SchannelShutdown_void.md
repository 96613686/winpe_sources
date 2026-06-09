# SchannelShutdown(void)

- ea: `0x180054884`
- end: `0x180054a85`
- name: `?SchannelShutdown@@YAHXZ`
- size: `513`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `14`
- tags: `loader_planting`

## callers

- `0x180025c38`
- `0x18003c970`

## callees

- `0x180047578`
- `0x180054884`
- `0x180054a8c`
- `0x180057ec0`
- `0x18005fa88`
- `0x18007164c`
- `0x180071698`
- `0x1800716ec`
- `0x180071e90`
- `0x180073c18`
- `0x180075a64`
- `0x180077bbc`
- `0x180078330`
- `0x1800887f4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054a26`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054a26`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800549f9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800549f9`
- `ntdll!RtlEnterCriticalSection` at `0x1800548a3`
- `ntdll!RtlEnterCriticalSection` at `0x1800548a3`
- `ntdll!RtlLeaveCriticalSection` at `0x180054a6f`
- `ntdll!RtlLeaveCriticalSection` at `0x180054a6f`
- `ntdll!RtlDeleteResource` at `0x180054a19`
- `ntdll!RtlDeleteResource` at `0x180054a19`
- `ntdll!RtlAcquireResourceExclusive` at `0x18005499a`
- `ntdll!RtlAcquireResourceExclusive` at `0x18005499a`
- `ntdll!RtlReleaseResource` at `0x1800549ae`
- `ntdll!RtlReleaseResource` at `0x1800549ae`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180054918`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180054933`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18005494e`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180054969`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180054918`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180054933`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18005494e`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180054969`
- `CRYPTSP!CryptReleaseContext` at `0x180054984`
- `CRYPTSP!CryptReleaseContext` at `0x180054984`

## pseudocode

```c
__int64 SchannelShutdown(void)
{
  BOOL v0; // ebx
  unsigned int v1; // edx
  CSslCredManager *v2; // rcx
  CCipherMill *v3; // rcx
  unsigned int v4; // ebx

  v0 = LsaTable == 0;
  RtlEnterCriticalSection(&CSslGlobals::m_InitCriticalSection);
  if ( v0 )
  {
    UnloadSslRegOptions();
  }
  else
  {
    v2 = CSessionCacheManager::m_pSessionCacheManager;
    if ( CSessionCacheManager::m_pSessionCacheManager )
    {
      CSessionCacheManager::ShutdownSessionCache(CSessionCacheManager::m_pSessionCacheManager);
      CSessionCacheManager::m_pSessionCacheManager = 0;
    }
    if ( CSslCredManager::m_pCredManager )
    {
      CSslCredManager::FreeCredentialManager(v2);
      CSslCredManager::m_pCredManager = 0;
    }
    if ( DTLSCookieManager::m_pCookieMgr )
    {
      DTLSCookieManager::`scalar deleting destructor'(DTLSCookieManager::m_pCookieMgr, v1);
      DTLSCookieManager::m_pCookieMgr = 0;
    }
    ShutdownIssuerCache();
    SchShutdownEvents();
    UnloadSslRegOptions();
    TlsCloseBCryptHashProviders();
    if ( g_hSHAProvider )
    {
      BCryptCloseAlgorithmProvider(g_hSHAProvider, 0);
      g_hSHAProvider = 0;
    }
    if ( g_hMD5Provider )
    {
      BCryptCloseAlgorithmProvider(g_hMD5Provider, 0);
      g_hMD5Provider = 0;
    }
    if ( g_hDSAProvider )
    {
      BCryptCloseAlgorithmProvider(g_hDSAProvider, 0);
      g_hDSAProvider = 0;
    }
    if ( g_hRSAProvider )
    {
      BCryptCloseAlgorithmProvider(g_hRSAProvider, 0);
      g_hRSAProvider = 0;
    }
    if ( g_hDhSchannelProv )
    {
      CryptReleaseContext(g_hDhSchannelProv, 0);
      g_hDhSchannelProv = 0;
    }
    RtlAcquireResourceExclusive(&Resource, 1u);
    CCipherMill::ClearCipherMill(v3, 1u);
    RtlReleaseResource(&Resource);
    CSslGlobals::CleanupPeriodicCleanupHandler();
    CSslGlobals::CleanupCryptLocatorHandles();
    CSslGlobals::CleanupCryptLocatorEvents();
  }
  if ( CTelemetryContext::s_IsTelemetryGloballyInitialized )
  {
    CTelemetryContext::s_IsTelemetryGloballyInitialized = 0;
    TlgUnregisterAggregateProvider();
  }
  if ( g_hMskeyprotect )
  {
    g_pKeyFileProtectSessionTicket = 0;
    g_pKeyFileUnprotectSessionTicket = 0;
    FreeLibrary(g_hMskeyprotect);
    g_hMskeyprotect = 0;
    g_InitOnceMskeyprotect.Ptr = 0;
  }
  if ( g_pSslProvCacheRWLock )
  {
    RtlDeleteResource(g_pSslProvCacheRWLock);
    LocalFree(g_pSslProvCacheRWLock);
  }
  v4 = 0;
  for ( g_pSslProvCacheRWLock = 0; v4 < g_cCachedPagedSslProvs; ++v4 )
    DestroyCachedSslProv((struct CACHED_SSL_PROVIDER *)(&g_rgCachedPagedSslProvs + 2 * v4));
  g_cCachedPagedSslProvs = 0;
  CSslGlobals::m_bSchannelInitialized = 0;
  RtlLeaveCriticalSection(&CSslGlobals::m_InitCriticalSection);
  return 1;
}

```

## disassembly

```asm
0x180054884  mov     [rsp+arg_0], rbx
0x180054889  push    rdi
0x18005488a  sub     rsp, 20h
0x18005488e  xor     edi, edi
0x180054890  lea     rcx, ?m_InitCriticalSection@CSslGlobals@@2U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180054897  cmp     cs:LsaTable, rdi
0x18005489e  mov     ebx, edi
0x1800548a0  setz    bl
0x1800548a3  call    cs:__imp_RtlEnterCriticalSection
0x1800548a9  test    ebx, ebx
0x1800548ab  jnz     loc_1800549C5
0x1800548b1  mov     rcx, cs:?m_pSessionCacheManager@CSessionCacheManager@@0PEAV1@EA; this
0x1800548b8  test    rcx, rcx
0x1800548bb  jz      short loc_1800548C9
0x1800548bd  call    ?ShutdownSessionCache@CSessionCacheManager@@QEAAKXZ; CSessionCacheManager::ShutdownSessionCache(void)
0x1800548c2  mov     cs:?m_pSessionCacheManager@CSessionCacheManager@@0PEAV1@EA, rdi; CSessionCacheManager * CSessionCacheManager::m_pSessionCacheManager
0x1800548c9  cmp     cs:?m_pCredManager@CSslCredManager@@0PEAV1@EA, rdi; CSslCredManager * CSslCredManager::m_pCredManager
0x1800548d0  jz      short loc_1800548DE
0x1800548d2  call    ?FreeCredentialManager@CSslCredManager@@QEAAXXZ; CSslCredManager::FreeCredentialManager(void)
0x1800548d7  mov     cs:?m_pCredManager@CSslCredManager@@0PEAV1@EA, rdi; CSslCredManager * CSslCredManager::m_pCredManager
0x1800548de  mov     rcx, cs:?m_pCookieMgr@DTLSCookieManager@@0PEAV1@EA; this
0x1800548e5  test    rcx, rcx
0x1800548e8  jz      short loc_1800548F6
0x1800548ea  call    ??_GDTLSCookieManager@@QEAAPEAXI@Z; DTLSCookieManager::`scalar deleting destructor'(uint)
0x1800548ef  mov     cs:?m_pCookieMgr@DTLSCookieManager@@0PEAV1@EA, rdi; DTLSCookieManager * DTLSCookieManager::m_pCookieMgr
0x1800548f6  call    ?ShutdownIssuerCache@@YAXXZ; ShutdownIssuerCache(void)
0x1800548fb  call    ?SchShutdownEvents@@YAXXZ; SchShutdownEvents(void)
0x180054900  call    ?UnloadSslRegOptions@@YAXXZ; UnloadSslRegOptions(void)
0x180054905  call    ?TlsCloseBCryptHashProviders@@YAXXZ; TlsCloseBCryptHashProviders(void)
0x18005490a  mov     rcx, cs:?g_hSHAProvider@@3PEAXEA; hAlgorithm
0x180054911  test    rcx, rcx
0x180054914  jz      short loc_180054925
0x180054916  xor     edx, edx; dwFlags
0x180054918  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18005491e  mov     cs:?g_hSHAProvider@@3PEAXEA, rdi; void * g_hSHAProvider
0x180054925  mov     rcx, cs:?g_hMD5Provider@@3PEAXEA; hAlgorithm
0x18005492c  test    rcx, rcx
0x18005492f  jz      short loc_180054940
0x180054931  xor     edx, edx; dwFlags
0x180054933  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180054939  mov     cs:?g_hMD5Provider@@3PEAXEA, rdi; void * g_hMD5Provider
0x180054940  mov     rcx, cs:?g_hDSAProvider@@3PEAXEA; hAlgorithm
0x180054947  test    rcx, rcx
0x18005494a  jz      short loc_18005495B
0x18005494c  xor     edx, edx; dwFlags
0x18005494e  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180054954  mov     cs:?g_hDSAProvider@@3PEAXEA, rdi; void * g_hDSAProvider
0x18005495b  mov     rcx, cs:?g_hRSAProvider@@3PEAXEA; hAlgorithm
0x180054962  test    rcx, rcx
0x180054965  jz      short loc_180054976
0x180054967  xor     edx, edx; dwFlags
0x180054969  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18005496f  mov     cs:?g_hRSAProvider@@3PEAXEA, rdi; void * g_hRSAProvider
0x180054976  mov     rcx, cs:?g_hDhSchannelProv@@3_KA; hProv
0x18005497d  test    rcx, rcx
0x180054980  jz      short loc_180054991
0x180054982  xor     edx, edx; dwFlags
0x180054984  call    cs:__imp_CryptReleaseContext
0x18005498a  mov     cs:?g_hDhSchannelProv@@3_KA, rdi; unsigned __int64 g_hDhSchannelProv
0x180054991  mov     dl, 1; Wait
0x180054993  lea     rcx, Resource; Resource
0x18005499a  call    cs:__imp_RtlAcquireResourceExclusive
0x1800549a0  mov     dl, 1; unsigned __int8
0x1800549a2  call    ?ClearCipherMill@CCipherMill@@AEAAXE@Z; CCipherMill::ClearCipherMill(uchar)
0x1800549a7  lea     rcx, Resource; Resource
0x1800549ae  call    cs:__imp_RtlReleaseResource
0x1800549b4  call    ?CleanupPeriodicCleanupHandler@CSslGlobals@@SAXXZ; CSslGlobals::CleanupPeriodicCleanupHandler(void)
0x1800549b9  call    ?CleanupCryptLocatorHandles@CSslGlobals@@SAXXZ; CSslGlobals::CleanupCryptLocatorHandles(void)
0x1800549be  call    ?CleanupCryptLocatorEvents@CSslGlobals@@SAXXZ; CSslGlobals::CleanupCryptLocatorEvents(void)
0x1800549c3  jmp     short loc_1800549CA
0x1800549c5  call    ?UnloadSslRegOptions@@YAXXZ; UnloadSslRegOptions(void)
0x1800549ca  cmp     cs:?s_IsTelemetryGloballyInitialized@CTelemetryContext@@1_NA, dil; bool CTelemetryContext::s_IsTelemetryGloballyInitialized
0x1800549d1  jz      short loc_1800549DF
0x1800549d3  mov     cs:?s_IsTelemetryGloballyInitialized@CTelemetryContext@@1_NA, dil; bool CTelemetryContext::s_IsTelemetryGloballyInitialized
0x1800549da  call    TlgUnregisterAggregateProvider
0x1800549df  mov     rcx, cs:?g_hMskeyprotect@@3PEAUHINSTANCE__@@EA; hLibModule
0x1800549e6  test    rcx, rcx
0x1800549e9  jz      short loc_180054A0D
0x1800549eb  mov     cs:?g_pKeyFileProtectSessionTicket@@3P6AKPEAEKPEBGPEAPEAEPEAK@ZEA, rdi; ulong (*g_pKeyFileProtectSessionTicket)(uchar *,ulong,ushort const *,uchar * *,ulong *)
0x1800549f2  mov     cs:?g_pKeyFileUnprotectSessionTicket@@3P6AKPEAEKPEBGPEAPEAEPEAK@ZEA, rdi; ulong (*g_pKeyFileUnprotectSessionTicket)(uchar *,ulong,ushort const *,uchar * *,ulong *)
0x1800549f9  call    cs:__imp_FreeLibrary
0x1800549ff  mov     cs:?g_hMskeyprotect@@3PEAUHINSTANCE__@@EA, rdi; HINSTANCE__ * g_hMskeyprotect
0x180054a06  mov     qword ptr cs:?g_InitOnceMskeyprotect@@3T_RTL_RUN_ONCE@@A, rdi; _RTL_RUN_ONCE g_InitOnceMskeyprotect ...
0x180054a0d  mov     rcx, cs:?g_pSslProvCacheRWLock@@3PEAU_RTL_RESOURCE@@EA; Resource
0x180054a14  test    rcx, rcx
0x180054a17  jz      short loc_180054A2C
0x180054a19  call    cs:__imp_RtlDeleteResource
0x180054a1f  mov     rcx, cs:?g_pSslProvCacheRWLock@@3PEAU_RTL_RESOURCE@@EA; hMem
0x180054a26  call    cs:__imp_LocalFree
0x180054a2c  cmp     cs:?g_cCachedPagedSslProvs@@3KA, edi; ulong g_cCachedPagedSslProvs
0x180054a32  mov     ebx, edi
0x180054a34  mov     cs:?g_pSslProvCacheRWLock@@3PEAU_RTL_RESOURCE@@EA, rdi; _RTL_RESOURCE * g_pSslProvCacheRWLock
0x180054a3b  jbe     short loc_180054A5C
0x180054a3d  lea     rdx, ?g_rgCachedPagedSslProvs@@3PAUCACHED_SSL_PROVIDER@@A; CACHED_SSL_PROVIDER near * g_rgCachedPagedSslProvs
0x180054a44  mov     ecx, ebx
0x180054a46  shl     rcx, 4
0x180054a4a  add     rcx, rdx; struct CACHED_SSL_PROVIDER *
0x180054a4d  call    ?DestroyCachedSslProv@@YAXPEAUCACHED_SSL_PROVIDER@@@Z; DestroyCachedSslProv(CACHED_SSL_PROVIDER *)
0x180054a52  inc     ebx
0x180054a54  cmp     ebx, cs:?g_cCachedPagedSslProvs@@3KA; ulong g_cCachedPagedSslProvs
0x180054a5a  jb      short loc_180054A3D
0x180054a5c  lea     rcx, ?m_InitCriticalSection@CSslGlobals@@2U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180054a63  mov     cs:?g_cCachedPagedSslProvs@@3KA, edi; ulong g_cCachedPagedSslProvs
0x180054a69  mov     cs:?m_bSchannelInitialized@CSslGlobals@@2HA, edi; int CSslGlobals::m_bSchannelInitialized
0x180054a6f  call    cs:__imp_RtlLeaveCriticalSection
0x180054a75  mov     rbx, [rsp+28h+arg_0]
0x180054a7a  mov     eax, 1
0x180054a7f  add     rsp, 20h
0x180054a83  pop     rdi
0x180054a84  retn
```
