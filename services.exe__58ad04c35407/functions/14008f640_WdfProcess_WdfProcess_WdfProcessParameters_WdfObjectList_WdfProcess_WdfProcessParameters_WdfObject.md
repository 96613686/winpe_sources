# WdfProcess::WdfProcess(WdfProcessParameters *,WdfObjectList<WdfProcess,WdfProcessParameters> *,WdfObject *)

- ea: `0x14008f640`
- end: `0x140090bab`
- name: `??0WdfProcess@@QEAA@PEAVWdfProcessParameters@@PEAV?$WdfObjectList@VWdfProcess@@VWdfProcessParameters@@@@PEAVWdfObject@@@Z`
- size: `5483`
- prototype: `WdfProcess *__fastcall(WdfProcess *this, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `27`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x14001a4ec`

## callees

- `0x140003e54`
- `0x140004c58`
- `0x14001b180`
- `0x14001b2f4`
- `0x14001b3d0`
- `0x14001b928`
- `0x14001f99c`
- `0x14001f9c4`
- `0x140022c34`
- `0x140027708`
- `0x14002d610`
- `0x14002db94`
- `0x14002dd70`
- `0x140043f94`
- `0x140044300`
- `0x1400575b0`
- `0x14008f4c0`
- `0x14008f5e8`
- `0x14008f640`
- `0x140090d30`
- `0x140090db0`
- `0x140091804`
- `0x140091a50`
- `0x140091b24`
- `0x140091f24`
- `0x140092060`
- `0x140094020`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140090919`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140090919`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14009044b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140090731`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14009077b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140090873`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14009044b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140090731`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14009077b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140090873`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x140090727`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x140090727`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x140090a25`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x140090a25`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x140090863`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x140090863`
- `RPCRT4!UuidToStringW` at `0x14008fc44`
- `RPCRT4!UuidToStringW` at `0x14008fce2`
- `RPCRT4!UuidToStringW` at `0x14008fc44`
- `RPCRT4!UuidToStringW` at `0x14008fce2`
- `RPCRT4!RpcStringFreeW` at `0x14008fd71`
- `RPCRT4!RpcStringFreeW` at `0x140090b09`
- `RPCRT4!RpcStringFreeW` at `0x140090b19`
- `RPCRT4!RpcStringFreeW` at `0x14008fd71`
- `RPCRT4!RpcStringFreeW` at `0x140090b09`
- `RPCRT4!RpcStringFreeW` at `0x140090b19`
- `RPCRT4!UuidCreate` at `0x14008fa7e`
- `RPCRT4!UuidCreate` at `0x14008fcc2`
- `RPCRT4!UuidCreate` at `0x14008fa7e`
- `RPCRT4!UuidCreate` at `0x14008fcc2`
- `profapi!__imp_LoadProfileBasic` at `0x140090611`
- `profapi!__imp_LoadProfileBasic` at `0x140090611`

## string_xrefs

- `0x14008fa4f`: `m_HostImagePath not valid`
- `0x140090342`: `-ImagePath:`
- `0x140090530`: `LocalService`

## pseudocode

```c
WdfProcess *__fastcall WdfProcess::WdfProcess(WdfProcess *this, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v8; // rdx
  void *v9; // r15
  WdfDriverManager *v10; // rax
  __int64 v11; // r12
  __int64 *v12; // r14
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rax
  int v16; // ebx
  bool v17; // zf
  LPWSTR v18; // r12
  const wchar_t *v19; // rcx
  __int64 v20; // r15
  unsigned __int64 v21; // r8
  size_t v22; // rsi
  unsigned __int128 v23; // rax
  wchar_t *v24; // rax
  PRPC_ASYNC_STATE v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // rdx
  __int64 v30; // rcx
  const UUID *v31; // rsi
  unsigned int v32; // eax
  PRPC_ASYNC_STATE v33; // rcx
  __int64 v34; // rdx
  const wchar_t *v35; // rcx
  HRESULT v36; // eax
  unsigned __int64 v37; // r8
  size_t v38; // rsi
  unsigned __int128 v39; // rax
  wchar_t *v40; // rax
  HRESULT v41; // esi
  __int64 v42; // rax
  __int64 v43; // r13
  unsigned int v44; // esi
  unsigned int v45; // r12d
  unsigned int v46; // eax
  unsigned __int64 v47; // r8
  __int64 v48; // rcx
  __int64 v49; // rax
  unsigned __int64 v50; // r14
  unsigned __int128 v51; // rax
  wchar_t *v52; // rcx
  HRESULT v53; // eax
  PRPC_ASYNC_STATE v54; // rcx
  __int64 v55; // rdx
  __int64 v56; // rsi
  HRESULT HostReportBaseFileName; // eax
  PRPC_ASYNC_STATE v58; // rcx
  __int64 v59; // rdx
  __int64 v60; // r12
  __int64 v61; // rax
  __int64 v62; // rdx
  __int64 v63; // r13
  __int64 v64; // rcx
  __int64 v65; // rax
  int *v66; // r14
  size_t v67; // r10
  int *v68; // rdx
  __int64 v69; // rax
  __int64 v70; // rcx
  unsigned __int64 v71; // rsi
  unsigned __int64 v72; // r8
  __int64 v73; // rcx
  __int64 v74; // rax
  __int64 v75; // rdx
  __int64 v76; // rcx
  unsigned __int128 v77; // rax
  wchar_t *v78; // rax
  HRESULT v79; // r14d
  __int64 v80; // rdx
  __int64 v81; // r9
  __int64 v82; // rax
  int v83; // edx
  int v84; // ecx
  unsigned __int16 *v85; // rsi
  DWORD v86; // eax
  void **v87; // r12
  unsigned int v88; // eax
  unsigned int v89; // edx
  void *v90; // r9
  unsigned int v91; // eax
  void *v92; // rbx
  void *v93; // rcx
  int ProfileBasic; // eax
  unsigned int v95; // r15d
  struct _WDF_COMPANION_PROCESS_SETTINGS *v96; // r8
  unsigned int *v97; // r12
  DWORD LastError; // eax
  DWORD v99; // eax
  __int64 v100; // rcx
  DrvMgrLpcNotification *v101; // r14
  void **v102; // rsi
  DWORD v103; // eax
  DWORD v104; // esi
  unsigned int v105; // r14d
  __int64 v106; // rdx
  __int64 v107; // rcx
  char *v108; // rsi
  PRPC_ASYNC_STATE v109; // rcx
  __int64 v110; // r9
  __int64 *v111; // rdx
  char *v112; // r8
  __int64 v113; // rcx
  __int64 v114; // rsi
  int v115; // ecx
  __int64 v116; // rcx
  LPWSTR lpCommandLine; // [rsp+A0h] [rbp-80h]
  void *v119; // [rsp+A8h] [rbp-78h]
  DWORD ExitCode; // [rsp+B0h] [rbp-70h] BYREF
  RPC_WSTR String; // [rsp+B8h] [rbp-68h] BYREF
  RPC_WSTR StringUuid; // [rsp+C0h] [rbp-60h] BYREF
  size_t pcchLength; // [rsp+C8h] [rbp-58h] BYREF
  void *v124; // [rsp+D0h] [rbp-50h] BYREF
  __int64 v125; // [rsp+D8h] [rbp-48h]
  void *v126; // [rsp+E0h] [rbp-40h] BYREF
  __int64 v127; // [rsp+E8h] [rbp-38h] BYREF
  size_t v128; // [rsp+F0h] [rbp-30h] BYREF
  __int64 v129; // [rsp+F8h] [rbp-28h]
  DrvMgrLpcNotification *v130; // [rsp+100h] [rbp-20h]
  _WORD v131[2]; // [rsp+108h] [rbp-18h] BYREF
  int v132; // [rsp+10Ch] [rbp-14h]
  void **v133; // [rsp+110h] [rbp-10h]
  __int16 v134; // [rsp+118h] [rbp-8h]
  int v135; // [rsp+11Ch] [rbp-4h]
  __int64 *v136; // [rsp+120h] [rbp+0h]
  __int64 v137; // [rsp+128h] [rbp+8h]
  __int64 v138; // [rsp+130h] [rbp+10h]
  struct _SECURITY_ATTRIBUTES ProcessAttributes; // [rsp+138h] [rbp+18h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+150h] [rbp+30h] BYREF
  UUID Uuid; // [rsp+1C0h] [rbp+A0h] BYREF
  wchar_t v142[12]; // [rsp+1D0h] [rbp+B0h] BYREF
  wchar_t pszDest[12]; // [rsp+1E8h] [rbp+C8h] BYREF
  wchar_t v144[8]; // [rsp+200h] [rbp+E0h] BYREF
  _BYTE v145[26]; // [rsp+210h] [rbp+F0h] BYREF

  v138 = a3;
  v137 = a2;
  WdfObject::WdfObject(this, *(_QWORD *)(a2 + 8), a4);
  *(_QWORD *)this = &WdfProcess::`vftable';
  *((_QWORD *)this + 35) = 0;
  *((_DWORD *)this + 72) = 0;
  StringUuid = 0;
  Uuid = 0;
  memset(&StartupInfo, 0, sizeof(StartupInfo));
  String = 0;
  v128 = 0;
  v127 = 0;
  memset(pszDest, 0, 22);
  v9 = 0;
  memset(v142, 0, 22);
  v133 = &v126;
  memset(v145, 0, sizeof(v145));
  v136 = &v127;
  v126 = 0;
  *(_OWORD *)v144 = 0;
  v131[0] = 0;
  v132 = 0x1FFFFF;
  v134 = 0;
  v135 = 1024;
  *(_QWORD *)&ProcessAttributes.nLength = 24;
  *(_OWORD *)&ProcessAttributes.lpSecurityDescriptor = 0;
  v119 = 0;
  v124 = 0;
  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
    && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 8) != 0
    && *((int *)&WPP_GLOBAL_Control->u.NotificationRoutine + 5) < 0 )
  {
    WPP_SF_qqq(WPP_GLOBAL_Control->u.APC.hThread, v8, WPP_9e86a345ea7c3fd289cca579774c5c03_Traceguids, a2, a3, a4);
  }
  *((_QWORD *)this + 32) = 0;
  *((_QWORD *)this + 31) = 0;
  *((_BYTE *)this + 264) = 0;
  *(_OWORD *)((char *)this + 120) = 0;
  String = 0;
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 20) = 0;
  *((_DWORD *)this + 44) = 0;
  *((_QWORD *)this + 11) = *(_QWORD *)(a2 + 16);
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 21) = 0;
  *((_QWORD *)this + 29) = 0;
  *((_DWORD *)this + 45) = *(_DWORD *)(a2 + 32);
  *((_QWORD *)this + 23) = 0;
  *((_DWORD *)this + 48) = *(_DWORD *)(a2 + 4);
  v10 = DrvMgrExt;
  *((_BYTE *)this + 240) = 0;
  *((_QWORD *)this + 18) = 0;
  *(_OWORD *)((char *)this + 300) = 0;
  lpCommandLine = 0;
  *(_OWORD *)((char *)this + 312) = 0;
  v11 = *(_QWORD *)(a2 + 40);
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 34) = 0;
  v12 = (__int64 *)*((_QWORD *)v10 + 26);
  v129 = v11;
  WudfVerify(0, v8, L"minkernel\\wdf\\framework\\umdf\\drivermanager\\process.cpp", 94, "WdfProcess::WdfProcess");
  v130 = (DrvMgrLpcNotification *)*((_QWORD *)DrvMgrExt + 17);
  WudfVerify(v14, v13, L"minkernel\\wdf\\framework\\umdf\\drivermanager\\process.cpp", 96, "WdfProcess::WdfProcess");
  *(_QWORD *)((char *)this + 292) = 0;
  v15 = *(_QWORD *)(a2 + 64);
  *(_OWORD *)((char *)this + 200) = 0;
  v125 = v15;
  *(_OWORD *)((char *)this + 216) = 0;
  v16 = *((_DWORD *)this + 4);
  if ( v16 < 0 )
  {
    v18 = 0;
    goto LABEL_261;
  }
  v17 = *((_DWORD *)this + 48) == 2;
  ExitCode = 32;
  if ( v17 )
  {
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].RuntimeInfo) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control[1].RuntimeInfo) >= 4u )
    {
      WPP_SF_(WPP_GLOBAL_Control[1].UserInfo, 11, WPP_9e86a345ea7c3fd289cca579774c5c03_Traceguids);
    }
    ExitCode = 128;
  }
  if ( !a3 )
  {
    v16 = -1073741811;
    v18 = 0;
    goto LABEL_261;
  }
  v19 = *(const wchar_t **)(a2 + 48);
  v20 = -1;
  if ( v19 )
  {
    pcchLength = 0;
    if ( StringCchLengthW(v19, 0x7FFFFFFFu, &pcchLength) < 0 )
    {
      v16 = -1073741811;
      goto LABEL_17;
    }
    v22 = pcchLength + 1;
    v23 = (pcchLength + 1) * (unsigned __int128)2uLL;
    if ( !is_mul_ok(pcchLength + 1, 2u) )
      *(_QWORD *)&v23 = -1;
    v24 = (wchar_t *)operator new(v23, DWORD2(v23), v21);
    *((_QWORD *)this + 32) = v24;
    if ( !v24 )
    {
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
        || (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 8) == 0
        || *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) < 2u )
      {
        goto LABEL_27;
      }
      v26 = 12;
      goto LABEL_26;
    }
    StringCchCopyW(v24, v22, *(STRSAFE_LPCWSTR *)(a2 + 48));
    WudfVerify(v28, v27, L"minkernel\\wdf\\framework\\umdf\\drivermanager\\process.cpp", 153, "WdfProcess::WdfProcess");
  }
  if ( !(unsigned int)WdfProcess::LoadRegistrySettings(this) || !*((_QWORD *)this + 14) )
  {
    v16 = -1073741811;
    v18 = 0;
LABEL_18:
    v9 = v119;
    goto LABEL_261;
  }
  WudfVerify(v30, v29, L"minkernel\\wdf\\framework\\umdf\\drivermanager\\process.cpp", 164, "WdfProcess::WdfProcess");
  v31 = (const UUID *)((char *)this + 96);
  v32 = UuidCreate((UUID *)this + 6);
  if ( v32 && v32 != 1824 )
  {
    v33 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
      || (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 8) == 0
      || *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) < 2u )
    {
      goto LABEL_40;
    }
    v34 = 13;
LABEL_39:
    WPP_SF_d(v33->u.APC.hThread, v34, WPP_9e86a345ea7c3fd289cca579774c5c03_Traceguids, v32);
LABEL_40:
    v16 = -1073741670;
    v18 = 0;
    goto LABEL_29;
  }
  v35 = *(const wchar_t **)(v11 + 280);
  if ( v35 )
  {
    v36 = StringCchLengthW(v35, 0x7FFFFFFEu, &v128);
    if ( v36 >= 0 )
    {
      v38 = v128 + 1;
      v39 = (v128 + 1) * (unsigned __int128)2uLL;
      if ( !is_mul_ok(v128 + 1, 2u) )
        *(_QWORD *)&v39 = -1;
      v40 = (wchar_t *)operator new(v39, DWORD2(v39), v37);
      *((_QWORD *)this + 31) = v40;
      if ( v40 )
      {
        v41 = StringCchCopyW(v40, v38, *(STRSAFE_LPCWSTR *)(v11 + 280));
        if ( v41 < 0 )
        {
          operator delete(*((void **)this + 31));
          *((_QWORD *)this + 31) = 0;
          if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 8) != 0
            && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 3u )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control->u.APC.hThread,
              16,
              WPP_9e86a345ea7c3fd289cca579774c5c03_Traceguids,
              (unsigned int)v41);
          }
        }
      }
      else if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
             && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 8) != 0
             && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 3u )
      {
        WPP_SF_(WPP_GLOBAL_Control->u.APC.hThread, 15, WPP_9e86a345ea7c3fd289cca579774c5c03_Traceguids);
      }
      v31 = (const UUID *)((char *)this + 96);
    }
    else if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
           && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 8) != 0
           && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 3u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->u.APC.hThread,
        14,
        WPP_9e86a345ea7c3fd289cca579774c5c03_Traceguids,
        (unsigned int)v36);
    }
  }
  if ( *(_DWORD *)(v11 + 328) || *(_DWORD *)(v11 + 332) )
  {
    *(_OWORD *)((char *)this + 300) = *(_OWORD *)(v11 + 312);
    *(_OWORD *)((char *)this + 312) = *(_OWORD *)(v11 + 324);
  }
  v32 = UuidToStringW(v31, &StringUuid);
  if ( v32 )
  {
    v33 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
      || (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 8) == 0
      || *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) < 2u )
    {
      goto LABEL_40;
    }
    v34 = 17;
    goto LABEL_39;
  }
  v42 = *v12;
  pcchLength = 0;
  v43 = (*(__int64 (__fastcall **)(__int64 *, __int64))(v42 + 24))(v12, 4);
  v44 = 0;
  v45 = 4 - (v125 != 0);
  while ( 1 )
  {
    if ( v44 >= v45 )
    {
      v56 = v125;
      if ( v125 )
      {
        HostReportBaseFileName = StringCchPrintfW(pszDest, 0xBu, L"%lu", *((unsigned int *)this + 46));
        if ( HostReportBaseFileName < 0 )
        {
          v58 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            || (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 8) == 0
            || *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) < 2u )
          {
            goto LABEL_91;
          }
          v59 = 22;
          goto LABEL_107;
        }
        HostReportBaseFileName = StringCchPrintfW(v142, 0xBu, L"%lu", *((unsigned int *)this + 47));
        if ( HostReportBaseFileName < 0 )
        {
          v58 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            || (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 8) == 0
            || *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) < 2u )
          {
            goto LABEL_91;
          }
          v59 = 23;
          goto LABEL_107;
        }
        v60 = v129;
      }
      else
      {
        v60 = v129;
        v61 = *(_QWORD *)(v129 + 256);
        *(_QWORD *)((char *)this + 292) = v61;
        HostReportBaseFileName = StringCchPrintfW(
                                   v144,
                                   0x15u,
                                   L"%I64u",
                                   v61 & 0xF | (16LL * (*((_DWORD *)this + 74) & 0xF)));
        if ( HostReportBaseFileName < 0 )
        {
          v58 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            || (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 8) == 0
            || *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) < 2u )
          {
            goto LABEL_91;
          }
          v59 = 24;
          goto LABEL_107;
        }
      }
      v62 = -1;
      do
        ++v62;
      while ( StringUuid[v62] );
      v63 = v137;
      v64 = -1;
      do
        ++v64;
      while ( *(_WORD *)(*(_QWORD *)(v137 + 8) + 2 * v64) );
      v65 = -1;
      do
        ++v65;
      while ( *(_WORD *)(*((_QWORD *)this + 14) + 2 * v65) );
      v66 = &dword_14009C804;
      v67 = v62 + v64 + v65 + pcchLength + 91;
      if ( v56 )
      {
        v72 = -1;
        do
          ++v72;
        while ( pszDest[v72] );
        v75 = -1;
        do
          ++v75;
        while ( v142[v75] );
        v76 = -1;
        do
          ++v76;
        while ( *(_WORD *)(*(_QWORD *)(*(_QWORD *)(v137 + 64) + 16LL) + 2 * v76) );
        v71 = v76 + v67 + v75 + v72 + 61;
      }
      else
      {
        v68 = &dword_14009C804;
        if ( *((_QWORD *)this + 32) )
          v68 = (int *)*((_QWORD *)this + 32);
        v69 = -1;
        do
          ++v69;
        while ( v144[v69] );
        v70 = -1;
        do
          ++v70;
        while ( *((_WORD *)v68 + v70) );
        v71 = v70 + 58 + v67 + v69;
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WdfUmdfDma>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WdfUmdfDma>::GetImpl'::`2'::impl) )
        {
          v73 = *(_QWORD *)(v60 + 344);
          if ( v73 )
          {
            v74 = -1;
            do
              ++v74;
            while ( *(_WORD *)(v73 + 2 * v74) );
            v71 += v74 + 1;
          }
        }
      }
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
        && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 8) != 0
        && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 5u )
      {
        WPP_SF_q(WPP_GLOBAL_Control->u.APC.hThread, 25, WPP_9e86a345ea7c3fd289cca579774c5c03_Traceguids, v71);
      }
      v77 = v71 * (unsigned __int128)2uLL;
      if ( !is_mul_ok(v71, 2u) )
        *(_QWORD *)&v77 = -1;
      v78 = (wchar_t *)operator new(v77, DWORD2(v77), v72);
      lpCommandLine = v78;
      if ( !v78 )
      {
        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 8) != 0
          && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 3u )
        {
          WPP_SF_(WPP_GLOBAL_Control->u.APC.hThread, 26, WPP_9e86a345ea7c3fd289cca579774c5c03_Traceguids);
        }
        v16 = -1073741801;
        goto LABEL_28;
      }
      if ( v125 )
      {
        v79 = StringCchPrintfW(
                v78,
                v71,
                L"\"%s\" %s%s %s%s %s%s %s%s %s%s %s%s %s%s %s%s",
                *((_QWORD *)this + 14),
                L"-HostGUID:",
                *(_QWORD *)(v63 + 8),
                L"-IoEventPortName:",
                *((_QWORD *)this + 25),
                L"-SystemEventPortName:",
                *((_QWORD *)this + 27),
                L"-IoCancelEventPortName:",
                *((_QWORD *)this + 26),
                L"-ImagePath:",
                *(_QWORD *)(*(_QWORD *)(v63 + 64) + 16LL),
                L"-TimeoutOnStartInSec:",
                pszDest,
                L"-TimeoutOnModuleLoadInSec:",
                v142,
                L"-LifetimeId:",
                StringUuid);
      }
      else
      {
        if ( *((_QWORD *)this + 32) )
          v66 = (int *)*((_QWORD *)this + 32);
        v79 = StringCchPrintfW(
                v78,
                v71,
                L"\"%s\" %s%s %s%s %s%s %s%s %s%s %s%s %s%s %s%s",
                *((_QWORD *)this + 14),
                L"-HostGUID:",
                *(_QWORD *)(v63 + 8),
                L"-IoEventPortName:",
                *((_QWORD *)this + 25),
                L"-SystemEventPortName:",
                *((_QWORD *)this + 27),
                L"-IoCancelEventPortName:",
                *((_QWORD *)this + 26),
                L"-NonStateChangingEventPortName:",
                *((_QWORD *)this + 28),
                L"-LifetimeId:",
                StringUuid,
                L"-DeviceGroupId:",
                v66,
                L"-HostArg:",
                v144);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WdfUmdfDma>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WdfUmdfDma>::GetImpl'::`2'::impl) )
        {
          if ( v79 < 0 )
          {
            v18 = lpCommandLine;
            goto LABEL_174;
          }
          v81 = *(_QWORD *)(v60 + 344);
          v18 = lpCommandLine;
          if ( !v81 )
          {
            do
LABEL_168:
              ++v20;
            while ( v18[v20] );
            WudfVerify(
              0,
              v80,
              L"minkernel\\wdf\\framework\\umdf\\drivermanager\\process.cpp",
              495,
              "WdfProcess::WdfProcess");
            v84 = (int)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
              || (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 8) == 0 )
            {
              v85 = lpCommandLine;
            }
            else
            {
              v85 = lpCommandLine;
              if ( *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 5u )
                WPP_SF_SS(
                  WPP_GLOBAL_Control->u.APC.hThread,
                  28,
                  (unsigned int)WPP_9e86a345ea7c3fd289cca579774c5c03_Traceguids,
                  *((_QWORD *)this + 14),
                  (__int64)lpCommandLine);
            }
            if ( (Microsoft_Windows_DriverFrameworks_UserModeEnableBits & 1) != 0 )
              McTemplateU0jzz_EventWriteTransfer(
                v84,
                v83,
                (_DWORD)this + 96,
                *(_QWORD *)(v63 + 8),
                *(_QWORD *)(v63 + 24));
            v127 = (*(__int64 (__fastcall **)(struct IUMDFPlatformSecurity *, __int64))(*(_QWORD *)g_PlatformSecurity
                                                                                      + 40LL))(
                     g_PlatformSecurity,
                     26);
            if ( !v127 )
            {
              v25 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                || (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 8) == 0
                || *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) < 2u )
              {
                goto LABEL_27;
              }
              v26 = 29;
LABEL_26:
              WPP_SF_(v25->u.APC.hThread, v26, WPP_9e86a345ea7c3fd289cca579774c5c03_Traceguids);
              goto LABEL_27;
            }
            v87 = (void **)((char *)this + 152);
            v88 = (*(__int64 (__fastcall **)(struct IUMDFPlatformSecurity *, const wchar_t *, const wchar_t *, char *, void **))(*(_QWORD *)g_PlatformSecurity + 72LL))(
                    g_PlatformSecurity,
                    L"LocalService",
                    L"NT AUTHORITY",
                    (char *)this + 152,
                    &v126);
            if ( v88 )
            {
              if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 8) != 0
                && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 2u )
              {
                WPP_SF_d(WPP_GLOBAL_Control->u.APC.hThread, 30, WPP_9e86a345ea7c3fd289cca579774c5c03_Traceguids, v88);
              }
LABEL_91:
              v16 = -1073741595;
              goto LABEL_28;
            }
            if ( v126 )
            {
              v91 = DmCreateAndSetHostSD((struct DM_ACE_DATA *const)v131, v89, v126, v90, &v124);
              if ( v91 )
              {
                if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                  && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 8) != 0
                  && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 2u )
                {
                  WPP_SF_d(WPP_GLOBAL_Control->u.APC.hThread, 31, WPP_9e86a345ea7c3fd289cca579774c5c03_Traceguids, v91);
                }
                v9 = v124;
                v18 = lpCommandLine;
                goto LABEL_261;
              }
              v92 = v124;
            }
            else
            {
              v92 = 0;
            }
            v93 = *v87;
            v119 = v92;
            ProcessAttributes.lpSecurityDescriptor = v92;
            ProfileBasic = LoadProfileBasic(v93, (char *)this + 144);
            if ( ProfileBasic < 0 )
            {
              if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 8) != 0
                && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 2u )
              {
                WPP_SF_d(
                  WPP_GLOBAL_Control->u.APC.hThread,
                  32,
                  WPP_9e86a345ea7c3fd289cca579774c5c03_Traceguids,
                  (unsigned int)ProfileBasic);
              }
              *((_QWORD *)this + 18) = 0;
            }
            v95 = -1;
            if ( v125 )
            {
              v96 = *(struct _WDF_COMPANION_PROCESS_SETTINGS **)(v63 + 64);
              if ( *(_DWORD *)v96 == 2 )
              {
                v16 = WdfProcess::LaunchSecureCompanionProcess(this, v85, v96, v92, *v87, ExitCode);
                if ( v16 < 0 )
                {
                  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                    && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 8) != 0
                    && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 2u )
                  {
                    WPP_SF_d(
                      WPP_GLOBAL_Control->u.APC.hThread,
                      33,
                      WPP_9e86a345ea7c3fd289cca579774c5c03_Traceguids,
                      (unsigned int)v16);
                  }
                  goto LABEL_28;
                }
                v97 = (unsigned int *)((char *)this + 136);
LABEL_236:
                v104 = 10;
                v105 = 0;
                if ( *(_DWORD *)(v63 + 56) || (v95 = 1000 * *((_DWORD *)this + 45)) != 0 )
                {
                  while ( 1 )
                  {
                    v16 = DrvMgrLpcNotification::Connect(
                            v130,
                            (void *)*v97,
                            *((const unsigned __int16 **)this + 27),
                            (struct IUMDFLPCCommPortInterface **)this + 29);
                    if ( v16 >= 0 )
                      break;
                    if ( !WaitForSingleObject(*((HANDLE *)this + 15), v104) )
                    {
                      ExitCode = 31;
                      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                        && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 8) != 0
                        && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 2u )
                      {
                        WPP_SF_(WPP_GLOBAL_Control->u.APC.hThread, 37, WPP_9e86a345ea7c3fd289cca579774c5c03_Traceguids);
                      }
                      GetExitCodeProcess(*((HANDLE *)this + 15), &ExitCode);
                      if ( (Microsoft_Windows_DriverFrameworks_UserModeEnableBits & 4) != 0 )
                      {
                        v108 = (char *)this + 96;
                        McTemplateU0jq_EventWriteTransfer(
                          v113,
                          EVENT_DM_CREATE_HOST_FAILURE,
                          (char *)this + 96,
                          ExitCode);
                      }
                      else
                      {
LABEL_243:
                        v108 = (char *)this + 96;
                      }
                      v109 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                        && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 8) != 0
                        && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 2u )
                      {
                        WPP_SF_Sd(
                          WPP_GLOBAL_Control->u.APC.hThread,
                          38,
                          (unsigned int)WPP_9e86a345ea7c3fd289cca579774c5c03_Traceguids,
                          *((_QWORD *)this + 27),
                          v16);
                      }
                      if ( (Microsoft_Windows_DriverFrameworks_UserModeEnableBits & 4) != 0 )
                      {
                        v110 = 31;
                        v111 = EVENT_DM_CREATE_HOST_FAILURE;
                        v112 = v108;
                        goto LABEL_250;
                      }
                      goto LABEL_17;
                    }
                    WudfVerify(
                      v107,
                      v106,
                      L"minkernel\\wdf\\framework\\umdf\\drivermanager\\process.cpp",
                      759,
                      "WdfProcess::WdfProcess");
                    v105 += v104;
                    v104 *= 2;
                    if ( v104 > 0x1388 )
                      v104 = 5000;
                    if ( v105 >= v95 )
                      goto LABEL_243;
                  }
                }
                v114 = v138;
                *((_QWORD *)this + 21) = v138;
                (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v114 + 32) + 24LL))(*(_QWORD *)(v114 + 32));
                *((_QWORD *)this + 6) = *(_QWORD *)(v114 + 96);
                v115 = *(_DWORD *)(v114 + 88);
                *(_DWORD *)(v114 + 88) = v115 + 1;
                *((_DWORD *)this + 14) = v115;
                v116 = *(_QWORD *)(v114 + 32);
                *(_QWORD *)(v114 + 96) = this;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v116 + 40LL))(v116);
                *((_DWORD *)this + 44) = 1;
                if ( (Microsoft_Windows_DriverFrameworks_UserModeEnableBits & 1) != 0 )
                {
                  v110 = 0;
                  v112 = (char *)this + 96;
                  v111 = EVENT_DM_CREATE_HOST_OK;
LABEL_250:
                  McTemplateU0jq_EventWriteTransfer(v109, v111, v112, v110);
                }
LABEL_17:
                v18 = lpCommandLine;
                goto LABEL_18;
              }
            }
            if ( !CreateProcessAsUserW(
                    *v87,
                    *((LPCWSTR *)this + 14),
                    v85,
                    &ProcessAttributes,
                    0,
                    0,
                    ExitCode | 0x14,
                    0,
                    0,
                    &StartupInfo,
                    (LPPROCESS_INFORMATION)this + 5) )
            {
              LastError = GetLastError();
              if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 8) != 0
                && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 2u )
              {
                WPP_SF_d(
                  WPP_GLOBAL_Control->u.APC.hThread,
                  34,
                  WPP_9e86a345ea7c3fd289cca579774c5c03_Traceguids,
                  LastError);
              }
              if ( (Microsoft_Windows_DriverFrameworks_UserModeEnableBits & 4) != 0 )
              {
                v99 = GetLastError();
                McTemplateU0jq_EventWriteTransfer(v100, EVENT_DM_CREATE_HOST_FAILURE, (char *)this + 96, v99);
              }
              goto LABEL_91;
            }
            v97 = (unsigned int *)((char *)this + 136);
            HostReportBaseFileName = WdfProcess::GenerateHostReportBaseFileName(this, *((_DWORD *)this + 34));
            if ( HostReportBaseFileName >= 0 )
            {
              v101 = v130;
              v102 = (void **)((char *)this + 120);
              v16 = DrvMgrLpcNotification::SetAccessControl(
                      v130,
                      *((void **)this + 15),
                      *((unsigned __int16 **)this + 25));
              if ( v16 < 0 )
                goto LABEL_17;
              v16 = DrvMgrLpcNotification::SetAccessControl(v101, *v102, *((unsigned __int16 **)this + 26));
              if ( v16 < 0 )
                goto LABEL_17;
              v16 = DrvMgrLpcNotification::SetAccessControl(v101, *v102, *((unsigned __int16 **)this + 27));
              if ( v16 < 0 )
                goto LABEL_17;
              v16 = DrvMgrLpcNotification::SetAccessControl(v101, *v102, *((unsigned __int16 **)this + 28));
              if ( v16 < 0 )
                goto LABEL_17;
              if ( ResumeThread(*((HANDLE *)this + 16)) == -1 )
              {
                v16 = -1073741823;
                v103 = GetLastError();
                if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                  && (BYTE4(WPP_GLOBAL_Control[1].RuntimeInfo) & 2) != 0
                  && BYTE1(WPP_GLOBAL_Control[1].RuntimeInfo) >= 2u )
                {
                  WPP_SF_d(WPP_GLOBAL_Control[1].UserInfo, 36, WPP_9e86a345ea7c3fd289cca579774c5c03_Traceguids, v103);
                }
                goto LABEL_28;
              }
              goto LABEL_236;
            }
            v58 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
              || (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 8) == 0
              || *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) < 2u )
            {
              goto LABEL_91;
            }
            v59 = 35;
LABEL_107:
            WPP_SF_d(
              v58->u.APC.hThread,
              v59,
              WPP_9e86a345ea7c3fd289cca579774c5c03_Traceguids,
              (unsigned int)HostReportBaseFileName);
            goto LABEL_91;
          }
          v82 = -1;
          do
            ++v82;
          while ( lpCommandLine[v82] );
          v79 = StringCchPrintfW(&lpCommandLine[v82], v71 - v82, L" %s");
LABEL_167:
          if ( v79 >= 0 )
            goto LABEL_168;
LABEL_174:
          v86 = GetLastError();
          if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 8) != 0
            && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 2u )
          {
            WPP_SF_d(WPP_GLOBAL_Control->u.APC.hThread, 27, WPP_9e86a345ea7c3fd289cca579774c5c03_Traceguids, v86);
          }
          v16 = -1073741595;
          goto LABEL_29;
        }
      }
      v18 = lpCommandLine;
      goto LABEL_167;
    }
    v46 = UuidCreate(&Uuid);
    if ( v46 )
    {
      if ( v46 != 1824 )
        break;
    }
    v46 = UuidToStringW(&Uuid, &String);
    if ( v46 )
    {
      v54 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
        && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 8) != 0
        && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 2u )
      {
        v55 = 19;
        goto LABEL_86;
      }
      goto LABEL_27;
    }
    v48 = -1;
    do
      ++v48;
    while ( String[v48] );
    v49 = -1;
    do
      ++v49;
    while ( *(_WORD *)(v43 + 2 * v49) );
    v50 = v49 + v48 + 14;
    v51 = v50 * (unsigned __int128)2uLL;
    if ( !is_mul_ok(v50, 2u) )
      *(_QWORD *)&v51 = -1;
    v52 = (wchar_t *)operator new(v51, DWORD2(v51), v47);
    *((_QWORD *)this + v44 + 25) = v52;
    if ( !v52 )
    {
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
        && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 8) != 0
        && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 2u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->u.APC.hThread, 20, WPP_9e86a345ea7c3fd289cca579774c5c03_Traceguids, v44);
      }
      v16 = -1073741801;
      goto LABEL_17;
    }
    v53 = StringCchPrintfW(v52, v50, L"%s\\HostProcess-%s", v43, String);
    if ( v53 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
        && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 8) != 0
        && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 2u )
      {
        WPP_SF_Sd(
          WPP_GLOBAL_Control->u.APC.hThread,
          21,
          (unsigned int)WPP_9e86a345ea7c3fd289cca579774c5c03_Traceguids,
          (_DWORD)String,
          v53);
      }
      goto LABEL_91;
    }
    pcchLength = v50 + pcchLength - 1;
    RpcStringFreeW(&String);
    String = 0;
    ++v44;
  }
  v54 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
    && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 8) != 0
    && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 2u )
  {
    v55 = 18;
LABEL_86:
    WPP_SF_d(v54->u.APC.hThread, v55, WPP_9e86a345ea7c3fd289cca579774c5c03_Traceguids, v46);
  }
LABEL_27:
  v16 = -1073741670;
LABEL_28:
  v18 = lpCommandLine;
LABEL_29:
  v9 = v119;
LABEL_261:
  operator delete(v18);
  if ( v127 )
    (*(void (__fastcall **)(struct IUMDFPlatform *))(*(_QWORD *)g_Platform + 96LL))(g_Platform);
  if ( String )
    RpcStringFreeW(&String);
  if ( StringUuid )
    RpcStringFreeW(&StringUuid);
  if ( v9 )
    operator delete(v9);
  (*(void (__fastcall **)(struct IUMDFPlatformSecurity *, _QWORD, void *))(*(_QWORD *)g_PlatformSecurity + 80LL))(
    g_PlatformSecurity,
    0,
    v126);
  WdfCtorStatus::SetCtorStatus((WdfProcess *)((char *)this + 16), v16);
  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
    && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 8) != 0
    && *((int *)&WPP_GLOBAL_Control->u.NotificationRoutine + 5) < 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control->u.APC.hThread, 39, WPP_9e86a345ea7c3fd289cca579774c5c03_Traceguids, v16 >= 0);
  }
  return this;
}

```

## disassembly

```asm
0x14008f640  push    rbp
0x14008f642  push    rbx
0x14008f643  push    rsi
0x14008f644  push    rdi
0x14008f645  push    r12
0x14008f647  push    r13
0x14008f649  push    r14
0x14008f64b  push    r15
0x14008f64d  lea     rbp, [rsp-128h]
0x14008f655  sub     rsp, 248h
0x14008f65c  mov     rax, cs:__security_cookie
0x14008f663  xor     rax, rsp
0x14008f666  mov     [rbp+160h+var_50], rax
0x14008f66d  mov     rsi, r8
0x14008f670  mov     [rbp+160h+var_150], r8
0x14008f674  mov     r13, rdx
0x14008f677  mov     [rbp+160h+var_158], rdx
0x14008f67b  mov     rdx, [rdx+8]
0x14008f67f  mov     r8, r9
0x14008f682  mov     rbx, r9
0x14008f685  mov     rdi, rcx
0x14008f688  call    ??0WdfObject@@QEAA@PEBGPEAV0@EW4RdType@@@Z; WdfObject::WdfObject(ushort const *,WdfObject *,uchar,RdType)
0x14008f68d  xor     r14d, r14d
0x14008f690  lea     rax, ??_7WdfProcess@@6B@; const WdfProcess::`vftable'
0x14008f697  mov     [rdi], rax
0x14008f69a  lea     rcx, [rbp+160h+StartupInfo]; void *
0x14008f69e  xorps   xmm0, xmm0
0x14008f6a1  mov     [rdi+118h], r14
0x14008f6a8  xor     edx, edx; Val
0x14008f6aa  mov     [rdi+120h], r14d
0x14008f6b1  lea     r8d, [r14+68h]; Size
0x14008f6b5  mov     [rbp+160h+StringUuid], r14
0x14008f6b9  movups  xmmword ptr [rbp+160h+Uuid.Data1], xmm0
0x14008f6c0  call    memset
0x14008f6c5  xorps   xmm0, xmm0
0x14008f6c8  mov     [rbp+160h+String], r14
0x14008f6cc  xor     eax, eax
0x14008f6ce  mov     [rbp+160h+var_190], r14
0x14008f6d2  xorps   xmm1, xmm1
0x14008f6d5  mov     [rbp+160h+var_198], r14
0x14008f6d9  movups  xmmword ptr [rbp+160h+pszDest], xmm0
0x14008f6e0  mov     qword ptr [rbp+160h+pszDest+0Eh], rax
0x14008f6e7  mov     r15d, r14d
0x14008f6ea  movups  xmmword ptr [rbp+160h+var_B0], xmm1
0x14008f6f1  mov     qword ptr [rbp+160h+var_B0+0Eh], rax
0x14008f6f8  lea     rax, [rbp+160h+var_1A0]
0x14008f6fc  mov     [rbp+160h+var_170], rax
0x14008f700  lea     rax, [rbp+160h+var_198]
0x14008f704  movups  xmmword ptr [rbp+160h+var_70], xmm0
0x14008f70b  mov     [rbp+160h+var_160], rax
0x14008f70f  mov     [rbp+160h+var_1A0], r14
0x14008f713  movups  xmmword ptr [rbp+160h+var_80], xmm0
0x14008f71a  mov     [rbp+160h+var_178], r14w
0x14008f71f  movups  xmmword ptr [rbp+160h+var_70+0Ah], xmm0
0x14008f726  mov     [rbp+160h+var_174], 1FFFFFh
0x14008f72d  mov     [rbp+160h+var_168], r14w
0x14008f732  mov     [rbp+160h+var_164], 400h
0x14008f739  mov     qword ptr [rbp+160h+ProcessAttributes.nLength], 18h
0x14008f741  movdqu  xmmword ptr [rbp+160h+ProcessAttributes.lpSecurityDescriptor], xmm0
0x14008f746  mov     [rbp+160h+var_1D8], r14
0x14008f74a  mov     [rbp+160h+var_1B0], r14
0x14008f74e  mov     rcx, cs:WPP_GLOBAL_Control
0x14008f755  lea     rax, WPP_GLOBAL_Control
0x14008f75c  cmp     rcx, rax
0x14008f75f  jz      short loc_14008F78A
0x14008f761  test    byte ptr [rcx+44h], 8
0x14008f765  jz      short loc_14008F78A
0x14008f767  cmp     [rcx+44h], r14d
0x14008f76b  jge     short loc_14008F78A
0x14008f76d  mov     rcx, [rcx+38h]
0x14008f771  lea     r8, WPP_9e86a345ea7c3fd289cca579774c5c03_Traceguids
0x14008f778  mov     qword ptr [rsp+280h+bInheritHandles], rbx
0x14008f77d  mov     r9, r13
0x14008f780  mov     [rsp+280h+lpThreadAttributes], rsi
0x14008f785  call    WPP_SF_qqq
0x14008f78a  mov     [rdi+100h], r14
0x14008f791  lea     rbx, aLpcObjectNotVa; "lpc object not valid"
0x14008f798  mov     [rdi+0F8h], r14
0x14008f79f  lea     r8, aMinkernelWdfFr_4; "minkernel\\wdf\\framework\\umdf\\driver"...
0x14008f7a6  mov     [rdi+108h], r14b
0x14008f7ad  xorps   xmm0, xmm0
0x14008f7b0  movups  xmmword ptr [rdi+78h], xmm0
0x14008f7b4  xor     ecx, ecx
0x14008f7b6  mov     [rbp+160h+String], r14
0x14008f7ba  mov     [rdi+88h], rcx
0x14008f7c1  mov     [rdi+0A0h], r14
0x14008f7c8  mov     [rdi+0B0h], r14d
0x14008f7cf  mov     rax, [r13+10h]
0x14008f7d3  lea     r9d, [rcx+5Eh]
0x14008f7d7  mov     [rdi+58h], rax
0x14008f7db  mov     [rdi+70h], r14
0x14008f7df  mov     [rdi+0A8h], r14
0x14008f7e6  mov     [rdi+0E8h], r14
0x14008f7ed  mov     eax, [r13+20h]
0x14008f7f1  mov     [rdi+0B4h], eax
0x14008f7f7  mov     [rdi+0B8h], r14
0x14008f7fe  mov     eax, [r13+4]
0x14008f802  mov     [rdi+0C0h], eax
0x14008f808  mov     rax, cs:?DrvMgrExt@@3PEAVWdfDriverManager@@EA; WdfDriverManager * DrvMgrExt
0x14008f80f  mov     [rdi+0F0h], r14b
0x14008f816  mov     [rdi+90h], r14
0x14008f81d  movups  xmmword ptr [rdi+12Ch], xmm0
0x14008f824  mov     [rbp+160h+lpCommandLine], r14
0x14008f828  movups  xmmword ptr [rdi+138h], xmm0
0x14008f82f  mov     r12, [r13+28h]
0x14008f833  mov     [rdi+98h], r14
0x14008f83a  mov     [rdi+110h], r14
0x14008f841  mov     r14, [rax+0D0h]
0x14008f848  test    r14, r14
0x14008f84b  mov     [rbp+160h+var_188], r12
0x14008f84f  setnz   al
0x14008f852  mov     byte ptr [rsp+280h+lpStartupInfo], al
0x14008f856  lea     rax, aWdfprocessWdfp_0; "WdfProcess::WdfProcess"
0x14008f85d  mov     [rsp+280h+lpCurrentDirectory], rbx
0x14008f862  mov     [rsp+280h+lpThreadAttributes], rax
0x14008f867  call    ?WudfVerify@@YAXW4WdfComponentType@@PEAUIUMDFPlatform@@PEBGKPEBDW4WdfDriverStopType@@W4WdfErrorClass@@K3_NPEAD@Z; WudfVerify(WdfComponentType,IUMDFPlatform *,ushort const *,ulong,char const *,WdfDriverStopType,WdfErrorClass,ulong,char const *,bool,char *)
0x14008f86c  mov     rax, cs:?DrvMgrExt@@3PEAVWdfDriverManager@@EA; WdfDriverManager * DrvMgrExt
0x14008f873  lea     r8, aMinkernelWdfFr_4; "minkernel\\wdf\\framework\\umdf\\driver"...
0x14008f87a  mov     r9d, 60h ; '`'
0x14008f880  mov     rax, [rax+88h]
0x14008f887  test    rax, rax
0x14008f88a  mov     [rbp+160h+var_180], rax
0x14008f88e  setnz   al
0x14008f891  mov     byte ptr [rsp+280h+lpStartupInfo], al
0x14008f895  lea     rax, aWdfprocessWdfp_0; "WdfProcess::WdfProcess"
0x14008f89c  mov     [rsp+280h+lpCurrentDirectory], rbx
0x14008f8a1  mov     [rsp+280h+lpThreadAttributes], rax
0x14008f8a6  call    ?WudfVerify@@YAXW4WdfComponentType@@PEAUIUMDFPlatform@@PEBGKPEBDW4WdfDriverStopType@@W4WdfErrorClass@@K3_NPEAD@Z; WudfVerify(WdfComponentType,IUMDFPlatform *,ushort const *,ulong,char const *,WdfDriverStopType,WdfErrorClass,ulong,char const *,bool,char *)
0x14008f8ab  xor     eax, eax
0x14008f8ad  xorps   xmm0, xmm0
0x14008f8b0  mov     [rdi+124h], rax
0x14008f8b7  xor     r11d, r11d
0x14008f8ba  mov     rax, [r13+40h]
0x14008f8be  movups  xmmword ptr [rdi+0C8h], xmm0
0x14008f8c5  mov     [rbp+160h+var_1A8], rax
0x14008f8c9  movups  xmmword ptr [rdi+0D8h], xmm0
0x14008f8d0  mov     ebx, [rdi+10h]
0x14008f8d3  test    ebx, ebx
0x14008f8d5  js      loc_140090ACE
0x14008f8db  cmp     dword ptr [rdi+0C0h], 2
0x14008f8e2  mov     [rbp+160h+ExitCode], 20h ; ' '
0x14008f8e9  jnz     short loc_14008F931
0x14008f8eb  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14008f8f2  lea     rax, WPP_GLOBAL_Control
0x14008f8f9  cmp     rcx, rax
0x14008f8fc  jz      short loc_14008F92A
0x14008f8fe  test    byte ptr [rcx+94h], 2
0x14008f905  jz      short loc_14008F92A
0x14008f907  cmp     byte ptr [rcx+91h], 4
0x14008f90e  jb      short loc_14008F92A
0x14008f910  mov     rcx, [rcx+88h]
0x14008f917  lea     edx, [r11+0Bh]
0x14008f91b  lea     r8, WPP_9e86a345ea7c3fd289cca579774c5c03_Traceguids
0x14008f922  call    WPP_SF_
0x14008f927  xor     r11d, r11d
0x14008f92a  mov     [rbp+160h+ExitCode], 80h
0x14008f931  test    rsi, rsi
0x14008f934  jnz     short loc_14008F943
0x14008f936  mov     ebx, 0C000000Dh
0x14008f93b  mov     r12, r15
0x14008f93e  jmp     loc_140090AD1
0x14008f943  mov     rcx, [r13+30h]; psz
0x14008f947  or      r15, 0FFFFFFFFFFFFFFFFh
0x14008f94b  test    rcx, rcx
0x14008f94e  jz      loc_14008FA2B
0x14008f954  lea     r8, [rbp+160h+pcchLength]; pcchLength
0x14008f958  mov     [rbp+160h+pcchLength], r11
0x14008f95c  mov     edx, 7FFFFFFFh; cchMax
0x14008f961  call    StringCchLengthW
0x14008f966  test    eax, eax
0x14008f968  jns     short loc_14008F97C
0x14008f96a  mov     ebx, 0C000000Dh
0x14008f96f  mov     r12, [rbp+160h+lpCommandLine]
0x14008f973  mov     r15, [rbp+160h+var_1D8]
0x14008f977  jmp     loc_140090AD1
0x14008f97c  mov     rsi, [rbp+160h+pcchLength]
0x14008f980  mov     eax, 2
0x14008f985  inc     rsi
0x14008f988  mul     rsi
0x14008f98b  cmovb   rax, r15
0x14008f98f  mov     rcx, rax; Size
0x14008f992  call    ??2@YAPEAX_KK0@Z; operator new(unsigned __int64,ulong,unsigned __int64)
0x14008f997  mov     [rdi+100h], rax
0x14008f99e  test    rax, rax
0x14008f9a1  jnz     short loc_14008F9E7
0x14008f9a3  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14008f9aa  lea     rsi, WPP_GLOBAL_Control
0x14008f9b1  cmp     rcx, rsi
0x14008f9b4  jz      short loc_14008F9D5
0x14008f9b6  test    byte ptr [rcx+44h], 8
0x14008f9ba  jz      short loc_14008F9D5
0x14008f9bc  cmp     byte ptr [rcx+41h], 2
0x14008f9c0  jb      short loc_14008F9D5
0x14008f9c2  lea     edx, [rax+0Ch]
0x14008f9c5  mov     rcx, [rcx+38h]
0x14008f9c9  lea     r8, WPP_9e86a345ea7c3fd289cca579774c5c03_Traceguids
0x14008f9d0  call    WPP_SF_
0x14008f9d5  mov     ebx, 0C000009Ah
0x14008f9da  mov     r12, [rbp+160h+lpCommandLine]
0x14008f9de  mov     r15, [rbp+160h+var_1D8]
0x14008f9e2  jmp     loc_140090AD8
0x14008f9e7  mov     r8, [r13+30h]; pszSrc
0x14008f9eb  mov     rdx, rsi; cchDest
0x14008f9ee  mov     rcx, rax; pszDest
0x14008f9f1  call    StringCchCopyW
0x14008f9f6  shr     eax, 1Fh
0x14008f9f9  lea     rsi, aWdfprocessWdfp_0; "WdfProcess::WdfProcess"
0x14008fa00  xor     al, 1
0x14008fa02  lea     r8, aMinkernelWdfFr_4; "minkernel\\wdf\\framework\\umdf\\driver"...
0x14008fa09  mov     byte ptr [rsp+280h+lpStartupInfo], al
0x14008fa0d  mov     r9d, 99h
0x14008fa13  lea     rax, aUnexpectedFail; "Unexpected failure"
0x14008fa1a  mov     [rsp+280h+lpCurrentDirectory], rax
0x14008fa1f  mov     [rsp+280h+lpThreadAttributes], rsi
0x14008fa24  call    ?WudfVerify@@YAXW4WdfComponentType@@PEAUIUMDFPlatform@@PEBGKPEBDW4WdfDriverStopType@@W4WdfErrorClass@@K3_NPEAD@Z; WudfVerify(WdfComponentType,IUMDFPlatform *,ushort const *,ulong,char const *,WdfDriverStopType,WdfErrorClass,ulong,char const *,bool,char *)
0x14008fa29  jmp     short loc_14008FA32
0x14008fa2b  lea     rsi, aWdfprocessWdfp_0; "WdfProcess::WdfProcess"
0x14008fa32  mov     rcx, rdi; this
0x14008fa35  call    ?LoadRegistrySettings@WdfProcess@@AEAAHXZ; WdfProcess::LoadRegistrySettings(void)
0x14008fa3a  xor     r13d, r13d
0x14008fa3d  test    eax, eax
0x14008fa3f  jz      loc_140090AC1
0x14008fa45  cmp     [rdi+70h], r13
0x14008fa49  jz      loc_140090AC1
0x14008fa4f  lea     rax, aMHostimagepath; "m_HostImagePath not valid"
0x14008fa56  mov     byte ptr [rsp+280h+lpStartupInfo], 1
0x14008fa5b  mov     [rsp+280h+lpCurrentDirectory], rax
0x14008fa60  lea     r8, aMinkernelWdfFr_4; "minkernel\\wdf\\framework\\umdf\\driver"...
0x14008fa67  mov     r9d, 0A4h
0x14008fa6d  mov     [rsp+280h+lpThreadAttributes], rsi
0x14008fa72  call    ?WudfVerify@@YAXW4WdfComponentType@@PEAUIUMDFPlatform@@PEBGKPEBDW4WdfDriverStopType@@W4WdfErrorClass@@K3_NPEAD@Z; WudfVerify(WdfComponentType,IUMDFPlatform *,ushort const *,ulong,char const *,WdfDriverStopType,WdfErrorClass,ulong,char const *,bool,char *)
0x14008fa77  lea     rsi, [rdi+60h]
0x14008fa7b  mov     rcx, rsi; Uuid
0x14008fa7e  call    cs:__imp_UuidCreate
0x14008fa84  test    eax, eax
0x14008fa86  jz      short loc_14008FAD2
0x14008fa88  cmp     eax, 720h
0x14008fa8d  jz      short loc_14008FAD2
0x14008fa8f  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14008fa96  lea     rsi, WPP_GLOBAL_Control
0x14008fa9d  cmp     rcx, rsi
0x14008faa0  jz      short loc_14008FAC5
0x14008faa2  test    byte ptr [rcx+44h], 8
0x14008faa6  jz      short loc_14008FAC5
0x14008faa8  cmp     byte ptr [rcx+41h], 2
0x14008faac  jb      short loc_14008FAC5
0x14008faae  lea     edx, [r13+0Dh]
0x14008fab2  mov     rcx, [rcx+38h]
0x14008fab6  lea     r8, WPP_9e86a345ea7c3fd289cca579774c5c03_Traceguids
0x14008fabd  mov     r9d, eax
0x14008fac0  call    WPP_SF_d
0x14008fac5  mov     ebx, 0C000009Ah
0x14008faca  mov     r12, r13
0x14008facd  jmp     loc_14008F9DE
0x14008fad2  mov     rcx, [r12+118h]; psz
0x14008fada  test    rcx, rcx
0x14008fadd  jz      loc_14008FC09
0x14008fae3  lea     r8, [rbp+160h+var_190]; pcchLength
0x14008fae7  mov     edx, 7FFFFFFEh; cchMax
0x14008faec  call    StringCchLengthW
0x14008faf1  test    eax, eax
0x14008faf3  jns     short loc_14008FB3D
0x14008faf5  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14008fafc  lea     r8, WPP_GLOBAL_Control
0x14008fb03  cmp     rcx, r8
0x14008fb06  jz      loc_14008FC09
0x14008fb0c  test    byte ptr [rcx+44h], 8
0x14008fb10  jz      loc_14008FC09
0x14008fb16  cmp     byte ptr [rcx+41h], 3
0x14008fb1a  jb      loc_14008FC09
0x14008fb20  mov     rcx, [rcx+38h]
0x14008fb24  lea     r8, WPP_9e86a345ea7c3fd289cca579774c5c03_Traceguids
0x14008fb2b  mov     edx, 0Eh
0x14008fb30  mov     r9d, eax
0x14008fb33  call    WPP_SF_d
0x14008fb38  jmp     loc_14008FC09
0x14008fb3d  mov     rsi, [rbp+160h+var_190]
0x14008fb41  mov     eax, 2
0x14008fb46  inc     rsi
0x14008fb49  mul     rsi
0x14008fb4c  cmovb   rax, r15
0x14008fb50  mov     rcx, rax; Size
0x14008fb53  call    ??2@YAPEAX_KK0@Z; operator new(unsigned __int64,ulong,unsigned __int64)
0x14008fb58  mov     [rdi+0F8h], rax
0x14008fb5f  test    rax, rax
0x14008fb62  jnz     short loc_14008FBA2
0x14008fb64  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14008fb6b  lea     rax, WPP_GLOBAL_Control
0x14008fb72  cmp     rcx, rax
0x14008fb75  jz      loc_14008FC05
0x14008fb7b  test    byte ptr [rcx+44h], 8
0x14008fb7f  jz      loc_14008FC05
0x14008fb85  cmp     byte ptr [rcx+41h], 3
0x14008fb89  jb      short loc_14008FC05
0x14008fb8b  mov     rcx, [rcx+38h]
0x14008fb8f  lea     r8, WPP_9e86a345ea7c3fd289cca579774c5c03_Traceguids
0x14008fb96  mov     edx, 0Fh
0x14008fb9b  call    WPP_SF_
0x14008fba0  jmp     short loc_14008FC05
0x14008fba2  mov     r8, [r12+118h]; pszSrc
  ... truncated ...
```
