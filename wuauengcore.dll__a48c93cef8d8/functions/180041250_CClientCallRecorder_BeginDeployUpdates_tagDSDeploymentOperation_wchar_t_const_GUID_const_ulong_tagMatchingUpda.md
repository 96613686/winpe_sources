# CClientCallRecorder::BeginDeployUpdates(tagDSDeploymentOperation,wchar_t const *,_GUID const &,ulong,tagMatchingUpdate const * const,tagDeploymentOperationPriority,ulong,ulong,unsigned __int64,ISusDeploymentCallback *,unsigned __int64,unsigned __int64,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,_GUID *)

- ea: `0x180041250`
- end: `0x180041cef`
- name: `?BeginDeployUpdates@CClientCallRecorder@@UEAAJW4tagDSDeploymentOperation@@PEB_WAEBU_GUID@@KQEBUtagMatchingUpdate@@W4tagDeploymentOperationPriority@@KK_KPEAUISusDeploymentCallback@@551111PEAU3@@Z`
- size: `2719`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, struct _GUID *, unsigned int, struct tagMatchingUpdate *, int, unsigned int, int, __int64, struct IUnknown *, void *, __int64, char *, wchar_t *, wchar_t *, wchar_t *, GUID *)`
- caller_count: `0`
- callee_count: `32`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18000def4`
- `0x18001898c`
- `0x18003d95c`
- `0x18003efbc`
- `0x180041250`
- `0x18004a3d8`
- `0x18004a4a0`
- `0x18004e534`
- `0x18004f840`
- `0x180052c68`
- `0x1800548fc`
- `0x18005c79c`
- `0x180062770`
- `0x1800c880c`
- `0x1800c8b70`
- `0x1800d5778`
- `0x1800d5bf0`
- `0x180105194`
- `0x1801051cc`
- `0x180106214`
- `0x180106274`
- `0x1801062d4`
- `0x180106dec`
- `0x180113ae8`
- `0x180119e48`
- `0x18011b63c`
- `0x18012b618`
- `0x18012bed4`
- `0x180238960`
- `0x180238984`
- `0x180239110`
- `0x180240cc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180041c02`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180041c02`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180041abe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180041abe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180041be1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180041c62`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180041be1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180041c62`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180041526`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800417b0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800417fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180041c8d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180041526`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800417b0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800417fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180041c8d`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180041c7b`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180041c7b`

## string_xrefs

- `0x180041704`: `Install`
- `0x1800416fb`: `Uninstall`
- `0x1800416f2`: `Commit`
- `0x1800413cd`: `C:\__w\1\s\src\Client\Engine\Agent\ClientCallRecorder.cpp`
- `0x1800414e1`: `C:\__w\1\s\src\Client\Engine\Agent\ClientCallRecorder.cpp`
- `0x1800415d8`: `C:\__w\1\s\src\Client\Engine\Agent\ClientCallRecorder.cpp`
- `0x18004172c`: `C:\__w\1\s\src\Client\Engine\Agent\ClientCallRecorder.cpp`
- `0x180041794`: `C:\__w\1\s\src\Client\Engine\Agent\ClientCallRecorder.cpp`
- `0x1800418fc`: `C:\__w\1\s\src\Client\Engine\Agent\ClientCallRecorder.cpp`
- `0x180041afe`: `C:\__w\1\s\src\Client\Engine\Agent\ClientCallRecorder.cpp`
- `0x180041b86`: `C:\__w\1\s\src\Client\Engine\Agent\ClientCallRecorder.cpp`
- `0x180041308`: `CClientCallRecorder::BeginDeployUpdates`
- `0x180041646`: `Non-elevated admin user is requesting %ws of updates`
- `0x18004163a`: `Installing`
- `0x180041631`: `Uninstalling`
- `0x18004161f`: `Commiting`

## pseudocode

```c
__int64 __fastcall CClientCallRecorder::BeginDeployUpdates(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        struct _GUID *a4,
        unsigned int a5,
        struct tagMatchingUpdate *a6,
        int a7,
        unsigned int a8,
        int a9,
        __int64 a10,
        struct IUnknown *a11,
        void *a12,
        __int64 a13,
        char *a14,
        wchar_t *a15,
        wchar_t *a16,
        wchar_t *a17,
        GUID *a18)
{
  __int64 v22; // rdx
  int ServiceObject; // r14d
  unsigned int i; // ebx
  __int64 v25; // rdx
  CCallerIdentity *v26; // rbx
  unsigned int v27; // ebx
  CCallerIdentity *v28; // rsi
  __int64 v29; // rdx
  const wchar_t *v30; // rax
  HANDLE v31; // rbx
  CCallerIdentity *v32; // rdi
  __int64 v33; // rdx
  const wchar_t *v34; // rax
  unsigned int v35; // r15d
  unsigned int v36; // r15d
  unsigned int v37; // r15d
  unsigned __int64 v38; // r9
  int v39; // eax
  CDeployCall *v40; // rdi
  CDeployCall *v41; // rbx
  __int64 v42; // rdx
  wchar_t **v43; // r9
  int v44; // eax
  int v45; // eax
  void *v46; // rdi
  __int64 v47; // rdx
  struct IUnknown *v48; // r15
  unsigned __int64 v49; // r9
  const struct CDeployCall *v50; // rdx
  int v51; // eax
  HANDLE v52; // rcx
  CIdleTimerHelper *v53; // rbx
  int v55; // [rsp+20h] [rbp-E0h]
  int v56; // [rsp+20h] [rbp-E0h]
  char *v57; // [rsp+28h] [rbp-D8h]
  int v58; // [rsp+80h] [rbp-80h] BYREF
  void *lpMem; // [rsp+88h] [rbp-78h] BYREF
  HANDLE v60; // [rsp+90h] [rbp-70h] BYREF
  CCallerIdentity *v61; // [rsp+98h] [rbp-68h] BYREF
  int v62; // [rsp+A0h] [rbp-60h] BYREF
  int v63; // [rsp+A4h] [rbp-5Ch] BYREF
  unsigned int v64[2]; // [rsp+A8h] [rbp-58h]
  struct IUnknown *v65; // [rsp+B0h] [rbp-50h]
  struct _GUID *v66; // [rsp+B8h] [rbp-48h]
  struct _GUID v67; // [rsp+C0h] [rbp-40h] BYREF
  wchar_t *v68; // [rsp+D0h] [rbp-30h]
  wchar_t *v69; // [rsp+D8h] [rbp-28h]
  wchar_t *v70; // [rsp+E0h] [rbp-20h]
  char *v71; // [rsp+E8h] [rbp-18h]
  struct _GUID v72; // [rsp+F0h] [rbp-10h] BYREF
  GUID *v73; // [rsp+100h] [rbp+0h]
  char *v74; // [rsp+108h] [rbp+8h]
  __int64 v75; // [rsp+110h] [rbp+10h]
  HANDLE *p_hObject; // [rsp+118h] [rbp+18h]
  __int64 v77; // [rsp+120h] [rbp+20h]
  _BYTE v78[80]; // [rsp+130h] [rbp+30h] BYREF
  char v79; // [rsp+180h] [rbp+80h] BYREF
  HANDLE hObject; // [rsp+188h] [rbp+88h] BYREF
  CIdleTimerHelper *v81[2]; // [rsp+190h] [rbp+90h] BYREF
  GUID v82; // [rsp+1A0h] [rbp+A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+108h]

  v66 = a4;
  *(_QWORD *)&v72.Data1 = a3;
  *(_QWORD *)v64 = a6;
  v65 = a11;
  lpMem = a12;
  v71 = a14;
  v68 = a15;
  v69 = a16;
  v70 = a17;
  v73 = a18;
  *(_OWORD *)v81 = 0;
  CActiveCallerCounter::CActiveCallerCounter(
    (CActiveCallerCounter *)v81,
    (int *)(a1 + 464),
    (struct ISusIdleTimer *)(*(_QWORD *)(a1 + 448) + 9992LL),
    L"CClientCallRecorder::BeginDeployUpdates");
  hObject = 0;
  v79 = 0;
  if ( !a11 )
  {
    v22 = 2861;
LABEL_5:
    ServiceObject = -2147467261;
LABEL_17:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v22,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\ClientCallRecorder.cpp",
      (const char *)(unsigned int)ServiceObject,
      v55);
LABEL_127:
    v52 = hObject;
    goto LABEL_128;
  }
  if ( !a18 )
  {
    v22 = 2862;
    goto LABEL_5;
  }
  if ( !a3 )
  {
    ServiceObject = -2147024809;
    v22 = 2863;
    goto LABEL_17;
  }
  if ( !a5 )
  {
    ServiceObject = -2147024809;
    v22 = 2864;
    goto LABEL_17;
  }
  if ( !a6 )
  {
    ServiceObject = -2147467261;
    v22 = 2865;
    goto LABEL_17;
  }
  if ( *(_QWORD *)&c_idSrvNone.Data1 == *(_QWORD *)&a4->Data1 && *(_QWORD *)c_idSrvNone.Data4 == *(_QWORD *)a4->Data4 )
  {
    ServiceObject = -2147024809;
    v22 = 2866;
    goto LABEL_17;
  }
  ServiceObject = CClientCallRecorder::PrepareBeforeAPICall((CClientCallRecorder *)a1);
  if ( ServiceObject < 0 )
  {
    v22 = 2868;
    goto LABEL_17;
  }
  v77 = 1;
  v74 = &v79;
  v75 = a1;
  p_hObject = &hObject;
  *a18 = GUID_NULL;
  for ( i = 0; i < a5; ++i )
  {
    if ( !(unsigned int)IsValidMatchingUpdate((struct tagMatchingUpdate *)((char *)a6 + 232 * i), 1u) )
    {
      ServiceObject = -2147024809;
      v25 = 2887;
      goto LABEL_32;
    }
  }
  v61 = 0;
  ServiceObject = CAgentServiceManager::GetServiceObject(*(CAgentServiceManager **)(a1 + 480), a4, &v61);
  if ( ServiceObject < 0 )
  {
    v25 = 2892;
LABEL_32:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v25,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\ClientCallRecorder.cpp",
      (const char *)(unsigned int)ServiceObject,
      v55);
    goto LABEL_123;
  }
  v58 = 0;
  v26 = v61;
  ServiceObject = CSusService::GetAllowUninstall(v61, &v58);
  if ( ServiceObject < 0 )
  {
    v25 = 2895;
    goto LABEL_32;
  }
  if ( !v58 && a2 == 2 )
  {
    ServiceObject = -2145124312;
    v25 = 2898;
    goto LABEL_32;
  }
  if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)(a1 + 88) + 24LL))(a1 + 88) == 2 && a2 == 4 )
  {
    ServiceObject = -2145124281;
    v25 = 2902;
    goto LABEL_32;
  }
  v27 = (*((_DWORD *)v26 + 124) & 0x8000 | 0x6800u) >> 10;
  v61 = 0;
  v63 = 1;
  v58 = 0;
  v62 = 0;
  if ( hObject )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  v67 = *a4;
  ServiceObject = CClientCallRecorder::PrepareCallSecurityForUpdates(
                    (CClientCallRecorder *)a1,
                    v27,
                    &v67,
                    a5,
                    a6,
                    &v58,
                    &v62,
                    &v61,
                    v65,
                    &v63,
                    &hObject);
  v28 = v61;
  if ( ServiceObject < 0 )
  {
    v29 = 2928;
LABEL_42:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v29,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\ClientCallRecorder.cpp",
      (const char *)(unsigned int)ServiceObject,
      v56);
    goto LABEL_121;
  }
  if ( !*((_DWORD *)v61 + 1) || *(_DWORD *)v61 || *((_DWORD *)v61 + 2) )
  {
LABEL_55:
    *(_QWORD *)&v67.Data1 = lpMem;
    if ( lpMem )
    {
      lpMem = 0;
      v31 = 0;
      v60 = 0;
      ServiceObject = WuSmartPtr::XPtrBase<CCallerIdentity,WuSmartPtr::Policies::STPolicy<CCallerIdentity>>::ReleaseAndAlloc(&lpMem);
      v32 = (CCallerIdentity *)lpMem;
      if ( ServiceObject < 0 )
      {
        v33 = 2963;
LABEL_74:
        v38 = (unsigned int)ServiceObject;
LABEL_77:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v33,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\ClientCallRecorder.cpp",
          (const char *)v38,
          v56);
        if ( v31 )
          CloseHandle(v31);
        if ( v32 )
        {
          CCallerIdentity::~CCallerIdentity(v32);
          operator delete(v32, (const struct std::nothrow_t *)0xA8);
        }
        goto LABEL_121;
      }
      ServiceObject = DuplicateCallerToken(&v67, &v60);
      v31 = v60;
      if ( ServiceObject < 0 )
      {
        v33 = 2967;
        goto LABEL_74;
      }
      v39 = CCallerIdentity::Init(v32, v60, 1, 11, *(struct CSusSecurityChecker **)(a1 + 448));
      ServiceObject = v39;
      if ( v39 < 0 )
      {
        v38 = (unsigned int)v39;
        v33 = 2974;
        goto LABEL_77;
      }
      CCallerIdentity::~CCallerIdentity(v28);
      operator delete(v28, (const struct std::nothrow_t *)0xA8);
      v28 = v32;
      v61 = v32;
      if ( v31 )
        CloseHandle(v31);
    }
    v60 = 0;
    v40 = (CDeployCall *)operator new(0x528u, (const struct std::nothrow_t *)&std::nothrow);
    *(_QWORD *)&v67.Data1 = v40;
    if ( v40 )
      v41 = CDeployCall::CDeployCall(
              v40,
              *(struct ISusDatastore **)(a1 + 456),
              *(struct CAgentUpdateManager **)(a1 + 472),
              (struct CReporter *)(*(_QWORD *)(a1 + 448) + 2408LL),
              (struct ISubmitWorkItem *)((a1 + 96) & ((unsigned __int128)-(__int128)(unsigned __int64)a1 >> 64)),
              (struct ISusIdleTimer *)(*(_QWORD *)(a1 + 448) + 9992LL),
              (struct IUpdateDeploymentHasEnded *)((a1 + 120) & -(__int64)(a1 != 0)),
              (struct ISusRebootStatus *)((a1 + 88) & -(__int64)(a1 != 0)),
              (struct ISusServiceStatus *)((a1 + 128) & ((unsigned __int128)-(__int128)(unsigned __int64)a1 >> 64)),
              *(struct IWUUpdateDeploymentData **)(a1 + 584));
    else
      v41 = 0;
    v60 = v41;
    if ( !v41 )
    {
      ServiceObject = -2147024882;
      v42 = 2990;
LABEL_90:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v42,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\ClientCallRecorder.cpp",
        (const char *)(unsigned int)ServiceObject,
        v56);
LABEL_119:
      if ( v41 )
        (*(void (__fastcall **)(CDeployCall *, __int64))(*(_QWORD *)v41 + 16LL))(v41, 1);
      goto LABEL_121;
    }
    ServiceObject = CSusAsyncCall::GenerateExternalId(v41);
    if ( ServiceObject < 0 )
    {
      v42 = 2992;
      goto LABEL_90;
    }
    v44 = a8 & 0x80;
    if ( v62 )
    {
      if ( v58 )
        v45 = v44 != 0 ? 5 : 2;
      else
        v45 = (v44 != 0) + 3;
      *((_DWORD *)v41 + 266) = v45;
    }
    lpMem = 0;
    ServiceObject = CSusAsyncCallHelper::ValidateAndGetFinalSessionData(
                      (CSusAsyncCallHelper *)a5,
                      v64[0],
                      (const struct tagMatchingUpdate *const)&lpMem,
                      v43);
    v46 = lpMem;
    if ( ServiceObject >= 0 )
    {
      v82 = GUID_NULL;
      ServiceObject = CClientCallRecorder::CreateUpdateDeploymentSessionCFHost(
                        a1,
                        a2,
                        (__int64)v66,
                        a5,
                        *(__int64 *)v64,
                        a7,
                        (__int64)lpMem,
                        &v82);
      if ( ServiceObject >= 0 )
      {
        ServiceObject = CCallerIdentity::SetUpdateTargeting(v28, v68);
        if ( ServiceObject >= 0 )
        {
          ServiceObject = CCallerIdentity::SetDeviceTargeting(v28, v69);
          if ( ServiceObject >= 0 )
          {
            ServiceObject = CCallerIdentity::SetProductTargeting(v28, v70);
            if ( ServiceObject >= 0 )
            {
              v48 = v65;
              v57 = v71;
              v56 = a9;
              ServiceObject = CDeployCall::Init(v41, *(_QWORD *)&v72.Data1, v66, a8);
              if ( ServiceObject >= 0 )
              {
                EnterCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)(a1 + 488) + 8LL));
                v79 = 1;
                *((_DWORD *)v41 + 236) = 1;
                if ( *(_DWORD *)(a1 + 256) == 2 )
                {
                  ServiceObject = -2145124330;
                  wil::details::in1diag3::Return_HrMsg(
                    retaddr,
                    (void *)0xBED,
                    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\ClientCallRecorder.cpp",
                    (const char *)0x80240016LL,
                    (int)"Deployment rejected because mandatory reboot is needed",
                    v57);
                  goto LABEL_117;
                }
                v72 = *(struct _GUID *)((char *)v41 + 116);
                Trace::GuidToString::GuidToString((Trace::GuidToString *)v78, &v72);
                WUTrace(
                  0,
                  0,
                  1,
                  4,
                  0,
                  L"Beginning deployment of parallel work item. Deploy call internal id = %d, external id = %ws");
                CSusListIterator<CSusAsyncCall>::Append(a1 + 152, v41);
                v51 = CClientCallRecorder::AddCallToParallelDeploymentQueue((CClientCallRecorder *)a1, v50);
                ServiceObject = v51;
                if ( v51 >= 0 )
                {
                  *v73 = *(GUID *)((char *)v41 + 116);
                  *((_DWORD *)v41 + 7) = 1;
                  (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)v41 + 40) + 8LL))(*((_QWORD *)v41 + 40), 1);
                  ++*(_DWORD *)(a1 + 432);
                  v41 = 0;
                  v60 = 0;
                  if ( v79 )
                  {
                    LeaveCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)(a1 + 488) + 8LL));
                    v79 = 0;
                  }
                  CClientCallRecorder::AddRefReleaseCallback((CClientCallRecorder *)a1, v48, 1);
                  SetEvent(*(HANDLE *)(a1 + 576));
                  ServiceObject = 0;
                  goto LABEL_117;
                }
                v49 = (unsigned int)v51;
                v47 = 3065;
LABEL_113:
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)v47,
                  (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\ClientCallRecorder.cpp",
                  (const char *)v49,
                  v56);
LABEL_117:
                if ( v46 )
                  SusFree(v46);
                goto LABEL_119;
              }
              v47 = 3042;
            }
            else
            {
              v47 = 3026;
            }
          }
          else
          {
            v47 = 3025;
          }
        }
        else
        {
          v47 = 3024;
        }
      }
      else
      {
        v47 = 3022;
      }
    }
    else
    {
      v47 = 3013;
    }
    v49 = (unsigned int)ServiceObject;
    goto LABEL_113;
  }
  if ( a13 )
  {
    ServiceObject = -2145124250;
    v29 = 2935;
    goto LABEL_42;
  }
  if ( (v27 & 0x20) != 0 && *((_DWORD *)v61 + 32) )
  {
    switch ( a2 )
    {
      case 1u:
        v30 = L"Installing";
        break;
      case 2u:
        v30 = L"Uninstalling";
        break;
      case 4u:
        v30 = L"Reverting";
        break;
      case 8u:
        v30 = L"Commiting";
        break;
      default:
        v30 = L"Unknown";
        break;
    }
    WUTrace(0, 0, 1, 5, 0, L"Non-elevated admin user is requesting %ws of updates", v30);
    goto LABEL_55;
  }
  if ( v58 )
    goto LABEL_55;
  if ( (a8 & 3) != 0 )
  {
    v35 = a2 - 1;
    if ( !v35 )
    {
      v34 = L"Install";
      goto LABEL_71;
    }
    v36 = v35 - 1;
    if ( v36 )
    {
      v37 = v36 - 2;
      if ( v37 )
      {
        if ( v37 == 4 )
          v34 = L"Commit";
        else
          v34 = L"Unknown";
        goto LABEL_71;
      }
      goto LABEL_62;
    }
LABEL_69:
    v34 = L"Uninstall";
    goto LABEL_71;
  }
  if ( a2 == 2 )
    goto LABEL_69;
  if ( a2 != 4 )
    goto LABEL_55;
LABEL_62:
  v34 = (const wchar_t *)L"Revert";
LABEL_71:
  ServiceObject = -2147024891;
  wil::details::in1diag3::Return_HrMsg(
    retaddr,
    (void *)0xB86,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\ClientCallRecorder.cpp",
    (const char *)0x80070005LL,
    (int)"Non admin user is requesting invalid %ws type",
    (const char *)v34);
LABEL_121:
  if ( v28 )
  {
    CCallerIdentity::~CCallerIdentity(v28);
    operator delete(v28, (const struct std::nothrow_t *)0xA8);
  }
LABEL_123:
  if ( v79 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)(a1 + 488) + 8LL));
    v79 = 0;
  }
  v52 = hObject;
  if ( hObject )
  {
    ImpersonateLoggedOnUser(hObject);
    goto LABEL_127;
  }
LABEL_128:
  if ( v52 )
  {
    CloseHandle(v52);
    hObject = 0;
  }
  _InterlockedDecrement((volatile signed __int32 *)v81[0]);
  v53 = v81[1];
  if ( v81[1] )
  {
    CIdleTimerHelper::~CIdleTimerHelper(v81[1]);
    operator delete(v53, (const struct std::nothrow_t *)0x18);
  }
  return (unsigned int)ServiceObject;
}

```

## disassembly

```asm
0x180041250  push    rbp
0x180041252  push    rbx
0x180041253  push    rsi
0x180041254  push    rdi
0x180041255  push    r12
0x180041257  push    r13
0x180041259  push    r14
0x18004125b  push    r15
0x18004125d  lea     rbp, [rsp-0C8h]
0x180041265  sub     rsp, 1C8h
0x18004126c  mov     rax, cs:__security_cookie
0x180041273  xor     rax, rsp
0x180041276  mov     [rbp+100h+var_50], rax
0x18004127d  mov     rdi, r9
0x180041280  mov     [rbp+100h+var_148], r9
0x180041284  mov     r12, r8
0x180041287  mov     qword ptr [rbp+100h+var_110.Data1], r8
0x18004128b  mov     r15d, edx
0x18004128e  mov     r13, rcx
0x180041291  mov     rsi, [rbp+100h+arg_28]
0x180041298  mov     qword ptr [rbp+100h+var_158], rsi
0x18004129c  mov     r14, [rbp+100h+arg_50]
0x1800412a3  mov     [rbp+100h+var_150], r14
0x1800412a7  mov     rax, [rbp+100h+arg_58]
0x1800412ae  mov     [rbp+100h+lpMem], rax
0x1800412b2  mov     rax, [rbp+100h+arg_68]
0x1800412b9  mov     [rbp+100h+var_118], rax
0x1800412bd  mov     rax, [rbp+100h+arg_70]
0x1800412c4  mov     [rbp+100h+var_130], rax
0x1800412c8  mov     rax, [rbp+100h+arg_78]
0x1800412cf  mov     [rbp+100h+var_128], rax
0x1800412d3  mov     rax, [rbp+100h+arg_80]
0x1800412da  mov     [rbp+100h+var_120], rax
0x1800412de  mov     rbx, [rbp+100h+arg_88]
0x1800412e5  mov     [rbp+100h+var_100], rbx
0x1800412e9  xorps   xmm0, xmm0
0x1800412ec  movups  xmmword ptr [rbp+100h+var_70], xmm0
0x1800412f3  mov     r8, [rcx+1C0h]
0x1800412fa  add     r8, 2708h; struct ISusIdleTimer *
0x180041301  lea     rdx, [rcx+1D0h]; int *
0x180041308  lea     r9, aCclientcallrec_19; "CClientCallRecorder::BeginDeployUpdates"
0x18004130f  lea     rcx, [rbp+100h+var_70]; this
0x180041316  call    ??0CActiveCallerCounter@@QEAA@PEAJPEAVISusIdleTimer@@PEB_W@Z; CActiveCallerCounter::CActiveCallerCounter(long *,ISusIdleTimer *,wchar_t const *)
0x18004131b  nop
0x18004131c  mov     [rbp+100h+hObject], 0
0x180041327  mov     [rbp+100h+var_80], 0
0x18004132e  test    r14, r14
0x180041331  jnz     short loc_18004133A
0x180041333  mov     edx, 0B2Dh
0x180041338  jmp     short loc_180041344
0x18004133a  test    rbx, rbx
0x18004133d  jnz     short loc_18004134C
0x18004133f  mov     edx, 0B2Eh
0x180041344  mov     r14d, 80004003h
0x18004134a  jmp     short loc_1800413C3
0x18004134c  test    r12, r12
0x18004134f  jnz     short loc_18004135E
0x180041351  mov     r14d, 80070057h
0x180041357  mov     edx, 0B2Fh
0x18004135c  jmp     short loc_1800413C3
0x18004135e  mov     r12d, dword ptr [rbp+100h+arg_20]
0x180041365  test    r12d, r12d
0x180041368  jnz     short loc_180041377
0x18004136a  mov     r14d, 80070057h
0x180041370  mov     edx, 0B30h
0x180041375  jmp     short loc_1800413C3
0x180041377  test    rsi, rsi
0x18004137a  jnz     short loc_180041389
0x18004137c  mov     r14d, 80004003h
0x180041382  mov     edx, 0B31h
0x180041387  jmp     short loc_1800413C3
0x180041389  mov     rax, qword ptr cs:c_idSrvNone.Data1
0x180041390  cmp     rax, [rdi]
0x180041393  jnz     short loc_1800413AF
0x180041395  mov     rax, qword ptr cs:c_idSrvNone.Data4
0x18004139c  cmp     rax, [rdi+8]
0x1800413a0  jnz     short loc_1800413AF
0x1800413a2  mov     r14d, 80070057h
0x1800413a8  mov     edx, 0B32h
0x1800413ad  jmp     short loc_1800413C3
0x1800413af  mov     rcx, r13; this
0x1800413b2  call    ?PrepareBeforeAPICall@CClientCallRecorder@@AEAAJXZ; CClientCallRecorder::PrepareBeforeAPICall(void)
0x1800413b7  mov     r14d, eax
0x1800413ba  test    eax, eax
0x1800413bc  jns     short loc_1800413DE
0x1800413be  mov     edx, 0B34h; void *
0x1800413c3  mov     rcx, [rbp+108h]; this
0x1800413ca  mov     r9d, r14d; char *
0x1800413cd  lea     r8, aCW1SSrcClientE_27; "C:\\__w\\1\\s\\src\\Client\\Engine\\Age"...
0x1800413d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800413d9  jmp     loc_180041C81
0x1800413de  xorps   xmm0, xmm0
0x1800413e1  movups  [rbp+100h+var_F8], xmm0
0x1800413e5  movups  [rbp+100h+var_E8], xmm0
0x1800413e9  lea     rax, [rbp+100h+var_80]
0x1800413f0  mov     qword ptr [rbp+100h+var_F8], rax
0x1800413f4  mov     qword ptr [rbp+100h+var_F8+8], r13
0x1800413f8  lea     rax, [rbp+100h+hObject]
0x1800413ff  mov     qword ptr [rbp+100h+var_E8], rax
0x180041403  mov     byte ptr [rbp+100h+var_E8+8], 1
0x180041407  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18004140e  movdqu  xmmword ptr [rbx], xmm0
0x180041412  xor     ebx, ebx
0x180041414  test    r12d, r12d
0x180041417  jz      short loc_18004143A
0x180041419  mov     eax, ebx
0x18004141b  imul    rcx, rax, 0E8h
0x180041422  add     rcx, rsi; struct tagMatchingUpdate *
0x180041425  mov     edx, 1; unsigned int
0x18004142a  call    ?IsValidMatchingUpdate@@YAHAEBUtagMatchingUpdate@@K@Z; IsValidMatchingUpdate(tagMatchingUpdate const &,ulong)
0x18004142f  test    eax, eax
0x180041431  jz      short loc_180041463
0x180041433  inc     ebx
0x180041435  cmp     ebx, r12d
0x180041438  jb      short loc_180041419
0x18004143a  mov     [rbp+100h+var_168], 0
0x180041442  lea     r8, [rbp+100h+var_168]; struct CSusService **
0x180041446  mov     rdx, rdi; struct _GUID *
0x180041449  mov     rcx, [r13+1E0h]; this
0x180041450  call    ?GetServiceObject@CAgentServiceManager@@QEAAJAEBU_GUID@@PEAPEAVCSusService@@@Z; CAgentServiceManager::GetServiceObject(_GUID const &,CSusService * *)
0x180041455  mov     r14d, eax
0x180041458  test    eax, eax
0x18004145a  jns     short loc_180041470
0x18004145c  mov     edx, 0B4Ch
0x180041461  jmp     short loc_1800414D7
0x180041463  mov     r14d, 80070057h
0x180041469  mov     edx, 0B47h
0x18004146e  jmp     short loc_1800414D7
0x180041470  mov     [rbp+100h+var_180], 0
0x180041477  lea     rdx, [rbp+100h+var_180]; int *
0x18004147b  mov     rbx, [rbp+100h+var_168]
0x18004147f  mov     rcx, rbx; this
0x180041482  call    ?GetAllowUninstall@CSusService@@QEAAJPEAH@Z; CSusService::GetAllowUninstall(int *)
0x180041487  mov     r14d, eax
0x18004148a  test    eax, eax
0x18004148c  jns     short loc_180041495
0x18004148e  mov     edx, 0B4Fh
0x180041493  jmp     short loc_1800414D7
0x180041495  xor     r14d, r14d
0x180041498  cmp     [rbp+100h+var_180], r14d
0x18004149c  jnz     short loc_1800414B1
0x18004149e  cmp     r15d, 2
0x1800414a2  jnz     short loc_1800414B1
0x1800414a4  mov     r14d, 80240028h
0x1800414aa  mov     edx, 0B52h
0x1800414af  jmp     short loc_1800414D7
0x1800414b1  lea     rcx, [r13+58h]
0x1800414b5  mov     rax, [rcx]
0x1800414b8  mov     rax, [rax+18h]
0x1800414bc  call    _guard_dispatch_icall
0x1800414c1  cmp     eax, 2
0x1800414c4  jnz     short loc_1800414F2
0x1800414c6  cmp     r15d, 4
0x1800414ca  jnz     short loc_1800414F2
0x1800414cc  mov     r14d, 80240047h
0x1800414d2  mov     edx, 0B56h; void *
0x1800414d7  mov     rcx, [rbp+108h]; this
0x1800414de  mov     r9d, r14d; char *
0x1800414e1  lea     r8, aCW1SSrcClientE_27; "C:\\__w\\1\\s\\src\\Client\\Engine\\Age"...
0x1800414e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800414ed  jmp     loc_180041C4E
0x1800414f2  mov     ebx, [rbx+1F0h]
0x1800414f8  and     ebx, 8000h
0x1800414fe  or      ebx, 6800h
0x180041504  shr     ebx, 0Ah
0x180041507  mov     [rbp+100h+var_168], r14
0x18004150b  mov     [rbp+100h+var_15C], 1
0x180041512  mov     [rbp+100h+var_180], r14d
0x180041516  mov     [rbp+100h+var_160], r14d
0x18004151a  mov     rcx, [rbp+100h+hObject]; hObject
0x180041521  test    rcx, rcx
0x180041524  jz      short loc_180041533
0x180041526  call    cs:__imp_CloseHandle
0x18004152c  mov     [rbp+100h+hObject], r14
0x180041533  movups  xmm0, xmmword ptr [rdi]
0x180041536  movdqu  xmmword ptr [rbp+100h+var_140.Data1], xmm0
0x18004153b  lea     rax, [rbp+100h+hObject]
0x180041542  mov     [rsp+200h+var_1B0], rax; void **
0x180041547  lea     rax, [rbp+100h+var_15C]
0x18004154b  mov     [rsp+200h+var_1B8], rax; int *
0x180041550  mov     rax, [rbp+100h+var_150]
0x180041554  mov     [rsp+200h+var_1C0], rax; struct IUnknown *
0x180041559  lea     rax, [rbp+100h+var_168]
0x18004155d  mov     [rsp+200h+var_1C8], rax; struct CCallerIdentity **
0x180041562  lea     rax, [rbp+100h+var_160]
0x180041566  mov     [rsp+200h+var_1D0], rax; int *
0x18004156b  lea     rax, [rbp+100h+var_180]
0x18004156f  mov     [rsp+200h+var_1D8], rax; int *
0x180041574  mov     [rsp+200h+var_1E0], rsi; int
0x180041579  mov     r9d, r12d; unsigned int
0x18004157c  lea     r8, [rbp+100h+var_140]; struct _GUID
0x180041580  mov     edx, ebx; unsigned int
0x180041582  mov     rcx, r13; this
0x180041585  call    ?PrepareCallSecurityForUpdates@CClientCallRecorder@@AEAAJKU_GUID@@KQEBUtagMatchingUpdate@@PEAH2PEAPEAVCCallerIdentity@@PEAUIUnknown@@2PEAPEAX@Z; CClientCallRecorder::PrepareCallSecurityForUpdates(ulong,_GUID,ulong,tagMatchingUpdate const * const,int *,int *,CCallerIdentity * *,IUnknown *,int *,void * *)
0x18004158a  mov     r14d, eax
0x18004158d  mov     rsi, [rbp+100h+var_168]
0x180041591  test    eax, eax
0x180041593  jns     short loc_18004159C
0x180041595  mov     edx, 0B70h
0x18004159a  jmp     short loc_1800415CE
0x18004159c  cmp     dword ptr [rsi+4], 0
0x1800415a0  jz      loc_18004166C
0x1800415a6  cmp     dword ptr [rsi], 0
0x1800415a9  jnz     loc_18004166C
0x1800415af  cmp     dword ptr [rsi+8], 0
0x1800415b3  jnz     loc_18004166C
0x1800415b9  cmp     [rbp+100h+arg_60], 0
0x1800415c1  jz      short loc_1800415E9
0x1800415c3  mov     r14d, 80240066h
0x1800415c9  mov     edx, 0B77h; void *
0x1800415ce  mov     rcx, [rbp+108h]; this
0x1800415d5  mov     r9d, r14d; char *
0x1800415d8  lea     r8, aCW1SSrcClientE_27; "C:\\__w\\1\\s\\src\\Client\\Engine\\Age"...
0x1800415df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800415e4  jmp     loc_180041C33
0x1800415e9  test    bl, 20h
0x1800415ec  jz      loc_1800416AD
0x1800415f2  cmp     dword ptr [rsi+80h], 0
0x1800415f9  jz      loc_1800416AD
0x1800415ff  mov     ecx, r15d
0x180041602  sub     ecx, 1
0x180041605  jz      short loc_18004163A
0x180041607  sub     ecx, 1
0x18004160a  jz      short loc_180041631
0x18004160c  sub     ecx, 2
0x18004160f  jz      short loc_180041628
0x180041611  cmp     ecx, 4
0x180041614  jz      short loc_18004161F
0x180041616  lea     rax, aUnknown_3; "Unknown"
0x18004161d  jmp     short loc_180041641
0x18004161f  lea     rax, aCommiting; "Commiting"
0x180041626  jmp     short loc_180041641
0x180041628  lea     rax, aReverting; "Reverting"
0x18004162f  jmp     short loc_180041641
0x180041631  lea     rax, aUninstalling; "Uninstalling"
0x180041638  jmp     short loc_180041641
0x18004163a  lea     rax, aInstalling; "Installing"
0x180041641  mov     [rsp+200h+var_1D0], rax
0x180041646  lea     rax, aNonElevatedAdm_0; "Non-elevated admin user is requesting %"...
0x18004164d  mov     [rsp+200h+var_1D8], rax
0x180041652  mov     [rsp+200h+var_1E0], 0
0x18004165b  xor     edx, edx
0x18004165d  xor     ecx, ecx
0x18004165f  lea     r9d, [rdx+5]
0x180041663  lea     r8d, [rdx+1]
0x180041667  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18004166c  mov     rax, [rbp+100h+lpMem]
0x180041670  mov     qword ptr [rbp+100h+var_140.Data1], rax
0x180041674  test    rax, rax
0x180041677  jz      loc_180041805
0x18004167d  mov     [rbp+100h+lpMem], 0
0x180041685  xor     ebx, ebx
0x180041687  mov     [rbp+100h+var_170], rbx
0x18004168b  lea     rcx, [rbp+100h+lpMem]
0x18004168f  call    ?ReleaseAndAlloc@?$XPtrBase@VCCallerIdentity@@U?$STPolicy@VCCallerIdentity@@@Policies@WuSmartPtr@@@WuSmartPtr@@QEAAJXZ; WuSmartPtr::XPtrBase<CCallerIdentity,WuSmartPtr::Policies::STPolicy<CCallerIdentity>>::ReleaseAndAlloc(void)
0x180041694  mov     r14d, eax
0x180041697  mov     rdi, [rbp+100h+lpMem]
0x18004169b  test    eax, eax
0x18004169d  jns     loc_180041742
0x1800416a3  mov     edx, 0B93h
0x1800416a8  jmp     loc_18004175F
0x1800416ad  cmp     [rbp+100h+var_180], 0
0x1800416b1  jnz     short loc_18004166C
0x1800416b3  test    byte ptr [rbp+100h+arg_38], 3
0x1800416ba  jnz     short loc_1800416D1
0x1800416bc  cmp     r15d, 2
0x1800416c0  jz      short loc_1800416FB
0x1800416c2  cmp     r15d, 4
0x1800416c6  jnz     short loc_18004166C
0x1800416c8  lea     rax, aRevert; "Revert"
0x1800416cf  jmp     short loc_18004170B
0x1800416d1  sub     r15d, 1
0x1800416d5  jz      short loc_180041704
0x1800416d7  sub     r15d, 1
0x1800416db  jz      short loc_1800416FB
0x1800416dd  sub     r15d, 2
0x1800416e1  jz      short loc_1800416C8
0x1800416e3  cmp     r15d, 4
0x1800416e7  jz      short loc_1800416F2
0x1800416e9  lea     rax, aUnknown_3; "Unknown"
0x1800416f0  jmp     short loc_18004170B
0x1800416f2  lea     rax, aCommit; "Commit"
0x1800416f9  jmp     short loc_18004170B
0x1800416fb  lea     rax, aUninstall_0; "Uninstall"
0x180041702  jmp     short loc_18004170B
0x180041704  lea     rax, aInstall; "Install"
0x18004170b  mov     rcx, [rbp+108h]; this
0x180041712  mov     [rsp+200h+var_1D8], rax; char *
0x180041717  lea     rax, aNonAdminUserIs_1; "Non admin user is requesting invalid %w"...
0x18004171e  mov     [rsp+200h+var_1E0], rax; int
0x180041723  mov     r14d, 80070005h
0x180041729  mov     r9d, r14d; char *
0x18004172c  lea     r8, aCW1SSrcClientE_27; "C:\\__w\\1\\s\\src\\Client\\Engine\\Age"...
0x180041733  mov     edx, 0B86h; void *
0x180041738  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004173d  jmp     loc_180041C33
0x180041742  lea     rdx, [rbp+100h+var_170]
0x180041746  lea     rcx, [rbp+100h+var_140]
0x18004174a  call    DuplicateCallerToken
0x18004174f  mov     r14d, eax
  ... truncated ...
```
