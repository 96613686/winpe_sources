# LRPC_SCALL::HandleRequest(_PORT_MESSAGE *,_PORT_MESSAGE *,void *,unsigned __int64,RPCP_ALPC_HANDLE_ATTR *)

- ea: `0x18001a4f0`
- end: `0x18001aff0`
- name: `?HandleRequest@LRPC_SCALL@@QEAAXPEAU_PORT_MESSAGE@@0PEAX_KPEAVRPCP_ALPC_HANDLE_ATTR@@@Z`
- size: `2816`
- prototype: `void __fastcall(LRPC_SCALL *this, struct _PORT_MESSAGE *, struct _PORT_MESSAGE *, __int64, unsigned __int64, struct RPCP_ALPC_HANDLE_ATTR *)`
- caller_count: `2`
- callee_count: `33`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180019720`
- `0x18001f070`

## callees

- `0x180015ca0`
- `0x1800184d8`
- `0x1800190e4`
- `0x18001917c`
- `0x1800191d0`
- `0x180019300`
- `0x1800193a8`
- `0x180019eac`
- `0x180019f18`
- `0x180019f40`
- `0x18001a2f0`
- `0x18001a4f0`
- `0x18001aff8`
- `0x18001c140`
- `0x18001d65c`
- `0x180021e18`
- `0x180021e70`
- `0x180023ca0`
- `0x1800274e0`
- `0x180027d50`
- `0x180027dd4`
- `0x180027e10`
- `0x1800283bc`
- `0x180036934`
- `0x18004c240`
- `0x1800826b0`
- `0x18008435c`
- `0x18008a000`
- `0x18008a5bc`
- `0x18009d7f0`
- `0x1800a4e4c`
- `0x1800ca140`
- `0x1800d2010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18001ab4e`
- `ntdll!RtlLeaveCriticalSection` at `0x18001ae46`
- `ntdll!RtlLeaveCriticalSection` at `0x18001ab4e`
- `ntdll!RtlLeaveCriticalSection` at `0x18001ae46`
- `ntdll!RtlEnterCriticalSection` at `0x18001ab32`
- `ntdll!RtlEnterCriticalSection` at `0x18001ab32`
- `ntdll!RtlReleaseSRWLockShared` at `0x18001a613`
- `ntdll!RtlReleaseSRWLockShared` at `0x18001aeab`
- `ntdll!RtlReleaseSRWLockShared` at `0x18001a613`
- `ntdll!RtlReleaseSRWLockShared` at `0x18001aeab`
- `ntdll!RtlAcquireSRWLockShared` at `0x18001a5a3`
- `ntdll!RtlAcquireSRWLockShared` at `0x18001a5a3`
- `ntdll!AlpcFreeCompletionListMessage` at `0x18001ad8b`
- `ntdll!AlpcFreeCompletionListMessage` at `0x18001ad8b`

## pseudocode

```c
void __fastcall LRPC_SCALL::HandleRequest(
        LRPC_SCALL *this,
        struct _PORT_MESSAGE *a2,
        struct _PORT_MESSAGE *a3,
        __int64 a4,
        unsigned __int64 a5,
        struct RPCP_ALPC_HANDLE_ATTR *a6)
{
  char *v6; // r15
  unsigned int v7; // ebx
  __int64 v9; // rdi
  struct _PORT_MESSAGE *v10; // r12
  union _PORT_MESSAGE::$C6BC508B531A81D74C33985719C23F49 v12; // xmm0
  int v13; // esi
  __int64 i; // rcx
  unsigned int v15; // eax
  _DWORD *j; // rbx
  __int64 v17; // rsi
  int v18; // eax
  __int64 v19; // r15
  int v20; // eax
  __int64 v21; // rax
  int v22; // ebx
  SecurityCacheEntry *v23; // r14
  int v24; // eax
  unsigned __int64 ReservedForNtRpc; // rdx
  unsigned __int64 v26; // rdx
  SecurityCacheEntry *v27; // r14
  RPCP_ALPC_HANDLE_ATTR *v28; // rsi
  signed __int64 v29; // rdx
  unsigned int m; // ecx
  __int64 v31; // rax
  __int64 v32; // rax
  int v33; // ecx
  unsigned __int16 v34; // ax
  unsigned __int16 v35; // ax
  unsigned int v36; // ebx
  struct tagExtendedErrorInfo *ExtendedErrorInfoRecord; // rax
  struct tagExtendedErrorInfo *v38; // r15
  __int128 v39; // xmm0
  __int64 v40; // xmm1_8
  __int64 v41; // rdx
  struct _LRPC_FAULT_MESSAGE *v42; // rsi
  LRPC_ADDRESS *v43; // r12
  BOOL v44; // r15d
  int v45; // eax
  __int64 v46; // rsi
  BCACHE *v47; // rcx
  BCACHE *v48; // rcx
  void *v49; // rdx
  bool v50; // zf
  signed __int32 v51; // eax
  unsigned __int8 v52; // bl
  _QWORD *v53; // rax
  __int64 v54; // rdx
  unsigned int k; // ecx
  void *v56; // rdx
  int v57; // eax
  void *v58; // r9
  char v59; // [rsp+40h] [rbp-C0h] BYREF
  char v60; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int64 v61; // [rsp+50h] [rbp-B0h] BYREF
  SecurityCacheEntry *v62; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v63; // [rsp+60h] [rbp-A0h]
  RPCP_ALPC_HANDLE_ATTR *v64; // [rsp+68h] [rbp-98h] BYREF
  __int64 v65; // [rsp+70h] [rbp-90h] BYREF
  int v66[2]; // [rsp+78h] [rbp-88h] BYREF
  void *v67; // [rsp+80h] [rbp-80h]
  __int128 v68; // [rsp+88h] [rbp-78h] BYREF
  __int64 v69; // [rsp+98h] [rbp-68h]
  _BYTE v70[16]; // [rsp+A0h] [rbp-60h] BYREF
  char *v71; // [rsp+B0h] [rbp-50h]
  __int64 v72; // [rsp+B8h] [rbp-48h]
  char *v73; // [rsp+C0h] [rbp-40h]
  __int64 v74; // [rsp+C8h] [rbp-38h]
  SecurityCacheEntry **v75; // [rsp+D0h] [rbp-30h]
  __int64 v76; // [rsp+D8h] [rbp-28h]
  int *v77; // [rsp+E0h] [rbp-20h]
  __int64 v78; // [rsp+E8h] [rbp-18h]
  RPCP_ALPC_HANDLE_ATTR **v79; // [rsp+F0h] [rbp-10h]
  __int64 v80; // [rsp+F8h] [rbp-8h]

  v6 = (char *)this + 416;
  v7 = *((_DWORD *)this + 133);
  v9 = *((_QWORD *)this + 38);
  v10 = a2;
  v64 = a6;
  *((_DWORD *)this + 104) = 16;
  v63 = a4;
  v67 = a2;
  LODWORD(v61) = 0;
  if ( !(_WORD)v7 )
    LRPC_CANCEL_HISTORY_INFORMATION::AdvanceRecord((PRTL_BITMAP)(v9 + 448), v7, (struct MUTEX *)(v9 + 112));
  if ( *(_DWORD *)(v9 + 464) || *(_DWORD *)(v9 + 468) )
  {
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(v9 + 112));
    v36 = v7 - *(_DWORD *)(v9 + 472);
    if ( v36 >= 0xFFFFFFC1 || v36 == 0 )
    {
      v52 = _bittest64(*(const signed __int64 **)(v9 + 456), -v36);
      RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(v9 + 112));
      if ( v52 )
        LODWORD(v10[1].DoNotUseThisField) |= 8u;
    }
    else
    {
      RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(v9 + 112));
    }
  }
  v12 = v10->8;
  *((_QWORD *)this + 56) = a3;
  *((_QWORD *)this + 55) = v10;
  *((union _PORT_MESSAGE::$C6BC508B531A81D74C33985719C23F49 *)this + 31) = v12;
  v13 = *((_DWORD *)&v10[1].DoNotUseThisField + 2);
  RtlAcquireSRWLockShared(v9 + 240);
  for ( i = 0; ; i = v15 )
  {
    if ( (unsigned int)i >= *(_DWORD *)(v9 + 72) )
      goto LABEL_10;
    v15 = i + 1;
    if ( *(_QWORD *)(8 * i + *(_QWORD *)(v9 + 64)) )
      break;
  }
  _mm_lfence();
  for ( j = *(_DWORD **)(8 * i + *(_QWORD *)(v9 + 64)); ; j = 0 )
  {
LABEL_11:
    if ( !j )
    {
      RtlReleaseSRWLockShared(v9 + 240);
      v54 = *((int *)&v10[1].DoNotUseThisField + 2);
      DWORD2(v68) = *((_DWORD *)&v10[1].DoNotUseThisField + 2);
      v22 = 1717;
      LODWORD(v68) = 3;
      if ( dword_1800F9624 )
      {
        for ( k = 0; k < 4; ++k )
        {
          if ( `LogEventToEtw'::`2'::EtwEventSubjectFilter[k] == 73 )
            goto LABEL_75;
        }
        if ( (Microsoft_Windows_RPCEnableBits & 8) != 0 )
        {
          v65 = v54;
          v71 = &v59;
          *(_QWORD *)v66 = 30;
          v73 = &v60;
          v62 = (SecurityCacheEntry *)1717;
          v75 = &v62;
          v60 = 2;
          v77 = v66;
          v79 = (RPCP_ALPC_HANDLE_ATTR **)&v65;
          v59 = 73;
          v72 = 1;
          v74 = 1;
          v76 = 8;
          v78 = 8;
          v80 = 8;
          McGenEventWrite_EtwEventWriteTransfer(
            (unsigned int)&RpcEtwGuid_Context,
            (unsigned int)RPCLogEvent,
            0,
            6,
            (__int64)v70);
        }
      }
LABEL_75:
      ExtendedErrorInfoRecord = AllocateExtendedErrorInfoRecord(1u);
      v38 = ExtendedErrorInfoRecord;
      if ( ExtendedErrorInfoRecord )
      {
        InitializePrivateEEInfo(ExtendedErrorInfoRecord);
        v39 = v68;
        *((_WORD *)v38 + 28) = 30;
        v40 = v69;
        *((_DWORD *)v38 + 12) = 2;
        *((_DWORD *)v38 + 13) = 1717;
        *((_OWORD *)v38 + 4) = v39;
        *((_QWORD *)v38 + 10) = v40;
        if ( (unsigned int)AddPrivateRecord(v38) )
          FreeEEInfoRecord(v38);
      }
      else
      {
        FreeEEInfoPrivateParam(&v68);
      }
      v19 = v63;
      goto LABEL_79;
    }
    if ( j[2] == v13 )
      break;
    while ( v15 < *(_DWORD *)(v9 + 72) )
    {
      j = *(_DWORD **)(*(_QWORD *)(v9 + 64) + 8LL * v15++);
      if ( j )
        goto LABEL_11;
    }
LABEL_10:
    v15 = 0;
  }
  RtlReleaseSRWLockShared(v9 + 240);
  *((_QWORD *)this + 39) = j;
  v17 = *(_QWORD *)j;
  v18 = *((_DWORD *)&v10[1].DoNotUseThisField + 3);
  *((_QWORD *)this + 48) = v6;
  v19 = v63;
  *((_DWORD *)this + 91) = v18;
  *((_QWORD *)this + 42) = this;
  if ( v19 )
  {
    v32 = v19 ^ 1;
    v33 = v19 & 1;
    v61 = v19 & 1;
    if ( (v19 & 1) == 0 )
      v32 = v19;
    v63 = v32;
    v19 = v32;
    *((_QWORD *)this + 44) = v32;
    *((_DWORD *)this + 90) = a5;
    if ( v33 )
    {
      *((_QWORD *)this + 59) = v32;
      _InterlockedOr((volatile signed __int32 *)this + 58, 0x1020u);
    }
    else
    {
      _InterlockedOr((volatile signed __int32 *)this + 58, 0x20u);
    }
LABEL_18:
    if ( (*((_DWORD *)this + 58) & 0x80u) != 0 )
    {
      if ( (*(_DWORD *)(*(_QWORD *)j + 56LL) & 2) == 0 )
      {
        v22 = 1728;
        goto LABEL_79;
      }
      v20 = 0;
    }
    else
    {
      v20 = 4096;
    }
    *((_DWORD *)this + 102) = v20;
    *((_DWORD *)this + 86) = 16;
    if ( (LOBYTE(v10[1].DoNotUseThisField) & 1) != 0 )
    {
      *((_DWORD *)this + 128) = 1;
      *(union _PORT_MESSAGE::$C6BC508B531A81D74C33985719C23F49 *)((char *)this + 516) = v10[2].8;
    }
    else
    {
      *((_DWORD *)this + 128) = 0;
    }
    if ( (LOBYTE(v10[1].DoNotUseThisField) & 8) != 0 )
    {
      do
        v51 = *((_DWORD *)this + 58);
      while ( (v51 & 0x400) == 0
           && v51 != _InterlockedCompareExchange((volatile signed __int32 *)this + 58, v51 | 0x10, v51) );
    }
    if ( !*(_QWORD *)(v17 + 72)
      && !*(_QWORD *)(v17 + 560)
      && !(*(__int64 (__fastcall **)(LRPC_SCALL *))(*(_QWORD *)this + 488LL))(this) )
    {
LABEL_43:
      v28 = v64;
      if ( !v64
        || (v22 = LRPC_SYSTEM_HANDLE_DATA::FromAlpcHandleAttribute(
                    (LRPC_SCALL *)((char *)this + 608),
                    *(void **)(*(_QWORD *)(v9 + 56) + 208LL),
                    v10,
                    v64)) == 0 )
      {
        LRPC_SCALL::QueueOrDispatchCall(this);
        goto LABEL_45;
      }
      LODWORD(v68) = 3;
      DWORD2(v68) = 0;
      RpcpErrorAddRecord(2u, v22, 0x20u, 1, (struct tagParam *)&v68);
      goto LABEL_69;
    }
    if ( (*(_DWORD *)(v17 + 8) & 0x100) != 0 )
    {
      if ( !*((_QWORD *)this + 37) )
      {
        v53 = AllocWrapper(0x18u);
        if ( !v53 )
        {
          *((_QWORD *)this + 37) = 0;
          v22 = 14;
          goto LABEL_79;
        }
        *v53 = 0;
        v53[1] = 0;
        v53[2] = 0;
        *((_QWORD *)this + 37) = v53;
      }
      v22 = RPC_INTERFACE::DoAsyncSecurityCallback((RPC_INTERFACE *)v17, this);
LABEL_42:
      if ( v22 )
      {
        if ( v22 == 997 )
          goto LABEL_45;
        v31 = *((_QWORD *)this + 39);
        LODWORD(v68) = 3;
        DWORD2(v68) = *(_DWORD *)(*(_QWORD *)v31 + 84LL);
        RpcpErrorAddRecord(2u, v22, 0x1Fu, 1, (struct tagParam *)&v68);
        goto LABEL_79;
      }
      goto LABEL_43;
    }
    v21 = *(_QWORD *)this;
    v62 = 0;
    v66[0] = 0;
    v22 = (*(__int64 (__fastcall **)(LRPC_SCALL *, __int64, SecurityCacheEntry **))(v21 + 424))(this, v17, &v62);
    if ( v22
      || ((v23 = v62, (*(_DWORD *)(v17 + 8) & 0x80u) != 0)
        ? (v34 = (*(__int64 (__fastcall **)(LRPC_SCALL *))(*(_QWORD *)this + 272LL))(this),
           v24 = SecurityCacheEntry::LookupCall(v23, *(_DWORD *)(v17 + 364), v34))
        : (v24 = SecurityCacheEntry::LookupCall(v62, *(_DWORD *)(v17 + 364))),
          !v24) )
    {
      v22 = RPC_INTERFACE::EnforceInterfaceSecurityDescriptor((RPC_INTERFACE *)v17, this);
      if ( !v22 )
      {
LABEL_30:
        if ( (unsigned int)RpcpConvertToLongRunning() )
        {
          v22 = 14;
        }
        else
        {
          ReservedForNtRpc = (unsigned __int64)NtCurrentTeb()->ReservedForNtRpc;
          if ( ReservedForNtRpc
            && (ReservedForNtRpc ^= 0xABABABABDEDEDEDEuLL,
                *(HANDLE *)(ReservedForNtRpc + 16) != NtCurrentTeb()->ClientId.UniqueThread)
            || (*(_QWORD *)(ReservedForNtRpc + 32) = this,
                *(_DWORD *)ReservedForNtRpc = 0,
                v22 = RPC_INTERFACE::DoSecurityCallbackHelper((RPC_INTERFACE *)v17, this, v66),
                (v26 = (unsigned __int64)NtCurrentTeb()->ReservedForNtRpc) != 0)
            && (v26 ^= 0xABABABABDEDEDEDEuLL, *(HANDLE *)(v26 + 16) != NtCurrentTeb()->ClientId.UniqueThread) )
          {
            __fastfail(0x1Eu);
          }
          *(_QWORD *)(v26 + 32) = 0;
          *(_DWORD *)v26 = 0;
          if ( !v22 )
          {
            v27 = v62;
            if ( !v62 )
              goto LABEL_42;
            if ( (*(_DWORD *)(v17 + 8) & 0x80u) != 0 )
            {
              v35 = (*(__int64 (__fastcall **)(LRPC_SCALL *))(*(_QWORD *)this + 272LL))(this);
              SecurityCacheEntry::RememberCall(v27, *(_DWORD *)(v17 + 364), v35);
            }
            else
            {
              SecurityCacheEntry::RememberCall(v62, *(_DWORD *)(v17 + 364));
            }
          }
        }
      }
    }
    else if ( (*(_DWORD *)(v17 + 8) & 0x40) != 0 )
    {
      goto LABEL_30;
    }
    if ( v62 )
      (*(void (__fastcall **)(LRPC_SCALL *))(*(_QWORD *)this + 432LL))(this);
    goto LABEL_42;
  }
  *((_QWORD *)this + 44) = (char *)v10 + 104;
  *((_DWORD *)this + 90) = (unsigned __int16)v10->u1.s1.TotalLength - 104;
  if ( (LOBYTE(v10[1].DoNotUseThisField) & 4) == 0 )
    goto LABEL_18;
  v22 = 14;
LABEL_79:
  v28 = v64;
  if ( v64 )
LABEL_69:
    RPCP_ALPC_HANDLE_ATTR::Cleanup(v28);
  v41 = *((_QWORD *)this + 55);
  if ( (*(_BYTE *)(v41 + 48) & 2) != 0 )
  {
    v57 = LRPC_SASSOCIATION::CFCallDispatchFailure((LRPC_SASSOCIATION *)v9, (struct _LRPC_REQUEST_MESSAGE *)v41);
    LRPC_ADDRESS::HandleFailureNoAssociation(
      *(LRPC_ADDRESS **)(v9 + 56),
      v22,
      *((struct _PORT_MESSAGE **)this + 56),
      v19 != 0,
      v57 == 0,
      0);
  }
  else
  {
    v42 = (struct _LRPC_FAULT_MESSAGE *)*((_QWORD *)this + 56);
    v43 = *(LRPC_ADDRESS **)(v9 + 56);
    v44 = v63 != 0;
    SetFaultPacket(v42, v22, 0, 0);
    v45 = LRPC_ADDRESS::AlpcSend(v43, (struct _PORT_MESSAGE *)v42, v44, 0, 0, 0, 0);
    if ( v45 < 0
      && (*(unsigned int (__fastcall **)(LRPC_ADDRESS *, _QWORD))(*(_QWORD *)v43 + 184LL))(v43, (unsigned int)v45) == 14 )
    {
      SetCommonFaultFields(v42, v22, 0, 0);
      LRPC_ADDRESS::AlpcSend(v43, (struct _PORT_MESSAGE *)v42, v44, v58, 0, 0, 0);
    }
    v10 = (struct _PORT_MESSAGE *)v67;
  }
  v46 = *(_QWORD *)(*((_QWORD *)this + 38) + 56LL);
  v47 = *(BCACHE **)(v46 + 296);
  if ( v47
    && v10 > (struct _PORT_MESSAGE *)v47
    && v10 < (struct _PORT_MESSAGE *)((char *)v47 + *(unsigned int *)(v46 + 304)) )
  {
    if ( dword_1800F9624 )
      LogEventToEtw(0x4Cu, 0x62u, (__int64)v10, v46, *(_QWORD *)(v46 + 296));
    AlpcFreeCompletionListMessage(*(_QWORD *)(v46 + 296), v10);
  }
  else
  {
    BCACHE::Free(v47, v10);
  }
  v49 = (void *)*((_QWORD *)this + 56);
  *((_QWORD *)this + 55) = 0;
  if ( v49 )
    BCACHE::Free(v48, v49);
  v50 = (_DWORD)v61 == 0;
  *((_QWORD *)this + 56) = 0;
  if ( !v50 )
  {
    v56 = (void *)*((_QWORD *)this + 59);
    if ( v56 )
      BCACHE::Free(v48, v56);
    _InterlockedAnd((volatile signed __int32 *)this + 58, 0xFFFFEFFF);
    *((_QWORD *)this + 59) = 0;
  }
  if ( (*((_DWORD *)this + 58) & 0x180) != 0 )
    LRPC_SCALL::KillPipe(this, v22, 1, 1);
  else
    REFERENCED_OBJECT::RemoveReference(this);
  do
  {
LABEL_45:
    v29 = *(_QWORD *)(v9 + 200);
    if ( (_DWORD)v29 )
    {
      LRPC_SASSOCIATION::MessageReceivedWithClosePending((LRPC_SASSOCIATION *)v9);
      return;
    }
    v61 = v29 + 0x100000000LL;
  }
  while ( v29 != _InterlockedCompareExchange64((volatile signed __int64 *)(v9 + 200), v29 + 0x100000000LL, v29) );
  if ( dword_1800F9624 )
  {
    for ( m = 0; m < 4; ++m )
    {
      if ( `LogEventToEtw'::`2'::EtwEventSubjectFilter[m] == 65 )
        return;
    }
    if ( (Microsoft_Windows_RPCEnableBits & 8) != 0 )
    {
      v64 = 0;
      v61 = (unsigned __int64)(v29 + 0x100000000LL) >> 32;
      v71 = &v60;
      v65 = v9;
      v73 = &v59;
      v75 = (SecurityCacheEntry **)&v65;
      v77 = (int *)&v61;
      v79 = &v64;
      v59 = 81;
      v60 = 65;
      v72 = 1;
      v74 = 1;
      v76 = 8;
      v78 = 8;
      v80 = 8;
      McGenEventWrite_EtwEventWriteTransfer(
        (unsigned int)&RpcEtwGuid_Context,
        (unsigned int)RPCLogEvent,
        (unsigned __int64)(v29 + 0x100000000LL) >> 32,
        6,
        (__int64)v70);
    }
  }
}

```

## disassembly

```asm
0x18001a4f0  mov     [rsp-8+arg_10], rbx
0x18001a4f5  push    rbp
0x18001a4f6  push    rsi
0x18001a4f7  push    rdi
0x18001a4f8  push    r12
0x18001a4fa  push    r13
0x18001a4fc  push    r14
0x18001a4fe  push    r15
0x18001a500  lea     rbp, [rsp-10h]
0x18001a505  sub     rsp, 110h
0x18001a50c  mov     rax, cs:__security_cookie
0x18001a513  xor     rax, rsp
0x18001a516  mov     [rbp+40h+var_40], rax
0x18001a51a  mov     rax, [rbp+40h+arg_28]
0x18001a51e  lea     r15, [rcx+1A0h]
0x18001a525  mov     ebx, [rcx+214h]
0x18001a52b  mov     rsi, r8
0x18001a52e  mov     rdi, [rcx+130h]
0x18001a535  mov     r12, rdx
0x18001a538  mov     [rsp+140h+var_D8], rax
0x18001a53d  mov     r13, rcx
0x18001a540  mov     dword ptr [r15], 10h
0x18001a547  mov     [rsp+140h+var_E0], r9
0x18001a54c  mov     [rbp+40h+var_C0], rdx
0x18001a550  mov     dword ptr [rsp+140h+var_F0], 0
0x18001a558  test    bx, bx
0x18001a55b  jz      loc_18001AAED
0x18001a561  cmp     dword ptr [rdi+1D0h], 0
0x18001a568  jnz     loc_18001AB2E
0x18001a56e  cmp     dword ptr [rdi+1D4h], 0
0x18001a575  jnz     loc_18001AB2E
0x18001a57b  movups  xmm0, xmmword ptr [r12+8]
0x18001a581  mov     [r13+1C0h], rsi
0x18001a588  lea     rcx, [rdi+0F0h]
0x18001a58f  mov     [r13+1B8h], r12
0x18001a596  movups  xmmword ptr [r13+1F0h], xmm0
0x18001a59e  mov     esi, [r12+38h]
0x18001a5a3  call    cs:__imp_RtlAcquireSRWLockShared
0x18001a5a9  mov     edx, [rdi+48h]
0x18001a5ac  xor     ecx, ecx
0x18001a5ae  xchg    ax, ax
0x18001a5b0  cmp     ecx, edx
0x18001a5b2  jnb     short loc_18001A5DB
0x18001a5b4  lea     rbx, ds:0[rcx*8]
0x18001a5bc  lea     eax, [rcx+1]
0x18001a5bf  mov     rcx, [rdi+40h]
0x18001a5c3  cmp     qword ptr [rbx+rcx], 0
0x18001a5c8  jnz     short loc_18001A5CE
0x18001a5ca  mov     ecx, eax
0x18001a5cc  jmp     short loc_18001A5B0
0x18001a5ce  lfence
0x18001a5d1  mov     rcx, [rdi+40h]
0x18001a5d5  mov     rbx, [rbx+rcx]
0x18001a5d9  jmp     short loc_18001A5DF
0x18001a5db  xor     eax, eax
0x18001a5dd  xor     ebx, ebx
0x18001a5df  test    rbx, rbx
0x18001a5e2  jz      loc_18001AEA4
0x18001a5e8  cmp     [rbx+8], esi
0x18001a5eb  jz      short loc_18001A60C
0x18001a5ed  mov     r8d, [rdi+48h]
0x18001a5f1  cmp     eax, r8d
0x18001a5f4  jnb     short loc_18001A5DB
0x18001a5f6  mov     ecx, eax
0x18001a5f8  lea     edx, [rax+1]
0x18001a5fb  mov     rax, [rdi+40h]
0x18001a5ff  mov     rbx, [rax+rcx*8]
0x18001a603  mov     eax, edx
0x18001a605  test    rbx, rbx
0x18001a608  jz      short loc_18001A5F1
0x18001a60a  jmp     short loc_18001A5DF
0x18001a60c  lea     rcx, [rdi+0F0h]
0x18001a613  call    cs:__imp_RtlReleaseSRWLockShared
0x18001a619  mov     [r13+138h], rbx
0x18001a620  mov     rsi, [rbx]
0x18001a623  mov     eax, [r12+3Ch]
0x18001a628  mov     [r13+180h], r15
0x18001a62f  mov     r15, [rsp+140h+var_E0]
0x18001a634  mov     [r13+16Ch], eax
0x18001a63b  mov     [r13+150h], r13
0x18001a642  test    r15, r15
0x18001a645  jnz     loc_18001AA00
0x18001a64b  lea     rax, [r12+68h]
0x18001a650  mov     [r13+160h], rax
0x18001a657  movzx   eax, word ptr [r12+2]
0x18001a65d  sub     eax, 68h ; 'h'
0x18001a660  mov     [r13+168h], eax
0x18001a667  test    byte ptr [r12+30h], 4
0x18001a66d  jnz     loc_18001AEFF
0x18001a673  mov     eax, [r13+0E8h]
0x18001a67a  test    al, al
0x18001a67c  js      loc_18001ADB1
0x18001a682  mov     eax, 1000h
0x18001a687  xor     ebx, ebx
0x18001a689  mov     [r13+198h], eax
0x18001a690  mov     dword ptr [r13+158h], 10h
0x18001a69b  test    byte ptr [r12+30h], 1
0x18001a6a1  jnz     loc_18001A963
0x18001a6a7  mov     [r13+200h], ebx
0x18001a6ae  test    byte ptr [r12+30h], 8
0x18001a6b4  jnz     loc_18001ADF0
0x18001a6ba  cmp     qword ptr [rsi+48h], 0
0x18001a6bf  jz      loc_18001A9D1
0x18001a6c5  mov     eax, [rsi+8]
0x18001a6c8  bt      eax, 8
0x18001a6cc  jb      loc_18001AE5F
0x18001a6d2  mov     rax, [r13+0]
0x18001a6d6  lea     r8, [rsp+140h+var_E8]
0x18001a6db  mov     rdx, rsi
0x18001a6de  mov     [rsp+140h+var_E8], rbx
0x18001a6e3  mov     rcx, r13
0x18001a6e6  mov     [rsp+140h+var_C8], ebx
0x18001a6ea  mov     rax, [rax+1A8h]
0x18001a6f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a6f6  mov     ebx, eax
0x18001a6f8  test    eax, eax
0x18001a6fa  jnz     loc_18001AE16
0x18001a700  mov     eax, [rsi+8]
0x18001a703  mov     r14, [rsp+140h+var_E8]
0x18001a708  test    al, al
0x18001a70a  js      loc_18001AA4C
0x18001a710  mov     edx, [rsi+16Ch]; unsigned int
0x18001a716  mov     rcx, r14; this
0x18001a719  call    ?LookupCall@SecurityCacheEntry@@QEAAHK@Z; SecurityCacheEntry::LookupCall(ulong)
0x18001a71e  test    eax, eax
0x18001a720  jz      loc_18001AE16
0x18001a726  mov     eax, [rsi+8]
0x18001a729  test    al, 40h
0x18001a72b  jz      loc_18001A7F0
0x18001a731  call    ?RpcpConvertToLongRunning@@YAJXZ; RpcpConvertToLongRunning(void)
0x18001a736  test    eax, eax
0x18001a738  jnz     loc_18001AF5A
0x18001a73e  mov     rax, gs:30h
0x18001a747  mov     r14, 0ABABABABDEDEDEDEh
0x18001a751  mov     rdx, [rax+1698h]
0x18001a758  test    rdx, rdx
0x18001a75b  jz      short loc_18001A773
0x18001a75d  mov     rax, gs:30h
0x18001a766  xor     rdx, r14
0x18001a769  mov     rcx, [rax+48h]
0x18001a76d  cmp     [rdx+10h], rcx
0x18001a771  jnz     short loc_18001A7BA
0x18001a773  mov     [rdx+20h], r13
0x18001a777  lea     r8, [rsp+140h+var_C8]; int *
0x18001a77c  mov     dword ptr [rdx], 0
0x18001a782  mov     rcx, rsi; this
0x18001a785  mov     rdx, r13; void *
0x18001a788  call    ?DoSecurityCallbackHelper@RPC_INTERFACE@@QEAAJPEAXPEAH@Z; RPC_INTERFACE::DoSecurityCallbackHelper(void *,int *)
0x18001a78d  mov     ebx, eax
0x18001a78f  mov     rax, gs:30h
0x18001a798  mov     rdx, [rax+1698h]
0x18001a79f  test    rdx, rdx
0x18001a7a2  jz      short loc_18001A7C1
0x18001a7a4  mov     rax, gs:30h
0x18001a7ad  xor     rdx, r14
0x18001a7b0  mov     rcx, [rax+48h]
0x18001a7b4  cmp     [rdx+10h], rcx
0x18001a7b8  jz      short loc_18001A7C1
0x18001a7ba  mov     ecx, 1Eh
0x18001a7bf  int     29h; Win8: RtlFailFast(ecx)
0x18001a7c1  xor     eax, eax
0x18001a7c3  mov     [rdx+20h], rax
0x18001a7c7  mov     [rdx], eax
0x18001a7c9  test    ebx, ebx
0x18001a7cb  jnz     short loc_18001A7F0
0x18001a7cd  mov     r14, [rsp+140h+var_E8]
0x18001a7d2  test    r14, r14
0x18001a7d5  jz      short loc_18001A80D
0x18001a7d7  mov     eax, [rsi+8]
0x18001a7da  test    al, al
0x18001a7dc  js      loc_18001AB04
0x18001a7e2  mov     edx, [rsi+16Ch]; unsigned int
0x18001a7e8  mov     rcx, r14; this
0x18001a7eb  call    ?RememberCall@SecurityCacheEntry@@QEAAXK@Z; SecurityCacheEntry::RememberCall(ulong)
0x18001a7f0  mov     rdx, [rsp+140h+var_E8]
0x18001a7f5  test    rdx, rdx
0x18001a7f8  jz      short loc_18001A80D
0x18001a7fa  mov     rax, [r13+0]
0x18001a7fe  mov     rcx, r13
0x18001a801  mov     rax, [rax+1B0h]
0x18001a808  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a80d  test    ebx, ebx
0x18001a80f  jnz     loc_18001A981
0x18001a815  mov     rsi, [rsp+140h+var_D8]
0x18001a81a  test    rsi, rsi
0x18001a81d  jnz     loc_18001AA83
0x18001a823  mov     rcx, r13; this
0x18001a826  call    ?QueueOrDispatchCall@LRPC_SCALL@@AEAAXXZ; LRPC_SCALL::QueueOrDispatchCall(void)
0x18001a82b  lea     r14, ?EtwEventSubjectFilter@?1??LogEventToEtw@@YAXEE_J00@Z@4QBEB; "HbBr"
0x18001a832  nop     dword ptr [rax+00h]
0x18001a836  nop     word ptr [rax+rax+00000000h]
0x18001a840  mov     rdx, [rdi+0C8h]
0x18001a847  test    edx, edx
0x18001a849  jnz     loc_18001AA76
0x18001a84f  mov     rax, rdx
0x18001a852  mov     dword ptr [rsp+140h+var_F0], edx
0x18001a856  shr     rax, 20h
0x18001a85a  inc     eax
0x18001a85c  mov     dword ptr [rsp+140h+var_F0+4], eax
0x18001a860  mov     rax, rdx
0x18001a863  mov     rcx, [rsp+140h+var_F0]
0x18001a868  mov     r8, rcx
0x18001a86b  shr     r8, 20h
0x18001a86f  lock cmpxchg [rdi+0C8h], rcx
0x18001a878  jnz     short loc_18001A840
0x18001a87a  cmp     cs:dword_1800F9624, edx
0x18001a880  jz      short loc_18001A8A4
0x18001a882  xor     r9d, r9d
0x18001a885  mov     ecx, r9d
0x18001a888  cmp     ecx, 4
0x18001a88b  jnb     short loc_18001A89B
0x18001a88d  movsxd  rax, ecx
0x18001a890  cmp     byte ptr [rax+r14], 41h ; 'A'
0x18001a895  jz      short loc_18001A8A4
0x18001a897  inc     ecx
0x18001a899  jmp     short loc_18001A888
0x18001a89b  test    cs:Microsoft_Windows_RPCEnableBits, 8
0x18001a8a2  jnz     short loc_18001A8CB
0x18001a8a4  mov     rcx, [rbp+40h+var_40]
0x18001a8a8  xor     rcx, rsp; StackCookie
0x18001a8ab  call    __security_check_cookie
0x18001a8b0  mov     rbx, [rsp+140h+arg_10]
0x18001a8b8  add     rsp, 110h
0x18001a8bf  pop     r15
0x18001a8c1  pop     r14
0x18001a8c3  pop     r13
0x18001a8c5  pop     r12
0x18001a8c7  pop     rdi
0x18001a8c8  pop     rsi
0x18001a8c9  pop     rbp
0x18001a8ca  retn
0x18001a8cb  movsxd  rax, edx
0x18001a8ce  lea     rcx, RpcEtwGuid_Context
0x18001a8d5  mov     [rsp+140h+var_D8], rax
0x18001a8da  lea     rdx, RPCLogEvent
0x18001a8e1  lea     rax, [rsp+140h+var_F8]
0x18001a8e6  mov     [rsp+140h+var_F0], r8
0x18001a8eb  mov     [rbp+40h+var_90], rax
0x18001a8ef  mov     r9d, 6
0x18001a8f5  lea     rax, [rsp+140h+var_100]
0x18001a8fa  mov     [rsp+140h+var_D0], rdi
0x18001a8ff  mov     [rbp+40h+var_80], rax
0x18001a903  lea     rax, [rsp+140h+var_D0]
0x18001a908  mov     [rbp+40h+var_70], rax
0x18001a90c  lea     rax, [rsp+140h+var_F0]
0x18001a911  mov     [rbp+40h+var_60], rax
0x18001a915  lea     rax, [rsp+140h+var_D8]
0x18001a91a  mov     [rbp+40h+var_50], rax
0x18001a91e  lea     rax, [rbp+40h+var_A0]
0x18001a922  mov     [rsp+140h+var_120], rax
0x18001a927  mov     [rsp+140h+var_100], 51h ; 'Q'
0x18001a92c  mov     [rsp+140h+var_F8], 41h ; 'A'
0x18001a931  mov     [rbp+40h+var_88], 1
0x18001a939  mov     [rbp+40h+var_78], 1
0x18001a941  mov     [rbp+40h+var_68], 8
0x18001a949  mov     [rbp+40h+var_58], 8
0x18001a951  mov     [rbp+40h+var_48], 8
0x18001a959  call    McGenEventWrite_EtwEventWriteTransfer
0x18001a95e  jmp     loc_18001A8A4
0x18001a963  mov     dword ptr [r13+200h], 1
0x18001a96e  movups  xmm0, xmmword ptr [r12+58h]
0x18001a974  movups  xmmword ptr [r13+204h], xmm0
0x18001a97c  jmp     loc_18001A6AE
0x18001a981  cmp     ebx, 3E5h
0x18001a987  jz      loc_18001A82B
0x18001a98d  mov     rax, [r13+138h]
0x18001a994  mov     r8d, 1Fh; unsigned __int16
0x18001a99a  mov     r9d, 1; int
0x18001a9a0  mov     dword ptr [rbp+40h+var_B8], 3
0x18001a9a7  mov     edx, ebx; int
0x18001a9a9  mov     rcx, [rax]
0x18001a9ac  mov     eax, [rcx+54h]
0x18001a9af  mov     ecx, 2; unsigned int
0x18001a9b4  mov     dword ptr [rbp+40h+var_B8+8], eax
0x18001a9b7  lea     rax, [rbp+40h+var_B8]
0x18001a9bb  mov     [rsp+140h+var_120], rax; struct tagParam *
0x18001a9c0  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x18001a9c5  lea     r14, ?EtwEventSubjectFilter@?1??LogEventToEtw@@YAXEE_J00@Z@4QBEB; "HbBr"
0x18001a9cc  jmp     loc_18001ABBE
0x18001a9d1  cmp     qword ptr [rsi+230h], 0
0x18001a9d9  jnz     loc_18001A6C5
0x18001a9df  mov     rax, [r13+0]
0x18001a9e3  mov     rcx, r13
0x18001a9e6  mov     rax, [rax+1E8h]
0x18001a9ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a9f2  test    rax, rax
0x18001a9f5  jz      loc_18001A815
0x18001a9fb  jmp     loc_18001A6C5
0x18001aa00  mov     rcx, r15
0x18001aa03  mov     rax, r15
0x18001aa06  xor     rax, 1
0x18001aa0a  and     ecx, 1
0x18001aa0d  test    rcx, rcx
0x18001aa10  mov     [rsp+140h+var_F0], rcx
0x18001aa15  cmovz   rax, r15
0x18001aa19  mov     [rsp+140h+var_E0], rax
0x18001aa1e  mov     r15, rax
0x18001aa21  mov     [r13+160h], rax
0x18001aa28  mov     eax, dword ptr [rbp+40h+arg_20]
0x18001aa2b  mov     [r13+168h], eax
  ... truncated ...
```
