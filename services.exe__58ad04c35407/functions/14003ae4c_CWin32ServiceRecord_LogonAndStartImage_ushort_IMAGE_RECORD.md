# CWin32ServiceRecord::LogonAndStartImage(ushort *,_IMAGE_RECORD * *)

- ea: `0x14003ae4c`
- end: `0x14003c506`
- name: `?LogonAndStartImage@CWin32ServiceRecord@@IEAAKPEAGPEAPEAU_IMAGE_RECORD@@@Z`
- size: `5818`
- prototype: `__int64 __fastcall(CWin32ServiceRecord *this, unsigned __int16 *, struct _IMAGE_RECORD **)`
- caller_count: `1`
- callee_count: `45`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x14003c510`

## callees

- `0x140003e54`
- `0x140004c58`
- `0x14000b014`
- `0x14000bebc`
- `0x14000cf60`
- `0x140013b0c`
- `0x140014824`
- `0x140016318`
- `0x1400188fc`
- `0x14001c87c`
- `0x14001d818`
- `0x14001e710`
- `0x140020d84`
- `0x140022c34`
- `0x140022d20`
- `0x140023c00`
- `0x140026328`
- `0x140026494`
- `0x140027320`
- `0x140029228`
- `0x14002b3ec`
- `0x14002c220`
- `0x140030a5c`
- `0x1400322dc`
- `0x140037f90`
- `0x140038698`
- `0x14003ae4c`
- `0x1400575b0`
- `0x14005b040`
- `0x14005b0a8`
- `0x14005b268`
- `0x140063144`
- `0x140063928`
- `0x140064a90`
- `0x14006d760`
- `0x14006f128`
- `0x1400703f4`
- `0x14007b1cc`
- `0x140082710`
- `0x140082bd0`
- `0x140082dd0`
- `0x140083348`
- `0x1400833c0`
- `0x140092060`
- `0x140094020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b9c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003bbc4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003bdf5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003c078`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b9c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003bbc4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003bdf5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003c078`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x14003c35b`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x14003c35b`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x14003b9bb`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x14003b9bb`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x14003bde7`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x14003bde7`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x14003c453`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x14003c453`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x14003c057`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x14003c057`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003c3a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003c442`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003c4ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003c3a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003c442`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003c4ab`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x14003bce7`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x14003bd56`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x14003bea3`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x14003bce7`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x14003bd56`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x14003bea3`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x14003bbba`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x14003bbba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003c285`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003c2d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003c2eb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003c285`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003c2d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003c2eb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003c272`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003c272`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x14003c4d4`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x14003c4d4`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x14003c4be`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x14003c4be`
- `ntdll!RtlReleaseResource` at `0x14003b193`
- `ntdll!RtlReleaseResource` at `0x14003b33c`
- `ntdll!RtlReleaseResource` at `0x14003b193`
- `ntdll!RtlReleaseResource` at `0x14003b33c`
- `ntdll!RtlAcquireResourceShared` at `0x14003b0a9`
- `ntdll!RtlAcquireResourceShared` at `0x14003b1a2`
- `ntdll!RtlAcquireResourceShared` at `0x14003b469`
- `ntdll!RtlAcquireResourceShared` at `0x14003b0a9`
- `ntdll!RtlAcquireResourceShared` at `0x14003b1a2`
- `ntdll!RtlAcquireResourceShared` at `0x14003b469`
- `ntdll!RtlNtStatusToDosError` at `0x14003bb66`
- `ntdll!RtlNtStatusToDosError` at `0x14003c1bd`
- `ntdll!RtlNtStatusToDosError` at `0x14003bb66`
- `ntdll!RtlNtStatusToDosError` at `0x14003c1bd`
- `ntdll!RtlFreeHeap` at `0x14003c2b5`
- `ntdll!RtlFreeHeap` at `0x14003c31f`
- `ntdll!RtlFreeHeap` at `0x14003c346`
- `ntdll!RtlFreeHeap` at `0x14003c373`
- `ntdll!RtlFreeHeap` at `0x14003c394`
- `ntdll!RtlFreeHeap` at `0x14003c3c5`
- `ntdll!RtlFreeHeap` at `0x14003c3e6`
- `ntdll!RtlFreeHeap` at `0x14003c407`
- `ntdll!RtlFreeHeap` at `0x14003c2b5`
- `ntdll!RtlFreeHeap` at `0x14003c31f`
- `ntdll!RtlFreeHeap` at `0x14003c346`
- `ntdll!RtlFreeHeap` at `0x14003c373`
- `ntdll!RtlFreeHeap` at `0x14003c394`
- `ntdll!RtlFreeHeap` at `0x14003c3c5`
- `ntdll!RtlFreeHeap` at `0x14003c3e6`
- `ntdll!RtlFreeHeap` at `0x14003c407`
- `ntdll!RtlRegisterWait` at `0x14003c189`
- `ntdll!RtlRegisterWait` at `0x14003c189`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x14003bc9e`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x14003bc9e`
- `ntdll!RtlDeleteSecurityObject` at `0x14003c417`
- `ntdll!RtlDeleteSecurityObject` at `0x14003c417`
- `ntdll!RtlDeregisterWait` at `0x14003c469`
- `ntdll!RtlDeregisterWait` at `0x14003c469`
- `ntdll!RtlAllocateHeap` at `0x14003b854`
- `ntdll!RtlAllocateHeap` at `0x14003b854`
- `profapi!__imp_CreateEnvBlock` at `0x14003b5c5`
- `profapi!__imp_CreateEnvBlock` at `0x14003b705`
- `profapi!__imp_CreateEnvBlock` at `0x14003b5c5`
- `profapi!__imp_CreateEnvBlock` at `0x14003b705`
- `profapi!__imp_DestroyEnvBlock` at `0x14003c296`
- `profapi!__imp_DestroyEnvBlock` at `0x14003c296`
- `profapi!__imp_UnloadProfileBasic` at `0x14003c433`
- `profapi!__imp_UnloadProfileBasic` at `0x14003c433`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x14003b626`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x14003b626`
- `ext-ms-win-com-psmregister-l1-3-0!PsmAdjustActivationTokenEx` at `0x14003bc8f`
- `ext-ms-win-com-psmregister-l1-3-0!PsmAdjustActivationTokenEx` at `0x14003bc8f`
- `ext-ms-win-desktopappx-l1-1-0!PostCreateProcessDesktopAppXActivation` at `0x14003bec6`
- `ext-ms-win-desktopappx-l1-1-0!PostCreateProcessDesktopAppXActivation` at `0x14003bec6`
- `ext-ms-win-desktopappx-l1-1-0!PrepareDesktopAppXActivation` at `0x14003bd19`
- `ext-ms-win-desktopappx-l1-1-0!PrepareDesktopAppXActivation` at `0x14003bd19`

## pseudocode

```c
__int64 __fastcall CWin32ServiceRecord::LogonAndStartImage(
        CWin32ServiceRecord *this,
        unsigned __int16 *a2,
        struct _IMAGE_RECORD **a3)
{
  unsigned __int16 *v5; // r13
  bool v6; // zf
  unsigned int v7; // eax
  ULONG StartingImageMitigationConfiguration; // ebx
  __int64 v10; // r8
  int v11; // r9d
  __int64 v12; // rax
  DWORD *v13; // rcx
  unsigned int v14; // r13d
  unsigned int v15; // eax
  PRPC_ASYNC_STATE v16; // rcx
  int v17; // edx
  unsigned int v18; // ebx
  __int64 v19; // rcx
  unsigned __int16 v20; // ax
  __int128 *v21; // r13
  HANDLE v22; // rdx
  __int64 v23; // r8
  __int64 v24; // rax
  __int64 (__fastcall *v25)(CWin32ServiceRecord *); // rax
  unsigned int v26; // eax
  __int128 *v27; // rdx
  ULONG v28; // eax
  __int64 v29; // r8
  int v30; // r9d
  __int64 v31; // rax
  LPWSTR v32; // r12
  int v33; // eax
  int v34; // r8d
  __int64 v35; // rax
  int v36; // eax
  PRPC_ASYNC_STATE v37; // rcx
  int v38; // edx
  unsigned int TokenInformation; // eax
  unsigned int v40; // eax
  DWORD v41; // eax
  PRPC_ASYNC_STATE v42; // rcx
  __int64 v43; // rdx
  __int64 v44; // r12
  __int64 v45; // rax
  __int64 v46; // rax
  SIZE_T v47; // r12
  __int64 v48; // rax
  unsigned __int64 v49; // rdx
  WCHAR *v50; // r12
  PRPC_ASYNC_STATE v51; // r10
  __int64 v52; // rdx
  __int64 v53; // r10
  struct _PROC_THREAD_ATTRIBUTE_LIST *v54; // rcx
  DWORD LastError; // eax
  const unsigned __int16 **v56; // r12
  PRPC_ASYNC_STATE v57; // rcx
  __int64 v58; // rdx
  HLOCAL *p_hMem; // rax
  int v60; // eax
  NTSTATUS v61; // r12d
  struct _PROC_THREAD_ATTRIBUTE_LIST *v62; // rcx
  __int64 v63; // rdx
  PVOID v64; // rbx
  int v65; // eax
  int v66; // eax
  __int64 v67; // r9
  __int64 v68; // r8
  DWORD v69; // eax
  int v70; // eax
  unsigned int v71; // r13d
  unsigned int inited; // eax
  PRPC_ASYNC_STATE v73; // rcx
  int v74; // edx
  HLOCAL v75; // rcx
  __int64 v76; // rbx
  DWORD v77; // eax
  DWORD v78; // ebx
  unsigned __int16 *JITReadDisplayName; // rax
  unsigned int v80; // eax
  NTSTATUS v81; // eax
  NTSTATUS v82; // ebx
  void *v83; // rbx
  unsigned __int64 v84; // rax
  unsigned int ImageRecord; // eax
  HLOCAL *v86; // rax
  unsigned int i; // r12d
  PVOID *v88; // r13
  unsigned int v89; // r12d
  unsigned int v90; // r14d
  LPPROC_THREAD_ATTRIBUTE_LIST v91; // r12
  HANDLE hProcess; // rcx
  unsigned int v93; // eax
  unsigned int v94; // [rsp+58h] [rbp-A8h]
  unsigned int v95; // [rsp+80h] [rbp-80h] BYREF
  PVOID P; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v97; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v98; // [rsp+94h] [rbp-6Ch] BYREF
  HANDLE hToken; // [rsp+98h] [rbp-68h] BYREF
  LPWSTR lpCommandLine; // [rsp+A0h] [rbp-60h]
  unsigned int v101; // [rsp+A8h] [rbp-58h] BYREF
  int v102; // [rsp+ACh] [rbp-54h] BYREF
  unsigned int v103; // [rsp+B0h] [rbp-50h] BYREF
  PVOID lpValue; // [rsp+B8h] [rbp-48h] BYREF
  int v105; // [rsp+C0h] [rbp-40h]
  unsigned int v106; // [rsp+C4h] [rbp-3Ch] BYREF
  LPVOID lpEnvironment; // [rsp+C8h] [rbp-38h] BYREF
  LPWSTR Buffer; // [rsp+D0h] [rbp-30h]
  int v109; // [rsp+D8h] [rbp-28h] BYREF
  DWORD dwCreationFlags[2]; // [rsp+E0h] [rbp-20h] BYREF
  HLOCAL hMem; // [rsp+E8h] [rbp-18h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+F0h] [rbp-10h] BYREF
  HLOCAL v113; // [rsp+108h] [rbp+8h] BYREF
  struct _SC_SERVICE_CHANNEL_CONTEXT *v114; // [rsp+110h] [rbp+10h] BYREF
  struct _IMAGE_RECORD **v115; // [rsp+118h] [rbp+18h] BYREF
  __int64 v116; // [rsp+120h] [rbp+20h] BYREF
  unsigned int v117; // [rsp+128h] [rbp+28h] BYREF
  void *phNewWaitObject; // [rsp+130h] [rbp+30h] BYREF
  LPPROC_THREAD_ATTRIBUTE_LIST lpAttributeList; // [rsp+138h] [rbp+38h] BYREF
  PVOID v120; // [rsp+140h] [rbp+40h] BYREF
  PSECURITY_DESCRIPTOR ObjectDescriptor; // [rsp+148h] [rbp+48h] BYREF
  __int64 v122; // [rsp+150h] [rbp+50h] BYREF
  HKEY hKey; // [rsp+158h] [rbp+58h] BYREF
  PVOID v124; // [rsp+160h] [rbp+60h] BYREF
  PVOID v125; // [rsp+168h] [rbp+68h] BYREF
  unsigned __int16 *v126; // [rsp+170h] [rbp+70h]
  struct _SECURITY_ATTRIBUTES ProcessAttributes; // [rsp+178h] [rbp+78h] BYREF
  __int64 v128; // [rsp+190h] [rbp+90h] BYREF
  __int128 v129; // [rsp+198h] [rbp+98h] BYREF
  __int128 v130; // [rsp+1A8h] [rbp+A8h]
  __int64 v131; // [rsp+1B8h] [rbp+B8h]
  struct _STARTUPINFOEXW StartupInfo; // [rsp+1C0h] [rbp+C0h] BYREF
  __int128 v133; // [rsp+230h] [rbp+130h] BYREF
  __int128 v134; // [rsp+240h] [rbp+140h]
  __int64 v135; // [rsp+250h] [rbp+150h]

  v115 = a3;
  lpCommandLine = a2;
  hToken = 0;
  v126 = 0;
  hKey = 0;
  P = 0;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  v5 = 0;
  v95 = 0;
  hMem = LocalSystemSid;
  lpEnvironment = 0;
  phNewWaitObject = 0;
  v113 = 0;
  v101 = 0;
  v124 = 0;
  v106 = 0;
  v109 = 0;
  v117 = 0;
  v114 = 0;
  memset(&StartupInfo, 0, sizeof(StartupInfo));
  v103 = 0;
  v6 = (*((_DWORD *)this + 20) & 0x200) == 0;
  v128 = 0;
  v125 = 0;
  lpValue = 0;
  v120 = 0;
  v98 = 0;
  v129 = 0;
  v131 = 0;
  v130 = 0;
  v122 = 0;
  ObjectDescriptor = 0;
  lpAttributeList = 0;
  memset(&ProcessAttributes, 0, sizeof(ProcessAttributes));
  v97 = 0;
  if ( v6 )
    goto LABEL_19;
  if ( (unsigned __int8)IsPostCreateProcessDesktopAppXActivationPresent()
    && (unsigned __int8)IsPostCreateProcessDesktopAppXActivationPresent()
    && (unsigned __int8)IsPsmAdjustActivationTokenExPresent() )
  {
    v7 = ScReadServicePackageInfoFromRegistry(this, (unsigned __int16 **)&lpValue, (unsigned __int16 **)&v120, &v98);
    StartingImageMitigationConfiguration = v7;
    if ( v7 )
    {
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        WPP_SF_Sd(
          WPP_GLOBAL_Control->StubInfo,
          55,
          (unsigned int)WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids,
          *((_QWORD *)this + 7),
          v7);
      return StartingImageMitigationConfiguration;
    }
    if ( !lpValue || !v120 )
    {
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        WPP_SF_S(
          WPP_GLOBAL_Control->StubInfo,
          56,
          WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids,
          *((_QWORD *)this + 7));
      return 87;
    }
LABEL_19:
    v6 = *((_BYTE *)this + 80) >= 0;
    v105 = -2147467259;
    Buffer = a2;
    if ( v6 )
    {
      StartingImageMitigationConfiguration = ScLookupServiceAccount(
                                               *((struct _SERVICE_CONFIG_ROOT **)this + 27),
                                               *((unsigned __int16 **)this + 7),
                                               (unsigned __int16 **)&P);
      if ( StartingImageMitigationConfiguration )
      {
        RtlAcquireResourceShared(&ScServiceRecordLock, 1u);
        CScmLock::LockAutoExclusive((char *)this + 312, &v116);
        v10 = (*(__int64 (__fastcall **)(CWin32ServiceRecord *))(*(_QWORD *)this + 160LL))(this);
        if ( (unsigned int)dword_1400BA2A0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400BA2A0, 0x400000000000LL, v10) )
        {
          v103 = StartingImageMitigationConfiguration;
          v98 = 2;
          v102 = ScShutdownInProgress != 0;
          v97 = (*((_DWORD *)this + 20) >> 4) & 1;
          v12 = 0;
          if ( v10 )
            v12 = *(_QWORD *)(v10 + 24);
          *(_QWORD *)dwCreationFlags = v12;
          v115 = (struct _IMAGE_RECORD **)*((_QWORD *)this + 7);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            0,
            (unsigned int)byte_1400AF115,
            v10,
            v11,
            (__int64)&v115,
            (__int64)dwCreationFlags,
            (__int64)&v97,
            (__int64)&v102,
            (__int64)&v98,
            (__int64)&v103);
        }
        CWin32ServiceRecord::QueueRecoveryAction(this, 2, v10);
        v13 = (DWORD *)&v116;
LABEL_27:
        CScmSyncLockExclusive::InternalUnlock((CScmSyncLockExclusive *)v13);
LABEL_28:
        RtlReleaseResource(&ScServiceRecordLock);
LABEL_29:
        v5 = (unsigned __int16 *)P;
        goto LABEL_260;
      }
      RtlAcquireResourceShared(&ScServiceRecordLock, 1u);
      StartingImageMitigationConfiguration = ScGetStartingImageMitigationConfiguration(
                                               this,
                                               lpCommandLine,
                                               &v95,
                                               (int *)&v97,
                                               (struct _SC_PROCESS_MITIGATION_POLICY *)&ProcessAttributes);
      if ( StartingImageMitigationConfiguration )
      {
        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        {
          WPP_SF_Sd(
            WPP_GLOBAL_Control->StubInfo,
            57,
            (unsigned int)WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids,
            *((_QWORD *)this + 7),
            StartingImageMitigationConfiguration);
        }
        goto LABEL_28;
      }
      v14 = v97;
      if ( g_CetSupportEnabled && v97 )
        v95 |= 0x400u;
      v15 = ScCreateServiceSids(lpCommandLine, this, 1, (void ***)&v113, &v101, &v95, &v109, &v117);
      StartingImageMitigationConfiguration = v15;
      if ( v15 )
      {
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        {
          goto LABEL_28;
        }
        v17 = 58;
        goto LABEL_41;
      }
      v15 = ScCreateCapabilitySids(this, (void ***)&v124, &v106);
      StartingImageMitigationConfiguration = v15;
      if ( v15 )
      {
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        {
          goto LABEL_28;
        }
        v17 = 59;
        goto LABEL_41;
      }
      v97 = (*(__int64 (__fastcall **)(CWin32ServiceRecord *))(*(_QWORD *)this + 224LL))(this);
      v18 = v97;
      v19 = *(_QWORD *)this;
      dwCreationFlags[0] = v97 != 0 ? 787468 : 525324;
      v20 = (*(__int64 (__fastcall **)(CWin32ServiceRecord *))(v19 + 128))(this);
      v15 = ScCreateProcessAttributeList(
              *((const unsigned __int16 **)this + 7),
              v18,
              v14,
              (struct _SC_PROCESS_MITIGATION_POLICY *)&ProcessAttributes,
              v20,
              lpValue,
              &lpAttributeList);
      StartingImageMitigationConfiguration = v15;
      if ( v15 )
      {
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        {
          goto LABEL_28;
        }
        v17 = 60;
LABEL_41:
        WPP_SF_Sd(
          v16->StubInfo,
          v17,
          (unsigned int)WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids,
          *((_QWORD *)this + 7),
          v15);
        goto LABEL_28;
      }
      RtlReleaseResource(&ScServiceRecordLock);
      v21 = (__int128 *)P;
      if ( P || v101 || *((_QWORD *)this + 9) )
      {
        v24 = *(_QWORD *)this;
        v133 = *(_OWORD *)L"NT AUTHORITY\\SYSTEM";
        v25 = *(__int64 (__fastcall **)(CWin32ServiceRecord *))(v24 + 112);
        v135 = *(_QWORD *)L"TEM";
        v134 = *(_OWORD *)L"RITY\\SYSTEM";
        v26 = v25(this);
        v27 = &v133;
        if ( v21 )
          v27 = v21;
        v94 = v26;
        v28 = ScLogonService(
                *((_QWORD *)this + 7),
                v27,
                v113,
                v101,
                v124,
                v106,
                (v95 >> 3) & 1,
                v109,
                *((_QWORD *)this + 43) != 0,
                v117,
                *((_DWORD *)this + 95));
        v5 = (unsigned __int16 *)P;
        StartingImageMitigationConfiguration = v28;
        if ( v28 )
        {
          if ( !(*(unsigned int (__fastcall **)(CWin32ServiceRecord *))(*(_QWORD *)this + 112LL))(this) )
            goto LABEL_260;
          RtlAcquireResourceShared(&ScServiceRecordLock, 1u);
          CScmLock::LockAutoExclusive((char *)this + 312, dwCreationFlags);
          v29 = (*(__int64 (__fastcall **)(CWin32ServiceRecord *))(*(_QWORD *)this + 160LL))(this);
          if ( (unsigned int)dword_1400BA2A0 > 5
            && (unsigned __int8)tlgKeywordOn(&dword_1400BA2A0, 0x400000000000LL, v29) )
          {
            v103 = StartingImageMitigationConfiguration;
            v98 = 3;
            v102 = ScShutdownInProgress != 0;
            v97 = (*((_DWORD *)this + 20) >> 4) & 1;
            v31 = 0;
            if ( v29 )
              v31 = *(_QWORD *)(v29 + 24);
            v116 = v31;
            v115 = (struct _IMAGE_RECORD **)*((_QWORD *)this + 7);
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              0,
              (unsigned int)&word_1400AF0AE,
              v29,
              v30,
              (__int64)&v115,
              (__int64)&v116,
              (__int64)&v97,
              (__int64)&v102,
              (__int64)&v98,
              (__int64)&v103);
          }
          CWin32ServiceRecord::QueueRecoveryAction(this, 3, v29);
          v13 = dwCreationFlags;
          goto LABEL_27;
        }
        v32 = lpCommandLine;
        StartingImageMitigationConfiguration = ScRemovePrivileges(
                                                 this,
                                                 lpCommandLine,
                                                 0,
                                                 hToken,
                                                 (const unsigned __int16 *)P,
                                                 &v95);
        if ( StartingImageMitigationConfiguration )
        {
          if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
          {
            WPP_SF_dSS(
              WPP_GLOBAL_Control->StubInfo,
              61,
              (unsigned int)WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids,
              StartingImageMitigationConfiguration,
              *((_QWORD *)this + 7),
              (__int64)v32);
          }
          goto LABEL_260;
        }
        v22 = hToken;
        v23 = 0;
      }
      else
      {
        v22 = g_hProcessToken;
        v23 = 1;
      }
      v33 = CreateEnvBlock(&lpEnvironment, v22, v23);
LABEL_90:
      v105 = v33;
      if ( v33 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 68, WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids, (unsigned int)v33);
        }
        lpEnvironment = 0;
      }
      else
      {
        v40 = CServiceRecord::OpenServiceConfigKey(this, 0x20019u, v34, &hKey);
        StartingImageMitigationConfiguration = v40;
        if ( v40 )
        {
          if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
          {
            WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 66, WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids, v40);
          }
          goto LABEL_29;
        }
        v41 = ScMergeEnvironments(hKey, &lpEnvironment);
        StartingImageMitigationConfiguration = v41;
        if ( v41 )
        {
          if ( v41 != 2 )
          {
            v42 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
              || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
            {
              goto LABEL_29;
            }
            v43 = 67;
            goto LABEL_100;
          }
          StartingImageMitigationConfiguration = 0;
        }
      }
      if ( (*((_BYTE *)this + 80) & 0x30) == 0x30 )
      {
        v44 = -1;
        v45 = -1;
        do
          ++v45;
        while ( lpCommandLine[v45] );
        v116 = v45;
        v46 = (*(__int64 (__fastcall **)(CWin32ServiceRecord *, _QWORD))(*(_QWORD *)this + 24LL))(this, 0);
        do
          ++v44;
        while ( *(_WORD *)(v46 + 2 * v44) );
        v47 = 2 * (v44 + v116) + 16;
        Buffer = (LPWSTR)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v47);
        if ( Buffer )
        {
          v48 = (*(__int64 (__fastcall **)(CWin32ServiceRecord *))(*(_QWORD *)this + 24LL))(this);
          v49 = v47;
          v50 = Buffer;
          StringCbPrintfW(Buffer, v49, L"%s -s %s", lpCommandLine, v48);
        }
        else
        {
          v50 = lpCommandLine;
          Buffer = lpCommandLine;
        }
      }
      else
      {
        v50 = Buffer;
      }
      if ( !P && !v101 && !*((_QWORD *)this + 9) && *((char *)this + 80) >= 0 )
      {
        if ( (*((_DWORD *)this + 20) & 0x100) != 0 )
        {
          if ( (unsigned int)ScAllowInteractiveServices() )
          {
            v51 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
              || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 2) == 0 )
            {
              goto LABEL_129;
            }
            v52 = 81;
          }
          else
          {
            v51 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
              || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 2) == 0 )
            {
              goto LABEL_129;
            }
            v52 = 82;
          }
          WPP_SF_S(v51->StubInfo, v52, WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids, *((_QWORD *)this + 7));
        }
LABEL_129:
        ScInitStartupInfo(&StartupInfo, 0);
        v54 = StartupInfo.lpAttributeList;
        if ( lpAttributeList )
          v54 = lpAttributeList;
        StartupInfo.lpAttributeList = v54;
        if ( (PRPC_ASYNC_STATE *)v53 != &WPP_GLOBAL_Control && (*(_BYTE *)(v53 + 28) & 4) != 0 )
          WPP_SF_S(*(_QWORD *)(v53 + 16), 83, WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids, *((_QWORD *)this + 7));
        if ( !CreateProcessW(
                0,
                v50,
                0,
                0,
                0,
                dwCreationFlags[0],
                lpEnvironment,
                0,
                &StartupInfo.StartupInfo,
                &ProcessInformation) )
        {
          LastError = GetLastError();
          StartingImageMitigationConfiguration = LastError;
          if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
          {
            WPP_SF_SSD(
              WPP_GLOBAL_Control->StubInfo,
              84,
              (unsigned int)WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids,
              *((_QWORD *)this + 7),
              (__int64)v50,
              LastError);
          }
          if ( !StartingImageMitigationConfiguration )
            StartingImageMitigationConfiguration = 1066;
          goto LABEL_29;
        }
        if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->UserInfo) & 0x400) == 0 )
        {
          v56 = (const unsigned __int16 **)((char *)this + 56);
        }
        else
        {
          v56 = (const unsigned __int16 **)((char *)this + 56);
          WPP_SF_S(
            WPP_GLOBAL_Control->StubInfo,
            85,
            WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids,
            *((_QWORD *)this + 7));
        }
LABEL_210:
        if ( hToken && *((char *)this + 80) >= 0 )
        {
          v5 = (unsigned __int16 *)P;
        }
        else
        {
          v5 = (unsigned __int16 *)P;
          inited = ScRemovePrivileges(
                     this,
                     lpCommandLine,
                     ProcessInformation.hProcess,
                     hToken,
                     (const unsigned __int16 *)P,
                     &v95);
          StartingImageMitigationConfiguration = inited;
          if ( inited )
          {
            v73 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
              || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
            {
              goto LABEL_29;
            }
            v74 = 86;
LABEL_216:
            WPP_SF_SSD(
              v73->StubInfo,
              v74,
              (unsigned int)WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids,
              (unsigned int)*v56,
              (__int64)lpCommandLine,
              inited);
            goto LABEL_260;
          }
        }
        if ( (v95 & 8) != 0 )
        {
          v75 = hMem;
          if ( hMem == LocalSystemSid || v97 )
          {
LABEL_226:
            inited = ScInitControlMessageContext(v75, ProcessInformation.hProcess);
            StartingImageMitigationConfiguration = inited;
            if ( inited )
            {
              v73 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
              {
                goto LABEL_260;
              }
              v74 = 88;
            }
            else
            {
              if ( ResumeThread(ProcessInformation.hThread) == -1
                && WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
              {
                v76 = (__int64)*v56;
                v77 = GetLastError();
                WPP_SF_dSS(
                  WPP_GLOBAL_Control->StubInfo,
                  89,
                  (unsigned int)WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids,
                  v77,
                  v76,
                  (__int64)lpCommandLine);
              }
              inited = ScWaitForFirstResponse(v114, ProcessInformation.hProcess, this, &v103);
              StartingImageMitigationConfiguration = inited;
              if ( !inited )
              {
                v78 = v103;
                if ( ProcessInformation.dwProcessId != v103 )
                {
                  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                    && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
                  {
                    WPP_SF_Dd(WPP_GLOBAL_Control->StubInfo, 91, WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids);
                  }
                  JITReadDisplayName = CServiceRecord::GetJITReadDisplayName(this);
                  ScLogEvent(0x27u, JITReadDisplayName, ProcessInformation.dwProcessId, v78);
                  ProcessInformation.dwProcessId = v78;
                }
                if ( (*((_BYTE *)this + 80) & 0x20) == 0
                  || (*((_DWORD *)this + 13) & 0x400000) != 0
                  || (*((_BYTE *)this + 80) & 0x10) != 0 )
                {
                  v80 = v95;
                }
                else
                {
                  v80 = v95 | 1;
                  v95 |= 1u;
                }
                if ( *((_QWORD *)this + 9) )
                  v95 = v80 | 0x800;
                v81 = RtlRegisterWait(
                        &phNewWaitObject,
                        ProcessInformation.hProcess,
                        ScProcessHandleIsSignaled,
                        ProcessInformation.hProcess,
                        0xFFFFFFFF,
                        8u);
                v82 = v81;
                if ( v81 >= 0 )
                {
                  v83 = phNewWaitObject;
                  v84 = (*(__int64 (__fastcall **)(CWin32ServiceRecord *))(*(_QWORD *)this + 80LL))(this);
                  ImageRecord = ScCreateImageRecord(
                                  v115,
                                  lpCommandLine,
                                  v126,
                                  v5,
                                  ProcessInformation.dwProcessId,
                                  ProcessInformation.hProcess,
                                  hToken,
                                  v126,
                                  v95,
                                  v114,
                                  v97,
                                  v94,
                                  v84,
                                  v83);
                  StartingImageMitigationConfiguration = ImageRecord;
                  if ( ImageRecord )
                  {
                    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                      && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
                    {
                      WPP_SF_Sd(
                        WPP_GLOBAL_Control->StubInfo,
                        93,
                        (unsigned int)WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids,
                        (unsigned int)*v56,
                        ImageRecord);
                    }
                  }
                  else
                  {
                    phNewWaitObject = 0;
                  }
                }
                else
                {
                  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                    && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
                  {
                    WPP_SF_d(
                      WPP_GLOBAL_Control->StubInfo,
                      92,
                      WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids,
                      (unsigned int)v81);
                  }
                  StartingImageMitigationConfiguration = RtlNtStatusToDosError(v82);
                }
                goto LABEL_260;
              }
              v73 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
              {
LABEL_260:
                if ( hKey )
                  RegCloseKey(hKey);
                if ( hMem != LocalSystemSid )
                  LocalFree(hMem);
                if ( v105 >= 0 )
                  DestroyEnvBlock(lpEnvironment);
                if ( v5 )
                  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
                v86 = (HLOCAL *)v113;
                if ( v113 )
                {
                  for ( i = 0; i < v101; ++i )
                  {
                    LocalFree(v86[i]);
                    v86 = (HLOCAL *)v113;
                  }
                  LocalFree(v86);
                }
                v88 = (PVOID *)v124;
                if ( v124 )
                {
                  v89 = 0;
                  if ( v106 )
                  {
                    v90 = v106;
                    do
                      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v88[v89++]);
                    while ( v89 < v90 );
                  }
                  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v88);
                }
                v91 = lpAttributeList;
                if ( lpAttributeList )
                {
                  DeleteProcThreadAttributeList(lpAttributeList);
                  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v91);
                }
                if ( v125 )
                  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v125);
                if ( ProcessInformation.hThread )
                  CloseHandle(ProcessInformation.hThread);
                if ( Buffer != lpCommandLine )
                  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
                if ( lpValue )
                  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, lpValue);
                if ( v120 )
                  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v120);
                if ( ObjectDescriptor )
                  RtlDeleteSecurityObject(&ObjectDescriptor);
                if ( StartingImageMitigationConfiguration )
                {
                  if ( *((char *)this + 80) >= 0 )
                    UnloadProfileBasic(hToken, v126);
                  if ( hToken )
                    CloseHandle(hToken);
                  hProcess = ProcessInformation.hProcess;
                  if ( ProcessInformation.hProcess )
                  {
                    TerminateProcess(ProcessInformation.hProcess, 0);
                    hProcess = ProcessInformation.hProcess;
                  }
                  if ( phNewWaitObject )
                  {
                    v93 = RtlDeregisterWait(phNewWaitObject);
                    if ( v93 )
                    {
                      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                        && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
                      {
                        WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 94, WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids, v93);
                      }
                      hProcess = 0;
                      ProcessInformation.hProcess = 0;
                    }
                    else
                    {
                      hProcess = ProcessInformation.hProcess;
                    }
                  }
                  if ( hProcess )
                    CloseHandle(hProcess);
                  if ( v114 )
                  {
                    RtlAcquireSRWLockExclusive(&g_ScServiceChannelLock);
                    ScReleaseRefAndFreeServiceChannelContextUnlocked(&v114);
                    RtlReleaseSRWLockExclusive(&g_ScServiceChannelLock);
                  }
                }
                return StartingImageMitigationConfiguration;
              }
              v74 = 90;
            }
            goto LABEL_216;
          }
          inited = ScAdjustTokenObjectSecurity(ProcessInformation.hProcess, hMem);
          StartingImageMitigationConfiguration = inited;
          if ( inited )
          {
            v73 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
              || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
            {
              goto LABEL_29;
            }
            v74 = 87;
            goto LABEL_216;
          }
        }
        v75 = hMem;
        goto LABEL_226;
      }
      memset(&ProcessAttributes, 0, sizeof(ProcessAttributes));
      if ( !P && (*((_DWORD *)this + 20) & 0x100) != 0 )
      {
        if ( (unsigned int)ScAllowInteractiveServices() )
        {
          v57 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 2) != 0 )
          {
            v58 = 69;
LABEL_153:
            WPP_SF_S(v57->StubInfo, v58, WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids, *((_QWORD *)this + 7));
          }
        }
        else
        {
          v57 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 2) != 0 )
          {
            v58 = 70;
            goto LABEL_153;
          }
        }
      }
      v6 = *((_BYTE *)this + 80) >= 0;
      p_hMem = &hMem;
      LOWORD(v133) = 0;
      if ( !v6 )
        p_hMem = (HLOCAL *)&v128;
      BYTE2(v133) = 0;
      *((_QWORD *)&v133 + 1) = p_hMem;
      DWORD1(v133) = 0x1FFFFF;
      *((_QWORD *)&v134 + 1) = &AliasAdminsSid;
      LOWORD(v134) = 0;
      BYTE2(v134) = 0;
      DWORD1(v134) = 5120;
      v60 = ScCreateAndSetSD((unsigned int)&v133, 2, v109 != 0 ? (unsigned int)hMem : 0, 0, (__int64)&ObjectDescriptor);
      v61 = v60;
      if ( v60 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 71, WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids, (unsigned int)v60);
        }
        StartingImageMitigationConfiguration = RtlNtStatusToDosError(v61);
        goto LABEL_29;
      }
      ProcessAttributes.lpSecurityDescriptor = ObjectDescriptor;
      ProcessAttributes.bInheritHandle = 0;
      ProcessAttributes.nLength = 24;
      ScInitStartupInfo(&StartupInfo, 0);
      v62 = StartupInfo.lpAttributeList;
      if ( lpAttributeList )
        v62 = lpAttributeList;
      StartupInfo.lpAttributeList = v62;
      if ( !ImpersonateLoggedOnUser(hToken) )
      {
        v41 = GetLastError();
        StartingImageMitigationConfiguration = v41;
        v42 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        {
          goto LABEL_29;
        }
        v43 = 72;
LABEL_100:
        WPP_SF_d(v42->StubInfo, v43, WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids, v41);
        goto LABEL_29;
      }
      v56 = (const unsigned __int16 **)((char *)this + 56);
      if ( (*((_DWORD *)this + 20) & 0x200) != 0 )
      {
        ScPackagedServiceProcessCreationActivityStart(*v56, (const unsigned __int16 *)lpValue);
        v102 = 0;
        if ( (int)ScFullTrustCapabilitiesAreDisabledByDefault((const unsigned __int16 *)lpValue, &v102) < 0 )
          goto LABEL_29;
        v63 = 2415919117LL;
        if ( v102 )
        {
          if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) != 0 )
          {
            WPP_SF_S(WPP_GLOBAL_Control->StubInfo, 73, WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids, *v56);
          }
          v63 = 2415923213LL;
        }
        v64 = lpValue;
        v65 = PsmAdjustActivationTokenEx(hToken, v63, 1, lpValue, v120, v98, 0, 0, 0);
        v98 = v65;
        if ( v65 < 0 )
        {
          StartingImageMitigationConfiguration = RtlNtStatusToDosErrorNoTeb(v65);
          if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
          {
            WPP_SF_Sd(
              WPP_GLOBAL_Control->StubInfo,
              74,
              (unsigned int)WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids,
              (unsigned int)*v56,
              v98);
          }
          ScPackagedServiceProcessCreationActivityStop(*v56, lpValue, 1, StartingImageMitigationConfiguration);
LABEL_179:
          RevertToSelf();
          goto LABEL_29;
        }
        *(_QWORD *)&v129 = hToken;
        *(_QWORD *)&v130 = v64;
        LODWORD(v131) = 3;
        v66 = PrepareDesktopAppXActivation(&v129, &v122);
        v98 = v66;
        if ( v66 < 0 )
        {
          if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
          {
            WPP_SF_Sd(
              WPP_GLOBAL_Control->StubInfo,
              75,
              (unsigned int)WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids,
              (unsigned int)*v56,
              v66);
          }
          StartingImageMitigationConfiguration = 87;
          RevertToSelf();
          v67 = v98;
          v68 = 2;
LABEL_185:
          ScPackagedServiceProcessCreationActivityStop(*v56, lpValue, v68, v67);
          goto LABEL_29;
        }
      }
      else
      {
        v64 = lpValue;
      }
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) != 0 )
      {
        v56 = (const unsigned __int16 **)((char *)this + 56);
        WPP_SF_S(
          WPP_GLOBAL_Control->StubInfo,
          76,
          WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids,
          *((_QWORD *)this + 7));
      }
      if ( !CreateProcessAsUserW(
              hToken,
              0,
              Buffer,
              &ProcessAttributes,
              0,
              0,
              dwCreationFlags[0],
              lpEnvironment,
              0,
              &StartupInfo.StartupInfo,
              &ProcessInformation) )
      {
        v69 = GetLastError();
        StartingImageMitigationConfiguration = v69;
        if ( (*((_DWORD *)this + 20) & 0x200) != 0 )
          ScPackagedServiceProcessCreationActivityStop(*v56, lpValue, 3, v69);
        if ( StartingImageMitigationConfiguration )
        {
          if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
          {
            WPP_SF_SSD(
              WPP_GLOBAL_Control->StubInfo,
              78,
              (unsigned int)WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids,
              (unsigned int)*v56,
              (__int64)Buffer,
              StartingImageMitigationConfiguration);
          }
        }
        else
        {
          StartingImageMitigationConfiguration = 1066;
          if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
          {
            WPP_SF_SS(
              WPP_GLOBAL_Control->StubInfo,
              77,
              (unsigned int)WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids,
              (unsigned int)*v56,
              (__int64)Buffer);
          }
        }
        goto LABEL_179;
      }
      RevertToSelf();
      if ( (*((_DWORD *)this + 20) & 0x200) != 0 )
      {
        *(_DWORD *)(v122 + 44) = 2;
        v70 = PostCreateProcessDesktopAppXActivation(hToken, v122, &ProcessInformation);
        v71 = v70;
        if ( v70 < 0 )
        {
          if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
          {
            WPP_SF_Sd(
              WPP_GLOBAL_Control->StubInfo,
              79,
              (unsigned int)WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids,
              (unsigned int)*v56,
              v70);
          }
          StartingImageMitigationConfiguration = 87;
          v67 = v71;
          v68 = 4;
          goto LABEL_185;
        }
        ScPackagedServiceProcessCreationActivityStop(*v56, v64, 0, 0);
      }
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->UserInfo) & 0x400) != 0 )
      {
        WPP_SF_S(WPP_GLOBAL_Control->StubInfo, 80, WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids, *v56);
      }
      goto LABEL_210;
    }
    if ( !(unsigned __int8)IsUMgrQueryUserContextPresent() )
    {
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        WPP_SF_S(
          WPP_GLOBAL_Control->StubInfo,
          62,
          WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids,
          *((_QWORD *)this + 7));
      StartingImageMitigationConfiguration = 50;
      goto LABEL_260;
    }
    v35 = (*(__int64 (__fastcall **)(CWin32ServiceRecord *))(*(_QWORD *)this + 80LL))(this);
    v36 = UMgrQueryUserToken(v35, &hToken);
    if ( v36 >= 0 )
    {
      v36 = ScMarkTokenAsUserService(hToken, *((_DWORD *)this + 11));
      if ( !v36 )
      {
        TokenInformation = ScGetTokenInformation(hToken, TokenUser, &v125);
        StartingImageMitigationConfiguration = TokenInformation;
        if ( !TokenInformation )
        {
          v97 = 0;
          dwCreationFlags[0] = 525324;
          v128 = *(_QWORD *)v125;
          v33 = CreateEnvBlock(&lpEnvironment, hToken, 0);
          goto LABEL_90;
        }
        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        {
          WPP_SF_Sd(
            WPP_GLOBAL_Control->StubInfo,
            65,
            (unsigned int)WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids,
            *((_QWORD *)this + 7),
            TokenInformation);
        }
LABEL_80:
        StartingImageMitigationConfiguration = 1057;
        goto LABEL_260;
      }
      v37 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        goto LABEL_80;
      v38 = 64;
    }
    else
    {
      v37 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        goto LABEL_80;
      v38 = 63;
    }
    WPP_SF_SSD(
      v37->StubInfo,
      v38,
      (unsigned int)WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids,
      *((_QWORD *)this + 7),
      (__int64)a2,
      v36);
    goto LABEL_80;
  }
  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
    WPP_SF_S(WPP_GLOBAL_Control->StubInfo, 54, WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids, *((_QWORD *)this + 7));
  return 50;
}

```

## disassembly

```asm
0x14003ae4c  mov     [rsp-8+arg_18], rbx
0x14003ae51  push    rbp
0x14003ae52  push    rsi
0x14003ae53  push    rdi
0x14003ae54  push    r12
0x14003ae56  push    r13
0x14003ae58  push    r14
0x14003ae5a  push    r15
0x14003ae5c  lea     rbp, [rsp-160h]
0x14003ae64  sub     rsp, 260h
0x14003ae6b  mov     rax, cs:__security_cookie
0x14003ae72  xor     rax, rsp
0x14003ae75  mov     [rbp+190h+var_38], rax
0x14003ae7c  xor     esi, esi
0x14003ae7e  mov     [rbp+190h+var_178], r8
0x14003ae82  xor     eax, eax
0x14003ae84  mov     [rbp+190h+lpCommandLine], rdx
0x14003ae88  mov     qword ptr [rbp+190h+ProcessInformation.dwProcessId], rax
0x14003ae8c  mov     r12, rdx
0x14003ae8f  mov     rax, cs:LocalSystemSid
0x14003ae96  mov     rdi, rcx
0x14003ae99  xorps   xmm0, xmm0
0x14003ae9c  mov     [rbp+190h+hToken], rsi
0x14003aea0  lea     r8d, [rsi+70h]; Size
0x14003aea4  mov     [rbp+190h+var_120], rsi
0x14003aea8  xor     edx, edx; Val
0x14003aeaa  mov     [rbp+190h+hKey], rsi
0x14003aeae  lea     rcx, [rbp+190h+StartupInfo]; void *
0x14003aeb5  mov     [rbp+190h+P], rsi
0x14003aeb9  movups  xmmword ptr [rbp+190h+ProcessInformation.hProcess], xmm0
0x14003aebd  mov     r13d, esi
0x14003aec0  mov     [rbp+190h+var_210], esi
0x14003aec3  mov     [rbp+190h+hMem], rax
0x14003aec7  mov     [rbp+190h+var_1C8], rsi
0x14003aecb  mov     [rbp+190h+phNewWaitObject], rsi
0x14003aecf  mov     [rbp+190h+var_188], rsi
0x14003aed3  mov     [rbp+190h+var_1E8], esi
0x14003aed6  mov     [rbp+190h+var_130], rsi
0x14003aeda  mov     [rbp+190h+var_1CC], esi
0x14003aedd  mov     [rbp+190h+var_1B8], esi
0x14003aee0  mov     [rbp+190h+var_168], esi
0x14003aee3  mov     [rbp+190h+var_180], rsi
0x14003aee7  call    memset
0x14003aeec  xor     eax, eax
0x14003aeee  mov     [rbp+190h+var_1E0], esi
0x14003aef1  test    dword ptr [rdi+50h], 200h
0x14003aef8  xorps   xmm0, xmm0
0x14003aefb  mov     [rbp+190h+var_100], rsi
0x14003af02  mov     [rbp+190h+var_128], rsi
0x14003af06  mov     [rbp+190h+lpValue], rsi
0x14003af0a  mov     [rbp+190h+var_150], rsi
0x14003af0e  mov     [rbp+190h+var_1FC], esi
0x14003af11  movups  [rbp+190h+var_F8], xmm0
0x14003af18  mov     [rbp+190h+var_D8], rax
0x14003af1f  movups  [rbp+190h+var_E8], xmm0
0x14003af26  mov     [rbp+190h+var_140], rsi
0x14003af2a  mov     [rbp+190h+ObjectDescriptor], rsi
0x14003af2e  mov     [rbp+190h+lpAttributeList], rsi
0x14003af32  movups  xmmword ptr [rbp+190h+ProcessAttributes.nLength], xmm0
0x14003af36  mov     qword ptr [rbp+190h+ProcessAttributes.bInheritHandle], rax
0x14003af3d  mov     [rbp+190h+var_200], esi
0x14003af40  jz      loc_14003B056
0x14003af46  call    IsPostCreateProcessDesktopAppXActivationPresent
0x14003af4b  test    al, al
0x14003af4d  jz      loc_14003B017
0x14003af53  call    IsPostCreateProcessDesktopAppXActivationPresent
0x14003af58  test    al, al
0x14003af5a  jz      loc_14003B017
0x14003af60  call    IsPsmAdjustActivationTokenExPresent
0x14003af65  test    al, al
0x14003af67  jz      loc_14003B017
0x14003af6d  lea     r9, [rbp+190h+var_1FC]; unsigned int *
0x14003af71  mov     rcx, rdi; struct CServiceRecord *
0x14003af74  lea     r8, [rbp+190h+var_150]; unsigned __int16 **
0x14003af78  lea     rdx, [rbp+190h+lpValue]; unsigned __int16 **
0x14003af7c  call    ?ScReadServicePackageInfoFromRegistry@@YAKPEAVCServiceRecord@@PEAPEAG1PEAK@Z; ScReadServicePackageInfoFromRegistry(CServiceRecord *,ushort * *,ushort * *,ulong *)
0x14003af81  mov     ebx, eax
0x14003af83  test    eax, eax
0x14003af85  jz      short loc_14003AFCC
0x14003af87  mov     rcx, cs:WPP_GLOBAL_Control
0x14003af8e  lea     r14, WPP_GLOBAL_Control
0x14003af95  cmp     rcx, r14
0x14003af98  jz      loc_14003C4DA
0x14003af9e  lea     esi, [r13+1]
0x14003afa2  test    [rcx+1Ch], sil
0x14003afa6  jz      loc_14003C4DA
0x14003afac  mov     r9, [rdi+38h]
0x14003afb0  lea     edx, [rsi+36h]
0x14003afb3  mov     rcx, [rcx+10h]
0x14003afb7  lea     r8, WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids
0x14003afbe  mov     [rsp+290h+bInheritHandles], eax
0x14003afc2  call    WPP_SF_Sd
0x14003afc7  jmp     loc_14003C4DA
0x14003afcc  cmp     [rbp+190h+lpValue], rsi
0x14003afd0  jz      short loc_14003AFD8
0x14003afd2  cmp     [rbp+190h+var_150], rsi
0x14003afd6  jnz     short loc_14003B056
0x14003afd8  mov     rcx, cs:WPP_GLOBAL_Control
0x14003afdf  lea     r14, WPP_GLOBAL_Control
0x14003afe6  cmp     rcx, r14
0x14003afe9  jz      short loc_14003B00D
0x14003afeb  mov     esi, 1
0x14003aff0  test    [rcx+1Ch], sil
0x14003aff4  jz      short loc_14003B00D
0x14003aff6  mov     r9, [rdi+38h]
0x14003affa  lea     edx, [rsi+37h]
0x14003affd  mov     rcx, [rcx+10h]
0x14003b001  lea     r8, WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids
0x14003b008  call    WPP_SF_S
0x14003b00d  mov     eax, 57h ; 'W'
0x14003b012  jmp     loc_14003C4DC
0x14003b017  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b01e  lea     r14, WPP_GLOBAL_Control
0x14003b025  cmp     rcx, r14
0x14003b028  jz      short loc_14003B04C
0x14003b02a  mov     esi, 1
0x14003b02f  test    [rcx+1Ch], sil
0x14003b033  jz      short loc_14003B04C
0x14003b035  mov     r9, [rdi+38h]
0x14003b039  lea     edx, [rsi+35h]
0x14003b03c  mov     rcx, [rcx+10h]
0x14003b040  lea     r8, WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids
0x14003b047  call    WPP_SF_S
0x14003b04c  mov     eax, 32h ; '2'
0x14003b051  jmp     loc_14003C4DC
0x14003b056  test    byte ptr [rdi+50h], 80h
0x14003b05a  lea     r14, WPP_GLOBAL_Control
0x14003b061  mov     [rbp+190h+var_1D0], 80004005h
0x14003b068  lea     r15, WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids
0x14003b06f  mov     [rbp+190h+Buffer], r12
0x14003b073  jnz     loc_14003B5D3
0x14003b079  mov     rdx, [rdi+38h]; unsigned __int16 *
0x14003b07d  lea     r8, [rbp+190h+P]; unsigned __int16 **
0x14003b081  mov     rcx, [rdi+0D8h]; struct _SERVICE_CONFIG_ROOT *
0x14003b088  call    ?ScLookupServiceAccount@@YAKPEAU_SERVICE_CONFIG_ROOT@@PEAGPEAPEAG@Z; ScLookupServiceAccount(_SERVICE_CONFIG_ROOT *,ushort *,ushort * *)
0x14003b08d  lea     r12, ?ScServiceRecordLock@@3VCServiceRecordLock@@A; CServiceRecordLock ScServiceRecordLock
0x14003b094  mov     esi, 1
0x14003b099  mov     dl, sil; Wait
0x14003b09c  mov     rcx, r12; Resource
0x14003b09f  mov     ebx, eax
0x14003b0a1  test    eax, eax
0x14003b0a3  jz      loc_14003B1A2
0x14003b0a9  call    cs:__imp_RtlAcquireResourceShared
0x14003b0af  lea     rcx, [rdi+138h]
0x14003b0b6  lea     rdx, [rbp+190h+var_170]
0x14003b0ba  call    ?LockAutoExclusive@CScmLock@@QEAA?AVCScmSyncLockExclusive@@XZ; CScmLock::LockAutoExclusive(void)
0x14003b0bf  mov     rcx, [rdi]
0x14003b0c2  mov     rax, [rcx+0A0h]
0x14003b0c9  mov     rcx, rdi
0x14003b0cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003b0d1  mov     ecx, cs:dword_1400BA2A0
0x14003b0d7  lea     r13d, [rsi+1]
0x14003b0db  mov     r8, rax
0x14003b0de  cmp     ecx, 5
0x14003b0e1  jbe     loc_14003B17C
0x14003b0e7  mov     rdx, 400000000000h
0x14003b0f1  lea     rcx, dword_1400BA2A0
0x14003b0f8  call    _tlgKeywordOn
0x14003b0fd  xor     ecx, ecx
0x14003b0ff  test    al, al
0x14003b101  jz      short loc_14003B17C
0x14003b103  cmp     cs:?ScShutdownInProgress@@3KA, ecx; ulong ScShutdownInProgress
0x14003b109  mov     eax, ecx
0x14003b10b  mov     [rbp+190h+var_1E0], ebx
0x14003b10e  setnz   al
0x14003b111  mov     [rbp+190h+var_1FC], r13d
0x14003b115  mov     [rbp+190h+var_1E4], eax
0x14003b118  mov     eax, [rdi+50h]
0x14003b11b  shr     eax, 4
0x14003b11e  and     eax, esi
0x14003b120  mov     [rbp+190h+var_200], eax
0x14003b123  mov     eax, ecx
0x14003b125  test    r8, r8
0x14003b128  jz      short loc_14003B12E
0x14003b12a  mov     rax, [r8+18h]
0x14003b12e  mov     qword ptr [rbp+190h+var_1B0], rax
0x14003b132  lea     rdx, byte_1400AF115
0x14003b139  mov     rax, [rdi+38h]
0x14003b13d  mov     [rbp+190h+var_178], rax
0x14003b141  lea     rax, [rbp+190h+var_1E0]
0x14003b145  mov     [rsp+290h+lpProcessInformation], rax
0x14003b14a  lea     rax, [rbp+190h+var_1FC]
0x14003b14e  mov     [rsp+290h+lpStartupInfo], rax
0x14003b153  lea     rax, [rbp+190h+var_1E4]
0x14003b157  mov     [rsp+290h+lpCurrentDirectory], rax
0x14003b15c  lea     rax, [rbp+190h+var_200]
0x14003b160  mov     [rsp+290h+lpEnvironment], rax
0x14003b165  lea     rax, [rbp+190h+var_1B0]
0x14003b169  mov     qword ptr [rsp+290h+dwCreationFlags], rax
0x14003b16e  lea     rax, [rbp+190h+var_178]
0x14003b172  mov     qword ptr [rsp+290h+bInheritHandles], rax
0x14003b177  call    ??$Write@U?$_tlgWrapSz@G@@U1@U?$_tlgWrapperByVal@$03@@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByVal@$03@@444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14003b17c  mov     edx, r13d
0x14003b17f  mov     rcx, rdi
0x14003b182  call    ?QueueRecoveryAction@CWin32ServiceRecord@@QEAAXW4SERVICE_FAILURE_REASON@@@Z; CWin32ServiceRecord::QueueRecoveryAction(SERVICE_FAILURE_REASON)
0x14003b187  lea     rcx, [rbp+190h+var_170]; this
0x14003b18b  call    ?InternalUnlock@CScmSyncLockExclusive@@IEAAXXZ; CScmSyncLockExclusive::InternalUnlock(void)
0x14003b190  mov     rcx, r12; Resource
0x14003b193  call    cs:__imp_RtlReleaseResource
0x14003b199  mov     r13, [rbp+190h+P]
0x14003b19d  jmp     loc_14003C269
0x14003b1a2  call    cs:__imp_RtlAcquireResourceShared
0x14003b1a8  mov     rdx, [rbp+190h+lpCommandLine]; unsigned __int16 *
0x14003b1ac  lea     rax, [rbp+190h+ProcessAttributes]
0x14003b1b0  lea     r9, [rbp+190h+var_200]; int *
0x14003b1b4  mov     qword ptr [rsp+290h+bInheritHandles], rax; struct _SC_PROCESS_MITIGATION_POLICY *
0x14003b1b9  lea     r8, [rbp+190h+var_210]; unsigned int *
0x14003b1bd  mov     rcx, rdi; this
0x14003b1c0  call    ?ScGetStartingImageMitigationConfiguration@@YAKPEAVCWin32ServiceRecord@@PEAGPEAKPEAHPEAU_SC_PROCESS_MITIGATION_POLICY@@@Z; ScGetStartingImageMitigationConfiguration(CWin32ServiceRecord *,ushort *,ulong *,int *,_SC_PROCESS_MITIGATION_POLICY *)
0x14003b1c5  mov     ebx, eax
0x14003b1c7  xor     eax, eax
0x14003b1c9  test    ebx, ebx
0x14003b1cb  jz      short loc_14003B1F8
0x14003b1cd  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b1d4  cmp     rcx, r14
0x14003b1d7  jz      short loc_14003B190
0x14003b1d9  test    [rcx+1Ch], sil
0x14003b1dd  jz      short loc_14003B190
0x14003b1df  lea     edx, [rax+39h]
0x14003b1e2  mov     [rsp+290h+bInheritHandles], ebx
0x14003b1e6  mov     r9, [rdi+38h]
0x14003b1ea  mov     r8, r15
0x14003b1ed  mov     rcx, [rcx+10h]
0x14003b1f1  call    WPP_SF_Sd
0x14003b1f6  jmp     short loc_14003B190
0x14003b1f8  cmp     cs:?g_CetSupportEnabled@@3HA, eax; int g_CetSupportEnabled
0x14003b1fe  mov     r13d, [rbp+190h+var_200]
0x14003b202  jz      short loc_14003B20E
0x14003b204  test    r13d, r13d
0x14003b207  jz      short loc_14003B20E
0x14003b209  bts     [rbp+190h+var_210], 0Ah
0x14003b20e  mov     rcx, [rbp+190h+lpCommandLine]; unsigned __int16 *
0x14003b212  lea     rax, [rbp+190h+var_168]
0x14003b216  mov     [rsp+290h+lpCurrentDirectory], rax; unsigned int *
0x14003b21b  lea     r9, [rbp+190h+var_188]; void ***
0x14003b21f  lea     rax, [rbp+190h+var_1B8]
0x14003b223  mov     r8d, esi; int
0x14003b226  mov     [rsp+290h+lpEnvironment], rax; int *
0x14003b22b  mov     rdx, rdi; struct CWin32ServiceRecord *
0x14003b22e  lea     rax, [rbp+190h+var_210]
0x14003b232  mov     qword ptr [rsp+290h+dwCreationFlags], rax; unsigned int *
0x14003b237  lea     rax, [rbp+190h+var_1E8]
0x14003b23b  mov     qword ptr [rsp+290h+bInheritHandles], rax; unsigned int *
0x14003b240  call    ?ScCreateServiceSids@@YAKPEAGPEAVCWin32ServiceRecord@@HPEAPEAPEAXPEAK3PEAH3@Z; ScCreateServiceSids(ushort *,CWin32ServiceRecord *,int,void * * *,ulong *,ulong *,int *,ulong *)
0x14003b245  mov     ebx, eax
0x14003b247  test    eax, eax
0x14003b249  jz      short loc_14003B273
0x14003b24b  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b252  cmp     rcx, r14
0x14003b255  jz      loc_14003B190
0x14003b25b  test    [rcx+1Ch], sil
0x14003b25f  jz      loc_14003B190
0x14003b265  mov     edx, 3Ah ; ':'
0x14003b26a  mov     [rsp+290h+bInheritHandles], eax
0x14003b26e  jmp     loc_14003B1E6
0x14003b273  lea     r8, [rbp+190h+var_1CC]; unsigned int *
0x14003b277  mov     rcx, rdi; struct CWin32ServiceRecord *
0x14003b27a  lea     rdx, [rbp+190h+var_130]; void ***
0x14003b27e  call    ?ScCreateCapabilitySids@@YAKPEAVCWin32ServiceRecord@@PEAPEAPEAXPEAK@Z; ScCreateCapabilitySids(CWin32ServiceRecord *,void * * *,ulong *)
0x14003b283  mov     ebx, eax
0x14003b285  test    eax, eax
0x14003b287  jz      short loc_14003B2AA
0x14003b289  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b290  cmp     rcx, r14
0x14003b293  jz      loc_14003B190
0x14003b299  test    [rcx+1Ch], sil
0x14003b29d  jz      loc_14003B190
0x14003b2a3  mov     edx, 3Bh ; ';'
0x14003b2a8  jmp     short loc_14003B26A
0x14003b2aa  mov     rax, [rdi]
0x14003b2ad  mov     rcx, rdi
0x14003b2b0  mov     rax, [rax+0E0h]
0x14003b2b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003b2bc  mov     ecx, eax
0x14003b2be  mov     [rbp+190h+var_200], eax
0x14003b2c1  mov     ebx, eax
0x14003b2c3  neg     ecx
0x14003b2c5  mov     rcx, [rdi]
0x14003b2c8  sbb     eax, eax
0x14003b2ca  and     eax, 40000h
0x14003b2cf  add     eax, 8040Ch
0x14003b2d4  mov     [rbp+190h+var_1B0], eax
0x14003b2d7  mov     rax, [rcx+80h]
0x14003b2de  mov     rcx, rdi
0x14003b2e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003b2e6  lea     rcx, [rbp+190h+lpAttributeList]
0x14003b2ea  mov     r8d, r13d; int
0x14003b2ed  mov     [rsp+290h+lpEnvironment], rcx; struct _PROC_THREAD_ATTRIBUTE_LIST **
0x14003b2f2  lea     r9, [rbp+190h+ProcessAttributes]; struct _SC_PROCESS_MITIGATION_POLICY *
0x14003b2f6  mov     rcx, [rbp+190h+lpValue]
0x14003b2fa  mov     edx, ebx; unsigned int
0x14003b2fc  mov     qword ptr [rsp+290h+dwCreationFlags], rcx; lpValue
0x14003b301  mov     rcx, [rdi+38h]; unsigned __int16 *
0x14003b305  mov     word ptr [rsp+290h+bInheritHandles], ax; unsigned __int16
0x14003b30a  call    ?ScCreateProcessAttributeList@@YAKPEBGKHPEAU_SC_PROCESS_MITIGATION_POLICY@@G0PEAPEAU_PROC_THREAD_ATTRIBUTE_LIST@@@Z; ScCreateProcessAttributeList(ushort const *,ulong,int,_SC_PROCESS_MITIGATION_POLICY *,ushort,ushort const *,_PROC_THREAD_ATTRIBUTE_LIST * *)
0x14003b30f  mov     ebx, eax
0x14003b311  test    eax, eax
0x14003b313  jz      short loc_14003B339
0x14003b315  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b31c  cmp     rcx, r14
  ... truncated ...
```
