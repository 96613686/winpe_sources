# RDeleteService

- ea: `0x14006a9e0`
- end: `0x14006ae4c`
- name: `RDeleteService`
- size: `1132`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `27`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x140003e54`
- `0x1400044a4`
- `0x140004c58`
- `0x140004c98`
- `0x14000512c`
- `0x1400083f0`
- `0x140008548`
- `0x140008b90`
- `0x14000ac50`
- `0x140013b0c`
- `0x140014a8c`
- `0x14001c87c`
- `0x14001f7c0`
- `0x140020d84`
- `0x140022e34`
- `0x14002e844`
- `0x140038698`
- `0x140043dc4`
- `0x14004401c`
- `0x1400575b0`
- `0x1400644c0`
- `0x14006a9e0`
- `0x14006aeec`
- `0x14006fa84`
- `0x14007bffc`
- `0x140092060`
- `0x140094020`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14006aa8d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14006aa8d`
- `RPCRT4!RpcImpersonateClient` at `0x14006ab94`
- `RPCRT4!RpcImpersonateClient` at `0x14006ab94`
- `RPCRT4!RpcRevertToSelf` at `0x14006ac01`
- `RPCRT4!RpcRevertToSelf` at `0x14006ac01`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x14006acaf`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x14006acaf`
- `ntdll!NtDeleteObjectAuditAlarm` at `0x14006abc9`
- `ntdll!NtDeleteObjectAuditAlarm` at `0x14006abc9`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x14006ae16`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x14006ae16`
- `ntdll!RtlAcquireResourceExclusive` at `0x14006aaa0`
- `ntdll!RtlAcquireResourceExclusive` at `0x14006aaa0`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x14006aa87`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x14006aa87`
- `ntdll!RtlReleaseResource` at `0x14006ace1`
- `ntdll!RtlReleaseResource` at `0x14006ace1`
- `ntdll!RtlAreAllAccessesGranted` at `0x14006aa70`
- `ntdll!RtlAreAllAccessesGranted` at `0x14006aa70`
- `ntdll!RtlInitUnicodeString` at `0x14006abb3`
- `ntdll!RtlInitUnicodeString` at `0x14006abb3`
- `ntdll!RtlFreeHeap` at `0x14006ae09`
- `ntdll!RtlFreeHeap` at `0x14006ae09`

## pseudocode

```c
__int64 __fastcall RDeleteService(ACCESS_MASK *a1)
{
  _QWORD *v3; // rcx
  BOOL v4; // esi
  __int64 v5; // rbx
  __int64 v6; // r8
  unsigned int v7; // edi
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  int v11; // esi
  struct CServiceRecord *v12; // rcx
  RPC_STATUS v13; // eax
  NTSTATUS v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // edi
  RPC_STATUS v17; // eax
  int v18; // edx
  int v19; // r8d
  char v20; // cl
  struct _SERVICE_CONFIG_ROOT *v21; // rcx
  unsigned int v22; // eax
  PSID v23; // rsi
  PSID v24; // r8
  int v25; // eax
  unsigned int Pid[2]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v27[8]; // [rsp+38h] [rbp-C8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v29; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v30; // [rsp+60h] [rbp-A0h]
  WCHAR SourceString[264]; // [rsp+70h] [rbp-90h] BYREF

  DestinationString = 0;
  memset(SourceString, 0, 0x202u);
  ScSetTcpKeepalive();
  if ( ScShutdownInProgress )
    return 1115;
  if ( !(unsigned int)ScIsValidServiceHandle(a1) )
    return 6;
  if ( (unsigned int)ScCheckServiceProtectedProcess(v3, 0) || !RtlAreAllAccessesGranted(a1[2], 0x10000u) )
    return 5;
  v4 = 0;
  RtlAcquireSRWLockExclusive(&g_TriggerRegistrationLock);
  GetCurrentThreadId();
  v5 = *((_QWORD *)a1 + 2);
  RtlAcquireResourceExclusive(&ScServiceRecordLock, 1u);
  CScmLock::LockAutoExclusive(v5 + 312, v27);
  (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v5 + 152LL))(v5, 0);
  if ( (*(_DWORD *)(v5 + 52) & 1) != 0 )
  {
    CServiceRecord::LogPidsWithOpenHandles((CServiceRecord *)v5);
    v7 = 1072;
  }
  else
  {
    if ( (unsigned int)dword_1400BA2A0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400BA2A0, 0x200000000000LL, v6) )
    {
      *(_QWORD *)Pid = *(_QWORD *)(v5 + 56);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        v8,
        (__int64)byte_1400AE5E9,
        v9,
        v10,
        Pid);
    }
    if ( (unsigned int)CServiceRecord::AllocateDeletedCacheEntry((CServiceRecord *)v5) )
    {
      v11 = 1;
      CServiceRecord::SetStatusFlag((CServiceRecord *)v5, 1u);
      _InterlockedExchange((volatile __int32 *)(v5 + 36), 4);
      ScMarkForDelete(v12);
      v13 = RpcImpersonateClient(0);
      if ( v13 )
      {
        ScLogImpersonateFailureEvent(v13);
        v11 = 0;
      }
      RtlInitUnicodeString(&DestinationString, L"SC Manager");
      v14 = NtDeleteObjectAuditAlarm(&DestinationString, a1, a1[1] & 1);
      if ( v14 < 0
        && WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 78, WPP_119db94a907b38ec33df27ba8ada49ba_Traceguids, (unsigned int)v14);
      }
      if ( v11 )
      {
        v15 = RpcRevertToSelf();
        v16 = v15;
        if ( v15 )
        {
          if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
          {
            WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 79, WPP_119db94a907b38ec33df27ba8ada49ba_Traceguids, v15);
          }
          ScLogEvent(5u, L"RpcRevertToSelf", v16);
        }
      }
      v7 = 0;
      CServiceRecord::PostCompletedNotification((CServiceRecord *)v5, (struct CServiceRecord *)v5, 0xAu, 0, 0);
      StringCchCopyW(SourceString, 0x101u, *(const unsigned __int16 **)(v5 + 56));
      v4 = (*(_BYTE *)(v5 + 80) & 0x30) != 0;
    }
    else
    {
      v7 = 8;
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        WPP_SF_Sd(
          WPP_GLOBAL_Control->StubInfo,
          77,
          (unsigned int)WPP_119db94a907b38ec33df27ba8ada49ba_Traceguids,
          *(_QWORD *)(v5 + 56),
          8);
    }
  }
  CScmSyncLockExclusive::InternalUnlock((CScmSyncLockExclusive *)v27);
  Pid[0] = 0;
  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->UserInfo) & 0x100) != 0 )
  {
    v17 = I_RpcBindingInqLocalClientPID(0, Pid);
    v20 = 0;
    if ( !v17 )
      v20 = Pid[0];
    WPP_SF_SdL(WPP_GLOBAL_Control->StubInfo, v18, v19, *(_QWORD *)(v5 + 56), v7, v20);
  }
  RtlReleaseResource(&ScServiceRecordLock);
  if ( !v7 )
  {
    if ( v4 )
      ScUpdateServiceSidCache(SourceString, 0);
    ScDrainRemoteNotifyQueues();
    ScUnregisterDirectTriggerAction((struct CServiceRecord *)v5);
    if ( (*(_DWORD *)(v5 + 52) & 0x400) != 0 )
    {
      v21 = *(struct _SERVICE_CONFIG_ROOT **)(v5 + 216);
      v30 = 0;
      v29 = 0;
      *(_QWORD *)Pid = 0;
      v22 = ScResolveServiceAccount(v21, SourceString, (void **)Pid);
      if ( v22
        && WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      {
        WPP_SF_Sd(
          WPP_GLOBAL_Control->StubInfo,
          81,
          (unsigned int)WPP_119db94a907b38ec33df27ba8ada49ba_Traceguids,
          (unsigned int)SourceString,
          v22);
      }
      v23 = *(PSID *)Pid;
      v24 = *(PSID *)Pid;
      if ( !*(_QWORD *)Pid )
        v24 = LocalSystemSid;
      v25 = ((__int64 (__fastcall *)(__int128 *, WCHAR *, PSID, _QWORD, _DWORD))g_pScExtFunctionPointers[10])(
              &v29,
              SourceString,
              v24,
              0,
              0);
      if ( v25 )
      {
        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        {
          WPP_SF_Sd(
            WPP_GLOBAL_Control->StubInfo,
            82,
            (unsigned int)WPP_119db94a907b38ec33df27ba8ada49ba_Traceguids,
            (unsigned int)SourceString,
            v25);
        }
      }
      else
      {
        CServiceRecord::ClearStatusFlag((CServiceRecord *)v5, 1024);
      }
      if ( v23 )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v23);
    }
  }
  RtlReleaseSRWLockExclusive(&g_TriggerRegistrationLock);
  return v7;
}

```

## disassembly

```asm
0x14006a9e0  mov     [rsp-8+arg_8], rbx
0x14006a9e5  mov     [rsp-8+arg_10], rsi
0x14006a9ea  push    rbp
0x14006a9eb  push    rdi
0x14006a9ec  push    r12
0x14006a9ee  lea     rbp, [rsp-190h]
0x14006a9f6  sub     rsp, 290h
0x14006a9fd  mov     rax, cs:__security_cookie
0x14006aa04  xor     rax, rsp
0x14006aa07  mov     [rbp+1A0h+var_20], rax
0x14006aa0e  mov     rdi, rcx
0x14006aa11  xorps   xmm0, xmm0
0x14006aa14  lea     rcx, [rsp+2A0h+SourceString]; void *
0x14006aa19  xor     edx, edx; Val
0x14006aa1b  mov     r8d, 202h; Size
0x14006aa21  movups  xmmword ptr [rsp+2A0h+DestinationString.Length], xmm0
0x14006aa26  call    memset
0x14006aa2b  call    ?ScSetTcpKeepalive@@YAXXZ; ScSetTcpKeepalive(void)
0x14006aa30  cmp     cs:?ScShutdownInProgress@@3KA, 0; ulong ScShutdownInProgress
0x14006aa37  jz      short loc_14006AA43
0x14006aa39  mov     eax, 45Bh
0x14006aa3e  jmp     loc_14006AE25
0x14006aa43  mov     rcx, rdi; void *
0x14006aa46  call    ?ScIsValidServiceHandle@@YAHPEAX@Z; ScIsValidServiceHandle(void *)
0x14006aa4b  test    eax, eax
0x14006aa4d  jnz     short loc_14006AA59
0x14006aa4f  mov     eax, 6
0x14006aa54  jmp     loc_14006AE25
0x14006aa59  xor     edx, edx; unsigned __int8
0x14006aa5b  call    ?ScCheckServiceProtectedProcess@@YAKPEAXE@Z; ScCheckServiceProtectedProcess(void *,uchar)
0x14006aa60  test    eax, eax
0x14006aa62  jnz     loc_14006AE20
0x14006aa68  mov     ecx, [rdi+8]; GrantedAccess
0x14006aa6b  mov     edx, 10000h; DesiredAccess
0x14006aa70  call    cs:__imp_RtlAreAllAccessesGranted
0x14006aa76  test    al, al
0x14006aa78  jz      loc_14006AE20
0x14006aa7e  lea     rcx, g_TriggerRegistrationLock
0x14006aa85  xor     esi, esi
0x14006aa87  call    cs:__imp_RtlAcquireSRWLockExclusive
0x14006aa8d  call    cs:__imp_GetCurrentThreadId
0x14006aa93  mov     rbx, [rdi+10h]
0x14006aa97  lea     rcx, ?ScServiceRecordLock@@3VCServiceRecordLock@@A; Resource
0x14006aa9e  mov     dl, 1; Wait
0x14006aaa0  call    cs:__imp_RtlAcquireResourceExclusive
0x14006aaa6  lea     rcx, [rbx+138h]
0x14006aaad  lea     rdx, [rsp+2A0h+var_268]
0x14006aab2  call    ?LockAutoExclusive@CScmLock@@QEAA?AVCScmSyncLockExclusive@@XZ; CScmLock::LockAutoExclusive(void)
0x14006aab7  mov     rax, [rbx]
0x14006aaba  xor     edx, edx
0x14006aabc  mov     rcx, rbx
0x14006aabf  mov     rax, [rax+98h]
0x14006aac6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006aacb  mov     eax, [rbx+34h]
0x14006aace  lea     r12, WPP_GLOBAL_Control
0x14006aad5  test    al, 1
0x14006aad7  jz      short loc_14006AAEB
0x14006aad9  mov     rcx, rbx; this
0x14006aadc  call    ?LogPidsWithOpenHandles@CServiceRecord@@QEAAXXZ; CServiceRecord::LogPidsWithOpenHandles(void)
0x14006aae1  mov     edi, 430h
0x14006aae6  jmp     loc_14006AC81
0x14006aaeb  mov     eax, cs:dword_1400BA2A0
0x14006aaf1  cmp     eax, 5
0x14006aaf4  jbe     short loc_14006AB2F
0x14006aaf6  mov     rdx, 200000000000h
0x14006ab00  lea     rcx, dword_1400BA2A0
0x14006ab07  call    _tlgKeywordOn
0x14006ab0c  test    al, al
0x14006ab0e  jz      short loc_14006AB2F
0x14006ab10  mov     rax, [rbx+38h]
0x14006ab14  lea     rdx, byte_1400AE5E9
0x14006ab1b  mov     qword ptr [rsp+2A0h+Pid], rax
0x14006ab20  lea     rax, [rsp+2A0h+Pid]
0x14006ab25  mov     [rsp+2A0h+var_280], rax
0x14006ab2a  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x14006ab2f  mov     rcx, rbx; this
0x14006ab32  call    ?AllocateDeletedCacheEntry@CServiceRecord@@QEAAHXZ; CServiceRecord::AllocateDeletedCacheEntry(void)
0x14006ab37  test    eax, eax
0x14006ab39  jnz     short loc_14006AB78
0x14006ab3b  lea     edi, [rax+8]
0x14006ab3e  mov     rcx, cs:WPP_GLOBAL_Control
0x14006ab45  cmp     rcx, r12
0x14006ab48  jz      loc_14006AC81
0x14006ab4e  test    byte ptr [rcx+1Ch], 1
0x14006ab52  jz      loc_14006AC81
0x14006ab58  mov     r9, [rbx+38h]
0x14006ab5c  lea     edx, [rax+4Dh]
0x14006ab5f  mov     rcx, [rcx+10h]
0x14006ab63  lea     r8, WPP_119db94a907b38ec33df27ba8ada49ba_Traceguids
0x14006ab6a  mov     dword ptr [rsp+2A0h+var_280], edi
0x14006ab6e  call    WPP_SF_Sd
0x14006ab73  jmp     loc_14006AC81
0x14006ab78  mov     esi, 1
0x14006ab7d  mov     rcx, rbx; this
0x14006ab80  mov     edx, esi; unsigned int
0x14006ab82  call    ?SetStatusFlag@CServiceRecord@@QEAAXK@Z; CServiceRecord::SetStatusFlag(ulong)
0x14006ab87  lea     eax, [rsi+3]
0x14006ab8a  xchg    eax, [rbx+24h]
0x14006ab8d  call    ?ScMarkForDelete@@YAXPEAVCServiceRecord@@@Z; ScMarkForDelete(CServiceRecord *)
0x14006ab92  xor     ecx, ecx; BindingHandle
0x14006ab94  call    cs:__imp_RpcImpersonateClient
0x14006ab9a  test    eax, eax
0x14006ab9c  jz      short loc_14006ABA7
0x14006ab9e  mov     ecx, eax; int
0x14006aba0  call    ?ScLogImpersonateFailureEvent@@YAXJ@Z; ScLogImpersonateFailureEvent(long)
0x14006aba5  xor     esi, esi
0x14006aba7  lea     rdx, aScManager; "SC Manager"
0x14006abae  lea     rcx, [rsp+2A0h+DestinationString]; DestinationString
0x14006abb3  call    cs:__imp_RtlInitUnicodeString
0x14006abb9  mov     r8b, [rdi+4]
0x14006abbd  lea     rcx, [rsp+2A0h+DestinationString]; SubsystemName
0x14006abc2  and     r8b, 1; GenerateOnClose
0x14006abc6  mov     rdx, rdi; HandleId
0x14006abc9  call    cs:__imp_NtDeleteObjectAuditAlarm
0x14006abcf  test    eax, eax
0x14006abd1  jns     short loc_14006ABFD
0x14006abd3  mov     rcx, cs:WPP_GLOBAL_Control
0x14006abda  cmp     rcx, r12
0x14006abdd  jz      short loc_14006ABFD
0x14006abdf  test    byte ptr [rcx+1Ch], 1
0x14006abe3  jz      short loc_14006ABFD
0x14006abe5  mov     rcx, [rcx+10h]
0x14006abe9  lea     r8, WPP_119db94a907b38ec33df27ba8ada49ba_Traceguids
0x14006abf0  mov     edx, 4Eh ; 'N'
0x14006abf5  mov     r9d, eax
0x14006abf8  call    WPP_SF_d
0x14006abfd  test    esi, esi
0x14006abff  jz      short loc_14006AC4B
0x14006ac01  call    cs:__imp_RpcRevertToSelf
0x14006ac07  mov     edi, eax
0x14006ac09  test    eax, eax
0x14006ac0b  jz      short loc_14006AC4B
0x14006ac0d  mov     rcx, cs:WPP_GLOBAL_Control
0x14006ac14  cmp     rcx, r12
0x14006ac17  jz      short loc_14006AC37
0x14006ac19  test    byte ptr [rcx+1Ch], 1
0x14006ac1d  jz      short loc_14006AC37
0x14006ac1f  mov     rcx, [rcx+10h]
0x14006ac23  lea     r8, WPP_119db94a907b38ec33df27ba8ada49ba_Traceguids
0x14006ac2a  mov     edx, 4Fh ; 'O'
0x14006ac2f  mov     r9d, eax
0x14006ac32  call    WPP_SF_d
0x14006ac37  mov     r8d, edi
0x14006ac3a  lea     rdx, aRpcreverttosel; "RpcRevertToSelf"
0x14006ac41  mov     ecx, 5; unsigned int
0x14006ac46  call    ?ScLogEvent@@YAXKZZ; ScLogEvent(ulong,...)
0x14006ac4b  xor     edi, edi
0x14006ac4d  xor     r9d, r9d; struct _SC_NOTIFY_BLOCK *
0x14006ac50  mov     rdx, rbx; struct CServiceRecord *
0x14006ac53  mov     [rsp+2A0h+var_280], rdi; void **
0x14006ac58  mov     rcx, rbx; this
0x14006ac5b  lea     r8d, [rdi+0Ah]; unsigned int
0x14006ac5f  call    ?PostCompletedNotification@CServiceRecord@@QEAAXPEAV1@KPEAU_SC_NOTIFY_BLOCK@@PEAPEAX@Z; CServiceRecord::PostCompletedNotification(CServiceRecord *,ulong,_SC_NOTIFY_BLOCK *,void * *)
0x14006ac64  mov     r8, [rbx+38h]; unsigned __int16 *
0x14006ac68  lea     rcx, [rsp+2A0h+SourceString]; unsigned __int16 *
0x14006ac6d  mov     edx, 101h; unsigned __int64
0x14006ac72  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14006ac77  test    byte ptr [rbx+50h], 30h
0x14006ac7b  mov     esi, edi
0x14006ac7d  setnz   sil
0x14006ac81  lea     rcx, [rsp+2A0h+var_268]; this
0x14006ac86  call    ?InternalUnlock@CScmSyncLockExclusive@@IEAAXXZ; CScmSyncLockExclusive::InternalUnlock(void)
0x14006ac8b  mov     [rsp+2A0h+Pid], 0
0x14006ac93  mov     rax, cs:WPP_GLOBAL_Control
0x14006ac9a  cmp     rax, r12
0x14006ac9d  jz      short loc_14006ACDA
0x14006ac9f  test    dword ptr [rax+1Ch], 100h
0x14006aca6  jz      short loc_14006ACDA
0x14006aca8  lea     rdx, [rsp+2A0h+Pid]; Pid
0x14006acad  xor     ecx, ecx; Binding
0x14006acaf  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x14006acb5  mov     r9, [rbx+38h]
0x14006acb9  xor     ecx, ecx
0x14006acbb  test    eax, eax
0x14006acbd  cmovz   ecx, [rsp+2A0h+Pid]
0x14006acc2  mov     [rsp+2A0h+var_278], ecx
0x14006acc6  mov     rcx, cs:WPP_GLOBAL_Control
0x14006accd  mov     dword ptr [rsp+2A0h+var_280], edi
0x14006acd1  mov     rcx, [rcx+10h]
0x14006acd5  call    WPP_SF_SdL
0x14006acda  lea     rcx, ?ScServiceRecordLock@@3VCServiceRecordLock@@A; Resource
0x14006ace1  call    cs:__imp_RtlReleaseResource
0x14006ace7  test    edi, edi
0x14006ace9  jnz     loc_14006AE0F
0x14006acef  test    esi, esi
0x14006acf1  jz      short loc_14006ACFF
0x14006acf3  xor     edx, edx; int
0x14006acf5  lea     rcx, [rsp+2A0h+SourceString]; SourceString
0x14006acfa  call    ?ScUpdateServiceSidCache@@YAXPEBGH@Z; ScUpdateServiceSidCache(ushort const *,int)
0x14006acff  call    ?ScDrainRemoteNotifyQueues@@YAXXZ; ScDrainRemoteNotifyQueues(void)
0x14006ad04  mov     rcx, rbx; struct CServiceRecord *
0x14006ad07  call    ?ScUnregisterDirectTriggerAction@@YAXPEAVCServiceRecord@@@Z; ScUnregisterDirectTriggerAction(CServiceRecord *)
0x14006ad0c  mov     eax, [rbx+34h]
0x14006ad0f  bt      eax, 0Ah
0x14006ad13  jnb     loc_14006AE0F
0x14006ad19  mov     rcx, [rbx+0D8h]; struct _SERVICE_CONFIG_ROOT *
0x14006ad20  lea     r8, [rsp+2A0h+Pid]; void **
0x14006ad25  xor     eax, eax
0x14006ad27  lea     rdx, [rsp+2A0h+SourceString]; unsigned __int16 *
0x14006ad2c  xorps   xmm0, xmm0
0x14006ad2f  mov     [rsp+2A0h+var_240], rax
0x14006ad34  movups  [rsp+2A0h+var_250], xmm0
0x14006ad39  mov     qword ptr [rsp+2A0h+Pid], rax
0x14006ad3e  call    ?ScResolveServiceAccount@@YAKPEAU_SERVICE_CONFIG_ROOT@@PEAGPEAPEAX@Z; ScResolveServiceAccount(_SERVICE_CONFIG_ROOT *,ushort *,void * *)
0x14006ad43  test    eax, eax
0x14006ad45  jz      short loc_14006AD77
0x14006ad47  mov     rcx, cs:WPP_GLOBAL_Control
0x14006ad4e  cmp     rcx, r12
0x14006ad51  jz      short loc_14006AD77
0x14006ad53  test    byte ptr [rcx+1Ch], 1
0x14006ad57  jz      short loc_14006AD77
0x14006ad59  mov     rcx, [rcx+10h]
0x14006ad5d  lea     r9, [rsp+2A0h+SourceString]
0x14006ad62  mov     edx, 51h ; 'Q'
0x14006ad67  mov     dword ptr [rsp+2A0h+var_280], eax
0x14006ad6b  lea     r8, WPP_119db94a907b38ec33df27ba8ada49ba_Traceguids
0x14006ad72  call    WPP_SF_Sd
0x14006ad77  mov     rsi, qword ptr [rsp+2A0h+Pid]
0x14006ad7c  lea     rdx, [rsp+2A0h+SourceString]
0x14006ad81  mov     rax, cs:?g_pScExtFunctionPointers@@3PEAPEAXEA; void * * g_pScExtFunctionPointers
0x14006ad88  lea     rcx, [rsp+2A0h+var_250]
0x14006ad8d  test    rsi, rsi
0x14006ad90  mov     dword ptr [rsp+2A0h+var_280], 0
0x14006ad98  mov     r8, rsi
0x14006ad9b  cmovz   r8, cs:LocalSystemSid
0x14006ada3  xor     r9d, r9d
0x14006ada6  mov     rax, [rax+50h]
0x14006adaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006adaf  test    eax, eax
0x14006adb1  jz      short loc_14006ADE5
0x14006adb3  mov     rcx, cs:WPP_GLOBAL_Control
0x14006adba  cmp     rcx, r12
0x14006adbd  jz      short loc_14006ADF2
0x14006adbf  test    byte ptr [rcx+1Ch], 1
0x14006adc3  jz      short loc_14006ADF2
0x14006adc5  mov     rcx, [rcx+10h]
0x14006adc9  lea     r9, [rsp+2A0h+SourceString]
0x14006adce  mov     edx, 52h ; 'R'
0x14006add3  mov     dword ptr [rsp+2A0h+var_280], eax
0x14006add7  lea     r8, WPP_119db94a907b38ec33df27ba8ada49ba_Traceguids
0x14006adde  call    WPP_SF_Sd
0x14006ade3  jmp     short loc_14006ADF2
0x14006ade5  mov     edx, 400h; unsigned int
0x14006adea  mov     rcx, rbx; this
0x14006aded  call    ?ClearStatusFlag@CServiceRecord@@QEAAXK@Z; CServiceRecord::ClearStatusFlag(ulong)
0x14006adf2  test    rsi, rsi
0x14006adf5  jz      short loc_14006AE0F
0x14006adf7  mov     rcx, gs:60h
0x14006ae00  mov     r8, rsi; P
0x14006ae03  xor     edx, edx; Flags
0x14006ae05  mov     rcx, [rcx+30h]; HeapHandle
0x14006ae09  call    cs:__imp_RtlFreeHeap
0x14006ae0f  lea     rcx, g_TriggerRegistrationLock
0x14006ae16  call    cs:__imp_RtlReleaseSRWLockExclusive
0x14006ae1c  mov     eax, edi
0x14006ae1e  jmp     short loc_14006AE25
0x14006ae20  mov     eax, 5
0x14006ae25  mov     rcx, [rbp+1A0h+var_20]
0x14006ae2c  xor     rcx, rsp; StackCookie
0x14006ae2f  call    __security_check_cookie
0x14006ae34  lea     r11, [rsp+2A0h+var_10]
0x14006ae3c  mov     rbx, [r11+28h]
0x14006ae40  mov     rsi, [r11+30h]
0x14006ae44  mov     rsp, r11
0x14006ae47  pop     r12
0x14006ae49  pop     rdi
0x14006ae4a  pop     rbp
0x14006ae4b  retn
```
