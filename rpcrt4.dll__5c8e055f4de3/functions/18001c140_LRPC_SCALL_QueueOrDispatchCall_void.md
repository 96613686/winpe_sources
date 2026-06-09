# LRPC_SCALL::QueueOrDispatchCall(void)

- ea: `0x18001c140`
- end: `0x18001cb78`
- name: `?QueueOrDispatchCall@LRPC_SCALL@@AEAAXXZ`
- size: `2616`
- prototype: `void __fastcall(LRPC_SCALL *__hidden this)`
- caller_count: `2`
- callee_count: `33`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001a4f0`
- `0x1800a8610`

## callees

- `0x1800164f8`
- `0x180018484`
- `0x180018d9c`
- `0x180018f84`
- `0x1800191d0`
- `0x1800193a8`
- `0x18001c140`
- `0x18001d620`
- `0x18001d750`
- `0x180021ce0`
- `0x180021e18`
- `0x1800229b0`
- `0x180023ca0`
- `0x180025130`
- `0x180026d10`
- `0x1800274e0`
- `0x1800280b0`
- `0x1800283bc`
- `0x1800289e0`
- `0x180028a00`
- `0x180030af8`
- `0x180036610`
- `0x180036644`
- `0x180036874`
- `0x180036934`
- `0x18004c178`
- `0x180050e3c`
- `0x1800951bc`
- `0x18009e258`
- `0x1800a8b04`
- `0x1800b4674`
- `0x1800ca140`
- `0x1800d2010`

## import_xrefs

- `ntdll!NtAlpcSendWaitReceivePort` at `0x18001c441`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x18001c441`
- `ntdll!RtlLeaveCriticalSection` at `0x18001c70d`
- `ntdll!RtlLeaveCriticalSection` at `0x18001c888`
- `ntdll!RtlLeaveCriticalSection` at `0x18001cb54`
- `ntdll!RtlLeaveCriticalSection` at `0x18001c70d`
- `ntdll!RtlLeaveCriticalSection` at `0x18001c888`
- `ntdll!RtlLeaveCriticalSection` at `0x18001cb54`
- `ntdll!RtlEnterCriticalSection` at `0x18001c677`
- `ntdll!RtlEnterCriticalSection` at `0x18001c677`
- `ntdll!TpWorkOnBehalfClearTicket` at `0x18001c1dc`
- `ntdll!TpWorkOnBehalfClearTicket` at `0x18001c3d0`
- `ntdll!TpWorkOnBehalfClearTicket` at `0x18001c1dc`
- `ntdll!TpWorkOnBehalfClearTicket` at `0x18001c3d0`
- `ntdll!TpCallbackSendAlpcMessageOnCompletion` at `0x18001c303`
- `ntdll!TpCallbackSendAlpcMessageOnCompletion` at `0x18001c303`
- `ntdll!AlpcFreeCompletionListMessage` at `0x18001c74c`
- `ntdll!AlpcFreeCompletionListMessage` at `0x18001c74c`

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
      if ( dword_1800F9624 )
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
          if ( dword_1800F9624 )
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
    if ( dword_1800F9624 )
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
  if ( dword_1800F9624 )
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
0x18001c140  push    rbp
0x18001c142  push    rbx
0x18001c143  push    rdi
0x18001c144  push    r12
0x18001c146  push    r15
0x18001c148  lea     rbp, [rsp-37h]
0x18001c14d  sub     rsp, 0F0h
0x18001c154  mov     rax, cs:__security_cookie
0x18001c15b  xor     rax, rsp
0x18001c15e  mov     [rbp+57h+var_30], rax
0x18001c162  xor     r15d, r15d
0x18001c165  mov     rbx, rcx
0x18001c168  mov     rcx, [rcx+130h]; this
0x18001c16f  mov     r12d, r15d
0x18001c172  mov     [rbp+57h+var_C0], r15
0x18001c176  mov     [rbp+57h+var_A0], rcx
0x18001c17a  mov     rax, [rbx+1B8h]
0x18001c181  mov     [rbp+57h+var_B8], r15d
0x18001c185  mov     dword ptr [rbp+57h+var_A8], r15d
0x18001c189  test    byte ptr [rax+30h], 2
0x18001c18d  jnz     loc_18001C788
0x18001c193  mov     eax, [rbx+0E8h]
0x18001c199  mov     [rsp+110h+arg_10], r13
0x18001c1a1  mov     [rsp+110h+arg_18], r14
0x18001c1a9  bt      eax, 10h
0x18001c1ad  jnb     short loc_18001C1C8
0x18001c1af  lea     rcx, [rbx+288h]; struct _RTL_WORK_ON_BEHALF_TICKET *
0x18001c1b6  test    rcx, rcx
0x18001c1b9  jz      short loc_18001C1C8
0x18001c1bb  call    ?RpcpSetThreadWorkOnBehalfTicket@@YAJPEAU_RTL_WORK_ON_BEHALF_TICKET@@@Z; RpcpSetThreadWorkOnBehalfTicket(_RTL_WORK_ON_BEHALF_TICKET *)
0x18001c1c0  test    eax, eax
0x18001c1c2  jz      loc_18001C654
0x18001c1c8  mov     r13d, r15d
0x18001c1cb  call    ?ThreadSelf@@YAPEAVTHREAD@@XZ; ThreadSelf(void)
0x18001c1d0  test    rax, rax
0x18001c1d3  jz      short loc_18001C1E2
0x18001c1d5  mov     rcx, [rax+0C0h]
0x18001c1dc  call    cs:__imp_TpWorkOnBehalfClearTicket
0x18001c1e2  lea     rdx, [rbp+57h+var_B8]; int *
0x18001c1e6  mov     [rsp+110h+arg_8], rsi
0x18001c1ee  mov     rcx, rbx; this
0x18001c1f1  call    ?DispatchRequest@LRPC_SCALL@@QEAAJPEAH@Z; LRPC_SCALL::DispatchRequest(int *)
0x18001c1f6  mov     r14d, [rbp+57h+var_B8]
0x18001c1fa  mov     edi, eax
0x18001c1fc  test    eax, eax
0x18001c1fe  jnz     loc_18001C4DD
0x18001c204  lea     r9, ?EtwEventSubjectFilter@?1??LogEventToEtw@@YAXEE_J00@Z@4QBEB; "HbBr"
0x18001c20b  test    r14d, r14d
0x18001c20e  jnz     loc_18001C362
0x18001c214  cmp     [rbx+1D0h], r15
0x18001c21b  jnz     loc_18001C7F9
0x18001c221  mov     eax, [rbx+0E8h]
0x18001c227  test    al, 40h
0x18001c229  jnz     loc_18001C7F9
0x18001c22f  lea     rdx, [rbx+260h]
0x18001c236  cmp     [rdx], r15
0x18001c239  jnz     loc_18001C7F9
0x18001c23f  mov     eax, [rbx+0E8h]
0x18001c245  test    al, 20h
0x18001c247  jnz     loc_18001C809
0x18001c24d  mov     rax, [rbx+130h]
0x18001c254  xor     r8d, r8d
0x18001c257  mov     rsi, [rbx+1C0h]
0x18001c25e  mov     r15, [rax+38h]
0x18001c262  test    rsi, rsi
0x18001c265  jz      loc_18001C9FA
0x18001c26b  movsx   edx, word ptr [rsi+2]
0x18001c26f  cmp     cs:dword_1800F9624, 0
0x18001c276  jz      short loc_18001C29B
0x18001c278  mov     ecx, r8d
0x18001c27b  cmp     ecx, 4
0x18001c27e  jnb     short loc_18001C28E
0x18001c280  movsxd  rax, ecx
0x18001c283  cmp     byte ptr [rax+r9], 4Ch ; 'L'
0x18001c288  jz      short loc_18001C29B
0x18001c28a  inc     ecx
0x18001c28c  jmp     short loc_18001C27B
0x18001c28e  test    cs:Microsoft_Windows_RPCEnableBits, 8
0x18001c295  jnz     loc_18001C573
0x18001c29b  mov     rax, gs:30h
0x18001c2a4  mov     rdi, [rax+1698h]
0x18001c2ab  test    rdi, rdi
0x18001c2ae  jz      short loc_18001C2D4
0x18001c2b0  mov     rax, 0ABABABABDEDEDEDEh
0x18001c2ba  xor     rdi, rax
0x18001c2bd  mov     rax, gs:30h
0x18001c2c6  mov     rcx, [rax+48h]
0x18001c2ca  cmp     [rdi+10h], rcx
0x18001c2ce  jnz     loc_18001C412
0x18001c2d4  mov     r14d, 1
0x18001c2da  test    rdi, rdi
0x18001c2dd  jz      loc_18001C419
0x18001c2e3  mov     rcx, [rdi+0C0h]
0x18001c2ea  test    rcx, rcx
0x18001c2ed  jz      loc_18001C419
0x18001c2f3  mov     rdx, [r15+0D0h]
0x18001c2fa  mov     r9, rsi
0x18001c2fd  mov     r8d, 410000h
0x18001c303  call    cs:__imp_TpCallbackSendAlpcMessageOnCompletion
0x18001c309  mov     edx, eax
0x18001c30b  test    eax, eax
0x18001c30d  js      loc_18001C419
0x18001c313  mov     [rdi+0C8h], r14d
0x18001c31a  xor     r15d, r15d
0x18001c31d  test    edx, edx
0x18001c31f  js      loc_18001CA62
0x18001c325  mov     rax, [rbx+130h]
0x18001c32c  mov     rdi, [rbx+1C0h]
0x18001c333  mov     rsi, [rax+38h]
0x18001c337  mov     rcx, [rsi+128h]; this
0x18001c33e  test    rcx, rcx
0x18001c341  jnz     loc_18001C607
0x18001c347  test    rdi, rdi
0x18001c34a  jz      short loc_18001C354
0x18001c34c  mov     rdx, rdi; void *
0x18001c34f  call    ?Free@BCACHE@@QEAAXPEAX@Z; BCACHE::Free(void *)
0x18001c354  mov     [rbx+1C0h], r15
0x18001c35b  lea     r9, ?EtwEventSubjectFilter@?1??LogEventToEtw@@YAXEE_J00@Z@4QBEB; "HbBr"
0x18001c362  lock or [rsp+110h+var_110], 0
0x18001c367  movsxd  rdx, dword ptr [rbx+10h]
0x18001c36b  cmp     cs:dword_1800F9624, 0
0x18001c372  jz      short loc_18001C397
0x18001c374  mov     ecx, r15d
0x18001c377  cmp     ecx, 4
0x18001c37a  jnb     short loc_18001C38A
0x18001c37c  movsxd  rax, ecx
0x18001c37f  cmp     byte ptr [rax+r9], 72h ; 'r'
0x18001c384  jz      short loc_18001C397
0x18001c386  inc     ecx
0x18001c388  jmp     short loc_18001C377
0x18001c38a  test    cs:Microsoft_Windows_RPCEnableBits, 8
0x18001c391  jnz     loc_18001C44E
0x18001c397  mov     eax, 0FFFFFFFFh
0x18001c39c  lock xadd [rbx+10h], eax
0x18001c3a1  cmp     eax, 1
0x18001c3a4  jnz     short loc_18001C3B5
0x18001c3a6  mov     rax, [rbx]
0x18001c3a9  mov     rcx, rbx
0x18001c3ac  mov     rax, [rax+18h]
0x18001c3b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c3b5  test    r13d, r13d
0x18001c3b8  jz      short loc_18001C3D6
0x18001c3ba  test    r14d, r14d
0x18001c3bd  jnz     short loc_18001C3D6
0x18001c3bf  call    ?ThreadSelf@@YAPEAVTHREAD@@XZ; ThreadSelf(void)
0x18001c3c4  test    rax, rax
0x18001c3c7  jz      short loc_18001C3D6
0x18001c3c9  mov     rcx, [rax+0C0h]
0x18001c3d0  call    cs:__imp_TpWorkOnBehalfClearTicket
0x18001c3d6  test    r12, r12
0x18001c3d9  jnz     loc_18001C65F
0x18001c3df  mov     rsi, [rsp+110h+arg_8]
0x18001c3e7  mov     r13, [rsp+110h+arg_10]
0x18001c3ef  mov     r14, [rsp+110h+arg_18]
0x18001c3f7  mov     rcx, [rbp+57h+var_30]
0x18001c3fb  xor     rcx, rsp; StackCookie
0x18001c3fe  call    __security_check_cookie
0x18001c403  add     rsp, 0F0h
0x18001c40a  pop     r15
0x18001c40c  pop     r12
0x18001c40e  pop     rdi
0x18001c40f  pop     rbx
0x18001c410  pop     rbp
0x18001c411  retn
0x18001c412  mov     ecx, 1Eh
0x18001c417  int     29h; Win8: RtlFailFast(ecx)
0x18001c419  mov     rcx, [r15+0D0h]
0x18001c420  xor     eax, eax
0x18001c422  mov     [rsp+110h+var_D8], rax
0x18001c427  xor     r9d, r9d
0x18001c42a  mov     [rsp+110h+var_E0], rax
0x18001c42f  mov     r8, rsi
0x18001c432  mov     [rsp+110h+var_E8], rax
0x18001c437  mov     edx, 410000h
0x18001c43c  mov     [rsp+110h+var_F0], rax
0x18001c441  call    cs:__imp_NtAlpcSendWaitReceivePort
0x18001c447  mov     edx, eax
0x18001c449  jmp     loc_18001C31A
0x18001c44e  movsxd  rax, dword ptr [rbx+0Ch]
0x18001c452  lea     rcx, RpcEtwGuid_Context
0x18001c459  mov     qword ptr [rbp+57h+var_B8], rax
0x18001c45d  mov     r9d, 6
0x18001c463  lea     rax, [rbp+57h+var_C8]
0x18001c467  mov     qword ptr [rbp+57h+var_B0], rdx
0x18001c46b  mov     [rbp+57h+var_80], rax
0x18001c46f  lea     rdx, RPCLogEvent
0x18001c476  lea     rax, [rbp+57h+var_D0]
0x18001c47a  mov     [rbp+57h+var_C0], rbx
0x18001c47e  mov     [rbp+57h+var_70], rax
0x18001c482  lea     rax, [rbp+57h+var_C0]
0x18001c486  mov     [rbp+57h+var_60], rax
0x18001c48a  lea     rax, [rbp+57h+var_B8]
0x18001c48e  mov     [rbp+57h+var_50], rax
0x18001c492  lea     rax, [rbp+57h+var_B0]
0x18001c496  mov     [rbp+57h+var_40], rax
0x18001c49a  lea     rax, [rbp+57h+var_90]
0x18001c49e  mov     [rsp+110h+var_F0], rax
0x18001c4a3  mov     [rbp+57h+var_D0], 2Dh ; '-'
0x18001c4a7  mov     [rbp+57h+var_C8], 72h ; 'r'
0x18001c4ab  mov     [rbp+57h+var_78], 1
0x18001c4b3  mov     [rbp+57h+var_68], 1
0x18001c4bb  mov     [rbp+57h+var_58], 8
0x18001c4c3  mov     [rbp+57h+var_48], 8
0x18001c4cb  mov     [rbp+57h+var_38], 8
0x18001c4d3  call    McGenEventWrite_EtwEventWriteTransfer
0x18001c4d8  jmp     loc_18001C397
0x18001c4dd  mov     rsi, [rbx+1C0h]
0x18001c4e4  call    ?RpcpGetThreadPointer@@YAPEAVTHREAD@@XZ; RpcpGetThreadPointer(void)
0x18001c4e9  test    rax, rax
0x18001c4ec  jz      short loc_18001C514
0x18001c4ee  mov     r15, [rax+50h]
0x18001c4f2  test    r15, r15
0x18001c4f5  jz      short loc_18001C511
0x18001c4f7  cmp     cs:?g_fSendEEInfo@@3HA, 0; int g_fSendEEInfo
0x18001c4fe  jnz     loc_18001CA96
0x18001c504  call    ?IsEEInfoEtwEnabled@@YAHXZ; IsEEInfoEtwEnabled(void)
0x18001c509  test    eax, eax
0x18001c50b  jnz     loc_18001CAEA
0x18001c511  xor     r15d, r15d
0x18001c514  mov     [rsi+34h], r15d
0x18001c518  mov     qword ptr [rsi+28h], 2
0x18001c520  mov     [rsi+30h], edi
0x18001c523  mov     qword ptr [rsi], 3C0014h
0x18001c52a  mov     [rsi+20h], r15
0x18001c52e  lea     rcx, [rbx+260h]; this
0x18001c535  mov     edx, 1; unsigned int
0x18001c53a  call    ?CleanupSystemHandles@LRPC_SYSTEM_HANDLE_DATA@@QEAAHK@Z; LRPC_SYSTEM_HANDLE_DATA::CleanupSystemHandles(ulong)
0x18001c53f  cmp     qword ptr [rbx+1D0h], 0
0x18001c547  jnz     loc_18001CAF4
0x18001c54d  mov     rcx, rbx; this
0x18001c550  call    ?SendReply@LRPC_SCALL@@QEAAXXZ; LRPC_SCALL::SendReply(void)
0x18001c555  mov     eax, [rbx+0E8h]
0x18001c55b  mov     rcx, rbx; this
0x18001c55e  test    eax, 180h
0x18001c563  jnz     loc_18001C757
0x18001c569  call    ?RemoveReference@REFERENCED_OBJECT@@UEAAXXZ; REFERENCED_OBJECT::RemoveReference(void)
0x18001c56e  jmp     loc_18001C3B5
0x18001c573  mov     eax, edx
0x18001c575  lea     rcx, RpcEtwGuid_Context
0x18001c57c  mov     qword ptr [rbp+57h+var_B0], rax
0x18001c580  lea     rdx, RPCLogEvent
0x18001c587  mov     rax, [r15+0D0h]
0x18001c58e  mov     r9d, 6
0x18001c594  mov     qword ptr [rbp+57h+var_B8], rax
0x18001c598  lea     rax, [rbp+57h+var_D0]
0x18001c59c  mov     [rbp+57h+var_80], rax
0x18001c5a0  lea     rax, [rbp+57h+var_C8]
0x18001c5a4  mov     [rbp+57h+var_70], rax
0x18001c5a8  lea     rax, [rbp+57h+var_C0]
0x18001c5ac  mov     [rbp+57h+var_60], rax
0x18001c5b0  lea     rax, [rbp+57h+var_B8]
0x18001c5b4  mov     [rbp+57h+var_50], rax
0x18001c5b8  lea     rax, [rbp+57h+var_B0]
0x18001c5bc  mov     [rbp+57h+var_40], rax
0x18001c5c0  lea     rax, [rbp+57h+var_90]
0x18001c5c4  mov     [rsp+110h+var_F0], rax
0x18001c5c9  mov     [rbp+57h+var_C0], rsi
0x18001c5cd  mov     [rbp+57h+var_C8], 4Bh ; 'K'
0x18001c5d1  mov     [rbp+57h+var_D0], 4Ch ; 'L'
0x18001c5d5  mov     [rbp+57h+var_78], 1
0x18001c5dd  mov     [rbp+57h+var_68], 1
0x18001c5e5  mov     [rbp+57h+var_58], 8
0x18001c5ed  mov     [rbp+57h+var_48], 8
0x18001c5f5  mov     [rbp+57h+var_38], 8
0x18001c5fd  call    McGenEventWrite_EtwEventWriteTransfer
0x18001c602  jmp     loc_18001C29B
0x18001c607  cmp     rdi, rcx
0x18001c60a  jbe     loc_18001C347
0x18001c610  mov     eax, [rsi+130h]
0x18001c616  add     rax, rcx
0x18001c619  cmp     rdi, rax
0x18001c61c  jnb     loc_18001C347
0x18001c622  cmp     cs:dword_1800F9624, 0
0x18001c629  jz      loc_18001C742
0x18001c62f  mov     edx, r15d
0x18001c632  lea     r8, ?EtwEventSubjectFilter@?1??LogEventToEtw@@YAXEE_J00@Z@4QBEB; "HbBr"
0x18001c639  cmp     edx, 4
0x18001c63c  jnb     loc_18001C739
0x18001c642  movsxd  rax, edx
0x18001c645  cmp     byte ptr [rax+r8], 4Ch ; 'L'
0x18001c64a  jz      loc_18001C742
0x18001c650  inc     edx
0x18001c652  jmp     short loc_18001C639
0x18001c654  mov     r13d, 1
0x18001c65a  jmp     loc_18001C1E2
0x18001c65f  mov     r13d, dword ptr [rbp+57h+var_A8]
0x18001c663  lea     r14, [r12+81h]
0x18001c66b  mov     [rbp+57h+var_B8], r15d
0x18001c66f  mov     ebx, r15d
0x18001c672  lea     rcx, [r12+40h]; CriticalSection
0x18001c677  call    cs:__imp_RtlEnterCriticalSection
0x18001c67d  cmp     r13d, [r12+68h]
0x18001c682  js      loc_18001C870
0x18001c688  lea     r14, [r12+81h]
0x18001c690  test    ebx, ebx
0x18001c692  jnz     loc_18001C870
0x18001c698  lea     r14, [r12+81h]
0x18001c6a0  lea     r13, [r12+70h]
0x18001c6a5  lea     r9, [r12+88h]
0x18001c6ad  mov     [rbp+57h+var_C0], r9
  ... truncated ...
```
