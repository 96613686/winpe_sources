# RChangeServiceConfig2W

- ea: `0x14006b060`
- end: `0x14006c616`
- name: `RChangeServiceConfig2W`
- size: `5558`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `51`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140074670`

## callees

- `0x140002890`
- `0x140003e54`
- `0x140004c58`
- `0x140004c98`
- `0x14000512c`
- `0x140005464`
- `0x1400083f0`
- `0x140008548`
- `0x14000ac50`
- `0x14000bebc`
- `0x14000c220`
- `0x14000c8f0`
- `0x14000ca18`
- `0x14000cf60`
- `0x140013f60`
- `0x140015314`
- `0x140015a28`
- `0x140015b14`
- `0x140016804`
- `0x140016844`
- `0x1400188fc`
- `0x140019014`
- `0x14001c87c`
- `0x14001f99c`
- `0x140020d84`
- `0x14002309c`
- `0x140023c94`
- `0x140026508`
- `0x1400265ac`
- `0x1400282a4`
- `0x14002cfac`
- `0x14002e8c0`
- `0x140030238`
- `0x140032be0`
- `0x140035f80`
- `0x140036ae8`
- `0x140036e10`
- `0x140038698`
- `0x140043354`
- `0x140043dc4`
- `0x1400441f0`
- `0x1400575b0`
- `0x1400644c0`
- `0x14006b060`
- `0x14006c61c`
- `0x14006c798`
- `0x14007ce50`
- `0x14007d0fc`
- `0x140086624`
- `0x140092060`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14006b12a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14006b12a`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x14006c090`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x14006c090`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x14006b157`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x14006b157`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x14006c57e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x14006c57e`
- `ntdll!RtlAcquireResourceExclusive` at `0x14006b196`
- `ntdll!RtlAcquireResourceExclusive` at `0x14006c248`
- `ntdll!RtlAcquireResourceExclusive` at `0x14006b196`
- `ntdll!RtlAcquireResourceExclusive` at `0x14006c248`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x14006b124`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x14006b124`
- `ntdll!RtlReleaseResource` at `0x14006c1b0`
- `ntdll!RtlReleaseResource` at `0x14006c476`
- `ntdll!RtlReleaseResource` at `0x14006c1b0`
- `ntdll!RtlReleaseResource` at `0x14006c476`
- `ntdll!RtlAreAllAccessesGranted` at `0x14006b0fd`
- `ntdll!RtlAreAllAccessesGranted` at `0x14006b6ef`
- `ntdll!RtlAreAllAccessesGranted` at `0x14006b0fd`
- `ntdll!RtlAreAllAccessesGranted` at `0x14006b6ef`
- `ntdll!NtClose` at `0x14006c58e`
- `ntdll!NtClose` at `0x14006c58e`
- `ntdll!RtlNtStatusToDosError` at `0x14006c596`
- `ntdll!RtlNtStatusToDosError` at `0x14006c596`
- `ntdll!RtlFreeHeap` at `0x14006b9f2`
- `ntdll!RtlFreeHeap` at `0x14006bad4`
- `ntdll!RtlFreeHeap` at `0x14006c5b3`
- `ntdll!RtlFreeHeap` at `0x14006b9f2`
- `ntdll!RtlFreeHeap` at `0x14006bad4`
- `ntdll!RtlFreeHeap` at `0x14006c5b3`

## string_xrefs

- `0x14006b348`: `ServiceSidType`
- `0x14006b881`: `FailureCommand`

## pseudocode

```c
__int64 __fastcall RChangeServiceConfig2W(ACCESS_MASK *a1, __int64 a2)
{
  PVOID v4; // r12
  _QWORD *v6; // rcx
  unsigned int v7; // r15d
  __int64 v8; // rdi
  RPC_STATUS v9; // eax
  int v10; // edx
  int v11; // r8d
  char v12; // cl
  __int64 v13; // r14
  unsigned int NumaNodeProcessorMask; // ebx
  PRPC_ASYNC_STATE v15; // rcx
  __int64 v16; // rdx
  ACCESS_MASK v17; // edx
  struct _GROUP_AFFINITY *v18; // rdx
  unsigned int v19; // r8d
  _DWORD *v20; // rsi
  unsigned int v21; // eax
  PRPC_ASYNC_STATE v22; // rcx
  int v23; // edx
  CServiceRecord *v24; // rcx
  CServiceRecord *v25; // rcx
  unsigned int v26; // r9d
  CServiceRecord *v27; // rcx
  unsigned int v28; // r10d
  unsigned int v29; // edx
  _DWORD *v30; // rsi
  _DWORD *v31; // rsi
  __int64 v32; // rax
  PRPC_ASYNC_STATE v33; // rcx
  int v34; // edx
  struct _SERVICE_FAILURE_ACTIONSW *v35; // r14
  SC_ACTION *lpsaActions; // r10
  DWORD cActions; // edx
  int v38; // ebx
  int v39; // r8d
  int v40; // r15d
  DWORD i; // ecx
  __int64 Type; // r9
  PRPC_ASYNC_STATE v43; // rcx
  __int64 v44; // rdx
  PRPC_ASYNC_STATE v45; // rcx
  __int64 v46; // rdx
  const unsigned __int16 *lpRebootMsg; // rdx
  unsigned __int16 v48; // ax
  const unsigned __int16 **v49; // rsi
  unsigned int OptionalString; // eax
  unsigned int v51; // eax
  unsigned __int16 v52; // ax
  unsigned int StringIndirect; // eax
  PVOID v54; // rsi
  const unsigned __int16 *v55; // r8
  unsigned int v56; // eax
  __int64 v57; // r8
  PRPC_ASYNC_STATE *v58; // rdx
  unsigned __int16 *JITReadDisplayName; // rax
  __int64 v60; // r8
  _DWORD *v61; // rsi
  unsigned int v62; // eax
  char *v63; // rsi
  unsigned __int16 *v64; // rsi
  unsigned int RealServiceType; // eax
  __int64 v66; // r8
  unsigned int v67; // r8d
  unsigned int *v68; // rsi
  unsigned int v69; // r14d
  __int64 v70; // r8
  __int64 v71; // rcx
  __int64 v72; // r8
  __int64 v73; // r9
  struct _SERVICE_TRIGGER_INFO *v74; // rsi
  int v75; // r13d
  unsigned int v76; // eax
  unsigned int v77; // eax
  unsigned int v78; // eax
  PVOID v79; // r8
  unsigned int TriggerInfo; // eax
  unsigned int v81; // eax
  __int64 v82; // rdx
  __int64 v83; // r8
  char v84; // si
  unsigned __int16 *v85; // rax
  unsigned int v86; // eax
  PSID v87; // r8
  int v88; // eax
  NTSTATUS v89; // eax
  PVOID *p_P; // [rsp+28h] [rbp-D8h]
  PVOID v91; // [rsp+40h] [rbp-C0h] BYREF
  char v92[8]; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE Handle; // [rsp+50h] [rbp-B0h] BYREF
  int v94; // [rsp+58h] [rbp-A8h]
  unsigned int Pid; // [rsp+5Ch] [rbp-A4h] BYREF
  int v96; // [rsp+60h] [rbp-A0h] BYREF
  struct _SERVICE_TRIGGER_INFO *v97; // [rsp+68h] [rbp-98h] BYREF
  __int64 v98; // [rsp+70h] [rbp-90h] BYREF
  __int128 v99; // [rsp+78h] [rbp-88h] BYREF
  __int64 v100; // [rsp+88h] [rbp-78h]
  int v101; // [rsp+90h] [rbp-70h]
  _QWORD v102[3]; // [rsp+98h] [rbp-68h] BYREF
  int v103; // [rsp+B0h] [rbp-50h]
  PVOID P; // [rsp+B8h] [rbp-48h] BYREF
  _DWORD RpcCallAttributes[32]; // [rsp+C0h] [rbp-40h] BYREF

  Pid = 0;
  v96 = 0;
  memset(RpcCallAttributes, 0, 0x78u);
  Handle = 0;
  v4 = 0;
  v97 = 0;
  v91 = 0;
  ScSetTcpKeepalive();
  if ( ScShutdownInProgress )
    return 1115;
  if ( !(unsigned int)ScIsValidServiceHandle(a1) )
    return 6;
  if ( (unsigned int)ScCheckServiceProtectedProcess(v6, 0) || !RtlAreAllAccessesGranted(a1[2], 2u) )
    return 5;
  v7 = *(_DWORD *)a2;
  v94 = 0;
  LODWORD(P) = v7;
  if ( v7 == 8 )
  {
    RtlAcquireSRWLockExclusive(&g_TriggerRegistrationLock);
    GetCurrentThreadId();
  }
  v8 = *((_QWORD *)a1 + 2);
  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->UserInfo) & 0x100) != 0 )
  {
    v9 = I_RpcBindingInqLocalClientPID(0, &Pid);
    v12 = 0;
    if ( !v9 )
      v12 = Pid;
    WPP_SF_SqLd(WPP_GLOBAL_Control->StubInfo, v10, v11, *(_QWORD *)(v8 + 56), (char)a1, v12, v7);
  }
  RtlAcquireResourceExclusive(&ScServiceRecordLock, 1u);
  v13 = v8 + 312;
  CScmLock::LockAutoExclusive(v8 + 312, v92);
  if ( (*(_DWORD *)(v8 + 52) & 1) == 0 )
  {
    if ( *(char *)(v8 + 80) < 0 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        goto LABEL_22;
      v16 = 12;
LABEL_21:
      WPP_SF_(v15->StubInfo, v16, &WPP_e81ebefcb3343b070146729bdebc64dd_Traceguids);
LABEL_22:
      NumaNodeProcessorMask = 87;
LABEL_23:
      CScmSyncLockExclusive::InternalUnlock((CScmSyncLockExclusive *)v92);
LABEL_24:
      v4 = v91;
      goto LABEL_303;
    }
    if ( (*(_DWORD *)(v8 + 52) & 0x100000) != 0 && v7 != 1 && v7 != 2 && v7 != 3 && v7 != 4 && v7 != 8 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        goto LABEL_22;
      v16 = 13;
      goto LABEL_21;
    }
    if ( (*(_DWORD *)(v8 + 80) & 0x400) != 0 && v7 != 1 )
    {
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        WPP_SF_Sd(
          WPP_GLOBAL_Control->StubInfo,
          14,
          (unsigned int)&WPP_e81ebefcb3343b070146729bdebc64dd_Traceguids,
          *(_QWORD *)(v8 + 56),
          v7);
      goto LABEL_22;
    }
    v17 = 196639;
    if ( v7 != 8 )
      v17 = 131103;
    NumaNodeProcessorMask = CServiceRecord::OpenServiceConfigKey(
                              (CServiceRecord *)v8,
                              v17,
                              (__int64)&WPP_e81ebefcb3343b070146729bdebc64dd_Traceguids,
                              (HKEY *)&Handle);
    if ( NumaNodeProcessorMask )
      goto LABEL_16;
    if ( v7 > 6 )
    {
      switch ( v7 )
      {
        case 7u:
          v68 = *(unsigned int **)(a2 + 8);
          if ( v68 )
          {
            v69 = *v68;
            NumaNodeProcessorMask = ScRegSetValueExW((HKEY)Handle, L"PreshutdownTimeout", v19, 4u, v68, 4u);
            if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
              && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) != 0 )
            {
              WPP_SF_SLd(
                WPP_GLOBAL_Control->StubInfo,
                31,
                (unsigned int)&WPP_e81ebefcb3343b070146729bdebc64dd_Traceguids,
                *(_QWORD *)(v8 + 56),
                *v68,
                NumaNodeProcessorMask);
            }
            if ( v69 > 0x2BF20
              && (unsigned int)dword_1400BA2A0 > 5
              && (unsigned __int8)tlgKeywordOn(&dword_1400BA2A0, 0x400000000000LL, v70) )
            {
              v98 = *(_QWORD *)(v8 + 56);
              p_P = &P;
              LODWORD(P) = v69;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
                v71,
                (__int64)&byte_1400AE6EF,
                v72,
                v73,
                &v98);
            }
            goto LABEL_248;
          }
          break;
        case 8u:
          goto LABEL_249;
        case 9u:
          v64 = *(unsigned __int16 **)(a2 + 8);
          if ( v64 )
          {
            if ( *((_BYTE *)v64 + 2) )
            {
              NumaNodeProcessorMask = ScRegDeleteValue((HKEY)Handle, L"PreferredNode");
              if ( NumaNodeProcessorMask )
              {
                if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                  && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
                {
                  WPP_SF_Sd(
                    WPP_GLOBAL_Control->StubInfo,
                    33,
                    (unsigned int)&WPP_e81ebefcb3343b070146729bdebc64dd_Traceguids,
                    *(_QWORD *)(v8 + 56),
                    NumaNodeProcessorMask);
                }
              }
              else
              {
                (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v8 + 136LL))(v8, 0);
                if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                  && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) != 0 )
                {
                  WPP_SF_S(
                    WPP_GLOBAL_Control->StubInfo,
                    NumaNodeProcessorMask + 32,
                    &WPP_e81ebefcb3343b070146729bdebc64dd_Traceguids,
                    *(_QWORD *)(v8 + 56));
                }
              }
            }
            else if ( (*(_BYTE *)(v8 + 80) & 0x20) != 0 )
            {
              NumaNodeProcessorMask = 87;
              if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
              {
                RealServiceType = CServiceRecord::GetRealServiceType((CServiceRecord *)v8);
                WPP_SF_LdSd(*(_QWORD *)(v66 + 16), *v64, v66, RealServiceType, *v64, *(_QWORD *)(v8 + 56));
              }
            }
            else
            {
              NumaNodeProcessorMask = ScGetNumaNodeProcessorMaskEx(*v64, v18);
              if ( NumaNodeProcessorMask )
              {
                if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                  && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
                {
                  WPP_SF_dSd(
                    WPP_GLOBAL_Control->StubInfo,
                    35,
                    (unsigned int)&WPP_e81ebefcb3343b070146729bdebc64dd_Traceguids,
                    *v64,
                    *(_QWORD *)(v8 + 56),
                    NumaNodeProcessorMask);
                }
              }
              else
              {
                NumaNodeProcessorMask = ScRegSetValueExW((HKEY)Handle, L"PreferredNode", v67, 3u, v64, 2u);
                if ( NumaNodeProcessorMask )
                {
                  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                    && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
                  {
                    WPP_SF_SLd(
                      WPP_GLOBAL_Control->StubInfo,
                      37,
                      (unsigned int)&WPP_e81ebefcb3343b070146729bdebc64dd_Traceguids,
                      *(_QWORD *)(v8 + 56),
                      *v64,
                      NumaNodeProcessorMask);
                  }
                }
                else
                {
                  (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v8 + 136LL))(v8, (unsigned __int16)(*v64 + 1));
                  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                    && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) != 0 )
                  {
                    WPP_SF_Sd(
                      WPP_GLOBAL_Control->StubInfo,
                      NumaNodeProcessorMask + 36,
                      (unsigned int)&WPP_e81ebefcb3343b070146729bdebc64dd_Traceguids,
                      *(_QWORD *)(v8 + 56),
                      *v64);
                  }
                }
              }
            }
            goto LABEL_249;
          }
          break;
        case 0xBu:
          v63 = *(char **)(a2 + 8);
          if ( !v63 )
            goto LABEL_50;
          if ( *v63 == 1 )
          {
            if ( *(_QWORD *)(v8 + 136) )
            {
              NumaNodeProcessorMask = 87;
              v33 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
              {
                goto LABEL_23;
              }
              v34 = 38;
              goto LABEL_91;
            }
          }
          else if ( *v63 )
          {
            goto LABEL_55;
          }
          v21 = ScWriteServiceManagedAccount(Handle, *v63 != 0);
          NumaNodeProcessorMask = v21;
          if ( !v21 )
          {
            if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
              && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) != 0 )
            {
              WPP_SF_Sd(
                WPP_GLOBAL_Control->StubInfo,
                40,
                (unsigned int)&WPP_e81ebefcb3343b070146729bdebc64dd_Traceguids,
                *(_QWORD *)(v8 + 56),
                *v63);
            }
            (*(void (__fastcall **)(__int64, bool))(*(_QWORD *)v8 + 208LL))(v8, *v63 != 0);
            goto LABEL_249;
          }
          v22 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
          {
            goto LABEL_23;
          }
          v23 = 39;
          goto LABEL_85;
        case 0xCu:
          v61 = *(_DWORD **)(a2 + 8);
          if ( !v61 )
            goto LABEL_50;
          if ( *v61 >= 5u || (*(_BYTE *)(v8 + 80) & 0x30) == 0 )
            goto LABEL_55;
          if ( *v61 )
            v62 = ScRegSetValueExW((HKEY)Handle, L"LaunchProtected", v19, 4u, v61, 4u);
          else
            v62 = ScRegDeleteValue((HKEY)Handle, L"LaunchProtected");
          NumaNodeProcessorMask = v62;
          if ( v62 )
          {
            if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
              && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
            {
              WPP_SF_Sd(
                WPP_GLOBAL_Control->StubInfo,
                41,
                (unsigned int)&WPP_e81ebefcb3343b070146729bdebc64dd_Traceguids,
                *(_QWORD *)(v8 + 56),
                v62);
            }
            goto LABEL_23;
          }
          if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) != 0 )
          {
            WPP_SF_Sd(
              WPP_GLOBAL_Control->StubInfo,
              42,
              (unsigned int)&WPP_e81ebefcb3343b070146729bdebc64dd_Traceguids,
              *(_QWORD *)(v8 + 56),
              *v61);
          }
          *(_DWORD *)(v8 + 392) = *v61;
          goto LABEL_249;
        default:
LABEL_186:
          NumaNodeProcessorMask = 124;
          goto LABEL_249;
      }
    }
    else
    {
      switch ( v7 )
      {
        case 6u:
          v60 = *(_QWORD *)(a2 + 8);
          if ( v60 )
          {
            NumaNodeProcessorMask = ScWritePrivileges(
                                      (HKEY)Handle,
                                      (struct CServiceRecord *)v8,
                                      *(unsigned __int16 **)(v60 + 8),
                                      *(_DWORD *)v60);
            goto LABEL_249;
          }
          break;
        case 1u:
          v49 = *(const unsigned __int16 ***)(a2 + 8);
          P = 0;
          if ( v49 )
          {
            OptionalString = ScReadOptionalString((HKEY)Handle, L"Description", (unsigned __int16 **)&P, 0);
            NumaNodeProcessorMask = OptionalString;
            if ( OptionalString )
            {
              if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
              {
                WPP_SF_d(
                  WPP_GLOBAL_Control->StubInfo,
                  15,
                  &WPP_e81ebefcb3343b070146729bdebc64dd_Traceguids,
                  OptionalString);
              }
              goto LABEL_23;
            }
            v51 = ScWriteOptionalString((HKEY)Handle, L"Description", *v49);
            NumaNodeProcessorMask = v51;
            if ( v51 )
            {
              if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
              {
                WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 16, &WPP_e81ebefcb3343b070146729bdebc64dd_Traceguids, v51);
              }
              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
              goto LABEL_23;
            }
            v52 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 48LL))(v8);
            StringIndirect = ScReadStringIndirect((HKEY)Handle, L"Description", (unsigned __int16 *)*v49, v52, 0);
            v54 = P;
            NumaNodeProcessorMask = StringIndirect;
            if ( StringIndirect )
            {
              v55 = (const unsigned __int16 *)&dword_14009C804;
              if ( P )
                v55 = (const unsigned __int16 *)P;
              v56 = ScWriteOptionalString((HKEY)Handle, L"Description", v55);
              if ( v56 )
              {
                v58 = &WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control )
                {
                  v57 = 1;
                  if ( (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
                    WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 17, &WPP_e81ebefcb3343b070146729bdebc64dd_Traceguids, v56);
                }
                JITReadDisplayName = CServiceRecord::GetJITReadDisplayName((CServiceRecord *)v8, (__int64)v58, v57);
                ScLogServiceEvent(0x25u, JITReadDisplayName, 0x59u, 0, 0, 0);
              }
            }
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v54);
            goto LABEL_249;
          }
          break;
        case 2u:
          v35 = *(struct _SERVICE_FAILURE_ACTIONSW **)(a2 + 8);
          if ( !v35 )
          {
            NumaNodeProcessorMask = 0;
LABEL_248:
            v13 = v8 + 312;
            goto LABEL_249;
          }
          lpsaActions = v35->lpsaActions;
          if ( lpsaActions )
          {
            cActions = v35->cActions;
            if ( cActions )
            {
              if ( (*(_BYTE *)(v8 + 80) & 0x30) == 0 )
              {
                NumaNodeProcessorMask = 1080;
                goto LABEL_248;
              }
              v38 = 0;
              v39 = 0;
              v40 = 0;
              for ( i = 0; i < cActions; ++i )
              {
                Type = (unsigned int)lpsaActions[i].Type;
                switch ( (_DWORD)Type )
                {
                  case 1:
                  case 4:
                    v39 = 1;
                    break;
                  case 2:
                    v38 = 1;
                    break;
                  case 3:
                    v40 = 1;
                    break;
                  default:
                    if ( (_DWORD)Type )
                    {
                      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                        && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
                      {
                        WPP_SF_d(
                          WPP_GLOBAL_Control->StubInfo,
                          18,
                          &WPP_e81ebefcb3343b070146729bdebc64dd_Traceguids,
                          Type);
                      }
                      NumaNodeProcessorMask = 87;
                      CScmSyncLockExclusive::InternalUnlock((CScmSyncLockExclusive *)v92);
                      v7 = (unsigned int)P;
                      goto LABEL_24;
                    }
                    break;
                }
              }
              if ( v39 && !RtlAreAllAccessesGranted(a1[2], 0x10u) )
              {
                v43 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                  && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
                {
                  v44 = 19;
                  goto LABEL_126;
                }
                goto LABEL_127;
              }
              if ( v38 )
              {
                if ( (*(_DWORD *)(v8 + 52) & 0x100000) != 0 )
                {
                  v45 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                    && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
                  {
                    v46 = 20;
                    goto LABEL_134;
                  }
                  goto LABEL_135;
                }
                if ( (int)ScPrivilegeCheckAndAudit(19, (unsigned __int64)a1, 2u) < 0 )
                {
                  v43 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                    && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
                  {
                    v44 = 21;
LABEL_126:
                    WPP_SF_(v43->StubInfo, v44, &WPP_e81ebefcb3343b070146729bdebc64dd_Traceguids);
                  }
LABEL_127:
                  NumaNodeProcessorMask = 5;
                  goto LABEL_128;
                }
              }
              if ( v40 && (*(_DWORD *)(v8 + 52) & 0x100000) != 0 )
              {
                v45 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                  && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
                {
                  v46 = 22;
LABEL_134:
                  WPP_SF_(v45->StubInfo, v46, &WPP_e81ebefcb3343b070146729bdebc64dd_Traceguids);
                }
LABEL_135:
                NumaNodeProcessorMask = 87;
LABEL_128:
                v7 = *(_DWORD *)a2;
                goto LABEL_248;
              }
              P = 0;
              NumaNodeProcessorMask = ScGetImageFileName((HKEY)Handle, 0, (unsigned __int16 **)&P);
              if ( NumaNodeProcessorMask )
              {
                if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                  && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
                {
                  WPP_SF_d(
                    WPP_GLOBAL_Control->StubInfo,
                    23,
                    &WPP_e81ebefcb3343b070146729bdebc64dd_Traceguids,
                    NumaNodeProcessorMask);
                }
                goto LABEL_149;
              }
              if ( (unsigned int)ScImagePathsMatch((const unsigned __int16 *)P, ScGlobalThisExePath) )
              {
                NumaNodeProcessorMask = 1081;
LABEL_149:
                CHeapPtr<_SERVICE_FAILURE_ACTIONS_WOW64 *>::~CHeapPtr<_SERVICE_FAILURE_ACTIONS_WOW64 *>(&P);
                goto LABEL_128;
              }
              CHeapPtr<_SERVICE_FAILURE_ACTIONS_WOW64 *>::~CHeapPtr<_SERVICE_FAILURE_ACTIONS_WOW64 *>(&P);
              v7 = *(_DWORD *)a2;
            }
          }
          lpRebootMsg = v35->lpRebootMsg;
          v102[0] = Handle;
          *(_QWORD *)&v99 = Handle;
          *((_QWORD *)&v99 + 1) = L"FailureCommand";
          v102[1] = L"RebootMessage";
          v102[2] = 0;
          v103 = 0;
          v100 = 0;
          v101 = 0;
          NumaNodeProcessorMask = CUpdateOptionalString::Update((CUpdateOptionalString *)v102, lpRebootMsg);
          if ( !NumaNodeProcessorMask )
          {
            v48 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 48LL))(v8);
            NumaNodeProcessorMask = ScReadStringIndirect((HKEY)Handle, L"RebootMessage", v35->lpRebootMsg, v48, 0);
            if ( !NumaNodeProcessorMask )
            {
              NumaNodeProcessorMask = CUpdateOptionalString::Update((CUpdateOptionalString *)&v99, v35->lpCommand);
              if ( !NumaNodeProcessorMask )
              {
                NumaNodeProcessorMask = ScWriteFailureActions((HKEY)Handle, v35);
                if ( !NumaNodeProcessorMask )
                {
                  v103 = 0;
                  v101 = 0;
                }
              }
            }
          }
          CUpdateOptionalString::~CUpdateOptionalString((CUpdateOptionalString *)&v99);
          CUpdateOptionalString::~CUpdateOptionalString((CUpdateOptionalString *)v102);
          goto LABEL_248;
        case 3u:
          v31 = *(_DWORD **)(a2 + 8);
          if ( !v31 )
            goto LABEL_50;
          if ( *v31 != 1 )
          {
            if ( *v31 )
              goto LABEL_55;
            goto LABEL_81;
          }
          v32 = *(_QWORD *)(v8 + 136);
          if ( !v32 || *(_DWORD *)(v32 + 28) == -1 )
          {
LABEL_81:
            v21 = ScRegSetValueExW((HKEY)Handle, L"DelayedAutostart", v19, 4u, v31, 4u);
            NumaNodeProcessorMask = v21;
            if ( !v21 )
            {
              if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) != 0 )
              {
                WPP_SF_Sd(
                  WPP_GLOBAL_Control->StubInfo,
                  26,
                  (unsigned int)&WPP_e81ebefcb3343b070146729bdebc64dd_Traceguids,
                  *(_QWORD *)(v8 + 56),
                  *v31);
              }
              if ( *v31 == 1 )
              {
                if ( (*(_DWORD *)(v8 + 52) & 8) == 0 )
                  CServiceRecord::SetStatusFlag((CServiceRecord *)v8, 0x10u);
                v29 = 8;
                v27 = (CServiceRecord *)v8;
                goto LABEL_66;
              }
              v29 = 8;
              v27 = (CServiceRecord *)v8;
              goto LABEL_100;
            }
            v22 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
              || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
            {
              goto LABEL_23;
            }
            v23 = 25;
LABEL_85:
            WPP_SF_Sd(
              v22->StubInfo,
              v23,
              (unsigned int)&WPP_e81ebefcb3343b070146729bdebc64dd_Traceguids,
              *(_QWORD *)(v8 + 56),
              v21);
            goto LABEL_23;
          }
          NumaNodeProcessorMask = 87;
          v33 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
          {
            goto LABEL_23;
          }
          v34 = 24;
LABEL_91:
          WPP_SF_Sd(
            v33->StubInfo,
            v34,
            (unsigned int)&WPP_e81ebefcb3343b070146729bdebc64dd_Traceguids,
            *(_QWORD *)(v8 + 56),
            87);
          goto LABEL_23;
        case 4u:
          v30 = *(_DWORD **)(a2 + 8);
          if ( !v30 )
            goto LABEL_50;
          if ( *v30 > 1u )
            goto LABEL_55;
          v21 = ScRegSetValueExW((HKEY)Handle, L"FailureActionsOnNonCrashFailures", 1u, 4u, v30, 4u);
          NumaNodeProcessorMask = v21;
          if ( v21 )
          {
            v22 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
              || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
            {
              goto LABEL_23;
            }
            v23 = 27;
            goto LABEL_85;
          }
          if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) != 0 )
          {
            WPP_SF_Sd(
              WPP_GLOBAL_Control->StubInfo,
              28,
              (unsigned int)&WPP_e81ebefcb3343b070146729bdebc64dd_Traceguids,
              *(_QWORD *)(v8 + 56),
              *v30);
          }
          v29 = 32;
          v27 = (CServiceRecord *)v8;
          if ( *v30 == 1 )
            goto LABEL_66;
LABEL_100:
          CServiceRecord::ClearStatusFlag(v27, v29);
          goto LABEL_249;
        case 5u:
          v20 = *(_DWORD **)(a2 + 8);
          if ( !v20 )
          {
LABEL_50:
            NumaNodeProcessorMask = 0;
LABEL_51:
            CScmSyncLockExclusive::InternalUnlock((CScmSyncLockExclusive *)v92);
LABEL_302:
            v4 = v91;
            goto LABEL_303;
          }
          if ( (*v20 & 0xFFFFFFFC) != 0 || *v20 == 2 || (*(_BYTE *)(v8 + 80) & 0x30) == 0 )
          {
LABEL_55:
            NumaNodeProcessorMask = 87;
            goto LABEL_51;
          }
          v21 = ScRegSetValueExW((HKEY)Handle, L"ServiceSidType", v19, 4u, v20, 4u);
          NumaNodeProcessorMask = v21;
          if ( v21 )
          {
            v22 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
              || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
            {
              goto LABEL_23;
            }
            v23 = 29;
            goto LABEL_85;
          }
          if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) != 0 )
          {
            WPP_SF_Sd(
              WPP_GLOBAL_Control->StubInfo,
              30,
              (unsigned int)&WPP_e81ebefcb3343b070146729bdebc64dd_Traceguids,
              *(_QWORD *)(v8 + 56),
              *v20);
          }
          CServiceRecord::ClearStatusFlag((CServiceRecord *)v8, 64);
          CServiceRecord::ClearStatusFlag(v24, 256);
          if ( ((unsigned __int8)(v26 - 63) & *(_BYTE *)v20) != 0 )
          {
            CServiceRecord::SetStatusFlag(v25, v26);
            if ( *v20 == 3 )
            {
              v29 = v28;
LABEL_66:
              CServiceRecord::SetStatusFlag(v27, v29);
            }
          }
LABEL_249:
          CScmSyncLockExclusive::InternalUnlock((CScmSyncLockExclusive *)v92);
          if ( v7 != 8 )
          {
            v94 = 0;
            if ( NumaNodeProcessorMask )
              goto LABEL_302;
LABEL_301:
            CScmLock::LockAutoShared(v13, &v98);
            ScNotifyServicePropertyChange((struct CServiceRecord *)v8);
            Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockShared *)&v98);
            goto LABEL_302;
          }
          v74 = *(struct _SERVICE_TRIGGER_INFO **)(a2 + 8);
          v75 = 0;
          P = 0;
          if ( !v74 )
          {
            NumaNodeProcessorMask = 0;
            goto LABEL_301;
          }
          v76 = ScValidateTriggerInfo(*(const unsigned __int16 **)(v8 + 56), v74, &v96);
          NumaNodeProcessorMask = v76;
          if ( v76 )
          {
            if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
              && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
            {
              WPP_SF_Sd(
                WPP_GLOBAL_Control->StubInfo,
                43,
                (unsigned int)&WPP_e81ebefcb3343b070146729bdebc64dd_Traceguids,
                *(_QWORD *)(v8 + 56),
                v76);
            }
            goto LABEL_24;
          }
          RpcCallAttributes[0] = 3;
          RpcCallAttributes[1] = 32;
          v77 = RpcServerInqCallAttributesW(0, RpcCallAttributes);
          NumaNodeProcessorMask = v77;
          if ( v77 )
          {
            if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
              && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
            {
              WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 44, &WPP_e81ebefcb3343b070146729bdebc64dd_Traceguids, v77);
            }
            goto LABEL_24;
          }
          if ( RpcCallAttributes[15] != 1 && v96 )
          {
            NumaNodeProcessorMask = 87;
            if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
              && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
            {
              WPP_SF_(WPP_GLOBAL_Control->StubInfo, 45, &WPP_e81ebefcb3343b070146729bdebc64dd_Traceguids);
            }
            goto LABEL_24;
          }
          if ( (*(_DWORD *)(v8 + 52) & 0x800) != 0
            || !g_BootTriggerRegistrationComplete
            || (unsigned int)ScSuppressServiceStartInSafeMode((struct CServiceRecord *)v8) )
          {
            v4 = v91;
          }
          else
          {
            CScmLock::LockAutoExclusive(v13, v92);
            v21 = ScGetServiceChangeNotificationName((struct CServiceRecord *)v8, 1, (struct _WNF_STATE_NAME *)&P);
            NumaNodeProcessorMask = v21;
            if ( v21 )
            {
              v22 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
              {
                goto LABEL_23;
              }
              v23 = 46;
              goto LABEL_85;
            }
            CScmSyncLockExclusive::InternalUnlock((CScmSyncLockExclusive *)v92);
            RtlReleaseResource(&ScServiceRecordLock);
            v78 = ScResolveServiceAccount(
                    *(struct _SERVICE_CONFIG_ROOT **)(v8 + 216),
                    *(unsigned __int16 **)(v8 + 56),
                    &v91);
            if ( v78
              && WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
              && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
            {
              WPP_SF_Sd(
                WPP_GLOBAL_Control->StubInfo,
                47,
                (unsigned int)&WPP_e81ebefcb3343b070146729bdebc64dd_Traceguids,
                *(_QWORD *)(v8 + 56),
                v78);
            }
            v4 = v91;
            v79 = v91;
            if ( !v91 )
              v79 = LocalSystemSid;
            NumaNodeProcessorMask = ((__int64 (__fastcall *)(struct _SERVICE_TRIGGER_INFO *, _QWORD, PVOID, PVOID *, _DWORD, PVOID *))g_pScExtFunctionPointers[10])(
                                      v74,
                                      *(_QWORD *)(v8 + 56),
                                      v79,
                                      &P,
                                      0,
                                      p_P);
            RtlAcquireResourceExclusive(&ScServiceRecordLock, 1u);
            if ( NumaNodeProcessorMask )
            {
              if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
              {
                WPP_SF_Sd(
                  WPP_GLOBAL_Control->StubInfo,
                  48,
                  (unsigned int)&WPP_e81ebefcb3343b070146729bdebc64dd_Traceguids,
                  *(_QWORD *)(v8 + 56),
                  NumaNodeProcessorMask);
              }
              goto LABEL_282;
            }
            v75 = 1;
            v94 = 1;
            CScmSyncLockExclusive::InternalUnlock((CScmSyncLockExclusive *)v92);
          }
          CScmLock::LockAutoExclusive(v13, v92);
          TriggerInfo = ScGetTriggerInfo(
                          *(struct _SERVICE_CONFIG_ROOT **)(v8 + 216),
                          *(const unsigned __int16 **)(v8 + 56),
                          (HKEY)Handle,
                          *(_DWORD *)(v8 + 80),
                          1,
                          (*(_DWORD *)(v8 + 168) >> 1) & 1,
                          &v97);
          NumaNodeProcessorMask = TriggerInfo;
          if ( TriggerInfo )
          {
            if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
              && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
            {
              WPP_SF_Sd(
                WPP_GLOBAL_Control->StubInfo,
                49,
                (unsigned int)&WPP_e81ebefcb3343b070146729bdebc64dd_Traceguids,
                *(_QWORD *)(v8 + 56),
                TriggerInfo);
            }
          }
          else
          {
            NumaNodeProcessorMask = ScSaveTriggerInfo(
                                      *(struct _SERVICE_CONFIG_ROOT **)(v8 + 216),
                                      *(const unsigned __int16 **)(v8 + 56),
                                      (HKEY)Handle,
                                      *(_DWORD *)(v8 + 80),
                                      (*(_DWORD *)(v8 + 168) >> 1) & 1,
                                      v74);
            if ( !NumaNodeProcessorMask )
            {
              if ( v75 )
              {
                if ( v74->cTriggers )
                  CServiceRecord::SetStatusFlag((CServiceRecord *)v8, 0x400u);
                else
                  CServiceRecord::ClearStatusFlag((CServiceRecord *)v8, 1024);
              }
              CScmSyncLockExclusive::InternalUnlock((CScmSyncLockExclusive *)v92);
              goto LABEL_301;
            }
            v81 = ScSaveTriggerInfo(
                    *(struct _SERVICE_CONFIG_ROOT **)(v8 + 216),
                    *(const unsigned __int16 **)(v8 + 56),
                    (HKEY)Handle,
                    *(_DWORD *)(v8 + 80),
                    (*(_DWORD *)(v8 + 168) >> 1) & 1,
                    v97);
            v84 = v81;
            if ( v81 )
            {
              v85 = CServiceRecord::GetJITReadDisplayName((CServiceRecord *)v8, v82, v83);
              ScLogServiceEvent(0x25u, v85, 0x5Au, 0, 0, 0);
            }
            if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
              && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
            {
              WPP_SF_SLd(
                WPP_GLOBAL_Control->StubInfo,
                50,
                (unsigned int)&WPP_e81ebefcb3343b070146729bdebc64dd_Traceguids,
                *(_QWORD *)(v8 + 56),
                NumaNodeProcessorMask,
                v84);
            }
          }
LABEL_282:
          CScmSyncLockExclusive::InternalUnlock((CScmSyncLockExclusive *)v92);
          goto LABEL_303;
        default:
          goto LABEL_186;
      }
    }
    NumaNodeProcessorMask = 0;
    goto LABEL_249;
  }
  CServiceRecord::LogPidsWithOpenHandles((CServiceRecord *)v8);
  NumaNodeProcessorMask = 1072;
LABEL_16:
  CScmSyncLockExclusive::InternalUnlock((CScmSyncLockExclusive *)v92);
LABEL_303:
  RtlReleaseResource(&ScServiceRecordLock);
  if ( v97 )
    ScFreeTriggerInfo(&v97);
  if ( NumaNodeProcessorMask && v94 )
  {
    v100 = 0;
    v99 = 0;
    if ( !v4 )
    {
      v86 = ScResolveServiceAccount(*(struct _SERVICE_CONFIG_ROOT **)(v8 + 216), *(unsigned __int16 **)(v8 + 56), &v91);
      if ( v86
        && WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      {
        WPP_SF_Sd(
          WPP_GLOBAL_Control->StubInfo,
          51,
          (unsigned int)&WPP_e81ebefcb3343b070146729bdebc64dd_Traceguids,
          *(_QWORD *)(v8 + 56),
          v86);
      }
      v4 = v91;
    }
    v87 = v4;
    if ( !v4 )
      v87 = LocalSystemSid;
    v88 = ((__int64 (__fastcall *)(__int128 *, _QWORD, PSID, _QWORD, _DWORD))g_pScExtFunctionPointers[10])(
            &v99,
            *(_QWORD *)(v8 + 56),
            v87,
            0,
            0);
    if ( v88 )
    {
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        WPP_SF_Sd(
          WPP_GLOBAL_Control->StubInfo,
          52,
          (unsigned int)&WPP_e81ebefcb3343b070146729bdebc64dd_Traceguids,
          *(_QWORD *)(v8 + 56),
          v88);
    }
    else
    {
      CServiceRecord::ClearStatusFlag((CServiceRecord *)v8, 1024);
    }
  }
  if ( v7 == 8 )
    RtlReleaseSRWLockExclusive(&g_TriggerRegistrationLock);
  if ( Handle )
  {
    v89 = NtClose(Handle);
    RtlNtStatusToDosError(v89);
  }
  if ( v4 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->UserInfo) & 0x100) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 53, &WPP_e81ebefcb3343b070146729bdebc64dd_Traceguids, NumaNodeProcessorMask);
  }
  return NumaNodeProcessorMask;
}

```

## disassembly

```asm
0x14006b060  mov     [rsp-8+arg_10], rbx
0x14006b065  push    rbp
0x14006b066  push    rsi
0x14006b067  push    rdi
0x14006b068  push    r12
0x14006b06a  push    r13
0x14006b06c  push    r14
0x14006b06e  push    r15
0x14006b070  lea     rbp, [rsp-50h]
0x14006b075  sub     rsp, 150h
0x14006b07c  mov     rax, cs:__security_cookie
0x14006b083  xor     rax, rsp
0x14006b086  mov     [rbp+80h+var_40], rax
0x14006b08a  xor     ebx, ebx
0x14006b08c  mov     r13, rdx
0x14006b08f  mov     rsi, rcx
0x14006b092  mov     [rsp+180h+Pid], ebx
0x14006b096  xor     edx, edx; Val
0x14006b098  mov     [rsp+180h+var_120], ebx
0x14006b09c  lea     rcx, [rbp+80h+RpcCallAttributes]; void *
0x14006b0a0  lea     r8d, [rbx+78h]; Size
0x14006b0a4  call    memset
0x14006b0a9  mov     [rsp+180h+Handle], rbx
0x14006b0ae  mov     r12d, ebx
0x14006b0b1  mov     [rsp+180h+var_118], rbx
0x14006b0b6  mov     [rsp+180h+var_140], rbx
0x14006b0bb  call    ?ScSetTcpKeepalive@@YAXXZ; ScSetTcpKeepalive(void)
0x14006b0c0  cmp     cs:?ScShutdownInProgress@@3KA, ebx; ulong ScShutdownInProgress
0x14006b0c6  jz      short loc_14006B0D2
0x14006b0c8  mov     eax, 45Bh
0x14006b0cd  jmp     loc_14006C5EF
0x14006b0d2  mov     rcx, rsi; void *
0x14006b0d5  call    ?ScIsValidServiceHandle@@YAHPEAX@Z; ScIsValidServiceHandle(void *)
0x14006b0da  test    eax, eax
0x14006b0dc  jnz     short loc_14006B0E8
0x14006b0de  mov     eax, 6
0x14006b0e3  jmp     loc_14006C5EF
0x14006b0e8  xor     edx, edx; unsigned __int8
0x14006b0ea  call    ?ScCheckServiceProtectedProcess@@YAKPEAXE@Z; ScCheckServiceProtectedProcess(void *,uchar)
0x14006b0ef  test    eax, eax
0x14006b0f1  jnz     loc_14006C5EA
0x14006b0f7  mov     ecx, [rsi+8]; GrantedAccess
0x14006b0fa  lea     edx, [rax+2]; DesiredAccess
0x14006b0fd  call    cs:__imp_RtlAreAllAccessesGranted
0x14006b103  test    al, al
0x14006b105  jz      loc_14006C5EA
0x14006b10b  mov     r15d, [r13+0]
0x14006b10f  mov     [rsp+180h+var_128], ebx
0x14006b113  mov     dword ptr [rbp+80h+P], r15d
0x14006b117  cmp     r15d, 8
0x14006b11b  jnz     short loc_14006B130
0x14006b11d  lea     rcx, g_TriggerRegistrationLock
0x14006b124  call    cs:__imp_RtlAcquireSRWLockExclusive
0x14006b12a  call    cs:__imp_GetCurrentThreadId
0x14006b130  mov     rdi, [rsi+10h]
0x14006b134  mov     rax, cs:WPP_GLOBAL_Control
0x14006b13b  lea     rcx, WPP_GLOBAL_Control
0x14006b142  cmp     rax, rcx
0x14006b145  jz      short loc_14006B188
0x14006b147  test    dword ptr [rax+1Ch], 100h
0x14006b14e  jz      short loc_14006B188
0x14006b150  lea     rdx, [rsp+180h+Pid]; Pid
0x14006b155  xor     ecx, ecx; Binding
0x14006b157  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x14006b15d  mov     r9, [rdi+38h]
0x14006b161  mov     ecx, ebx
0x14006b163  test    eax, eax
0x14006b165  mov     dword ptr [rsp+180h+var_150], r15d
0x14006b16a  cmovz   ecx, [rsp+180h+Pid]
0x14006b16f  mov     dword ptr [rsp+180h+var_158], ecx
0x14006b173  mov     rcx, cs:WPP_GLOBAL_Control
0x14006b17a  mov     [rsp+180h+var_160], rsi
0x14006b17f  mov     rcx, [rcx+10h]
0x14006b183  call    WPP_SF_SqLd
0x14006b188  mov     ebx, 1
0x14006b18d  lea     rcx, ?ScServiceRecordLock@@3VCServiceRecordLock@@A; Resource
0x14006b194  mov     dl, bl; Wait
0x14006b196  call    cs:__imp_RtlAcquireResourceExclusive
0x14006b19c  lea     r14, [rdi+138h]
0x14006b1a3  mov     rcx, r14
0x14006b1a6  lea     rdx, [rsp+180h+var_138]
0x14006b1ab  call    ?LockAutoExclusive@CScmLock@@QEAA?AVCScmSyncLockExclusive@@XZ; CScmLock::LockAutoExclusive(void)
0x14006b1b0  mov     eax, [rdi+34h]
0x14006b1b3  lea     r8, WPP_e81ebefcb3343b070146729bdebc64dd_Traceguids; int
0x14006b1ba  test    bl, al
0x14006b1bc  jz      short loc_14006B1DA
0x14006b1be  mov     rcx, rdi; this
0x14006b1c1  call    ?LogPidsWithOpenHandles@CServiceRecord@@QEAAXXZ; CServiceRecord::LogPidsWithOpenHandles(void)
0x14006b1c6  mov     ebx, 430h
0x14006b1cb  lea     rcx, [rsp+180h+var_138]; this
0x14006b1d0  call    ?InternalUnlock@CScmSyncLockExclusive@@IEAAXXZ; CScmSyncLockExclusive::InternalUnlock(void)
0x14006b1d5  jmp     loc_14006C468
0x14006b1da  test    byte ptr [rdi+50h], 80h
0x14006b1de  jz      short loc_14006B21F
0x14006b1e0  mov     rcx, cs:WPP_GLOBAL_Control
0x14006b1e7  lea     r14, WPP_GLOBAL_Control
0x14006b1ee  cmp     rcx, r14
0x14006b1f1  jz      short loc_14006B206
0x14006b1f3  test    [rcx+1Ch], bl
0x14006b1f6  jz      short loc_14006B206
0x14006b1f8  mov     edx, 0Ch
0x14006b1fd  mov     rcx, [rcx+10h]
0x14006b201  call    WPP_SF_
0x14006b206  mov     ebx, 57h ; 'W'
0x14006b20b  lea     rcx, [rsp+180h+var_138]; this
0x14006b210  call    ?InternalUnlock@CScmSyncLockExclusive@@IEAAXXZ; CScmSyncLockExclusive::InternalUnlock(void)
0x14006b215  mov     r12, [rsp+180h+var_140]
0x14006b21a  jmp     loc_14006C46F
0x14006b21f  mov     eax, [rdi+34h]
0x14006b222  bt      eax, 14h
0x14006b226  jnb     short loc_14006B25F
0x14006b228  mov     eax, r15d
0x14006b22b  sub     eax, ebx
0x14006b22d  jz      short loc_14006B25F
0x14006b22f  sub     eax, ebx
0x14006b231  jz      short loc_14006B25F
0x14006b233  sub     eax, ebx
0x14006b235  jz      short loc_14006B25F
0x14006b237  sub     eax, ebx
0x14006b239  jz      short loc_14006B25F
0x14006b23b  cmp     eax, 4
0x14006b23e  jz      short loc_14006B25F
0x14006b240  mov     rcx, cs:WPP_GLOBAL_Control
0x14006b247  lea     r14, WPP_GLOBAL_Control
0x14006b24e  cmp     rcx, r14
0x14006b251  jz      short loc_14006B206
0x14006b253  test    [rcx+1Ch], bl
0x14006b256  jz      short loc_14006B206
0x14006b258  mov     edx, 0Dh
0x14006b25d  jmp     short loc_14006B1FD
0x14006b25f  test    dword ptr [rdi+50h], 400h
0x14006b266  jz      short loc_14006B2A1
0x14006b268  cmp     r15d, ebx
0x14006b26b  jz      short loc_14006B2A1
0x14006b26d  mov     rcx, cs:WPP_GLOBAL_Control
0x14006b274  lea     r14, WPP_GLOBAL_Control
0x14006b27b  cmp     rcx, r14
0x14006b27e  jz      short loc_14006B206
0x14006b280  test    [rcx+1Ch], bl
0x14006b283  jz      short loc_14006B206
0x14006b285  mov     r9, [rdi+38h]
0x14006b289  mov     edx, 0Eh
0x14006b28e  mov     rcx, [rcx+10h]
0x14006b292  mov     dword ptr [rsp+180h+var_160], r15d
0x14006b297  call    WPP_SF_Sd
0x14006b29c  jmp     loc_14006B206
0x14006b2a1  mov     edx, 3001Fh
0x14006b2a6  lea     r9, [rsp+180h+Handle]; HKEY *
0x14006b2ab  mov     eax, 2001Fh
0x14006b2b0  cmp     r15d, 8
0x14006b2b4  mov     rcx, rdi; this
0x14006b2b7  cmovnz  edx, eax; unsigned int
0x14006b2ba  call    ?OpenServiceConfigKey@CServiceRecord@@QEAAKKHPEAPEAUHKEY__@@@Z; CServiceRecord::OpenServiceConfigKey(ulong,int,HKEY__ * *)
0x14006b2bf  xor     r11d, r11d
0x14006b2c2  mov     ebx, eax
0x14006b2c4  test    eax, eax
0x14006b2c6  jnz     loc_14006B1CB
0x14006b2cc  lea     r12d, [rax+57h]
0x14006b2d0  cmp     r15d, 6
0x14006b2d4  ja      loc_14006BB07
0x14006b2da  jz      loc_14006BADF
0x14006b2e0  mov     eax, r15d
0x14006b2e3  sub     eax, 1
0x14006b2e6  jz      loc_14006B923
0x14006b2ec  sub     eax, 1
0x14006b2ef  jz      loc_14006B618
0x14006b2f5  sub     eax, 1
0x14006b2f8  jz      loc_14006B4D9
0x14006b2fe  sub     eax, 1
0x14006b301  jz      loc_14006B41D
0x14006b307  cmp     eax, 1
0x14006b30a  jnz     loc_14006BB33
0x14006b310  mov     rsi, [r13+8]
0x14006b314  test    rsi, rsi
0x14006b317  jnz     short loc_14006B32B
0x14006b319  mov     ebx, r11d
0x14006b31c  lea     rcx, [rsp+180h+var_138]; this
0x14006b321  call    ?InternalUnlock@CScmSyncLockExclusive@@IEAAXXZ; CScmSyncLockExclusive::InternalUnlock(void)
0x14006b326  jmp     loc_14006C463
0x14006b32b  test    dword ptr [rsi], 0FFFFFFFCh
0x14006b331  jnz     short loc_14006B33E
0x14006b333  cmp     dword ptr [rsi], 2
0x14006b336  jz      short loc_14006B33E
0x14006b338  test    byte ptr [rdi+50h], 30h
0x14006b33c  jnz     short loc_14006B343
0x14006b33e  mov     ebx, r12d
0x14006b341  jmp     short loc_14006B31C
0x14006b343  mov     rcx, [rsp+180h+Handle]; KeyHandle
0x14006b348  lea     rdx, aServicesidtype; "ServiceSidType"
0x14006b34f  mov     eax, 4
0x14006b354  mov     dword ptr [rsp+180h+var_158], eax; unsigned int
0x14006b358  mov     r9d, eax; unsigned int
0x14006b35b  mov     [rsp+180h+var_160], rsi; void *
0x14006b360  call    ?ScRegSetValueExW@@YAKPEAUHKEY__@@PEBGKKPEAXK@Z; ScRegSetValueExW(HKEY__ *,ushort const *,ulong,ulong,void *,ulong)
0x14006b365  mov     ebx, eax
0x14006b367  test    eax, eax
0x14006b369  jz      short loc_14006B39B
0x14006b36b  mov     rcx, cs:WPP_GLOBAL_Control
0x14006b372  lea     r14, WPP_GLOBAL_Control
0x14006b379  cmp     rcx, r14
0x14006b37c  jz      loc_14006B20B
0x14006b382  mov     r8d, 1
0x14006b388  test    [rcx+1Ch], r8b
0x14006b38c  jz      loc_14006B20B
0x14006b392  lea     edx, [r8+1Ch]
0x14006b396  jmp     loc_14006B54A
0x14006b39b  mov     rcx, cs:WPP_GLOBAL_Control
0x14006b3a2  lea     rax, WPP_GLOBAL_Control
0x14006b3a9  cmp     rcx, rax
0x14006b3ac  jz      short loc_14006B3D3
0x14006b3ae  test    byte ptr [rcx+1Ch], 4
0x14006b3b2  jz      short loc_14006B3D3
0x14006b3b4  mov     eax, [rsi]
0x14006b3b6  lea     r8, WPP_e81ebefcb3343b070146729bdebc64dd_Traceguids
0x14006b3bd  mov     r9, [rdi+38h]
0x14006b3c1  mov     edx, 1Eh
0x14006b3c6  mov     rcx, [rcx+10h]
0x14006b3ca  mov     dword ptr [rsp+180h+var_160], eax
0x14006b3ce  call    WPP_SF_Sd
0x14006b3d3  mov     r9d, 40h ; '@'
0x14006b3d9  mov     rcx, rdi; this
0x14006b3dc  mov     edx, r9d; unsigned int
0x14006b3df  call    ?ClearStatusFlag@CServiceRecord@@QEAAXK@Z; CServiceRecord::ClearStatusFlag(ulong)
0x14006b3e4  mov     r10d, 100h
0x14006b3ea  mov     edx, r10d; unsigned int
0x14006b3ed  call    ?ClearStatusFlag@CServiceRecord@@QEAAXK@Z; CServiceRecord::ClearStatusFlag(ulong)
0x14006b3f2  lea     r8d, [r9-3Fh]
0x14006b3f6  test    [rsi], r8b
0x14006b3f9  jz      loc_14006BFF2
0x14006b3ff  mov     edx, r9d; unsigned int
0x14006b402  call    ?SetStatusFlag@CServiceRecord@@QEAAXK@Z; CServiceRecord::SetStatusFlag(ulong)
0x14006b407  cmp     dword ptr [rsi], 3
0x14006b40a  jnz     loc_14006BFF2
0x14006b410  mov     edx, r10d; unsigned int
0x14006b413  call    ?SetStatusFlag@CServiceRecord@@QEAAXK@Z; CServiceRecord::SetStatusFlag(ulong)
0x14006b418  jmp     loc_14006BFF2
0x14006b41d  mov     rsi, [r13+8]
0x14006b421  test    rsi, rsi
0x14006b424  jz      loc_14006B319
0x14006b42a  mov     r8d, 1; unsigned int
0x14006b430  cmp     [rsi], r8d
0x14006b433  ja      loc_14006B33E
0x14006b439  mov     rcx, [rsp+180h+Handle]; KeyHandle
0x14006b43e  lea     eax, [r8+3]
0x14006b442  mov     dword ptr [rsp+180h+var_158], eax; unsigned int
0x14006b446  lea     rdx, aFailureactions_0; "FailureActionsOnNonCrashFailures"
0x14006b44d  mov     r9d, eax; unsigned int
0x14006b450  mov     [rsp+180h+var_160], rsi; void *
0x14006b455  call    ?ScRegSetValueExW@@YAKPEAUHKEY__@@PEBGKKPEAXK@Z; ScRegSetValueExW(HKEY__ *,ushort const *,ulong,ulong,void *,ulong)
0x14006b45a  mov     ebx, eax
0x14006b45c  test    eax, eax
0x14006b45e  jz      short loc_14006B48B
0x14006b460  mov     rcx, cs:WPP_GLOBAL_Control
0x14006b467  lea     r14, WPP_GLOBAL_Control
0x14006b46e  cmp     rcx, r14
0x14006b471  jz      loc_14006B20B
0x14006b477  test    byte ptr [rcx+1Ch], 1
0x14006b47b  jz      loc_14006B20B
0x14006b481  mov     edx, 1Bh
0x14006b486  jmp     loc_14006B54A
0x14006b48b  mov     rcx, cs:WPP_GLOBAL_Control
0x14006b492  lea     rax, WPP_GLOBAL_Control
0x14006b499  cmp     rcx, rax
0x14006b49c  jz      short loc_14006B4C3
0x14006b49e  test    byte ptr [rcx+1Ch], 4
0x14006b4a2  jz      short loc_14006B4C3
0x14006b4a4  mov     eax, [rsi]
0x14006b4a6  lea     r8, WPP_e81ebefcb3343b070146729bdebc64dd_Traceguids
0x14006b4ad  mov     r9, [rdi+38h]
0x14006b4b1  mov     edx, 1Ch
0x14006b4b6  mov     rcx, [rcx+10h]
0x14006b4ba  mov     dword ptr [rsp+180h+var_160], eax
0x14006b4be  call    WPP_SF_Sd
0x14006b4c3  cmp     dword ptr [rsi], 1
0x14006b4c6  mov     edx, 20h ; ' '
0x14006b4cb  mov     rcx, rdi
0x14006b4ce  jnz     loc_14006B60E
0x14006b4d4  jmp     loc_14006B413
0x14006b4d9  mov     rsi, [r13+8]
0x14006b4dd  test    rsi, rsi
0x14006b4e0  jz      loc_14006B319
0x14006b4e6  mov     edx, 1
0x14006b4eb  cmp     [rsi], edx
0x14006b4ed  jz      short loc_14006B550
0x14006b4ef  cmp     [rsi], r11d
0x14006b4f2  jnz     loc_14006B33E
0x14006b4f8  mov     rcx, [rsp+180h+Handle]; KeyHandle
0x14006b4fd  lea     rdx, aDelayedautosta; "DelayedAutostart"
0x14006b504  mov     eax, 4
0x14006b509  mov     dword ptr [rsp+180h+var_158], eax; unsigned int
0x14006b50d  mov     r9d, eax; unsigned int
0x14006b510  mov     [rsp+180h+var_160], rsi; void *
0x14006b515  call    ?ScRegSetValueExW@@YAKPEAUHKEY__@@PEBGKKPEAXK@Z; ScRegSetValueExW(HKEY__ *,ushort const *,ulong,ulong,void *,ulong)
0x14006b51a  mov     ebx, eax
0x14006b51c  test    eax, eax
0x14006b51e  jz      loc_14006B5A8
0x14006b524  mov     rcx, cs:WPP_GLOBAL_Control
0x14006b52b  lea     r14, WPP_GLOBAL_Control
0x14006b532  cmp     rcx, r14
0x14006b535  jz      loc_14006B20B
  ... truncated ...
```
