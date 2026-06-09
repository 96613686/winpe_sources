# LRPC_SCALL::QueueOrDispatchCall(void)

- ea: `0x18001d170`
- end: `0x18001dbd0`
- name: `?QueueOrDispatchCall@LRPC_SCALL@@AEAAXXZ`
- size: `2656`
- prototype: `void __fastcall(LRPC_SCALL *__hidden this)`
- caller_count: `2`
- callee_count: `33`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001b4d0`
- `0x1800abf30`

## callees

- `0x18000e69c`
- `0x1800152d8`
- `0x180015948`
- `0x1800162e0`
- `0x1800182c0`
- `0x180019e3c`
- `0x18001a008`
- `0x18001a30c`
- `0x18001d170`
- `0x18001e690`
- `0x18001e7d0`
- `0x180022e80`
- `0x180022fb8`
- `0x180023b80`
- `0x180025d70`
- `0x1800263a0`
- `0x180027e90`
- `0x180028670`
- `0x1800292c0`
- `0x1800295d8`
- `0x180029c18`
- `0x180029c38`
- `0x18003227c`
- `0x180059a38`
- `0x18007a664`
- `0x18007a698`
- `0x18007a8c4`
- `0x18009858c`
- `0x1800a1c34`
- `0x1800ac41c`
- `0x1800b8778`
- `0x1800ceda0`
- `0x1800d7010`

## import_xrefs

- `ntdll!NtAlpcSendWaitReceivePort` at `0x18001d484`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x18001d484`
- `ntdll!RtlLeaveCriticalSection` at `0x18001d74d`
- `ntdll!RtlLeaveCriticalSection` at `0x18001d8d4`
- `ntdll!RtlLeaveCriticalSection` at `0x18001dba6`
- `ntdll!RtlLeaveCriticalSection` at `0x18001d74d`
- `ntdll!RtlLeaveCriticalSection` at `0x18001d8d4`
- `ntdll!RtlLeaveCriticalSection` at `0x18001dba6`
- `ntdll!RtlEnterCriticalSection` at `0x18001d6c0`
- `ntdll!RtlEnterCriticalSection` at `0x18001d6c0`
- `ntdll!TpWorkOnBehalfClearTicket` at `0x18001d20c`
- `ntdll!TpWorkOnBehalfClearTicket` at `0x18001d40c`
- `ntdll!TpWorkOnBehalfClearTicket` at `0x18001d20c`
- `ntdll!TpWorkOnBehalfClearTicket` at `0x18001d40c`
- `ntdll!TpCallbackSendAlpcMessageOnCompletion` at `0x18001d339`
- `ntdll!TpCallbackSendAlpcMessageOnCompletion` at `0x18001d339`
- `ntdll!AlpcFreeCompletionListMessage` at `0x18001d792`
- `ntdll!AlpcFreeCompletionListMessage` at `0x18001d792`

## pseudocode

```c
void __fastcall LRPC_SCALL::QueueOrDispatchCall(LRPC_SCALL *this)
{
  _DWORD *v1; // r15
  LRPC_SASSOCIATION *v3; // rcx
  struct LRPC_SCAUSAL_FLOW *v4; // r12
  __int64 v5; // rax
  int v6; // r13d
  struct THREAD *v7; // rax
  int v8; // eax
  BCACHE *v9; // rcx
  __int64 v10; // r8
  int v11; // r14d
  int v12; // edi
  const char *v13; // r9
  __int16 *v14; // rsi
  __int64 v15; // r15
  unsigned int v16; // edx
  unsigned int i; // ecx
  unsigned __int64 ReservedForNtRpc; // rdi
  __int64 v19; // rcx
  int v20; // edx
  int v21; // r9d
  BCACHE *v22; // rdi
  __int64 v23; // rsi
  BCACHE *v24; // rcx
  __int64 v25; // rdx
  unsigned int j; // ecx
  struct THREAD *v27; // rax
  __int64 v28; // rsi
  struct THREAD *ThreadPointer; // rax
  struct tagExtendedErrorInfo *v30; // r15
  unsigned int v31; // edx
  const char *v32; // r8
  int v33; // r13d
  _BYTE *v34; // r14
  int v35; // ebx
  _QWORD **v36; // r13
  struct LRPC_SCAUSAL_FLOW *v37; // r9
  int v38; // edx
  bool v39; // zf
  _QWORD *v40; // rcx
  unsigned int v41; // r8d
  int v42; // eax
  int v43; // edi
  struct LRPC_SYSTEM_HANDLE_DATA *v44; // rax
  struct THREAD *v45; // rax
  int v46; // eax
  void *v47; // rdx
  int v48; // eax
  struct tagExtendedErrorInfo *v49; // rax
  unsigned __int64 v50; // r8
  __int64 v51; // rcx
  void *v52; // rdx
  signed __int32 v53[8]; // [rsp+0h] [rbp-B9h] BYREF
  unsigned __int64 v54; // [rsp+28h] [rbp-91h]
  struct LRPC_SYSTEM_HANDLE_DATA *v55; // [rsp+30h] [rbp-89h]
  char v56; // [rsp+40h] [rbp-79h] BYREF
  char v57; // [rsp+48h] [rbp-71h] BYREF
  struct LRPC_SCAUSAL_FLOW *v58; // [rsp+50h] [rbp-69h] BYREF
  int v59[2]; // [rsp+58h] [rbp-61h] BYREF
  int v60[2]; // [rsp+60h] [rbp-59h] BYREF
  _DWORD *v61; // [rsp+68h] [rbp-51h]
  LRPC_SASSOCIATION *v62; // [rsp+70h] [rbp-49h]
  _BYTE v63[16]; // [rsp+80h] [rbp-39h] BYREF
  char *v64; // [rsp+90h] [rbp-29h]
  __int64 v65; // [rsp+98h] [rbp-21h]
  char *v66; // [rsp+A0h] [rbp-19h]
  __int64 v67; // [rsp+A8h] [rbp-11h]
  struct LRPC_SCAUSAL_FLOW **v68; // [rsp+B0h] [rbp-9h]
  __int64 v69; // [rsp+B8h] [rbp-1h]
  int *v70; // [rsp+C0h] [rbp+7h]
  __int64 v71; // [rsp+C8h] [rbp+Fh]
  int *v72; // [rsp+D0h] [rbp+17h]
  __int64 v73; // [rsp+D8h] [rbp+1Fh]

  v1 = 0;
  v3 = (LRPC_SASSOCIATION *)*((_QWORD *)this + 38);
  v4 = 0;
  v58 = 0;
  v62 = v3;
  v5 = *((_QWORD *)this + 55);
  v59[0] = 0;
  LODWORD(v61) = 0;
  if ( (*(_BYTE *)(v5 + 48) & 2) != 0 )
  {
    *((_DWORD *)this + 144) = *(_DWORD *)(v5 + 80);
    v60[0] = 0;
    v42 = LRPC_SASSOCIATION::MaybeQueueCall(v3, this, v60, &v58);
    v43 = v42;
    if ( v42 )
    {
      RpcpErrorAddRecord(2u, v42, 0x514u, 0, 0);
      LRPC_ADDRESS::RpcFreeLrpcAddressBuffer(*(LRPC_ADDRESS **)(*((_QWORD *)this + 38) + 56LL), *((void **)this + 55));
      *((_QWORD *)this + 55) = 0;
      LRPC_SCALL::PostDispatchCleanup(this, v43, v43 == 14);
      return;
    }
    if ( v60[0] )
    {
      (*(void (__fastcall **)(struct LRPC_SCAUSAL_FLOW *))(*(_QWORD *)v58 + 32LL))(v58);
      return;
    }
    v4 = v58;
    if ( v58 )
    {
      if ( dword_1800FE624 )
        LogEventToEtw(0x46u, 0x6Bu, (__int64)this, *((_QWORD *)v58 + 7), *((unsigned int *)this + 144));
      LODWORD(v61) = *((_DWORD *)this + 144);
    }
  }
  if ( (*((_DWORD *)this + 58) & 0x10000) == 0
    || this == (LRPC_SCALL *)-648LL
    || (unsigned int)RpcpSetThreadWorkOnBehalfTicket((LRPC_SCALL *)((char *)this + 648)) )
  {
    v6 = 0;
    v7 = ThreadSelf();
    if ( v7 )
      TpWorkOnBehalfClearTicket(*((_QWORD *)v7 + 24));
  }
  else
  {
    v6 = 1;
  }
  v8 = LRPC_SCALL::DispatchRequest(this, v59);
  v11 = v59[0];
  v12 = v8;
  if ( v8 )
  {
    v28 = *((_QWORD *)this + 56);
    ThreadPointer = RpcpGetThreadPointer();
    if ( ThreadPointer )
    {
      v30 = (struct tagExtendedErrorInfo *)*((_QWORD *)ThreadPointer + 10);
      if ( v30 )
      {
        if ( g_fSendEEInfo )
        {
          v58 = 0;
          v49 = RpcpGetAndLockEEInfo();
          if ( v49 && !(unsigned int)GetLengthOfPickledEEInfo(v49, (unsigned __int64 *)&v58) && v58 )
          {
            TrimIfNecessaryAndSetImmediateBuffer((struct _LRPC_FAULT_MESSAGE *)v28, v12, v50, v30, 0, 0);
            v1 = 0;
            goto LABEL_59;
          }
        }
        else if ( (unsigned int)IsEEInfoEtwEnabled() )
        {
          LogEEInfoToEtw();
        }
      }
      v1 = 0;
    }
    *(_DWORD *)(v28 + 52) = 0;
    *(_QWORD *)(v28 + 40) = 2;
    *(_DWORD *)(v28 + 48) = v12;
    *(_QWORD *)v28 = 3932180;
    *(_QWORD *)(v28 + 32) = 0;
LABEL_59:
    LRPC_SYSTEM_HANDLE_DATA::CleanupSystemHandles((LRPC_SCALL *)((char *)this + 608), 1u);
    if ( *((_QWORD *)this + 58) )
    {
      LRPC_ADDRESS::AlpcFreeSection(*(LRPC_ADDRESS **)(*((_QWORD *)this + 38) + 56LL), *((void **)this + 57));
      v51 = *((_QWORD *)this + 38);
      v52 = (void *)*((_QWORD *)this + 58);
      *((_QWORD *)this + 57) = 0;
      LRPC_ADDRESS::AlpcFreeView(*(LRPC_ADDRESS **)(v51 + 56), v52);
      *((_QWORD *)this + 58) = 0;
    }
    LRPC_SCALL::SendReply(this);
    if ( (*((_DWORD *)this + 58) & 0x180) != 0 )
      LRPC_SCALL::KillPipe(this, v12, 1, 1);
    else
      REFERENCED_OBJECT::RemoveReference(this);
    goto LABEL_44;
  }
  v13 = "HbBr";
  if ( !v59[0] )
  {
    if ( *((_QWORD *)this + 58) || (*((_DWORD *)this + 58) & 0x40) != 0 || *((_QWORD *)this + 76) )
    {
      LRPC_SCALL::SendReply(this);
      v11 = 0;
LABEL_34:
      v13 = "HbBr";
      goto LABEL_35;
    }
    if ( (*((_DWORD *)this + 58) & 0x20) != 0 )
    {
      if ( (*((_DWORD *)this + 58) & 0x1000) != 0 )
      {
        v47 = (void *)*((_QWORD *)this + 59);
        if ( v47 )
          BCACHE::Free(v9, v47);
        *((_QWORD *)this + 59) = 0;
      }
      else if ( (*((_DWORD *)this + 58) & 0x4000) == 0 )
      {
        v44 = 0;
        if ( *((_QWORD *)this + 76) )
          v44 = (LRPC_SCALL *)((char *)this + 608);
        v11 = 0;
        v20 = LRPC_ADDRESS::AlpcSend(
                *(LRPC_ADDRESS **)(*((_QWORD *)this + 38) + 56LL),
                *((struct _PORT_MESSAGE **)this + 56),
                1,
                0,
                0,
                0,
                v44);
LABEL_29:
        if ( v20 < 0 )
        {
          v48 = (*(__int64 (__fastcall **)(LRPC_SCALL *))(*(_QWORD *)this + 496LL))(this);
          if ( v48 != 1726 )
          {
            if ( v48 )
              LRPC_SCALL::AsyncSendFailure(this, v48);
          }
        }
        v22 = (BCACHE *)*((_QWORD *)this + 56);
        v23 = *(_QWORD *)(*((_QWORD *)this + 38) + 56LL);
        v24 = *(BCACHE **)(v23 + 296);
        if ( v24 && v22 > v24 && v22 < (BCACHE *)((char *)v24 + *(unsigned int *)(v23 + 304)) )
        {
          if ( dword_1800FE624 )
          {
            v31 = 0;
            v32 = "HbBr";
            while ( v31 < 4 )
            {
              if ( `LogEventToEtw'::`2'::EtwEventSubjectFilter[v31] == 76 )
                goto LABEL_85;
              ++v31;
            }
            if ( (Microsoft_Windows_RPCEnableBits & 8) != 0 )
            {
              LOBYTE(v21) = 98;
              LOBYTE(v32) = 76;
              McTemplateU0uuxxx_EtwEventWriteTransfer(
                (_DWORD)v24,
                v31,
                (_DWORD)v32,
                v21,
                (char)v22,
                v23,
                *(_QWORD *)(v23 + 296));
            }
          }
LABEL_85:
          AlpcFreeCompletionListMessage(*(_QWORD *)(v23 + 296), v22);
        }
        else if ( v22 )
        {
          BCACHE::Free(v24, v22);
        }
        *((_QWORD *)this + 56) = 0;
        goto LABEL_34;
      }
    }
    v14 = (__int16 *)*((_QWORD *)this + 56);
    v15 = *(_QWORD *)(*((_QWORD *)this + 38) + 56LL);
    if ( v14 )
      v16 = v14[1];
    else
      v16 = 0;
    if ( dword_1800FE624 )
    {
      for ( i = 0; i < 4; ++i )
      {
        if ( `LogEventToEtw'::`2'::EtwEventSubjectFilter[i] == 76 )
          goto LABEL_22;
      }
      if ( (Microsoft_Windows_RPCEnableBits & 8) != 0 )
      {
        *(_QWORD *)v60 = v16;
        *(_QWORD *)v59 = *(_QWORD *)(v15 + 208);
        v64 = &v56;
        v66 = &v57;
        v68 = &v58;
        v70 = v59;
        v72 = v60;
        v58 = (struct LRPC_SCAUSAL_FLOW *)v14;
        v57 = 75;
        v56 = 76;
        v65 = 1;
        v67 = 1;
        v69 = 8;
        v71 = 8;
        v73 = 8;
        McGenEventWrite_EtwEventWriteTransfer(
          (unsigned int)&RpcEtwGuid_Context,
          (unsigned int)RPCLogEvent,
          0,
          6,
          (__int64)v63);
      }
    }
LABEL_22:
    ReservedForNtRpc = (unsigned __int64)NtCurrentTeb()->ReservedForNtRpc;
    if ( ReservedForNtRpc )
    {
      ReservedForNtRpc ^= 0xABABABABDEDEDEDEuLL;
      if ( *(HANDLE *)(ReservedForNtRpc + 16) != NtCurrentTeb()->ClientId.UniqueThread )
        __fastfail(0x1Eu);
    }
    v11 = 1;
    if ( ReservedForNtRpc
      && (v19 = *(_QWORD *)(ReservedForNtRpc + 192)) != 0
      && (v20 = TpCallbackSendAlpcMessageOnCompletion(v19, *(_QWORD *)(v15 + 208), 4259840, v14), v20 >= 0) )
    {
      *(_DWORD *)(ReservedForNtRpc + 200) = 1;
    }
    else
    {
      v20 = NtAlpcSendWaitReceivePort(*(_QWORD *)(v15 + 208), 4259840, v14, 0, 0, 0, 0, 0);
    }
    v1 = 0;
    goto LABEL_29;
  }
LABEL_35:
  _InterlockedOr(v53, 0);
  v25 = *((int *)this + 4);
  if ( dword_1800FE624 )
  {
    for ( j = 0; j < 4; ++j )
    {
      if ( `LogEventToEtw'::`2'::EtwEventSubjectFilter[j] == 114 )
        goto LABEL_42;
    }
    if ( (Microsoft_Windows_RPCEnableBits & 8) != 0 )
    {
      *(_QWORD *)v59 = *((int *)this + 3);
      *(_QWORD *)v60 = v25;
      v64 = &v57;
      v58 = this;
      v66 = &v56;
      v68 = &v58;
      v70 = v59;
      v72 = v60;
      v56 = 45;
      v57 = 114;
      v65 = 1;
      v67 = 1;
      v69 = 8;
      v71 = 8;
      v73 = 8;
      McGenEventWrite_EtwEventWriteTransfer(
        (unsigned int)&RpcEtwGuid_Context,
        (unsigned int)RPCLogEvent,
        v10,
        6,
        (__int64)v63);
    }
  }
LABEL_42:
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 4, 0xFFFFFFFF) == 1 )
    (*(void (__fastcall **)(LRPC_SCALL *, __int64, __int64, const char *))(*(_QWORD *)this + 24LL))(this, v25, v10, v13);
LABEL_44:
  if ( v6 )
  {
    if ( !v11 )
    {
      v27 = ThreadSelf();
      if ( v27 )
        TpWorkOnBehalfClearTicket(*((_QWORD *)v27 + 24));
    }
  }
  if ( v4 )
  {
    v33 = (int)v61;
    v34 = (char *)v4 + 129;
    v59[0] = 0;
    v35 = 0;
LABEL_72:
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)v4 + 64));
    if ( v33 - *((_DWORD *)v4 + 26) < 0 || (v34 = (char *)v4 + 129, v35) )
    {
      v39 = *v34 == 0;
      *((_BYTE *)v4 + 128) = 1;
      if ( !v39 )
        v35 = 1;
      RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)v4 + 64));
LABEL_81:
      if ( !v35 )
        goto LABEL_82;
    }
    else
    {
      v34 = (char *)v4 + 129;
      v36 = (_QWORD **)((char *)v4 + 112);
      v37 = (struct LRPC_SCAUSAL_FLOW *)((char *)v4 + 136);
      while ( 2 )
      {
        v58 = v37;
        v38 = *((_DWORD *)v4 + 26) + 1;
        v39 = *((_BYTE *)v4 + 130) == 0;
        *((_DWORD *)v4 + 26) = v38;
        if ( !v39 && (unsigned int)(v38 - *(_DWORD *)v37) < 0x40000000 )
        {
          *((_BYTE *)v4 + 130) = 0;
          *((_DWORD *)v4 + 36) = 0;
        }
        if ( *v34 && v38 == *((_DWORD *)v4 + 33) )
          v35 = 1;
        v40 = *v36;
        v41 = v38 + 1;
        while ( v40 != v36 )
        {
          v41 = v38 + 1;
          v61 = v40 - 70;
          if ( *((_DWORD *)v40 + 4) == v38 + 1 )
          {
            --*((_DWORD *)v4 + 35);
            RpcpfRemoveEntryListAndZeroOutLinks();
            v1 = v61;
LABEL_80:
            RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)v4 + 64));
            if ( !v1 )
              goto LABEL_81;
            LogEvent(0x46u, 0x6Bu, v1, *((void **)v4 + 7), (unsigned int)v1[144], v54, (int)v55);
            v45 = RpcpGetThreadPointer();
            if ( v45 )
              RpcpPurgeEEInfoFromThreadIfNecessary(v45);
            if ( (v1[58] & 0x2000) != 0 )
            {
              v33 = v1[144];
              REFERENCED_OBJECT::RemoveReference((REFERENCED_OBJECT *)v1);
              v1 = 0;
            }
            else
            {
              v46 = LRPC_SCALL::DispatchRequest((LRPC_SCALL *)v1, v59);
              v33 = v1[144];
              if ( v46 )
              {
                LRPC_SCALL::AsyncSendFailureAndAbort((LRPC_SCALL *)v1, v46);
              }
              else if ( !v59[0] )
              {
                LRPC_SCALL::SendReply((LRPC_SCALL *)v1);
              }
              REFERENCED_OBJECT::RemoveReference((REFERENCED_OBJECT *)v1);
              REFERENCED_OBJECT::RemoveReference((REFERENCED_OBJECT *)v1);
              v1 = 0;
            }
            goto LABEL_72;
          }
          v40 = (_QWORD *)*v40;
        }
        if ( !*((_BYTE *)v4 + 130) || v38 - *(_DWORD *)v37 != -1 )
          goto LABEL_80;
        if ( !v35 )
        {
          LogEvent(0x46u, 0x6Bu, 0, *((void **)v4 + 7), v41, v54, (int)v55);
          v37 = v58;
          continue;
        }
        break;
      }
      *((_BYTE *)v4 + 128) = 1;
      RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)v4 + 64));
    }
    LRPC_SASSOCIATION::DeleteCausalFlowEntry(v62, v4, 0);
LABEL_82:
    (*(void (__fastcall **)(struct LRPC_SCAUSAL_FLOW *))(*(_QWORD *)v4 + 32LL))(v4);
  }
}

```

## disassembly

```asm
0x18001d170  push    rbp
0x18001d172  push    rbx
0x18001d173  push    rdi
0x18001d174  push    r12
0x18001d176  push    r15
0x18001d178  lea     rbp, [rsp-37h]
0x18001d17d  sub     rsp, 0F0h
0x18001d184  mov     rax, cs:__security_cookie
0x18001d18b  xor     rax, rsp
0x18001d18e  mov     [rbp+57h+var_30], rax
0x18001d192  xor     r15d, r15d
0x18001d195  mov     rbx, rcx
0x18001d198  mov     rcx, [rcx+130h]; this
0x18001d19f  mov     r12d, r15d
0x18001d1a2  mov     [rbp+57h+var_C0], r15
0x18001d1a6  mov     [rbp+57h+var_A0], rcx
0x18001d1aa  mov     rax, [rbx+1B8h]
0x18001d1b1  mov     [rbp+57h+var_B8], r15d
0x18001d1b5  mov     dword ptr [rbp+57h+var_A8], r15d
0x18001d1b9  test    byte ptr [rax+30h], 2
0x18001d1bd  jnz     loc_18001D7D4
0x18001d1c3  mov     eax, [rbx+0E8h]
0x18001d1c9  mov     [rsp+110h+arg_10], r13
0x18001d1d1  mov     [rsp+110h+arg_18], r14
0x18001d1d9  bt      eax, 10h
0x18001d1dd  jnb     short loc_18001D1F8
0x18001d1df  lea     rcx, [rbx+288h]; struct _RTL_WORK_ON_BEHALF_TICKET *
0x18001d1e6  test    rcx, rcx
0x18001d1e9  jz      short loc_18001D1F8
0x18001d1eb  call    ?RpcpSetThreadWorkOnBehalfTicket@@YAJPEAU_RTL_WORK_ON_BEHALF_TICKET@@@Z; RpcpSetThreadWorkOnBehalfTicket(_RTL_WORK_ON_BEHALF_TICKET *)
0x18001d1f0  test    eax, eax
0x18001d1f2  jz      loc_18001D69D
0x18001d1f8  mov     r13d, r15d
0x18001d1fb  call    ?ThreadSelf@@YAPEAVTHREAD@@XZ; ThreadSelf(void)
0x18001d200  test    rax, rax
0x18001d203  jz      short loc_18001D218
0x18001d205  mov     rcx, [rax+0C0h]
0x18001d20c  call    cs:__imp_TpWorkOnBehalfClearTicket
0x18001d213  nop     dword ptr [rax+rax+00h]
0x18001d218  lea     rdx, [rbp+57h+var_B8]; int *
0x18001d21c  mov     [rsp+110h+arg_8], rsi
0x18001d224  mov     rcx, rbx; this
0x18001d227  call    ?DispatchRequest@LRPC_SCALL@@QEAAJPEAH@Z; LRPC_SCALL::DispatchRequest(int *)
0x18001d22c  mov     r14d, [rbp+57h+var_B8]
0x18001d230  mov     edi, eax
0x18001d232  test    eax, eax
0x18001d234  jnz     loc_18001D526
0x18001d23a  lea     r9, ?EtwEventSubjectFilter@?1??LogEventToEtw@@YAXEE_J00@Z@4QBEB; "HbBr"
0x18001d241  test    r14d, r14d
0x18001d244  jnz     loc_18001D39E
0x18001d24a  cmp     [rbx+1D0h], r15
0x18001d251  jnz     loc_18001D845
0x18001d257  mov     eax, [rbx+0E8h]
0x18001d25d  test    al, 40h
0x18001d25f  jnz     loc_18001D845
0x18001d265  lea     rdx, [rbx+260h]
0x18001d26c  cmp     [rdx], r15
0x18001d26f  jnz     loc_18001D845
0x18001d275  mov     eax, [rbx+0E8h]
0x18001d27b  test    al, 20h
0x18001d27d  jnz     loc_18001D855
0x18001d283  mov     rax, [rbx+130h]
0x18001d28a  xor     r8d, r8d
0x18001d28d  mov     rsi, [rbx+1C0h]
0x18001d294  mov     r15, [rax+38h]
0x18001d298  test    rsi, rsi
0x18001d29b  jz      loc_18001DA4C
0x18001d2a1  movsx   edx, word ptr [rsi+2]
0x18001d2a5  cmp     cs:dword_1800FE624, 0
0x18001d2ac  jz      short loc_18001D2D1
0x18001d2ae  mov     ecx, r8d
0x18001d2b1  cmp     ecx, 4
0x18001d2b4  jnb     short loc_18001D2C4
0x18001d2b6  movsxd  rax, ecx
0x18001d2b9  cmp     byte ptr [rax+r9], 4Ch ; 'L'
0x18001d2be  jz      short loc_18001D2D1
0x18001d2c0  inc     ecx
0x18001d2c2  jmp     short loc_18001D2B1
0x18001d2c4  test    cs:Microsoft_Windows_RPCEnableBits, 8
0x18001d2cb  jnz     loc_18001D5BC
0x18001d2d1  mov     rax, gs:30h
0x18001d2da  mov     rdi, [rax+1698h]
0x18001d2e1  test    rdi, rdi
0x18001d2e4  jz      short loc_18001D30A
0x18001d2e6  mov     rax, 0ABABABABDEDEDEDEh
0x18001d2f0  xor     rdi, rax
0x18001d2f3  mov     rax, gs:30h
0x18001d2fc  mov     rcx, [rax+48h]
0x18001d300  cmp     [rdi+10h], rcx
0x18001d304  jnz     loc_18001D455
0x18001d30a  mov     r14d, 1
0x18001d310  test    rdi, rdi
0x18001d313  jz      loc_18001D45C
0x18001d319  mov     rcx, [rdi+0C0h]
0x18001d320  test    rcx, rcx
0x18001d323  jz      loc_18001D45C
0x18001d329  mov     rdx, [r15+0D0h]
0x18001d330  mov     r9, rsi
0x18001d333  mov     r8d, 410000h
0x18001d339  call    cs:__imp_TpCallbackSendAlpcMessageOnCompletion
0x18001d340  nop     dword ptr [rax+rax+00h]
0x18001d345  mov     edx, eax
0x18001d347  test    eax, eax
0x18001d349  js      loc_18001D45C
0x18001d34f  mov     [rdi+0C8h], r14d
0x18001d356  xor     r15d, r15d
0x18001d359  test    edx, edx
0x18001d35b  js      loc_18001DAB4
0x18001d361  mov     rax, [rbx+130h]
0x18001d368  mov     rdi, [rbx+1C0h]
0x18001d36f  mov     rsi, [rax+38h]
0x18001d373  mov     rcx, [rsi+128h]; this
0x18001d37a  test    rcx, rcx
0x18001d37d  jnz     loc_18001D650
0x18001d383  test    rdi, rdi
0x18001d386  jz      short loc_18001D390
0x18001d388  mov     rdx, rdi; void *
0x18001d38b  call    ?Free@BCACHE@@QEAAXPEAX@Z; BCACHE::Free(void *)
0x18001d390  mov     [rbx+1C0h], r15
0x18001d397  lea     r9, ?EtwEventSubjectFilter@?1??LogEventToEtw@@YAXEE_J00@Z@4QBEB; "HbBr"
0x18001d39e  lock or [rsp+110h+var_110], 0
0x18001d3a3  movsxd  rdx, dword ptr [rbx+10h]
0x18001d3a7  cmp     cs:dword_1800FE624, 0
0x18001d3ae  jz      short loc_18001D3D3
0x18001d3b0  mov     ecx, r15d
0x18001d3b3  cmp     ecx, 4
0x18001d3b6  jnb     short loc_18001D3C6
0x18001d3b8  movsxd  rax, ecx
0x18001d3bb  cmp     byte ptr [rax+r9], 72h ; 'r'
0x18001d3c0  jz      short loc_18001D3D3
0x18001d3c2  inc     ecx
0x18001d3c4  jmp     short loc_18001D3B3
0x18001d3c6  test    cs:Microsoft_Windows_RPCEnableBits, 8
0x18001d3cd  jnz     loc_18001D497
0x18001d3d3  mov     eax, 0FFFFFFFFh
0x18001d3d8  lock xadd [rbx+10h], eax
0x18001d3dd  cmp     eax, 1
0x18001d3e0  jnz     short loc_18001D3F1
0x18001d3e2  mov     rax, [rbx]
0x18001d3e5  mov     rcx, rbx
0x18001d3e8  mov     rax, [rax+18h]
0x18001d3ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d3f1  test    r13d, r13d
0x18001d3f4  jz      short loc_18001D418
0x18001d3f6  test    r14d, r14d
0x18001d3f9  jnz     short loc_18001D418
0x18001d3fb  call    ?ThreadSelf@@YAPEAVTHREAD@@XZ; ThreadSelf(void)
0x18001d400  test    rax, rax
0x18001d403  jz      short loc_18001D418
0x18001d405  mov     rcx, [rax+0C0h]
0x18001d40c  call    cs:__imp_TpWorkOnBehalfClearTicket
0x18001d413  nop     dword ptr [rax+rax+00h]
0x18001d418  test    r12, r12
0x18001d41b  jnz     loc_18001D6A8
0x18001d421  mov     rsi, [rsp+110h+arg_8]
0x18001d429  mov     r13, [rsp+110h+arg_10]
0x18001d431  mov     r14, [rsp+110h+arg_18]
0x18001d439  mov     rcx, [rbp+57h+var_30]
0x18001d43d  xor     rcx, rsp; StackCookie
0x18001d440  call    __security_check_cookie
0x18001d445  add     rsp, 0F0h
0x18001d44c  pop     r15
0x18001d44e  pop     r12
0x18001d450  pop     rdi
0x18001d451  pop     rbx
0x18001d452  pop     rbp
0x18001d453  retn
0x18001d455  mov     ecx, 1Eh
0x18001d45a  int     29h; Win8: RtlFailFast(ecx)
0x18001d45c  mov     rcx, [r15+0D0h]
0x18001d463  xor     eax, eax
0x18001d465  mov     [rsp+110h+var_D8], rax
0x18001d46a  xor     r9d, r9d
0x18001d46d  mov     [rsp+110h+var_E0], rax
0x18001d472  mov     r8, rsi
0x18001d475  mov     [rsp+110h+var_E8], rax
0x18001d47a  mov     edx, 410000h
0x18001d47f  mov     [rsp+110h+var_F0], rax
0x18001d484  call    cs:__imp_NtAlpcSendWaitReceivePort
0x18001d48b  nop     dword ptr [rax+rax+00h]
0x18001d490  mov     edx, eax
0x18001d492  jmp     loc_18001D356
0x18001d497  movsxd  rax, dword ptr [rbx+0Ch]
0x18001d49b  lea     rcx, RpcEtwGuid_Context
0x18001d4a2  mov     qword ptr [rbp+57h+var_B8], rax
0x18001d4a6  mov     r9d, 6
0x18001d4ac  lea     rax, [rbp+57h+var_C8]
0x18001d4b0  mov     qword ptr [rbp+57h+var_B0], rdx
0x18001d4b4  mov     [rbp+57h+var_80], rax
0x18001d4b8  lea     rdx, RPCLogEvent
0x18001d4bf  lea     rax, [rbp+57h+var_D0]
0x18001d4c3  mov     [rbp+57h+var_C0], rbx
0x18001d4c7  mov     [rbp+57h+var_70], rax
0x18001d4cb  lea     rax, [rbp+57h+var_C0]
0x18001d4cf  mov     [rbp+57h+var_60], rax
0x18001d4d3  lea     rax, [rbp+57h+var_B8]
0x18001d4d7  mov     [rbp+57h+var_50], rax
0x18001d4db  lea     rax, [rbp+57h+var_B0]
0x18001d4df  mov     [rbp+57h+var_40], rax
0x18001d4e3  lea     rax, [rbp+57h+var_90]
0x18001d4e7  mov     [rsp+110h+var_F0], rax
0x18001d4ec  mov     [rbp+57h+var_D0], 2Dh ; '-'
0x18001d4f0  mov     [rbp+57h+var_C8], 72h ; 'r'
0x18001d4f4  mov     [rbp+57h+var_78], 1
0x18001d4fc  mov     [rbp+57h+var_68], 1
0x18001d504  mov     [rbp+57h+var_58], 8
0x18001d50c  mov     [rbp+57h+var_48], 8
0x18001d514  mov     [rbp+57h+var_38], 8
0x18001d51c  call    McGenEventWrite_EtwEventWriteTransfer
0x18001d521  jmp     loc_18001D3D3
0x18001d526  mov     rsi, [rbx+1C0h]
0x18001d52d  call    ?RpcpGetThreadPointer@@YAPEAVTHREAD@@XZ; RpcpGetThreadPointer(void)
0x18001d532  test    rax, rax
0x18001d535  jz      short loc_18001D55D
0x18001d537  mov     r15, [rax+50h]
0x18001d53b  test    r15, r15
0x18001d53e  jz      short loc_18001D55A
0x18001d540  cmp     cs:?g_fSendEEInfo@@3HA, 0; int g_fSendEEInfo
0x18001d547  jnz     loc_18001DAE8
0x18001d54d  call    ?IsEEInfoEtwEnabled@@YAHXZ; IsEEInfoEtwEnabled(void)
0x18001d552  test    eax, eax
0x18001d554  jnz     loc_18001DB3C
0x18001d55a  xor     r15d, r15d
0x18001d55d  mov     [rsi+34h], r15d
0x18001d561  mov     qword ptr [rsi+28h], 2
0x18001d569  mov     [rsi+30h], edi
0x18001d56c  mov     qword ptr [rsi], 3C0014h
0x18001d573  mov     [rsi+20h], r15
0x18001d577  lea     rcx, [rbx+260h]; this
0x18001d57e  mov     edx, 1; unsigned int
0x18001d583  call    ?CleanupSystemHandles@LRPC_SYSTEM_HANDLE_DATA@@QEAAHK@Z; LRPC_SYSTEM_HANDLE_DATA::CleanupSystemHandles(ulong)
0x18001d588  cmp     qword ptr [rbx+1D0h], 0
0x18001d590  jnz     loc_18001DB46
0x18001d596  mov     rcx, rbx; this
0x18001d599  call    ?SendReply@LRPC_SCALL@@QEAAXXZ; LRPC_SCALL::SendReply(void)
0x18001d59e  mov     eax, [rbx+0E8h]
0x18001d5a4  mov     rcx, rbx; this
0x18001d5a7  test    eax, 180h
0x18001d5ac  jnz     loc_18001D7A3
0x18001d5b2  call    ?RemoveReference@REFERENCED_OBJECT@@UEAAXXZ; REFERENCED_OBJECT::RemoveReference(void)
0x18001d5b7  jmp     loc_18001D3F1
0x18001d5bc  mov     eax, edx
0x18001d5be  lea     rcx, RpcEtwGuid_Context
0x18001d5c5  mov     qword ptr [rbp+57h+var_B0], rax
0x18001d5c9  lea     rdx, RPCLogEvent
0x18001d5d0  mov     rax, [r15+0D0h]
0x18001d5d7  mov     r9d, 6
0x18001d5dd  mov     qword ptr [rbp+57h+var_B8], rax
0x18001d5e1  lea     rax, [rbp+57h+var_D0]
0x18001d5e5  mov     [rbp+57h+var_80], rax
0x18001d5e9  lea     rax, [rbp+57h+var_C8]
0x18001d5ed  mov     [rbp+57h+var_70], rax
0x18001d5f1  lea     rax, [rbp+57h+var_C0]
0x18001d5f5  mov     [rbp+57h+var_60], rax
0x18001d5f9  lea     rax, [rbp+57h+var_B8]
0x18001d5fd  mov     [rbp+57h+var_50], rax
0x18001d601  lea     rax, [rbp+57h+var_B0]
0x18001d605  mov     [rbp+57h+var_40], rax
0x18001d609  lea     rax, [rbp+57h+var_90]
0x18001d60d  mov     [rsp+110h+var_F0], rax
0x18001d612  mov     [rbp+57h+var_C0], rsi
0x18001d616  mov     [rbp+57h+var_C8], 4Bh ; 'K'
0x18001d61a  mov     [rbp+57h+var_D0], 4Ch ; 'L'
0x18001d61e  mov     [rbp+57h+var_78], 1
0x18001d626  mov     [rbp+57h+var_68], 1
0x18001d62e  mov     [rbp+57h+var_58], 8
0x18001d636  mov     [rbp+57h+var_48], 8
0x18001d63e  mov     [rbp+57h+var_38], 8
0x18001d646  call    McGenEventWrite_EtwEventWriteTransfer
0x18001d64b  jmp     loc_18001D2D1
0x18001d650  cmp     rdi, rcx
0x18001d653  jbe     loc_18001D383
0x18001d659  mov     eax, [rsi+130h]
0x18001d65f  add     rax, rcx
0x18001d662  cmp     rdi, rax
0x18001d665  jnb     loc_18001D383
0x18001d66b  cmp     cs:dword_1800FE624, 0
0x18001d672  jz      loc_18001D788
0x18001d678  mov     edx, r15d
0x18001d67b  lea     r8, ?EtwEventSubjectFilter@?1??LogEventToEtw@@YAXEE_J00@Z@4QBEB; "HbBr"
0x18001d682  cmp     edx, 4
0x18001d685  jnb     loc_18001D77F
0x18001d68b  movsxd  rax, edx
0x18001d68e  cmp     byte ptr [rax+r8], 4Ch ; 'L'
0x18001d693  jz      loc_18001D788
0x18001d699  inc     edx
0x18001d69b  jmp     short loc_18001D682
0x18001d69d  mov     r13d, 1
0x18001d6a3  jmp     loc_18001D218
0x18001d6a8  mov     r13d, dword ptr [rbp+57h+var_A8]
0x18001d6ac  lea     r14, [r12+81h]
0x18001d6b4  mov     [rbp+57h+var_B8], r15d
0x18001d6b8  mov     ebx, r15d
0x18001d6bb  lea     rcx, [r12+40h]; CriticalSection
0x18001d6c0  call    cs:__imp_RtlEnterCriticalSection
0x18001d6c7  nop     dword ptr [rax+rax+00h]
0x18001d6cc  cmp     r13d, [r12+68h]
0x18001d6d1  js      loc_18001D8BC
0x18001d6d7  lea     r14, [r12+81h]
0x18001d6df  test    ebx, ebx
  ... truncated ...
```
