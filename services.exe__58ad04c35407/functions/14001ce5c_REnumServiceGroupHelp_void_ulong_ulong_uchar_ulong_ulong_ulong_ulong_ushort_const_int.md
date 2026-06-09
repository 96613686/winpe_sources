# REnumServiceGroupHelp(void *,ulong,ulong,uchar *,ulong,ulong *,ulong *,ulong *,ushort const *,int)

- ea: `0x14001ce5c`
- end: `0x14001d810`
- name: `?REnumServiceGroupHelp@@YAKPEAXKKPEAEKPEAK22PEBGH@Z`
- size: `2484`
- prototype: `unsigned int __usercall@<eax>(void *@<rcx>, unsigned int@<edx>, unsigned int@<r8d>, unsigned __int8 *@<r9>, unsigned int, unsigned int *, unsigned int *, unsigned int *, const unsigned __int16 *, int)`
- caller_count: `4`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x14001cbb0`
- `0x14001cd80`
- `0x14001cde0`
- `0x140073dd0`

## callees

- `0x140002890`
- `0x140003310`
- `0x1400037b4`
- `0x140003e54`
- `0x140004b10`
- `0x140004c58`
- `0x140007130`
- `0x1400078dc`
- `0x1400083f0`
- `0x14000ab50`
- `0x14000cf60`
- `0x140013b0c`
- `0x140013f60`
- `0x140017160`
- `0x14001c080`
- `0x14001ce5c`
- `0x140029228`
- `0x140040a20`
- `0x14004401c`
- `0x1400795ac`
- `0x140094020`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14001cfee`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14001cfee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001d41c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001d41c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14001d08f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14001d08f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14001d07c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14001d07c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001d7d4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001d7d4`
- `RPCRT4!RpcImpersonateClient` at `0x14001d067`
- `RPCRT4!RpcImpersonateClient` at `0x14001d1e9`
- `RPCRT4!RpcImpersonateClient` at `0x14001d54b`
- `RPCRT4!RpcImpersonateClient` at `0x14001d067`
- `RPCRT4!RpcImpersonateClient` at `0x14001d1e9`
- `RPCRT4!RpcImpersonateClient` at `0x14001d54b`
- `RPCRT4!RpcRevertToSelf` at `0x14001d0f2`
- `RPCRT4!RpcRevertToSelf` at `0x14001d277`
- `RPCRT4!RpcRevertToSelf` at `0x14001d584`
- `RPCRT4!RpcRevertToSelf` at `0x14001d783`
- `RPCRT4!RpcRevertToSelf` at `0x14001d0f2`
- `RPCRT4!RpcRevertToSelf` at `0x14001d277`
- `RPCRT4!RpcRevertToSelf` at `0x14001d584`
- `RPCRT4!RpcRevertToSelf` at `0x14001d783`
- `ntdll!RtlAreAllAccessesGranted` at `0x14001cf02`
- `ntdll!RtlAreAllAccessesGranted` at `0x14001cf02`
- `ntdll!RtlFreeHeap` at `0x14001d334`
- `ntdll!RtlFreeHeap` at `0x14001d680`
- `ntdll!RtlFreeHeap` at `0x14001d334`
- `ntdll!RtlFreeHeap` at `0x14001d680`

## pseudocode

```c
__int64 __fastcall REnumServiceGroupHelp(
        ACCESS_MASK *a1,
        int a2,
        int a3,
        unsigned __int8 *a4,
        unsigned int a5,
        unsigned int *a6,
        unsigned int *a7,
        unsigned int *a8,
        wchar_t *String2,
        int a10)
{
  unsigned int v14; // r13d
  unsigned int v15; // r14d
  unsigned int *v16; // r15
  const unsigned __int16 *v17; // rcx
  unsigned int ServiceDisplayName; // esi
  unsigned __int16 *v20; // r14
  unsigned __int16 **v21; // r12
  struct CDriverRecord *v22; // rbx
  unsigned int v23; // r8d
  int v24; // edi
  RPC_STATUS v25; // eax
  HANDLE CurrentThread; // rax
  __int64 v27; // rcx
  unsigned int v28; // edi
  unsigned int v29; // eax
  __int64 v30; // rcx
  const unsigned __int16 *v31; // r15
  const unsigned __int16 *v32; // rcx
  __int64 v33; // rdx
  int v34; // eax
  __int64 v35; // rdx
  __int64 v36; // r8
  int v37; // r12d
  unsigned __int16 v38; // ax
  __int64 v39; // rdx
  __int64 v40; // r8
  void *JITReadDisplayName; // r14
  unsigned int v42; // edi
  __int64 v43; // rdx
  int v44; // r15d
  unsigned __int8 *v45; // rdi
  unsigned __int8 *v46; // rax
  _OWORD *v47; // rax
  __int64 v48; // rcx
  DWORD LastError; // eax
  unsigned int v50; // r8d
  unsigned int v51; // eax
  __int64 v52; // rdx
  __int64 v53; // r8
  __int64 v54; // rcx
  int v55; // r14d
  unsigned __int16 v56; // ax
  unsigned int v57; // edi
  _WORD *v58; // r8
  __int64 v59; // rax
  __int64 v60; // rcx
  __int64 v61; // rcx
  unsigned int v62; // eax
  unsigned int v63; // ebx
  char *v64; // [rsp+30h] [rbp-50h] BYREF
  int v65; // [rsp+38h] [rbp-48h]
  PVOID P; // [rsp+40h] [rbp-40h] BYREF
  struct CDriverRecord *v67; // [rsp+48h] [rbp-38h] BYREF
  int v68; // [rsp+50h] [rbp-30h]
  unsigned int v69; // [rsp+54h] [rbp-2Ch]
  void *TokenHandle; // [rsp+58h] [rbp-28h] BYREF
  unsigned __int8 *v71; // [rsp+60h] [rbp-20h]
  struct CNameEntry *NamedGroupRecord; // [rsp+68h] [rbp-18h]
  unsigned __int16 *v73; // [rsp+70h] [rbp-10h] BYREF
  unsigned __int16 **v74; // [rsp+78h] [rbp-8h]

  v67 = 0;
  TokenHandle = 0;
  P = 0;
  ScSetTcpKeepalive();
  if ( ScShutdownInProgress )
  {
    v14 = 1115;
LABEL_17:
    Microsoft::WRL::ComPtr<CServiceRecord>::InternalRelease(&v67);
    return v14;
  }
  if ( !(unsigned int)ScIsValidScManagerHandle(a1) )
  {
    v14 = 6;
    goto LABEL_17;
  }
  if ( (a2 & 0x3FF) == 0 || (a2 & 0xFFFFFC00) != 0 || (a3 & 3) == 0 || (a3 & 0xFFFFFFFC) != 0 )
  {
    Microsoft::WRL::ComPtr<CServiceRecord>::InternalRelease(&v67);
    return 87;
  }
  if ( !RtlAreAllAccessesGranted(a1[2], 4u) )
  {
    v14 = 5;
    goto LABEL_17;
  }
  v15 = 0;
  v16 = a7;
  NamedGroupRecord = 0;
  v69 = 0;
  v65 = 0;
  *a7 = 0;
  *a6 = 0;
  if ( a8 )
  {
    v15 = *a8;
    v69 = *a8;
  }
  v17 = String2;
  if ( String2 )
  {
    if ( *String2 )
    {
      NamedGroupRecord = ScGetNamedGroupRecord(String2);
      if ( !NamedGroupRecord )
      {
        v14 = 1060;
        goto LABEL_17;
      }
    }
    else
    {
      v65 = 1;
    }
  }
  ServiceDisplayName = 0;
  if ( !(unsigned int)CServiceDatabase::FindServiceByResumeIndex((__int64)v17, v15, &v67) )
  {
LABEL_138:
    v24 = 0;
    goto LABEL_144;
  }
  v68 = 0;
  v20 = (unsigned __int16 *)&a4[a5 & 0xFFFFFFFE];
  v71 = a4;
  v73 = v20;
  v21 = (unsigned __int16 **)a4;
  while ( 1 )
  {
    v22 = v67;
    if ( !v67 )
    {
      v24 = 0;
      if ( *v16 )
      {
LABEL_140:
        if ( *a6 )
          ServiceDisplayName = 234;
        if ( a8 )
          *a8 = ServiceDisplayName != 0 ? v69 : 0;
      }
      goto LABEL_144;
    }
    if ( (a2 & 0xB) != 0 && (*((_BYTE *)v67 + 80) & 0xB) != 0 )
      ScGetDriverStatus(v67, 0);
    AcquireSRWLockShared((PSRWLOCK)v22 + 39);
    v64 = (char *)v22 + 312;
    v24 = 0;
    if ( NamedGroupRecord )
    {
      if ( NamedGroupRecord == *((struct CNameEntry **)v22 + 16) )
        goto LABEL_31;
      if ( !v65 )
        goto LABEL_88;
    }
    else if ( !v65 )
    {
      goto LABEL_31;
    }
    if ( *((_QWORD *)v22 + 16) )
      goto LABEL_88;
LABEL_31:
    if ( (a2 & *((_DWORD *)v22 + 20)) == 0
      || (((*((_DWORD *)v22 + 21) == 1) + 1) & a3) == 0
      || (*((_DWORD *)v22 + 13) & 0x100000) != 0 && (a2 & 0x40) == 0 )
    {
      goto LABEL_88;
    }
    if ( TokenHandle )
      goto LABEL_47;
    v25 = RpcImpersonateClient(0);
    ServiceDisplayName = v25;
    if ( v25 )
      goto LABEL_93;
    v24 = 1;
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
      break;
    if ( ((unsigned __int16 (__fastcall *)(__int64))g_pScExtFunctionPointers[7])(v27) != g_SystemLanguageId )
    {
      v68 = 1;
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) != 0 )
        WPP_SF_Dd(WPP_GLOBAL_Control->StubInfo, 11, WPP_a76578a3009a35419e1ae513b791565b_Traceguids);
    }
    v28 = RpcRevertToSelf();
    if ( v28 )
    {
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 12, WPP_a76578a3009a35419e1ae513b791565b_Traceguids, v28);
      ScLogEvent(5u, L"RpcRevertToSelf", v28);
    }
LABEL_47:
    v29 = ScAccessCheck(*((void **)v22 + 18), TokenHandle, v23);
    ServiceDisplayName = v29;
    if ( v29 == 5 )
    {
      Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockShared *)&v64);
      CServiceDatabase::GetNext(v30, &v67);
      ServiceDisplayName = 0;
      goto LABEL_49;
    }
    if ( v29 )
    {
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        WPP_SF_Sd(
          WPP_GLOBAL_Control->StubInfo,
          13,
          (unsigned int)WPP_a76578a3009a35419e1ae513b791565b_Traceguids,
          *((_QWORD *)v22 + 7),
          v29);
      Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockShared *)&v64);
      goto LABEL_138;
    }
    v31 = (const unsigned __int16 *)((char *)v21 + (a10 != 0 ? 44LL : 36LL));
    v74 = (unsigned __int16 **)v31;
    if ( v31 >= v20 )
      goto LABEL_95;
    v32 = (const unsigned __int16 *)*((_QWORD *)v22 + 7);
    v33 = -1;
    do
      ++v33;
    while ( v32[v33] );
    v34 = ScCopyStringToBufferW(v32, v33, v31, &v73, v21, a4);
    v37 = 0;
    if ( !v34 )
    {
LABEL_95:
      v24 = 0;
LABEL_96:
      Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockShared *)&v64);
      while ( 2 )
      {
        CScmLock::LockAutoShared((char *)v22 + 312, &v64);
        if ( NamedGroupRecord )
        {
          if ( NamedGroupRecord != *((struct CNameEntry **)v22 + 16) )
          {
            if ( v65 )
              goto LABEL_102;
            goto LABEL_128;
          }
        }
        else if ( v65 )
        {
LABEL_102:
          if ( !*((_QWORD *)v22 + 16) )
            break;
LABEL_128:
          Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockShared *)&v64);
          CServiceDatabase::GetNext(v61, &v67);
LABEL_129:
          Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockShared *)&v64);
          v22 = v67;
          if ( !v67 )
            goto LABEL_140;
          continue;
        }
        break;
      }
      if ( (a2 & *((_DWORD *)v22 + 20)) == 0 || (((*((_DWORD *)v22 + 21) == 1) + 1) & a3) == 0 )
        goto LABEL_128;
      v51 = ScAccessCheck(*((void **)v22 + 18), TokenHandle, v50);
      ServiceDisplayName = v51;
      if ( v51 == 5 )
      {
        Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockShared *)&v64);
        CServiceDatabase::GetNext(v54, &v67);
        ServiceDisplayName = 0;
        goto LABEL_129;
      }
      if ( v51 )
      {
        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        {
          WPP_SF_Sd(
            WPP_GLOBAL_Control->StubInfo,
            16,
            (unsigned int)WPP_a76578a3009a35419e1ae513b791565b_Traceguids,
            *((_QWORD *)v22 + 7),
            v51);
        }
        goto LABEL_92;
      }
      v55 = 0;
      if ( v68 )
      {
        v25 = RpcImpersonateClient(0);
        ServiceDisplayName = v25;
        if ( v25 )
          goto LABEL_93;
        v56 = (*(__int64 (__fastcall **)(struct CDriverRecord *))(*(_QWORD *)v22 + 48LL))(v22);
        ServiceDisplayName = ScGetServiceDisplayName(
                               *((struct _SERVICE_CONFIG_ROOT **)v22 + 27),
                               *((unsigned __int16 **)v22 + 7),
                               v56,
                               (unsigned __int16 **)&P);
        v57 = RpcRevertToSelf();
        if ( v57 )
        {
          if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
          {
            WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 17, WPP_a76578a3009a35419e1ae513b791565b_Traceguids, v57);
          }
          ScLogEvent(5u, L"RpcRevertToSelf", v57);
        }
        v24 = 0;
        if ( !ServiceDisplayName )
        {
          v58 = P;
          v55 = 1;
LABEL_122:
          v59 = -1;
          v60 = -1;
          do
            ++v60;
          while ( v58[v60] );
          do
            ++v59;
          while ( *(_WORD *)(*((_QWORD *)v22 + 7) + 2 * v59) );
          *a6 += (a10 != 0 ? 48 : 40) + 2 * (v59 + v60);
          if ( v55 && v58 )
          {
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v58);
            P = 0;
          }
          goto LABEL_128;
        }
        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        {
          WPP_SF_Sd(
            WPP_GLOBAL_Control->StubInfo,
            18,
            (unsigned int)WPP_a76578a3009a35419e1ae513b791565b_Traceguids,
            *((_QWORD *)v22 + 7),
            ServiceDisplayName);
        }
        ServiceDisplayName = 0;
      }
      P = CServiceRecord::GetJITReadDisplayName(v22, v52, v53);
      v58 = P;
      goto LABEL_122;
    }
    v24 = 0;
    if ( v68 )
    {
      v25 = RpcImpersonateClient(0);
      ServiceDisplayName = v25;
      if ( v25 )
      {
LABEL_93:
        ScLogImpersonateFailureEvent(v25);
        Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockShared *)&v64);
        goto LABEL_144;
      }
      v38 = (*(__int64 (__fastcall **)(struct CDriverRecord *))(*(_QWORD *)v22 + 48LL))(v22);
      ServiceDisplayName = ScGetServiceDisplayName(
                             *((struct _SERVICE_CONFIG_ROOT **)v22 + 27),
                             *((unsigned __int16 **)v22 + 7),
                             v38,
                             (unsigned __int16 **)&P);
      if ( ServiceDisplayName )
      {
        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        {
          WPP_SF_Sd(
            WPP_GLOBAL_Control->StubInfo,
            14,
            (unsigned int)WPP_a76578a3009a35419e1ae513b791565b_Traceguids,
            *((_QWORD *)v22 + 7),
            ServiceDisplayName);
        }
        ServiceDisplayName = 0;
        JITReadDisplayName = CServiceRecord::GetJITReadDisplayName(v22, v39, v40);
        P = JITReadDisplayName;
      }
      else
      {
        JITReadDisplayName = P;
        v37 = 1;
      }
      v42 = RpcRevertToSelf();
      if ( v42 )
      {
        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 15, WPP_a76578a3009a35419e1ae513b791565b_Traceguids, v42);
        }
        ScLogEvent(5u, L"RpcRevertToSelf", v42);
      }
      v24 = 0;
    }
    else
    {
      JITReadDisplayName = CServiceRecord::GetJITReadDisplayName(v22, v35, v36);
      P = JITReadDisplayName;
    }
    v43 = -1;
    do
      ++v43;
    while ( *((_WORD *)JITReadDisplayName + v43) );
    v44 = ScCopyStringToBufferW(
            (const unsigned __int16 *)JITReadDisplayName,
            v43,
            v31,
            &v73,
            (unsigned __int16 **)(v71 + 4),
            a4);
    if ( v37 && JITReadDisplayName )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, JITReadDisplayName);
      P = 0;
    }
    if ( !v44 )
      goto LABEL_96;
    v45 = 0;
    v46 = v71;
    if ( a10 )
    {
      v45 = v71 + 8;
      *(_QWORD *)(v71 + 36) = 0;
    }
    v47 = v46 + 8;
    if ( (*((_BYTE *)v22 + 80) & 0xB) != 0 )
    {
      if ( v47 )
      {
        *v47 = *((_OWORD *)v22 + 5);
        *(_OWORD *)((char *)v47 + 12) = *(_OWORD *)((char *)v22 + 92);
      }
    }
    else
    {
      if ( v47 )
      {
        *v47 = *((_OWORD *)v22 + 5);
        *(_OWORD *)((char *)v47 + 12) = *(_OWORD *)((char *)v22 + 92);
      }
      if ( a10 )
      {
        if ( (*(__int64 (__fastcall **)(struct CDriverRecord *))(*(_QWORD *)v22 + 160LL))(v22) )
        {
          *((_DWORD *)v45 + 7) = *(_DWORD *)((*(__int64 (__fastcall **)(struct CDriverRecord *))(*(_QWORD *)v22 + 160LL))(v22)
                                           + 40);
          if ( (*(_BYTE *)((*(__int64 (__fastcall **)(struct CDriverRecord *))(*(_QWORD *)v22 + 160LL))(v22) + 104) & 2) != 0 )
            *((_DWORD *)v45 + 8) |= 1u;
        }
      }
    }
    v16 = a7;
    v21 = v74;
    v20 = v73;
    v71 = (unsigned __int8 *)v74;
    ++*a7;
    v69 = *((_DWORD *)v22 + 8);
LABEL_88:
    Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockShared *)&v64);
    CServiceDatabase::GetNext(v48, &v67);
LABEL_49:
    Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockShared *)&v64);
  }
  LastError = GetLastError();
  ServiceDisplayName = LastError;
  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 10, WPP_a76578a3009a35419e1ae513b791565b_Traceguids, LastError);
LABEL_92:
  Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockShared *)&v64);
LABEL_144:
  ScReleaseGroup(NamedGroupRecord);
  if ( v24 )
  {
    v62 = RpcRevertToSelf();
    v63 = v62;
    if ( v62 )
    {
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 19, WPP_a76578a3009a35419e1ae513b791565b_Traceguids, v62);
      ScLogEvent(5u, L"RpcRevertToSelf", v63);
    }
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  Microsoft::WRL::ComPtr<CServiceRecord>::InternalRelease(&v67);
  return ServiceDisplayName;
}

```

## disassembly

```asm
0x14001ce5c  mov     rax, rsp
0x14001ce5f  mov     [rax+8], rbx
0x14001ce63  mov     [rax+20h], r9
0x14001ce67  mov     [rax+18h], r8d
0x14001ce6b  mov     [rax+10h], edx
0x14001ce6e  push    rbp
0x14001ce6f  push    rsi
0x14001ce70  push    rdi
0x14001ce71  push    r12
0x14001ce73  push    r13
0x14001ce75  push    r14
0x14001ce77  push    r15
0x14001ce79  mov     rbp, rsp
0x14001ce7c  sub     rsp, 80h
0x14001ce83  xor     r12d, r12d
0x14001ce86  mov     rdi, r9
0x14001ce89  mov     [rbp+var_38], r12
0x14001ce8d  mov     r14d, r8d
0x14001ce90  mov     [rbp+TokenHandle], r12
0x14001ce94  mov     esi, edx
0x14001ce96  mov     [rbp+P], r12
0x14001ce9a  mov     rbx, rcx
0x14001ce9d  call    ?ScSetTcpKeepalive@@YAXXZ; ScSetTcpKeepalive(void)
0x14001cea2  cmp     cs:?ScShutdownInProgress@@3KA, r12d; ulong ScShutdownInProgress
0x14001cea9  jz      short loc_14001CEB6
0x14001ceab  mov     r13d, 45Bh
0x14001ceb1  jmp     loc_14001CF67
0x14001ceb6  mov     rcx, rbx; void *
0x14001ceb9  call    ?ScIsValidScManagerHandle@@YAHPEAX@Z; ScIsValidScManagerHandle(void *)
0x14001cebe  test    eax, eax
0x14001cec0  jnz     short loc_14001CECB
0x14001cec2  lea     r13d, [rax+6]
0x14001cec6  jmp     loc_14001CF67
0x14001cecb  test    esi, 3FFh
0x14001ced1  jz      loc_14001D7E7
0x14001ced7  test    esi, 0FFFFFC00h
0x14001cedd  jnz     loc_14001D7E7
0x14001cee3  test    r14b, 3
0x14001cee7  jz      loc_14001D7E7
0x14001ceed  test    r14d, 0FFFFFFFCh
0x14001cef4  jnz     loc_14001D7E7
0x14001cefa  mov     ecx, [rbx+8]; GrantedAccess
0x14001cefd  mov     edx, 4; DesiredAccess
0x14001cf02  call    cs:__imp_RtlAreAllAccessesGranted
0x14001cf08  test    al, al
0x14001cf0a  jnz     short loc_14001CF14
0x14001cf0c  mov     r13d, 5
0x14001cf12  jmp     short loc_14001CF67
0x14001cf14  mov     rax, [rbp+arg_28]
0x14001cf18  mov     r14d, r12d
0x14001cf1b  mov     r15, [rbp+arg_30]
0x14001cf1f  mov     [rbp+var_18], r12
0x14001cf23  mov     [rbp+var_2C], r12d
0x14001cf27  mov     [rbp+var_48], r12d
0x14001cf2b  mov     [r15], r12d
0x14001cf2e  mov     [rax], r12d
0x14001cf31  mov     rax, [rbp+arg_38]
0x14001cf35  test    rax, rax
0x14001cf38  jz      short loc_14001CF41
0x14001cf3a  mov     r14d, [rax]
0x14001cf3d  mov     [rbp+var_2C], r14d
0x14001cf41  mov     rcx, [rbp+String2]; String2
0x14001cf48  test    rcx, rcx
0x14001cf4b  jz      short loc_14001CF7F
0x14001cf4d  cmp     [rcx], r12w
0x14001cf51  jz      short loc_14001CF78
0x14001cf53  call    ?ScGetNamedGroupRecord@@YAPEAVCNameEntry@@PEBG@Z; ScGetNamedGroupRecord(ushort const *)
0x14001cf58  mov     [rbp+var_18], rax
0x14001cf5c  test    rax, rax
0x14001cf5f  jnz     short loc_14001CF7F
0x14001cf61  mov     r13d, 424h
0x14001cf67  lea     rcx, [rbp+var_38]
0x14001cf6b  call    ?InternalRelease@?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CServiceRecord>::InternalRelease(void)
0x14001cf70  mov     eax, r13d
0x14001cf73  jmp     loc_14001D7F5
0x14001cf78  mov     [rbp+var_48], 1
0x14001cf7f  lea     r8, [rbp+var_38]
0x14001cf83  mov     edx, r14d
0x14001cf86  mov     esi, r12d
0x14001cf89  call    ?FindServiceByResumeIndex@CServiceDatabase@@QEAAHKAEAV?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@@Z; CServiceDatabase::FindServiceByResumeIndex(ulong,Microsoft::WRL::ComPtr<CServiceRecord> &)
0x14001cf8e  lea     r14, WPP_GLOBAL_Control
0x14001cf95  mov     r13d, 5
0x14001cf9b  test    eax, eax
0x14001cf9d  jz      loc_14001D73C
0x14001cfa3  mov     r14d, [rbp+arg_20]
0x14001cfa7  mov     eax, 0FFFFFFFEh
0x14001cfac  and     r14, rax
0x14001cfaf  mov     [rbp+var_30], r12d
0x14001cfb3  add     r14, rdi
0x14001cfb6  mov     [rbp+var_20], rdi
0x14001cfba  mov     [rbp+var_10], r14
0x14001cfbe  mov     r12, rdi
0x14001cfc1  mov     rbx, [rbp+var_38]
0x14001cfc5  test    rbx, rbx
0x14001cfc8  jz      loc_14001D741
0x14001cfce  test    byte ptr [rbp+arg_8], 0Bh
0x14001cfd2  jz      short loc_14001CFE4
0x14001cfd4  test    byte ptr [rbx+50h], 0Bh
0x14001cfd8  jz      short loc_14001CFE4
0x14001cfda  xor     edx, edx; struct _SERVICE_STATUS *
0x14001cfdc  mov     rcx, rbx; struct CDriverRecord *
0x14001cfdf  call    ?ScGetDriverStatus@@YAKPEAVCDriverRecord@@PEAU_SERVICE_STATUS@@@Z; ScGetDriverStatus(CDriverRecord *,_SERVICE_STATUS *)
0x14001cfe4  lea     rdi, [rbx+138h]
0x14001cfeb  mov     rcx, rdi; SRWLock
0x14001cfee  call    cs:__imp_AcquireSRWLockShared
0x14001cff4  mov     rcx, [rbp+var_18]
0x14001cff8  mov     [rbp+var_50], rdi
0x14001cffc  xor     edi, edi
0x14001cffe  cmp     dword ptr [rbx+54h], 1
0x14001d002  mov     eax, edi
0x14001d004  setz    al
0x14001d007  inc     eax
0x14001d009  test    rcx, rcx
0x14001d00c  jnz     short loc_14001D015
0x14001d00e  cmp     [rbp+var_48], edi
0x14001d011  jz      short loc_14001D034
0x14001d013  jmp     short loc_14001D027
0x14001d015  cmp     rcx, [rbx+80h]
0x14001d01c  jz      short loc_14001D034
0x14001d01e  cmp     [rbp+var_48], edi
0x14001d021  jz      loc_14001D405
0x14001d027  cmp     [rbx+80h], rdi
0x14001d02e  jnz     loc_14001D405
0x14001d034  mov     ecx, [rbp+arg_8]
0x14001d037  test    [rbx+50h], ecx
0x14001d03a  jz      loc_14001D405
0x14001d040  test    [rbp+arg_10], eax
0x14001d043  jz      loc_14001D405
0x14001d049  mov     eax, [rbx+34h]
0x14001d04c  bt      eax, 14h
0x14001d050  jnb     short loc_14001D05B
0x14001d052  test    cl, 40h
0x14001d055  jz      loc_14001D405
0x14001d05b  cmp     [rbp+TokenHandle], rdi
0x14001d05f  jnz     loc_14001D143
0x14001d065  xor     ecx, ecx; BindingHandle
0x14001d067  call    cs:__imp_RpcImpersonateClient
0x14001d06d  mov     esi, eax
0x14001d06f  test    eax, eax
0x14001d071  jnz     loc_14001D463
0x14001d077  lea     esi, [rax+1]
0x14001d07a  mov     edi, esi
0x14001d07c  call    cs:__imp_GetCurrentThread
0x14001d082  lea     r9, [rbp+TokenHandle]; TokenHandle
0x14001d086  mov     r8d, esi; OpenAsSelf
0x14001d089  mov     rcx, rax; ThreadHandle
0x14001d08c  lea     edx, [rsi+7]; DesiredAccess
0x14001d08f  call    cs:__imp_OpenThreadToken
0x14001d095  test    eax, eax
0x14001d097  jz      loc_14001D41C
0x14001d09d  mov     rax, cs:?g_pScExtFunctionPointers@@3PEAPEAXEA; void * * g_pScExtFunctionPointers
0x14001d0a4  mov     rax, [rax+38h]
0x14001d0a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d0ad  movzx   edx, ax
0x14001d0b0  movzx   eax, cs:?g_SystemLanguageId@@3GA; ushort g_SystemLanguageId
0x14001d0b7  cmp     dx, ax
0x14001d0ba  jz      short loc_14001D0F2
0x14001d0bc  mov     [rbp+var_30], esi
0x14001d0bf  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d0c6  lea     r8, WPP_GLOBAL_Control
0x14001d0cd  cmp     rcx, r8
0x14001d0d0  jz      short loc_14001D0F2
0x14001d0d2  test    byte ptr [rcx+1Ch], 4
0x14001d0d6  jz      short loc_14001D0F2
0x14001d0d8  mov     rcx, [rcx+10h]
0x14001d0dc  lea     r8, WPP_a76578a3009a35419e1ae513b791565b_Traceguids
0x14001d0e3  mov     r9d, edx
0x14001d0e6  mov     dword ptr [rsp+80h+var_60], eax
0x14001d0ea  lea     edx, [rsi+0Ah]
0x14001d0ed  call    WPP_SF_Dd
0x14001d0f2  call    cs:__imp_RpcRevertToSelf
0x14001d0f8  mov     edi, eax
0x14001d0fa  test    eax, eax
0x14001d0fc  jz      short loc_14001D141
0x14001d0fe  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d105  lea     rax, WPP_GLOBAL_Control
0x14001d10c  cmp     rcx, rax
0x14001d10f  jz      short loc_14001D12F
0x14001d111  test    byte ptr [rcx+1Ch], 1
0x14001d115  jz      short loc_14001D12F
0x14001d117  mov     rcx, [rcx+10h]
0x14001d11b  lea     r8, WPP_a76578a3009a35419e1ae513b791565b_Traceguids
0x14001d122  mov     edx, 0Ch
0x14001d127  mov     r9d, edi
0x14001d12a  call    WPP_SF_d
0x14001d12f  mov     r8d, edi
0x14001d132  lea     rdx, aRpcreverttosel; "RpcRevertToSelf"
0x14001d139  mov     ecx, r13d; unsigned int
0x14001d13c  call    ?ScLogEvent@@YAXKZZ; ScLogEvent(ulong,...)
0x14001d141  xor     edi, edi
0x14001d143  mov     rdx, [rbp+TokenHandle]; void *
0x14001d147  mov     rcx, [rbx+90h]; void *
0x14001d14e  call    ?ScAccessCheck@@YAKPEAX0K@Z; ScAccessCheck(void *,void *,ulong)
0x14001d153  mov     esi, eax
0x14001d155  cmp     eax, r13d
0x14001d158  jnz     short loc_14001D17C
0x14001d15a  lea     rcx, [rbp+var_50]; this
0x14001d15e  call    ?InternalUnlock@SyncLockShared@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock(void)
0x14001d163  lea     rdx, [rbp+var_38]
0x14001d167  call    ?GetNext@CServiceDatabase@@QEAAXAEAV?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@@Z; CServiceDatabase::GetNext(Microsoft::WRL::ComPtr<CServiceRecord> &)
0x14001d16c  mov     esi, edi
0x14001d16e  lea     rcx, [rbp+var_50]; this
0x14001d172  call    ?InternalUnlock@SyncLockShared@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock(void)
0x14001d177  jmp     loc_14001CFC1
0x14001d17c  test    eax, eax
0x14001d17e  jnz     loc_14001D6FA
0x14001d184  mov     eax, [rbp+arg_48]
0x14001d18a  neg     eax
0x14001d18c  sbb     rcx, rcx
0x14001d18f  and     ecx, 8
0x14001d192  lea     r15, [rcx+24h]
0x14001d196  add     r15, r12
0x14001d199  mov     [rbp+var_8], r15
0x14001d19d  cmp     r15, r14
0x14001d1a0  jnb     loc_14001D490
0x14001d1a6  mov     rcx, [rbx+38h]; unsigned __int16 *
0x14001d1aa  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14001d1ae  inc     rdx; unsigned int
0x14001d1b1  cmp     [rcx+rdx*2], di
0x14001d1b5  jnz     short loc_14001D1AE
0x14001d1b7  mov     rax, [rbp+arg_18]
0x14001d1bb  lea     r9, [rbp+var_10]; unsigned __int16 **
0x14001d1bf  mov     [rsp+80h+var_58], rax; unsigned __int8 *
0x14001d1c4  mov     r8, r15; unsigned __int16 *
0x14001d1c7  mov     [rsp+80h+var_60], r12; unsigned __int16 **
0x14001d1cc  call    ?ScCopyStringToBufferW@@YAHPEBGK0PEAPEAG1QEAE@Z; ScCopyStringToBufferW(ushort const *,ulong,ushort const *,ushort * *,ushort * *,uchar * const)
0x14001d1d1  xor     r12d, r12d
0x14001d1d4  test    eax, eax
0x14001d1d6  jz      loc_14001D493
0x14001d1dc  xor     edi, edi
0x14001d1de  cmp     [rbp+var_30], edi
0x14001d1e1  jz      loc_14001D2CE
0x14001d1e7  xor     ecx, ecx; BindingHandle
0x14001d1e9  call    cs:__imp_RpcImpersonateClient
0x14001d1ef  mov     esi, eax
0x14001d1f1  test    eax, eax
0x14001d1f3  jnz     loc_14001D47B
0x14001d1f9  mov     rax, [rbx]
0x14001d1fc  mov     rcx, rbx
0x14001d1ff  mov     rax, [rax+30h]
0x14001d203  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d208  mov     rdx, [rbx+38h]; unsigned __int16 *
0x14001d20c  lea     r9, [rbp+P]; unsigned __int16 **
0x14001d210  mov     rcx, [rbx+0D8h]; struct _SERVICE_CONFIG_ROOT *
0x14001d217  movzx   r8d, ax; unsigned __int16
0x14001d21b  call    ?ScGetServiceDisplayName@@YAKPEAU_SERVICE_CONFIG_ROOT@@PEAGGPEAPEAG@Z; ScGetServiceDisplayName(_SERVICE_CONFIG_ROOT *,ushort *,ushort,ushort * *)
0x14001d220  mov     esi, eax
0x14001d222  test    eax, eax
0x14001d224  jnz     short loc_14001D230
0x14001d226  mov     r14, [rbp+P]
0x14001d22a  lea     r12d, [rdi+1]
0x14001d22e  jmp     short loc_14001D277
0x14001d230  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d237  lea     rax, WPP_GLOBAL_Control
0x14001d23e  cmp     rcx, rax
0x14001d241  jz      short loc_14001D266
0x14001d243  test    byte ptr [rcx+1Ch], 1
0x14001d247  jz      short loc_14001D266
0x14001d249  mov     r9, [rbx+38h]
0x14001d24d  lea     r8, WPP_a76578a3009a35419e1ae513b791565b_Traceguids
0x14001d254  mov     rcx, [rcx+10h]
0x14001d258  mov     edx, 0Eh
0x14001d25d  mov     dword ptr [rsp+80h+var_60], esi
0x14001d261  call    WPP_SF_Sd
0x14001d266  mov     rcx, rbx; this
0x14001d269  mov     esi, edi
0x14001d26b  call    ?GetJITReadDisplayName@CServiceRecord@@QEAAPEAGXZ; CServiceRecord::GetJITReadDisplayName(void)
0x14001d270  mov     r14, rax
0x14001d273  mov     [rbp+P], rax
0x14001d277  call    cs:__imp_RpcRevertToSelf
0x14001d27d  mov     edi, eax
0x14001d27f  xor     eax, eax
0x14001d281  test    edi, edi
0x14001d283  jz      short loc_14001D2CA
0x14001d285  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d28c  lea     rax, WPP_GLOBAL_Control
0x14001d293  cmp     rcx, rax
0x14001d296  jz      short loc_14001D2B6
0x14001d298  test    byte ptr [rcx+1Ch], 1
0x14001d29c  jz      short loc_14001D2B6
0x14001d29e  mov     rcx, [rcx+10h]
0x14001d2a2  lea     r8, WPP_a76578a3009a35419e1ae513b791565b_Traceguids
0x14001d2a9  mov     edx, 0Fh
0x14001d2ae  mov     r9d, edi
0x14001d2b1  call    WPP_SF_d
0x14001d2b6  mov     r8d, edi
0x14001d2b9  lea     rdx, aRpcreverttosel; "RpcRevertToSelf"
0x14001d2c0  mov     ecx, r13d; unsigned int
0x14001d2c3  call    ?ScLogEvent@@YAXKZZ; ScLogEvent(ulong,...)
0x14001d2c8  xor     eax, eax
0x14001d2ca  mov     edi, eax
0x14001d2cc  jmp     short loc_14001D2DF
0x14001d2ce  mov     rcx, rbx; this
0x14001d2d1  call    ?GetJITReadDisplayName@CServiceRecord@@QEAAPEAGXZ; CServiceRecord::GetJITReadDisplayName(void)
0x14001d2d6  mov     r14, rax
0x14001d2d9  mov     [rbp+P], rax
0x14001d2dd  xor     eax, eax
0x14001d2df  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14001d2e3  inc     rdx; unsigned int
0x14001d2e6  cmp     [r14+rdx*2], ax
  ... truncated ...
```
