# LRPC_SCALL::HandleRequest(_PORT_MESSAGE *,_PORT_MESSAGE *,void *,unsigned __int64,RPCP_ALPC_HANDLE_ATTR *)

- ea: `0x18001b4d0`
- end: `0x18001bfec`
- name: `?HandleRequest@LRPC_SCALL@@QEAAXPEAU_PORT_MESSAGE@@0PEAX_KPEAVRPCP_ALPC_HANDLE_ATTR@@@Z`
- size: `2844`
- prototype: `void __fastcall(LRPC_SCALL *this, struct _PORT_MESSAGE *, struct _PORT_MESSAGE *, __int64, unsigned __int64, struct RPCP_ALPC_HANDLE_ATTR *)`
- caller_count: `2`
- callee_count: `33`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001a690`
- `0x180020140`

## callees

- `0x180015a1c`
- `0x1800162e0`
- `0x18001a170`
- `0x18001a20c`
- `0x18001a264`
- `0x18001a30c`
- `0x18001ae5c`
- `0x18001aecc`
- `0x18001af00`
- `0x18001b2c0`
- `0x18001b4d0`
- `0x18001bff4`
- `0x18001d170`
- `0x18001e6d0`
- `0x180022fb8`
- `0x180023020`
- `0x180025d70`
- `0x180028670`
- `0x180028f44`
- `0x180028fcc`
- `0x180029018`
- `0x1800295d8`
- `0x18007a8c4`
- `0x180083ff0`
- `0x180085138`
- `0x180085260`
- `0x18008bfe8`
- `0x18008c61c`
- `0x180097b90`
- `0x1800a112c`
- `0x1800a84a4`
- `0x1800ceda0`
- `0x1800d7010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18001bb35`
- `ntdll!RtlLeaveCriticalSection` at `0x18001be36`
- `ntdll!RtlLeaveCriticalSection` at `0x18001bb35`
- `ntdll!RtlLeaveCriticalSection` at `0x18001be36`
- `ntdll!RtlEnterCriticalSection` at `0x18001bb13`
- `ntdll!RtlEnterCriticalSection` at `0x18001bb13`
- `ntdll!RtlReleaseSRWLockShared` at `0x18001b5f7`
- `ntdll!RtlReleaseSRWLockShared` at `0x18001bea1`
- `ntdll!RtlReleaseSRWLockShared` at `0x18001b5f7`
- `ntdll!RtlReleaseSRWLockShared` at `0x18001bea1`
- `ntdll!RtlAcquireSRWLockShared` at `0x18001b583`
- `ntdll!RtlAcquireSRWLockShared` at `0x18001b583`
- `ntdll!AlpcFreeCompletionListMessage` at `0x18001bd78`
- `ntdll!AlpcFreeCompletionListMessage` at `0x18001bd78`

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
  RtlAcquireSRWLockShared(v9 + 240, a2);
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
      if ( dword_1800FE624 )
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
    if ( dword_1800FE624 )
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
  if ( dword_1800FE624 )
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
0x18001b4d0  mov     [rsp-8+arg_10], rbx
0x18001b4d5  push    rbp
0x18001b4d6  push    rsi
0x18001b4d7  push    rdi
0x18001b4d8  push    r12
0x18001b4da  push    r13
0x18001b4dc  push    r14
0x18001b4de  push    r15
0x18001b4e0  lea     rbp, [rsp-10h]
0x18001b4e5  sub     rsp, 110h
0x18001b4ec  mov     rax, cs:__security_cookie
0x18001b4f3  xor     rax, rsp
0x18001b4f6  mov     [rbp+40h+var_40], rax
0x18001b4fa  mov     rax, [rbp+40h+arg_28]
0x18001b4fe  lea     r15, [rcx+1A0h]
0x18001b505  mov     ebx, [rcx+214h]
0x18001b50b  mov     rsi, r8
0x18001b50e  mov     rdi, [rcx+130h]
0x18001b515  mov     r12, rdx
0x18001b518  mov     [rsp+140h+var_D8], rax
0x18001b51d  mov     r13, rcx
0x18001b520  mov     dword ptr [r15], 10h
0x18001b527  mov     [rsp+140h+var_E0], r9
0x18001b52c  mov     [rbp+40h+var_C0], rdx
0x18001b530  mov     dword ptr [rsp+140h+var_F0], 0
0x18001b538  test    bx, bx
0x18001b53b  jz      loc_18001BACE
0x18001b541  cmp     dword ptr [rdi+1D0h], 0
0x18001b548  jnz     loc_18001BB0F
0x18001b54e  cmp     dword ptr [rdi+1D4h], 0
0x18001b555  jnz     loc_18001BB0F
0x18001b55b  movups  xmm0, xmmword ptr [r12+8]
0x18001b561  mov     [r13+1C0h], rsi
0x18001b568  lea     rcx, [rdi+0F0h]
0x18001b56f  mov     [r13+1B8h], r12
0x18001b576  movups  xmmword ptr [r13+1F0h], xmm0
0x18001b57e  mov     esi, [r12+38h]
0x18001b583  call    cs:__imp_RtlAcquireSRWLockShared
0x18001b58a  nop     dword ptr [rax+rax+00h]
0x18001b58f  mov     edx, [rdi+48h]
0x18001b592  xor     ecx, ecx
0x18001b594  cmp     ecx, edx
0x18001b596  jnb     short loc_18001B5BF
0x18001b598  lea     rbx, ds:0[rcx*8]
0x18001b5a0  lea     eax, [rcx+1]
0x18001b5a3  mov     rcx, [rdi+40h]
0x18001b5a7  cmp     qword ptr [rbx+rcx], 0
0x18001b5ac  jnz     short loc_18001B5B2
0x18001b5ae  mov     ecx, eax
0x18001b5b0  jmp     short loc_18001B594
0x18001b5b2  lfence
0x18001b5b5  mov     rcx, [rdi+40h]
0x18001b5b9  mov     rbx, [rbx+rcx]
0x18001b5bd  jmp     short loc_18001B5C3
0x18001b5bf  xor     eax, eax
0x18001b5c1  xor     ebx, ebx
0x18001b5c3  test    rbx, rbx
0x18001b5c6  jz      loc_18001BE9A
0x18001b5cc  cmp     [rbx+8], esi
0x18001b5cf  jz      short loc_18001B5F0
0x18001b5d1  mov     r8d, [rdi+48h]
0x18001b5d5  cmp     eax, r8d
0x18001b5d8  jnb     short loc_18001B5BF
0x18001b5da  mov     ecx, eax
0x18001b5dc  lea     edx, [rax+1]
0x18001b5df  mov     rax, [rdi+40h]
0x18001b5e3  mov     rbx, [rax+rcx*8]
0x18001b5e7  mov     eax, edx
0x18001b5e9  test    rbx, rbx
0x18001b5ec  jz      short loc_18001B5D5
0x18001b5ee  jmp     short loc_18001B5C3
0x18001b5f0  lea     rcx, [rdi+0F0h]
0x18001b5f7  call    cs:__imp_RtlReleaseSRWLockShared
0x18001b5fe  nop     dword ptr [rax+rax+00h]
0x18001b603  mov     [r13+138h], rbx
0x18001b60a  mov     rsi, [rbx]
0x18001b60d  mov     eax, [r12+3Ch]
0x18001b612  mov     [r13+180h], r15
0x18001b619  mov     r15, [rsp+140h+var_E0]
0x18001b61e  mov     [r13+16Ch], eax
0x18001b625  mov     [r13+150h], r13
0x18001b62c  test    r15, r15
0x18001b62f  jnz     loc_18001B9E1
0x18001b635  lea     rax, [r12+68h]
0x18001b63a  mov     [r13+160h], rax
0x18001b641  movzx   eax, word ptr [r12+2]
0x18001b647  sub     eax, 68h ; 'h'
0x18001b64a  mov     [r13+168h], eax
0x18001b651  test    byte ptr [r12+30h], 4
0x18001b657  jnz     loc_18001BEFB
0x18001b65d  mov     eax, [r13+0E8h]
0x18001b664  test    al, al
0x18001b666  js      loc_18001BDA4
0x18001b66c  mov     eax, 1000h
0x18001b671  xor     ebx, ebx
0x18001b673  mov     [r13+198h], eax
0x18001b67a  mov     dword ptr [r13+158h], 10h
0x18001b685  test    byte ptr [r12+30h], 1
0x18001b68b  jnz     loc_18001B944
0x18001b691  mov     [r13+200h], ebx
0x18001b698  test    byte ptr [r12+30h], 8
0x18001b69e  jnz     loc_18001BDE0
0x18001b6a4  cmp     qword ptr [rsi+48h], 0
0x18001b6a9  jz      loc_18001B9B2
0x18001b6af  mov     eax, [rsi+8]
0x18001b6b2  bt      eax, 8
0x18001b6b6  jb      loc_18001BE55
0x18001b6bc  mov     rax, [r13+0]
0x18001b6c0  lea     r8, [rsp+140h+var_E8]
0x18001b6c5  mov     rdx, rsi
0x18001b6c8  mov     [rsp+140h+var_E8], rbx
0x18001b6cd  mov     rcx, r13
0x18001b6d0  mov     [rsp+140h+var_C8], ebx
0x18001b6d4  mov     rax, [rax+1A8h]
0x18001b6db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b6e0  mov     ebx, eax
0x18001b6e2  test    eax, eax
0x18001b6e4  jnz     loc_18001BE06
0x18001b6ea  mov     eax, [rsi+8]
0x18001b6ed  mov     r14, [rsp+140h+var_E8]
0x18001b6f2  test    al, al
0x18001b6f4  js      loc_18001BA2D
0x18001b6fa  mov     edx, [rsi+16Ch]; unsigned int
0x18001b700  mov     rcx, r14; this
0x18001b703  call    ?LookupCall@SecurityCacheEntry@@QEAAHK@Z; SecurityCacheEntry::LookupCall(ulong)
0x18001b708  test    eax, eax
0x18001b70a  jz      loc_18001BE06
0x18001b710  mov     eax, [rsi+8]
0x18001b713  test    al, 40h
0x18001b715  jz      loc_18001B7DA
0x18001b71b  call    ?RpcpConvertToLongRunning@@YAJXZ; RpcpConvertToLongRunning(void)
0x18001b720  test    eax, eax
0x18001b722  jnz     loc_18001BF56
0x18001b728  mov     rax, gs:30h
0x18001b731  mov     r14, 0ABABABABDEDEDEDEh
0x18001b73b  mov     rdx, [rax+1698h]
0x18001b742  test    rdx, rdx
0x18001b745  jz      short loc_18001B75D
0x18001b747  mov     rax, gs:30h
0x18001b750  xor     rdx, r14
0x18001b753  mov     rcx, [rax+48h]
0x18001b757  cmp     [rdx+10h], rcx
0x18001b75b  jnz     short loc_18001B7A4
0x18001b75d  mov     [rdx+20h], r13
0x18001b761  lea     r8, [rsp+140h+var_C8]; int *
0x18001b766  mov     dword ptr [rdx], 0
0x18001b76c  mov     rcx, rsi; this
0x18001b76f  mov     rdx, r13; void *
0x18001b772  call    ?DoSecurityCallbackHelper@RPC_INTERFACE@@QEAAJPEAXPEAH@Z; RPC_INTERFACE::DoSecurityCallbackHelper(void *,int *)
0x18001b777  mov     ebx, eax
0x18001b779  mov     rax, gs:30h
0x18001b782  mov     rdx, [rax+1698h]
0x18001b789  test    rdx, rdx
0x18001b78c  jz      short loc_18001B7AB
0x18001b78e  mov     rax, gs:30h
0x18001b797  xor     rdx, r14
0x18001b79a  mov     rcx, [rax+48h]
0x18001b79e  cmp     [rdx+10h], rcx
0x18001b7a2  jz      short loc_18001B7AB
0x18001b7a4  mov     ecx, 1Eh
0x18001b7a9  int     29h; Win8: RtlFailFast(ecx)
0x18001b7ab  xor     eax, eax
0x18001b7ad  mov     [rdx+20h], rax
0x18001b7b1  mov     [rdx], eax
0x18001b7b3  test    ebx, ebx
0x18001b7b5  jnz     short loc_18001B7DA
0x18001b7b7  mov     r14, [rsp+140h+var_E8]
0x18001b7bc  test    r14, r14
0x18001b7bf  jz      short loc_18001B7F7
0x18001b7c1  mov     eax, [rsi+8]
0x18001b7c4  test    al, al
0x18001b7c6  js      loc_18001BAE5
0x18001b7cc  mov     edx, [rsi+16Ch]; unsigned int
0x18001b7d2  mov     rcx, r14; this
0x18001b7d5  call    ?RememberCall@SecurityCacheEntry@@QEAAXK@Z; SecurityCacheEntry::RememberCall(ulong)
0x18001b7da  mov     rdx, [rsp+140h+var_E8]
0x18001b7df  test    rdx, rdx
0x18001b7e2  jz      short loc_18001B7F7
0x18001b7e4  mov     rax, [r13+0]
0x18001b7e8  mov     rcx, r13
0x18001b7eb  mov     rax, [rax+1B0h]
0x18001b7f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b7f7  test    ebx, ebx
0x18001b7f9  jnz     loc_18001B962
0x18001b7ff  mov     rsi, [rsp+140h+var_D8]
0x18001b804  test    rsi, rsi
0x18001b807  jnz     loc_18001BA64
0x18001b80d  mov     rcx, r13; this
0x18001b810  call    ?QueueOrDispatchCall@LRPC_SCALL@@AEAAXXZ; LRPC_SCALL::QueueOrDispatchCall(void)
0x18001b815  lea     r14, ?EtwEventSubjectFilter@?1??LogEventToEtw@@YAXEE_J00@Z@4QBEB; "HbBr"
0x18001b81c  nop     dword ptr [rax+00h]
0x18001b820  mov     rdx, [rdi+0C8h]
0x18001b827  test    edx, edx
0x18001b829  jnz     loc_18001BA57
0x18001b82f  mov     rax, rdx
0x18001b832  mov     dword ptr [rsp+140h+var_F0], edx
0x18001b836  shr     rax, 20h
0x18001b83a  inc     eax
0x18001b83c  mov     dword ptr [rsp+140h+var_F0+4], eax
0x18001b840  mov     rax, rdx
0x18001b843  mov     rcx, [rsp+140h+var_F0]
0x18001b848  mov     r8, rcx
0x18001b84b  shr     r8, 20h
0x18001b84f  lock cmpxchg [rdi+0C8h], rcx
0x18001b858  jnz     short loc_18001B820
0x18001b85a  cmp     cs:dword_1800FE624, edx
0x18001b860  jz      short loc_18001B884
0x18001b862  xor     r9d, r9d
0x18001b865  mov     ecx, r9d
0x18001b868  cmp     ecx, 4
0x18001b86b  jnb     short loc_18001B87B
0x18001b86d  movsxd  rax, ecx
0x18001b870  cmp     byte ptr [rax+r14], 41h ; 'A'
0x18001b875  jz      short loc_18001B884
0x18001b877  inc     ecx
0x18001b879  jmp     short loc_18001B868
0x18001b87b  test    cs:Microsoft_Windows_RPCEnableBits, 8
0x18001b882  jnz     short loc_18001B8AC
0x18001b884  mov     rcx, [rbp+40h+var_40]
0x18001b888  xor     rcx, rsp; StackCookie
0x18001b88b  call    __security_check_cookie
0x18001b890  mov     rbx, [rsp+140h+arg_10]
0x18001b898  add     rsp, 110h
0x18001b89f  pop     r15
0x18001b8a1  pop     r14
0x18001b8a3  pop     r13
0x18001b8a5  pop     r12
0x18001b8a7  pop     rdi
0x18001b8a8  pop     rsi
0x18001b8a9  pop     rbp
0x18001b8aa  retn
0x18001b8ac  movsxd  rax, edx
0x18001b8af  lea     rcx, RpcEtwGuid_Context
0x18001b8b6  mov     [rsp+140h+var_D8], rax
0x18001b8bb  lea     rdx, RPCLogEvent
0x18001b8c2  lea     rax, [rsp+140h+var_F8]
0x18001b8c7  mov     [rsp+140h+var_F0], r8
0x18001b8cc  mov     [rbp+40h+var_90], rax
0x18001b8d0  mov     r9d, 6
0x18001b8d6  lea     rax, [rsp+140h+var_100]
0x18001b8db  mov     [rsp+140h+var_D0], rdi
0x18001b8e0  mov     [rbp+40h+var_80], rax
0x18001b8e4  lea     rax, [rsp+140h+var_D0]
0x18001b8e9  mov     [rbp+40h+var_70], rax
0x18001b8ed  lea     rax, [rsp+140h+var_F0]
0x18001b8f2  mov     [rbp+40h+var_60], rax
0x18001b8f6  lea     rax, [rsp+140h+var_D8]
0x18001b8fb  mov     [rbp+40h+var_50], rax
0x18001b8ff  lea     rax, [rbp+40h+var_A0]
0x18001b903  mov     [rsp+140h+var_120], rax
0x18001b908  mov     [rsp+140h+var_100], 51h ; 'Q'
0x18001b90d  mov     [rsp+140h+var_F8], 41h ; 'A'
0x18001b912  mov     [rbp+40h+var_88], 1
0x18001b91a  mov     [rbp+40h+var_78], 1
0x18001b922  mov     [rbp+40h+var_68], 8
0x18001b92a  mov     [rbp+40h+var_58], 8
0x18001b932  mov     [rbp+40h+var_48], 8
0x18001b93a  call    McGenEventWrite_EtwEventWriteTransfer
0x18001b93f  jmp     loc_18001B884
0x18001b944  mov     dword ptr [r13+200h], 1
0x18001b94f  movups  xmm0, xmmword ptr [r12+58h]
0x18001b955  movups  xmmword ptr [r13+204h], xmm0
0x18001b95d  jmp     loc_18001B698
0x18001b962  cmp     ebx, 3E5h
0x18001b968  jz      loc_18001B815
0x18001b96e  mov     rax, [r13+138h]
0x18001b975  mov     r8d, 1Fh; unsigned __int16
0x18001b97b  mov     r9d, 1; int
0x18001b981  mov     dword ptr [rbp+40h+var_B8], 3
0x18001b988  mov     edx, ebx; int
0x18001b98a  mov     rcx, [rax]
0x18001b98d  mov     eax, [rcx+54h]
0x18001b990  mov     ecx, 2; unsigned int
0x18001b995  mov     dword ptr [rbp+40h+var_B8+8], eax
0x18001b998  lea     rax, [rbp+40h+var_B8]
0x18001b99c  mov     [rsp+140h+var_120], rax; struct tagParam *
0x18001b9a1  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x18001b9a6  lea     r14, ?EtwEventSubjectFilter@?1??LogEventToEtw@@YAXEE_J00@Z@4QBEB; "HbBr"
0x18001b9ad  jmp     loc_18001BBAB
0x18001b9b2  cmp     qword ptr [rsi+230h], 0
0x18001b9ba  jnz     loc_18001B6AF
0x18001b9c0  mov     rax, [r13+0]
0x18001b9c4  mov     rcx, r13
0x18001b9c7  mov     rax, [rax+1E8h]
0x18001b9ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b9d3  test    rax, rax
0x18001b9d6  jz      loc_18001B7FF
0x18001b9dc  jmp     loc_18001B6AF
0x18001b9e1  mov     rcx, r15
0x18001b9e4  mov     rax, r15
0x18001b9e7  xor     rax, 1
0x18001b9eb  and     ecx, 1
0x18001b9ee  test    rcx, rcx
0x18001b9f1  mov     [rsp+140h+var_F0], rcx
0x18001b9f6  cmovz   rax, r15
0x18001b9fa  mov     [rsp+140h+var_E0], rax
0x18001b9ff  mov     r15, rax
0x18001ba02  mov     [r13+160h], rax
0x18001ba09  mov     eax, dword ptr [rbp+40h+arg_20]
0x18001ba0c  mov     [r13+168h], eax
  ... truncated ...
```
