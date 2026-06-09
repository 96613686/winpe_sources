# CClientCallRecorder::BeginDeployUpdates_Legacy(tagDSDeploymentOperation,wchar_t const *,_GUID const &,ulong,tagMatchingUpdate const * const,tagDeploymentOperationPriority,ulong,ulong,unsigned __int64,ISusDeploymentCallback *,unsigned __int64,unsigned __int64,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,_GUID *)

- ea: `0x180041d00`
- end: `0x180042746`
- name: `?BeginDeployUpdates_Legacy@CClientCallRecorder@@UEAAJW4tagDSDeploymentOperation@@PEB_WAEBU_GUID@@KQEBUtagMatchingUpdate@@W4tagDeploymentOperationPriority@@KK_KPEAUISusDeploymentCallback@@5511111PEAU3@@Z`
- size: `2630`
- prototype: ``
- caller_count: `0`
- callee_count: `29`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18000def4`
- `0x18001898c`
- `0x18003d95c`
- `0x18003efbc`
- `0x180041d00`
- `0x18004a3d8`
- `0x18004a4a0`
- `0x18004e534`
- `0x18004f840`
- `0x180052c68`
- `0x18005c79c`
- `0x180062770`
- `0x1800c880c`
- `0x1800d5778`
- `0x1800d60ac`
- `0x180105194`
- `0x1801051cc`
- `0x180106214`
- `0x180106274`
- `0x1801062d4`
- `0x180106dec`
- `0x180119e48`
- `0x18011b63c`
- `0x18012b618`
- `0x18012bed4`
- `0x180238960`
- `0x180238984`
- `0x180239110`
- `0x180240cc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004266b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004266b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180042530`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180042530`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004264a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180042689`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004264a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180042689`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180041fef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004226a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800422bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800426b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180041fef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004226a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800422bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800426b3`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800426a1`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800426a1`

## string_xrefs

- `0x1800421bb`: `Install`
- `0x1800421b2`: `Uninstall`
- `0x1800421a9`: `Commit`
- `0x18004224e`: `C:\__w\1\s\src\Client\Engine\Agent\ClientCallRecorder.cpp`
- `0x1800425f0`: `C:\__w\1\s\src\Client\Engine\Agent\ClientCallRecorder.cpp`
- `0x18004210b`: `Non-elevated admin user is requesting %ws of updates`
- `0x180041dc0`: `CClientCallRecorder::BeginDeployUpdates_Legacy`
- `0x1800420ff`: `Installing`
- `0x1800420f6`: `Uninstalling`
- `0x1800420e4`: `Commiting`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CClientCallRecorder::BeginDeployUpdates_Legacy(
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
        CDeployCall *a12,
        __int64 a13,
        __int64 a14,
        __int64 a15,
        wchar_t *a16,
        wchar_t *a17,
        wchar_t *a18,
        GUID *a19)
{
  CCallerIdentity *v22; // r14
  CDeployCall *v23; // rbx
  int ServiceObject; // r15d
  __int64 v25; // rdx
  int v26; // esi
  struct tagMatchingUpdate *v27; // rdx
  unsigned int i; // edi
  __int64 v29; // rdi
  unsigned int v30; // edi
  const wchar_t *v31; // rax
  HANDLE v32; // rdi
  CCallerIdentity *v33; // rsi
  __int64 v34; // rdx
  const wchar_t *v35; // rax
  unsigned int v36; // r12d
  unsigned int v37; // r12d
  unsigned int v38; // r12d
  __int64 v39; // r9
  unsigned __int64 v40; // r9
  int v41; // eax
  CDeployCall *v42; // rdi
  int ExternalId; // eax
  int v44; // eax
  int v45; // eax
  struct IUnknown *v46; // r12
  const struct CDeployCall *v47; // rdx
  HANDLE v48; // rcx
  CIdleTimerHelper *v49; // rbx
  int v51; // [rsp+20h] [rbp-F0h]
  int v52; // [rsp+90h] [rbp-80h] BYREF
  HANDLE v53; // [rsp+98h] [rbp-78h] BYREF
  int v54; // [rsp+A0h] [rbp-70h] BYREF
  int v55; // [rsp+A4h] [rbp-6Ch] BYREF
  struct tagMatchingUpdate *v56; // [rsp+A8h] [rbp-68h]
  CCallerIdentity *v57; // [rsp+B0h] [rbp-60h] BYREF
  struct _GUID *v58; // [rsp+B8h] [rbp-58h]
  struct IUnknown *v59; // [rsp+C0h] [rbp-50h]
  struct _GUID v60; // [rsp+D0h] [rbp-40h] BYREF
  __int64 v61; // [rsp+E0h] [rbp-30h]
  __int64 v62; // [rsp+E8h] [rbp-28h]
  GUID *v63; // [rsp+F0h] [rbp-20h]
  CDeployCall *v64; // [rsp+F8h] [rbp-18h]
  CDeployCall *v65; // [rsp+100h] [rbp-10h] BYREF
  CDeployCall *v66; // [rsp+108h] [rbp-8h]
  wchar_t *v67; // [rsp+110h] [rbp+0h]
  wchar_t *v68; // [rsp+118h] [rbp+8h]
  wchar_t *v69; // [rsp+120h] [rbp+10h]
  struct _GUID v70; // [rsp+128h] [rbp+18h] BYREF
  int *v71; // [rsp+138h] [rbp+28h]
  __int64 v72; // [rsp+140h] [rbp+30h]
  HANDLE *p_hObject; // [rsp+148h] [rbp+38h]
  __int64 v74; // [rsp+150h] [rbp+40h]
  char v75[80]; // [rsp+160h] [rbp+50h] BYREF
  int v76; // [rsp+1B0h] [rbp+A0h] BYREF
  HANDLE hObject; // [rsp+1B8h] [rbp+A8h] BYREF
  CIdleTimerHelper *v78[2]; // [rsp+1C0h] [rbp+B0h] BYREF
  GUID v79; // [rsp+1D0h] [rbp+C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+128h]

  v58 = a4;
  v62 = a3;
  v56 = a6;
  v59 = a11;
  v66 = a12;
  v61 = a14;
  *(_QWORD *)&v70.Data1 = a15;
  v67 = a16;
  v68 = a17;
  v69 = a18;
  v63 = a19;
  *(_OWORD *)v78 = 0;
  CActiveCallerCounter::CActiveCallerCounter(
    (CActiveCallerCounter *)v78,
    (int *)(a1 + 464),
    (struct ISusIdleTimer *)(*(_QWORD *)(a1 + 448) + 9992LL),
    L"CClientCallRecorder::BeginDeployUpdates_Legacy");
  v22 = 0;
  v57 = 0;
  v23 = 0;
  v64 = 0;
  v55 = 1;
  hObject = 0;
  v52 = 0;
  v54 = 0;
  *(_QWORD *)&v60.Data1 = 0;
  LODWORD(v53) = 0;
  v76 = 0;
  v65 = a12;
  v79 = GUID_NULL;
  v74 = 1;
  v71 = &v76;
  v72 = a1;
  p_hObject = &hObject;
  ServiceObject = CClientCallRecorder::PrepareBeforeAPICall((CClientCallRecorder *)a1);
  if ( ServiceObject < 0 )
  {
    v25 = 3142;
LABEL_68:
    v39 = (unsigned int)ServiceObject;
LABEL_108:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v25,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\ClientCallRecorder.cpp",
      (const char *)v39,
      v51);
    goto LABEL_112;
  }
  if ( !v59 )
  {
    ServiceObject = -2147467261;
    v25 = 3143;
    goto LABEL_68;
  }
  if ( !v63 )
  {
    ServiceObject = -2147467261;
    v25 = 3144;
    goto LABEL_68;
  }
  if ( !v62 )
  {
    ServiceObject = -2147024809;
    v25 = 3145;
    goto LABEL_68;
  }
  v26 = a5;
  if ( !a5 )
  {
    ServiceObject = -2147024809;
    v25 = 3146;
    goto LABEL_68;
  }
  v27 = v56;
  if ( !v56 )
  {
    ServiceObject = -2147467261;
    v25 = 3147;
    goto LABEL_68;
  }
  if ( *(_QWORD *)&c_idSrvNone.Data1 == *(_QWORD *)&a4->Data1 && *(_QWORD *)c_idSrvNone.Data4 == *(_QWORD *)a4->Data4 )
  {
    ServiceObject = -2147024809;
    v25 = 3148;
    goto LABEL_68;
  }
  *v63 = GUID_NULL;
  for ( i = 0; i < a5; ++i )
  {
    if ( !(unsigned int)IsValidMatchingUpdate((struct tagMatchingUpdate *)((char *)v27 + 232 * i), 1u) )
    {
      ServiceObject = -2147024809;
      v25 = 3154;
      goto LABEL_68;
    }
    v27 = v56;
  }
  ServiceObject = CAgentServiceManager::GetServiceObject(
                    *(CAgentServiceManager **)(a1 + 480),
                    v58,
                    (struct CSusService **)&v60);
  if ( ServiceObject < 0 )
  {
    v25 = 3158;
    goto LABEL_68;
  }
  v29 = *(_QWORD *)&v60.Data1;
  ServiceObject = CSusService::GetAllowUninstall(*(CSusService **)&v60.Data1, (int *)&v53);
  if ( ServiceObject < 0 )
  {
    v25 = 3160;
    goto LABEL_68;
  }
  if ( !(_DWORD)v53 && a2 == 2 )
  {
    ServiceObject = -2145124312;
    v25 = 3163;
    goto LABEL_68;
  }
  if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)(a1 + 88) + 24LL))(a1 + 88) == 2 && a2 == 4 )
  {
    ServiceObject = -2145124281;
    v25 = 3167;
    goto LABEL_68;
  }
  v30 = (*(_DWORD *)(v29 + 496) & 0x8000 | 0x6800u) >> 10;
  if ( hObject )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  v60 = *v58;
  ServiceObject = CClientCallRecorder::PrepareCallSecurityForUpdates(
                    (CClientCallRecorder *)a1,
                    v30,
                    &v60,
                    a5,
                    v56,
                    &v52,
                    &v54,
                    &v57,
                    v59,
                    &v55,
                    &hObject);
  v22 = v57;
  if ( ServiceObject < 0 )
  {
    v25 = 3184;
    goto LABEL_68;
  }
  if ( *((_DWORD *)v57 + 1) && !*(_DWORD *)v57 && !*((_DWORD *)v57 + 2) )
  {
    if ( a13 )
    {
      ServiceObject = -2145124250;
      v25 = 3191;
      goto LABEL_68;
    }
    if ( (v30 & 0x20) != 0 && *((_DWORD *)v57 + 32) )
    {
      switch ( a2 )
      {
        case 1u:
          v31 = L"Installing";
          break;
        case 2u:
          v31 = L"Uninstalling";
          break;
        case 4u:
          v31 = L"Reverting";
          break;
        case 8u:
          v31 = L"Commiting";
          break;
        default:
          v31 = L"Unknown";
          break;
      }
      WUTrace(0, 0, 1, 5, 0, L"Non-elevated admin user is requesting %ws of updates", v31);
      goto LABEL_51;
    }
    if ( v52 )
      goto LABEL_51;
    if ( (a8 & 3) != 0 )
    {
      v36 = a2 - 1;
      if ( !v36 )
      {
        v35 = L"Install";
        goto LABEL_67;
      }
      v37 = v36 - 1;
      if ( v37 )
      {
        v38 = v37 - 2;
        if ( v38 )
        {
          if ( v38 == 4 )
            v35 = L"Commit";
          else
            v35 = L"Unknown";
          goto LABEL_67;
        }
        goto LABEL_58;
      }
    }
    else if ( a2 != 2 )
    {
      if ( a2 != 4 )
        goto LABEL_51;
LABEL_58:
      v35 = (const wchar_t *)L"Revert";
LABEL_67:
      WUTrace(0, 0, 1, 5, 0, L"Non admin user is requesting invalid %ws type", v35);
      ServiceObject = -2147024891;
      v25 = 3208;
      goto LABEL_68;
    }
    v35 = L"Uninstall";
    goto LABEL_67;
  }
LABEL_51:
  if ( v66 )
  {
    *(_QWORD *)&v60.Data1 = 0;
    v32 = 0;
    v53 = 0;
    ServiceObject = WuSmartPtr::XPtrBase<CCallerIdentity,WuSmartPtr::Policies::STPolicy<CCallerIdentity>>::ReleaseAndAlloc(&v60);
    v33 = *(CCallerIdentity **)&v60.Data1;
    if ( ServiceObject < 0 )
    {
      v34 = 3219;
LABEL_71:
      v40 = (unsigned int)ServiceObject;
LABEL_74:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v34,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\ClientCallRecorder.cpp",
        (const char *)v40,
        v51);
      if ( v32 )
        CloseHandle(v32);
      if ( v33 )
      {
        CCallerIdentity::~CCallerIdentity(v33);
        operator delete(v33, (const struct std::nothrow_t *)0xA8);
      }
      goto LABEL_112;
    }
    ServiceObject = DuplicateCallerToken(&v65, &v53);
    v32 = v53;
    if ( ServiceObject < 0 )
    {
      v34 = 3223;
      goto LABEL_71;
    }
    v41 = CCallerIdentity::Init(v33, v53, 1, 11, *(struct CSusSecurityChecker **)(a1 + 448));
    ServiceObject = v41;
    if ( v41 < 0 )
    {
      v40 = (unsigned int)v41;
      v34 = 3230;
      goto LABEL_74;
    }
    CCallerIdentity::~CCallerIdentity(v22);
    operator delete(v22, (const struct std::nothrow_t *)0xA8);
    v22 = v33;
    v57 = v33;
    if ( v32 )
      CloseHandle(v32);
    v26 = a5;
  }
  v42 = (CDeployCall *)operator new(0x528u, (const struct std::nothrow_t *)&std::nothrow);
  v65 = v42;
  if ( v42 )
    v23 = CDeployCall::CDeployCall(
            v42,
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
    v23 = 0;
  v64 = v23;
  if ( !v23 )
  {
    ServiceObject = -2147024882;
    v39 = 2147942414LL;
    v25 = 3245;
    goto LABEL_108;
  }
  ExternalId = CSusAsyncCall::GenerateExternalId(v23);
  ServiceObject = ExternalId;
  if ( ExternalId < 0 )
  {
    v25 = 3247;
LABEL_107:
    v39 = (unsigned int)ExternalId;
    goto LABEL_108;
  }
  v44 = a8 & 0x80;
  if ( v54 )
  {
    if ( v52 )
      v45 = v44 != 0 ? 5 : 2;
    else
      v45 = (v44 != 0) + 3;
    *((_DWORD *)v23 + 266) = v45;
  }
  ExternalId = CClientCallRecorder::CreateUpdateDeploymentSessionCFHost(
                 a1,
                 a2,
                 (__int64)v58,
                 v26,
                 (__int64)v56,
                 a7,
                 v61,
                 &v79);
  ServiceObject = ExternalId;
  if ( ExternalId < 0 )
  {
    v25 = 3271;
    goto LABEL_107;
  }
  ExternalId = CCallerIdentity::SetUpdateTargeting(v22, v67);
  ServiceObject = ExternalId;
  if ( ExternalId < 0 )
  {
    v25 = 3273;
    goto LABEL_107;
  }
  ExternalId = CCallerIdentity::SetDeviceTargeting(v22, v68);
  ServiceObject = ExternalId;
  if ( ExternalId < 0 )
  {
    v25 = 3274;
    goto LABEL_107;
  }
  ExternalId = CCallerIdentity::SetProductTargeting(v22, v69);
  ServiceObject = ExternalId;
  if ( ExternalId < 0 )
  {
    v25 = 3275;
    goto LABEL_107;
  }
  v46 = v59;
  v51 = a9;
  ExternalId = CDeployCall::Init_Legacy(v23, v62, v58, a8);
  ServiceObject = ExternalId;
  if ( ExternalId < 0 )
  {
    v25 = 3292;
    goto LABEL_107;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)(a1 + 488) + 8LL));
  v76 = 1;
  *((_DWORD *)v23 + 236) = 1;
  if ( *(_DWORD *)(a1 + 256) == 2 )
  {
    WUTrace(0, 0, 1, 4, 0, L"Deployment rejected because mandatory reboot is needed");
    ServiceObject = -2145124330;
    v39 = 2149842966LL;
    v25 = 3304;
    goto LABEL_108;
  }
  v70 = *(struct _GUID *)((char *)v23 + 116);
  Trace::GuidToString::GuidToString((Trace::GuidToString *)v75, &v70);
  WUTrace(0, 0, 1, 4, 0, L"Beginning deployment of parallel work item. Deploy call internal id = %d, external id = %ws");
  CSusListIterator<CSusAsyncCall>::Append(a1 + 152, v23);
  ExternalId = CClientCallRecorder::AddCallToParallelDeploymentQueue((CClientCallRecorder *)a1, v47);
  ServiceObject = ExternalId;
  if ( ExternalId < 0 )
  {
    v25 = 3316;
    goto LABEL_107;
  }
  *v63 = *(GUID *)((char *)v23 + 116);
  *((_DWORD *)v23 + 7) = 1;
  (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)v23 + 40) + 8LL))(*((_QWORD *)v23 + 40), 1);
  ++*(_DWORD *)(a1 + 432);
  v23 = 0;
  v64 = 0;
  if ( v76 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)(a1 + 488) + 8LL));
    v76 = 0;
  }
  CClientCallRecorder::AddRefReleaseCallback((CClientCallRecorder *)a1, v46, 1);
  SetEvent(*(HANDLE *)(a1 + 576));
  ServiceObject = 0;
LABEL_112:
  if ( v76 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)(a1 + 488) + 8LL));
    v76 = 0;
  }
  v48 = hObject;
  if ( hObject )
  {
    ImpersonateLoggedOnUser(hObject);
    v48 = hObject;
  }
  if ( v48 )
  {
    CloseHandle(v48);
    hObject = 0;
  }
  if ( v23 )
    (*(void (__fastcall **)(CDeployCall *, __int64))(*(_QWORD *)v23 + 16LL))(v23, 1);
  if ( v22 )
  {
    CCallerIdentity::~CCallerIdentity(v22);
    operator delete(v22, (const struct std::nothrow_t *)0xA8);
  }
  _InterlockedDecrement((volatile signed __int32 *)v78[0]);
  v49 = v78[1];
  if ( v78[1] )
  {
    CIdleTimerHelper::~CIdleTimerHelper(v78[1]);
    operator delete(v49, (const struct std::nothrow_t *)0x18);
  }
  return (unsigned int)ServiceObject;
}

```

## disassembly

```asm
0x180041d00  push    rbp
0x180041d02  push    rbx
0x180041d03  push    rsi
0x180041d04  push    rdi
0x180041d05  push    r12
0x180041d07  push    r13
0x180041d09  push    r14
0x180041d0b  push    r15
0x180041d0d  lea     rbp, [rsp-0E8h]
0x180041d15  sub     rsp, 1F8h
0x180041d1c  mov     rax, cs:__security_cookie
0x180041d23  xor     rax, rsp
0x180041d26  mov     [rbp+120h+var_50], rax
0x180041d2d  mov     rdi, r9
0x180041d30  mov     [rbp+120h+var_178], r9
0x180041d34  mov     [rbp+120h+var_148], r8
0x180041d38  mov     r12d, edx
0x180041d3b  mov     r13, rcx
0x180041d3e  mov     rax, [rbp+120h+arg_28]
0x180041d45  mov     [rbp+120h+var_188], rax
0x180041d49  mov     rax, [rbp+120h+arg_50]
0x180041d50  mov     [rbp+120h+var_170], rax
0x180041d54  mov     rsi, [rbp+120h+arg_58]
0x180041d5b  mov     [rbp+120h+var_128], rsi
0x180041d5f  mov     rax, [rbp+120h+arg_68]
0x180041d66  mov     [rbp+120h+var_150], rax
0x180041d6a  mov     rax, [rbp+120h+arg_70]
0x180041d71  mov     qword ptr [rbp+120h+var_108.Data1], rax
0x180041d75  mov     rax, [rbp+120h+arg_78]
0x180041d7c  mov     [rbp+120h+var_120], rax
0x180041d80  mov     rax, [rbp+120h+arg_80]
0x180041d87  mov     [rbp+120h+var_118], rax
0x180041d8b  mov     rax, [rbp+120h+arg_88]
0x180041d92  mov     [rbp+120h+var_110], rax
0x180041d96  mov     rax, [rbp+120h+arg_90]
0x180041d9d  mov     [rbp+120h+var_140], rax
0x180041da1  xorps   xmm0, xmm0
0x180041da4  movups  xmmword ptr [rbp+120h+var_70], xmm0
0x180041dab  mov     r8, [rcx+1C0h]
0x180041db2  add     r8, 2708h; struct ISusIdleTimer *
0x180041db9  lea     rdx, [rcx+1D0h]; int *
0x180041dc0  lea     r9, aCclientcallrec_16; "CClientCallRecorder::BeginDeployUpdates"...
0x180041dc7  lea     rcx, [rbp+120h+var_70]; this
0x180041dce  call    ??0CActiveCallerCounter@@QEAA@PEAJPEAVISusIdleTimer@@PEB_W@Z; CActiveCallerCounter::CActiveCallerCounter(long *,ISusIdleTimer *,wchar_t const *)
0x180041dd3  nop
0x180041dd4  xor     eax, eax
0x180041dd6  mov     r14d, eax
0x180041dd9  mov     [rbp+120h+var_180], rax
0x180041ddd  mov     ebx, eax
0x180041ddf  mov     [rbp+120h+var_138], rax
0x180041de3  mov     [rbp+120h+var_18C], 1
0x180041dea  mov     [rbp+120h+hObject], rax
0x180041df1  mov     [rbp+120h+var_1A0], eax
0x180041df4  mov     [rbp+120h+var_190], eax
0x180041df7  mov     qword ptr [rbp+120h+var_160.Data1], rax
0x180041dfb  mov     dword ptr [rbp+120h+var_198], eax
0x180041dfe  mov     [rbp+120h+var_80], eax
0x180041e04  mov     [rbp+120h+var_130], rsi
0x180041e08  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180041e0f  movdqu  [rbp+120h+var_60], xmm0
0x180041e17  xorps   xmm1, xmm1
0x180041e1a  movups  [rbp+120h+var_F8], xmm1
0x180041e1e  movups  [rbp+120h+var_E8], xmm1
0x180041e22  lea     rax, [rbp+120h+var_80]
0x180041e29  mov     qword ptr [rbp+120h+var_F8], rax
0x180041e2d  mov     qword ptr [rbp+120h+var_F8+8], r13
0x180041e31  lea     rax, [rbp+120h+hObject]
0x180041e38  mov     qword ptr [rbp+120h+var_E8], rax
0x180041e3c  mov     byte ptr [rbp+120h+var_E8+8], 1
0x180041e40  mov     rcx, r13; this
0x180041e43  call    ?PrepareBeforeAPICall@CClientCallRecorder@@AEAAJXZ; CClientCallRecorder::PrepareBeforeAPICall(void)
0x180041e48  mov     r15d, eax
0x180041e4b  test    eax, eax
0x180041e4d  jns     short loc_180041E59
0x180041e4f  mov     edx, 0C46h
0x180041e54  jmp     loc_1800421F4
0x180041e59  cmp     [rbp+120h+var_170], 0
0x180041e5e  jnz     short loc_180041E70
0x180041e60  mov     r15d, 80004003h
0x180041e66  mov     edx, 0C47h
0x180041e6b  jmp     loc_1800421F4
0x180041e70  mov     rcx, [rbp+120h+var_140]
0x180041e74  test    rcx, rcx
0x180041e77  jnz     short loc_180041E89
0x180041e79  mov     r15d, 80004003h
0x180041e7f  mov     edx, 0C48h
0x180041e84  jmp     loc_1800421F4
0x180041e89  cmp     [rbp+120h+var_148], 0
0x180041e8e  jnz     short loc_180041EA0
0x180041e90  mov     r15d, 80070057h
0x180041e96  mov     edx, 0C49h
0x180041e9b  jmp     loc_1800421F4
0x180041ea0  mov     esi, [rbp+120h+arg_20]
0x180041ea6  test    esi, esi
0x180041ea8  jnz     short loc_180041EBA
0x180041eaa  mov     r15d, 80070057h
0x180041eb0  mov     edx, 0C4Ah
0x180041eb5  jmp     loc_1800421F4
0x180041eba  mov     rdx, [rbp+120h+var_188]
0x180041ebe  test    rdx, rdx
0x180041ec1  jnz     short loc_180041ED3
0x180041ec3  mov     r15d, 80004003h
0x180041ec9  mov     edx, 0C4Bh
0x180041ece  jmp     loc_1800421F4
0x180041ed3  mov     rax, qword ptr cs:c_idSrvNone.Data1
0x180041eda  cmp     rax, [rdi]
0x180041edd  jnz     short loc_180041EFC
0x180041edf  mov     rax, qword ptr cs:c_idSrvNone.Data4
0x180041ee6  cmp     rax, [rdi+8]
0x180041eea  jnz     short loc_180041EFC
0x180041eec  mov     r15d, 80070057h
0x180041ef2  mov     edx, 0C4Ch
0x180041ef7  jmp     loc_1800421F4
0x180041efc  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180041f03  movdqu  xmmword ptr [rcx], xmm0
0x180041f07  xor     edi, edi
0x180041f09  test    esi, esi
0x180041f0b  jz      short loc_180041F31
0x180041f0d  mov     eax, edi
0x180041f0f  imul    rcx, rax, 0E8h
0x180041f16  add     rcx, rdx; struct tagMatchingUpdate *
0x180041f19  mov     edx, 1; unsigned int
0x180041f1e  call    ?IsValidMatchingUpdate@@YAHAEBUtagMatchingUpdate@@K@Z; IsValidMatchingUpdate(tagMatchingUpdate const &,ulong)
0x180041f23  test    eax, eax
0x180041f25  jz      short loc_180041F56
0x180041f27  inc     edi
0x180041f29  cmp     edi, esi
0x180041f2b  mov     rdx, [rbp+120h+var_188]
0x180041f2f  jb      short loc_180041F0D
0x180041f31  lea     r8, [rbp+120h+var_160]; struct CSusService **
0x180041f35  mov     rdx, [rbp+120h+var_178]; struct _GUID *
0x180041f39  mov     rcx, [r13+1E0h]; this
0x180041f40  call    ?GetServiceObject@CAgentServiceManager@@QEAAJAEBU_GUID@@PEAPEAVCSusService@@@Z; CAgentServiceManager::GetServiceObject(_GUID const &,CSusService * *)
0x180041f45  mov     r15d, eax
0x180041f48  test    eax, eax
0x180041f4a  jns     short loc_180041F66
0x180041f4c  mov     edx, 0C56h
0x180041f51  jmp     loc_1800421F4
0x180041f56  mov     r15d, 80070057h
0x180041f5c  mov     edx, 0C52h
0x180041f61  jmp     loc_1800421F4
0x180041f66  lea     rdx, [rbp+120h+var_198]; int *
0x180041f6a  mov     rdi, qword ptr [rbp+120h+var_160.Data1]
0x180041f6e  mov     rcx, rdi; this
0x180041f71  call    ?GetAllowUninstall@CSusService@@QEAAJPEAH@Z; CSusService::GetAllowUninstall(int *)
0x180041f76  mov     r15d, eax
0x180041f79  test    eax, eax
0x180041f7b  jns     short loc_180041F87
0x180041f7d  mov     edx, 0C58h
0x180041f82  jmp     loc_1800421F4
0x180041f87  cmp     dword ptr [rbp+120h+var_198], 0
0x180041f8b  jnz     short loc_180041FA3
0x180041f8d  cmp     r12d, 2
0x180041f91  jnz     short loc_180041FA3
0x180041f93  mov     r15d, 80240028h
0x180041f99  mov     edx, 0C5Bh
0x180041f9e  jmp     loc_1800421F4
0x180041fa3  lea     rcx, [r13+58h]
0x180041fa7  mov     rax, [rcx]
0x180041faa  mov     rax, [rax+18h]
0x180041fae  call    _guard_dispatch_icall
0x180041fb3  cmp     eax, 2
0x180041fb6  jnz     short loc_180041FCE
0x180041fb8  cmp     r12d, 4
0x180041fbc  jnz     short loc_180041FCE
0x180041fbe  mov     r15d, 80240047h
0x180041fc4  mov     edx, 0C5Fh
0x180041fc9  jmp     loc_1800421F4
0x180041fce  mov     edi, [rdi+1F0h]
0x180041fd4  and     edi, 8000h
0x180041fda  or      edi, 6800h
0x180041fe0  shr     edi, 0Ah
0x180041fe3  mov     rcx, [rbp+120h+hObject]; hObject
0x180041fea  test    rcx, rcx
0x180041fed  jz      short loc_180042000
0x180041fef  call    cs:__imp_CloseHandle
0x180041ff5  mov     [rbp+120h+hObject], 0
0x180042000  mov     rax, [rbp+120h+var_178]
0x180042004  movups  xmm0, xmmword ptr [rax]
0x180042007  movdqu  xmmword ptr [rbp+120h+var_160.Data1], xmm0
0x18004200c  lea     rax, [rbp+120h+hObject]
0x180042013  mov     [rsp+230h+var_1E0], rax; void **
0x180042018  lea     rax, [rbp+120h+var_18C]
0x18004201c  mov     [rsp+230h+var_1E8], rax; int *
0x180042021  mov     rax, [rbp+120h+var_170]
0x180042025  mov     [rsp+230h+var_1F0], rax; struct IUnknown *
0x18004202a  lea     rax, [rbp+120h+var_180]
0x18004202e  mov     [rsp+230h+var_1F8], rax; struct CCallerIdentity **
0x180042033  lea     rax, [rbp+120h+var_190]
0x180042037  mov     [rsp+230h+var_200], rax; int *
0x18004203c  lea     rax, [rbp+120h+var_1A0]
0x180042040  mov     [rsp+230h+var_208], rax; int *
0x180042045  mov     rax, [rbp+120h+var_188]
0x180042049  mov     [rsp+230h+var_210], rax; struct tagMatchingUpdate *
0x18004204e  mov     r9d, esi; unsigned int
0x180042051  lea     r8, [rbp+120h+var_160]; struct _GUID
0x180042055  mov     edx, edi; unsigned int
0x180042057  mov     rcx, r13; this
0x18004205a  call    ?PrepareCallSecurityForUpdates@CClientCallRecorder@@AEAAJKU_GUID@@KQEBUtagMatchingUpdate@@PEAH2PEAPEAVCCallerIdentity@@PEAUIUnknown@@2PEAPEAX@Z; CClientCallRecorder::PrepareCallSecurityForUpdates(ulong,_GUID,ulong,tagMatchingUpdate const * const,int *,int *,CCallerIdentity * *,IUnknown *,int *,void * *)
0x18004205f  mov     r15d, eax
0x180042062  mov     r14, [rbp+120h+var_180]
0x180042066  test    eax, eax
0x180042068  jns     short loc_180042074
0x18004206a  mov     edx, 0C70h
0x18004206f  jmp     loc_1800421F4
0x180042074  xor     r15d, r15d
0x180042077  cmp     [r14+4], r15d
0x18004207b  jz      loc_18004212D
0x180042081  cmp     [r14], r15d
0x180042084  jnz     loc_18004212D
0x18004208a  cmp     [r14+8], r15d
0x18004208e  jnz     loc_18004212D
0x180042094  cmp     [rbp+120h+arg_60], r15
0x18004209b  jz      short loc_1800420AD
0x18004209d  mov     r15d, 80240066h
0x1800420a3  mov     edx, 0C77h
0x1800420a8  jmp     loc_1800421F4
0x1800420ad  test    dil, 20h
0x1800420b1  jz      loc_180042164
0x1800420b7  cmp     [r14+80h], r15d
0x1800420be  jz      loc_180042164
0x1800420c4  mov     ecx, r12d
0x1800420c7  sub     ecx, 1
0x1800420ca  jz      short loc_1800420FF
0x1800420cc  sub     ecx, 1
0x1800420cf  jz      short loc_1800420F6
0x1800420d1  sub     ecx, 2
0x1800420d4  jz      short loc_1800420ED
0x1800420d6  cmp     ecx, 4
0x1800420d9  jz      short loc_1800420E4
0x1800420db  lea     rax, aUnknown_3; "Unknown"
0x1800420e2  jmp     short loc_180042106
0x1800420e4  lea     rax, aCommiting; "Commiting"
0x1800420eb  jmp     short loc_180042106
0x1800420ed  lea     rax, aReverting; "Reverting"
0x1800420f4  jmp     short loc_180042106
0x1800420f6  lea     rax, aUninstalling; "Uninstalling"
0x1800420fd  jmp     short loc_180042106
0x1800420ff  lea     rax, aInstalling; "Installing"
0x180042106  mov     [rsp+230h+var_200], rax
0x18004210b  lea     rax, aNonElevatedAdm_0; "Non-elevated admin user is requesting %"...
0x180042112  mov     [rsp+230h+var_208], rax
0x180042117  mov     [rsp+230h+var_210], r15
0x18004211c  xor     edx, edx
0x18004211e  xor     ecx, ecx
0x180042120  lea     r9d, [rdx+5]
0x180042124  lea     r8d, [rdx+1]
0x180042128  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18004212d  cmp     [rbp+120h+var_128], r15
0x180042131  jz      loc_1800422C8
0x180042137  mov     qword ptr [rbp+120h+var_160.Data1], r15
0x18004213b  mov     rdi, r15
0x18004213e  mov     [rbp+120h+var_198], r15
0x180042142  lea     rcx, [rbp+120h+var_160]
0x180042146  call    ?ReleaseAndAlloc@?$XPtrBase@VCCallerIdentity@@U?$STPolicy@VCCallerIdentity@@@Policies@WuSmartPtr@@@WuSmartPtr@@QEAAJXZ; WuSmartPtr::XPtrBase<CCallerIdentity,WuSmartPtr::Policies::STPolicy<CCallerIdentity>>::ReleaseAndAlloc(void)
0x18004214b  mov     r15d, eax
0x18004214e  mov     rsi, qword ptr [rbp+120h+var_160.Data1]
0x180042152  test    eax, eax
0x180042154  jns     loc_1800421FC
0x18004215a  mov     edx, 0C93h
0x18004215f  jmp     loc_180042219
0x180042164  cmp     [rbp+120h+var_1A0], r15d
0x180042168  jnz     short loc_18004212D
0x18004216a  test    byte ptr [rbp+120h+arg_38], 3
0x180042171  jnz     short loc_180042188
0x180042173  cmp     r12d, 2
0x180042177  jz      short loc_1800421B2
0x180042179  cmp     r12d, 4
0x18004217d  jnz     short loc_18004212D
0x18004217f  lea     rax, aRevert; "Revert"
0x180042186  jmp     short loc_1800421C2
0x180042188  sub     r12d, 1
0x18004218c  jz      short loc_1800421BB
0x18004218e  sub     r12d, 1
0x180042192  jz      short loc_1800421B2
0x180042194  sub     r12d, 2
0x180042198  jz      short loc_18004217F
0x18004219a  cmp     r12d, 4
0x18004219e  jz      short loc_1800421A9
0x1800421a0  lea     rax, aUnknown_3; "Unknown"
0x1800421a7  jmp     short loc_1800421C2
0x1800421a9  lea     rax, aCommit; "Commit"
0x1800421b0  jmp     short loc_1800421C2
0x1800421b2  lea     rax, aUninstall_0; "Uninstall"
0x1800421b9  jmp     short loc_1800421C2
0x1800421bb  lea     rax, aInstall; "Install"
0x1800421c2  mov     [rsp+230h+var_200], rax
0x1800421c7  lea     rax, aNonAdminUserIs_3; "Non admin user is requesting invalid %w"...
0x1800421ce  mov     [rsp+230h+var_208], rax
0x1800421d3  mov     [rsp+230h+var_210], r15
0x1800421d8  xor     edx, edx
0x1800421da  xor     ecx, ecx
0x1800421dc  lea     r9d, [rdx+5]
0x1800421e0  lea     r8d, [rdx+1]
0x1800421e4  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800421e9  mov     r15d, 80070005h
0x1800421ef  mov     edx, 0C88h
0x1800421f4  mov     r9d, r15d
0x1800421f7  jmp     loc_1800425F0
0x1800421fc  lea     rdx, [rbp+120h+var_198]
  ... truncated ...
```
