# CINetHttpEdge::INetAsyncSendRequest(void)

- ea: `0x18009a0c0`
- end: `0x18009ac77`
- name: `?INetAsyncSendRequest@CINetHttpEdge@@UEAAJXZ`
- size: `2999`
- prototype: `__int64 __fastcall(CINetHttpEdge *__hidden this)`
- caller_count: `0`
- callee_count: `34`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180008610`
- `0x18000a8d0`
- `0x18000b2e0`
- `0x18000b490`
- `0x18000d1b0`
- `0x18000e7f0`
- `0x180012350`
- `0x180017340`
- `0x180017e60`
- `0x180028410`
- `0x180033780`
- `0x180033858`
- `0x18003426c`
- `0x18005cd30`
- `0x18005d1e0`
- `0x1800614ec`
- `0x180067460`
- `0x180070fa8`
- `0x1800786e8`
- `0x18007dbe0`
- `0x18007e1c0`
- `0x18007ff78`
- `0x180081f34`
- `0x18008321c`
- `0x180083c44`
- `0x180088d1c`
- `0x180098e50`
- `0x18009a0c0`
- `0x18009c70c`
- `0x1800bd9a8`
- `0x1800ecef4`
- `0x1801285e6`
- `0x180128660`
- `0x180129010`

## import_xrefs

- `msvcrt!_wtol` at `0x18009a966`
- `msvcrt!_wtol` at `0x18009a966`
- `iertutil!__imp_CoInternetFeatureValueInternal` at `0x18009ab13`
- `iertutil!__imp_CoInternetFeatureValueInternal` at `0x18009ab13`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009a1e2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009aa93`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009a1e2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009aa93`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009a1c5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009aa54`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009a1c5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009aa54`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18009a8b9`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18009a8b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009a228`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009a349`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009a713`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009a228`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009a349`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009a713`
- `WININET!InternetSetOptionW` at `0x18009a548`
- `WININET!InternetSetOptionW` at `0x18009a57c`
- `WININET!InternetSetOptionW` at `0x18009a5b0`
- `WININET!InternetSetOptionW` at `0x18009a6fd`
- `WININET!InternetSetOptionW` at `0x18009a548`
- `WININET!InternetSetOptionW` at `0x18009a57c`
- `WININET!InternetSetOptionW` at `0x18009a5b0`
- `WININET!InternetSetOptionW` at `0x18009a6fd`
- `WININET!InternetSetOptionA` at `0x18009a3ae`
- `WININET!InternetSetOptionA` at `0x18009a48b`
- `WININET!InternetSetOptionA` at `0x18009a4b6`
- `WININET!InternetSetOptionA` at `0x18009a50c`
- `WININET!InternetSetOptionA` at `0x18009a61b`
- `WININET!InternetSetOptionA` at `0x18009a663`
- `WININET!InternetSetOptionA` at `0x18009a816`
- `WININET!InternetSetOptionA` at `0x18009a840`
- `WININET!InternetSetOptionA` at `0x18009aaee`
- `WININET!InternetSetOptionA` at `0x18009a3ae`
- `WININET!InternetSetOptionA` at `0x18009a48b`
- `WININET!InternetSetOptionA` at `0x18009a4b6`
- `WININET!InternetSetOptionA` at `0x18009a50c`
- `WININET!InternetSetOptionA` at `0x18009a61b`
- `WININET!InternetSetOptionA` at `0x18009a663`
- `WININET!InternetSetOptionA` at `0x18009a816`
- `WININET!InternetSetOptionA` at `0x18009a840`
- `WININET!InternetSetOptionA` at `0x18009aaee`
- `WININET!HttpPushEnable` at `0x18009a7a0`
- `WININET!HttpPushEnable` at `0x18009a7a0`

## pseudocode

```c
__int64 __fastcall CINetHttpEdge::INetAsyncSendRequest(CINetHttpEdge *this)
{
  int NextSendBuffer; // edi
  int v3; // esi
  unsigned int v4; // r15d
  void *v5; // r13
  char v6; // cl
  char v7; // r8
  struct IInternetBindInfo *RefCountedBindInfo; // rax
  struct IInternetBindInfo *v9; // r14
  struct IInternetBindInfoVtbl *v10; // rax
  unsigned __int16 *v11; // rax
  void *v12; // rcx
  unsigned int IsDNTException; // eax
  void *v14; // rcx
  __int64 v15; // rsi
  BOOL v16; // edi
  void *v17; // rcx
  void *v18; // rcx
  int v19; // ecx
  int v20; // eax
  void *v21; // rcx
  void *v22; // rcx
  void *v23; // rcx
  void *v24; // rcx
  struct IInternetBindInfoVtbl *lpVtbl; // rax
  int v26; // eax
  _WORD *v27; // rcx
  __int64 v28; // r9
  DWORD v29; // eax
  void *v30; // rcx
  struct IInternetBindInfo *v31; // rax
  struct IInternetBindInfo *v32; // r15
  struct IInternetBindInfoVtbl *v33; // rcx
  struct IInternetBindInfoVtbl *v34; // rax
  unsigned int v35; // r14d
  int v36; // esi
  const char *v37; // r9
  __int64 v38; // rcx
  struct IStream *RefCountedStream; // r14
  void *v40; // rcx
  unsigned int v41; // ebx
  int Buffer; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID lpBuffer; // [rsp+50h] [rbp-B0h] BYREF
  char v46; // [rsp+58h] [rbp-A8h]
  unsigned int v47; // [rsp+60h] [rbp-A0h]
  __int64 v48; // [rsp+68h] [rbp-98h] BYREF
  void *v49; // [rsp+70h] [rbp-90h] BYREF
  char v50; // [rsp+78h] [rbp-88h]
  CINetHttpEdge *v51; // [rsp+80h] [rbp-80h] BYREF
  char v52; // [rsp+88h] [rbp-78h]
  struct _EVENT_DATA_DESCRIPTOR v53; // [rsp+90h] [rbp-70h] BYREF
  LPVOID *p_lpBuffer; // [rsp+B0h] [rbp-50h]
  __int64 v55; // [rsp+B8h] [rbp-48h]
  unsigned __int8 v56[512]; // [rsp+C0h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2F8h] [rbp+1F8h]

  if ( (unsigned int)dword_180166000 > 5 && (qword_180166010 & 0x20) != 0 && (qword_180166018 & 0x20) == qword_180166018 )
  {
    lpBuffer = this;
    p_lpBuffer = &lpBuffer;
    v55 = 8;
    tlgWriteTransfer_BrowserWriteTransfer((__int64)&dword_180166000, (unsigned __int8 *)byte_180151F33, 0, 0, 3u, &v53);
  }
  v51 = this;
  v52 = 0;
  _InterlockedIncrement((volatile signed __int32 *)this + 300);
  NextSendBuffer = 0;
  if ( !CINetEdge::CAutoStateLock::AcquireLock((CINetEdge::CAutoStateLock *)&v51) )
  {
    v3 = 2;
    goto LABEL_124;
  }
  v3 = CINetEdge::CheckAndSetINetEdgeState((__int64)this, 14);
  if ( v3 != 1 )
    goto LABEL_124;
  v4 = 1223;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 984));
  *((_DWORD *)this + 32) = 5;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 984));
  v5 = 0;
  v47 = 0;
  CINetHttpEdge::GetVerb(this);
  v6 = *((_BYTE *)this + 976);
  if ( ((v6 & 2) != 0 || *((_DWORD *)this + 108) + *((_DWORD *)this + 109)) && *((_QWORD *)this + 159) )
  {
    CoTaskMemFree(*((LPVOID *)this + 159));
    v6 = *((_BYTE *)this + 976);
    *((_QWORD *)this + 159) = 0;
  }
  if ( (v6 & 2) == 0 && !(*((_DWORD *)this + 108) + *((_DWORD *)this + 109)) )
    CINetHttpEdge::GetAdditionalHeader(this);
  v7 = *((_BYTE *)this + 976);
  if ( (v7 & 6) != 2 )
  {
    v47 = 0;
    if ( this != (CINetHttpEdge *)-752LL && *((_DWORD *)this + 199) && *((_DWORD *)this + 192) == 1 )
    {
      v5 = (void *)*((_QWORD *)this + 97);
      v47 = *((_DWORD *)this + 202);
    }
  }
  if ( !*((_DWORD *)this + 108) && !*((_DWORD *)this + 109) && (v7 & 2) == 0 )
  {
    NextSendBuffer = CINetHttpEdge::HttpNegBeginningTransaction(this);
    if ( NextSendBuffer == -2147467260 )
    {
LABEL_121:
      *((_DWORD *)this + 31) = NextSendBuffer;
      CINetEdge::SetBindResult(this, v4, NextSendBuffer);
      v3 = CINetEdge::CheckAndSetINetEdgeState((__int64)this, 17);
      if ( v3 != 1 )
        goto LABEL_124;
      goto LABEL_119;
    }
  }
  RefCountedBindInfo = CINetEdge::GetRefCountedBindInfo(this);
  v9 = RefCountedBindInfo;
  if ( !RefCountedBindInfo )
  {
    NextSendBuffer = -2147467260;
    goto LABEL_121;
  }
  if ( (*((_BYTE *)this + 740) & 0x20) == 0 || *((_QWORD *)this + 160) )
  {
    if ( NextSendBuffer < 0 )
      goto LABEL_78;
LABEL_32:
    if ( g_fDoNotTrackAllowExceptions && g_fDoNotTrack )
    {
      IsDNTException = CINetEdge::IsDNTException(this, *((struct IUri **)this + 17));
      v14 = (void *)*((_QWORD *)this + 47);
      Buffer = IsDNTException;
      InternetSetOptionA(v14, 0x7Bu, &Buffer, 4u);
    }
    CINetHttpEdge::HttpNegGetRootSecurityId(this);
    v15 = *((_QWORD *)this + 17);
    lpBuffer = this;
    v46 = 0;
    _InterlockedIncrement((volatile signed __int32 *)this + 300);
    v16 = 1;
    if ( CINetEdge::CAutoStateLock::AcquireLock((CINetEdge::CAutoStateLock *)&lpBuffer)
      && *((_QWORD *)this + 162)
      && (int)EnsureSecurityManager() >= 0 )
    {
      if ( *((_QWORD *)this + 162) == -1 )
      {
        v16 = 0;
      }
      else
      {
        Buffer = 512;
        if ( (int)GetZoneAgnosticSecurityIdFromUri(
                    (__int64)g_pInternetSecurityManagerEx2,
                    v15,
                    (__int64)v56,
                    (__int64)&Buffer,
                    0) >= 0 )
          v16 = SecurityIdsMatch(v56, Buffer, *((unsigned __int8 **)this + 162), *((_DWORD *)this + 326)) == 0;
      }
    }
    CINetEdge::CAutoStateLock::~CAutoStateLock((CINetEdge::CAutoStateLock *)&lpBuffer);
    v17 = (void *)*((_QWORD *)this + 47);
    LODWORD(v48) = v16;
    InternetSetOptionA(v17, 0x56u, &v48, 4u);
    v18 = (void *)*((_QWORD *)this + 47);
    LODWORD(pv) = 1;
    InternetSetOptionA(v18, 0x41u, &pv, 4u);
    v19 = *((_DWORD *)this + 185);
    Buffer = 0;
    if ( (v19 & 0x10001) != 0 )
    {
      v20 = 0;
      if ( (v19 & 1) != 0 )
      {
        Buffer = 4;
        v20 = 4;
      }
      if ( (v19 & 0x10000) != 0 )
        Buffer = v20 | 8;
      InternetSetOptionA(*((HINTERNET *)this + 47), 0x55u, &Buffer, 4u);
    }
    CINetEdge::EnableSingleSignOnIfNeeded(this);
    if ( (*((_BYTE *)this + 740) & 0x40) == 0 )
    {
      v21 = (void *)*((_QWORD *)this + 47);
      Buffer = 1;
      InternetSetOptionW(v21, 0x7Au, &Buffer, 4u);
    }
    if ( (*((_BYTE *)this + 744) & 2) != 0 )
    {
      v22 = (void *)*((_QWORD *)this + 47);
      Buffer = 1;
      InternetSetOptionW(v22, 0xAAu, &Buffer, 4u);
    }
    if ( (*((_BYTE *)this + 744) & 4) != 0 )
    {
      v23 = (void *)*((_QWORD *)this + 47);
      Buffer = 1;
      InternetSetOptionW(v23, 0xACu, &Buffer, 4u);
    }
    v49 = 0;
    if ( (int)CINetEdge::QueryService(this, &GUID_79eac9d5_bafa_11ce_8c82_00aa004ba90b, &v49) >= 0 && v49 )
    {
      lpBuffer = 0;
      if ( !(*(unsigned int (__fastcall **)(void *, GUID *, LPVOID *))(*(_QWORD *)v49 + 24LL))(
              v49,
              &IID_IWindowForBindingUI,
              &lpBuffer) )
        InternetSetOptionA(*((HINTERNET *)this + 47), 0x70u, &lpBuffer, 8u);
      (*(void (__fastcall **)(void *))(*(_QWORD *)v49 + 16LL))(v49);
    }
    if ( (*((_DWORD *)this + 203) & 0x20000000) != 0 )
    {
      v24 = (void *)*((_QWORD *)this + 47);
      Buffer = 1;
      InternetSetOptionA(v24, 0x6Eu, &Buffer, 4u);
    }
    if ( *((_DWORD *)this + 199) == 1 && (*((_BYTE *)this + 1360) & 0x20) == 0 )
    {
      lpVtbl = v9->lpVtbl;
      Buffer = 0;
      lpBuffer = 0;
      v26 = ((__int64 (__fastcall *)(struct IInternetBindInfo *, __int64, LPVOID *, __int64, int *))lpVtbl->GetBindString)(
              v9,
              12,
              &lpBuffer,
              1,
              &Buffer);
      v27 = lpBuffer;
      if ( lpBuffer )
      {
        if ( !v26 )
        {
          *((_BYTE *)this + 1360) |= 0x20u;
          v28 = -1;
          do
            ++v28;
          while ( v27[v28] );
          InternetSetOptionW(*((HINTERNET *)this + 47), 0x35u, v27, v28 + 1);
          v27 = lpBuffer;
        }
        if ( v27 )
          CoTaskMemFree(v27);
      }
    }
    lpBuffer = this;
    v46 = 0;
    _InterlockedIncrement((volatile signed __int32 *)this + 300);
    if ( !CINetEdge::CAutoStateLock::AcquireLock((CINetEdge::CAutoStateLock *)&lpBuffer) )
    {
      NextSendBuffer = -2147467259;
      goto LABEL_77;
    }
    NextSendBuffer = 0;
    if ( !memcmp_0((char *)this + 1936, &GUID_NULL, 0x10u) || !memcmp_0((char *)this + 1952, &GUID_NULL, 0x10u) )
      goto LABEL_77;
    if ( *((_QWORD *)this + 241) )
    {
      v29 = 12019;
    }
    else
    {
      v29 = HttpPushEnable(
              *((HINTERNET *)this + 47),
              (HTTP_PUSH_TRANSPORT_SETTING *)((char *)this + 1936),
              (HTTP_PUSH_WAIT_HANDLE *)this + 241);
      if ( !v29 )
      {
LABEL_77:
        CINetEdge::CAutoStateLock::~CAutoStateLock((CINetEdge::CAutoStateLock *)&lpBuffer);
        goto LABEL_78;
      }
    }
    v4 = v29;
    NextSendBuffer = -2147467260;
    goto LABEL_77;
  }
  v10 = RefCountedBindInfo->lpVtbl;
  Buffer = 0;
  pv = 0;
  NextSendBuffer = -2147024882;
  if ( ((int (__fastcall *)(struct IInternetBindInfo *, __int64, LPVOID *, __int64, int *))v10->GetBindString)(
         v9,
         19,
         &pv,
         1,
         &Buffer) >= 0 )
  {
    v11 = OLESTRDuplicate((const unsigned __int16 *)pv);
    v12 = pv;
    *((_QWORD *)this + 160) = v11;
    if ( v12 )
      CoTaskMemFree(v12);
    if ( *((_QWORD *)this + 160) )
    {
      CINetHttpEdge::SetWininetDownloadModeCore((HINTERNET *)this);
      goto LABEL_32;
    }
  }
LABEL_78:
  ((void (__fastcall *)(struct IInternetBindInfo *))v9->lpVtbl->Release)(v9);
  if ( NextSendBuffer == -2147467260 )
    goto LABEL_121;
  CINetHttpEdge::SetWininetPriority(this);
  if ( (*((_DWORD *)this + 130) & 0x4000010) == 0x10 )
  {
    v30 = (void *)*((_QWORD *)this + 47);
    LODWORD(pv) = 1;
    InternetSetOptionA(v30, 0x73u, &pv, 4u);
  }
  if ( (*((_DWORD *)this + 185) & 0x1000000) != 0 )
    InternetSetOptionA(*((HINTERNET *)this + 47), 0x7Cu, 0, 0);
  v31 = CINetEdge::GetRefCountedBindInfo(this);
  v32 = v31;
  if ( v31 )
  {
    v33 = v31->lpVtbl;
    LODWORD(pv) = 0;
    if ( ((int (__fastcall *)(struct IInternetBindInfo *, __int64, char *, __int64, LPVOID *))v33->GetBindString)(
           v31,
           24,
           (char *)this + 1352,
           1,
           &pv) >= 0 )
      (*(void (__fastcall **)(CINetHttpEdge *))(*(_QWORD *)this + 408LL))(this);
    InitOnceExecuteOnce(&stru_18016BB00, (PINIT_ONCE_FN)InitOnceDeviceFamily, 0, 0);
    if ( byte_18016AF34 )
    {
      v49 = this;
      v50 = 0;
      _InterlockedIncrement((volatile signed __int32 *)this + 300);
      if ( CINetEdge::CAutoStateLock::AcquireLock((CINetEdge::CAutoStateLock *)&v49) )
      {
        v34 = v32->lpVtbl;
        v48 = 0;
        v35 = 0;
        v36 = ((__int64 (__fastcall *)(struct IInternetBindInfo *, GUID *, __int64 *))v34->QueryInterface)(
                v32,
                &GUID_8fd4c3a8_e3e8_4b62_9f2f_483e5c09661d,
                &v48);
        if ( v36 >= 0 )
        {
          Buffer = 0;
          lpBuffer = 0;
          v36 = (*(__int64 (__fastcall **)(__int64, __int64, LPVOID *, int *))(*(_QWORD *)v48 + 32LL))(
                  v48,
                  2,
                  &lpBuffer,
                  &Buffer);
          if ( !v36 )
          {
            if ( !Buffer || !lpBuffer )
              wil::details::in1diag3::_FailFast_GetLastError(
                retaddr,
                (void *)0x24E9,
                (__int64)"onecoreuap\\inetcore\\urlmon\\iapp\\edge\\cnetedge.cxx",
                v37);
            v35 = _wtol((const wchar_t *)lpBuffer);
          }
        }
        v38 = v48;
        if ( v48 )
        {
          v48 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
        }
        CINetEdge::CAutoStateLock::~CAutoStateLock((CINetEdge::CAutoStateLock *)&v49);
        if ( v36 >= 0 && v35 )
          CINetEdge::s_SetTimeoutsOnHandle(*((HINTERNET *)this + 47), v35, 1, v35, 1, v35, 1);
      }
      else
      {
        CINetEdge::CAutoStateLock::~CAutoStateLock((CINetEdge::CAutoStateLock *)&v49);
      }
    }
    ((void (__fastcall *)(struct IInternetBindInfo *))v32->lpVtbl->Release)(v32);
  }
  CINetHttpEdge::ComputeSameSiteCookiePolicy(this, 0);
  CINetEdge::SetStatePending((__int64)this, -2147483638, 4);
  if ( !NextSendBuffer )
  {
    v3 = CINetEdge::CheckAndSetINetEdgeState((__int64)this, 15);
    if ( CINetEdge::IsUpLoad(this) )
    {
      RefCountedStream = CINetHttpEdge::GetRefCountedStream(this);
      if ( RefCountedStream )
        goto LABEL_108;
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 984));
      if ( this != (CINetHttpEdge *)-752LL && *((_DWORD *)this + 192) == 4 )
      {
        RefCountedStream = (struct IStream *)*((_QWORD *)this + 97);
        ((void (__fastcall *)(struct IStream *))RefCountedStream->lpVtbl->AddRef)(RefCountedStream);
        *((_QWORD *)this + 238) = RefCountedStream;
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 984));
      if ( RefCountedStream )
      {
LABEL_108:
        NextSendBuffer = CINetHttpEdge::GetNextSendBuffer(
                           this,
                           (struct _INTERNET_BUFFERSW *)((char *)this + 888),
                           RefCountedStream,
                           1);
        ((void (__fastcall *)(struct IStream *))RefCountedStream->lpVtbl->Release)(RefCountedStream);
      }
    }
    else
    {
      v40 = (void *)*((_QWORD *)this + 47);
      LODWORD(pv) = 11;
      InternetSetOptionA(v40, 0x3Eu, &pv, 4u);
    }
    if ( FCK::FEATURE_BROWSER_EMULATION )
    {
      Buffer = 0;
      if ( (int)CoInternetFeatureValueInternal(FCK::FEATURE_BROWSER_EMULATION, &Buffer) < 0 )
      {
LABEL_115:
        NextSendBuffer = CINetHttpEdge::DoSendRequest(this, NextSendBuffer, v5, v47);
        goto LABEL_124;
      }
      dword_180166E68 = Buffer;
      FCK::FEATURE_BROWSER_EMULATION = 0;
    }
    if ( dword_180166E68 != 7000 )
      CoInternetGetBrowserEmulationState((CINetHttpEdge *)((char *)this + 1416));
    goto LABEL_115;
  }
  CINetEdge::SetStatePending((__int64)this, 0, 4);
  v3 = CINetEdge::CheckAndSetINetEdgeState((__int64)this, 17);
  if ( v3 == 1 && NextSendBuffer != -2147483638 && *((_DWORD *)this + 31) )
LABEL_119:
    CINetHttpEdge::ReportResultAndStop(this, NextSendBuffer, 0, 0, 0);
LABEL_124:
  v41 = CINetEdge::CheckTransitionStatusAndDispatchAbort((unsigned int *)this, v3, NextSendBuffer);
  CINetEdge::CAutoStateLock::~CAutoStateLock((CINetEdge::CAutoStateLock *)&v51);
  return v41;
}

```

## disassembly

```asm
0x18009a0c0  push    rbp
0x18009a0c2  push    rbx
0x18009a0c3  lea     rbp, [rsp-1E8h]
0x18009a0cb  sub     rsp, 2E8h
0x18009a0d2  mov     rax, cs:__security_cookie
0x18009a0d9  xor     rax, rsp
0x18009a0dc  mov     [rbp+1F0h+var_30], rax
0x18009a0e3  mov     eax, cs:dword_180166000
0x18009a0e9  mov     rbx, rcx
0x18009a0ec  cmp     eax, 5
0x18009a0ef  jbe     short loc_18009A14E
0x18009a0f1  mov     rcx, cs:qword_180166018
0x18009a0f8  mov     rax, cs:qword_180166010
0x18009a0ff  test    al, 20h
0x18009a101  jz      short loc_18009A14E
0x18009a103  mov     rax, rcx
0x18009a106  and     eax, 20h
0x18009a109  cmp     rax, rcx
0x18009a10c  jnz     short loc_18009A14E
0x18009a10e  lea     rax, [rsp+2F0h+lpBuffer]
0x18009a113  mov     [rsp+2F0h+lpBuffer], rbx
0x18009a118  mov     [rbp+1F0h+var_240], rax
0x18009a11c  lea     rdx, byte_180151F33
0x18009a123  lea     rax, [rbp+1F0h+var_260]
0x18009a127  mov     [rbp+1F0h+var_238], 8
0x18009a12f  mov     qword ptr [rsp+2F0h+var_2C8], rax
0x18009a134  lea     rcx, dword_180166000
0x18009a13b  xor     r9d, r9d
0x18009a13e  mov     dword ptr [rsp+2F0h+var_2D0], 3
0x18009a146  xor     r8d, r8d
0x18009a149  call    _tlgWriteTransfer_BrowserWriteTransfer
0x18009a14e  mov     [rsp+2F0h+arg_8], rsi
0x18009a156  mov     [rsp+2F0h+arg_10], rdi
0x18009a15e  mov     [rsp+2F0h+arg_18], r12
0x18009a166  mov     [rsp+2F0h+var_10], r13
0x18009a16e  mov     [rsp+2F0h+var_18], r14
0x18009a176  mov     [rsp+2F0h+var_20], r15
0x18009a17e  mov     [rbp+1F0h+var_270], rbx
0x18009a182  mov     [rbp+1F0h+var_268], 0
0x18009a186  lock inc dword ptr [rbx+4B0h]
0x18009a18d  lea     rcx, [rbp+1F0h+var_270]; this
0x18009a191  call    ?AcquireLock@CAutoStateLock@CINetEdge@@QEAA_NXZ; CINetEdge::CAutoStateLock::AcquireLock(void)
0x18009a196  xor     edi, edi
0x18009a198  test    al, al
0x18009a19a  jz      loc_18009ABF5
0x18009a1a0  mov     edx, 0Eh
0x18009a1a5  mov     rcx, rbx
0x18009a1a8  call    ?CheckAndSetINetEdgeState@CINetEdge@@IEAA?AW4INetEdgeStateTransition@@W4INetEdgeState@@@Z; CINetEdge::CheckAndSetINetEdgeState(INetEdgeState)
0x18009a1ad  mov     esi, eax
0x18009a1af  cmp     eax, 1
0x18009a1b2  jnz     loc_18009ABFA
0x18009a1b8  lea     rcx, [rbx+3D8h]; lpCriticalSection
0x18009a1bf  mov     r15d, 4C7h
0x18009a1c5  call    cs:__imp_EnterCriticalSection
0x18009a1cc  nop     dword ptr [rax+rax+00h]
0x18009a1d1  lea     rcx, [rbx+3D8h]; lpCriticalSection
0x18009a1d8  mov     dword ptr [rbx+80h], 5
0x18009a1e2  call    cs:__imp_LeaveCriticalSection
0x18009a1e9  nop     dword ptr [rax+rax+00h]
0x18009a1ee  xor     esi, esi
0x18009a1f0  mov     rcx, rbx; this
0x18009a1f3  mov     r13d, esi
0x18009a1f6  mov     [rsp+2F0h+var_290], esi
0x18009a1fa  call    ?GetVerb@CINetHttpEdge@@QEAAPEBGXZ; CINetHttpEdge::GetVerb(void)
0x18009a1ff  movzx   ecx, byte ptr [rbx+3D0h]
0x18009a206  test    cl, 2
0x18009a209  jnz     short loc_18009A219
0x18009a20b  mov     eax, [rbx+1B4h]
0x18009a211  add     eax, [rbx+1B0h]
0x18009a217  jz      short loc_18009A242
0x18009a219  mov     rax, [rbx+4F8h]
0x18009a220  test    rax, rax
0x18009a223  jz      short loc_18009A242
0x18009a225  mov     rcx, rax; pv
0x18009a228  call    cs:__imp_CoTaskMemFree
0x18009a22f  nop     dword ptr [rax+rax+00h]
0x18009a234  movzx   ecx, byte ptr [rbx+3D0h]
0x18009a23b  mov     [rbx+4F8h], rsi
0x18009a242  test    cl, 2
0x18009a245  jnz     short loc_18009A25D
0x18009a247  mov     eax, [rbx+1B4h]
0x18009a24d  add     eax, [rbx+1B0h]
0x18009a253  jnz     short loc_18009A25D
0x18009a255  mov     rcx, rbx; this
0x18009a258  call    ?GetAdditionalHeader@CINetHttpEdge@@QEAAJXZ; CINetHttpEdge::GetAdditionalHeader(void)
0x18009a25d  movzx   r8d, byte ptr [rbx+3D0h]
0x18009a265  movzx   eax, r8b
0x18009a269  and     al, 6
0x18009a26b  cmp     al, 2
0x18009a26d  jz      short loc_18009A29A
0x18009a26f  lea     rdx, [rbx+2F0h]
0x18009a276  mov     [rsp+2F0h+var_290], esi
0x18009a27a  test    rdx, rdx
0x18009a27d  jz      short loc_18009A29A
0x18009a27f  mov     ecx, [rdx+2Ch]
0x18009a282  test    ecx, ecx
0x18009a284  jz      short loc_18009A29A
0x18009a286  sub     ecx, 1
0x18009a289  cmp     dword ptr [rdx+10h], 1
0x18009a28d  jnz     short loc_18009A29A
0x18009a28f  mov     eax, [rdx+38h]
0x18009a292  mov     r13, [rdx+18h]
0x18009a296  mov     [rsp+2F0h+var_290], eax
0x18009a29a  cmp     [rbx+1B0h], esi
0x18009a2a0  jnz     short loc_18009A2C5
0x18009a2a2  cmp     [rbx+1B4h], esi
0x18009a2a8  jnz     short loc_18009A2C5
0x18009a2aa  test    r8b, 2
0x18009a2ae  jnz     short loc_18009A2C5
0x18009a2b0  mov     rcx, rbx; this
0x18009a2b3  call    ?HttpNegBeginningTransaction@CINetHttpEdge@@QEAAJXZ; CINetHttpEdge::HttpNegBeginningTransaction(void)
0x18009a2b8  mov     edi, eax
0x18009a2ba  cmp     eax, 80004004h
0x18009a2bf  jz      loc_18009ABB5
0x18009a2c5  mov     rcx, rbx; this
0x18009a2c8  call    ?GetRefCountedBindInfo@CINetEdge@@IEAAPEAUIInternetBindInfo@@_N@Z; CINetEdge::GetRefCountedBindInfo(bool)
0x18009a2cd  mov     r14, rax
0x18009a2d0  test    rax, rax
0x18009a2d3  jz      loc_18009ABB0
0x18009a2d9  test    byte ptr [rbx+2E4h], 20h
0x18009a2e0  jz      loc_18009A36C
0x18009a2e6  cmp     [rbx+500h], rsi
0x18009a2ed  jnz     short loc_18009A36C
0x18009a2ef  mov     rax, [rax]
0x18009a2f2  lea     rcx, [rsp+2F0h+Buffer]
0x18009a2f7  mov     [rsp+2F0h+var_2D0], rcx
0x18009a2fc  lea     r8, [rsp+2F0h+pv]
0x18009a301  mov     r9d, 1
0x18009a307  mov     [rsp+2F0h+Buffer], esi
0x18009a30b  mov     edx, 13h
0x18009a310  mov     [rsp+2F0h+pv], rsi
0x18009a315  mov     rax, [rax+20h]
0x18009a319  mov     rcx, r14
0x18009a31c  mov     edi, 8007000Eh
0x18009a321  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a326  test    eax, eax
0x18009a328  js      loc_18009A7C4
0x18009a32e  mov     rcx, [rsp+2F0h+pv]; unsigned __int16 *
0x18009a333  call    ?OLESTRDuplicate@@YAPEAGPEBG@Z; OLESTRDuplicate(ushort const *)
0x18009a338  mov     rcx, [rsp+2F0h+pv]; pv
0x18009a33d  mov     [rbx+500h], rax
0x18009a344  test    rcx, rcx
0x18009a347  jz      short loc_18009A355
0x18009a349  call    cs:__imp_CoTaskMemFree
0x18009a350  nop     dword ptr [rax+rax+00h]
0x18009a355  cmp     [rbx+500h], rsi
0x18009a35c  jz      loc_18009A7C4
0x18009a362  mov     rcx, rbx; this
0x18009a365  call    ?SetWininetDownloadModeCore@CINetHttpEdge@@IEAAJXZ; CINetHttpEdge::SetWininetDownloadModeCore(void)
0x18009a36a  jmp     short loc_18009A374
0x18009a36c  test    edi, edi
0x18009a36e  js      loc_18009A7C4
0x18009a374  cmp     cs:?g_fDoNotTrackAllowExceptions@@3HA, esi; int g_fDoNotTrackAllowExceptions
0x18009a37a  jz      short loc_18009A3BA
0x18009a37c  cmp     cs:?g_fDoNotTrack@@3HA, esi; int g_fDoNotTrack
0x18009a382  jz      short loc_18009A3BA
0x18009a384  mov     rdx, [rbx+88h]; struct IUri *
0x18009a38b  mov     rcx, rbx; this
0x18009a38e  call    ?IsDNTException@CINetEdge@@IEAAHPEAUIUri@@@Z; CINetEdge::IsDNTException(IUri *)
0x18009a393  mov     rcx, [rbx+178h]; hInternet
0x18009a39a  lea     r8, [rsp+2F0h+Buffer]; lpBuffer
0x18009a39f  mov     r9d, 4; dwBufferLength
0x18009a3a5  mov     [rsp+2F0h+Buffer], eax
0x18009a3a9  mov     edx, 7Bh ; '{'; dwOption
0x18009a3ae  call    cs:__imp_InternetSetOptionA
0x18009a3b5  nop     dword ptr [rax+rax+00h]
0x18009a3ba  mov     rcx, rbx; this
0x18009a3bd  call    ?HttpNegGetRootSecurityId@CINetHttpEdge@@QEAAJXZ; CINetHttpEdge::HttpNegGetRootSecurityId(void)
0x18009a3c2  mov     rsi, [rbx+88h]
0x18009a3c9  mov     [rsp+2F0h+lpBuffer], rbx
0x18009a3ce  mov     [rsp+2F0h+var_298], 0
0x18009a3d3  lock inc dword ptr [rbx+4B0h]
0x18009a3da  lea     rcx, [rsp+2F0h+lpBuffer]; this
0x18009a3df  mov     edi, 1
0x18009a3e4  call    ?AcquireLock@CAutoStateLock@CINetEdge@@QEAA_NXZ; CINetEdge::CAutoStateLock::AcquireLock(void)
0x18009a3e9  test    al, al
0x18009a3eb  jz      short loc_18009A464
0x18009a3ed  cmp     qword ptr [rbx+510h], 0
0x18009a3f5  jz      short loc_18009A464
0x18009a3f7  call    ?EnsureSecurityManager@@YAJXZ; EnsureSecurityManager(void)
0x18009a3fc  test    eax, eax
0x18009a3fe  js      short loc_18009A464
0x18009a400  cmp     qword ptr [rbx+510h], 0FFFFFFFFFFFFFFFFh
0x18009a408  jnz     short loc_18009A410
0x18009a40a  xor     esi, esi
0x18009a40c  mov     edi, esi
0x18009a40e  jmp     short loc_18009A466
0x18009a410  mov     rcx, cs:?g_pInternetSecurityManagerEx2@@3PEAUIInternetSecurityManagerEx2@@EA; IInternetSecurityManagerEx2 * g_pInternetSecurityManagerEx2
0x18009a417  lea     r9, [rsp+2F0h+Buffer]
0x18009a41c  lea     r8, [rbp+1F0h+var_230]
0x18009a420  mov     [rsp+2F0h+Buffer], 200h
0x18009a428  mov     rdx, rsi
0x18009a42b  mov     [rsp+2F0h+var_2D0], 0
0x18009a434  call    GetZoneAgnosticSecurityIdFromUri
0x18009a439  test    eax, eax
0x18009a43b  js      short loc_18009A464
0x18009a43d  mov     r9d, [rbx+518h]; unsigned int
0x18009a444  lea     rcx, [rbp+1F0h+var_230]; unsigned __int8 *
0x18009a448  mov     r8, [rbx+510h]; unsigned __int8 *
0x18009a44f  mov     edx, [rsp+2F0h+Buffer]; unsigned int
0x18009a453  call    ?SecurityIdsMatch@@YAHPEAEK0K@Z; SecurityIdsMatch(uchar *,ulong,uchar *,ulong)
0x18009a458  xor     esi, esi
0x18009a45a  test    eax, eax
0x18009a45c  mov     edi, esi
0x18009a45e  setz    dil
0x18009a462  jmp     short loc_18009A466
0x18009a464  xor     esi, esi
0x18009a466  lea     rcx, [rsp+2F0h+lpBuffer]; this
0x18009a46b  call    ??1CAutoStateLock@CINetEdge@@QEAA@XZ; CINetEdge::CAutoStateLock::~CAutoStateLock(void)
0x18009a470  mov     rcx, [rbx+178h]; hInternet
0x18009a477  lea     r8, [rsp+2F0h+var_288]; lpBuffer
0x18009a47c  mov     r9d, 4; dwBufferLength
0x18009a482  mov     dword ptr [rsp+2F0h+var_288], edi
0x18009a486  mov     edx, 56h ; 'V'; dwOption
0x18009a48b  call    cs:__imp_InternetSetOptionA
0x18009a492  nop     dword ptr [rax+rax+00h]
0x18009a497  mov     rcx, [rbx+178h]; hInternet
0x18009a49e  lea     r8, [rsp+2F0h+pv]; lpBuffer
0x18009a4a3  mov     r9d, 4; dwBufferLength
0x18009a4a9  mov     dword ptr [rsp+2F0h+pv], 1
0x18009a4b1  mov     edx, 41h ; 'A'; dwOption
0x18009a4b6  call    cs:__imp_InternetSetOptionA
0x18009a4bd  nop     dword ptr [rax+rax+00h]
0x18009a4c2  mov     ecx, [rbx+2E4h]
0x18009a4c8  mov     [rsp+2F0h+Buffer], esi
0x18009a4cc  test    ecx, 10001h
0x18009a4d2  jz      short loc_18009A518
0x18009a4d4  mov     eax, esi
0x18009a4d6  test    cl, 1
0x18009a4d9  jz      short loc_18009A4E8
0x18009a4db  mov     [rsp+2F0h+Buffer], 4
0x18009a4e3  mov     eax, 4
0x18009a4e8  bt      ecx, 10h
0x18009a4ec  jnb     short loc_18009A4F5
0x18009a4ee  or      eax, 8
0x18009a4f1  mov     [rsp+2F0h+Buffer], eax
0x18009a4f5  mov     rcx, [rbx+178h]; hInternet
0x18009a4fc  lea     r8, [rsp+2F0h+Buffer]; lpBuffer
0x18009a501  mov     r9d, 4; dwBufferLength
0x18009a507  mov     edx, 55h ; 'U'; dwOption
0x18009a50c  call    cs:__imp_InternetSetOptionA
0x18009a513  nop     dword ptr [rax+rax+00h]
0x18009a518  mov     rcx, rbx; this
0x18009a51b  call    ?EnableSingleSignOnIfNeeded@CINetEdge@@IEAAXXZ; CINetEdge::EnableSingleSignOnIfNeeded(void)
0x18009a520  test    byte ptr [rbx+2E4h], 40h
0x18009a527  jnz     short loc_18009A554
0x18009a529  mov     rcx, [rbx+178h]; hInternet
0x18009a530  lea     r8, [rsp+2F0h+Buffer]; lpBuffer
0x18009a535  mov     r9d, 4; dwBufferLength
0x18009a53b  mov     [rsp+2F0h+Buffer], 1
0x18009a543  mov     edx, 7Ah ; 'z'; dwOption
0x18009a548  call    cs:__imp_InternetSetOptionW
0x18009a54f  nop     dword ptr [rax+rax+00h]
0x18009a554  test    byte ptr [rbx+2E8h], 2
0x18009a55b  jz      short loc_18009A588
0x18009a55d  mov     rcx, [rbx+178h]; hInternet
0x18009a564  lea     r8, [rsp+2F0h+Buffer]; lpBuffer
0x18009a569  mov     r9d, 4; dwBufferLength
0x18009a56f  mov     [rsp+2F0h+Buffer], 1
0x18009a577  mov     edx, 0AAh; dwOption
0x18009a57c  call    cs:__imp_InternetSetOptionW
0x18009a583  nop     dword ptr [rax+rax+00h]
0x18009a588  test    byte ptr [rbx+2E8h], 4
0x18009a58f  jz      short loc_18009A5BC
0x18009a591  mov     rcx, [rbx+178h]; hInternet
0x18009a598  lea     r8, [rsp+2F0h+Buffer]; lpBuffer
0x18009a59d  mov     r9d, 4; dwBufferLength
0x18009a5a3  mov     [rsp+2F0h+Buffer], 1
0x18009a5ab  mov     edx, 0ACh; dwOption
0x18009a5b0  call    cs:__imp_InternetSetOptionW
0x18009a5b7  nop     dword ptr [rax+rax+00h]
0x18009a5bc  lea     r8, [rsp+2F0h+var_280]; void **
0x18009a5c1  mov     [rsp+2F0h+var_280], rsi
0x18009a5c6  lea     rdx, _GUID_79eac9d5_bafa_11ce_8c82_00aa004ba90b; struct _GUID *
0x18009a5cd  mov     rcx, rbx; this
0x18009a5d0  call    ?QueryService@CINetEdge@@IEAAJAEBU_GUID@@PEAPEAX@Z; CINetEdge::QueryService(_GUID const &,void * *)
0x18009a5d5  test    eax, eax
0x18009a5d7  js      short loc_18009A638
0x18009a5d9  mov     rcx, [rsp+2F0h+var_280]
0x18009a5de  test    rcx, rcx
0x18009a5e1  jz      short loc_18009A638
0x18009a5e3  mov     [rsp+2F0h+lpBuffer], rsi
0x18009a5e8  lea     r8, [rsp+2F0h+lpBuffer]
0x18009a5ed  mov     rax, [rcx]
0x18009a5f0  lea     rdx, IID_IWindowForBindingUI
0x18009a5f7  mov     rax, [rax+18h]
0x18009a5fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a600  test    eax, eax
0x18009a602  jnz     short loc_18009A627
0x18009a604  mov     rcx, [rbx+178h]; hInternet
0x18009a60b  lea     r8, [rsp+2F0h+lpBuffer]; lpBuffer
0x18009a610  mov     r9d, 8; dwBufferLength
0x18009a616  mov     edx, 70h ; 'p'; dwOption
0x18009a61b  call    cs:__imp_InternetSetOptionA
0x18009a622  nop     dword ptr [rax+rax+00h]
0x18009a627  mov     rcx, [rsp+2F0h+var_280]
0x18009a62c  mov     rax, [rcx]
0x18009a62f  mov     rax, [rax+10h]
0x18009a633  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a638  test    dword ptr [rbx+32Ch], 20000000h
  ... truncated ...
```
