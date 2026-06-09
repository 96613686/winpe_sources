# ScCreateUserServicesForUser(unsigned __int64,ulong)

- ea: `0x140029908`
- end: `0x14002a361`
- name: `?ScCreateUserServicesForUser@@YAH_KK@Z`
- size: `2649`
- prototype: `__int64 __fastcall(unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `49`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140029340`

## callees

- `0x140002890`
- `0x140003e54`
- `0x140004c58`
- `0x140004c98`
- `0x140005464`
- `0x140005824`
- `0x1400070d0`
- `0x140007130`
- `0x140007770`
- `0x140007960`
- `0x14000bebc`
- `0x14000c8f0`
- `0x14000ca18`
- `0x14000cf60`
- `0x14000d1dc`
- `0x140013f60`
- `0x140015314`
- `0x140015900`
- `0x140015a28`
- `0x140016844`
- `0x14001761c`
- `0x1400188fc`
- `0x14001c87c`
- `0x14001e12c`
- `0x14001f7c0`
- `0x14001f9c4`
- `0x140020d84`
- `0x140020f3c`
- `0x140022a24`
- `0x1400236a4`
- `0x1400238c0`
- `0x140023c94`
- `0x140026508`
- `0x1400274f0`
- `0x1400282a4`
- `0x140029908`
- `0x140030a5c`
- `0x140030eb8`
- `0x1400310b8`
- `0x14004057c`
- `0x1400406c8`
- `0x140042c90`
- `0x1400575b0`
- `0x140057844`
- `0x14005b040`
- `0x140066ef4`
- `0x140071b34`
- `0x140071d14`
- `0x140094020`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140029af2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140029af2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002a284`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002a284`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x14002a22b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x14002a22b`
- `ntdll!RtlAcquireResourceExclusive` at `0x140029b02`
- `ntdll!RtlAcquireResourceExclusive` at `0x140029b02`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x140029aec`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x140029aec`
- `ntdll!RtlReleaseResource` at `0x14002a187`
- `ntdll!RtlReleaseResource` at `0x14002a187`
- `ntdll!NtClose` at `0x14002a125`
- `ntdll!NtClose` at `0x14002a140`
- `ntdll!NtClose` at `0x14002a125`
- `ntdll!NtClose` at `0x14002a140`
- `ntdll!RtlNtStatusToDosError` at `0x14002a12d`
- `ntdll!RtlNtStatusToDosError` at `0x14002a148`
- `ntdll!RtlNtStatusToDosError` at `0x14002a12d`
- `ntdll!RtlNtStatusToDosError` at `0x14002a148`
- `ntdll!RtlFreeHeap` at `0x14002a017`
- `ntdll!RtlFreeHeap` at `0x14002a066`
- `ntdll!RtlFreeHeap` at `0x14002a0d5`
- `ntdll!RtlFreeHeap` at `0x14002a0fc`
- `ntdll!RtlFreeHeap` at `0x14002a2a2`
- `ntdll!RtlFreeHeap` at `0x14002a017`
- `ntdll!RtlFreeHeap` at `0x14002a066`
- `ntdll!RtlFreeHeap` at `0x14002a0d5`
- `ntdll!RtlFreeHeap` at `0x14002a0fc`
- `ntdll!RtlFreeHeap` at `0x14002a2a2`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x1400299f9`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x1400299f9`

## pseudocode

```c
__int64 __fastcall ScCreateUserServicesForUser(unsigned __int64 a1, unsigned int a2)
{
  struct _SERVICE_TRIGGER_INFO *v3; // r15
  unsigned int v4; // esi
  int v5; // eax
  __int64 v6; // rdx
  __int64 v7; // r8
  unsigned int TokenInformation; // eax
  unsigned int Win32TemplateServices; // eax
  void **i; // rbx
  char *v11; // r15
  __int64 v12; // r8
  unsigned int ImageFileName; // esi
  __int64 v14; // rdx
  __int64 v15; // r8
  unsigned __int16 *JITReadDisplayName; // rax
  CServiceRecord *v17; // rcx
  unsigned int RealServiceType; // eax
  unsigned __int16 v19; // dx
  unsigned __int16 *v20; // r8
  unsigned int v21; // r9d
  unsigned int v22; // r10d
  __int64 v23; // r8
  unsigned int TriggerInfo; // eax
  PRPC_ASYNC_STATE v25; // rcx
  int v26; // edx
  wchar_t *v27; // r9
  void *v28; // rdx
  unsigned int v29; // eax
  PVOID v30; // rsi
  DWORD v31; // r9d
  DWORD v32; // r8d
  DWORD v33; // eax
  SC_ACTION *v34; // rdx
  int v35; // esi
  PVOID v36; // rsi
  NTSTATUS v37; // eax
  NTSTATUS v38; // eax
  void **j; // rbx
  int v40; // eax
  _QWORD *k; // rbx
  struct CServiceRecord *v42; // rcx
  void *v43; // rbx
  _QWORD *v44; // rdx
  char *v45; // rcx
  __int64 v46; // rax
  _QWORD *v47; // rbx
  _QWORD *v48; // rdx
  __int64 v49; // rax
  SmartPtrRef *v50; // rcx
  unsigned int v52[2]; // [rsp+20h] [rbp-100h]
  CServiceRecord *v53; // [rsp+A0h] [rbp-80h] BYREF
  char v54[8]; // [rsp+A8h] [rbp-78h] BYREF
  HANDLE Handle; // [rsp+B0h] [rbp-70h] BYREF
  int v56; // [rsp+B8h] [rbp-68h]
  int IsDsmaUserContext; // [rsp+BCh] [rbp-64h]
  struct _SERVICE_TRIGGER_INFO *v58; // [rsp+C0h] [rbp-60h] BYREF
  HANDLE v59; // [rsp+C8h] [rbp-58h] BYREF
  PVOID v60; // [rsp+D0h] [rbp-50h] BYREF
  PVOID v61; // [rsp+D8h] [rbp-48h] BYREF
  unsigned int v62; // [rsp+E0h] [rbp-40h]
  PVOID P; // [rsp+E8h] [rbp-38h] BYREF
  PVOID v64; // [rsp+F0h] [rbp-30h] BYREF
  HANDLE hObject; // [rsp+F8h] [rbp-28h] BYREF
  PVOID v66; // [rsp+100h] [rbp-20h] BYREF
  struct _WNF_STATE_NAME v67; // [rsp+108h] [rbp-18h] BYREF
  void *v68[3]; // [rsp+110h] [rbp-10h] BYREF
  _QWORD v69[3]; // [rsp+128h] [rbp+8h] BYREF
  void *v70[3]; // [rsp+140h] [rbp+20h] BYREF
  char v71[8]; // [rsp+158h] [rbp+38h] BYREF
  _SERVICE_FAILURE_ACTIONSW v72; // [rsp+160h] [rbp+40h] BYREF
  _QWORD v73[3]; // [rsp+188h] [rbp+68h] BYREF
  wchar_t Buffer[264]; // [rsp+1A0h] [rbp+80h] BYREF
  wchar_t v75[264]; // [rsp+3B0h] [rbp+290h] BYREF

  v62 = a2;
  v60 = 0;
  v64 = 0;
  v3 = 0;
  Handle = 0;
  v59 = 0;
  v58 = 0;
  v53 = 0;
  v67 = 0;
  hObject = 0;
  v66 = 0;
  v61 = 0;
  P = 0;
  memset(&v72, 0, sizeof(v72));
  utl::list<Microsoft::WRL::ComPtr<CServiceRecord>,utl::allocator<Microsoft::WRL::ComPtr<CServiceRecord>>>::list<Microsoft::WRL::ComPtr<CServiceRecord>,utl::allocator<Microsoft::WRL::ComPtr<CServiceRecord>>>(v70);
  utl::list<Microsoft::WRL::ComPtr<CServiceRecord>,utl::allocator<Microsoft::WRL::ComPtr<CServiceRecord>>>::list<Microsoft::WRL::ComPtr<CServiceRecord>,utl::allocator<Microsoft::WRL::ComPtr<CServiceRecord>>>(v69);
  utl::list<Microsoft::WRL::ComPtr<CServiceRecord>,utl::allocator<Microsoft::WRL::ComPtr<CServiceRecord>>>::list<Microsoft::WRL::ComPtr<CServiceRecord>,utl::allocator<Microsoft::WRL::ComPtr<CServiceRecord>>>(v68);
  if ( !(unsigned __int8)IsUMgrQueryUserContextPresent() )
  {
    v4 = 0;
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      WPP_SF_q(WPP_GLOBAL_Control->StubInfo, 58, WPP_036c406685683e02631f01bfa4d71e7e_Traceguids, a1);
    goto LABEL_117;
  }
  IsDsmaUserContext = ScIsDsmaUserContext(a1);
  v4 = IsDsmaUserContext;
  v5 = UMgrQueryUserToken(a1, &hObject);
  if ( v5 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      WPP_SF_ID(WPP_GLOBAL_Control->StubInfo, v6, v7, a1, v5);
    goto LABEL_117;
  }
  TokenInformation = ScGetTokenInformation(hObject, TokenUser, &v66);
  if ( TokenInformation )
  {
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      WPP_SF_iD(WPP_GLOBAL_Control->StubInfo, 60, WPP_036c406685683e02631f01bfa4d71e7e_Traceguids, a1, TokenInformation);
    goto LABEL_117;
  }
  Win32TemplateServices = ScGetWin32TemplateServices(v70);
  if ( Win32TemplateServices )
  {
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 61, WPP_036c406685683e02631f01bfa4d71e7e_Traceguids, Win32TemplateServices);
    goto LABEL_117;
  }
  v56 = 0;
  RtlAcquireSRWLockExclusive(&g_TriggerRegistrationLock);
  GetCurrentThreadId();
  RtlAcquireResourceExclusive(&ScServiceRecordLock, 1u);
  for ( i = (void **)v70[0]; i != v70; i = (void **)*i )
  {
    v11 = (char *)i[2];
    CScmLock::LockAutoShared(v11 + 312, v71);
    ImageFileName = CServiceRecord::OpenServiceConfigKey((CServiceRecord *)v11, 0x20019u, v12, (HKEY *)&Handle);
    if ( !ImageFileName )
    {
      if ( ScIsUserServiceAllowedForUser(*((const unsigned __int16 **)v11 + 7), (HKEY)Handle, IsDsmaUserContext) )
      {
        if ( !(unsigned int)StringCchPrintfW(Buffer, 0x101u, L"%s_%I64x", *((_QWORD *)v11 + 7), a1) )
        {
          JITReadDisplayName = CServiceRecord::GetJITReadDisplayName((CServiceRecord *)v11, v14, v15);
          if ( !(unsigned int)StringCchPrintfW(v75, 0x101u, L"%s_%I64x", JITReadDisplayName, a1) )
          {
            ImageFileName = ScGetImageFileName((HKEY)Handle, 0, (unsigned __int16 **)&v60);
            if ( !ImageFileName )
            {
              Microsoft::WRL::ComPtr<CServiceRecord>::InternalRelease(&v53);
              (*(void (__fastcall **)(char *))(*(_QWORD *)v11 + 48LL))(v11);
              CServiceRecord::GetGroupName((CServiceRecord *)v11);
              RealServiceType = CServiceRecord::GetRealServiceType(v17);
              ImageFileName = ScCreateService(
                                0,
                                *((struct _SERVICE_CONFIG_ROOT **)v11 + 27),
                                Buffer,
                                v75,
                                RealServiceType,
                                v22,
                                v21,
                                (unsigned __int16 *)v60,
                                v20,
                                0,
                                0,
                                0,
                                0,
                                0,
                                0,
                                v19,
                                a1,
                                v62,
                                (struct CServiceRecord *)v11,
                                &v53);
              if ( !ImageFileName )
              {
                CScmLock::LockAutoExclusive((char *)v53 + 312, v54);
                TriggerInfo = CServiceRecord::OpenServiceConfigKey(v53, 0x2001Fu, v23, (HKEY *)&v59);
                ImageFileName = TriggerInfo;
                if ( TriggerInfo )
                {
                  v25 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                    && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
                  {
                    v26 = 62;
                    goto LABEL_29;
                  }
                  goto LABEL_31;
                }
                CServiceRecord::SetStatusFlag(v53, *((_DWORD *)v11 + 13) & 0x28);
                if ( !ScReadDependencies((HKEY)Handle, (unsigned __int16 **)&v61, *((const unsigned __int16 **)v11 + 7)) )
                {
                  if ( v61 )
                  {
                    ImageFileName = ScCreateDependencies(v53, (unsigned __int16 *)v61);
                    if ( ImageFileName )
                      goto LABEL_31;
                  }
                }
                v28 = (void *)*((_QWORD *)v11 + 18);
                if ( v28 )
                {
                  TriggerInfo = CServiceRecord::SetServiceSd(v53, v28);
                  ImageFileName = TriggerInfo;
                  if ( TriggerInfo )
                  {
                    v25 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                      && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
                    {
                      v26 = 63;
                      goto LABEL_29;
                    }
                    goto LABEL_31;
                  }
                  v29 = ScWriteSd((HKEY)v59, *((void **)v53 + 18));
                  ImageFileName = v29;
                  if ( v29 )
                  {
                    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                      && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
                    {
                      WPP_SF_Sd(
                        WPP_GLOBAL_Control->StubInfo,
                        64,
                        (unsigned int)WPP_036c406685683e02631f01bfa4d71e7e_Traceguids,
                        (unsigned int)Buffer,
                        v29);
                    }
                    goto LABEL_31;
                  }
                }
                TriggerInfo = ScGetTriggerInfo(
                                *((struct _SERVICE_CONFIG_ROOT **)v11 + 27),
                                *((const unsigned __int16 **)v11 + 7),
                                (HKEY)Handle,
                                *((_DWORD *)v11 + 20),
                                1,
                                (*((_DWORD *)v11 + 42) >> 1) & 1,
                                &v58);
                ImageFileName = TriggerInfo;
                if ( TriggerInfo )
                {
                  v25 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                    && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
                  {
                    v27 = (wchar_t *)*((_QWORD *)v11 + 7);
                    v26 = 65;
                    goto LABEL_30;
                  }
                  goto LABEL_31;
                }
                if ( v58->cTriggers )
                {
                  TriggerInfo = ScSaveTriggerInfo(
                                  *((struct _SERVICE_CONFIG_ROOT **)v11 + 27),
                                  Buffer,
                                  (HKEY)v59,
                                  *((_DWORD *)v11 + 20),
                                  0,
                                  v58);
                  ImageFileName = TriggerInfo;
                  if ( TriggerInfo )
                  {
                    v25 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                      && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
                    {
                      v26 = 66;
                      goto LABEL_29;
                    }
                    goto LABEL_31;
                  }
                  TriggerInfo = ScGetServiceChangeNotificationName(v53, 1, &v67);
                  ImageFileName = TriggerInfo;
                  if ( TriggerInfo )
                  {
                    v25 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                      && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
                    {
                      v26 = 67;
LABEL_29:
                      v27 = Buffer;
LABEL_30:
                      WPP_SF_Sd(
                        v25->StubInfo,
                        v26,
                        (unsigned int)WPP_036c406685683e02631f01bfa4d71e7e_Traceguids,
                        (_DWORD)v27,
                        TriggerInfo);
                    }
LABEL_31:
                    CScmSyncLockExclusive::InternalUnlock((CScmSyncLockExclusive *)v54);
                    goto LABEL_86;
                  }
                  v73[0] = v53;
                  if ( v53 )
                    _InterlockedAdd((volatile signed __int32 *)v53 + 3, 1u);
                  v73[1] = v67;
                  v73[2] = v58;
                  if ( !(unsigned __int8)utl::list__ScCreateUserServicesForUser_::_2_::UserServiceTriggerEntry_utl::allocator__ScCreateUserServicesForUser_::_2_::UserServiceTriggerEntry___::push_back(
                                           v68,
                                           v73) )
                  {
                    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                      && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
                    {
                      WPP_SF_S(
                        WPP_GLOBAL_Control->StubInfo,
                        68,
                        WPP_036c406685683e02631f01bfa4d71e7e_Traceguids,
                        Buffer);
                    }
                    ImageFileName = 8;
                    Microsoft::WRL::ComPtr<CServiceRecord>::InternalRelease(v73);
                    goto LABEL_31;
                  }
                  v58 = 0;
                  CServiceRecord::SetStatusFlag(v53, 0x400u);
                  Microsoft::WRL::ComPtr<CServiceRecord>::InternalRelease(v73);
                }
                ScReadFailureActions((HKEY)Handle, (struct _SERVICE_FAILURE_ACTIONS_WOW64 **)&P, 0);
                v30 = P;
                if ( P )
                {
                  v31 = *((_DWORD *)P + 3);
                  v32 = 0;
                  v33 = *(_DWORD *)P;
                  v34 = (SC_ACTION *)((char *)P + *((unsigned int *)P + 4));
                  v72.cActions = v31;
                  v72.dwResetPeriod = v33;
                  v72.lpCommand = 0;
                  v72.lpRebootMsg = 0;
                  v72.lpsaActions = v34;
                  if ( v31 )
                  {
                    v35 = v56;
                    do
                    {
                      if ( (unsigned int)(v34[v32].Type - 2) <= 1 )
                        v35 = 1;
                      ++v32;
                    }
                    while ( v32 < v31 );
                    v56 = v35;
                    v30 = P;
                  }
                  if ( v56 )
                  {
                    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                      && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
                    {
                      WPP_SF_S(
                        WPP_GLOBAL_Control->StubInfo,
                        69,
                        WPP_036c406685683e02631f01bfa4d71e7e_Traceguids,
                        Buffer);
                    }
                  }
                  else
                  {
                    ScWriteFailureActions((HKEY)v59, &v72);
                  }
                  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v30);
                }
                if ( !ScReadOptionalString((HKEY)Handle, L"Description", (unsigned __int16 **)&v64, 0) )
                {
                  v36 = v64;
                  if ( v64 )
                  {
                    ScWriteOptionalString((HKEY)v59, L"Description", (const unsigned __int16 *)v64);
                    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v36);
                    v64 = 0;
                  }
                }
                if ( !(unsigned __int8)utl::list<Microsoft::WRL::ComPtr<CServiceRecord>,utl::allocator<Microsoft::WRL::ComPtr<CServiceRecord>>>::push_back(
                                         v69,
                                         &v53)
                  && WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                  && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
                {
                  WPP_SF_S(WPP_GLOBAL_Control->StubInfo, 70, WPP_036c406685683e02631f01bfa4d71e7e_Traceguids, Buffer);
                }
                CScmSyncLockExclusive::InternalUnlock((CScmSyncLockExclusive *)v54);
                ImageFileName = 0;
              }
            }
          }
        }
      }
    }
LABEL_86:
    if ( v60 )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v60);
      v60 = 0;
    }
    v3 = (struct _SERVICE_TRIGGER_INFO *)v61;
    if ( v61 )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v61);
      v3 = 0;
      v61 = 0;
    }
    if ( v58 != v3 )
    {
      ScFreeTriggerInfo(&v58);
      v58 = v3;
    }
    if ( Handle )
    {
      v37 = NtClose(Handle);
      RtlNtStatusToDosError(v37);
      Handle = v3;
    }
    if ( v59 )
    {
      v38 = NtClose(v59);
      RtlNtStatusToDosError(v38);
      v59 = v3;
    }
    if ( ImageFileName && v53 )
    {
      CServiceRecord::SetStatusFlag(v53, 1u);
      ScDeleteServiceRecord(v53);
    }
    Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockShared *)v71);
  }
  RtlReleaseResource(&ScServiceRecordLock);
  if ( IsDsmaUserContext != (_DWORD)v3 && (_QWORD *)v69[0] != v69 )
    DsmaUserLoggedIn = 1;
  ScDrainRemoteNotifyQueues();
  for ( j = (void **)v68[0]; j != v68; j = (void **)*j )
  {
    v52[0] = 16;
    v40 = ((__int64 (__fastcall *)(void *, _QWORD, _QWORD, void **, _QWORD))g_pScExtFunctionPointers[10])(
            j[4],
            *((_QWORD *)j[2] + 7),
            *(_QWORD *)v66,
            j + 3,
            *(_QWORD *)v52);
    if ( v40
      && WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
    {
      WPP_SF_Sd(
        WPP_GLOBAL_Control->StubInfo,
        71,
        (unsigned int)WPP_036c406685683e02631f01bfa4d71e7e_Traceguids,
        (unsigned int)Buffer,
        v40);
    }
    ScFreeTriggerInfo((struct _SERVICE_TRIGGER_INFO **)j + 4);
  }
  RtlReleaseSRWLockExclusive(&g_TriggerRegistrationLock);
  for ( k = (_QWORD *)v69[0]; k != v69; k = (_QWORD *)*k )
  {
    v42 = (struct CServiceRecord *)k[2];
    if ( *((_DWORD *)v42 + 9) == 2 && (*((_DWORD *)v42 + 13) & 8) == 0 )
      ScStartServiceAndDependencies(v42, 0, 0, 0, 8u, (struct CServiceRecord *)v3);
  }
  ScInitDelayStart(a1);
  v4 = IsDsmaUserContext;
LABEL_117:
  if ( hObject )
    CloseHandle(hObject);
  if ( v66 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v66);
  while ( 1 )
  {
    v43 = v68[0];
    if ( v68[0] == v68 )
      break;
    v44 = (_QWORD *)*((_QWORD *)v68[0] + 1);
    v45 = (char *)v68[0] + 16;
    v46 = *(_QWORD *)v68[0];
    *v44 = *(_QWORD *)v68[0];
    *(_QWORD *)(v46 + 8) = v44;
    Microsoft::WRL::ComPtr<CServiceRecord>::InternalRelease(v45);
    operator delete(v43, (const struct std::nothrow_t *)std::nothrow);
  }
  v68[2] = v3;
  utl::list<Microsoft::WRL::ComPtr<CServiceRecord>,utl::allocator<Microsoft::WRL::ComPtr<CServiceRecord>>>::clear((__int64)v69);
  while ( 1 )
  {
    v47 = v70[0];
    if ( v70[0] == v70 )
      break;
    v48 = (_QWORD *)*((_QWORD *)v70[0] + 1);
    v49 = *(_QWORD *)v70[0];
    *v48 = *(_QWORD *)v70[0];
    *(_QWORD *)(v49 + 8) = v48;
    v50 = (SmartPtrRef *)v47[2];
    if ( v50 )
    {
      v47[2] = v3;
      SmartPtrRef::Release(v50);
    }
    operator delete(v47, (const struct std::nothrow_t *)std::nothrow);
  }
  v70[2] = v3;
  Microsoft::WRL::ComPtr<CServiceRecord>::InternalRelease(&v53);
  return v4;
}

```

## disassembly

```asm
0x140029908  mov     [rsp-8+arg_10], rbx
0x14002990d  push    rbp
0x14002990e  push    rsi
0x14002990f  push    rdi
0x140029910  push    r12
0x140029912  push    r13
0x140029914  push    r14
0x140029916  push    r15
0x140029918  lea     rbp, [rsp-4B0h]
0x140029920  sub     rsp, 5D0h
0x140029927  mov     rax, cs:__security_cookie
0x14002992e  xor     rax, rsp
0x140029931  mov     [rbp+4E0h+var_40], rax
0x140029938  xor     eax, eax
0x14002993a  mov     [rbp+4E0h+var_520], edx
0x14002993d  xorps   xmm0, xmm0
0x140029940  mov     [rbp+4E0h+var_530], rax
0x140029944  mov     r13, rcx
0x140029947  mov     [rbp+4E0h+var_510], rax
0x14002994b  xor     r15d, r15d
0x14002994e  mov     [rbp+4E0h+Handle], rax
0x140029952  lea     rcx, [rbp+4E0h+var_4C0]
0x140029956  mov     [rbp+4E0h+var_538], rax
0x14002995a  mov     [rbp+4E0h+var_540], rax
0x14002995e  mov     [rbp+4E0h+var_560], rax
0x140029962  mov     qword ptr [rbp+4E0h+var_4F8.Data], rax
0x140029966  mov     [rbp+4E0h+hObject], rax
0x14002996a  mov     [rbp+4E0h+var_500], rax
0x14002996e  mov     [rbp+4E0h+var_528], rax
0x140029972  mov     [rbp+4E0h+P], r15
0x140029976  movups  xmmword ptr [rbp+4E0h+var_4A0.dwResetPeriod], xmm0
0x14002997a  mov     [rbp+4E0h+var_4A0.lpsaActions], rax
0x14002997e  movups  xmmword ptr [rbp+4E0h+var_4A0.lpCommand], xmm0
0x140029982  call    ??0?$list@V?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@@utl@@@utl@@QEAA@XZ; utl::list<Microsoft::WRL::ComPtr<CServiceRecord>,utl::allocator<Microsoft::WRL::ComPtr<CServiceRecord>>>::list<Microsoft::WRL::ComPtr<CServiceRecord>,utl::allocator<Microsoft::WRL::ComPtr<CServiceRecord>>>(void)
0x140029987  lea     rcx, [rbp+4E0h+var_4D8]
0x14002998b  call    ??0?$list@V?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@@utl@@@utl@@QEAA@XZ; utl::list<Microsoft::WRL::ComPtr<CServiceRecord>,utl::allocator<Microsoft::WRL::ComPtr<CServiceRecord>>>::list<Microsoft::WRL::ComPtr<CServiceRecord>,utl::allocator<Microsoft::WRL::ComPtr<CServiceRecord>>>(void)
0x140029990  lea     rcx, [rbp+4E0h+var_4F0]
0x140029994  call    ??0?$list@V?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@@utl@@@utl@@QEAA@XZ; utl::list<Microsoft::WRL::ComPtr<CServiceRecord>,utl::allocator<Microsoft::WRL::ComPtr<CServiceRecord>>>::list<Microsoft::WRL::ComPtr<CServiceRecord>,utl::allocator<Microsoft::WRL::ComPtr<CServiceRecord>>>(void)
0x140029999  call    IsUMgrQueryUserContextPresent
0x14002999e  test    al, al
0x1400299a0  jnz     short loc_1400299E5
0x1400299a2  mov     esi, r15d
0x1400299a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400299ac  lea     r14, WPP_GLOBAL_Control
0x1400299b3  cmp     rcx, r14
0x1400299b6  jz      loc_14002A27B
0x1400299bc  lea     edi, [r15+1]
0x1400299c0  test    [rcx+1Ch], dil
0x1400299c4  jz      loc_14002A27B
0x1400299ca  mov     rcx, [rcx+10h]
0x1400299ce  lea     edx, [rdi+39h]
0x1400299d1  mov     r9, r13
0x1400299d4  lea     r8, WPP_036c406685683e02631f01bfa4d71e7e_Traceguids
0x1400299db  call    WPP_SF_q
0x1400299e0  jmp     loc_14002A27B
0x1400299e5  mov     rcx, r13; unsigned __int64
0x1400299e8  call    ?ScIsDsmaUserContext@@YAH_K@Z; ScIsDsmaUserContext(unsigned __int64)
0x1400299ed  lea     rdx, [rbp+4E0h+hObject]
0x1400299f1  mov     [rbp+4E0h+var_544], eax
0x1400299f4  mov     rcx, r13
0x1400299f7  mov     esi, eax
0x1400299f9  call    cs:__imp_UMgrQueryUserToken
0x1400299ff  test    eax, eax
0x140029a01  jns     short loc_140029A3E
0x140029a03  mov     rcx, cs:WPP_GLOBAL_Control
0x140029a0a  lea     r14, WPP_GLOBAL_Control
0x140029a11  cmp     rcx, r14
0x140029a14  jz      loc_14002A27B
0x140029a1a  mov     edi, 1
0x140029a1f  test    [rcx+1Ch], dil
0x140029a23  jz      loc_14002A27B
0x140029a29  mov     rcx, [rcx+10h]
0x140029a2d  mov     r9, r13
0x140029a30  mov     [rsp+600h+var_5E0], eax
0x140029a34  call    WPP_SF_ID
0x140029a39  jmp     loc_14002A27B
0x140029a3e  mov     rcx, [rbp+4E0h+hObject]; TokenHandle
0x140029a42  lea     r8, [rbp+4E0h+var_500]; void **
0x140029a46  mov     edi, 1
0x140029a4b  mov     edx, edi; TokenInformationClass
0x140029a4d  call    ?ScGetTokenInformation@@YAKPEAXW4_TOKEN_INFORMATION_CLASS@@PEAPEAX@Z; ScGetTokenInformation(void *,_TOKEN_INFORMATION_CLASS,void * *)
0x140029a52  test    eax, eax
0x140029a54  jz      short loc_140029A96
0x140029a56  mov     rcx, cs:WPP_GLOBAL_Control
0x140029a5d  lea     r14, WPP_GLOBAL_Control
0x140029a64  cmp     rcx, r14
0x140029a67  jz      loc_14002A27B
0x140029a6d  test    [rcx+1Ch], dil
0x140029a71  jz      loc_14002A27B
0x140029a77  mov     rcx, [rcx+10h]
0x140029a7b  lea     edx, [rdi+3Bh]
0x140029a7e  mov     r9, r13
0x140029a81  mov     [rsp+600h+var_5E0], eax
0x140029a85  lea     r8, WPP_036c406685683e02631f01bfa4d71e7e_Traceguids
0x140029a8c  call    WPP_SF_iD
0x140029a91  jmp     loc_14002A27B
0x140029a96  lea     rcx, [rbp+4E0h+var_4C0]
0x140029a9a  call    ?ScGetWin32TemplateServices@@YAKAEAV?$list@V?$ComPtr@VCWin32ServiceRecord@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VCWin32ServiceRecord@@@WRL@Microsoft@@@utl@@@utl@@@Z; ScGetWin32TemplateServices(utl::list<Microsoft::WRL::ComPtr<CWin32ServiceRecord>,utl::allocator<Microsoft::WRL::ComPtr<CWin32ServiceRecord>>> &)
0x140029a9f  test    eax, eax
0x140029aa1  jz      short loc_140029AE1
0x140029aa3  mov     rcx, cs:WPP_GLOBAL_Control
0x140029aaa  lea     r14, WPP_GLOBAL_Control
0x140029ab1  cmp     rcx, r14
0x140029ab4  jz      loc_14002A27B
0x140029aba  test    [rcx+1Ch], dil
0x140029abe  jz      loc_14002A27B
0x140029ac4  mov     rcx, [rcx+10h]
0x140029ac8  lea     r8, WPP_036c406685683e02631f01bfa4d71e7e_Traceguids
0x140029acf  mov     edx, 3Dh ; '='
0x140029ad4  mov     r9d, eax
0x140029ad7  call    WPP_SF_d
0x140029adc  jmp     loc_14002A27B
0x140029ae1  lea     rcx, g_TriggerRegistrationLock
0x140029ae8  mov     [rbp+4E0h+var_548], r15d
0x140029aec  call    cs:__imp_RtlAcquireSRWLockExclusive
0x140029af2  call    cs:__imp_GetCurrentThreadId
0x140029af8  mov     dl, dil; Wait
0x140029afb  lea     rcx, ?ScServiceRecordLock@@3VCServiceRecordLock@@A; Resource
0x140029b02  call    cs:__imp_RtlAcquireResourceExclusive
0x140029b08  mov     rbx, [rbp+4E0h+var_4C0]
0x140029b0c  lea     r14, WPP_GLOBAL_Control
0x140029b13  lea     r12, WPP_036c406685683e02631f01bfa4d71e7e_Traceguids
0x140029b1a  lea     rax, [rbp+4E0h+var_4C0]
0x140029b1e  cmp     rbx, rax
0x140029b21  jz      loc_14002A180
0x140029b27  mov     r15, [rbx+10h]
0x140029b2b  lea     rdx, [rbp+4E0h+var_4A8]
0x140029b2f  lea     rcx, [r15+138h]
0x140029b36  call    ?LockAutoShared@CScmLock@@QEAA?AVCScmSyncLockShared@@XZ; CScmLock::LockAutoShared(void)
0x140029b3b  lea     r9, [rbp+4E0h+Handle]; HKEY *
0x140029b3f  mov     edx, 20019h; unsigned int
0x140029b44  mov     rcx, r15; this
0x140029b47  call    ?OpenServiceConfigKey@CServiceRecord@@QEAAKKHPEAPEAUHKEY__@@@Z; CServiceRecord::OpenServiceConfigKey(ulong,int,HKEY__ * *)
0x140029b4c  mov     esi, eax
0x140029b4e  test    eax, eax
0x140029b50  jnz     loc_14002A0BA
0x140029b56  mov     r8d, [rbp+4E0h+var_544]; int
0x140029b5a  mov     rdx, [rbp+4E0h+Handle]; HKEY
0x140029b5e  mov     rcx, [r15+38h]; unsigned __int16 *
0x140029b62  call    ?ScIsUserServiceAllowedForUser@@YAHPEBGPEAUHKEY__@@H@Z; ScIsUserServiceAllowedForUser(ushort const *,HKEY__ *,int)
0x140029b67  test    eax, eax
0x140029b69  jz      loc_14002A0BA
0x140029b6f  mov     r9, [r15+38h]
0x140029b73  lea     r8, aSI64x; "%s_%I64x"
0x140029b7a  mov     edx, 101h; unsigned __int64
0x140029b7f  mov     qword ptr [rsp+600h+var_5E0], r13
0x140029b84  lea     rcx, [rbp+4E0h+Buffer]; Buffer
0x140029b8b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140029b90  test    eax, eax
0x140029b92  jnz     loc_14002A0BA
0x140029b98  mov     rcx, r15; this
0x140029b9b  call    ?GetJITReadDisplayName@CServiceRecord@@QEAAPEAGXZ; CServiceRecord::GetJITReadDisplayName(void)
0x140029ba0  mov     r9, rax
0x140029ba3  mov     qword ptr [rsp+600h+var_5E0], r13
0x140029ba8  lea     r8, aSI64x; "%s_%I64x"
0x140029baf  mov     edx, 101h; unsigned __int64
0x140029bb4  lea     rcx, [rbp+4E0h+var_250]; Buffer
0x140029bbb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140029bc0  test    eax, eax
0x140029bc2  jnz     loc_14002A0BA
0x140029bc8  mov     rcx, [rbp+4E0h+Handle]; HKEY
0x140029bcc  lea     r8, [rbp+4E0h+var_530]; unsigned __int16 **
0x140029bd0  xor     edx, edx; unsigned __int16
0x140029bd2  call    ?ScGetImageFileName@@YAKPEAUHKEY__@@GPEAPEAG@Z; ScGetImageFileName(HKEY__ *,ushort,ushort * *)
0x140029bd7  mov     esi, eax
0x140029bd9  test    eax, eax
0x140029bdb  jnz     loc_14002A0BA
0x140029be1  lea     rcx, [rbp+4E0h+var_560]
0x140029be5  call    ?InternalRelease@?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CServiceRecord>::InternalRelease(void)
0x140029bea  mov     rax, [r15]
0x140029bed  mov     rcx, r15
0x140029bf0  mov     rax, [rax+30h]
0x140029bf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140029bf9  mov     rcx, r15; this
0x140029bfc  movzx   edx, ax
0x140029bff  call    ?GetGroupName@CServiceRecord@@QEAAPEAGXZ; CServiceRecord::GetGroupName(void)
0x140029c04  mov     r9d, [r15+28h]
0x140029c08  mov     r8, rax
0x140029c0b  mov     r10d, [r15+24h]
0x140029c0f  call    ?GetRealServiceType@CServiceRecord@@QEAAKXZ; CServiceRecord::GetRealServiceType(void)
0x140029c14  lea     rcx, [rbp+4E0h+var_560]
0x140029c18  mov     [rsp+600h+var_568], rcx; struct CServiceRecord **
0x140029c20  mov     ecx, [rbp+4E0h+var_520]
0x140029c23  mov     [rsp+600h+var_570], r15; struct CServiceRecord *
0x140029c2b  mov     [rsp+600h+var_578], ecx; unsigned int
0x140029c32  xor     ecx, ecx
0x140029c34  mov     [rsp+600h+var_580], r13; unsigned __int64
0x140029c3c  mov     [rsp+600h+var_588], dx; unsigned __int16
0x140029c41  mov     rdx, [r15+0D8h]; struct _SERVICE_CONFIG_ROOT *
0x140029c48  mov     [rsp+600h+var_590], ecx; unsigned int
0x140029c4c  mov     [rsp+600h+var_598], rcx; unsigned __int8 *
0x140029c51  mov     [rsp+600h+var_5A0], rcx; unsigned __int16 *
0x140029c56  mov     [rsp+600h+var_5A8], ecx; unsigned int
0x140029c5a  mov     [rsp+600h+var_5B0], rcx; unsigned __int8 *
0x140029c5f  mov     [rsp+600h+var_5B8], rcx; unsigned int *
0x140029c64  mov     rcx, [rbp+4E0h+var_530]
0x140029c68  mov     [rsp+600h+var_5C0], r8; unsigned __int16 *
0x140029c6d  lea     r8, [rbp+4E0h+Buffer]; unsigned __int16 *
0x140029c74  mov     [rsp+600h+var_5C8], rcx; unsigned __int16 *
0x140029c79  xor     ecx, ecx; void *
0x140029c7b  mov     dword ptr [rsp+600h+var_5D0], r9d; unsigned int
0x140029c80  lea     r9, [rbp+4E0h+var_250]; unsigned __int16 *
0x140029c87  mov     dword ptr [rsp+600h+var_5D8], r10d; unsigned int
0x140029c8c  mov     [rsp+600h+var_5E0], eax; unsigned int
0x140029c90  call    ?ScCreateService@@YAKPEAXPEAU_SERVICE_CONFIG_ROOT@@PEAG2KKK22PEAKPEAEK24KG_KKPEAVCServiceRecord@@PEAPEAV2@@Z; ScCreateService(void *,_SERVICE_CONFIG_ROOT *,ushort *,ushort *,ulong,ulong,ulong,ushort *,ushort *,ulong *,uchar *,ulong,ushort *,uchar *,ulong,ushort,unsigned __int64,ulong,CServiceRecord *,CServiceRecord * *)
0x140029c95  mov     esi, eax
0x140029c97  test    eax, eax
0x140029c99  jnz     loc_14002A0BA
0x140029c9f  mov     rcx, [rbp+4E0h+var_560]
0x140029ca3  lea     rdx, [rbp+4E0h+var_558]
0x140029ca7  add     rcx, 138h
0x140029cae  call    ?LockAutoExclusive@CScmLock@@QEAA?AVCScmSyncLockExclusive@@XZ; CScmLock::LockAutoExclusive(void)
0x140029cb3  mov     rcx, [rbp+4E0h+var_560]; this
0x140029cb7  lea     r9, [rbp+4E0h+var_538]; HKEY *
0x140029cbb  mov     edx, 2001Fh; unsigned int
0x140029cc0  call    ?OpenServiceConfigKey@CServiceRecord@@QEAAKKHPEAPEAUHKEY__@@@Z; CServiceRecord::OpenServiceConfigKey(ulong,int,HKEY__ * *)
0x140029cc5  mov     esi, eax
0x140029cc7  test    eax, eax
0x140029cc9  jz      short loc_140029D07
0x140029ccb  mov     rcx, cs:WPP_GLOBAL_Control
0x140029cd2  cmp     rcx, r14
0x140029cd5  jz      short loc_140029CF9
0x140029cd7  test    [rcx+1Ch], dil
0x140029cdb  jz      short loc_140029CF9
0x140029cdd  mov     edx, 3Eh ; '>'
0x140029ce2  lea     r9, [rbp+4E0h+Buffer]
0x140029ce9  mov     rcx, [rcx+10h]
0x140029ced  mov     r8, r12
0x140029cf0  mov     [rsp+600h+var_5E0], eax
0x140029cf4  call    WPP_SF_Sd
0x140029cf9  lea     rcx, [rbp+4E0h+var_558]; this
0x140029cfd  call    ?InternalUnlock@CScmSyncLockExclusive@@IEAAXXZ; CScmSyncLockExclusive::InternalUnlock(void)
0x140029d02  jmp     loc_14002A0BA
0x140029d07  mov     edx, [r15+34h]
0x140029d0b  mov     rcx, [rbp+4E0h+var_560]; this
0x140029d0f  and     edx, 28h; unsigned int
0x140029d12  call    ?SetStatusFlag@CServiceRecord@@QEAAXK@Z; CServiceRecord::SetStatusFlag(ulong)
0x140029d17  mov     r8, [r15+38h]; unsigned __int16 *
0x140029d1b  lea     rdx, [rbp+4E0h+var_528]; unsigned __int16 **
0x140029d1f  mov     rcx, [rbp+4E0h+Handle]; KeyHandle
0x140029d23  call    ?ScReadDependencies@@YAKPEAUHKEY__@@PEAPEAGPEBG@Z; ScReadDependencies(HKEY__ *,ushort * *,ushort const *)
0x140029d28  test    eax, eax
0x140029d2a  jnz     short loc_140029D47
0x140029d2c  mov     rax, [rbp+4E0h+var_528]
0x140029d30  test    rax, rax
0x140029d33  jz      short loc_140029D47
0x140029d35  mov     rcx, [rbp+4E0h+var_560]; struct CServiceRecord *
0x140029d39  mov     rdx, rax; unsigned __int16 *
0x140029d3c  call    ?ScCreateDependencies@@YAKPEAVCServiceRecord@@PEAG@Z; ScCreateDependencies(CServiceRecord *,ushort *)
0x140029d41  mov     esi, eax
0x140029d43  test    eax, eax
0x140029d45  jnz     short loc_140029CF9
0x140029d47  mov     rdx, [r15+90h]; void *
0x140029d4e  test    rdx, rdx
0x140029d51  jz      loc_140029DD7
0x140029d57  mov     rcx, [rbp+4E0h+var_560]; this
0x140029d5b  call    ?SetServiceSd@CServiceRecord@@QEAAKPEAXH@Z; CServiceRecord::SetServiceSd(void *,int)
0x140029d60  mov     esi, eax
0x140029d62  test    eax, eax
0x140029d64  jz      short loc_140029D82
0x140029d66  mov     rcx, cs:WPP_GLOBAL_Control
0x140029d6d  cmp     rcx, r14
0x140029d70  jz      short loc_140029CF9
0x140029d72  test    [rcx+1Ch], dil
0x140029d76  jz      short loc_140029CF9
0x140029d78  mov     edx, 3Fh ; '?'
0x140029d7d  jmp     loc_140029CE2
0x140029d82  mov     rdx, [rbp+4E0h+var_560]
0x140029d86  mov     rcx, [rbp+4E0h+var_538]; HKEY
0x140029d8a  mov     rdx, [rdx+90h]; void *
0x140029d91  call    ?ScWriteSd@@YAKPEAUHKEY__@@PEAX@Z; ScWriteSd(HKEY__ *,void *)
0x140029d96  mov     esi, eax
0x140029d98  test    eax, eax
0x140029d9a  jz      short loc_140029DD7
0x140029d9c  mov     rcx, cs:WPP_GLOBAL_Control
0x140029da3  cmp     rcx, r14
0x140029da6  jz      loc_140029CF9
0x140029dac  test    [rcx+1Ch], dil
0x140029db0  jz      loc_140029CF9
0x140029db6  mov     rcx, [rcx+10h]
0x140029dba  lea     r9, [rbp+4E0h+Buffer]
0x140029dc1  mov     edx, 40h ; '@'
0x140029dc6  mov     [rsp+600h+var_5E0], eax
0x140029dca  mov     r8, r12
0x140029dcd  call    WPP_SF_Sd
0x140029dd2  jmp     loc_140029CF9
0x140029dd7  mov     eax, [r15+0A8h]
0x140029dde  lea     rcx, [rbp+4E0h+var_540]
0x140029de2  mov     r9d, [r15+50h]; unsigned int
0x140029de6  mov     r8, [rbp+4E0h+Handle]; HKEY
0x140029dea  mov     rdx, [r15+38h]; unsigned __int16 *
0x140029dee  mov     [rsp+600h+var_5D0], rcx; struct _SERVICE_TRIGGER_INFO **
0x140029df3  mov     rcx, [r15+0D8h]; struct _SERVICE_CONFIG_ROOT *
0x140029dfa  shr     eax, 1
0x140029dfc  and     eax, edi
0x140029dfe  mov     dword ptr [rsp+600h+var_5D8], eax; int
0x140029e02  mov     [rsp+600h+var_5E0], edi; int
0x140029e06  call    ?ScGetTriggerInfo@@YAKPEAU_SERVICE_CONFIG_ROOT@@PEBGPEAUHKEY__@@KHHPEAPEAU_SERVICE_TRIGGER_INFO@@@Z; ScGetTriggerInfo(_SERVICE_CONFIG_ROOT *,ushort const *,HKEY__ *,ulong,int,int,_SERVICE_TRIGGER_INFO * *)
0x140029e0b  mov     esi, eax
0x140029e0d  test    eax, eax
  ... truncated ...
```
