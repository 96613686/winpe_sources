# CINetEdge::CINetCallback(void *,unsigned __int64,ulong,void *,ulong)

- ea: `0x18009b550`
- end: `0x18009c50e`
- name: `?CINetCallback@CINetEdge@@KAXPEAX_KK0K@Z`
- size: `4030`
- prototype: `void __stdcall(HINTERNET hInternet, DWORD_PTR dwContext, DWORD dwInternetStatus, LPVOID lpvStatusInformation, DWORD dwStatusInformationLength)`
- caller_count: `0`
- callee_count: `25`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18000367c`
- `0x180008610`
- `0x18000b2e0`
- `0x18000b490`
- `0x18000cbf0`
- `0x18000d60c`
- `0x18000d8a4`
- `0x18000dfec`
- `0x18000e4e8`
- `0x18000e7f0`
- `0x18000eca0`
- `0x18000f974`
- `0x180010de0`
- `0x180012350`
- `0x180017340`
- `0x18005d1e0`
- `0x1800786e8`
- `0x180084e3c`
- `0x180087ebc`
- `0x18009b550`
- `0x1800a25dc`
- `0x1800ed938`
- `0x1801285fe`
- `0x180128660`
- `0x180129010`

## import_xrefs

- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x18009bf0c`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x18009bf0c`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18009bef8`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18009bef8`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x18009bee2`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x18009bee2`
- `iertutil!__imp_?GetEdgeBrowsingEnvironment@@YAPEAUIEdgeBrowsingEnvironment@@XZ` at `0x18009bfd4`
- `iertutil!__imp_?GetEdgeBrowsingEnvironment@@YAPEAUIEdgeBrowsingEnvironment@@XZ` at `0x18009c01b`
- `iertutil!__imp_?GetEdgeBrowsingEnvironment@@YAPEAUIEdgeBrowsingEnvironment@@XZ` at `0x18009c041`
- `iertutil!__imp_?GetEdgeBrowsingEnvironment@@YAPEAUIEdgeBrowsingEnvironment@@XZ` at `0x18009bfd4`
- `iertutil!__imp_?GetEdgeBrowsingEnvironment@@YAPEAUIEdgeBrowsingEnvironment@@XZ` at `0x18009c01b`
- `iertutil!__imp_?GetEdgeBrowsingEnvironment@@YAPEAUIEdgeBrowsingEnvironment@@XZ` at `0x18009c041`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009b60e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009b8c3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009b9be`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009c21a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009c239`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009b60e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009b8c3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009b9be`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009c21a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009c239`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009b5f0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009b881`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009b97c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009c132`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009b5f0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009b881`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009b97c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009c132`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18009c117`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18009c117`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18009c08a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18009c08a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009c0b1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009c0b1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009c27c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009c27c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009c14f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009c14f`
- `WININET!InternetSetOptionA` at `0x18009bf76`
- `WININET!InternetSetOptionA` at `0x18009bf76`
- `WININET!InternetQueryOptionA` at `0x18009bb00`
- `WININET!InternetQueryOptionA` at `0x18009bf3f`
- `WININET!InternetQueryOptionA` at `0x18009bb00`
- `WININET!InternetQueryOptionA` at `0x18009bf3f`

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
          if ( (unsigned int)dword_180166000 > 5
            && (qword_180166010 & 0x20) != 0
            && (qword_180166018 & 0x20) == qword_180166018 )
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
              (__int64)&dword_180166000,
              (unsigned __int8 *)&unk_180152250,
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
      EnterCriticalSection(&stru_180169110);
      v58 = qword_18016AEF0;
      if ( qword_18016AEF0 )
        goto LABEL_130;
      v59 = CoTaskMemAlloc(0x30u);
      v58 = (__int64)v59;
      if ( !v59 )
      {
        qword_18016AEF0 = 0;
        goto LABEL_137;
      }
      v59[2] = 0;
      v59[5] = 10;
      v59[3] = 0;
      v59[1] = 0;
      *v59 = 0;
      v59[4] = 0;
      qword_18016AEF0 = (__int64)v59;
LABEL_130:
      v60 = *(_QWORD *)(v58 + 8);
      if ( *(_QWORD *)(v58 + 24) )
        goto LABEL_134;
      v61 = CPlex::Create((struct CPlex **)(v58 + 32), *(_DWORD *)(v58 + 40), v57);
      if ( !v61 )
      {
LABEL_137:
        LeaveCriticalSection(&stru_180169110);
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
      LeaveCriticalSection(&stru_180169110);
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
0x18009b550  test    rdx, rdx
0x18009b553  jz      locret_18009C2F7
0x18009b559  mov     r11, rsp
0x18009b55c  push    rbp
0x18009b55d  push    rdi
0x18009b55e  push    r13
0x18009b560  push    r14
0x18009b562  lea     rbp, [r11-118h]
0x18009b569  sub     rsp, 1F8h
0x18009b570  mov     rax, cs:__security_cookie
0x18009b577  xor     rax, rsp
0x18009b57a  mov     [rbp+110h+var_40], rax
0x18009b581  mov     [r11+8], rbx
0x18009b585  mov     r14, r9
0x18009b588  mov     [r11-28h], rsi
0x18009b58c  mov     edi, r8d
0x18009b58f  mov     [r11-30h], r12
0x18009b593  mov     r13, rdx
0x18009b596  mov     [r11-38h], r15
0x18009b59a  cmp     rdx, 7BAh
0x18009b5a1  jz      loc_18009B665
0x18009b5a7  lea     rdx, aCinetedgeCinet; "CINetEdge::CINetCallback"
0x18009b5ae  mov     rcx, r13; struct CINetEdge *
0x18009b5b1  call    ?IsCINetEdgeValid@@YA_NPEAVCINetEdge@@PEBD@Z; IsCINetEdgeValid(CINetEdge *,char const *)
0x18009b5b6  test    al, al
0x18009b5b8  jz      def_18009B6B6; jumptable 000000018009B6B6 default case, cases 11-19,21-29,32-59,61-69,71-79,81-99,101-109,111-139
0x18009b5be  mov     [rsp+210h+var_1B0], r13
0x18009b5c3  lea     r15, [r13+4B0h]
0x18009b5ca  mov     [rsp+210h+var_1C8], r13
0x18009b5cf  mov     byte ptr [rsp+210h+var_1C0], 0
0x18009b5d4  lock inc dword ptr [r15]
0x18009b5d8  lea     rcx, [rsp+210h+var_1C8]; this
0x18009b5dd  call    ?AcquireLock@CAutoStateLock@CINetEdge@@QEAA_NXZ; CINetEdge::CAutoStateLock::AcquireLock(void)
0x18009b5e2  xor     r12d, r12d
0x18009b5e5  test    al, al
0x18009b5e7  jz      short loc_18009B63A
0x18009b5e9  lea     rcx, [r13+3D8h]; lpCriticalSection
0x18009b5f0  call    cs:__imp_EnterCriticalSection
0x18009b5f7  nop     dword ptr [rax+rax+00h]
0x18009b5fc  mov     eax, [r13+400h]
0x18009b603  lea     rcx, [r13+3D8h]; lpCriticalSection
0x18009b60a  mov     [rsp+210h+dwBufferLength], eax
0x18009b60e  call    cs:__imp_LeaveCriticalSection
0x18009b615  nop     dword ptr [rax+rax+00h]
0x18009b61a  mov     rcx, r13; this
0x18009b61d  call    ?IsAbortInProgress@CINetEdge@@IEAA_NXZ; CINetEdge::IsAbortInProgress(void)
0x18009b622  movzx   ebx, al
0x18009b625  test    al, al
0x18009b627  jnz     short loc_18009B641
0x18009b629  cmp     edi, 46h ; 'F'
0x18009b62c  jz      short loc_18009B641
0x18009b62e  mov     edx, edi; unsigned int
0x18009b630  mov     rcx, r13; this
0x18009b633  call    ?ReportInternetStatusTimestamp@CINetEdge@@AEAAXK@Z; CINetEdge::ReportInternetStatusTimestamp(ulong)
0x18009b638  jmp     short loc_18009B641
0x18009b63a  mov     [rsp+210h+dwBufferLength], r12d
0x18009b63f  mov     bl, 1
0x18009b641  lea     rcx, [rsp+210h+var_1C8]; this
0x18009b646  call    ??1CAutoStateLock@CINetEdge@@QEAA@XZ; CINetEdge::CAutoStateLock::~CAutoStateLock(void)
0x18009b64b  test    bl, bl
0x18009b64d  jz      short loc_18009B660
0x18009b64f  cmp     edi, 46h ; 'F'
0x18009b652  jnz     def_18009B6B6; jumptable 000000018009B6B6 default case, cases 11-19,21-29,32-59,61-69,71-79,81-99,101-109,111-139
0x18009b658  lea     eax, [rdi-0Ah]
0x18009b65b  mov     rsi, r13
0x18009b65e  jmp     short loc_18009B69B
0x18009b660  mov     rsi, r13
0x18009b663  jmp     short loc_18009B67B
0x18009b665  xor     r12d, r12d
0x18009b668  mov     r15d, 4B0h
0x18009b66e  mov     esi, r12d
0x18009b671  mov     [rsp+210h+var_1B0], r12
0x18009b676  mov     [rsp+210h+dwBufferLength], r12d
0x18009b67b  cmp     edi, 140h
0x18009b681  ja      loc_18009BF87
0x18009b687  jz      loc_18009BFC2; jumptable 000000018009BFAF cases 321,324-327
0x18009b68d  lea     eax, [rdi-0Ah]; switch 131 cases
0x18009b690  cmp     eax, 82h
0x18009b695  ja      def_18009B6B6; jumptable 000000018009B6B6 default case, cases 11-19,21-29,32-59,61-69,71-79,81-99,101-109,111-139
0x18009b69b  lea     r13, __ImageBase
0x18009b6a2  movzx   eax, ds:(byte_18009C340 - 180000000h)[rax+r13]
0x18009b6ab  mov     ecx, ds:(jpt_18009B6B6 - 180000000h)[r13+rax*4]
0x18009b6b3  add     rcx, r13
0x18009b6b6  jmp     rcx; switch jump
0x18009b6bc  lock inc dword ptr [r15]; jumptable 000000018009B6B6 case 140
0x18009b6c0  mov     rdi, [r14]
0x18009b6c3  xor     edx, edx
0x18009b6c5  mov     ebx, [r14+8]
0x18009b6c9  mov     r8d, 4
0x18009b6cf  mov     rcx, rsi
0x18009b6d2  call    ?SetStatePending@CINetEdge@@IEAAJJW4ePendingStateReason@1@H@Z; CINetEdge::SetStatePending(long,CINetEdge::ePendingStateReason,int)
0x18009b6d7  mov     edx, 10h
0x18009b6dc  mov     [rsi+20Ch], ebx
0x18009b6e2  mov     rcx, rsi
0x18009b6e5  mov     [rsi+210h], rdi
0x18009b6ec  mov     dword ptr [rsi+1E8h], 800C0009h
0x18009b6f6  call    ?CheckAndSetINetEdgeState@CINetEdge@@IEAA?AW4INetEdgeStateTransition@@W4INetEdgeState@@@Z; CINetEdge::CheckAndSetINetEdgeState(INetEdgeState)
0x18009b6fb  mov     rcx, rsi
0x18009b6fe  cmp     eax, 1
0x18009b701  jnz     short loc_18009B720
0x18009b703  mov     edx, 7
0x18009b708  mov     r9d, 19h
0x18009b70e  mov     r8d, eax
0x18009b711  call    ?TransitState@CINetEdge@@IEAAXKHW4INetEdgeState@@@Z; CINetEdge::TransitState(ulong,int,INetEdgeState)
0x18009b716  mov     ebx, 0FFFFFFFFh
0x18009b71b  jmp     def_18009B83F; jumptable 000000018009B83F default case, cases 6,7
0x18009b720  xor     r8d, r8d
0x18009b723  mov     edx, eax
0x18009b725  call    ?CheckTransitionStatusAndDispatchAbort@CINetEdge@@IEAAJW4INetEdgeStateTransition@@J@Z; CINetEdge::CheckTransitionStatusAndDispatchAbort(INetEdgeStateTransition,long)
0x18009b72a  mov     ebx, 0FFFFFFFFh
0x18009b72f  jmp     def_18009B83F; jumptable 000000018009B83F default case, cases 6,7
0x18009b734  test    rsi, rsi; jumptable 000000018009B6B6 case 100
0x18009b737  jz      def_18009B6B6; jumptable 000000018009B6B6 default case, cases 11-19,21-29,32-59,61-69,71-79,81-99,101-109,111-139
0x18009b73d  mov     eax, cs:dword_180166000
0x18009b743  cmp     eax, 5
0x18009b746  jbe     loc_18009B817
0x18009b74c  mov     rcx, cs:qword_180166018
0x18009b753  mov     rax, cs:qword_180166010
0x18009b75a  test    al, 20h
0x18009b75c  jz      loc_18009B817
0x18009b762  mov     rax, rcx
0x18009b765  and     eax, 20h
0x18009b768  cmp     rax, rcx
0x18009b76b  jnz     loc_18009B817
0x18009b771  mov     eax, [r14+8]
0x18009b775  lea     rdx, unk_180152250
0x18009b77c  mov     dword ptr [rsp+210h+var_1B8+4], eax
0x18009b780  lea     rcx, dword_180166000
0x18009b787  mov     eax, [r14]
0x18009b78a  xor     r9d, r9d
0x18009b78d  mov     [rsp+210h+dwBufferLength+4], eax
0x18009b791  xor     r8d, r8d
0x18009b794  movzx   eax, word ptr [rsi+80h]
0x18009b79b  mov     word ptr [rsp+210h+var_1B8], ax
0x18009b7a0  lea     rax, [rsp+210h+var_1B8+4]
0x18009b7a5  mov     [rbp+110h+var_50], rax
0x18009b7ac  lea     rax, [rsp+210h+dwBufferLength+4]
0x18009b7b1  mov     [rbp+110h+var_60], rax
0x18009b7b8  lea     rax, [rsp+210h+var_1B8]
0x18009b7bd  mov     [rbp+110h+var_70], rax
0x18009b7c4  lea     rax, [rsp+210h+var_1C8]
0x18009b7c9  mov     [rbp+110h+var_80], rax
0x18009b7d0  lea     rax, [rbp+110h+var_A0]
0x18009b7d4  mov     qword ptr [rsp+210h+var_1E8], rax
0x18009b7d9  mov     dword ptr [rsp+210h+var_1F0], 6
0x18009b7e1  mov     [rsp+210h+var_1C8], rsi
0x18009b7e6  mov     [rbp+110h+var_48], 4
0x18009b7f1  mov     [rbp+110h+var_58], 4
0x18009b7fc  mov     [rbp+110h+var_68], 2
0x18009b807  mov     [rbp+110h+var_78], 8
0x18009b812  call    _tlgWriteTransfer_BrowserWriteTransfer
0x18009b817  lock inc dword ptr [r15]
0x18009b81b  mov     eax, [rsi+80h]
0x18009b821  mov     ebx, 0FFFFFFFFh
0x18009b826  add     eax, 0FFFFFFFEh; switch 9 cases
0x18009b829  cmp     eax, 8
0x18009b82c  ja      def_18009B83F; jumptable 000000018009B83F default case, cases 6,7
0x18009b832  cdqe
0x18009b834  mov     ecx, ds:(jpt_18009B83F - 180000000h)[r13+rax*4]
0x18009b83c  add     rcx, r13
0x18009b83f  jmp     rcx; switch jump
0x18009b845  mov     edx, [r14+8]; jumptable 000000018009B83F case 2
0x18009b849  mov     r8d, 800C0003h; int
0x18009b84f  mov     rcx, rsi; this
0x18009b852  call    ?SetBindResult@CINetEdge@@MEAAJKJ@Z; CINetEdge::SetBindResult(ulong,long)
0x18009b857  mov     edi, eax
0x18009b859  jmp     loc_18009BD23
0x18009b85e  mov     rdi, [r14]; jumptable 000000018009B83F case 3
0x18009b861  mov     rcx, rsi; this
0x18009b864  test    rdi, rdi
0x18009b867  jz      loc_18009B943
0x18009b86d  xor     edx, edx
0x18009b86f  mov     r8d, 2
0x18009b875  call    ?SetStatePending@CINetEdge@@IEAAJJW4ePendingStateReason@1@H@Z; CINetEdge::SetStatePending(long,CINetEdge::ePendingStateReason,int)
0x18009b87a  lea     rcx, [rsi+3D8h]; lpCriticalSection
0x18009b881  call    cs:__imp_EnterCriticalSection
0x18009b888  nop     dword ptr [rax+rax+00h]
0x18009b88d  cmp     dword ptr [rsi+2C8h], 1
0x18009b894  jnz     short loc_18009B8BC
0x18009b896  mov     rax, [rsi]
0x18009b899  mov     rdx, rdi
0x18009b89c  mov     rcx, rsi
0x18009b89f  mov     dword ptr [rsi+2C8h], 2
0x18009b8a9  mov     rax, [rax+1F8h]
0x18009b8b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b8b5  mov     [rsi+170h], rdi
0x18009b8bc  lea     rcx, [rsi+3D8h]; lpCriticalSection
0x18009b8c3  call    cs:__imp_LeaveCriticalSection
0x18009b8ca  nop     dword ptr [rax+rax+00h]
0x18009b8cf  cmp     qword ptr [rsi+170h], 0
0x18009b8d7  jz      short loc_18009B90A
0x18009b8d9  mov     edx, 7
0x18009b8de  mov     rcx, rsi
0x18009b8e1  call    ?CheckAndSetINetEdgeState@CINetEdge@@IEAA?AW4INetEdgeStateTransition@@W4INetEdgeState@@@Z; CINetEdge::CheckAndSetINetEdgeState(INetEdgeState)
0x18009b8e6  mov     edi, eax
0x18009b8e8  cmp     eax, 1
0x18009b8eb  jnz     short loc_18009B93C
0x18009b8ed  mov     r9d, 7
0x18009b8f3  xor     r8d, r8d
0x18009b8f6  mov     edx, 3
0x18009b8fb  mov     rcx, rsi
0x18009b8fe  call    ?TransitState@CINetEdge@@IEAAXKHW4INetEdgeState@@@Z; CINetEdge::TransitState(ulong,int,INetEdgeState)
0x18009b903  mov     edx, edi
0x18009b905  jmp     loc_18009BDDC
0x18009b90a  mov     eax, ebx
0x18009b90c  lock xadd [r15], eax
0x18009b911  cmp     eax, 1
0x18009b914  jnz     short loc_18009B92D
0x18009b916  mov     rax, [rsi]
0x18009b919  mov     edx, 1
0x18009b91e  mov     rcx, rsi
0x18009b921  mov     rax, [rax+0D8h]
0x18009b928  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b92d  mov     edx, 8
0x18009b932  mov     rcx, rsi
0x18009b935  call    ?CheckAndSetINetEdgeState@CINetEdge@@IEAA?AW4INetEdgeStateTransition@@W4INetEdgeState@@@Z; CINetEdge::CheckAndSetINetEdgeState(INetEdgeState)
0x18009b93a  mov     edi, eax
0x18009b93c  mov     edx, edi
0x18009b93e  jmp     loc_18009BDDC
0x18009b943  mov     edx, [r14+8]; unsigned int
0x18009b947  mov     r8d, 800C0004h; int
0x18009b94d  call    ?SetBindResult@CINetEdge@@MEAAJKJ@Z; CINetEdge::SetBindResult(ulong,long)
0x18009b952  mov     edi, eax
0x18009b954  jmp     loc_18009BD23
0x18009b959  mov     rdi, [r14]; jumptable 000000018009B83F case 4
0x18009b95c  mov     rcx, rsi; this
0x18009b95f  test    rdi, rdi
0x18009b962  jz      loc_18009BA95
0x18009b968  xor     edx, edx
0x18009b96a  mov     r8d, 3
0x18009b970  call    ?SetStatePending@CINetEdge@@IEAAJJW4ePendingStateReason@1@H@Z; CINetEdge::SetStatePending(long,CINetEdge::ePendingStateReason,int)
0x18009b975  lea     rcx, [rsi+3D8h]; lpCriticalSection
0x18009b97c  call    cs:__imp_EnterCriticalSection
0x18009b983  nop     dword ptr [rax+rax+00h]
0x18009b988  cmp     dword ptr [rsi+2CCh], 1
0x18009b98f  jnz     short loc_18009B9B7
0x18009b991  mov     rax, [rsi]
0x18009b994  mov     rdx, rdi
0x18009b997  mov     rcx, rsi
0x18009b99a  mov     dword ptr [rsi+2CCh], 2
0x18009b9a4  mov     rax, [rax+1F8h]
0x18009b9ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b9b0  mov     [rsi+178h], rdi
0x18009b9b7  lea     rcx, [rsi+3D8h]; lpCriticalSection
0x18009b9be  call    cs:__imp_LeaveCriticalSection
0x18009b9c5  nop     dword ptr [rax+rax+00h]
0x18009b9ca  xor     r12b, r12b
0x18009b9cd  cmp     qword ptr [rsi+178h], 0
0x18009b9d5  jz      short loc_18009BA3A
0x18009b9d7  mov     rax, [rsi]
0x18009b9da  mov     rcx, rsi
0x18009b9dd  mov     rax, [rax+108h]
0x18009b9e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b9e9  mov     rcx, rsi; this
0x18009b9ec  call    ?GetRefCountedBindInfo@CINetEdge@@IEAAPEAUIInternetBindInfo@@_N@Z; CINetEdge::GetRefCountedBindInfo(bool)
0x18009b9f1  mov     r14, rax
0x18009b9f4  test    rax, rax
0x18009b9f7  jz      short loc_18009BA33
0x18009b9f9  mov     rdx, [rsi]
0x18009b9fc  mov     rcx, rsi
0x18009b9ff  mov     rax, [rdx+110h]
0x18009ba06  mov     rdx, r14
0x18009ba09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ba0e  mov     rcx, [rsp+210h+var_1B0]
0x18009ba13  mov     edx, 0Bh
0x18009ba18  call    ?CheckAndSetINetEdgeState@CINetEdge@@IEAA?AW4INetEdgeStateTransition@@W4INetEdgeState@@@Z; CINetEdge::CheckAndSetINetEdgeState(INetEdgeState)
0x18009ba1d  mov     edi, eax
0x18009ba1f  mov     rcx, r14
0x18009ba22  mov     rax, [r14]
0x18009ba25  mov     rax, [rax+10h]
0x18009ba29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ba2e  mov     r12b, 1
0x18009ba31  jmp     short loc_18009BA6C
0x18009ba33  mov     rcx, [rsp+210h+var_1B0]
0x18009ba38  jmp     short loc_18009BA60
0x18009ba3a  mov     eax, ebx
0x18009ba3c  lock xadd [r15], eax
0x18009ba41  cmp     eax, 1
0x18009ba44  jnz     short loc_18009BA5D
0x18009ba46  mov     rax, [rsi]
0x18009ba49  mov     edx, 1
0x18009ba4e  mov     rcx, rsi
0x18009ba51  mov     rax, [rax+0D8h]
0x18009ba58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ba5d  mov     rcx, rsi
0x18009ba60  mov     edx, 0Ch
0x18009ba65  call    ?CheckAndSetINetEdgeState@CINetEdge@@IEAA?AW4INetEdgeStateTransition@@W4INetEdgeState@@@Z; CINetEdge::CheckAndSetINetEdgeState(INetEdgeState)
0x18009ba6a  mov     edi, eax
0x18009ba6c  cmp     edi, 1
0x18009ba6f  jnz     loc_18009B93C
0x18009ba75  test    r12b, r12b
0x18009ba78  jz      def_18009B83F; jumptable 000000018009B83F default case, cases 6,7
0x18009ba7e  mov     rax, [rsi]
0x18009ba81  mov     rcx, rsi
0x18009ba84  mov     rax, [rax+0F8h]
0x18009ba8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ba90  jmp     def_18009B83F; jumptable 000000018009B83F default case, cases 6,7
0x18009ba95  mov     edx, [r14+8]; unsigned int
0x18009ba99  mov     r8d, 800C0006h; int
0x18009ba9f  call    ?SetBindResult@CINetEdge@@MEAAJKJ@Z; CINetEdge::SetBindResult(ulong,long)
  ... truncated ...
```
