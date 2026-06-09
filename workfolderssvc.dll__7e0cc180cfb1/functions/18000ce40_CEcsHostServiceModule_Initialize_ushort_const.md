# CEcsHostServiceModule::Initialize(ushort const *)

- ea: `0x18000ce40`
- end: `0x18000d5c3`
- name: `?Initialize@CEcsHostServiceModule@@AEAAXPEBG@Z`
- size: `1923`
- prototype: `void __fastcall(CEcsHostServiceModule *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `37`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000ded0`

## callees

- `0x180002fa4`
- `0x180003604`
- `0x180004420`
- `0x180007b9c`
- `0x180007bc8`
- `0x180007e10`
- `0x180007fe4`
- `0x180008374`
- `0x1800083e8`
- `0x180008414`
- `0x18000855c`
- `0x180008898`
- `0x1800088a8`
- `0x180008908`
- `0x180008994`
- `0x180008b60`
- `0x180008c18`
- `0x180009188`
- `0x18000974c`
- `0x1800097b0`
- `0x18000afdc`
- `0x18000ce40`
- `0x180010d38`
- `0x180011084`
- `0x1800110fc`
- `0x180011258`
- `0x180011314`
- `0x18001133c`
- `0x18001a58c`
- `0x1800223f4`
- `0x1800235d4`
- `0x180028a30`
- `0x18005ce3c`
- `0x1800b178c`
- `0x1800b1a5c`
- `0x1800b1e44`
- `0x18013e010`

## import_xrefs

- `KERNEL32!CreateThreadpoolCleanupGroup` at `0x18000d43d`
- `KERNEL32!CreateThreadpoolCleanupGroup` at `0x18000d43d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000cf0c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000cf0c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d59b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d59b`
- `api-ms-win-core-com-l1-1-0!CoAllowUnmarshalerCLSID` at `0x18000d50f`
- `api-ms-win-core-com-l1-1-0!CoAllowUnmarshalerCLSID` at `0x18000d50f`

## string_xrefs

- `0x18000cecb`: `CEcsHostServiceModule::Initialize`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
void __fastcall CEcsHostServiceModule::Initialize(CEcsHostServiceModule *this, const unsigned __int16 *a2)
{
  _BYTE *v2; // rax
  char v3; // cl
  int v4; // edi
  int v5; // r12d
  int v6; // r13d
  signed int v7; // r9d
  signed int v8; // r9d
  signed int v9; // r9d
  signed int v10; // r9d
  signed int v11; // r9d
  int v12; // r15d
  int v13; // r14d
  PVOID *v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // r8
  int v19; // eax
  __int64 v20; // rbx
  void *v21; // rax
  __int64 v22; // rcx
  __int64 v23; // rax
  __int64 v24; // rcx
  CNetworkStatusController **v25; // rax
  CNetworkStatusController *v26; // rcx
  int v27; // eax
  __int64 v28; // [rsp+30h] [rbp-D0h]
  __int64 v29; // [rsp+30h] [rbp-D0h]
  __int64 v30; // [rsp+30h] [rbp-D0h]
  __int64 v31; // [rsp+30h] [rbp-D0h]
  __int64 v32; // [rsp+30h] [rbp-D0h]
  HKEY v33; // [rsp+48h] [rbp-B8h] BYREF
  int LastFailureAsHRESULT; // [rsp+50h] [rbp-B0h] BYREF
  int v35; // [rsp+54h] [rbp-ACh]
  char v36; // [rsp+58h] [rbp-A8h]
  const char *v37; // [rsp+60h] [rbp-A0h]
  __int64 v38; // [rsp+68h] [rbp-98h]
  CNetworkStatusController *v39; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v40[16]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v41; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v42[16]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v43[16]; // [rsp+A0h] [rbp-60h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+B0h] [rbp-50h] BYREF
  char v45; // [rsp+B8h] [rbp-48h]
  __int64 v46; // [rsp+C0h] [rbp-40h] BYREF
  int v47; // [rsp+C8h] [rbp-38h]
  int v48; // [rsp+CCh] [rbp-34h]
  int v49; // [rsp+D0h] [rbp-30h]
  int v50[4]; // [rsp+D8h] [rbp-28h] BYREF
  int v51[4]; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v52[2]; // [rsp+F8h] [rbp-8h] BYREF
  int v53[22]; // [rsp+108h] [rbp+8h] BYREF
  CEcsHostServiceModule *v54; // [rsp+170h] [rbp+70h] BYREF
  __int64 pExceptionObject; // [rsp+178h] [rbp+78h] BYREF
  int v56; // [rsp+180h] [rbp+80h] BYREF
  void *v57; // [rsp+188h] [rbp+88h]

  pExceptionObject = (__int64)a2;
  v54 = this;
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 42, WPP_152c595f472e31f48642c74f47fa958e_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  if ( (v2[68] & 8) == 0 || (v3 = 1, v2[65] < 6u) )
    v3 = 0;
  LastFailureAsHRESULT = 0;
  v35 = 769;
  v36 = v3;
  v37 = "CEcsHostServiceModule::Initialize";
  v38 = 0;
  CEcsExclusiveLock<CEcsCriticalSection>::CEcsExclusiveLock<CEcsCriticalSection>(&lpCriticalSection, &stru_1801AF858);
  CEcsHelperLibrary::Init();
  byte_1801AF8D8 = 1;
  CEcsFunctionTracer::InitShared();
  McGenEventRegister_EventRegister();
  pExceptionObject = (__int64)CreateEventW(0, 1, 0, 0);
  EcsUniqueHandle<void *,Win32HandleDeleter,0>::reset(&hEvent, &pExceptionObject);
  if ( !hEvent )
  {
    HIWORD(v35) = 781;
    LODWORD(pExceptionObject) = EcsGetLastFailureAsHRESULT();
    throw (long *)&pExceptionObject;
  }
  LastFailureAsHRESULT = 0;
  LOWORD(v35) = 781;
  v4 = 600;
  v5 = 600;
  v6 = 1800;
  pExceptionObject = -2147483646;
  CEcsRegKey::Get(
    &v33,
    &pExceptionObject,
    L"Software\\Microsoft\\Windows\\CurrentVersion\\WorkFolders",
    131097,
    0,
    0,
    0,
    0);
  CEcsRegKey::Close((CEcsRegKey *)&pExceptionObject);
  if ( v33 )
  {
    LODWORD(v54) = 0;
    LODWORD(pExceptionObject) = 0;
    CEcsRegKey::GetGenericValue<unsigned long,unsigned long>(
      &v33,
      L"PollIntervalSeconds",
      &v54,
      v7,
      &pExceptionObject,
      &pExceptionObject,
      v28,
      0);
    if ( (int)pExceptionObject > 0 )
      v4 = pExceptionObject;
    LODWORD(v54) = 0;
    LODWORD(pExceptionObject) = 0;
    CEcsRegKey::GetGenericValue<unsigned long,unsigned long>(
      &v33,
      L"ErrorRetryIntervalSeconds",
      &v54,
      v8,
      &pExceptionObject,
      &pExceptionObject,
      v29,
      0);
    if ( (int)pExceptionObject > 0 )
      v5 = pExceptionObject;
    LODWORD(v54) = 0;
    LODWORD(pExceptionObject) = 0;
    CEcsRegKey::GetGenericValue<unsigned long,unsigned long>(
      &v33,
      L"MaxWatcherWaitSeconds",
      &v54,
      v9,
      &pExceptionObject,
      &pExceptionObject,
      v30,
      0);
    if ( (int)pExceptionObject > 0 )
      v6 = pExceptionObject;
    LODWORD(v54) = 5;
    LODWORD(pExceptionObject) = 0;
    CEcsRegKey::GetGenericValue<unsigned long,unsigned long>(
      &v33,
      L"WatcherBackoffSeconds",
      &v54,
      v10,
      &pExceptionObject,
      &pExceptionObject,
      v31,
      0);
    v12 = pExceptionObject;
    if ( (int)pExceptionObject < 0 )
      v12 = 5;
    LODWORD(v54) = 30;
    LODWORD(pExceptionObject) = 0;
    CEcsRegKey::GetGenericValue<unsigned long,unsigned long>(
      &v33,
      L"WatcherMaxBackoffSeconds",
      &v54,
      v11,
      &pExceptionObject,
      &pExceptionObject,
      v32,
      0);
    v13 = pExceptionObject;
    if ( (int)pExceptionObject < 0 )
      v13 = 30;
  }
  else
  {
    v13 = 30;
    v12 = 5;
  }
  v14 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 43, WPP_152c595f472e31f48642c74f47fa958e_Traceguids);
      v14 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v14 != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v14 + 68) & 8) != 0 && *((_BYTE *)v14 + 65) >= 4u )
      {
        WPP_SF_d(v14[7], 44, WPP_152c595f472e31f48642c74f47fa958e_Traceguids);
        v14 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v14 != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)v14 + 68) & 8) != 0 && *((_BYTE *)v14 + 65) >= 4u )
        {
          WPP_SF_d(v14[7], 45, WPP_152c595f472e31f48642c74f47fa958e_Traceguids);
          v14 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v14 != &WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)v14 + 68) & 8) != 0 && *((_BYTE *)v14 + 65) >= 4u )
          {
            WPP_SF_d(v14[7], 46, WPP_152c595f472e31f48642c74f47fa958e_Traceguids);
            v14 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 68) & 8) != 0 && *((_BYTE *)v14 + 65) >= 4u )
            WPP_SF_d(v14[7], 47, WPP_152c595f472e31f48642c74f47fa958e_Traceguids);
        }
      }
    }
  }
  SyncShareManagerConfig::SyncShareManagerConfig((SyncShareManagerConfig *)&v46, v4, v5, v6, v12, v13);
  v15 = std::make_shared<CPartnershipPersister,>(v40);
  std::shared_ptr<IFileDownloadRunner>::shared_ptr<IFileDownloadRunner>(v53, v15);
  std::_Ptr_base<CEcsWebRequest::RequestBody>::_Decref(v40);
  v16 = std::make_shared<CSyncShareEngineFactory,>(v40);
  std::shared_ptr<IFileDownloadRunner>::shared_ptr<IFileDownloadRunner>(v52, v16);
  std::_Ptr_base<CEcsWebRequest::RequestBody>::_Decref(v40);
  v17 = std::make_shared<CProtocolClientFactory,>(v40);
  std::shared_ptr<IFileDownloadRunner>::shared_ptr<IFileDownloadRunner>(v51, v17);
  std::_Ptr_base<CEcsWebRequest::RequestBody>::_Decref(v40);
  LODWORD(pExceptionObject) = v49;
  LODWORD(v54) = v48;
  v56 = v47;
  v57 = operator new(0x28u);
  std::_Ref_count_obj2<CWatcherFactory>::_Ref_count_obj2<CWatcherFactory>(v57, &v56, &v54, &pExceptionObject);
  std::shared_ptr<IProtocolClientFactory>::shared_ptr<IProtocolClientFactory>(v42);
  std::shared_ptr<CUniqueSyncEngine>::_Set_ptr_rep_and_enable_shared<CUniqueSyncEngine>(v42, v18 + 16);
  std::shared_ptr<IFileDownloadRunner>::shared_ptr<IFileDownloadRunner>(v50, v42);
  std::_Ptr_base<CEcsWebRequest::RequestBody>::_Decref(v42);
  pExceptionObject = 0;
  v19 = ATL::CComObject<CSyncSharePartnershipManagerInternal>::CreateInstance(&pExceptionObject);
  LastFailureAsHRESULT = v19;
  if ( v19 < 0 )
  {
    HIWORD(v35) = 841;
    LODWORD(pExceptionObject) = v19;
    throw (long *)&pExceptionObject;
  }
  LOWORD(v35) = 841;
  v20 = pExceptionObject;
  v41 = pExceptionObject;
  if ( pExceptionObject )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)pExceptionObject + 8LL))(pExceptionObject);
  v21 = operator new(0xB0u);
  pExceptionObject = (__int64)v21;
  v22 = v20 + 80;
  if ( !v20 )
    v22 = 0;
  v23 = CSyncStateManager::CSyncStateManager((int)v21, (int)v53, (int)v51, (int)v50, (__int64)v52, (__int64)&v46, v22);
  std::shared_ptr<CSyncStateManager>::shared_ptr<CSyncStateManager>(v43, v23);
  CSyncSharePartnershipManagerInternal::Initialize(v20, v43);
  ATL::CComPtr<ISyncSharePartnershipManager>::operator=(v24, v20);
  std::shared_ptr<CSyncStateManager>::operator=(&pv, v43);
  pcbe.Version = 3;
  pcbe.Pool = 0;
  pcbe.CleanupGroup = 0;
  pcbe.CleanupGroupCancelCallback = 0;
  *(_OWORD *)&pcbe.RaceDll = 0;
  pcbe.FinalizationCallback = 0;
  pcbe.u.Flags = 0;
  pcbe.CallbackPriority = TP_CALLBACK_PRIORITY_NORMAL;
  pcbe.Size = 72;
  byte_1801AF8C8 = 1;
  pExceptionObject = (__int64)CreateThreadpoolCleanupGroup();
  EcsUniqueHandle<_TP_CLEANUP_GROUP *,Win32ThreadPoolCleanupGroupDeleter,0>::reset(&ptpcg, &pExceptionObject);
  if ( !ptpcg )
  {
    LastFailureAsHRESULT = EcsGetLastFailureAsHRESULT();
    HIWORD(v35) = 862;
    LODWORD(pExceptionObject) = LastFailureAsHRESULT;
    throw (long *)&pExceptionObject;
  }
  LastFailureAsHRESULT = 0;
  LOWORD(v35) = 862;
  pcbe.CleanupGroup = ptpcg;
  pcbe.CleanupGroupCancelCallback = 0;
  v25 = (CNetworkStatusController **)Microsoft::WRL::Details::Make<CNetworkStatusController,>(&pExceptionObject);
  v39 = 0;
  v26 = 0;
  if ( &v39 != v25 )
  {
    v26 = *v25;
    v39 = *v25;
    *v25 = 0;
  }
  v39 = qword_1801AF848;
  qword_1801AF848 = v26;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pExceptionObject);
  CNetworkStatusController::StartMonitoring(qword_1801AF848);
  v27 = CoAllowUnmarshalerCLSID(&GUID_CLSID_CSHAREDSTREAMPROXY);
  LastFailureAsHRESULT = v27;
  if ( v27 < 0 )
  {
    HIWORD(v35) = 871;
    LODWORD(pExceptionObject) = v27;
    throw (long *)&pExceptionObject;
  }
  LOWORD(v35) = 871;
  CEcsAsimovTelemetry::Init();
  std::_Ptr_base<CEcsWebRequest::RequestBody>::_Decref(v43);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v41);
  std::_Ptr_base<CEcsWebRequest::RequestBody>::_Decref(v50);
  std::_Ptr_base<CEcsWebRequest::RequestBody>::_Decref(v51);
  std::_Ptr_base<CEcsWebRequest::RequestBody>::_Decref(v52);
  std::_Ptr_base<CEcsWebRequest::RequestBody>::_Decref(v53);
  CEcsRegKey::Close((CEcsRegKey *)&v33);
  if ( v45 )
  {
    LeaveCriticalSection(lpCriticalSection);
    v45 = 0;
  }
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&LastFailureAsHRESULT);
}

```

## disassembly

```asm
0x18000ce40  mov     [rsp-8+pExceptionObject], rdx
0x18000ce45  mov     [rsp-8+arg_0], rcx
0x18000ce4a  push    rbp
0x18000ce4b  push    rbx
0x18000ce4c  push    rsi
0x18000ce4d  push    rdi
0x18000ce4e  push    r12
0x18000ce50  push    r13
0x18000ce52  push    r14
0x18000ce54  push    r15
0x18000ce56  lea     rbp, [rsp-28h]
0x18000ce5b  sub     rsp, 128h
0x18000ce62  xor     r14d, r14d
0x18000ce65  mov     [rsp+160h+var_120], r14d
0x18000ce6a  lea     rcx, WPP_GLOBAL_Control
0x18000ce71  mov     rax, cs:WPP_GLOBAL_Control
0x18000ce78  cmp     rax, rcx
0x18000ce7b  jz      short loc_18000CEA4
0x18000ce7d  test    byte ptr [rax+44h], 8
0x18000ce81  jz      short loc_18000CEA4
0x18000ce83  cmp     byte ptr [rax+41h], 6
0x18000ce87  jb      short loc_18000CEA4
0x18000ce89  lea     edx, [r14+2Ah]
0x18000ce8d  lea     r8, WPP_152c595f472e31f48642c74f47fa958e_Traceguids
0x18000ce94  mov     rcx, [rax+38h]
0x18000ce98  call    WPP_SF_
0x18000ce9d  mov     rax, cs:WPP_GLOBAL_Control
0x18000cea4  mov     ebx, 1
0x18000cea9  test    byte ptr [rax+44h], 8
0x18000cead  jz      short loc_18000CEB7
0x18000ceaf  cmp     byte ptr [rax+41h], 6
0x18000ceb3  mov     cl, bl
0x18000ceb5  jnb     short loc_18000CEBA
0x18000ceb7  mov     cl, r14b
0x18000ceba  mov     [rsp+160h+var_110], r14d
0x18000cebf  mov     [rsp+160h+var_10C], 301h
0x18000cec7  mov     [rsp+160h+var_108], cl
0x18000cecb  lea     rax, aCecshostservic_7; "CEcsHostServiceModule::Initialize"
0x18000ced2  mov     [rsp+160h+var_100], rax
0x18000ced7  mov     [rsp+160h+var_F8], r14
0x18000cedc  lea     rdx, stru_1801AF858
0x18000cee3  lea     rcx, [rbp+60h+lpCriticalSection]
0x18000cee7  call    ??0?$CEcsExclusiveLock@VCEcsCriticalSection@@@@QEAA@AEAVCEcsCriticalSection@@_N@Z; CEcsExclusiveLock<CEcsCriticalSection>::CEcsExclusiveLock<CEcsCriticalSection>(CEcsCriticalSection &,bool)
0x18000ceec  nop
0x18000ceed  call    ?Init@CEcsHelperLibrary@@SAXXZ; CEcsHelperLibrary::Init(void)
0x18000cef2  mov     cs:byte_1801AF8D8, bl
0x18000cef8  call    ?InitShared@CEcsFunctionTracer@@SAXXZ; CEcsFunctionTracer::InitShared(void)
0x18000cefd  call    McGenEventRegister_EventRegister
0x18000cf02  xor     r9d, r9d; lpName
0x18000cf05  xor     r8d, r8d; bInitialState
0x18000cf08  mov     edx, ebx; bManualReset
0x18000cf0a  xor     ecx, ecx; lpEventAttributes
0x18000cf0c  call    cs:__imp_CreateEventW
0x18000cf12  mov     [rbp+60h+pExceptionObject], rax
0x18000cf16  lea     rdx, [rbp+60h+pExceptionObject]
0x18000cf1a  lea     rcx, hEvent
0x18000cf21  call    ?reset@?$EcsUniqueHandle@PEAXUWin32HandleDeleter@@$0A@@@QEAAXAEBQEAX@Z; EcsUniqueHandle<void *,Win32HandleDeleter,0>::reset(void * const &)
0x18000cf26  mov     eax, [rsp+160h+var_110]
0x18000cf2a  mov     [rsp+160h+var_110], eax
0x18000cf2e  cmp     cs:hEvent, r14
0x18000cf35  jnz     short loc_18000CF5E
0x18000cf37  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x18000cf3c  mov     [rsp+160h+var_110], eax
0x18000cf40  mov     ecx, 30Dh
0x18000cf45  mov     word ptr [rsp+160h+var_10C+2], cx
0x18000cf4a  mov     dword ptr [rbp+60h+pExceptionObject], eax
0x18000cf4d  lea     rdx, _TI1J; pThrowInfo
0x18000cf54  lea     rcx, [rbp+60h+pExceptionObject]; pExceptionObject
0x18000cf58  call    _CxxThrowException_0
0x18000cf5e  mov     [rsp+160h+var_110], r14d
0x18000cf63  mov     ecx, 30Dh
0x18000cf68  mov     word ptr [rsp+160h+var_10C], cx
0x18000cf6d  mov     edi, 258h
0x18000cf72  mov     r12d, edi
0x18000cf75  mov     r13d, 708h
0x18000cf7b  mov     [rbp+60h+pExceptionObject], 0FFFFFFFF80000002h
0x18000cf83  mov     [rsp+160h+var_120], ebx
0x18000cf87  mov     byte ptr [rsp+160h+var_128], r14b
0x18000cf8c  mov     [rsp+160h+var_130], r14
0x18000cf91  mov     [rsp+160h+var_138], r14
0x18000cf96  mov     byte ptr [rsp+160h+var_140], r14b
0x18000cf9b  mov     r9d, 20019h
0x18000cfa1  lea     r8, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000cfa8  lea     rdx, [rbp+60h+pExceptionObject]
0x18000cfac  lea     rcx, [rsp+160h+var_118]
0x18000cfb1  call    ?Get@CEcsRegKey@@SA?AV1@AEBV1@PEBGK_NPEAU_SECURITY_ATTRIBUTES@@PEA_N2@Z; CEcsRegKey::Get(CEcsRegKey const &,ushort const *,ulong,bool,_SECURITY_ATTRIBUTES *,bool *,bool)
0x18000cfb6  nop
0x18000cfb7  and     ebx, 0FFFFFFFEh
0x18000cfba  mov     [rsp+160h+var_120], ebx
0x18000cfbe  lea     rcx, [rbp+60h+pExceptionObject]; this
0x18000cfc2  call    ?Close@CEcsRegKey@@QEAAXXZ; CEcsRegKey::Close(void)
0x18000cfc7  cmp     [rsp+160h+var_118], r14
0x18000cfcc  jz      loc_18000D110
0x18000cfd2  mov     dword ptr [rbp+60h+arg_0], r14d
0x18000cfd6  mov     dword ptr [rbp+60h+pExceptionObject], r14d
0x18000cfda  mov     [rsp+160h+var_128], r14
0x18000cfdf  lea     rax, [rbp+60h+pExceptionObject]
0x18000cfe3  mov     [rsp+160h+var_138], rax
0x18000cfe8  lea     rax, [rbp+60h+pExceptionObject]
0x18000cfec  mov     [rsp+160h+var_140], rax
0x18000cff1  lea     r8, [rbp+60h+arg_0]
0x18000cff5  lea     rdx, aPollintervalse; "PollIntervalSeconds"
0x18000cffc  lea     rcx, [rsp+160h+var_118]
0x18000d001  call    ??$GetGenericValue@KK@CEcsRegKey@@AEBA_NPEBGAEBKKAEAKPEAXKPEA_N@Z; CEcsRegKey::GetGenericValue<ulong,ulong>(ushort const *,ulong const &,ulong,ulong &,void *,ulong,bool *)
0x18000d006  mov     eax, dword ptr [rbp+60h+pExceptionObject]
0x18000d009  test    eax, eax
0x18000d00b  cmovg   edi, eax
0x18000d00e  mov     dword ptr [rbp+60h+arg_0], r14d
0x18000d012  mov     dword ptr [rbp+60h+pExceptionObject], r14d
0x18000d016  mov     [rsp+160h+var_128], r14
0x18000d01b  lea     rax, [rbp+60h+pExceptionObject]
0x18000d01f  mov     [rsp+160h+var_138], rax
0x18000d024  lea     rax, [rbp+60h+pExceptionObject]
0x18000d028  mov     [rsp+160h+var_140], rax
0x18000d02d  lea     r8, [rbp+60h+arg_0]
0x18000d031  lea     rdx, aErrorretryinte; "ErrorRetryIntervalSeconds"
0x18000d038  lea     rcx, [rsp+160h+var_118]
0x18000d03d  call    ??$GetGenericValue@KK@CEcsRegKey@@AEBA_NPEBGAEBKKAEAKPEAXKPEA_N@Z; CEcsRegKey::GetGenericValue<ulong,ulong>(ushort const *,ulong const &,ulong,ulong &,void *,ulong,bool *)
0x18000d042  mov     eax, dword ptr [rbp+60h+pExceptionObject]
0x18000d045  test    eax, eax
0x18000d047  cmovg   r12d, eax
0x18000d04b  mov     dword ptr [rbp+60h+arg_0], r14d
0x18000d04f  mov     dword ptr [rbp+60h+pExceptionObject], r14d
0x18000d053  mov     [rsp+160h+var_128], r14
0x18000d058  lea     rax, [rbp+60h+pExceptionObject]
0x18000d05c  mov     [rsp+160h+var_138], rax
0x18000d061  lea     rax, [rbp+60h+pExceptionObject]
0x18000d065  mov     [rsp+160h+var_140], rax
0x18000d06a  lea     r8, [rbp+60h+arg_0]
0x18000d06e  lea     rdx, aMaxwatcherwait; "MaxWatcherWaitSeconds"
0x18000d075  lea     rcx, [rsp+160h+var_118]
0x18000d07a  call    ??$GetGenericValue@KK@CEcsRegKey@@AEBA_NPEBGAEBKKAEAKPEAXKPEA_N@Z; CEcsRegKey::GetGenericValue<ulong,ulong>(ushort const *,ulong const &,ulong,ulong &,void *,ulong,bool *)
0x18000d07f  mov     eax, dword ptr [rbp+60h+pExceptionObject]
0x18000d082  test    eax, eax
0x18000d084  cmovg   r13d, eax
0x18000d088  mov     esi, 5
0x18000d08d  mov     dword ptr [rbp+60h+arg_0], esi
0x18000d090  mov     dword ptr [rbp+60h+pExceptionObject], r14d
0x18000d094  mov     [rsp+160h+var_128], r14
0x18000d099  lea     rax, [rbp+60h+pExceptionObject]
0x18000d09d  mov     [rsp+160h+var_138], rax
0x18000d0a2  lea     rax, [rbp+60h+pExceptionObject]
0x18000d0a6  mov     [rsp+160h+var_140], rax
0x18000d0ab  lea     r8, [rbp+60h+arg_0]
0x18000d0af  lea     rdx, aWatcherbackoff; "WatcherBackoffSeconds"
0x18000d0b6  lea     rcx, [rsp+160h+var_118]
0x18000d0bb  call    ??$GetGenericValue@KK@CEcsRegKey@@AEBA_NPEBGAEBKKAEAKPEAXKPEA_N@Z; CEcsRegKey::GetGenericValue<ulong,ulong>(ushort const *,ulong const &,ulong,ulong &,void *,ulong,bool *)
0x18000d0c0  mov     r15d, dword ptr [rbp+60h+pExceptionObject]
0x18000d0c4  test    r15d, r15d
0x18000d0c7  cmovs   r15d, esi
0x18000d0cb  mov     esi, 1Eh
0x18000d0d0  mov     dword ptr [rbp+60h+arg_0], esi
0x18000d0d3  mov     dword ptr [rbp+60h+pExceptionObject], r14d
0x18000d0d7  mov     [rsp+160h+var_128], r14
0x18000d0dc  lea     rax, [rbp+60h+pExceptionObject]
0x18000d0e0  mov     [rsp+160h+var_138], rax
0x18000d0e5  lea     rax, [rbp+60h+pExceptionObject]
0x18000d0e9  mov     [rsp+160h+var_140], rax
0x18000d0ee  lea     r8, [rbp+60h+arg_0]
0x18000d0f2  lea     rdx, aWatchermaxback; "WatcherMaxBackoffSeconds"
0x18000d0f9  lea     rcx, [rsp+160h+var_118]
0x18000d0fe  call    ??$GetGenericValue@KK@CEcsRegKey@@AEBA_NPEBGAEBKKAEAKPEAXKPEA_N@Z; CEcsRegKey::GetGenericValue<ulong,ulong>(ushort const *,ulong const &,ulong,ulong &,void *,ulong,bool *)
0x18000d103  mov     r14d, dword ptr [rbp+60h+pExceptionObject]
0x18000d107  test    r14d, r14d
0x18000d10a  cmovs   r14d, esi
0x18000d10e  jmp     short loc_18000D11A
0x18000d110  mov     r14d, 1Eh
0x18000d116  lea     r15d, [r14-19h]
0x18000d11a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d121  lea     rsi, WPP_GLOBAL_Control
0x18000d128  cmp     rcx, rsi
0x18000d12b  jz      loc_18000D21D
0x18000d131  test    byte ptr [rcx+44h], 8
0x18000d135  jz      short loc_18000D15C
0x18000d137  cmp     byte ptr [rcx+41h], 4
0x18000d13b  jb      short loc_18000D15C
0x18000d13d  mov     edx, 2Bh ; '+'
0x18000d142  mov     r9d, edi
0x18000d145  lea     r8, WPP_152c595f472e31f48642c74f47fa958e_Traceguids
0x18000d14c  mov     rcx, [rcx+38h]
0x18000d150  call    WPP_SF_d
0x18000d155  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d15c  cmp     rcx, rsi
0x18000d15f  jz      loc_18000D21D
0x18000d165  test    byte ptr [rcx+44h], 8
0x18000d169  jz      short loc_18000D190
0x18000d16b  cmp     byte ptr [rcx+41h], 4
0x18000d16f  jb      short loc_18000D190
0x18000d171  mov     edx, 2Ch ; ','
0x18000d176  mov     r9d, r12d
0x18000d179  lea     r8, WPP_152c595f472e31f48642c74f47fa958e_Traceguids
0x18000d180  mov     rcx, [rcx+38h]
0x18000d184  call    WPP_SF_d
0x18000d189  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d190  cmp     rcx, rsi
0x18000d193  jz      loc_18000D21D
0x18000d199  test    byte ptr [rcx+44h], 8
0x18000d19d  jz      short loc_18000D1C4
0x18000d19f  cmp     byte ptr [rcx+41h], 4
0x18000d1a3  jb      short loc_18000D1C4
0x18000d1a5  mov     edx, 2Dh ; '-'
0x18000d1aa  mov     r9d, r13d
0x18000d1ad  lea     r8, WPP_152c595f472e31f48642c74f47fa958e_Traceguids
0x18000d1b4  mov     rcx, [rcx+38h]
0x18000d1b8  call    WPP_SF_d
0x18000d1bd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d1c4  cmp     rcx, rsi
0x18000d1c7  jz      short loc_18000D21D
0x18000d1c9  test    byte ptr [rcx+44h], 8
0x18000d1cd  jz      short loc_18000D1F4
0x18000d1cf  cmp     byte ptr [rcx+41h], 4
0x18000d1d3  jb      short loc_18000D1F4
0x18000d1d5  mov     edx, 2Eh ; '.'
0x18000d1da  mov     r9d, r15d
0x18000d1dd  lea     r8, WPP_152c595f472e31f48642c74f47fa958e_Traceguids
0x18000d1e4  mov     rcx, [rcx+38h]
0x18000d1e8  call    WPP_SF_d
0x18000d1ed  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d1f4  cmp     rcx, rsi
0x18000d1f7  jz      short loc_18000D21D
0x18000d1f9  test    byte ptr [rcx+44h], 8
0x18000d1fd  jz      short loc_18000D21D
0x18000d1ff  cmp     byte ptr [rcx+41h], 4
0x18000d203  jb      short loc_18000D21D
0x18000d205  mov     edx, 2Fh ; '/'
0x18000d20a  mov     r9d, r14d
0x18000d20d  lea     r8, WPP_152c595f472e31f48642c74f47fa958e_Traceguids
0x18000d214  mov     rcx, [rcx+38h]
0x18000d218  call    WPP_SF_d
0x18000d21d  mov     dword ptr [rsp+160h+var_138], r14d; int
0x18000d222  mov     dword ptr [rsp+160h+var_140], r15d; pExceptionObject
0x18000d227  mov     r9d, r13d; int
0x18000d22a  mov     r8d, r12d; int
0x18000d22d  mov     edx, edi; int
0x18000d22f  lea     rcx, [rbp+60h+var_A0]; this
0x18000d233  call    ??0SyncShareManagerConfig@@QEAA@JJJJJ@Z; SyncShareManagerConfig::SyncShareManagerConfig(long,long,long,long,long)
0x18000d238  lea     rcx, [rsp+160h+var_E8]
0x18000d23d  call    ??$make_shared@VCPartnershipPersister@@$$V@std@@YA?AV?$shared_ptr@VCPartnershipPersister@@@0@XZ; std::make_shared<CPartnershipPersister,>(void)
0x18000d242  nop
0x18000d243  mov     rdx, rax
0x18000d246  lea     rcx, [rbp+60h+var_58]
0x18000d24a  call    ??0?$shared_ptr@VIFileDownloadRunner@@@std@@QEAA@$$QEAV01@@Z; std::shared_ptr<IFileDownloadRunner>::shared_ptr<IFileDownloadRunner>(std::shared_ptr<IFileDownloadRunner> &&)
0x18000d24f  nop
0x18000d250  lea     rcx, [rsp+160h+var_E8]
0x18000d255  call    ?_Decref@?$_Ptr_base@VRequestBody@CEcsWebRequest@@@std@@IEAAXXZ; std::_Ptr_base<CEcsWebRequest::RequestBody>::_Decref(void)
0x18000d25a  lea     rcx, [rsp+160h+var_E8]
0x18000d25f  call    ??$make_shared@VCSyncShareEngineFactory@@$$V@std@@YA?AV?$shared_ptr@VCSyncShareEngineFactory@@@0@XZ; std::make_shared<CSyncShareEngineFactory,>(void)
0x18000d264  nop
0x18000d265  mov     rdx, rax
0x18000d268  lea     rcx, [rbp+60h+var_68]
0x18000d26c  call    ??0?$shared_ptr@VIFileDownloadRunner@@@std@@QEAA@$$QEAV01@@Z; std::shared_ptr<IFileDownloadRunner>::shared_ptr<IFileDownloadRunner>(std::shared_ptr<IFileDownloadRunner> &&)
0x18000d271  nop
0x18000d272  lea     rcx, [rsp+160h+var_E8]
0x18000d277  call    ?_Decref@?$_Ptr_base@VRequestBody@CEcsWebRequest@@@std@@IEAAXXZ; std::_Ptr_base<CEcsWebRequest::RequestBody>::_Decref(void)
0x18000d27c  lea     rcx, [rsp+160h+var_E8]
0x18000d281  call    ??$make_shared@VCProtocolClientFactory@@$$V@std@@YA?AV?$shared_ptr@VCProtocolClientFactory@@@0@XZ; std::make_shared<CProtocolClientFactory,>(void)
0x18000d286  nop
0x18000d287  mov     rdx, rax
0x18000d28a  lea     rcx, [rbp+60h+var_78]
0x18000d28e  call    ??0?$shared_ptr@VIFileDownloadRunner@@@std@@QEAA@$$QEAV01@@Z; std::shared_ptr<IFileDownloadRunner>::shared_ptr<IFileDownloadRunner>(std::shared_ptr<IFileDownloadRunner> &&)
0x18000d293  nop
0x18000d294  lea     rcx, [rsp+160h+var_E8]
0x18000d299  call    ?_Decref@?$_Ptr_base@VRequestBody@CEcsWebRequest@@@std@@IEAAXXZ; std::_Ptr_base<CEcsWebRequest::RequestBody>::_Decref(void)
0x18000d29e  mov     eax, [rbp+60h+var_90]
0x18000d2a1  mov     dword ptr [rbp+60h+pExceptionObject], eax
0x18000d2a4  mov     eax, [rbp+60h+var_94]
0x18000d2a7  mov     dword ptr [rbp+60h+arg_0], eax
0x18000d2aa  mov     eax, [rbp+60h+var_98]
0x18000d2ad  mov     [rbp+60h+arg_10], eax
0x18000d2b3  mov     ecx, 28h ; '('; Size
0x18000d2b8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d2bd  mov     [rbp+60h+arg_18], rax
0x18000d2c4  lea     r9, [rbp+60h+pExceptionObject]
0x18000d2c8  lea     r8, [rbp+60h+arg_0]
0x18000d2cc  lea     rdx, [rbp+60h+arg_10]
0x18000d2d3  mov     rcx, rax
0x18000d2d6  call    ??$?0JJJ@?$_Ref_count_obj2@VCWatcherFactory@@@std@@QEAA@$$QEAJ00@Z; std::_Ref_count_obj2<CWatcherFactory>::_Ref_count_obj2<CWatcherFactory>(long &&,long &&,long &&)
0x18000d2db  mov     r8, rax
0x18000d2de  lea     rcx, [rbp+60h+var_D0]
0x18000d2e2  call    ??0?$shared_ptr@VIProtocolClientFactory@@@std@@QEAA@XZ; std::shared_ptr<IProtocolClientFactory>::shared_ptr<IProtocolClientFactory>(void)
0x18000d2e7  or      ebx, 10h
0x18000d2ea  mov     [rsp+160h+var_120], ebx
0x18000d2ee  lea     rdx, [r8+10h]
0x18000d2f2  lea     rcx, [rbp+60h+var_D0]
0x18000d2f6  call    ??$_Set_ptr_rep_and_enable_shared@VCUniqueSyncEngine@@@?$shared_ptr@VCUniqueSyncEngine@@@std@@AEAAXQEAVCUniqueSyncEngine@@QEAV_Ref_count_base@1@@Z; std::shared_ptr<CUniqueSyncEngine>::_Set_ptr_rep_and_enable_shared<CUniqueSyncEngine>(CUniqueSyncEngine * const,std::_Ref_count_base * const)
0x18000d2fb  lea     rdx, [rbp+60h+var_D0]
0x18000d2ff  lea     rcx, [rbp+60h+var_88]
0x18000d303  call    ??0?$shared_ptr@VIFileDownloadRunner@@@std@@QEAA@$$QEAV01@@Z; std::shared_ptr<IFileDownloadRunner>::shared_ptr<IFileDownloadRunner>(std::shared_ptr<IFileDownloadRunner> &&)
0x18000d308  nop
0x18000d309  and     ebx, 0FFFFFFEFh
0x18000d30c  mov     [rsp+160h+var_120], ebx
0x18000d310  lea     rcx, [rbp+60h+var_D0]
0x18000d314  call    ?_Decref@?$_Ptr_base@VRequestBody@CEcsWebRequest@@@std@@IEAAXXZ; std::_Ptr_base<CEcsWebRequest::RequestBody>::_Decref(void)
0x18000d319  xor     edi, edi
0x18000d31b  mov     [rbp+60h+pExceptionObject], rdi
0x18000d31f  lea     rcx, [rbp+60h+pExceptionObject]
0x18000d323  call    ?CreateInstance@?$CComObject@VCSyncSharePartnershipManagerInternal@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CSyncSharePartnershipManagerInternal>::CreateInstance(ATL::CComObject<CSyncSharePartnershipManagerInternal> * *)
0x18000d328  mov     [rsp+160h+var_110], eax
0x18000d32c  mov     [rsp+160h+var_110], eax
0x18000d330  mov     ecx, 349h
  ... truncated ...
```
