# LRPC_ADDRESS::ProcessIO(void *)

- ea: `0x180020a60`
- end: `0x1800217c8`
- name: `?ProcessIO@LRPC_ADDRESS@@QEAAXPEAX@Z`
- size: `3432`
- prototype: `void __fastcall(LRPC_ADDRESS *__hidden this, void *)`
- caller_count: `2`
- callee_count: `26`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18008c8b0`
- `0x1800abe60`

## callees

- `0x18000f2a8`
- `0x1800159c0`
- `0x1800166c8`
- `0x180016850`
- `0x180019fe0`
- `0x18001a040`
- `0x18001a30c`
- `0x18001e6d0`
- `0x180020140`
- `0x180020a60`
- `0x1800217d0`
- `0x180022fb8`
- `0x1800263a0`
- `0x180026df0`
- `0x180027e20`
- `0x180078c04`
- `0x18007c468`
- `0x18007e6c8`
- `0x180084050`
- `0x180085fe4`
- `0x1800979e8`
- `0x180098144`
- `0x18009b874`
- `0x18009d884`
- `0x1800a2d40`
- `0x1800ceda0`

## import_xrefs

- `ntdll!NtAlpcSendWaitReceivePort` at `0x180020bfa`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x18002149c`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x180020bfa`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x18002149c`
- `ntdll!NtAlpcQueryInformation` at `0x180020b95`
- `ntdll!NtAlpcQueryInformation` at `0x180020b95`
- `ntdll!RtlLeaveCriticalSection` at `0x1800213d1`
- `ntdll!RtlLeaveCriticalSection` at `0x18002157e`
- `ntdll!RtlLeaveCriticalSection` at `0x1800215ce`
- `ntdll!RtlLeaveCriticalSection` at `0x1800213d1`
- `ntdll!RtlLeaveCriticalSection` at `0x18002157e`
- `ntdll!RtlLeaveCriticalSection` at `0x1800215ce`
- `ntdll!RtlEnterCriticalSection` at `0x180021325`
- `ntdll!RtlEnterCriticalSection` at `0x180021325`
- `ntdll!TpCallbackSendPendingAlpcMessage` at `0x180020fb0`
- `ntdll!TpCallbackSendPendingAlpcMessage` at `0x180020fb0`
- `ntdll!AlpcUnregisterCompletionListWorkerThread` at `0x180020d65`
- `ntdll!AlpcUnregisterCompletionListWorkerThread` at `0x180020d65`
- `ntdll!AlpcGetMessageFromCompletionList` at `0x180020fcb`
- `ntdll!AlpcGetMessageFromCompletionList` at `0x180020fcb`
- `ntdll!AlpcRegisterCompletionListWorkerThread` at `0x180021155`
- `ntdll!AlpcRegisterCompletionListWorkerThread` at `0x180021155`
- `ntdll!RtlReleaseResource` at `0x180021106`
- `ntdll!RtlReleaseResource` at `0x180021106`
- `ntdll!RtlAcquireResourceShared` at `0x1800210eb`
- `ntdll!RtlAcquireResourceShared` at `0x1800210eb`
- `ntdll!RtlReleaseSRWLockShared` at `0x180020dfc`
- `ntdll!RtlReleaseSRWLockShared` at `0x180020dfc`
- `ntdll!RtlAcquireSRWLockShared` at `0x180020aa9`
- `ntdll!RtlAcquireSRWLockShared` at `0x180020aa9`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002113a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002113a`

## pseudocode

```c
void __fastcall LRPC_ADDRESS::ProcessIO(LRPC_ADDRESS *this, void *a2)
{
  char *v2; // r15
  int v5; // ebx
  void **UniqueThread; // rcx
  unsigned __int64 ReservedForNtRpc; // rsi
  __int64 v8; // r14
  void **v9; // rbx
  int v10; // r12d
  unsigned __int64 v11; // rdx
  struct _SLIST_ENTRY *v12; // rbx
  int v13; // esi
  int v14; // edx
  unsigned int j; // ecx
  _WORD *v16; // r15
  int v17; // r14d
  unsigned int v18; // r9d
  __int16 v19; // r13
  int v20; // esi
  __int64 v21; // r8
  unsigned int m; // eax
  LRPC_ADDRESS *v23; // rcx
  int v24; // eax
  unsigned int v25; // eax
  unsigned __int64 v26; // rdx
  struct _PORT_MESSAGE *v27; // rax
  __int64 *v28; // rsi
  __int64 v29; // rbx
  int v30; // r8d
  unsigned int k; // edx
  unsigned __int64 v32; // rbx
  unsigned __int64 v33; // rbx
  unsigned __int64 v34; // rdx
  __int64 MessageFromCompletionList; // rax
  unsigned int v36; // eax
  int v37; // r8d
  unsigned int v38; // ebx
  unsigned int i; // edx
  struct RPCP_ALPC_MESSAGE_ATTRIBUTES *v40; // r8
  LRPC_ADDRESS *v41; // rcx
  int v42; // esi
  int v43; // esi
  int v44; // esi
  int v45; // esi
  struct RPCP_ALPC_MESSAGE_ATTRIBUTES *v46; // r8
  int v47; // eax
  unsigned int HeaderSize; // eax
  __int64 v49; // r10
  LRPC_SASSOCIATION *v50; // rsi
  struct RPCP_ALPC_MESSAGE_ATTRIBUTES *v51; // r8
  LRPC_ADDRESS *v52; // rcx
  char v53; // [rsp+40h] [rbp-C0h] BYREF
  char v54; // [rsp+48h] [rbp-B8h] BYREF
  struct RPCP_ALPC_MESSAGE_ATTRIBUTES *v55; // [rsp+50h] [rbp-B0h] BYREF
  char v56; // [rsp+58h] [rbp-A8h] BYREF
  char v57; // [rsp+60h] [rbp-A0h] BYREF
  char v58; // [rsp+68h] [rbp-98h] BYREF
  char v59; // [rsp+70h] [rbp-90h] BYREF
  int v60; // [rsp+78h] [rbp-88h]
  __int64 v61; // [rsp+80h] [rbp-80h] BYREF
  LRPC_ADDRESS *v62; // [rsp+88h] [rbp-78h] BYREF
  __int64 v63; // [rsp+90h] [rbp-70h] BYREF
  struct _SLIST_ENTRY *v64; // [rsp+98h] [rbp-68h] BYREF
  __int128 v65; // [rsp+A0h] [rbp-60h] BYREF
  void *v66; // [rsp+B0h] [rbp-50h]
  LRPC_ADDRESS *v67; // [rsp+B8h] [rbp-48h] BYREF
  struct _SLIST_ENTRY *v68; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int64 v69; // [rsp+C8h] [rbp-38h] BYREF
  LRPC_ADDRESS *v70; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v71; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v72[16]; // [rsp+E0h] [rbp-20h] BYREF
  char *v73; // [rsp+F0h] [rbp-10h]
  __int64 v74; // [rsp+F8h] [rbp-8h]
  char *v75; // [rsp+100h] [rbp+0h]
  __int64 v76; // [rsp+108h] [rbp+8h]
  LRPC_ADDRESS **v77; // [rsp+110h] [rbp+10h]
  __int64 v78; // [rsp+118h] [rbp+18h]
  __int64 *v79; // [rsp+120h] [rbp+20h]
  __int64 v80; // [rsp+128h] [rbp+28h]
  LRPC_ADDRESS **v81; // [rsp+130h] [rbp+30h]
  __int64 v82; // [rsp+138h] [rbp+38h]
  char v83[16]; // [rsp+140h] [rbp+40h] BYREF
  char *v84; // [rsp+150h] [rbp+50h]
  __int64 v85; // [rsp+158h] [rbp+58h]
  char *v86; // [rsp+160h] [rbp+60h]
  __int64 v87; // [rsp+168h] [rbp+68h]
  LRPC_ADDRESS **v88; // [rsp+170h] [rbp+70h]
  __int64 v89; // [rsp+178h] [rbp+78h]
  struct _SLIST_ENTRY **v90; // [rsp+180h] [rbp+80h]
  __int64 v91; // [rsp+188h] [rbp+88h]
  unsigned __int64 *v92; // [rsp+190h] [rbp+90h]
  __int64 v93; // [rsp+198h] [rbp+98h]
  char v94[16]; // [rsp+1A0h] [rbp+A0h] BYREF
  char *v95; // [rsp+1B0h] [rbp+B0h]
  __int64 v96; // [rsp+1B8h] [rbp+B8h]
  char *v97; // [rsp+1C0h] [rbp+C0h]
  __int64 v98; // [rsp+1C8h] [rbp+C8h]
  LRPC_ADDRESS **v99; // [rsp+1D0h] [rbp+D0h]
  __int64 v100; // [rsp+1D8h] [rbp+D8h]
  __int64 *v101; // [rsp+1E0h] [rbp+E0h]
  __int64 v102; // [rsp+1E8h] [rbp+E8h]
  __int128 *v103; // [rsp+1F0h] [rbp+F0h]
  __int64 v104; // [rsp+1F8h] [rbp+F8h]
  _DWORD v105[40]; // [rsp+200h] [rbp+100h] BYREF

  v2 = (char *)this + 424;
  v66 = a2;
  v55 = 0;
  RtlAcquireSRWLockShared((char *)this + 424);
  while ( 1 )
  {
    v5 = *((_DWORD *)this + 73);
    v60 = v5;
    if ( v5 <= 0 )
      break;
    _InterlockedIncrement((volatile signed __int32 *)this + 84);
    v5 = *((_DWORD *)this + 73);
    v60 = v5;
    if ( v5 )
    {
      if ( ((v5 - 1) & 0xFFFFFFFD) != 0 )
        break;
      if ( !RtlAcquireResourceShared(*((PRTL_RESOURCE *)this + 43), 1u) )
      {
        RpcpReportFatalError(21, this);
        __debugbreak();
      }
      RtlReleaseResource(*((PRTL_RESOURCE *)this + 43));
      if ( v5 != 1 && *((_DWORD *)this + 73) == 3 )
        break;
    }
    LRPC_ADDRESS::UnlockCompletionListZone(this);
  }
  UniqueThread = (void **)0xABABABABDEDEDEDELL;
  if ( v5 >= 2 )
  {
    v28 = (__int64 *)((char *)this + 296);
    v36 = AlpcRegisterCompletionListWorkerThread(*((_QWORD *)this + 37));
    v38 = v36;
    if ( dword_1800FE624 )
    {
      for ( i = 0; i < 4; ++i )
      {
        if ( `LogEventToEtw'::`2'::EtwEventSubjectFilter[i] == 76 )
          goto LABEL_78;
      }
      if ( (Microsoft_Windows_RPCEnableBits & 8) != 0 )
      {
        v63 = *v28;
        v64 = (struct _SLIST_ENTRY *)v36;
        v73 = &v53;
        v62 = this;
        v75 = &v54;
        v77 = &v62;
        v79 = &v63;
        v81 = (LRPC_ADDRESS **)&v64;
        v54 = 43;
        v53 = 76;
        v74 = 1;
        v76 = 1;
        v78 = 8;
        v80 = 8;
        v82 = 8;
        McGenEventWrite_EtwEventWriteTransfer(
          (unsigned int)&RpcEtwGuid_Context,
          (unsigned int)RPCLogEvent,
          v37,
          6,
          (__int64)v72);
      }
    }
LABEL_78:
    if ( !v38 )
    {
      LRPC_ADDRESS::UnlockCompletionListZone(this);
      return;
    }
    if ( a2 )
      goto LABEL_63;
    UniqueThread = (void **)0xABABABABDEDEDEDELL;
  }
  v61 = 0;
  v55 = (struct RPCP_ALPC_MESSAGE_ATTRIBUTES *)v105;
  ReservedForNtRpc = (unsigned __int64)NtCurrentTeb()->ReservedForNtRpc;
  if ( ReservedForNtRpc )
  {
    ReservedForNtRpc ^= 0xABABABABDEDEDEDEuLL;
    UniqueThread = (void **)NtCurrentTeb()->ClientId.UniqueThread;
    if ( *(void ***)(ReservedForNtRpc + 16) != UniqueThread )
LABEL_57:
      __fastfail(0x1Eu);
  }
  v8 = *((_QWORD *)this + 26);
  if ( ReservedForNtRpc )
  {
    UniqueThread = *(void ***)(ReservedForNtRpc + 80);
    if ( UniqueThread )
    {
      do
      {
        v9 = (void **)*UniqueThread;
        FreeEEInfoRecord(UniqueThread);
        UniqueThread = v9;
      }
      while ( v9 );
      *(_QWORD *)(ReservedForNtRpc + 80) = 0;
    }
  }
  v61 = 152;
  v105[0] = -100663296;
  v10 = 0;
  v105[1] = 0;
  v65 = 0;
  if ( v8 && (int)NtAlpcQueryInformation(v8, 0, &v65, 16, 0) >= 0 && (v65 & 0x1000000) != 0 )
  {
    v61 = 65280;
    v11 = 65280;
  }
  else
  {
    v61 = 4096;
    v11 = 4096;
  }
  v12 = BCACHE::Allocate((BCACHE *)UniqueThread, v11);
  if ( !v12 )
  {
    v10 = 1;
    RtlEnterCriticalSection(LrpcEmergencyMessageMutex);
    v12 = (struct _SLIST_ENTRY *)LrpcEmergencyMessage;
  }
  v13 = NtAlpcSendWaitReceivePort(v8, 0, 0, 0, v12, &v61, v105, 0);
  if ( v13 )
  {
    v14 = v13;
  }
  else if ( v12 )
  {
    v14 = SWORD1(v12->Next);
  }
  else
  {
    v14 = 0;
  }
  if ( dword_1800FE624 )
  {
    for ( j = 0; j < 4; ++j )
    {
      if ( `LogEventToEtw'::`2'::EtwEventSubjectFilter[j] == 76 )
        goto LABEL_26;
    }
    if ( (Microsoft_Windows_RPCEnableBits & 8) != 0 )
    {
      v62 = (LRPC_ADDRESS *)v14;
      v64 = v12;
      v73 = &v54;
      v63 = v8 | 1;
      v75 = &v53;
      v53 = 75;
      v77 = (LRPC_ADDRESS **)&v64;
      v79 = &v63;
      v81 = &v62;
      v54 = 76;
      v74 = 1;
      v76 = 1;
      v78 = 8;
      v80 = 8;
      v82 = 8;
      McGenEventWrite_EtwEventWriteTransfer(
        (unsigned int)&RpcEtwGuid_Context,
        (unsigned int)RPCLogEvent,
        (unsigned int)&_ImageBase,
        6,
        (__int64)v72);
    }
  }
LABEL_26:
  if ( !v13 )
  {
    v16 = (_WORD *)&v12->Next + 2;
    v17 = 0;
    v18 = 1;
    v19 = (unsigned __int8)WORD2(v12->Next);
    v20 = (unsigned __int8)WORD2(v12->Next);
    if ( !v10 )
      goto LABEL_28;
    goto LABEL_29;
  }
  FreeEmergencyOrNormalMessage(v12);
  while ( 1 )
  {
    if ( v60 <= 0 )
      goto LABEL_59;
    v28 = (__int64 *)((char *)this + 296);
    v29 = (unsigned int)AlpcUnregisterCompletionListWorkerThread(*((_QWORD *)this + 37));
    if ( dword_1800FE624 )
    {
      for ( k = 0; k < 4; ++k )
      {
        if ( `LogEventToEtw'::`2'::EtwEventSubjectFilter[k] == 76 )
          goto LABEL_54;
      }
      if ( (Microsoft_Windows_RPCEnableBits & 8) != 0 )
      {
        v71 = *v28;
        *(_QWORD *)&v65 = v29;
        v95 = &v58;
        v70 = this;
        v97 = &v59;
        v99 = &v70;
        v101 = &v71;
        v103 = &v65;
        v59 = 45;
        v58 = 76;
        v96 = 1;
        v98 = 1;
        v100 = 8;
        v102 = 8;
        v104 = 8;
        McGenEventWrite_EtwEventWriteTransfer(
          (unsigned int)&RpcEtwGuid_Context,
          (unsigned int)RPCLogEvent,
          v30,
          6,
          (__int64)v94);
      }
    }
LABEL_54:
    if ( (_DWORD)v29 )
      break;
    v32 = (unsigned __int64)NtCurrentTeb()->ReservedForNtRpc;
    if ( v32 )
    {
      v33 = v32 ^ 0xABABABABDEDEDEDEuLL;
      if ( *(HANDLE *)(v33 + 16) != NtCurrentTeb()->ClientId.UniqueThread )
        goto LABEL_57;
      if ( *(_QWORD *)(v33 + 192) )
      {
        if ( *(_DWORD *)(v33 + 200) )
        {
          TpCallbackSendPendingAlpcMessage();
          *(_DWORD *)(v33 + 200) = 0;
        }
      }
    }
LABEL_63:
    MessageFromCompletionList = AlpcGetMessageFromCompletionList(*v28, &v55);
    v12 = (struct _SLIST_ENTRY *)MessageFromCompletionList;
    if ( MessageFromCompletionList )
    {
      v16 = (_WORD *)(MessageFromCompletionList + 4);
      v10 = 0;
      v17 = 1;
      v20 = (unsigned __int8)*(_WORD *)(MessageFromCompletionList + 4);
      v19 = (unsigned __int8)*(_WORD *)(MessageFromCompletionList + 4);
LABEL_28:
      v18 = 0;
LABEL_29:
      v21 = v66 != 0 ? 4 : 0;
      if ( dword_1800FE624 )
      {
        for ( m = 0; m < 4; ++m )
        {
          if ( `LogEventToEtw'::`2'::EtwEventSubjectFilter[m] == 65 )
            goto LABEL_36;
        }
        if ( (Microsoft_Windows_RPCEnableBits & 8) != 0 )
        {
          v68 = v12;
          v67 = this;
          v34 = v18 | *((unsigned int *)v55 + 1) | (unsigned int)(2 * v17) | (unsigned __int64)(unsigned int)(v20 << 8);
          v57 = 107;
          v56 = 65;
          v69 = v21 | v34;
          v84 = &v56;
          v85 = 1;
          v86 = &v57;
          v87 = 1;
          v88 = &v67;
          v89 = 8;
          v90 = &v68;
          v92 = &v69;
          v91 = 8;
          v93 = 8;
          McGenEventWrite_EtwEventWriteTransfer(
            (unsigned int)&RpcEtwGuid_Context,
            (unsigned int)RPCLogEvent,
            v21,
            6,
            (__int64)v83);
        }
      }
LABEL_36:
      if ( _InterlockedIncrement((volatile signed __int32 *)this + 100) == *((_DWORD *)this + 101) )
        SetEvent(*((HANDLE *)this + 51));
      v23 = 0;
      if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 101, 0, 0) > 0 )
      {
        if ( v10 )
          goto LABEL_121;
      }
      else
      {
        if ( !v10 )
          goto LABEL_40;
        if ( v19 == 10 )
        {
          LRPC_ADDRESS::RejectNewConnectionRequest(this, (struct _PORT_MESSAGE *)v12, v55);
          goto LABEL_121;
        }
        if ( v19 == 5 )
        {
          LRPC_ADDRESS::HandleConnectionClose(0, v55);
          goto LABEL_121;
        }
        if ( v19 != 1 )
        {
          if ( v19 != 3 && v19 != 12 )
          {
            LRPC_ADDRESS::HandleCommonFailure(
              this,
              14,
              (struct _PORT_MESSAGE *)v12,
              v55,
              *((_DWORD *)v55 + 1) & 0x40000000,
              0,
              0);
            goto LABEL_121;
          }
LABEL_40:
          if ( v20 == 1 )
          {
            v24 = *((_DWORD *)&v12[2].Next + 2);
            if ( v24 )
            {
              switch ( v24 )
              {
                case 1:
                  v40 = v55;
                  v41 = this;
                  if ( (*((_DWORD *)v55 + 1) & 0x40000000) != 0 )
                    goto LABEL_105;
                  LRPC_ADDRESS::HandleBindRequest(this, (struct _PORT_MESSAGE *)v12, v55, v17);
                  goto LABEL_86;
                case 5:
                  v40 = v55;
                  v41 = this;
                  if ( (*((_DWORD *)v55 + 1) & 0x40000000) == 0 )
                  {
                    LRPC_ADDRESS::HandleReservedMessageRequest(this, (struct _PORT_MESSAGE *)v12, v55);
                    goto LABEL_86;
                  }
LABEL_105:
                  LRPC_ADDRESS::HandleCommonFailure(v41, 1728, (struct _PORT_MESSAGE *)v12, v40, 1, 0, v17);
                  LRPC_ADDRESS::RpcFreeLrpcAddressBuffer(this, v12);
                  break;
                case 7:
                case 8:
                  v51 = v55;
                  v52 = this;
                  if ( (*((_DWORD *)v55 + 1) & 0x40000000) != 0 )
                    goto LABEL_140;
                  LRPC_ADDRESS::HandleAckOrNackCallback(this, (struct _PORT_MESSAGE *)v12, v55);
                  goto LABEL_45;
                case 9:
                  LRPC_ADDRESS::HandleCallbackRequest(this, (struct _PORT_MESSAGE *)v12, v55);
                  goto LABEL_45;
                case 12:
                case 13:
                  v51 = v55;
                  v52 = this;
                  if ( (*((_DWORD *)v55 + 1) & 0x40000000) != 0 )
                  {
LABEL_140:
                    LRPC_ADDRESS::HandleCommonFailure(v52, 1728, (struct _PORT_MESSAGE *)v12, v51, 1, 0, v17);
LABEL_86:
                    LRPC_ADDRESS::RpcFreeLrpcAddressBuffer(this, v12);
                  }
                  else
                  {
                    LRPC_ADDRESS::HandlePipeAck(this, (struct _PORT_MESSAGE *)v12, v55, v17);
                  }
                  break;
                default:
                  LRPC_ADDRESS::HandleCommonFailure(
                    this,
                    1728,
                    (struct _PORT_MESSAGE *)v12,
                    v55,
                    *((_DWORD *)v55 + 1) & 0x40000000,
                    0,
                    v17);
                  goto LABEL_86;
              }
            }
            else
            {
              v25 = *((_DWORD *)this + 104);
              v26 = v25;
              if ( v25 <= 0x1000 )
                v26 = 4096;
              v27 = (struct _PORT_MESSAGE *)BCACHE::Allocate(0, v26);
              LRPC_ADDRESS::HandleRequest(this, (struct _PORT_MESSAGE *)v12, v55, v27, v17);
            }
            goto LABEL_45;
          }
          v42 = v20 - 2;
          if ( !v42 )
          {
            if ( v10 )
            {
              RtlLeaveCriticalSection(LrpcEmergencyMessageMutex);
              LRPC_ADDRESS::HandleReply(this, 14, 0, v55);
            }
            else
            {
              LRPC_ADDRESS::HandleReply(this, 0, (struct _PORT_MESSAGE *)v12, v55);
            }
            goto LABEL_45;
          }
          v43 = v42 - 1;
          if ( !v43 )
          {
            if ( (*((_DWORD *)v55 + 1) & 0x40000000) != 0 )
            {
              LRPC_ADDRESS::HandleCommonFailure(this, 1728, (struct _PORT_MESSAGE *)v12, v55, 1, 0, v17);
              FreeEmergencyOrNormalMessageWithCompletionList(this, v12);
            }
            else
            {
              HeaderSize = RpcpAlpcpGetHeaderSize(*(_DWORD *)v55 & 0xC0000000);
              v50 = *(LRPC_SASSOCIATION **)(HeaderSize + v49);
              if ( WORD1(v12->Next) >= 0x40u )
                LRPC_SASSOCIATION::HandleCancelMessage(*(LRPC_SASSOCIATION **)(HeaderSize + v49), HIDWORD(v12[3].Next));
              if ( (*v16 & 0x2000) != 0 )
                NtAlpcSendWaitReceivePort(*((_QWORD *)this + 26), 0, v12, 0, 0, 0, 0, 0);
              LRPC_SASSOCIATION::MessageReceived(v50);
              FreeEmergencyOrNormalMessageWithCompletionList(this, v12);
            }
            goto LABEL_45;
          }
          v44 = v43 - 2;
          if ( !v44 )
          {
            LRPC_ADDRESS::HandleConnectionClose(0, v55);
            LRPC_ADDRESS::RpcFreeLrpcAddressBuffer(this, v12);
            goto LABEL_45;
          }
          v45 = v44 - 5;
          if ( v45 )
          {
            if ( v45 == 2 )
            {
              if ( (*v16 & 0x2000) != 0 )
                LRPC_ADDRESS::AlpcSend(this, (struct _PORT_MESSAGE *)v12, 0, 0, 0, 0, 0);
              LRPC_ADDRESS::HandleRumpMessage(v23, v55);
              FreeEmergencyOrNormalMessageWithCompletionList(this, v12);
            }
            goto LABEL_45;
          }
          v46 = v55;
          if ( (*((_DWORD *)v55 + 1) & 0x40000000) == 0 )
          {
            if ( !(unsigned int)LRPC_ADDRESS::NewConnectionRequest(this, (struct _PORT_MESSAGE *)v12, v55) )
              goto LABEL_45;
            v46 = v55;
          }
          LRPC_ADDRESS::RejectNewConnectionRequest(this, (struct _PORT_MESSAGE *)v12, v46);
          LRPC_ADDRESS::RpcFreeLrpcAddressBuffer(this, v12);
          goto LABEL_45;
        }
        v47 = *((_DWORD *)&v12[2].Next + 2);
        if ( v47 == 5 )
        {
          if ( (*((_DWORD *)v55 + 1) & 0x40000000) != 0 )
            goto LABEL_115;
          LRPC_ADDRESS::HandleReservedMessageRequest(this, (struct _PORT_MESSAGE *)v12, v55);
LABEL_121:
          RtlLeaveCriticalSection(LrpcEmergencyMessageMutex);
        }
        else
        {
          if ( v47 )
          {
            if ( (*((_DWORD *)v55 + 1) & 0x40000000) == 0 )
            {
              LRPC_ADDRESS::HandleCommonFailure(this, 14, (struct _PORT_MESSAGE *)v12, v55, 0, 0, 0);
              goto LABEL_121;
            }
LABEL_115:
            LRPC_ADDRESS::HandleCommonFailure(this, 1728, (struct _PORT_MESSAGE *)v12, v55, 1, 0, 0);
            goto LABEL_121;
          }
          LRPC_ADDRESS::HandleRequest(this, (struct _PORT_MESSAGE *)v12, v55, 0, 0);
        }
      }
LABEL_45:
      v2 = (char *)this + 424;
      continue;
    }
  }
  LRPC_ADDRESS::UnlockCompletionListZone(this);
LABEL_59:
  RtlReleaseSRWLockShared(v2);
}

```

## disassembly

```asm
0x180020a60  mov     [rsp-8+arg_18], rbx
0x180020a65  push    rbp
0x180020a66  push    rdi
0x180020a67  push    r13
0x180020a69  push    r14
0x180020a6b  push    r15
0x180020a6d  lea     rbp, [rsp-1B0h]
0x180020a75  sub     rsp, 2B0h
0x180020a7c  mov     rax, cs:__security_cookie
0x180020a83  xor     rax, rsp
0x180020a86  mov     [rbp+1D0h+var_30], rax
0x180020a8d  lea     r15, [rcx+1A8h]
0x180020a94  mov     [rbp+1D0h+var_220], rdx
0x180020a98  mov     rdi, rcx
0x180020a9b  xor     r13d, r13d
0x180020a9e  mov     rcx, r15
0x180020aa1  mov     [rsp+2D0h+var_280], r13
0x180020aa6  mov     r14, rdx
0x180020aa9  call    cs:__imp_RtlAcquireSRWLockShared
0x180020ab0  nop     dword ptr [rax+rax+00h]
0x180020ab5  mov     ebx, [rdi+124h]
0x180020abb  mov     [rsp+2D0h+var_258], ebx
0x180020abf  test    ebx, ebx
0x180020ac1  jg      loc_1800210BB
0x180020ac7  mov     [rsp+2D0h+arg_8], rsi
0x180020acf  mov     rcx, 0ABABABABDEDEDEDEh
0x180020ad9  mov     [rsp+2D0h+arg_10], r12
0x180020ae1  lea     r12, __ImageBase
0x180020ae8  cmp     ebx, 2
0x180020aeb  jge     loc_18002114B
0x180020af1  lea     rax, [rbp+1D0h+var_D0]
0x180020af8  mov     [rbp+1D0h+var_250], r13
0x180020afc  mov     [rsp+2D0h+var_280], rax
0x180020b01  mov     rax, gs:30h
0x180020b0a  mov     rsi, [rax+1698h]
0x180020b11  test    rsi, rsi
0x180020b14  jz      short loc_180020B30
0x180020b16  mov     rax, gs:30h
0x180020b1f  xor     rsi, rcx
0x180020b22  mov     rcx, [rax+48h]
0x180020b26  cmp     [rsi+10h], rcx
0x180020b2a  jnz     loc_180020DEA
0x180020b30  mov     r14, [rdi+0D0h]
0x180020b37  test    rsi, rsi
0x180020b3a  jz      short loc_180020B59
0x180020b3c  mov     rcx, [rsi+50h]; lpMem
0x180020b40  test    rcx, rcx
0x180020b43  jz      short loc_180020B59
0x180020b45  mov     rbx, [rcx]
0x180020b48  call    FreeEEInfoRecord
0x180020b4d  mov     rcx, rbx
0x180020b50  test    rbx, rbx
0x180020b53  jnz     short loc_180020B45
0x180020b55  mov     [rsi+50h], r13
0x180020b59  mov     [rbp+1D0h+var_250], 98h
0x180020b61  xorps   xmm0, xmm0
0x180020b64  mov     [rbp+1D0h+var_D0], 0FA000000h
0x180020b6e  mov     r12d, r13d
0x180020b71  mov     [rbp+1D0h+var_CC], r13d
0x180020b78  movups  [rbp+1D0h+var_230], xmm0
0x180020b7c  test    r14, r14
0x180020b7f  jz      short loc_180020BB2
0x180020b81  mov     r9d, 10h
0x180020b87  mov     [rsp+2D0h+var_2B0], r13
0x180020b8c  lea     r8, [rbp+1D0h+var_230]
0x180020b90  xor     edx, edx
0x180020b92  mov     rcx, r14
0x180020b95  call    cs:__imp_NtAlpcQueryInformation
0x180020b9c  nop     dword ptr [rax+rax+00h]
0x180020ba1  test    eax, eax
0x180020ba3  js      short loc_180020BB2
0x180020ba5  test    dword ptr [rbp+1D0h+var_230], 1000000h
0x180020bac  jnz     loc_1800211AF
0x180020bb2  mov     [rbp+1D0h+var_250], 1000h
0x180020bba  mov     edx, 1000h; unsigned __int64
0x180020bbf  call    ?Allocate@BCACHE@@QEAAPEAX_K@Z; BCACHE::Allocate(unsigned __int64)
0x180020bc4  mov     rbx, rax
0x180020bc7  test    rax, rax
0x180020bca  jz      loc_180021318
0x180020bd0  mov     [rsp+2D0h+var_298], r13
0x180020bd5  lea     rax, [rbp+1D0h+var_D0]
0x180020bdc  mov     [rsp+2D0h+var_2A0], rax
0x180020be1  xor     r9d, r9d
0x180020be4  lea     rax, [rbp+1D0h+var_250]
0x180020be8  xor     r8d, r8d
0x180020beb  mov     [rsp+2D0h+var_2A8], rax
0x180020bf0  xor     edx, edx
0x180020bf2  mov     rcx, r14
0x180020bf5  mov     [rsp+2D0h+var_2B0], rbx
0x180020bfa  call    cs:__imp_NtAlpcSendWaitReceivePort
0x180020c01  nop     dword ptr [rax+rax+00h]
0x180020c06  mov     esi, eax
0x180020c08  test    eax, eax
0x180020c0a  jnz     loc_180021253
0x180020c10  test    rbx, rbx
0x180020c13  jz      loc_18002173A
0x180020c19  movsx   edx, word ptr [rbx+2]
0x180020c1d  cmp     cs:dword_1800FE624, r13d
0x180020c24  jz      short loc_180020C54
0x180020c26  mov     ecx, r13d
0x180020c29  lea     r8, __ImageBase
0x180020c30  cmp     ecx, 4
0x180020c33  jnb     short loc_180020C47
0x180020c35  movsxd  rax, ecx
0x180020c38  cmp     byte ptr [rax+r8+0E66D8h], 4Ch ; 'L'
0x180020c41  jz      short loc_180020C54
0x180020c43  inc     ecx
0x180020c45  jmp     short loc_180020C30
0x180020c47  test    cs:Microsoft_Windows_RPCEnableBits, 8
0x180020c4e  jnz     loc_180020F05
0x180020c54  test    esi, esi
0x180020c56  jnz     loc_180021787
0x180020c5c  xor     r10d, r10d
0x180020c5f  lea     r15, [rbx+4]
0x180020c63  mov     eax, 0FFh
0x180020c68  mov     r14d, r10d
0x180020c6b  and     ax, [r15]
0x180020c6f  mov     r9d, 1
0x180020c75  movzx   r13d, ax
0x180020c79  mov     esi, r13d
0x180020c7c  test    r12d, r12d
0x180020c7f  jnz     short loc_180020C84
0x180020c81  mov     r9d, r10d
0x180020c84  mov     rax, [rbp+1D0h+var_220]
0x180020c88  neg     rax
0x180020c8b  sbb     r8, r8
0x180020c8e  and     r8d, 4
0x180020c92  cmp     cs:dword_1800FE624, 0
0x180020c99  jz      short loc_180020CC8
0x180020c9b  mov     eax, r10d
0x180020c9e  cmp     eax, 4
0x180020ca1  jnb     short loc_180020CBB
0x180020ca3  movsxd  rcx, eax
0x180020ca6  lea     rdx, __ImageBase
0x180020cad  cmp     byte ptr [rcx+rdx+0E66D8h], 41h ; 'A'
0x180020cb5  jz      short loc_180020CC8
0x180020cb7  inc     eax
0x180020cb9  jmp     short loc_180020C9E
0x180020cbb  test    cs:Microsoft_Windows_RPCEnableBits, 8
0x180020cc2  jnz     loc_180020E4A
0x180020cc8  mov     ecx, 1
0x180020ccd  lock xadd [rdi+190h], ecx
0x180020cd5  mov     eax, [rdi+194h]
0x180020cdb  inc     ecx
0x180020cdd  cmp     ecx, eax
0x180020cdf  jz      loc_180021133
0x180020ce5  xor     ecx, ecx; this
0x180020ce7  xor     eax, eax
0x180020ce9  lock cmpxchg [rdi+194h], ecx
0x180020cf1  test    eax, eax
0x180020cf3  jg      loc_18002156E
0x180020cf9  test    r12d, r12d
0x180020cfc  jnz     loc_180021360
0x180020d02  cmp     esi, 1
0x180020d05  jnz     loc_1800212B2
0x180020d0b  mov     eax, [rbx+28h]
0x180020d0e  test    eax, eax
0x180020d10  jnz     loc_18002125A
0x180020d16  mov     eax, [rdi+1A0h]
0x180020d1c  mov     edx, eax; unsigned __int64
0x180020d1e  cmp     eax, 1000h
0x180020d23  jbe     loc_180020E40
0x180020d29  call    ?Allocate@BCACHE@@QEAAPEAX_K@Z; BCACHE::Allocate(unsigned __int64)
0x180020d2e  mov     r8, [rsp+2D0h+var_280]; struct RPCP_ALPC_MESSAGE_ATTRIBUTES *
0x180020d33  mov     r9, rax; struct _PORT_MESSAGE *
0x180020d36  mov     rdx, rbx; struct _PORT_MESSAGE *
0x180020d39  mov     dword ptr [rsp+2D0h+var_2B0], r14d; int
0x180020d3e  mov     rcx, rdi; this
0x180020d41  call    ?HandleRequest@LRPC_ADDRESS@@AEAAXPEAU_PORT_MESSAGE@@PEAVRPCP_ALPC_MESSAGE_ATTRIBUTES@@0H@Z; LRPC_ADDRESS::HandleRequest(_PORT_MESSAGE *,RPCP_ALPC_MESSAGE_ATTRIBUTES *,_PORT_MESSAGE *,int)
0x180020d46  xor     r13d, r13d
0x180020d49  lea     r15, [rdi+1A8h]
0x180020d50  cmp     [rsp+2D0h+var_258], 0
0x180020d55  jle     loc_180020DF9
0x180020d5b  lea     rsi, [rdi+128h]
0x180020d62  mov     rcx, [rsi]
0x180020d65  call    cs:__imp_AlpcUnregisterCompletionListWorkerThread
0x180020d6c  nop     dword ptr [rax+rax+00h]
0x180020d71  cmp     cs:dword_1800FE624, 0
0x180020d78  mov     ebx, eax
0x180020d7a  jz      short loc_180020DA9
0x180020d7c  mov     edx, r13d
0x180020d7f  lea     rax, __ImageBase
0x180020d86  cmp     edx, 4
0x180020d89  jnb     short loc_180020D9C
0x180020d8b  movsxd  rcx, edx
0x180020d8e  cmp     byte ptr [rcx+rax+0E66D8h], 4Ch ; 'L'
0x180020d96  jz      short loc_180020DA9
0x180020d98  inc     edx
0x180020d9a  jmp     short loc_180020D86
0x180020d9c  test    cs:Microsoft_Windows_RPCEnableBits, 8
0x180020da3  jnz     loc_180021008
0x180020da9  test    ebx, ebx
0x180020dab  jnz     short loc_180020DF1
0x180020dad  mov     rax, gs:30h
0x180020db6  mov     rbx, [rax+1698h]
0x180020dbd  test    rbx, rbx
0x180020dc0  jz      loc_180020FC3
0x180020dc6  mov     rax, 0ABABABABDEDEDEDEh
0x180020dd0  xor     rbx, rax
0x180020dd3  mov     rax, gs:30h
0x180020ddc  mov     rcx, [rax+48h]
0x180020de0  cmp     [rbx+10h], rcx
0x180020de4  jz      loc_180020F9B
0x180020dea  mov     ecx, 1Eh
0x180020def  int     29h; Win8: RtlFailFast(ecx)
0x180020df1  mov     rcx, rdi; this
0x180020df4  call    ?UnlockCompletionListZone@LRPC_ADDRESS@@AEAAXXZ; LRPC_ADDRESS::UnlockCompletionListZone(void)
0x180020df9  mov     rcx, r15
0x180020dfc  call    cs:__imp_RtlReleaseSRWLockShared
0x180020e03  nop     dword ptr [rax+rax+00h]
0x180020e08  mov     rsi, [rsp+2D0h+arg_8]
0x180020e10  mov     r12, [rsp+2D0h+arg_10]
0x180020e18  mov     rcx, [rbp+1D0h+var_30]
0x180020e1f  xor     rcx, rsp; StackCookie
0x180020e22  call    __security_check_cookie
0x180020e27  mov     rbx, [rsp+2D0h+arg_18]
0x180020e2f  add     rsp, 2B0h
0x180020e36  pop     r15
0x180020e38  pop     r14
0x180020e3a  pop     r13
0x180020e3c  pop     rdi
0x180020e3d  pop     rbp
0x180020e3e  retn
0x180020e40  mov     edx, 1000h
0x180020e45  jmp     loc_180020D29
0x180020e4a  mov     rax, [rsp+2D0h+var_280]
0x180020e4f  lea     ecx, [r14+r14]
0x180020e53  mov     edx, esi
0x180020e55  mov     [rbp+1D0h+var_210], rbx
0x180020e59  shl     edx, 8
0x180020e5c  or      rdx, rcx
0x180020e5f  mov     [rbp+1D0h+var_218], rdi
0x180020e63  mov     ecx, [rax+4]
0x180020e66  or      rdx, rcx
0x180020e69  mov     eax, r9d
0x180020e6c  or      rdx, rax
0x180020e6f  mov     [rsp+2D0h+var_270], 6Bh ; 'k'
0x180020e74  or      rdx, r8
0x180020e77  mov     [rsp+2D0h+var_278], 41h ; 'A'
0x180020e7c  lea     rax, [rsp+2D0h+var_278]
0x180020e81  mov     [rbp+1D0h+var_208], rdx
0x180020e85  mov     [rbp+1D0h+var_180], rax
0x180020e89  lea     rdx, RPCLogEvent
0x180020e90  lea     rax, [rsp+2D0h+var_270]
0x180020e95  mov     [rbp+1D0h+var_178], 1
0x180020e9d  mov     [rbp+1D0h+var_170], rax
0x180020ea1  lea     rcx, RpcEtwGuid_Context
0x180020ea8  lea     rax, [rbp+1D0h+var_218]
0x180020eac  mov     [rbp+1D0h+var_168], 1
0x180020eb4  mov     [rbp+1D0h+var_160], rax
0x180020eb8  mov     r9d, 6
0x180020ebe  lea     rax, [rbp+1D0h+var_210]
0x180020ec2  mov     [rbp+1D0h+var_158], 8
0x180020eca  mov     [rbp+1D0h+var_150], rax
0x180020ed1  lea     rax, [rbp+1D0h+var_208]
0x180020ed5  mov     [rbp+1D0h+var_140], rax
0x180020edc  lea     rax, [rbp+1D0h+var_190]
0x180020ee0  mov     [rsp+2D0h+var_2B0], rax
0x180020ee5  mov     [rbp+1D0h+var_148], 8
0x180020ef0  mov     [rbp+1D0h+var_138], 8
0x180020efb  call    McGenEventWrite_EtwEventWriteTransfer
0x180020f00  jmp     loc_180020CC8
0x180020f05  movsxd  rax, edx
0x180020f08  lea     rcx, RpcEtwGuid_Context
0x180020f0f  mov     [rbp+1D0h+var_248], rax
0x180020f13  lea     rdx, RPCLogEvent
0x180020f1a  lea     rax, [rsp+2D0h+var_288]
0x180020f1f  mov     [rbp+1D0h+var_238], rbx
0x180020f23  mov     [rbp+1D0h+var_1E0], rax
0x180020f27  or      r14, 1
0x180020f2b  lea     rax, [rsp+2D0h+var_290]
0x180020f30  mov     [rbp+1D0h+var_240], r14
0x180020f34  mov     [rbp+1D0h+var_1D0], rax
0x180020f38  mov     r9d, 6
0x180020f3e  lea     rax, [rbp+1D0h+var_238]
0x180020f42  mov     [rsp+2D0h+var_290], 4Bh ; 'K'
0x180020f47  mov     [rbp+1D0h+var_1C0], rax
0x180020f4b  lea     rax, [rbp+1D0h+var_240]
0x180020f4f  mov     [rbp+1D0h+var_1B0], rax
0x180020f53  lea     rax, [rbp+1D0h+var_248]
0x180020f57  mov     [rbp+1D0h+var_1A0], rax
0x180020f5b  lea     rax, [rbp+1D0h+var_1F0]
0x180020f5f  mov     [rsp+2D0h+var_2B0], rax
0x180020f64  mov     [rsp+2D0h+var_288], 4Ch ; 'L'
0x180020f69  mov     [rbp+1D0h+var_1D8], 1
0x180020f71  mov     [rbp+1D0h+var_1C8], 1
0x180020f79  mov     [rbp+1D0h+var_1B8], 8
0x180020f81  mov     [rbp+1D0h+var_1A8], 8
0x180020f89  mov     [rbp+1D0h+var_198], 8
0x180020f91  call    McGenEventWrite_EtwEventWriteTransfer
0x180020f96  jmp     loc_180020C54
0x180020f9b  mov     rcx, [rbx+0C0h]
0x180020fa2  test    rcx, rcx
0x180020fa5  jz      short loc_180020FC3
0x180020fa7  cmp     dword ptr [rbx+0C8h], 0
0x180020fae  jz      short loc_180020FC3
0x180020fb0  call    cs:__imp_TpCallbackSendPendingAlpcMessage
0x180020fb7  nop     dword ptr [rax+rax+00h]
0x180020fbc  mov     [rbx+0C8h], r13d
0x180020fc3  mov     rcx, [rsi]
  ... truncated ...
```
