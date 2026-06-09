# CINetEdge::CINetCallback(void *,unsigned __int64,ulong,void *,ulong)

- ea: `0x180094ea0`
- end: `0x180095dba`
- name: `?CINetCallback@CINetEdge@@KAXPEAX_KK0K@Z`
- size: `3866`
- prototype: `void __stdcall(HINTERNET hInternet, DWORD_PTR dwContext, DWORD dwInternetStatus, LPVOID lpvStatusInformation, DWORD dwStatusInformationLength)`
- caller_count: `0`
- callee_count: `25`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180003520`
- `0x180007730`
- `0x18000a110`
- `0x18000a270`
- `0x18000b7f0`
- `0x18000cef0`
- `0x18000d1f0`
- `0x18000daf0`
- `0x18000eb40`
- `0x18003f4f8`
- `0x18003f68c`
- `0x180046cb0`
- `0x180046eb0`
- `0x180057860`
- `0x1800709bc`
- `0x180073b18`
- `0x18007a210`
- `0x180080928`
- `0x180082510`
- `0x180094ea0`
- `0x18009b9dc`
- `0x1800e3e90`
- `0x18011ba3e`
- `0x18011baa0`
- `0x18011c010`

## import_xrefs

- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x18009581a`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x18009581a`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18009580c`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18009580c`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x1800957fc`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x1800957fc`
- `iertutil!__imp_?GetEdgeBrowsingEnvironment@@YAPEAUIEdgeBrowsingEnvironment@@XZ` at `0x1800958cc`
- `iertutil!__imp_?GetEdgeBrowsingEnvironment@@YAPEAUIEdgeBrowsingEnvironment@@XZ` at `0x18009590d`
- `iertutil!__imp_?GetEdgeBrowsingEnvironment@@YAPEAUIEdgeBrowsingEnvironment@@XZ` at `0x18009592d`
- `iertutil!__imp_?GetEdgeBrowsingEnvironment@@YAPEAUIEdgeBrowsingEnvironment@@XZ` at `0x1800958cc`
- `iertutil!__imp_?GetEdgeBrowsingEnvironment@@YAPEAUIEdgeBrowsingEnvironment@@XZ` at `0x18009590d`
- `iertutil!__imp_?GetEdgeBrowsingEnvironment@@YAPEAUIEdgeBrowsingEnvironment@@XZ` at `0x18009592d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180094f58`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800951f9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800952e8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180095ada`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180095af3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180094f58`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800951f9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800952e8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180095ada`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180095af3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180094f40`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800951bd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800952ac`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180095a06`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180094f40`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800951bd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800952ac`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180095a06`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800959f1`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800959f1`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180095970`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180095970`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180095991`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180095991`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180095b30`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180095b30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180095a1d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180095a1d`
- `WININET!InternetSetOptionA` at `0x180095878`
- `WININET!InternetSetOptionA` at `0x180095878`
- `WININET!InternetQueryOptionA` at `0x180095424`
- `WININET!InternetQueryOptionA` at `0x180095847`
- `WININET!InternetQueryOptionA` at `0x180095424`
- `WININET!InternetQueryOptionA` at `0x180095847`

## pseudocode

```c
void __fastcall CINetEdge::CINetCallback(
        HINTERNET hInternet,
        __int64 dwContext,
        DWORD dwInternetStatus,
        unsigned int *lpvStatusInformation,
        DWORD dwStatusInformationLength)
{
  __int64 v8; // r15
  bool IsAbortInProgress; // bl
  int v10; // eax
  __int64 v11; // rsi
  _DWORD *v12; // rdi
  unsigned int v13; // ebx
  unsigned int v14; // eax
  int v15; // edi
  _DWORD *v16; // rdi
  __int64 v17; // rax
  unsigned int v18; // edi
  __int64 v19; // rdx
  _DWORD *v20; // rdi
  __int64 v21; // rax
  char v22; // r12
  bool v23; // dl
  struct IInternetBindInfo *RefCountedBindInfo; // r14
  __int64 v25; // rcx
  void *v26; // rcx
  __int128 v27; // xmm0
  __int128 v28; // xmm1
  __int128 v29; // xmm0
  __int128 v30; // xmm1
  __int128 v31; // xmm0
  __int128 v32; // xmm1
  __int128 v33; // xmm0
  __int128 v34; // xmm1
  int v35; // edx
  unsigned int v36; // eax
  __int64 v37; // rcx
  unsigned int v38; // edi
  int v39; // edx
  int v40; // r14d
  unsigned int v41; // eax
  unsigned int v42; // eax
  int v43; // eax
  int v44; // edx
  unsigned int v45; // edx
  __int64 v46; // rdx
  unsigned int v47; // eax
  _DWORD *v48; // rcx
  _DWORD *v49; // rcx
  struct IEdgeBrowsingEnvironment *EdgeBrowsingEnvironment; // rax
  __int64 v51; // rdx
  struct IEdgeBrowsingEnvironment *v52; // rdx
  struct IEdgeBrowsingEnvironment *v53; // rax
  _QWORD *Value; // rbx
  const char *v55; // r9
  char *v56; // rax
  unsigned int v57; // r8d
  __int64 v58; // rdi
  _QWORD *v59; // rax
  __int64 v60; // rsi
  struct CPlex *v61; // rax
  int v62; // r8d
  _QWORD *i; // rcx
  _QWORD *v64; // rcx
  _QWORD *v65; // rax
  void (__fastcall *v66)(_QWORD, _QWORD); // rax
  DWORD dwBufferLength[2]; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v68; // [rsp+50h] [rbp-B8h] BYREF
  __int16 v69; // [rsp+58h] [rbp-B0h]
  __int16 v70; // [rsp+60h] [rbp-A8h] BYREF
  int v71; // [rsp+64h] [rbp-A4h] BYREF
  __int64 v72; // [rsp+68h] [rbp-A0h]
  _BYTE Buffer[128]; // [rsp+78h] [rbp-90h] BYREF
  __int128 v74; // [rsp+F8h] [rbp-10h]
  __int128 v75; // [rsp+108h] [rbp+0h]
  __int128 v76; // [rsp+118h] [rbp+10h]
  __int128 v77; // [rsp+128h] [rbp+20h]
  __int128 v78; // [rsp+138h] [rbp+30h]
  __int128 v79; // [rsp+148h] [rbp+40h]
  __int128 v80; // [rsp+158h] [rbp+50h]
  __int128 v81; // [rsp+168h] [rbp+60h]
  struct _EVENT_DATA_DESCRIPTOR v82; // [rsp+178h] [rbp+70h] BYREF
  __int64 *v83; // [rsp+198h] [rbp+90h]
  __int64 v84; // [rsp+1A0h] [rbp+98h]
  __int16 *v85; // [rsp+1A8h] [rbp+A0h]
  __int64 v86; // [rsp+1B0h] [rbp+A8h]
  DWORD *v87; // [rsp+1B8h] [rbp+B0h]
  __int64 v88; // [rsp+1C0h] [rbp+B8h]
  int *v89; // [rsp+1C8h] [rbp+C0h]
  __int64 v90; // [rsp+1D0h] [rbp+C8h]
  wil::details::in1diag3 *retaddr; // [rsp+220h] [rbp+118h]

  if ( !dwContext )
    return;
  if ( dwContext == 1978 )
  {
    v8 = 1200;
    v11 = 0;
    v72 = 0;
    dwBufferLength[0] = 0;
  }
  else
  {
    if ( !IsCINetEdgeValid((struct CINetEdge *)dwContext, "CINetEdge::CINetCallback") )
      return;
    v72 = dwContext;
    v8 = dwContext + 1200;
    v68 = dwContext;
    LOBYTE(v69) = 0;
    _InterlockedIncrement((volatile signed __int32 *)(dwContext + 1200));
    if ( CINetEdge::CAutoStateLock::AcquireLock((CINetEdge::CAutoStateLock *)&v68) )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(dwContext + 984));
      dwBufferLength[0] = *(_DWORD *)(dwContext + 1024);
      LeaveCriticalSection((LPCRITICAL_SECTION)(dwContext + 984));
      IsAbortInProgress = CINetEdge::IsAbortInProgress((CINetEdge *)dwContext);
      if ( !IsAbortInProgress && dwInternetStatus != 70 )
        CINetEdge::ReportInternetStatusTimestamp((CINetEdge *)dwContext, dwInternetStatus);
    }
    else
    {
      dwBufferLength[0] = 0;
      IsAbortInProgress = 1;
    }
    CINetEdge::CAutoStateLock::~CAutoStateLock((CINetEdge::CAutoStateLock *)&v68);
    if ( IsAbortInProgress )
    {
      if ( dwInternetStatus != 70 )
        return;
      v10 = 60;
      v11 = dwContext;
      goto LABEL_17;
    }
    v11 = dwContext;
  }
  if ( dwInternetStatus <= 0x140 )
  {
    if ( dwInternetStatus == 320 )
    {
LABEL_117:
      CINetEdge::OnCookieNotification((CINetEdge *)v11, dwInternetStatus, lpvStatusInformation);
      return;
    }
    v10 = dwInternetStatus - 10;
LABEL_17:
    switch ( v10 )
    {
      case 0:
        CINetEdge::ReportNotification((CINetEdge *)v11, BINDSTATUS_FINDINGRESOURCE, (const char *)lpvStatusInformation);
        break;
      case 10:
        CINetEdge::ReportNotification((CINetEdge *)v11, BINDSTATUS_CONNECTING, (const char *)lpvStatusInformation);
        CINetEdge::RedirectProtectedModeURLIfNecessary((CINetEdge *)v11, *(const unsigned __int16 **)(v11 + 184), 1);
        break;
      case 20:
        CINetEdge::ReportNotification((CINetEdge *)v11, BINDSTATUS_SENDINGREQUEST, 0);
        break;
      case 21:
        (*(void (__fastcall **)(__int64, _QWORD, unsigned int *, _QWORD))(*(_QWORD *)v11 + 384LL))(
          v11,
          dwInternetStatus,
          lpvStatusInformation,
          dwStatusInformationLength);
        break;
      case 50:
        if ( ((unsigned int)IEConfiguration_GetDWORD(268435501) != 2
           || (unsigned __int8)IEConfiguration_GetBool(536870914))
          && LCIEIsCurrentProcessInPrivate() )
        {
          v48 = *(_DWORD **)lpvStatusInformation;
          dwBufferLength[0] = 0;
          dwBufferLength[1] = 4;
          InternetQueryOptionA(v48, 9u, dwBufferLength, &dwBufferLength[1]);
          if ( dwBufferLength[0] - 5 <= 3 )
          {
            v49 = *(_DWORD **)lpvStatusInformation;
            v71 = 0x20000;
            InternetSetOptionA(v49, 0x6Fu, &v71, 4u);
          }
        }
        break;
      case 60:
        if ( v11 && *(_QWORD *)lpvStatusInformation )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 512LL))(v11);
        break;
      case 70:
        CINetEdge::ReportNotification((CINetEdge *)v11, BINDSTATUS_PROXYDETECTING, 0);
        break;
      case 90:
        if ( v11 )
        {
          if ( (unsigned int)dword_180159000 > 5
            && (qword_180159010 & 0x20) != 0
            && (qword_180159018 & 0x20) == qword_180159018 )
          {
            v71 = lpvStatusInformation[2];
            dwBufferLength[1] = *lpvStatusInformation;
            v70 = *(_WORD *)(v11 + 128);
            v89 = &v71;
            v87 = &dwBufferLength[1];
            v85 = &v70;
            v83 = &v68;
            v68 = v11;
            v90 = 4;
            v88 = 4;
            v86 = 2;
            v84 = 8;
            tlgWriteTransfer_BrowserWriteTransfer(
              (__int64)&dword_180159000,
              (unsigned __int8 *)&unk_180145288,
              0,
              0,
              6u,
              &v82);
          }
          _InterlockedIncrement((volatile signed __int32 *)v8);
          switch ( *(_DWORD *)(v11 + 128) )
          {
            case 2:
              v15 = CINetEdge::SetBindResult((CINetEdge *)v11, lpvStatusInformation[2], -2146697213);
              goto LABEL_86;
            case 3:
              v16 = *(_DWORD **)lpvStatusInformation;
              if ( !*(_QWORD *)lpvStatusInformation )
              {
                v15 = CINetEdge::SetBindResult((CINetEdge *)v11, lpvStatusInformation[2], -2146697212);
                goto LABEL_86;
              }
              CINetEdge::SetStatePending(v11, 0, 2);
              EnterCriticalSection((LPCRITICAL_SECTION)(v11 + 984));
              if ( *(_DWORD *)(v11 + 712) == 1 )
              {
                v17 = *(_QWORD *)v11;
                *(_DWORD *)(v11 + 712) = 2;
                (*(void (__fastcall **)(__int64, _DWORD *))(v17 + 504))(v11, v16);
                *(_QWORD *)(v11 + 368) = v16;
              }
              LeaveCriticalSection((LPCRITICAL_SECTION)(v11 + 984));
              if ( !*(_QWORD *)(v11 + 368) )
              {
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)v8, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v11 + 216LL))(v11, 1);
                v18 = CINetEdge::CheckAndSetINetEdgeState(v11, 8);
                goto LABEL_37;
              }
              v18 = CINetEdge::CheckAndSetINetEdgeState(v11, 7);
              if ( v18 != 1 )
                goto LABEL_37;
              CINetEdge::TransitState(v11, 3, 0, 7);
              v19 = 1;
              goto LABEL_97;
            case 4:
              v20 = *(_DWORD **)lpvStatusInformation;
              if ( !*(_QWORD *)lpvStatusInformation )
              {
                v15 = CINetEdge::SetBindResult((CINetEdge *)v11, lpvStatusInformation[2], -2146697210);
                goto LABEL_86;
              }
              CINetEdge::SetStatePending(v11, 0, 3);
              EnterCriticalSection((LPCRITICAL_SECTION)(v11 + 984));
              if ( *(_DWORD *)(v11 + 716) == 1 )
              {
                v21 = *(_QWORD *)v11;
                *(_DWORD *)(v11 + 716) = 2;
                (*(void (__fastcall **)(__int64, _DWORD *))(v21 + 504))(v11, v20);
                *(_QWORD *)(v11 + 376) = v20;
              }
              LeaveCriticalSection((LPCRITICAL_SECTION)(v11 + 984));
              v22 = 0;
              if ( *(_QWORD *)(v11 + 376) )
              {
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 264LL))(v11);
                RefCountedBindInfo = CINetEdge::GetRefCountedBindInfo((CINetEdge *)v11, v23);
                if ( RefCountedBindInfo )
                {
                  (*(void (__fastcall **)(__int64, struct IInternetBindInfo *))(*(_QWORD *)v11 + 272LL))(
                    v11,
                    RefCountedBindInfo);
                  v18 = CINetEdge::CheckAndSetINetEdgeState(v72, 11);
                  ((void (__fastcall *)(struct IInternetBindInfo *))RefCountedBindInfo->lpVtbl->Release)(RefCountedBindInfo);
                  v22 = 1;
                  goto LABEL_50;
                }
                v25 = v72;
              }
              else
              {
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)v8, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v11 + 216LL))(v11, 1);
                v25 = v11;
              }
              v18 = CINetEdge::CheckAndSetINetEdgeState(v25, 12);
LABEL_50:
              if ( v18 != 1 )
              {
LABEL_37:
                v19 = v18;
                goto LABEL_97;
              }
              if ( v22 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 248LL))(v11);
              goto LABEL_99;
            case 5:
              v68 = v11;
              LOBYTE(v69) = 0;
              _InterlockedIncrement((volatile signed __int32 *)v8);
              if ( CINetEdge::CAutoStateLock::AcquireLock((CINetEdge::CAutoStateLock *)&v68) )
              {
                memset_0(Buffer, 0, 0x100u);
                v26 = *(void **)(v11 + 368);
                dwBufferLength[1] = 256;
                if ( v26 )
                {
                  if ( InternetQueryOptionA(v26, 0x9Cu, Buffer, &dwBufferLength[1]) )
                  {
                    v27 = v74;
                    v28 = v75;
                    *(_BYTE *)(v11 + 977) |= 0x10u;
                    *(_OWORD *)(v11 + 544) = v27;
                    v29 = v76;
                    *(_OWORD *)(v11 + 560) = v28;
                    v30 = v77;
                    *(_OWORD *)(v11 + 576) = v29;
                    v31 = v78;
                    *(_OWORD *)(v11 + 592) = v30;
                    v32 = v79;
                    *(_OWORD *)(v11 + 608) = v31;
                    v33 = v80;
                    *(_OWORD *)(v11 + 624) = v32;
                    v34 = v81;
                    *(_OWORD *)(v11 + 640) = v33;
                    *(_OWORD *)(v11 + 656) = v34;
                  }
                }
              }
              CINetEdge::CAutoStateLock::~CAutoStateLock((CINetEdge::CAutoStateLock *)&v68);
              if ( *(_QWORD *)lpvStatusInformation )
              {
                v35 = 16;
                if ( dwBufferLength[0] != 15 )
                  v35 = 24;
                v36 = CINetEdge::CheckAndSetINetEdgeState(v11, v35);
                v37 = v11;
                if ( v36 == 1 )
                {
                  CINetEdge::OnINetSendRequest((CINetEdge *)v11, 0, 0);
                  goto LABEL_99;
                }
LABEL_63:
                v19 = v36;
                goto LABEL_98;
              }
              v38 = lpvStatusInformation[2];
              if ( !v38 )
              {
                v38 = 0;
LABEL_71:
                v40 = 17;
                if ( dwBufferLength[0] != 15 )
                  v40 = 24;
                v15 = CINetEdge::SetBindResult((CINetEdge *)v11, v38, 0);
                v41 = CINetEdge::CheckAndSetINetEdgeState(v11, v40);
                goto LABEL_85;
              }
              switch ( v38 )
              {
                case 0x2F00u:
                case 0x2F05u:
                case 0x2F06u:
                case 0x2F07u:
                case 0x2F08u:
                case 0x2F0Cu:
                case 0x2F0Du:
                case 0x2F14u:
                case 0x2F16u:
                case 0x2F17u:
                case 0x2F19u:
                case 0x2F1Bu:
                case 0x2F1Eu:
                case 0x2F88u:
                case 0x2F89u:
                case 0x2F8Au:
                case 0x2F8Eu:
                  v39 = 16;
                  if ( dwBufferLength[0] != 15 )
                    v39 = 24;
                  v36 = CINetEdge::CheckAndSetINetEdgeState(v11, v39);
                  v37 = v11;
                  if ( v36 != 1 )
                    goto LABEL_63;
                  CINetEdge::OnINetSendRequest((CINetEdge *)v11, v38, 0);
                  break;
                default:
                  goto LABEL_71;
              }
              goto LABEL_99;
            case 8:
              if ( !*(_QWORD *)lpvStatusInformation )
              {
                v43 = CINetEdge::SetBindResult((CINetEdge *)v11, lpvStatusInformation[2], 0);
                v44 = 29;
                goto LABEL_84;
              }
              v68 = v11;
              LOBYTE(v69) = 0;
              _InterlockedIncrement((volatile signed __int32 *)v8);
              if ( !CINetEdge::CAutoStateLock::AcquireLock((CINetEdge::CAutoStateLock *)&v68) )
                goto LABEL_79;
              CINetEdge::SetStatePending(v11, 0, 6);
              v42 = CINetEdge::CheckAndSetINetEdgeState(v11, 35);
              if ( v42 == 1 )
              {
                CINetEdge::TransitState(v11, 8, 0, 26);
                CINetEdge::CAutoStateLock::~CAutoStateLock((CINetEdge::CAutoStateLock *)&v68);
                goto LABEL_99;
              }
              CINetEdge::CheckTransitionStatusAndDispatchAbort(v11, v42, 0);
              goto LABEL_79;
            case 9:
              v45 = lpvStatusInformation[2];
              if ( *(_QWORD *)lpvStatusInformation )
              {
                CINetEdge::OnINetDataAvailable((CINetEdge *)v11, v45);
              }
              else
              {
                v43 = CINetEdge::SetBindResult((CINetEdge *)v11, v45, 0);
                v44 = 36;
LABEL_84:
                v15 = v43;
                v41 = CINetEdge::CheckAndSetINetEdgeState(v11, v44);
LABEL_85:
                CINetEdge::CheckTransitionStatusAndDispatchAbort(v11, v41, 0);
LABEL_86:
                if ( v15 )
                {
                  v68 = v11;
                  LOBYTE(v69) = 0;
                  _InterlockedIncrement((volatile signed __int32 *)v8);
                  if ( CINetEdge::CAutoStateLock::AcquireLock((CINetEdge::CAutoStateLock *)&v68) )
                  {
                    v46 = *(unsigned int *)(v11 + 488);
                    if ( (_DWORD)v46 == -2146697189 || (_DWORD)v46 == -2146697196 && *(_DWORD *)(v11 + 696) == 12156 )
                      (*(void (__fastcall **)(__int64, __int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v11 + 288LL))(
                        v11,
                        v46,
                        0,
                        0,
                        *(_QWORD *)(v11 + 344));
                    else
                      (*(void (__fastcall **)(__int64, __int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v11 + 288LL))(
                        v11,
                        v46,
                        0,
                        0,
                        0);
                  }
LABEL_79:
                  CINetEdge::CAutoStateLock::~CAutoStateLock((CINetEdge::CAutoStateLock *)&v68);
                }
              }
              break;
            case 0xA:
              CINetEdge::SetStatePending(v11, 0, 7);
              v47 = CINetEdge::CheckAndSetINetEdgeState(v11, 32);
              if ( v47 == 1 )
              {
                CINetEdge::TransitState(v11, 10, 0, 30);
              }
              else
              {
                v19 = v47;
LABEL_97:
                v37 = v11;
LABEL_98:
                CINetEdge::CheckTransitionStatusAndDispatchAbort(v37, v19, 0);
              }
              goto LABEL_99;
            default:
              goto LABEL_99;
          }
          goto LABEL_99;
        }
        break;
      case 100:
        CINetEdge::OnRedirect((CINetEdge *)v11, (char *)lpvStatusInformation);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 192LL))(v11);
        break;
      case 130:
        _InterlockedIncrement((volatile signed __int32 *)v8);
        v12 = *(_DWORD **)lpvStatusInformation;
        v13 = lpvStatusInformation[2];
        CINetEdge::SetStatePending(v11, 0, 4);
        *(_DWORD *)(v11 + 524) = v13;
        *(_QWORD *)(v11 + 528) = v12;
        *(_DWORD *)(v11 + 488) = -2146697207;
        v14 = CINetEdge::CheckAndSetINetEdgeState(v11, 16);
        if ( v14 == 1 )
          CINetEdge::TransitState(v11, 7, 1, 25);
        else
          CINetEdge::CheckTransitionStatusAndDispatchAbort(v11, v14, 0);
LABEL_99:
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v8, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v11 + 216LL))(v11, 1);
        break;
      default:
        return;
    }
    return;
  }
  switch ( dwInternetStatus )
  {
    case 0x141u:
    case 0x144u:
    case 0x145u:
    case 0x146u:
    case 0x147u:
      goto LABEL_117;
    case 0x148u:
      CINetEdge::RefreshSingleSignOnCookiesIfNeeded((CINetEdge *)v11);
      return;
    case 0x149u:
      if ( (*(int (__fastcall **)(__int64))(*(_QWORD *)v11 + 120LL))(v11) >= 0 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 128LL))(v11);
      return;
    case 0x14Au:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 136LL))(v11);
      return;
    case 0x190u:
    case 0x191u:
      EdgeBrowsingEnvironment = GetEdgeBrowsingEnvironment();
      LOBYTE(v51) = dwInternetStatus == 400;
      (*(void (__fastcall **)(struct IEdgeBrowsingEnvironment *, __int64, unsigned int *))(*(_QWORD *)EdgeBrowsingEnvironment
                                                                                         + 32LL))(
        EdgeBrowsingEnvironment,
        v51,
        lpvStatusInformation);
      return;
    case 0x1A4u:
      if ( !lpvStatusInformation || lpvStatusInformation[2] != 4 || **(_DWORD **)lpvStatusInformation != 1 )
      {
        v52 = GetEdgeBrowsingEnvironment();
        (**(void (__fastcall ***)(struct IEdgeBrowsingEnvironment *))v52)(v52);
      }
      return;
    case 0x1AEu:
      if ( !lpvStatusInformation )
        return;
      v53 = GetEdgeBrowsingEnvironment();
      (*(void (__fastcall **)(struct IEdgeBrowsingEnvironment *, _QWORD, _QWORD, _QWORD, _QWORD, char *, unsigned int))(*(_QWORD *)v53 + 24LL))(
        v53,
        *(_QWORD *)lpvStatusInformation,
        *((_QWORD *)lpvStatusInformation + 1),
        *((_QWORD *)lpvStatusInformation + 2),
        *((_QWORD *)lpvStatusInformation + 3),
        (char *)lpvStatusInformation + 32,
        lpvStatusInformation[10]);
      Value = TlsGetValue(gTlsIndex);
      if ( Value )
        goto LABEL_140;
      v56 = (char *)HeapAlloc(g_hHeap, 0, 0x230u);
      Value = v56;
      if ( !v56 )
        return;
      *(_DWORD *)v56 = 0;
      *(_OWORD *)(v56 + 8) = 0;
      *(_OWORD *)(v56 + 24) = 0;
      *(_OWORD *)(v56 + 40) = 0;
      *(_OWORD *)(v56 + 56) = 0;
      *(_OWORD *)(v56 + 72) = 0;
      *(_OWORD *)(v56 + 532) = 0;
      *((_OWORD *)v56 + 34) = 0;
      *((_DWORD *)v56 + 1) = 1;
      *((_DWORD *)v56 + 22) = 0;
      memset_0(v56 + 92, 0, 0x1B8u);
      if ( !TlsSetValue(gTlsIndex, Value) )
      {
        HeapFree(g_hHeap, 0, Value);
        return;
      }
      EnterCriticalSection(&stru_18015C010);
      v58 = qword_18015DDF0;
      if ( qword_18015DDF0 )
        goto LABEL_130;
      v59 = CoTaskMemAlloc(0x30u);
      v58 = (__int64)v59;
      if ( !v59 )
      {
        qword_18015DDF0 = 0;
        goto LABEL_137;
      }
      v59[2] = 0;
      v59[5] = 10;
      v59[3] = 0;
      v59[1] = 0;
      *v59 = 0;
      v59[4] = 0;
      qword_18015DDF0 = (__int64)v59;
LABEL_130:
      v60 = *(_QWORD *)(v58 + 8);
      if ( *(_QWORD *)(v58 + 24) )
        goto LABEL_134;
      v61 = CPlex::Create((struct CPlex **)(v58 + 32), *(_DWORD *)(v58 + 40), v57);
      if ( !v61 )
      {
LABEL_137:
        LeaveCriticalSection(&stru_18015C010);
        return;
      }
      v62 = *(_DWORD *)(v58 + 40) - 1;
      for ( i = (_QWORD *)((char *)v61 + 24 * v62 + 16); v62 >= 0; --v62 )
      {
        *i = *(_QWORD *)(v58 + 24);
        *(_QWORD *)(v58 + 24) = i;
        i -= 3;
      }
LABEL_134:
      v64 = *(_QWORD **)(v58 + 24);
      *(_QWORD *)(v58 + 24) = *v64;
      v64[1] = v60;
      *v64 = 0;
      ++*(_DWORD *)(v58 + 16);
      v64[2] = Value;
      v65 = *(_QWORD **)(v58 + 8);
      if ( v65 )
        *v65 = v64;
      else
        *(_QWORD *)v58 = v64;
      *(_QWORD *)(v58 + 8) = v64;
      LeaveCriticalSection(&stru_18015C010);
LABEL_140:
      v66 = (void (__fastcall *)(_QWORD, _QWORD))Value[67];
      if ( v66 )
      {
        if ( dwContext != 1978 )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x1902,
            (unsigned int)"onecoreuap\\inetcore\\urlmon\\iapp\\edge\\cnetedge.cxx",
            v55);
        v66(lpvStatusInformation[10], Value[68]);
      }
      return;
    default:
      return;
  }
}

```

## disassembly

```asm
0x180094ea0  test    rdx, rdx
0x180094ea3  jz      locret_180095BA5
0x180094ea9  mov     r11, rsp
0x180094eac  push    rbp
0x180094ead  push    rdi
0x180094eae  push    r13
0x180094eb0  push    r14
0x180094eb2  lea     rbp, [r11-118h]
0x180094eb9  sub     rsp, 1F8h
0x180094ec0  mov     rax, cs:__security_cookie
0x180094ec7  xor     rax, rsp
0x180094eca  mov     [rbp+110h+var_40], rax
0x180094ed1  mov     [r11+8], rbx
0x180094ed5  mov     r14, r9
0x180094ed8  mov     [r11-28h], rsi
0x180094edc  mov     edi, r8d
0x180094edf  mov     [r11-30h], r12
0x180094ee3  mov     r13, rdx
0x180094ee6  mov     [r11-38h], r15
0x180094eea  cmp     rdx, 7BAh
0x180094ef1  jz      loc_180094FA9
0x180094ef7  lea     rdx, aCinetedgeCinet; "CINetEdge::CINetCallback"
0x180094efe  mov     rcx, r13; struct CINetEdge *
0x180094f01  call    ?IsCINetEdgeValid@@YA_NPEAVCINetEdge@@PEBD@Z; IsCINetEdgeValid(CINetEdge *,char const *)
0x180094f06  test    al, al
0x180094f08  jz      def_180094FFA; jumptable 0000000180094FFA default case, cases 11-19,21-29,32-59,61-69,71-79,81-99,101-109,111-139
0x180094f0e  mov     [rsp+210h+var_1B0], r13
0x180094f13  lea     r15, [r13+4B0h]
0x180094f1a  mov     [rsp+210h+var_1C8], r13
0x180094f1f  mov     byte ptr [rsp+210h+var_1C0], 0
0x180094f24  lock inc dword ptr [r15]
0x180094f28  lea     rcx, [rsp+210h+var_1C8]; this
0x180094f2d  call    ?AcquireLock@CAutoStateLock@CINetEdge@@QEAA_NXZ; CINetEdge::CAutoStateLock::AcquireLock(void)
0x180094f32  xor     r12d, r12d
0x180094f35  test    al, al
0x180094f37  jz      short loc_180094F7E
0x180094f39  lea     rcx, [r13+3D8h]; lpCriticalSection
0x180094f40  call    cs:__imp_EnterCriticalSection
0x180094f46  mov     eax, [r13+400h]
0x180094f4d  lea     rcx, [r13+3D8h]; lpCriticalSection
0x180094f54  mov     [rsp+210h+dwBufferLength], eax
0x180094f58  call    cs:__imp_LeaveCriticalSection
0x180094f5e  mov     rcx, r13; this
0x180094f61  call    ?IsAbortInProgress@CINetEdge@@IEAA_NXZ; CINetEdge::IsAbortInProgress(void)
0x180094f66  movzx   ebx, al
0x180094f69  test    al, al
0x180094f6b  jnz     short loc_180094F85
0x180094f6d  cmp     edi, 46h ; 'F'
0x180094f70  jz      short loc_180094F85
0x180094f72  mov     edx, edi; unsigned int
0x180094f74  mov     rcx, r13; this
0x180094f77  call    ?ReportInternetStatusTimestamp@CINetEdge@@AEAAXK@Z; CINetEdge::ReportInternetStatusTimestamp(ulong)
0x180094f7c  jmp     short loc_180094F85
0x180094f7e  mov     [rsp+210h+dwBufferLength], r12d
0x180094f83  mov     bl, 1
0x180094f85  lea     rcx, [rsp+210h+var_1C8]; this
0x180094f8a  call    ??1CAutoStateLock@CINetEdge@@QEAA@XZ; CINetEdge::CAutoStateLock::~CAutoStateLock(void)
0x180094f8f  test    bl, bl
0x180094f91  jz      short loc_180094FA4
0x180094f93  cmp     edi, 46h ; 'F'
0x180094f96  jnz     def_180094FFA; jumptable 0000000180094FFA default case, cases 11-19,21-29,32-59,61-69,71-79,81-99,101-109,111-139
0x180094f9c  lea     eax, [rdi-0Ah]
0x180094f9f  mov     rsi, r13
0x180094fa2  jmp     short loc_180094FDF
0x180094fa4  mov     rsi, r13
0x180094fa7  jmp     short loc_180094FBF
0x180094fa9  xor     r12d, r12d
0x180094fac  mov     r15d, 4B0h
0x180094fb2  mov     esi, r12d
0x180094fb5  mov     [rsp+210h+var_1B0], r12
0x180094fba  mov     [rsp+210h+dwBufferLength], r12d
0x180094fbf  cmp     edi, 140h
0x180094fc5  ja      loc_180095883
0x180094fcb  jz      loc_1800958BA; jumptable 00000001800958AB cases 321,324-327
0x180094fd1  lea     eax, [rdi-0Ah]; switch 131 cases
0x180094fd4  cmp     eax, 82h
0x180094fd9  ja      def_180094FFA; jumptable 0000000180094FFA default case, cases 11-19,21-29,32-59,61-69,71-79,81-99,101-109,111-139
0x180094fdf  lea     r13, __ImageBase
0x180094fe6  movzx   eax, ds:(byte_180095BEC - 180000000h)[rax+r13]
0x180094fef  mov     ecx, ds:(jpt_180094FFA - 180000000h)[r13+rax*4]
0x180094ff7  add     rcx, r13
0x180094ffa  jmp     rcx; switch jump
0x180094ffc  lock inc dword ptr [r15]; jumptable 0000000180094FFA case 140
0x180095000  mov     rdi, [r14]
0x180095003  xor     edx, edx
0x180095005  mov     ebx, [r14+8]
0x180095009  mov     r8d, 4
0x18009500f  mov     rcx, rsi
0x180095012  call    ?SetStatePending@CINetEdge@@IEAAJJW4ePendingStateReason@1@H@Z; CINetEdge::SetStatePending(long,CINetEdge::ePendingStateReason,int)
0x180095017  mov     edx, 10h
0x18009501c  mov     [rsi+20Ch], ebx
0x180095022  mov     rcx, rsi
0x180095025  mov     [rsi+210h], rdi
0x18009502c  mov     dword ptr [rsi+1E8h], 800C0009h
0x180095036  call    ?CheckAndSetINetEdgeState@CINetEdge@@IEAA?AW4INetEdgeStateTransition@@W4INetEdgeState@@@Z; CINetEdge::CheckAndSetINetEdgeState(INetEdgeState)
0x18009503b  mov     rcx, rsi
0x18009503e  cmp     eax, 1
0x180095041  jnz     short loc_180095060
0x180095043  mov     edx, 7
0x180095048  mov     r9d, 19h
0x18009504e  mov     r8d, eax
0x180095051  call    ?TransitState@CINetEdge@@IEAAXKHW4INetEdgeState@@@Z; CINetEdge::TransitState(ulong,int,INetEdgeState)
0x180095056  mov     ebx, 0FFFFFFFFh
0x18009505b  jmp     def_18009517F; jumptable 000000018009517F default case, cases 6,7
0x180095060  xor     r8d, r8d
0x180095063  mov     edx, eax
0x180095065  call    ?CheckTransitionStatusAndDispatchAbort@CINetEdge@@IEAAJW4INetEdgeStateTransition@@J@Z; CINetEdge::CheckTransitionStatusAndDispatchAbort(INetEdgeStateTransition,long)
0x18009506a  mov     ebx, 0FFFFFFFFh
0x18009506f  jmp     def_18009517F; jumptable 000000018009517F default case, cases 6,7
0x180095074  test    rsi, rsi; jumptable 0000000180094FFA case 100
0x180095077  jz      def_180094FFA; jumptable 0000000180094FFA default case, cases 11-19,21-29,32-59,61-69,71-79,81-99,101-109,111-139
0x18009507d  mov     eax, cs:dword_180159000
0x180095083  cmp     eax, 5
0x180095086  jbe     loc_180095157
0x18009508c  mov     rcx, cs:qword_180159018
0x180095093  mov     rax, cs:qword_180159010
0x18009509a  test    al, 20h
0x18009509c  jz      loc_180095157
0x1800950a2  mov     rax, rcx
0x1800950a5  and     eax, 20h
0x1800950a8  cmp     rax, rcx
0x1800950ab  jnz     loc_180095157
0x1800950b1  mov     eax, [r14+8]
0x1800950b5  lea     rdx, unk_180145288
0x1800950bc  mov     dword ptr [rsp+210h+var_1B8+4], eax
0x1800950c0  lea     rcx, dword_180159000
0x1800950c7  mov     eax, [r14]
0x1800950ca  xor     r9d, r9d
0x1800950cd  mov     [rsp+210h+dwBufferLength+4], eax
0x1800950d1  xor     r8d, r8d
0x1800950d4  movzx   eax, word ptr [rsi+80h]
0x1800950db  mov     word ptr [rsp+210h+var_1B8], ax
0x1800950e0  lea     rax, [rsp+210h+var_1B8+4]
0x1800950e5  mov     [rbp+110h+var_50], rax
0x1800950ec  lea     rax, [rsp+210h+dwBufferLength+4]
0x1800950f1  mov     [rbp+110h+var_60], rax
0x1800950f8  lea     rax, [rsp+210h+var_1B8]
0x1800950fd  mov     [rbp+110h+var_70], rax
0x180095104  lea     rax, [rsp+210h+var_1C8]
0x180095109  mov     [rbp+110h+var_80], rax
0x180095110  lea     rax, [rbp+110h+var_A0]
0x180095114  mov     qword ptr [rsp+210h+var_1E8], rax
0x180095119  mov     dword ptr [rsp+210h+var_1F0], 6
0x180095121  mov     [rsp+210h+var_1C8], rsi
0x180095126  mov     [rbp+110h+var_48], 4
0x180095131  mov     [rbp+110h+var_58], 4
0x18009513c  mov     [rbp+110h+var_68], 2
0x180095147  mov     [rbp+110h+var_78], 8
0x180095152  call    _tlgWriteTransfer_BrowserWriteTransfer
0x180095157  lock inc dword ptr [r15]
0x18009515b  mov     eax, [rsi+80h]
0x180095161  mov     ebx, 0FFFFFFFFh
0x180095166  add     eax, 0FFFFFFFEh; switch 9 cases
0x180095169  cmp     eax, 8
0x18009516c  ja      def_18009517F; jumptable 000000018009517F default case, cases 6,7
0x180095172  cdqe
0x180095174  mov     ecx, ds:(jpt_18009517F - 180000000h)[r13+rax*4]
0x18009517c  add     rcx, r13
0x18009517f  jmp     rcx; switch jump
0x180095181  mov     edx, [r14+8]; jumptable 000000018009517F case 2
0x180095185  mov     r8d, 800C0003h; int
0x18009518b  mov     rcx, rsi; this
0x18009518e  call    ?SetBindResult@CINetEdge@@MEAAJKJ@Z; CINetEdge::SetBindResult(ulong,long)
0x180095193  mov     edi, eax
0x180095195  jmp     loc_18009563D
0x18009519a  mov     rdi, [r14]; jumptable 000000018009517F case 3
0x18009519d  mov     rcx, rsi; this
0x1800951a0  test    rdi, rdi
0x1800951a3  jz      loc_180095273
0x1800951a9  xor     edx, edx
0x1800951ab  mov     r8d, 2
0x1800951b1  call    ?SetStatePending@CINetEdge@@IEAAJJW4ePendingStateReason@1@H@Z; CINetEdge::SetStatePending(long,CINetEdge::ePendingStateReason,int)
0x1800951b6  lea     rcx, [rsi+3D8h]; lpCriticalSection
0x1800951bd  call    cs:__imp_EnterCriticalSection
0x1800951c3  cmp     dword ptr [rsi+2C8h], 1
0x1800951ca  jnz     short loc_1800951F2
0x1800951cc  mov     rax, [rsi]
0x1800951cf  mov     rdx, rdi
0x1800951d2  mov     rcx, rsi
0x1800951d5  mov     dword ptr [rsi+2C8h], 2
0x1800951df  mov     rax, [rax+1F8h]
0x1800951e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800951eb  mov     [rsi+170h], rdi
0x1800951f2  lea     rcx, [rsi+3D8h]; lpCriticalSection
0x1800951f9  call    cs:__imp_LeaveCriticalSection
0x1800951ff  cmp     qword ptr [rsi+170h], 0
0x180095207  jz      short loc_18009523A
0x180095209  mov     edx, 7
0x18009520e  mov     rcx, rsi
0x180095211  call    ?CheckAndSetINetEdgeState@CINetEdge@@IEAA?AW4INetEdgeStateTransition@@W4INetEdgeState@@@Z; CINetEdge::CheckAndSetINetEdgeState(INetEdgeState)
0x180095216  mov     edi, eax
0x180095218  cmp     eax, 1
0x18009521b  jnz     short loc_18009526C
0x18009521d  mov     r9d, 7
0x180095223  xor     r8d, r8d
0x180095226  mov     edx, 3
0x18009522b  mov     rcx, rsi
0x18009522e  call    ?TransitState@CINetEdge@@IEAAXKHW4INetEdgeState@@@Z; CINetEdge::TransitState(ulong,int,INetEdgeState)
0x180095233  mov     edx, edi
0x180095235  jmp     loc_1800956F6
0x18009523a  mov     eax, ebx
0x18009523c  lock xadd [r15], eax
0x180095241  cmp     eax, 1
0x180095244  jnz     short loc_18009525D
0x180095246  mov     rax, [rsi]
0x180095249  mov     edx, 1
0x18009524e  mov     rcx, rsi
0x180095251  mov     rax, [rax+0D8h]
0x180095258  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009525d  mov     edx, 8
0x180095262  mov     rcx, rsi
0x180095265  call    ?CheckAndSetINetEdgeState@CINetEdge@@IEAA?AW4INetEdgeStateTransition@@W4INetEdgeState@@@Z; CINetEdge::CheckAndSetINetEdgeState(INetEdgeState)
0x18009526a  mov     edi, eax
0x18009526c  mov     edx, edi
0x18009526e  jmp     loc_1800956F6
0x180095273  mov     edx, [r14+8]; unsigned int
0x180095277  mov     r8d, 800C0004h; int
0x18009527d  call    ?SetBindResult@CINetEdge@@MEAAJKJ@Z; CINetEdge::SetBindResult(ulong,long)
0x180095282  mov     edi, eax
0x180095284  jmp     loc_18009563D
0x180095289  mov     rdi, [r14]; jumptable 000000018009517F case 4
0x18009528c  mov     rcx, rsi; this
0x18009528f  test    rdi, rdi
0x180095292  jz      loc_1800953B9
0x180095298  xor     edx, edx
0x18009529a  mov     r8d, 3
0x1800952a0  call    ?SetStatePending@CINetEdge@@IEAAJJW4ePendingStateReason@1@H@Z; CINetEdge::SetStatePending(long,CINetEdge::ePendingStateReason,int)
0x1800952a5  lea     rcx, [rsi+3D8h]; lpCriticalSection
0x1800952ac  call    cs:__imp_EnterCriticalSection
0x1800952b2  cmp     dword ptr [rsi+2CCh], 1
0x1800952b9  jnz     short loc_1800952E1
0x1800952bb  mov     rax, [rsi]
0x1800952be  mov     rdx, rdi
0x1800952c1  mov     rcx, rsi
0x1800952c4  mov     dword ptr [rsi+2CCh], 2
0x1800952ce  mov     rax, [rax+1F8h]
0x1800952d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800952da  mov     [rsi+178h], rdi
0x1800952e1  lea     rcx, [rsi+3D8h]; lpCriticalSection
0x1800952e8  call    cs:__imp_LeaveCriticalSection
0x1800952ee  xor     r12b, r12b
0x1800952f1  cmp     qword ptr [rsi+178h], 0
0x1800952f9  jz      short loc_18009535E
0x1800952fb  mov     rax, [rsi]
0x1800952fe  mov     rcx, rsi
0x180095301  mov     rax, [rax+108h]
0x180095308  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009530d  mov     rcx, rsi; this
0x180095310  call    ?GetRefCountedBindInfo@CINetEdge@@IEAAPEAUIInternetBindInfo@@_N@Z; CINetEdge::GetRefCountedBindInfo(bool)
0x180095315  mov     r14, rax
0x180095318  test    rax, rax
0x18009531b  jz      short loc_180095357
0x18009531d  mov     rdx, [rsi]
0x180095320  mov     rcx, rsi
0x180095323  mov     rax, [rdx+110h]
0x18009532a  mov     rdx, r14
0x18009532d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095332  mov     rcx, [rsp+210h+var_1B0]
0x180095337  mov     edx, 0Bh
0x18009533c  call    ?CheckAndSetINetEdgeState@CINetEdge@@IEAA?AW4INetEdgeStateTransition@@W4INetEdgeState@@@Z; CINetEdge::CheckAndSetINetEdgeState(INetEdgeState)
0x180095341  mov     edi, eax
0x180095343  mov     rcx, r14
0x180095346  mov     rax, [r14]
0x180095349  mov     rax, [rax+10h]
0x18009534d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095352  mov     r12b, 1
0x180095355  jmp     short loc_180095390
0x180095357  mov     rcx, [rsp+210h+var_1B0]
0x18009535c  jmp     short loc_180095384
0x18009535e  mov     eax, ebx
0x180095360  lock xadd [r15], eax
0x180095365  cmp     eax, 1
0x180095368  jnz     short loc_180095381
0x18009536a  mov     rax, [rsi]
0x18009536d  mov     edx, 1
0x180095372  mov     rcx, rsi
0x180095375  mov     rax, [rax+0D8h]
0x18009537c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095381  mov     rcx, rsi
0x180095384  mov     edx, 0Ch
0x180095389  call    ?CheckAndSetINetEdgeState@CINetEdge@@IEAA?AW4INetEdgeStateTransition@@W4INetEdgeState@@@Z; CINetEdge::CheckAndSetINetEdgeState(INetEdgeState)
0x18009538e  mov     edi, eax
0x180095390  cmp     edi, 1
0x180095393  jnz     loc_18009526C
0x180095399  test    r12b, r12b
0x18009539c  jz      def_18009517F; jumptable 000000018009517F default case, cases 6,7
0x1800953a2  mov     rax, [rsi]
0x1800953a5  mov     rcx, rsi
0x1800953a8  mov     rax, [rax+0F8h]
0x1800953af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800953b4  jmp     def_18009517F; jumptable 000000018009517F default case, cases 6,7
0x1800953b9  mov     edx, [r14+8]; unsigned int
0x1800953bd  mov     r8d, 800C0006h; int
0x1800953c3  call    ?SetBindResult@CINetEdge@@MEAAJKJ@Z; CINetEdge::SetBindResult(ulong,long)
0x1800953c8  mov     edi, eax
0x1800953ca  jmp     loc_18009563D
0x1800953cf  mov     [rsp+210h+var_1C8], rsi; jumptable 000000018009517F case 5
0x1800953d4  mov     byte ptr [rsp+210h+var_1C0], 0
0x1800953d9  lock inc dword ptr [r15]
0x1800953dd  lea     rcx, [rsp+210h+var_1C8]; this
  ... truncated ...
```
