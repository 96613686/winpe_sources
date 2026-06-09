# CSnapComponentTelemetry::ProcessView::Stop(IApplicationView *,IImmersiveMonitor *,bool,SnappedWindowOcclusionModel,bool,bool)

- ea: `0x18024b650`
- end: `0x18024bfab`
- name: `?Stop@ProcessView@CSnapComponentTelemetry@@QEAAXPEAUIApplicationView@@PEAUIImmersiveMonitor@@_NW4SnappedWindowOcclusionModel@@22@Z`
- size: `2395`
- prototype: `void __high(struct IApplicationView *, struct IImmersiveMonitor *, bool, enum SnappedWindowOcclusionModel, bool, bool)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002f010`

## callees

- `0x18000f158`
- `0x18002d790`
- `0x180031c70`
- `0x1800cb1d0`
- `0x180151b88`
- `0x18024b650`
- `0x180356360`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18024b80e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18024bb73`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18024b80e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18024bb73`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18024b824`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18024b83f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18024b857`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18024bb89`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18024bba4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18024bbbc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18024b824`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18024b83f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18024b857`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18024bb89`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18024bba4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18024bbbc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18024bf61`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18024bf7b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18024bf61`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18024bf7b`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18024bf22`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18024bf22`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18024bc94`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18024bc94`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18024b90f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18024bc75`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18024b90f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18024bc75`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x18024b902`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x18024bc68`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x18024b902`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x18024bc68`

## string_xrefs

- `0x18024b6fc`: `pcshell\twinui\snapcomponent\lib\SnapComponentTelemetry.h`
- `0x18024b73c`: `pcshell\twinui\snapcomponent\lib\SnapComponentTelemetry.h`
- `0x18024b77f`: `pcshell\twinui\snapcomponent\lib\SnapComponentTelemetry.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall CSnapComponentTelemetry::ProcessView::Stop(
        __int64 a1,
        ApplicationViewTraceLoggingHelpers *a2,
        unsigned __int16 **a3,
        char a4,
        unsigned int a5,
        char a6,
        char a7)
{
  __int64 v11; // rdi
  int v12; // eax
  int v13; // eax
  int v14; // eax
  __int64 v15; // r14
  int v16; // eax
  WCHAR *v17; // r15
  __int64 v18; // r14
  RTL_SRWLOCK *v19; // rbx
  RTL_SRWLOCK *v20; // rbx
  _DWORD *v21; // rdi
  int v22; // r9d
  const WCHAR *v23; // rbx
  LPWSTR FileNameW; // rax
  const WCHAR *v25; // r12
  RTL_SRWLOCK *v26; // rbx
  __int64 v27; // r13
  const WCHAR *v28; // r14
  LPWSTR v29; // rbx
  const WCHAR *v30; // r14
  __int64 v31; // r8
  __int64 v32; // rax
  int v33; // eax
  int v34; // edi
  __int64 v35; // rcx
  int UserDataCount; // [rsp+20h] [rbp-1A0h]
  char v37; // [rsp+140h] [rbp-80h] BYREF
  char v38; // [rsp+141h] [rbp-7Fh] BYREF
  _BYTE v39[2]; // [rsp+142h] [rbp-7Eh] BYREF
  int v40; // [rsp+144h] [rbp-7Ch] BYREF
  int v41; // [rsp+148h] [rbp-78h] BYREF
  unsigned int v42; // [rsp+14Ch] [rbp-74h] BYREF
  int v43; // [rsp+150h] [rbp-70h] BYREF
  unsigned int v44; // [rsp+154h] [rbp-6Ch] BYREF
  int v45; // [rsp+158h] [rbp-68h] BYREF
  __int64 v46; // [rsp+15Ch] [rbp-64h] BYREF
  int v47; // [rsp+164h] [rbp-5Ch] BYREF
  DWORD CurrentThreadId; // [rsp+168h] [rbp-58h] BYREF
  int v49; // [rsp+16Ch] [rbp-54h] BYREF
  int v50; // [rsp+170h] [rbp-50h] BYREF
  __int64 v51; // [rsp+174h] [rbp-4Ch] BYREF
  PSRWLOCK SRWLock; // [rsp+180h] [rbp-40h] BYREF
  PSRWLOCK v53; // [rsp+188h] [rbp-38h] BYREF
  PSRWLOCK v54; // [rsp+190h] [rbp-30h] BYREF
  __int64 v55; // [rsp+198h] [rbp-28h] BYREF
  int v56; // [rsp+1A0h] [rbp-20h] BYREF
  int v57; // [rsp+1A4h] [rbp-1Ch] BYREF
  int v58; // [rsp+1A8h] [rbp-18h] BYREF
  int v59; // [rsp+1ACh] [rbp-14h] BYREF
  int v60; // [rsp+1B0h] [rbp-10h] BYREF
  EVENT_DESCRIPTOR v61; // [rsp+1B8h] [rbp-8h] BYREF
  LPCWSTR pszPath; // [rsp+1C8h] [rbp+8h] BYREF
  __int64 v63; // [rsp+1D0h] [rbp+10h]
  __int64 v64; // [rsp+1D8h] [rbp+18h]
  LPWSTR v65; // [rsp+1E0h] [rbp+20h] BYREF
  const WCHAR *v66; // [rsp+1E8h] [rbp+28h] BYREF
  __int64 v67; // [rsp+1F0h] [rbp+30h] BYREF
  __int64 v68; // [rsp+1F8h] [rbp+38h] BYREF
  __int64 v69; // [rsp+200h] [rbp+40h] BYREF
  __int64 v70; // [rsp+208h] [rbp+48h] BYREF
  __int64 v71; // [rsp+210h] [rbp+50h] BYREF
  __int64 v72; // [rsp+218h] [rbp+58h] BYREF
  __int64 v73; // [rsp+220h] [rbp+60h] BYREF
  __int64 v74; // [rsp+228h] [rbp+68h] BYREF
  __int64 v75; // [rsp+230h] [rbp+70h] BYREF
  LPVOID pv[3]; // [rsp+238h] [rbp+78h] BYREF
  __int128 v77; // [rsp+250h] [rbp+90h] BYREF
  __int128 v78; // [rsp+260h] [rbp+A0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+270h] [rbp+B0h] BYREF
  __int16 *v80; // [rsp+280h] [rbp+C0h]
  int v81; // [rsp+288h] [rbp+C8h]
  int v82; // [rsp+28Ch] [rbp+CCh]
  PSRWLOCK *v83; // [rsp+290h] [rbp+D0h]
  __int64 v84; // [rsp+298h] [rbp+D8h]
  int *v85; // [rsp+2A0h] [rbp+E0h]
  __int64 v86; // [rsp+2A8h] [rbp+E8h]
  DWORD *p_CurrentThreadId; // [rsp+2B0h] [rbp+F0h]
  __int64 v88; // [rsp+2B8h] [rbp+F8h]
  const WCHAR *v89; // [rsp+2C0h] [rbp+100h]
  int v90; // [rsp+2C8h] [rbp+108h]
  int v91; // [rsp+2CCh] [rbp+10Ch]
  LPWSTR v92; // [rsp+2D0h] [rbp+110h]
  int v93; // [rsp+2D8h] [rbp+118h]
  int v94; // [rsp+2DCh] [rbp+11Ch]
  int *v95; // [rsp+2E0h] [rbp+120h]
  __int64 v96; // [rsp+2E8h] [rbp+128h]
  int *v97; // [rsp+2F0h] [rbp+130h]
  __int64 v98; // [rsp+2F8h] [rbp+138h]
  __int64 *v99; // [rsp+300h] [rbp+140h]
  __int64 v100; // [rsp+308h] [rbp+148h]
  char *v101; // [rsp+310h] [rbp+150h]
  __int64 v102; // [rsp+318h] [rbp+158h]
  int *v103; // [rsp+320h] [rbp+160h]
  __int64 v104; // [rsp+328h] [rbp+168h]
  char *v105; // [rsp+330h] [rbp+170h]
  __int64 v106; // [rsp+338h] [rbp+178h]
  unsigned int *v107; // [rsp+340h] [rbp+180h]
  __int64 v108; // [rsp+348h] [rbp+188h]
  char *v109; // [rsp+350h] [rbp+190h]
  __int64 v110; // [rsp+358h] [rbp+198h]
  int *v111; // [rsp+360h] [rbp+1A0h]
  __int64 v112; // [rsp+368h] [rbp+1A8h]
  __int64 *v113; // [rsp+370h] [rbp+1B0h]
  __int64 v114; // [rsp+378h] [rbp+1B8h]
  char *v115; // [rsp+380h] [rbp+1C0h]
  __int64 v116; // [rsp+388h] [rbp+1C8h]
  PSRWLOCK *v117; // [rsp+390h] [rbp+1D0h]
  __int64 v118; // [rsp+398h] [rbp+1D8h]
  PSRWLOCK *p_SRWLock; // [rsp+3A0h] [rbp+1E0h]
  __int64 v120; // [rsp+3A8h] [rbp+1E8h]
  _BYTE *v121; // [rsp+3B0h] [rbp+1F0h]
  __int64 v122; // [rsp+3B8h] [rbp+1F8h]
  wil::details::in1diag3 *retaddr; // [rsp+408h] [rbp+248h]

  pv[0] = 0;
  v11 = -1;
  pv[1] = (LPVOID)-1LL;
  pv[2] = (LPVOID)-1LL;
  ApplicationViewTraceLoggingHelpers::GetTelemetryIdForView(a2, (struct IApplicationView *)pv, a3);
  pszPath = 0;
  v63 = -1;
  v64 = -1;
  (*(void (__fastcall **)(ApplicationViewTraceLoggingHelpers *, LPCWSTR *))(*(_QWORD *)a2 + 136LL))(a2, &pszPath);
  v41 = 0;
  v12 = (*((__int64 (__fastcall **)(unsigned __int16 **, int *))*a3 + 3))(a3, &v41);
  if ( v12 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1D0,
      (unsigned int)"pcshell\\twinui\\snapcomponent\\lib\\SnapComponentTelemetry.h",
      (const char *)(unsigned int)v12,
      UserDataCount);
  v78 = 0;
  v13 = (*((__int64 (__fastcall **)(unsigned __int16 **, __int128 *))*a3 + 11))(a3, &v78);
  if ( v13 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1D3,
      (unsigned int)"pcshell\\twinui\\snapcomponent\\lib\\SnapComponentTelemetry.h",
      (const char *)(unsigned int)v13,
      UserDataCount);
  v77 = 0;
  v14 = (*(__int64 (__fastcall **)(ApplicationViewTraceLoggingHelpers *, __int128 *))(*(_QWORD *)a2 + 128LL))(a2, &v77);
  if ( v14 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1D6,
      (unsigned int)"pcshell\\twinui\\snapcomponent\\lib\\SnapComponentTelemetry.h",
      (const char *)(unsigned int)v14,
      UserDataCount);
  v40 = 0;
  v55 = 0;
  if ( (*(int (__fastcall **)(ApplicationViewTraceLoggingHelpers *, GUID *, __int64 *))(*(_QWORD *)a2 + 104LL))(
         a2,
         &GUID_3fc0257d_21c2_4ad3_8fb0_fd481cd204e2,
         &v55) >= 0 )
    (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v55 + 32LL))(v55, &v40);
  v15 = *(_QWORD *)(a1 + 272);
  v16 = *(_DWORD *)(v15 + 72);
  v17 = (WCHAR *)pv[0];
  if ( v16 < 0 && (v18 = v15 + 80, v16 == *(_DWORD *)(v18 + 8)) )
  {
    v19 = *(RTL_SRWLOCK **)(a1 + 280);
    if ( v18 )
    {
      if ( v19 )
      {
        v20 = v19 + 33;
        AcquireSRWLockExclusive(v20);
        SRWLock = 0;
        **(_DWORD **)(a1 + 272) = 2;
        if ( v20 )
          ReleaseSRWLockExclusive(v20);
      }
      else
      {
        v53 = 0;
        **(_DWORD **)(a1 + 272) = 2;
      }
      v21 = (_DWORD *)*((_QWORD *)WindowManagementLogging::Instance() + 1);
      if ( *v21 > 5u )
      {
        v37 = a7;
        v60 = HIDWORD(v77);
        v56 = DWORD2(v77);
        v57 = DWORD1(v77);
        v58 = v77;
        v59 = v40;
        v38 = a6;
        v42 = a5;
        v39[0] = a4;
        v47 = HIDWORD(v78);
        CurrentThreadId = DWORD2(v78);
        v49 = DWORD1(v78);
        v50 = v78;
        LODWORD(v51) = v41;
        v23 = pszPath;
        FileNameW = 0;
        if ( pszPath )
        {
          if ( PathIsFileSpecW(pszPath) )
            FileNameW = (LPWSTR)v23;
          else
            FileNameW = PathFindFileNameW(v23);
        }
        v65 = FileNameW;
        v25 = &pvData;
        if ( v17 )
          v25 = v17;
        v66 = v25;
        v67 = *(_QWORD *)(v18 + 48);
        HIDWORD(v51) = *(_DWORD *)(v18 + 68);
        v43 = *(_DWORD *)(v18 + 16);
        v68 = *(_QWORD *)(v18 + 120);
        v69 = *(_QWORD *)(v18 + 112);
        v44 = *(_DWORD *)(v18 + 104);
        v70 = *(_QWORD *)(v18 + 96);
        v71 = *(_QWORD *)(v18 + 88);
        v45 = *(_DWORD *)(v18 + 80);
        v75 = *(_QWORD *)(v18 + 72);
        LODWORD(v46) = *(_DWORD *)(v18 + 32);
        v72 = *(_QWORD *)(v18 + 24);
        HIDWORD(v46) = *(_DWORD *)v18;
        v73 = *(_QWORD *)(v18 + 128);
        LODWORD(v53) = *(_DWORD *)(v18 + 64);
        v74 = *(_QWORD *)(v18 + 56);
        LODWORD(SRWLock) = *(_DWORD *)(v18 + 8);
        *(_QWORD *)&v61.Id = 0x1000000;
        v54 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(
          (_DWORD)v21,
          (unsigned int)&dword_180818C8C,
          *(_QWORD *)(a1 + 272) + 8,
          v22,
          (__int64)&v54,
          (__int64)&v61,
          (__int64)&SRWLock,
          (__int64)&v74,
          (__int64)&v53,
          (__int64)&v73,
          (__int64)&v46 + 4,
          (__int64)&v72,
          (__int64)&v46,
          (__int64)&v75,
          (__int64)&v45,
          (__int64)&v71,
          (__int64)&v70,
          (__int64)&v44,
          (__int64)&v69,
          (__int64)&v68,
          (__int64)&v43,
          (__int64)&v51 + 4,
          (__int64)&v67,
          (__int64)&v66,
          (__int64)&v65,
          (__int64)&v51,
          (__int64)&v50,
          (__int64)&v49,
          (__int64)&CurrentThreadId,
          (__int64)&v47,
          (__int64)v39,
          (__int64)&v42,
          (__int64)&v38,
          (__int64)&v59,
          (__int64)&v58,
          (__int64)&v57,
          (__int64)&v56,
          (__int64)&v60,
          (__int64)&v37);
      }
      goto LABEL_46;
    }
  }
  else
  {
    v19 = *(RTL_SRWLOCK **)(a1 + 280);
  }
  if ( v19 )
  {
    v26 = v19 + 33;
    AcquireSRWLockExclusive(v26);
    v54 = 0;
    **(_DWORD **)(a1 + 272) = 2;
    if ( v26 )
      ReleaseSRWLockExclusive(v26);
  }
  else
  {
    *(_QWORD *)&v61.Id = 0;
    **(_DWORD **)(a1 + 272) = 2;
  }
  v27 = *((_QWORD *)WindowManagementLogging::Instance() + 1);
  if ( *(_DWORD *)v27 > 5u )
  {
    v39[0] = a7;
    LODWORD(SRWLock) = HIDWORD(v77);
    LODWORD(v53) = DWORD2(v77);
    v46 = v77;
    v45 = v40;
    v38 = a6;
    v44 = a5;
    v37 = a4;
    v43 = HIDWORD(v78);
    v51 = *(_QWORD *)((char *)&v78 + 4);
    v50 = v78;
    v49 = v41;
    v28 = pszPath;
    v29 = 0;
    if ( pszPath )
    {
      if ( PathIsFileSpecW(pszPath) )
        v29 = (LPWSTR)v28;
      else
        v29 = PathFindFileNameW(v28);
    }
    v30 = &pvData;
    if ( v17 )
      v30 = v17;
    CurrentThreadId = GetCurrentThreadId();
    v31 = *(_QWORD *)(a1 + 272);
    v47 = *(_DWORD *)(v31 + 72);
    v54 = 0;
    v121 = v39;
    v122 = 1;
    p_SRWLock = &SRWLock;
    v120 = 4;
    v117 = &v53;
    v118 = 4;
    v115 = (char *)&v46 + 4;
    v116 = 4;
    v113 = &v46;
    v114 = 4;
    v111 = &v45;
    v112 = 4;
    v109 = &v38;
    v110 = 1;
    v107 = &v44;
    v108 = 4;
    v105 = &v37;
    v106 = 1;
    v103 = &v43;
    v104 = 4;
    v101 = (char *)&v51 + 4;
    v102 = 4;
    v99 = &v51;
    v100 = 4;
    v97 = &v50;
    v98 = 4;
    v95 = &v49;
    v96 = 4;
    if ( v29 )
    {
      v32 = -1;
      do
        ++v32;
      while ( v29[v32] );
      v33 = 2 * v32 + 2;
    }
    else
    {
      v29 = (LPWSTR)&pvData;
      v33 = 2;
    }
    v92 = v29;
    v93 = v33;
    v94 = 0;
    if ( v30 )
    {
      do
        ++v11;
      while ( v30[v11] );
      v34 = 2 * v11 + 2;
    }
    else
    {
      v30 = &pvData;
      v34 = 2;
    }
    v89 = v30;
    v90 = v34;
    v91 = 0;
    p_CurrentThreadId = &CurrentThreadId;
    v88 = 4;
    v85 = &v47;
    v86 = 4;
    v83 = &v54;
    v84 = 8;
    *(_QWORD *)&v61.Id = 0x2050B000000LL;
    v61.Keyword = 0;
    UserData.Ptr = *(_QWORD *)(v27 + 8);
    UserData.Size = *(unsigned __int16 *)UserData.Ptr;
    UserData.Reserved = 2;
    v80 = word_180818EC2;
    v81 = 293;
    v82 = 1;
    v42 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(*(_QWORD *)(v27 + 32), &v61, (LPCGUID)(v31 + 8), 0, 0x15u, &UserData);
  }
LABEL_46:
  if ( *(_DWORD *)(a1 + 312) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)(a1 + 288));
  v35 = v55;
  if ( v55 )
  {
    v55 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
  }
  if ( pszPath )
  {
    CoTaskMemFree((LPVOID)pszPath);
    pszPath = 0;
  }
  v63 = 0;
  v64 = 0;
  if ( v17 )
    CoTaskMemFree(v17);
}

```

## disassembly

```asm
0x18024b650  mov     [rsp-8+arg_18], rbx
0x18024b655  push    rbp
0x18024b656  push    rsi
0x18024b657  push    rdi
0x18024b658  push    r12
0x18024b65a  push    r13
0x18024b65c  push    r14
0x18024b65e  push    r15
0x18024b660  lea     rbp, [rsp-210h]
0x18024b668  sub     rsp, 3D0h
0x18024b66f  mov     rax, cs:__security_cookie
0x18024b676  xor     rax, rsp
0x18024b679  mov     [rbp+240h+var_40], rax
0x18024b680  movzx   r12d, r9b
0x18024b684  mov     r14, r8
0x18024b687  mov     rbx, rdx
0x18024b68a  mov     rsi, rcx
0x18024b68d  xor     r13d, r13d
0x18024b690  mov     [rbp+240h+pv], r13
0x18024b694  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18024b69b  mov     [rbp+240h+var_1C0], rdi
0x18024b6a2  mov     [rbp+240h+var_1B8], rdi
0x18024b6a9  lea     rdx, [rbp+240h+pv]; struct IApplicationView *
0x18024b6ad  mov     rcx, rbx; this
0x18024b6b0  call    ?GetTelemetryIdForView@ApplicationViewTraceLoggingHelpers@@YAJPEAUIApplicationView@@PEAPEAG@Z; ApplicationViewTraceLoggingHelpers::GetTelemetryIdForView(IApplicationView *,ushort * *)
0x18024b6b5  mov     [rbp+240h+pszPath], r13
0x18024b6b9  mov     [rbp+240h+var_230], rdi
0x18024b6bd  mov     [rbp+240h+var_228], rdi
0x18024b6c1  mov     rax, [rbx]
0x18024b6c4  lea     rdx, [rbp+240h+pszPath]
0x18024b6c8  mov     rcx, rbx
0x18024b6cb  mov     rax, [rax+88h]
0x18024b6d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024b6d7  mov     [rbp+240h+var_2B8], r13d
0x18024b6db  mov     rax, [r14]
0x18024b6de  lea     rdx, [rbp+240h+var_2B8]
0x18024b6e2  mov     rcx, r14
0x18024b6e5  mov     rax, [rax+18h]
0x18024b6e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024b6ee  mov     rcx, [rbp+248h]; this
0x18024b6f5  test    eax, eax
0x18024b6f7  jns     short loc_18024B70D
0x18024b6f9  mov     r9d, eax; char *
0x18024b6fc  lea     r8, aPcshellTwinuiS_3; "pcshell\\twinui\\snapcomponent\\lib\\Sn"...
0x18024b703  mov     edx, 1D0h; void *
0x18024b708  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18024b70d  xorps   xmm0, xmm0
0x18024b710  movdqu  [rbp+240h+var_1A0], xmm0
0x18024b718  mov     rax, [r14]
0x18024b71b  lea     rdx, [rbp+240h+var_1A0]
0x18024b722  mov     rcx, r14
0x18024b725  mov     rax, [rax+58h]
0x18024b729  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024b72e  mov     rcx, [rbp+248h]; this
0x18024b735  test    eax, eax
0x18024b737  jns     short loc_18024B74D
0x18024b739  mov     r9d, eax; char *
0x18024b73c  lea     r8, aPcshellTwinuiS_3; "pcshell\\twinui\\snapcomponent\\lib\\Sn"...
0x18024b743  mov     edx, 1D3h; void *
0x18024b748  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18024b74d  xorps   xmm0, xmm0
0x18024b750  movdqu  [rbp+240h+var_1B0], xmm0
0x18024b758  mov     rax, [rbx]
0x18024b75b  lea     rdx, [rbp+240h+var_1B0]
0x18024b762  mov     rcx, rbx
0x18024b765  mov     rax, [rax+80h]
0x18024b76c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024b771  mov     rcx, [rbp+248h]; this
0x18024b778  test    eax, eax
0x18024b77a  jns     short loc_18024B790
0x18024b77c  mov     r9d, eax; char *
0x18024b77f  lea     r8, aPcshellTwinuiS_3; "pcshell\\twinui\\snapcomponent\\lib\\Sn"...
0x18024b786  mov     edx, 1D6h; void *
0x18024b78b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18024b790  mov     [rbp+240h+var_2BC], r13d
0x18024b794  mov     [rbp+240h+var_268], r13
0x18024b798  mov     rax, [rbx]
0x18024b79b  lea     r8, [rbp+240h+var_268]
0x18024b79f  lea     rdx, _GUID_3fc0257d_21c2_4ad3_8fb0_fd481cd204e2
0x18024b7a6  mov     rcx, rbx
0x18024b7a9  mov     rax, [rax+68h]
0x18024b7ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024b7b2  test    eax, eax
0x18024b7b4  js      short loc_18024B7CA
0x18024b7b6  mov     rcx, [rbp+240h+var_268]
0x18024b7ba  mov     rax, [rcx]
0x18024b7bd  lea     rdx, [rbp+240h+var_2BC]
0x18024b7c1  mov     rax, [rax+20h]
0x18024b7c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024b7ca  mov     r14, [rsi+110h]
0x18024b7d1  mov     eax, [r14+48h]
0x18024b7d5  mov     r15, [rbp+240h+pv]
0x18024b7d9  test    eax, eax
0x18024b7db  jns     loc_18024BB5D
0x18024b7e1  add     r14, 50h ; 'P'
0x18024b7e5  cmp     eax, [r14+8]
0x18024b7e9  jnz     loc_18024BB5D
0x18024b7ef  mov     rbx, [rsi+118h]
0x18024b7f6  test    r14, r14
0x18024b7f9  jz      loc_18024BB64
0x18024b7ff  test    rbx, rbx
0x18024b802  jz      short loc_18024B847
0x18024b804  add     rbx, 108h
0x18024b80b  mov     rcx, rbx; SRWLock
0x18024b80e  call    cs:__imp_AcquireSRWLockExclusive
0x18024b814  lea     rax, [rbp+240h+SRWLock]
0x18024b818  mov     [rax], r13
0x18024b81b  mov     rcx, [rbp+240h+SRWLock]; SRWLock
0x18024b81f  test    rcx, rcx
0x18024b822  jz      short loc_18024B82A
0x18024b824  call    cs:__imp_ReleaseSRWLockExclusive
0x18024b82a  mov     rax, [rsi+110h]
0x18024b831  mov     dword ptr [rax], 2
0x18024b837  test    rbx, rbx
0x18024b83a  jz      short loc_18024B86A
0x18024b83c  mov     rcx, rbx; SRWLock
0x18024b83f  call    cs:__imp_ReleaseSRWLockExclusive
0x18024b845  jmp     short loc_18024B86A
0x18024b847  lea     rax, [rbp+240h+var_278]
0x18024b84b  mov     [rax], r13
0x18024b84e  mov     rcx, [rbp+240h+var_278]; SRWLock
0x18024b852  test    rcx, rcx
0x18024b855  jz      short loc_18024B85D
0x18024b857  call    cs:__imp_ReleaseSRWLockExclusive
0x18024b85d  mov     rax, [rsi+110h]
0x18024b864  mov     dword ptr [rax], 2
0x18024b86a  call    ?Instance@WindowManagementLogging@@KAPEAV1@XZ; WindowManagementLogging::Instance(void)
0x18024b86f  mov     rdi, [rax+8]
0x18024b873  mov     eax, [rdi]
0x18024b875  cmp     eax, 5
0x18024b878  jbe     loc_18024BF2B
0x18024b87e  movzx   eax, [rbp+240h+arg_30]
0x18024b885  mov     [rbp+240h+var_2C0], al
0x18024b888  mov     eax, dword ptr [rbp+240h+var_1B0+0Ch]
0x18024b88e  mov     [rbp+240h+var_250], eax
0x18024b891  mov     eax, dword ptr [rbp+240h+var_1B0+8]
0x18024b897  mov     [rbp+240h+var_260], eax
0x18024b89a  mov     eax, dword ptr [rbp+240h+var_1B0+4]
0x18024b8a0  mov     [rbp+240h+var_25C], eax
0x18024b8a3  mov     eax, dword ptr [rbp+240h+var_1B0]
0x18024b8a9  mov     [rbp+240h+var_258], eax
0x18024b8ac  mov     eax, [rbp+240h+var_2BC]
0x18024b8af  mov     [rbp+240h+var_254], eax
0x18024b8b2  movzx   eax, [rbp+240h+arg_28]
0x18024b8b9  mov     [rbp+240h+var_2BF], al
0x18024b8bc  mov     eax, [rbp+240h+arg_20]
0x18024b8c2  mov     [rbp+240h+var_2B4], eax
0x18024b8c5  mov     [rbp+240h+var_2BE], r12b
0x18024b8c9  mov     eax, dword ptr [rbp+240h+var_1A0+0Ch]
0x18024b8cf  mov     [rbp+240h+var_29C], eax
0x18024b8d2  mov     eax, dword ptr [rbp+240h+var_1A0+8]
0x18024b8d8  mov     [rbp+240h+var_298], eax
0x18024b8db  mov     eax, dword ptr [rbp+240h+var_1A0+4]
0x18024b8e1  mov     [rbp+240h+var_294], eax
0x18024b8e4  mov     eax, dword ptr [rbp+240h+var_1A0]
0x18024b8ea  mov     [rbp+240h+var_290], eax
0x18024b8ed  mov     eax, [rbp+240h+var_2B8]
0x18024b8f0  mov     dword ptr [rbp+240h+var_28C], eax
0x18024b8f3  mov     rbx, [rbp+240h+pszPath]
0x18024b8f7  mov     rax, r13
0x18024b8fa  test    rbx, rbx
0x18024b8fd  jz      short loc_18024B91A
0x18024b8ff  mov     rcx, rbx; pszPath
0x18024b902  call    cs:__imp_PathIsFileSpecW
0x18024b908  test    eax, eax
0x18024b90a  jnz     short loc_18024B917
0x18024b90c  mov     rcx, rbx; pszPath
0x18024b90f  call    cs:__imp_PathFindFileNameW
0x18024b915  jmp     short loc_18024B91A
0x18024b917  mov     rax, rbx
0x18024b91a  mov     [rbp+240h+var_220], rax
0x18024b91e  lea     r12, pvData
0x18024b925  test    r15, r15
0x18024b928  cmovnz  r12, r15
0x18024b92c  mov     [rbp+240h+var_218], r12
0x18024b930  mov     rax, [r14+30h]
0x18024b934  mov     [rbp+240h+var_210], rax
0x18024b938  mov     eax, [r14+44h]
0x18024b93c  mov     dword ptr [rbp+240h+var_28C+4], eax
0x18024b93f  mov     eax, [r14+10h]
0x18024b943  mov     [rbp+240h+var_2B0], eax
0x18024b946  mov     rax, [r14+78h]
0x18024b94a  mov     [rbp+240h+var_208], rax
0x18024b94e  mov     rax, [r14+70h]
0x18024b952  mov     [rbp+240h+var_200], rax
0x18024b956  mov     eax, [r14+68h]
0x18024b95a  mov     [rbp+240h+var_2AC], eax
0x18024b95d  mov     rax, [r14+60h]
0x18024b961  mov     [rbp+240h+var_1F8], rax
0x18024b965  mov     rax, [r14+58h]
0x18024b969  mov     [rbp+240h+var_1F0], rax
0x18024b96d  mov     eax, [r14+50h]
0x18024b971  mov     [rbp+240h+var_2A8], eax
0x18024b974  mov     rax, [r14+48h]
0x18024b978  mov     [rbp+240h+var_1D0], rax
0x18024b97c  mov     eax, [r14+20h]
0x18024b980  mov     dword ptr [rbp+240h+var_2A4], eax
0x18024b983  mov     rax, [r14+18h]
0x18024b987  mov     [rbp+240h+var_1E8], rax
0x18024b98b  mov     eax, [r14]
0x18024b98e  mov     dword ptr [rbp+240h+var_2A4+4], eax
0x18024b991  mov     rax, [r14+80h]
0x18024b998  mov     [rbp+240h+var_1E0], rax
0x18024b99c  mov     eax, [r14+40h]
0x18024b9a0  mov     dword ptr [rbp+240h+var_278], eax
0x18024b9a3  mov     rax, [r14+38h]
0x18024b9a7  mov     [rbp+240h+var_1D8], rax
0x18024b9ab  mov     eax, [r14+8]
0x18024b9af  mov     dword ptr [rbp+240h+SRWLock], eax
0x18024b9b2  mov     [rbp+240h+var_248], 1000000h
0x18024b9ba  mov     [rbp+240h+var_270], r13
0x18024b9be  mov     r8, [rsi+110h]
0x18024b9c5  add     r8, 8
0x18024b9c9  lea     rax, [rbp+240h+var_2C0]
0x18024b9cd  mov     [rsp+400h+var_2D0], rax
0x18024b9d5  lea     rax, [rbp+240h+var_250]
0x18024b9d9  mov     [rsp+400h+var_2D8], rax
0x18024b9e1  lea     rax, [rbp+240h+var_260]
0x18024b9e5  mov     [rsp+400h+var_2E0], rax
0x18024b9ed  lea     rax, [rbp+240h+var_25C]
0x18024b9f1  mov     [rsp+400h+var_2E8], rax
0x18024b9f9  lea     rax, [rbp+240h+var_258]
0x18024b9fd  mov     [rsp+400h+var_2F0], rax
0x18024ba05  lea     rax, [rbp+240h+var_254]
0x18024ba09  mov     [rsp+400h+var_2F8], rax
0x18024ba11  lea     rax, [rbp+240h+var_2BF]
0x18024ba15  mov     [rsp+400h+var_300], rax
0x18024ba1d  lea     rax, [rbp+240h+var_2B4]
0x18024ba21  mov     [rsp+400h+var_308], rax
0x18024ba29  lea     rax, [rbp+240h+var_2BE]
0x18024ba2d  mov     [rsp+400h+var_310], rax
0x18024ba35  lea     rax, [rbp+240h+var_29C]
0x18024ba39  mov     [rsp+400h+var_318], rax
0x18024ba41  lea     rax, [rbp+240h+var_298]
0x18024ba45  mov     [rsp+400h+var_320], rax
0x18024ba4d  lea     rax, [rbp+240h+var_294]
0x18024ba51  mov     [rsp+400h+var_328], rax
0x18024ba59  lea     rax, [rbp+240h+var_290]
0x18024ba5d  mov     [rsp+400h+var_330], rax
0x18024ba65  lea     rax, [rbp+240h+var_28C]
0x18024ba69  mov     [rsp+400h+var_338], rax
0x18024ba71  lea     rax, [rbp+240h+var_220]
0x18024ba75  mov     [rsp+400h+var_340], rax
0x18024ba7d  lea     rax, [rbp+240h+var_218]
0x18024ba81  mov     [rsp+400h+var_348], rax
0x18024ba89  lea     rax, [rbp+240h+var_210]
0x18024ba8d  mov     [rsp+400h+var_350], rax
0x18024ba95  lea     rax, [rbp+240h+var_28C+4]
0x18024ba99  mov     [rsp+400h+var_358], rax
0x18024baa1  lea     rax, [rbp+240h+var_2B0]
0x18024baa5  mov     [rsp+400h+var_360], rax
0x18024baad  lea     rax, [rbp+240h+var_208]
0x18024bab1  mov     [rsp+400h+var_368], rax
0x18024bab9  lea     rax, [rbp+240h+var_200]
0x18024babd  mov     [rsp+400h+var_370], rax
0x18024bac5  lea     rax, [rbp+240h+var_2AC]
0x18024bac9  mov     [rsp+400h+var_378], rax
0x18024bad1  lea     rax, [rbp+240h+var_1F8]
0x18024bad5  mov     [rsp+400h+var_380], rax
0x18024badd  lea     rax, [rbp+240h+var_1F0]
0x18024bae1  mov     [rsp+400h+var_388], rax
0x18024bae6  lea     rax, [rbp+240h+var_2A8]
0x18024baea  mov     [rsp+400h+var_390], rax
0x18024baef  lea     rax, [rbp+240h+var_1D0]
0x18024baf3  mov     [rsp+400h+var_398], rax
0x18024baf8  lea     rax, [rbp+240h+var_2A4]
0x18024bafc  mov     [rsp+400h+var_3A0], rax
0x18024bb01  lea     rax, [rbp+240h+var_1E8]
0x18024bb05  mov     [rsp+400h+var_3A8], rax
0x18024bb0a  lea     rax, [rbp+240h+var_2A4+4]
0x18024bb0e  mov     [rsp+400h+var_3B0], rax
0x18024bb13  lea     rax, [rbp+240h+var_1E0]
0x18024bb17  mov     [rsp+400h+var_3B8], rax
0x18024bb1c  lea     rax, [rbp+240h+var_278]
0x18024bb20  mov     [rsp+400h+var_3C0], rax
0x18024bb25  lea     rax, [rbp+240h+var_1D8]
0x18024bb29  mov     [rsp+400h+var_3C8], rax
0x18024bb2e  lea     rax, [rbp+240h+SRWLock]
0x18024bb32  mov     [rsp+400h+var_3D0], rax
0x18024bb37  lea     rax, [rbp+240h+var_248]
0x18024bb3b  mov     [rsp+400h+UserData], rax
0x18024bb40  lea     rax, [rbp+240h+var_270]
0x18024bb44  mov     qword ptr [rsp+400h+UserDataCount], rax
0x18024bb49  lea     rdx, dword_180818C8C
0x18024bb50  mov     rcx, rdi
0x18024bb53  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@U4@U4@U2@U2@U2@U2@U2@U?$_tlgWrapperByVal@$00@@U2@U5@U2@U2@U2@U2@U2@U5@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@454564564456644444AEBU?$_tlgWrapperByVal@$00@@47444447@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &)
0x18024bb58  jmp     loc_18024BF2B
0x18024bb5d  mov     rbx, [rsi+118h]
0x18024bb64  test    rbx, rbx
0x18024bb67  jz      short loc_18024BBAC
0x18024bb69  add     rbx, 108h
0x18024bb70  mov     rcx, rbx; SRWLock
0x18024bb73  call    cs:__imp_AcquireSRWLockExclusive
0x18024bb79  lea     rax, [rbp+240h+var_270]
0x18024bb7d  mov     [rax], r13
0x18024bb80  mov     rcx, [rbp+240h+var_270]; SRWLock
0x18024bb84  test    rcx, rcx
0x18024bb87  jz      short loc_18024BB8F
0x18024bb89  call    cs:__imp_ReleaseSRWLockExclusive
0x18024bb8f  mov     rax, [rsi+110h]
  ... truncated ...
```
