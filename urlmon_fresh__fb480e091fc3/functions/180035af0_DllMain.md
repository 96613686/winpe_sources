# DllMain

- ea: `0x180035af0`
- end: `0x180036005`
- name: `DllMain`
- size: `1301`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800a9084`

## callees

- `0x18001db50`
- `0x180033fa4`
- `0x180035af0`
- `0x180036010`
- `0x1800364a0`
- `0x1800369c8`
- `0x180036a2c`
- `0x180036a64`
- `0x180036b2c`
- `0x180036b94`
- `0x180036c08`
- `0x180036c2c`
- `0x180036c64`
- `0x180036cb0`
- `0x180036cd8`
- `0x180036ec4`
- `0x1800376a8`
- `0x180037828`
- `0x180037874`
- `0x180037af8`
- `0x180037b90`
- `0x180037c94`
- `0x18008d464`
- `0x180129010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180035bf6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180035c13`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180035bf6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180035c13`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180035bd7`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180035bd7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180035d61`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180035d97`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180035db0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180035d61`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180035d97`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180035db0`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x180035d18`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x180035d18`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x180035e12`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x180035e12`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180035e2f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180035e2f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180035df6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180035df6`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180035cf0`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180035cf0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035d39`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035d70`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035ebe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035f25`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035f84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035f9c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035fe3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035d39`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035d70`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035ebe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035f25`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035f84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035f9c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035fe3`
- `WININET!InternetCloseHandle` at `0x180035f4d`
- `WININET!InternetCloseHandle` at `0x180035f4d`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  CMediaTypeHolder *v7; // rdi
  int v8; // edi
  int v9; // ebx
  bool v10; // bp
  __int64 v11; // r14
  CFeatureCache *v12; // rbp
  DWORD v13; // eax
  CMediaTypeHolder *v14; // rax
  unsigned int v15; // ecx
  CMediaTypeHolder *v16; // rsi
  LPVOID Value; // [rsp+58h] [rbp+20h] BYREF

  if ( !fdwReason )
  {
    TraceLoggingUnregister_EventUnregister(&dword_180166000, 0, lpvReserved, 0);
    if ( lpvReserved )
    {
      v10 = 1;
    }
    else
    {
      v10 = 0;
      if ( g_pszUserAgentStringCustom )
      {
        CoTaskMemFree((LPVOID)g_pszUserAgentStringCustom);
        g_pszUserAgentStringCustom = 0;
      }
      g_pcszUserAgentString = 0;
      if ( g_pwszLoginUrl )
      {
        CoTaskMemFree(g_pwszLoginUrl);
        g_pwszLoginUrl = 0;
      }
      if ( g_pwszAadLoginUrls )
      {
        CoTaskMemFree(g_pwszAadLoginUrls);
        g_pwszAadLoginUrls = 0;
      }
    }
    if ( g_pInternetSecurityManager )
    {
      ((void (__fastcall *)(IInternetSecurityManager *))g_pInternetSecurityManager->lpVtbl->Release)(g_pInternetSecurityManager);
      g_pInternetSecurityManager = 0;
    }
    if ( g_pInternetSecurityManagerEx2 )
    {
      ((void (__fastcall *)(struct IInternetSecurityManagerEx2 *))g_pInternetSecurityManagerEx2->lpVtbl->Release)(g_pInternetSecurityManagerEx2);
      g_pInternetSecurityManagerEx2 = 0;
    }
    if ( !v10 )
    {
      RemovePermanentInternetSecurityManager(1);
      RemovePermanentUrlRedirectionPolicyManager(1);
    }
    v11 = _InterlockedExchange64((volatile __int64 *)&qword_18016B808, 0);
    if ( v11 )
    {
      *(_QWORD *)v11 = 0;
      *(_BYTE *)(v11 + 16) = 1;
      *(_QWORD *)(v11 + 8) = 0;
      CIEApplicationAssociation::~CIEApplicationAssociation((CIEApplicationAssociation *)v11);
      CoTaskMemFree((LPVOID)v11);
    }
    if ( !v10 && g_pszUAInfoString )
    {
      CoTaskMemFree((LPVOID)g_pszUAInfoString);
      g_pszUAInfoString = 0;
    }
    if ( g_bInit )
      ZonesUnInit(v10);
    if ( g_pEFmtETC )
      ((void (__fastcall *)(IEnumFORMATETC *))g_pEFmtETC->lpVtbl->Release)(g_pEFmtETC);
    if ( v10 )
    {
      McGenEventUnregister_EventUnregister();
    }
    else
    {
      v12 = g_pFeatureCache;
      if ( g_pFeatureCache )
      {
        DeleteCriticalSection((LPCRITICAL_SECTION)((char *)g_pFeatureCache + 16));
        CoTaskMemFree(v12);
      }
      g_pFeatureCache = 0;
      DeinitBrowserMode();
      if ( g_bInitVersionManager )
      {
        DeleteCriticalSection(&g_critSectVersionManager);
        g_bInitVersionManager = 0;
      }
      DeleteCriticalSection(&g_csDll);
      McGenEventUnregister_EventUnregister();
      if ( g_pAxCompatCache )
      {
        (**(void (__fastcall ***)(struct CCompatCacheList *, __int64))g_pAxCompatCache)(g_pAxCompatCache, 1);
        g_pAxCompatCache = 0;
      }
    }
    CleanupAllThreadsOnProcessDetach(lpvReserved != 0);
    InitOnceExecuteOnce(&stru_18016BB00, InitOnceDeviceFamily, 0, 0);
    if ( !byte_18016AF34 || !lpvReserved )
    {
      UnregisterUrlMkWndClass();
      if ( !lpvReserved )
      {
        v16 = g_pCMHolder;
        if ( g_pCMHolder )
        {
          CMediaTypeHolder::~CMediaTypeHolder(g_pCMHolder);
          CoTaskMemFree(v16);
          g_pCMHolder = 0;
        }
        DeleteOInetSession(v15);
        if ( g_hSession )
        {
          InternetCloseHandle(g_hSession);
          g_hSession = 0;
        }
      }
    }
    TlsFree(gTlsIndex);
    goto LABEL_8;
  }
  if ( fdwReason != 1 )
  {
    if ( fdwReason - 2 >= 2 )
      return 1;
    if ( fdwReason == 1 )
    {
      v7 = 0;
      g_hInst = hinstDLL;
      g_hHeap = GetProcessHeap();
      if ( !g_hHeap
        || (v13 = TlsAlloc(), gTlsIndex = v13, v13 == -1)
        || (Value = TlsGetValue(v13)) == 0 && (int)CUrlMkTls::TLSAllocData((CUrlMkTls *)&Value) < 0 )
      {
LABEL_9:
        if ( !fdwReason )
          SHFusionUninitialize();
        return (int)v7;
      }
      v14 = (CMediaTypeHolder *)operator new(0x18u);
      if ( v14 )
        v7 = CMediaTypeHolder::CMediaTypeHolder(v14);
      g_pCMHolder = v7;
    }
    else if ( fdwReason == 3 )
    {
      CleanupCurrentThread(1);
    }
LABEL_8:
    LODWORD(v7) = 1;
    goto LABEL_9;
  }
  qword_18016AF40 = hinstDLL;
  dword_1801690BC = 123;
  g_hinstMUI = hinstDLL;
  v8 = 0;
  g_pszUAInfoString = GetUAInfoString();
  g_fFirstNavigationFlushed = 0;
  g_fClientCertSuppliedInProcess = 0;
  if ( (int)ConstructFeatureCache() < 0 )
    v9 = 0;
  else
    v9 = TlsDllMain(hinstDLL, 1, lpvReserved);
  McGenEventRegister_EventRegister();
  TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_180166000);
  LOBYTE(v8) = InitializeCriticalSectionEx(&g_critSectBM, 0, 0);
  g_bInitBM = v8;
  InitializeCriticalSection(&g_critSectVersionManager);
  g_bInitVersionManager = 1;
  InitializeCriticalSection(&g_csDll);
  CreateAXCompatCache();
  return v9;
}

```

## disassembly

```asm
0x180035af0  mov     [rsp+arg_8], rbx
0x180035af5  push    rbp
0x180035af6  push    rsi
0x180035af7  push    rdi
0x180035af8  sub     rsp, 20h
0x180035afc  mov     rsi, r8
0x180035aff  mov     ebx, edx
0x180035b01  mov     rbp, rcx
0x180035b04  mov     r9d, edx
0x180035b07  test    edx, edx
0x180035b09  jz      loc_180035C3E
0x180035b0f  sub     r9d, 1
0x180035b13  jz      short loc_180035B69
0x180035b15  sub     r9d, 1
0x180035b19  jz      short loc_180035B34
0x180035b1b  cmp     r9d, 1
0x180035b1f  jz      short loc_180035B34
0x180035b21  mov     eax, 1
0x180035b26  mov     rbx, [rsp+38h+arg_8]
0x180035b2b  add     rsp, 20h
0x180035b2f  pop     rdi
0x180035b30  pop     rsi
0x180035b31  pop     rbp
0x180035b32  retn
0x180035b34  mov     eax, ebx
0x180035b36  test    ebx, ebx
0x180035b38  jz      loc_180035E7D
0x180035b3e  sub     eax, 1
0x180035b41  jz      loc_180035DED
0x180035b47  cmp     eax, 2
0x180035b4a  jz      short loc_180035B5D
0x180035b4c  mov     edi, 1
0x180035b51  test    ebx, ebx
0x180035b53  jz      loc_180035C34
0x180035b59  mov     eax, edi
0x180035b5b  jmp     short loc_180035B26
0x180035b5d  mov     ecx, 1; int
0x180035b62  call    ?CleanupCurrentThread@@YAXH@Z; CleanupCurrentThread(int)
0x180035b67  jmp     short loc_180035B4C
0x180035b69  mov     cs:qword_18016AF40, rbp
0x180035b70  mov     cs:dword_1801690BC, 7Bh ; '{'
0x180035b7a  mov     cs:g_hinstMUI, rbp
0x180035b81  call    ?GetUAInfoString@@YAPEADXZ; GetUAInfoString(void)
0x180035b86  xor     edi, edi
0x180035b88  mov     cs:?g_pszUAInfoString@@3PEADEA, rax; char * g_pszUAInfoString
0x180035b8f  mov     cs:?g_fFirstNavigationFlushed@@3HA, edi; int g_fFirstNavigationFlushed
0x180035b95  mov     cs:?g_fClientCertSuppliedInProcess@@3HA, edi; int g_fClientCertSuppliedInProcess
0x180035b9b  call    ConstructFeatureCache
0x180035ba0  test    eax, eax
0x180035ba2  js      loc_180035F7D
0x180035ba8  mov     r8, rsi
0x180035bab  mov     edx, 1
0x180035bb0  mov     rcx, rbp
0x180035bb3  call    TlsDllMain
0x180035bb8  mov     ebx, eax
0x180035bba  call    McGenEventRegister_EventRegister
0x180035bbf  lea     rcx, dword_180166000; CallbackContext
0x180035bc6  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180035bcb  xor     r8d, r8d; Flags
0x180035bce  lea     rcx, ?g_critSectBM@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180035bd5  xor     edx, edx; dwSpinCount
0x180035bd7  call    cs:__imp_InitializeCriticalSectionEx
0x180035bde  nop     dword ptr [rax+rax+00h]
0x180035be3  test    eax, eax
0x180035be5  lea     rcx, ?g_critSectVersionManager@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180035bec  setnz   dil
0x180035bf0  mov     cs:?g_bInitBM@@3HA, edi; int g_bInitBM
0x180035bf6  call    cs:__imp_InitializeCriticalSection
0x180035bfd  nop     dword ptr [rax+rax+00h]
0x180035c02  lea     rcx, ?g_csDll@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180035c09  mov     cs:?g_bInitVersionManager@@3HA, 1; int g_bInitVersionManager
0x180035c13  call    cs:__imp_InitializeCriticalSection
0x180035c1a  nop     dword ptr [rax+rax+00h]
0x180035c1f  call    ?CreateAXCompatCache@@YAXXZ; CreateAXCompatCache(void)
0x180035c24  mov     eax, ebx
0x180035c26  mov     rbx, [rsp+38h+arg_8]
0x180035c2b  add     rsp, 20h
0x180035c2f  pop     rdi
0x180035c30  pop     rsi
0x180035c31  pop     rbp
0x180035c32  retn
0x180035c34  call    SHFusionUninitialize
0x180035c39  jmp     loc_180035B59
0x180035c3e  lea     rcx, dword_180166000
0x180035c45  mov     [rsp+38h+arg_0], r14
0x180035c4a  call    TraceLoggingUnregister_EventUnregister
0x180035c4f  xor     edi, edi
0x180035c51  test    rsi, rsi
0x180035c54  jz      loc_180035E84
0x180035c5a  mov     bpl, 1
0x180035c5d  mov     rcx, cs:?g_pInternetSecurityManager@@3PEAUIInternetSecurityManager@@EA; IInternetSecurityManager * g_pInternetSecurityManager
0x180035c64  test    rcx, rcx
0x180035c67  jnz     loc_180035F65
0x180035c6d  mov     rcx, cs:?g_pInternetSecurityManagerEx2@@3PEAUIInternetSecurityManagerEx2@@EA; IInternetSecurityManagerEx2 * g_pInternetSecurityManagerEx2
0x180035c74  test    rcx, rcx
0x180035c77  jnz     loc_180035FB4
0x180035c7d  test    bpl, bpl
0x180035c80  jz      loc_180035EED
0x180035c86  mov     r14, rdi
0x180035c89  xchg    r14, cs:qword_18016B808
0x180035c90  test    r14, r14
0x180035c93  jnz     loc_180035FCC
0x180035c99  mov     r14, [rsp+38h+arg_0]
0x180035c9e  test    bpl, bpl
0x180035ca1  jz      loc_180035D29
0x180035ca7  cmp     cs:?g_bInit@@3HA, edi; int g_bInit
0x180035cad  jnz     loc_180035E6F
0x180035cb3  mov     rcx, cs:?g_pEFmtETC@@3PEAUIEnumFORMATETC@@EA; IEnumFORMATETC * g_pEFmtETC
0x180035cba  test    rcx, rcx
0x180035cbd  jnz     loc_180035FF4
0x180035cc3  test    bpl, bpl
0x180035cc6  jz      loc_180035D51
0x180035ccc  call    McGenEventUnregister_EventUnregister
0x180035cd1  test    rsi, rsi
0x180035cd4  setnz   cl; bool
0x180035cd7  call    ?CleanupAllThreadsOnProcessDetach@@YAX_N@Z; CleanupAllThreadsOnProcessDetach(bool)
0x180035cdc  xor     r9d, r9d; Context
0x180035cdf  lea     rdx, ?InitOnceDeviceFamily@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180035ce6  xor     r8d, r8d; Parameter
0x180035ce9  lea     rcx, stru_18016BB00; InitOnce
0x180035cf0  call    cs:__imp_InitOnceExecuteOnce
0x180035cf7  nop     dword ptr [rax+rax+00h]
0x180035cfc  cmp     cs:byte_18016AF34, 0
0x180035d03  jz      loc_180035F00
0x180035d09  test    rsi, rsi
0x180035d0c  jz      loc_180035F00
0x180035d12  mov     ecx, cs:?gTlsIndex@@3KA; dwTlsIndex
0x180035d18  call    cs:__imp_TlsFree
0x180035d1f  nop     dword ptr [rax+rax+00h]
0x180035d24  jmp     loc_180035B4C
0x180035d29  mov     rcx, cs:?g_pszUAInfoString@@3PEADEA; pv
0x180035d30  test    rcx, rcx
0x180035d33  jz      loc_180035CA7
0x180035d39  call    cs:__imp_CoTaskMemFree
0x180035d40  nop     dword ptr [rax+rax+00h]
0x180035d45  mov     cs:?g_pszUAInfoString@@3PEADEA, rdi; char * g_pszUAInfoString
0x180035d4c  jmp     loc_180035CA7
0x180035d51  mov     rbp, cs:?g_pFeatureCache@@3PEAVCFeatureCache@@EA; CFeatureCache * g_pFeatureCache
0x180035d58  test    rbp, rbp
0x180035d5b  jz      short loc_180035D7C
0x180035d5d  lea     rcx, [rbp+10h]; lpCriticalSection
0x180035d61  call    cs:__imp_DeleteCriticalSection
0x180035d68  nop     dword ptr [rax+rax+00h]
0x180035d6d  mov     rcx, rbp; pv
0x180035d70  call    cs:__imp_CoTaskMemFree
0x180035d77  nop     dword ptr [rax+rax+00h]
0x180035d7c  mov     cs:?g_pFeatureCache@@3PEAVCFeatureCache@@EA, rdi; CFeatureCache * g_pFeatureCache
0x180035d83  call    ?DeinitBrowserMode@@YAXXZ; DeinitBrowserMode(void)
0x180035d88  cmp     cs:?g_bInitVersionManager@@3HA, edi; int g_bInitVersionManager
0x180035d8e  jz      short loc_180035DA9
0x180035d90  lea     rcx, ?g_critSectVersionManager@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180035d97  call    cs:__imp_DeleteCriticalSection
0x180035d9e  nop     dword ptr [rax+rax+00h]
0x180035da3  mov     cs:?g_bInitVersionManager@@3HA, edi; int g_bInitVersionManager
0x180035da9  lea     rcx, ?g_csDll@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180035db0  call    cs:__imp_DeleteCriticalSection
0x180035db7  nop     dword ptr [rax+rax+00h]
0x180035dbc  call    McGenEventUnregister_EventUnregister
0x180035dc1  mov     rcx, cs:?g_pAxCompatCache@@3PEAVCCompatCacheList@@EA; CCompatCacheList * g_pAxCompatCache
0x180035dc8  test    rcx, rcx
0x180035dcb  jz      loc_180035CD1
0x180035dd1  mov     rax, [rcx]
0x180035dd4  mov     edx, 1
0x180035dd9  mov     rax, [rax]
0x180035ddc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035de1  mov     cs:?g_pAxCompatCache@@3PEAVCCompatCacheList@@EA, rdi; CCompatCacheList * g_pAxCompatCache
0x180035de8  jmp     loc_180035CD1
0x180035ded  xor     edi, edi
0x180035def  mov     cs:?g_hInst@@3PEAUHINSTANCE__@@EA, rbp; HINSTANCE__ * g_hInst
0x180035df6  call    cs:__imp_GetProcessHeap
0x180035dfd  nop     dword ptr [rax+rax+00h]
0x180035e02  mov     cs:?g_hHeap@@3PEAXEA, rax; void * g_hHeap
0x180035e09  test    rax, rax
0x180035e0c  jz      loc_180035B51
0x180035e12  call    cs:__imp_TlsAlloc
0x180035e19  nop     dword ptr [rax+rax+00h]
0x180035e1e  mov     cs:?gTlsIndex@@3KA, eax; ulong gTlsIndex
0x180035e24  cmp     eax, 0FFFFFFFFh
0x180035e27  jz      loc_180035B51
0x180035e2d  mov     ecx, eax; dwTlsIndex
0x180035e2f  call    cs:__imp_TlsGetValue
0x180035e36  nop     dword ptr [rax+rax+00h]
0x180035e3b  mov     [rsp+38h+arg_18], rax
0x180035e40  test    rax, rax
0x180035e43  jz      loc_180035ED6
0x180035e49  mov     ecx, 18h; Size
0x180035e4e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180035e53  test    rax, rax
0x180035e56  jz      short loc_180035E63
0x180035e58  mov     rcx, rax; this
0x180035e5b  call    ??0CMediaTypeHolder@@QEAA@XZ; CMediaTypeHolder::CMediaTypeHolder(void)
0x180035e60  mov     rdi, rax
0x180035e63  mov     cs:?g_pCMHolder@@3PEAVCMediaTypeHolder@@EA, rdi; CMediaTypeHolder * g_pCMHolder
0x180035e6a  jmp     loc_180035B4C
0x180035e6f  movzx   ecx, bpl; bool
0x180035e73  call    ?ZonesUnInit@@YAX_N@Z; ZonesUnInit(bool)
0x180035e78  jmp     loc_180035CB3
0x180035e7d  xor     edi, edi
0x180035e7f  jmp     loc_180035CD1
0x180035e84  mov     rcx, cs:?g_pszUserAgentStringCustom@@3PEADEA; pv
0x180035e8b  xor     bpl, bpl
0x180035e8e  test    rcx, rcx
0x180035e91  jnz     loc_180035F84
0x180035e97  mov     rcx, cs:?g_pwszLoginUrl@@3PEAGEA; pv
0x180035e9e  mov     cs:?g_pcszUserAgentString@@3PEBDEB, rdi; char const * const g_pcszUserAgentString
0x180035ea5  test    rcx, rcx
0x180035ea8  jnz     loc_180035F9C
0x180035eae  mov     rcx, cs:?g_pwszAadLoginUrls@@3PEAGEA; pv
0x180035eb5  test    rcx, rcx
0x180035eb8  jz      loc_180035C5D
0x180035ebe  call    cs:__imp_CoTaskMemFree
0x180035ec5  nop     dword ptr [rax+rax+00h]
0x180035eca  mov     cs:?g_pwszAadLoginUrls@@3PEAGEA, rdi; ushort * g_pwszAadLoginUrls
0x180035ed1  jmp     loc_180035C5D
0x180035ed6  lea     rcx, [rsp+38h+arg_18]; this
0x180035edb  call    ?TLSAllocData@CUrlMkTls@@AEAAJXZ; CUrlMkTls::TLSAllocData(void)
0x180035ee0  test    eax, eax
0x180035ee2  jns     loc_180035E49
0x180035ee8  jmp     loc_180035B51
0x180035eed  mov     cl, 1; bool
0x180035eef  call    ?RemovePermanentInternetSecurityManager@@YA_N_N@Z; RemovePermanentInternetSecurityManager(bool)
0x180035ef4  mov     cl, 1; bool
0x180035ef6  call    ?RemovePermanentUrlRedirectionPolicyManager@@YA_N_N@Z; RemovePermanentUrlRedirectionPolicyManager(bool)
0x180035efb  jmp     loc_180035C86
0x180035f00  call    ?UnregisterUrlMkWndClass@@YAHXZ; UnregisterUrlMkWndClass(void)
0x180035f05  test    rsi, rsi
0x180035f08  jnz     loc_180035D12
0x180035f0e  mov     rsi, cs:?g_pCMHolder@@3PEAVCMediaTypeHolder@@EA; CMediaTypeHolder * g_pCMHolder
0x180035f15  test    rsi, rsi
0x180035f18  jz      short loc_180035F38
0x180035f1a  mov     rcx, rsi; this
0x180035f1d  call    ??1CMediaTypeHolder@@QEAA@XZ; CMediaTypeHolder::~CMediaTypeHolder(void)
0x180035f22  mov     rcx, rsi; pv
0x180035f25  call    cs:__imp_CoTaskMemFree
0x180035f2c  nop     dword ptr [rax+rax+00h]
0x180035f31  mov     cs:?g_pCMHolder@@3PEAVCMediaTypeHolder@@EA, rdi; CMediaTypeHolder * g_pCMHolder
0x180035f38  call    ?DeleteOInetSession@@YAJK@Z; DeleteOInetSession(ulong)
0x180035f3d  mov     rcx, cs:?g_hSession@@3PEAXEA; hInternet
0x180035f44  test    rcx, rcx
0x180035f47  jz      loc_180035D12
0x180035f4d  call    cs:__imp_InternetCloseHandle
0x180035f54  nop     dword ptr [rax+rax+00h]
0x180035f59  mov     cs:?g_hSession@@3PEAXEA, rdi; void * g_hSession
0x180035f60  jmp     loc_180035D12
0x180035f65  mov     rax, [rcx]
0x180035f68  mov     rax, [rax+10h]
0x180035f6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035f71  mov     cs:?g_pInternetSecurityManager@@3PEAUIInternetSecurityManager@@EA, rdi; IInternetSecurityManager * g_pInternetSecurityManager
0x180035f78  jmp     loc_180035C6D
0x180035f7d  mov     ebx, edi
0x180035f7f  jmp     loc_180035BBA
0x180035f84  call    cs:__imp_CoTaskMemFree
0x180035f8b  nop     dword ptr [rax+rax+00h]
0x180035f90  mov     cs:?g_pszUserAgentStringCustom@@3PEADEA, rdi; char * g_pszUserAgentStringCustom
0x180035f97  jmp     loc_180035E97
0x180035f9c  call    cs:__imp_CoTaskMemFree
0x180035fa3  nop     dword ptr [rax+rax+00h]
0x180035fa8  mov     cs:?g_pwszLoginUrl@@3PEAGEA, rdi; ushort * g_pwszLoginUrl
0x180035faf  jmp     loc_180035EAE
0x180035fb4  mov     rax, [rcx]
0x180035fb7  mov     rax, [rax+10h]
0x180035fbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035fc0  mov     cs:?g_pInternetSecurityManagerEx2@@3PEAUIInternetSecurityManagerEx2@@EA, rdi; IInternetSecurityManagerEx2 * g_pInternetSecurityManagerEx2
0x180035fc7  jmp     loc_180035C7D
0x180035fcc  mov     rcx, r14; this
0x180035fcf  mov     [r14], rdi
0x180035fd2  mov     byte ptr [r14+10h], 1
0x180035fd7  mov     [r14+8], rdi
0x180035fdb  call    ??1CIEApplicationAssociation@@IEAA@XZ; CIEApplicationAssociation::~CIEApplicationAssociation(void)
0x180035fe0  mov     rcx, r14; pv
0x180035fe3  call    cs:__imp_CoTaskMemFree
0x180035fea  nop     dword ptr [rax+rax+00h]
0x180035fef  jmp     loc_180035C99
0x180035ff4  mov     rax, [rcx]
0x180035ff7  mov     rax, [rax+10h]
0x180035ffb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036000  jmp     loc_180035CC3
```
