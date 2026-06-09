# GlobalDataTerminate

- ea: `0x18016bf6c`
- end: `0x18016c3d1`
- name: `GlobalDataTerminate`
- size: `1125`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800d39b4`

## callees

- `0x180020fc4`
- `0x180027ec0`
- `0x1800b8714`
- `0x1800e70b4`
- `0x1800f20bc`
- `0x1801272fc`
- `0x1801368c4`
- `0x180137e10`
- `0x180140010`
- `0x180141ec8`
- `0x18014352c`
- `0x180158a70`
- `0x18015f638`
- `0x18015fe38`
- `0x18016bf6c`
- `0x18016d634`
- `0x18017e2b4`
- `0x180191b40`
- `0x1801b1974`
- `0x1801b19f8`
- `0x1801b1a3c`
- `0x1801e3c24`
- `0x1801e3c78`
- `0x1801ee010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18016c0ef`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18016c0ef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18016bffb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18016bffb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18016bfe9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18016bfe9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18016c267`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18016c289`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18016c267`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18016c289`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18016bfb8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18016bfb8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18016c2dc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18016c2dc`
- `ntdll!EtwEventUnregister` at `0x18016c239`
- `ntdll!EtwEventUnregister` at `0x18016c239`
- `HTTPAPI!HttpTerminate` at `0x18016c2c3`
- `HTTPAPI!HttpTerminate` at `0x18016c2c3`
- `WINHTTP!WinHttpCloseHandle` at `0x18016c1b0`
- `WINHTTP!WinHttpCloseHandle` at `0x18016c1b0`

## pseudocode

```c
void __fastcall GlobalDataTerminate(CHttpPolicyExtensionLoader *a1)
{
  unsigned int v1; // edx
  SECURITY_CACHE_LIST *v2; // rcx
  unsigned int i; // ebx

  if ( (BYTE2(xmmword_180266B60) & 4) != 0 )
    WPP_SF_(1042, 44, WPP_f3891ab5c3d93bfd7b4c17ad8322ed69_Traceguids);
  CHttpPolicyExtensionLoader::Unload(a1);
  if ( g_hWinInetXblExt )
  {
    g_pfnWinInetXblUninitialize();
    FreeLibrary(g_hWinInetXblExt);
    g_hWinInetXblExt = 0;
  }
  if ( g_pwcUserAndPassword )
  {
    PWC::Dereference(g_pwcUserAndPassword);
    g_pwcUserAndPassword = 0;
  }
  AuthFlush();
  EnterCriticalSection(&g_csAuth);
  AUTHCTX::UnloadAll();
  LeaveCriticalSection(&g_csAuth);
  UrlZonesDetach();
  if ( (xmmword_180266B60 & 8) != 0 )
    WPP_SF_(1027, 32, WPP_9a7b506b1d1c36ead396d6507984e889_Traceguids);
  if ( g_pDnsCache )
    CDnsCache::`scalar deleting destructor'((CDnsCache *)g_pDnsCache, v1);
  g_pDnsCache = 0;
  if ( (xmmword_180266B60 & 8) != 0 )
    WPP_SF_(1027, 33, WPP_9a7b506b1d1c36ead396d6507984e889_Traceguids);
  if ( CHstsManager::m_pHstsManager )
  {
    CHstsManager::`scalar deleting destructor'(CHstsManager::m_pHstsManager, v1);
    CHstsManager::m_pHstsManager = 0;
  }
  WxHeapFree<CSslCred *>(&lpvrgszMimeExclusionTable);
  WxHeapFree<_WX_AVL_TABLE>(&lpvrgdwMimeExclusionTableOfSizes);
  WxHeapFree<char>(&vszMimeExclusionList);
  vdwMimeExclusionTableCount = 0;
  WxHeapFree<CSslCred *>(&lpvrgszHeaderExclusionTable);
  WxHeapFree<char>(&vszHeaderExclusionList);
  vdwHeaderExclusionTableCount = 0;
  if ( (BYTE1(xmmword_180266B60) & 1) != 0 )
    WPP_SF_q(1032, 10, WPP_3d17f0a0b1de3313160355230d09edb7_Traceguids, &GlobalCertCache);
  SECURITY_CACHE_LIST::ClearList(v2);
  DeleteCriticalSection(&stru_180268068);
  if ( (BYTE1(xmmword_180266B60) & 1) != 0 )
    WPP_SF_(1032, 11, WPP_3d17f0a0b1de3313160355230d09edb7_Traceguids);
  if ( g_pEdpChangeCookie )
  {
    WxUnRegisterEdpChangeNotification();
    g_pEdpChangeCookie = 0;
  }
  if ( g_pWdagChangeCookie )
  {
    WxUnRegisterWdagChangeNotification();
    g_pWdagChangeCookie = 0;
  }
  if ( g_dwNetChangeCookie )
  {
    WxUnRegisterNetworkChangeNotification(g_dwNetChangeCookie);
    g_dwNetChangeCookie = 0;
  }
  if ( GlobalProxyInfo )
  {
    (*(void (__fastcall **)(struct IProxyResolver *))(*(_QWORD *)GlobalProxyInfo + 16LL))(GlobalProxyInfo);
    GlobalProxyInfo = 0;
  }
  if ( GlobalProxyList )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)GlobalProxyList + 16LL))(GlobalProxyList);
    GlobalProxyList = 0;
  }
  PurgeServerInfoList(1);
  GlobalUseImprovedConnectionLimits = 0;
  if ( GlobalWinHttpSession )
  {
    WinHttpCloseHandle(GlobalWinHttpSession);
    GlobalWinHttpSession = 0;
    GlobalWinHttpSessionInitOnce.Ptr = 0;
  }
  UnloadSecurity();
  if ( GlobalSslTokenBindingNegotiator )
  {
    WxHeapFree<CSslCred *>(&GlobalSslTokenBindingNegotiator);
    GlobalSslTokenBindingNegotiator = 0;
  }
  GlobalSslTokenBindingNegotiatorSize = 0;
  if ( dword_1802694EC )
  {
    TraceLoggingTerminate();
    dword_1802694EC = 0;
  }
  if ( g_bEtwInitialized )
  {
    McGenEventUnregister_EventUnregister(WININET_Context);
    McGenEventUnregister_EventUnregister(WININET_CAPTURE_Context);
    McGenEventUnregister_EventUnregister(WININET_PCA_Context);
    if ( g_fEtwCorrelationProviderInitialized )
    {
      EtwEventUnregister(Microsoft_Windows_Networking_CorrelationHandle);
      Microsoft_Windows_Networking_CorrelationHandle = 0;
      g_fEtwCorrelationProviderInitialized = 0;
    }
    g_bEtwInitialized = 0;
  }
  if ( g_pszCurrentUser )
  {
    HeapFree(g_hWxProcessHeap, 0, (LPVOID)g_pszCurrentUser);
    g_pszCurrentUser = 0;
  }
  if ( g_pszCurrentUserLowerCase )
  {
    HeapFree(g_hWxProcessHeap, 0, g_pszCurrentUserLowerCase);
    g_pszCurrentUserLowerCase = 0;
  }
  if ( (BYTE3(xmmword_180266B60) & 4) != 0 )
    WPP_SF_(1050, 35, WPP_0bbcb6fc992933018a736fcd53a9edfa_Traceguids);
  if ( g_ClientVTable )
  {
    HttpTerminate(1u, 0);
    g_ClientVTable = 0;
  }
  if ( g_QuicIo )
  {
    CloseThreadpoolIo(g_QuicIo);
    g_QuicIo = 0;
  }
  if ( GlobalInternetErrorRingBuffer )
  {
    WxFreeHeapEx(&GlobalInternetErrorRingBuffer);
    GlobalInternetErrorRingBuffer = 0;
  }
  if ( GlobalFsmErrorRingBuffer )
  {
    WxFreeHeapEx(&GlobalFsmErrorRingBuffer);
    GlobalFsmErrorRingBuffer = 0;
  }
  if ( GlobalResolveErrorRingBuffer )
  {
    WxFreeHeapEx(&GlobalResolveErrorRingBuffer);
    GlobalResolveErrorRingBuffer = 0;
  }
  if ( (BYTE1(xmmword_180266B60) & 0x40) != 0 )
    WPP_SF_(1038, 11, WPP_2de40998c5db34be4ac1b096b1e50e34_Traceguids);
  for ( i = 0; i < g_cPolicyCallbacks; ++i )
    FreePolicyCallbackEntry((struct _POLICY_CALLBACK_ENTRY **)&(&g_rgPolicyCallbacks)[i]);
  if ( (BYTE1(xmmword_180266B60) & 0x40) != 0 )
    WPP_SF_(1038, 12, WPP_2de40998c5db34be4ac1b096b1e50e34_Traceguids);
  GlobalDataInitialized = 0;
  if ( (BYTE2(xmmword_180266B60) & 4) != 0 )
    WPP_SF_(1042, 45, WPP_f3891ab5c3d93bfd7b4c17ad8322ed69_Traceguids);
}

```

## disassembly

```asm
0x18016bf6c  mov     [rsp+arg_0], rbx
0x18016bf71  push    rdi
0x18016bf72  sub     rsp, 20h
0x18016bf76  test    byte ptr cs:xmmword_180266B60+2, 4
0x18016bf7d  jz      short loc_18016BF95
0x18016bf7f  mov     edx, 2Ch ; ','
0x18016bf84  lea     r8, WPP_f3891ab5c3d93bfd7b4c17ad8322ed69_Traceguids
0x18016bf8b  mov     ecx, 412h
0x18016bf90  call    WPP_SF_
0x18016bf95  call    ?Unload@CHttpPolicyExtensionLoader@@QEAAXXZ; CHttpPolicyExtensionLoader::Unload(void)
0x18016bf9a  xor     edi, edi
0x18016bf9c  cmp     cs:?g_hWinInetXblExt@@3PEAUHINSTANCE__@@EA, rdi; HINSTANCE__ * g_hWinInetXblExt
0x18016bfa3  jz      short loc_18016BFC5
0x18016bfa5  mov     rax, cs:?g_pfnWinInetXblUninitialize@@3P6AXXZEA; void (*g_pfnWinInetXblUninitialize)(void)
0x18016bfac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016bfb1  mov     rcx, cs:?g_hWinInetXblExt@@3PEAUHINSTANCE__@@EA; hLibModule
0x18016bfb8  call    cs:__imp_FreeLibrary
0x18016bfbe  mov     cs:?g_hWinInetXblExt@@3PEAUHINSTANCE__@@EA, rdi; HINSTANCE__ * g_hWinInetXblExt
0x18016bfc5  mov     rcx, cs:?g_pwcUserAndPassword@@3PEAVPWC@@EA; this
0x18016bfcc  test    rcx, rcx
0x18016bfcf  jz      short loc_18016BFDD
0x18016bfd1  call    ?Dereference@PWC@@QEAAXXZ; PWC::Dereference(void)
0x18016bfd6  mov     cs:?g_pwcUserAndPassword@@3PEAVPWC@@EA, rdi; PWC * g_pwcUserAndPassword
0x18016bfdd  call    ?AuthFlush@@YAXXZ; AuthFlush(void)
0x18016bfe2  lea     rcx, ?g_csAuth@@3VWxCriticalSection@@A; lpCriticalSection
0x18016bfe9  call    cs:__imp_EnterCriticalSection
0x18016bfef  call    ?UnloadAll@AUTHCTX@@SAXXZ; AUTHCTX::UnloadAll(void)
0x18016bff4  lea     rcx, ?g_csAuth@@3VWxCriticalSection@@A; lpCriticalSection
0x18016bffb  call    cs:__imp_LeaveCriticalSection
0x18016c001  call    UrlZonesDetach
0x18016c006  test    byte ptr cs:xmmword_180266B60, 8
0x18016c00d  mov     ebx, 403h
0x18016c012  jz      short loc_18016C027
0x18016c014  mov     edx, 20h ; ' '
0x18016c019  lea     r8, WPP_9a7b506b1d1c36ead396d6507984e889_Traceguids
0x18016c020  mov     ecx, ebx
0x18016c022  call    WPP_SF_
0x18016c027  mov     rcx, cs:?g_pDnsCache@@3PEAVCDnsCache@@EA; this
0x18016c02e  test    rcx, rcx
0x18016c031  jz      short loc_18016C038
0x18016c033  call    ??_GCDnsCache@@QEAAPEAXI@Z; CDnsCache::`scalar deleting destructor'(uint)
0x18016c038  mov     cs:?g_pDnsCache@@3PEAVCDnsCache@@EA, rdi; CDnsCache * g_pDnsCache
0x18016c03f  test    byte ptr cs:xmmword_180266B60, 8
0x18016c046  jz      short loc_18016C05B
0x18016c048  mov     edx, 21h ; '!'
0x18016c04d  lea     r8, WPP_9a7b506b1d1c36ead396d6507984e889_Traceguids
0x18016c054  mov     ecx, ebx
0x18016c056  call    WPP_SF_
0x18016c05b  mov     rcx, cs:?m_pHstsManager@CHstsManager@@0PEAV1@EA; this
0x18016c062  test    rcx, rcx
0x18016c065  jz      short loc_18016C073
0x18016c067  call    ??_GCHstsManager@@AEAAPEAXI@Z; CHstsManager::`scalar deleting destructor'(uint)
0x18016c06c  mov     cs:?m_pHstsManager@CHstsManager@@0PEAV1@EA, rdi; CHstsManager * CHstsManager::m_pHstsManager
0x18016c073  lea     rcx, lpvrgszMimeExclusionTable
0x18016c07a  call    ??$WxHeapFree@PEAVCSslCred@@@@YAXPEAPEAPEAVCSslCred@@@Z; WxHeapFree<CSslCred *>(CSslCred * * *)
0x18016c07f  lea     rcx, lpvrgdwMimeExclusionTableOfSizes
0x18016c086  call    ??$WxHeapFree@U_WX_AVL_TABLE@@@@YAXPEAPEAU_WX_AVL_TABLE@@@Z; WxHeapFree<_WX_AVL_TABLE>(_WX_AVL_TABLE * *)
0x18016c08b  lea     rcx, vszMimeExclusionList
0x18016c092  call    ??$WxHeapFree@D@@YAXPEAPEAD@Z; WxHeapFree<char>(char * *)
0x18016c097  lea     rcx, lpvrgszHeaderExclusionTable
0x18016c09e  mov     cs:vdwMimeExclusionTableCount, edi
0x18016c0a4  call    ??$WxHeapFree@PEAVCSslCred@@@@YAXPEAPEAPEAVCSslCred@@@Z; WxHeapFree<CSslCred *>(CSslCred * * *)
0x18016c0a9  lea     rcx, vszHeaderExclusionList
0x18016c0b0  call    ??$WxHeapFree@D@@YAXPEAPEAD@Z; WxHeapFree<char>(char * *)
0x18016c0b5  mov     cs:vdwHeaderExclusionTableCount, edi
0x18016c0bb  test    byte ptr cs:xmmword_180266B60+1, 1
0x18016c0c2  mov     ebx, 408h
0x18016c0c7  jz      short loc_18016C0E3
0x18016c0c9  mov     edx, 0Ah
0x18016c0ce  lea     r9, GlobalCertCache
0x18016c0d5  mov     ecx, ebx
0x18016c0d7  lea     r8, WPP_3d17f0a0b1de3313160355230d09edb7_Traceguids
0x18016c0de  call    WPP_SF_q
0x18016c0e3  call    ?ClearList@SECURITY_CACHE_LIST@@QEAAXXZ; SECURITY_CACHE_LIST::ClearList(void)
0x18016c0e8  lea     rcx, stru_180268068; lpCriticalSection
0x18016c0ef  call    cs:__imp_DeleteCriticalSection
0x18016c0f5  test    byte ptr cs:xmmword_180266B60+1, 1
0x18016c0fc  jz      short loc_18016C111
0x18016c0fe  mov     edx, 0Bh
0x18016c103  lea     r8, WPP_3d17f0a0b1de3313160355230d09edb7_Traceguids
0x18016c10a  mov     ecx, ebx
0x18016c10c  call    WPP_SF_
0x18016c111  mov     rcx, cs:?g_pEdpChangeCookie@@3PEAXEA; void * g_pEdpChangeCookie
0x18016c118  test    rcx, rcx
0x18016c11b  jz      short loc_18016C129
0x18016c11d  call    WxUnRegisterEdpChangeNotification
0x18016c122  mov     cs:?g_pEdpChangeCookie@@3PEAXEA, rdi; void * g_pEdpChangeCookie
0x18016c129  mov     rcx, cs:?g_pWdagChangeCookie@@3PEAXEA; void * g_pWdagChangeCookie
0x18016c130  test    rcx, rcx
0x18016c133  jz      short loc_18016C141
0x18016c135  call    WxUnRegisterWdagChangeNotification
0x18016c13a  mov     cs:?g_pWdagChangeCookie@@3PEAXEA, rdi; void * g_pWdagChangeCookie
0x18016c141  mov     ecx, cs:?g_dwNetChangeCookie@@3KA; unsigned int
0x18016c147  test    ecx, ecx
0x18016c149  jz      short loc_18016C156
0x18016c14b  call    WxUnRegisterNetworkChangeNotification
0x18016c150  mov     cs:?g_dwNetChangeCookie@@3KA, edi; ulong g_dwNetChangeCookie
0x18016c156  mov     rcx, cs:GlobalProxyInfo
0x18016c15d  test    rcx, rcx
0x18016c160  jz      short loc_18016C175
0x18016c162  mov     rax, [rcx]
0x18016c165  mov     rax, [rax+10h]
0x18016c169  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016c16e  mov     cs:GlobalProxyInfo, rdi
0x18016c175  mov     rcx, cs:GlobalProxyList
0x18016c17c  test    rcx, rcx
0x18016c17f  jz      short loc_18016C194
0x18016c181  mov     rax, [rcx]
0x18016c184  mov     rax, [rax+10h]
0x18016c188  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016c18d  mov     cs:GlobalProxyList, rdi
0x18016c194  mov     ecx, 1; int
0x18016c199  call    ?PurgeServerInfoList@@YAXH@Z; PurgeServerInfoList(int)
0x18016c19e  mov     rcx, cs:GlobalWinHttpSession; hInternet
0x18016c1a5  mov     cs:GlobalUseImprovedConnectionLimits, edi
0x18016c1ab  test    rcx, rcx
0x18016c1ae  jz      short loc_18016C1C4
0x18016c1b0  call    cs:__imp_WinHttpCloseHandle
0x18016c1b6  mov     cs:GlobalWinHttpSession, rdi
0x18016c1bd  mov     qword ptr cs:?GlobalWinHttpSessionInitOnce@@3T_RTL_RUN_ONCE@@A, rdi; _RTL_RUN_ONCE GlobalWinHttpSessionInitOnce ...
0x18016c1c4  call    UnloadSecurity
0x18016c1c9  cmp     cs:GlobalSslTokenBindingNegotiator, rdi
0x18016c1d0  jz      short loc_18016C1E5
0x18016c1d2  lea     rcx, GlobalSslTokenBindingNegotiator
0x18016c1d9  call    ??$WxHeapFree@PEAVCSslCred@@@@YAXPEAPEAPEAVCSslCred@@@Z; WxHeapFree<CSslCred *>(CSslCred * * *)
0x18016c1de  mov     cs:GlobalSslTokenBindingNegotiator, rdi
0x18016c1e5  cmp     cs:dword_1802694EC, edi
0x18016c1eb  mov     cs:GlobalSslTokenBindingNegotiatorSize, edi
0x18016c1f1  jz      short loc_18016C1FE
0x18016c1f3  call    ?TraceLoggingTerminate@@YAXXZ; TraceLoggingTerminate(void)
0x18016c1f8  mov     cs:dword_1802694EC, edi
0x18016c1fe  cmp     cs:?g_bEtwInitialized@@3HA, edi; int g_bEtwInitialized
0x18016c204  jz      short loc_18016C252
0x18016c206  lea     rcx, WININET_Context
0x18016c20d  call    McGenEventUnregister_EventUnregister
0x18016c212  lea     rcx, WININET_CAPTURE_Context
0x18016c219  call    McGenEventUnregister_EventUnregister
0x18016c21e  lea     rcx, WININET_PCA_Context
0x18016c225  call    McGenEventUnregister_EventUnregister
0x18016c22a  cmp     cs:?g_fEtwCorrelationProviderInitialized@@3HA, edi; int g_fEtwCorrelationProviderInitialized
0x18016c230  jz      short loc_18016C24C
0x18016c232  mov     rcx, cs:Microsoft_Windows_Networking_CorrelationHandle
0x18016c239  call    cs:__imp_EtwEventUnregister
0x18016c23f  mov     cs:Microsoft_Windows_Networking_CorrelationHandle, rdi
0x18016c246  mov     cs:?g_fEtwCorrelationProviderInitialized@@3HA, edi; int g_fEtwCorrelationProviderInitialized
0x18016c24c  mov     cs:?g_bEtwInitialized@@3HA, edi; int g_bEtwInitialized
0x18016c252  mov     r8, cs:g_pszCurrentUser; lpMem
0x18016c259  test    r8, r8
0x18016c25c  jz      short loc_18016C274
0x18016c25e  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x18016c265  xor     edx, edx; dwFlags
0x18016c267  call    cs:__imp_HeapFree
0x18016c26d  mov     cs:g_pszCurrentUser, rdi
0x18016c274  mov     r8, cs:g_pszCurrentUserLowerCase; lpMem
0x18016c27b  test    r8, r8
0x18016c27e  jz      short loc_18016C296
0x18016c280  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x18016c287  xor     edx, edx; dwFlags
0x18016c289  call    cs:__imp_HeapFree
0x18016c28f  mov     cs:g_pszCurrentUserLowerCase, rdi
0x18016c296  test    byte ptr cs:xmmword_180266B60+3, 4
0x18016c29d  jz      short loc_18016C2B5
0x18016c29f  mov     edx, 23h ; '#'
0x18016c2a4  lea     r8, WPP_0bbcb6fc992933018a736fcd53a9edfa_Traceguids
0x18016c2ab  mov     ecx, 41Ah
0x18016c2b0  call    WPP_SF_
0x18016c2b5  cmp     cs:?g_ClientVTable@@3PEAU_HTTP_CLIENT_VTABLE@@EA, rdi; _HTTP_CLIENT_VTABLE * g_ClientVTable
0x18016c2bc  jz      short loc_18016C2D0
0x18016c2be  xor     edx, edx; pReserved
0x18016c2c0  lea     ecx, [rdx+1]; Flags
0x18016c2c3  call    cs:__imp_HttpTerminate
0x18016c2c9  mov     cs:?g_ClientVTable@@3PEAU_HTTP_CLIENT_VTABLE@@EA, rdi; _HTTP_CLIENT_VTABLE * g_ClientVTable
0x18016c2d0  mov     rcx, cs:?g_QuicIo@@3PEAU_TP_IO@@EA; pio
0x18016c2d7  test    rcx, rcx
0x18016c2da  jz      short loc_18016C2E9
0x18016c2dc  call    cs:__imp_CloseThreadpoolIo
0x18016c2e2  mov     cs:?g_QuicIo@@3PEAU_TP_IO@@EA, rdi; _TP_IO * g_QuicIo
0x18016c2e9  cmp     cs:GlobalInternetErrorRingBuffer, rdi
0x18016c2f0  jz      short loc_18016C305
0x18016c2f2  lea     rcx, GlobalInternetErrorRingBuffer
0x18016c2f9  call    WxFreeHeapEx
0x18016c2fe  mov     cs:GlobalInternetErrorRingBuffer, rdi
0x18016c305  cmp     cs:GlobalFsmErrorRingBuffer, rdi
0x18016c30c  jz      short loc_18016C321
0x18016c30e  lea     rcx, GlobalFsmErrorRingBuffer
0x18016c315  call    WxFreeHeapEx
0x18016c31a  mov     cs:GlobalFsmErrorRingBuffer, rdi
0x18016c321  cmp     cs:GlobalResolveErrorRingBuffer, rdi
0x18016c328  jz      short loc_18016C33D
0x18016c32a  lea     rcx, GlobalResolveErrorRingBuffer
0x18016c331  call    WxFreeHeapEx
0x18016c336  mov     cs:GlobalResolveErrorRingBuffer, rdi
0x18016c33d  test    byte ptr cs:xmmword_180266B60+1, 40h
0x18016c344  jz      short loc_18016C35C
0x18016c346  mov     edx, 0Bh
0x18016c34b  lea     r8, WPP_2de40998c5db34be4ac1b096b1e50e34_Traceguids
0x18016c352  mov     ecx, 40Eh
0x18016c357  call    WPP_SF_
0x18016c35c  cmp     cs:?g_cPolicyCallbacks@@3KA, edi; ulong g_cPolicyCallbacks
0x18016c362  mov     ebx, edi
0x18016c364  jbe     short loc_18016C382
0x18016c366  mov     eax, ebx
0x18016c368  lea     rdx, ?g_rgPolicyCallbacks@@3PAPEAU_POLICY_CALLBACK_ENTRY@@A; _POLICY_CALLBACK_ENTRY * near * g_rgPolicyCallbacks
0x18016c36f  lea     rcx, [rdx+rax*8]; struct _POLICY_CALLBACK_ENTRY **
0x18016c373  call    ?FreePolicyCallbackEntry@@YAXPEAPEAU_POLICY_CALLBACK_ENTRY@@@Z; FreePolicyCallbackEntry(_POLICY_CALLBACK_ENTRY * *)
0x18016c378  inc     ebx
0x18016c37a  cmp     ebx, cs:?g_cPolicyCallbacks@@3KA; ulong g_cPolicyCallbacks
0x18016c380  jb      short loc_18016C366
0x18016c382  test    byte ptr cs:xmmword_180266B60+1, 40h
0x18016c389  jz      short loc_18016C3A1
0x18016c38b  mov     edx, 0Ch
0x18016c390  lea     r8, WPP_2de40998c5db34be4ac1b096b1e50e34_Traceguids
0x18016c397  mov     ecx, 40Eh
0x18016c39c  call    WPP_SF_
0x18016c3a1  mov     cs:GlobalDataInitialized, edi
0x18016c3a7  test    byte ptr cs:xmmword_180266B60+2, 4
0x18016c3ae  jz      short loc_18016C3C6
0x18016c3b0  mov     edx, 2Dh ; '-'
0x18016c3b5  lea     r8, WPP_f3891ab5c3d93bfd7b4c17ad8322ed69_Traceguids
0x18016c3bc  mov     ecx, 412h
0x18016c3c1  call    WPP_SF_
0x18016c3c6  mov     rbx, [rsp+28h+arg_0]
0x18016c3cb  add     rsp, 20h
0x18016c3cf  pop     rdi
0x18016c3d0  retn
```
