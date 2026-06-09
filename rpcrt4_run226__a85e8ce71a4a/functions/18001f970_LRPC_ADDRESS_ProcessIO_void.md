# LRPC_ADDRESS::ProcessIO(void *)

- ea: `0x18001f970`
- end: `0x180020690`
- name: `?ProcessIO@LRPC_ADDRESS@@QEAAXPEAX@Z`
- size: `3360`
- prototype: `void __fastcall(LRPC_ADDRESS *__hidden this, void *)`
- caller_count: `2`
- callee_count: `26`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18008a840`
- `0x1800a8550`

## callees

- `0x18001537c`
- `0x180016b90`
- `0x1800182ac`
- `0x180018f60`
- `0x180018fb4`
- `0x1800193a8`
- `0x18001d65c`
- `0x18001f070`
- `0x18001f970`
- `0x1800206a0`
- `0x180021e18`
- `0x180025130`
- `0x180025c00`
- `0x180026ca0`
- `0x180033ed8`
- `0x18004c1e4`
- `0x18004ea20`
- `0x1800797d4`
- `0x180079b18`
- `0x180080d94`
- `0x180082704`
- `0x180083f44`
- `0x180097e20`
- `0x180099d20`
- `0x18009f62c`
- `0x1800ca140`

## import_xrefs

- `ntdll!NtAlpcSendWaitReceivePort` at `0x18001fafe`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x180020359`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x18001fafe`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x180020359`
- `ntdll!NtAlpcQueryInformation` at `0x18001fa9f`
- `ntdll!NtAlpcQueryInformation` at `0x18001fa9f`
- `ntdll!RtlLeaveCriticalSection` at `0x180020294`
- `ntdll!RtlLeaveCriticalSection` at `0x1800203d6`
- `ntdll!RtlLeaveCriticalSection` at `0x180020442`
- `ntdll!RtlLeaveCriticalSection` at `0x18002048c`
- `ntdll!RtlLeaveCriticalSection` at `0x18002053d`
- `ntdll!RtlLeaveCriticalSection` at `0x180020559`
- `ntdll!RtlLeaveCriticalSection` at `0x180020294`
- `ntdll!RtlLeaveCriticalSection` at `0x1800203d6`
- `ntdll!RtlLeaveCriticalSection` at `0x180020442`
- `ntdll!RtlLeaveCriticalSection` at `0x18002048c`
- `ntdll!RtlLeaveCriticalSection` at `0x18002053d`
- `ntdll!RtlLeaveCriticalSection` at `0x180020559`
- `ntdll!RtlEnterCriticalSection` at `0x1800201ee`
- `ntdll!RtlEnterCriticalSection` at `0x1800201ee`
- `ntdll!TpCallbackSendPendingAlpcMessage` at `0x18001fea1`
- `ntdll!TpCallbackSendPendingAlpcMessage` at `0x18001fea1`
- `ntdll!AlpcUnregisterCompletionListWorkerThread` at `0x18001fc63`
- `ntdll!AlpcUnregisterCompletionListWorkerThread` at `0x18001fc63`
- `ntdll!AlpcGetMessageFromCompletionList` at `0x18001feb6`
- `ntdll!AlpcGetMessageFromCompletionList` at `0x18001feb6`
- `ntdll!AlpcRegisterCompletionListWorkerThread` at `0x180020028`
- `ntdll!AlpcRegisterCompletionListWorkerThread` at `0x180020028`
- `ntdll!RtlReleaseResource` at `0x18001ffe5`
- `ntdll!RtlReleaseResource` at `0x18001ffe5`
- `ntdll!RtlAcquireResourceShared` at `0x18001ffd0`
- `ntdll!RtlAcquireResourceShared` at `0x18001ffd0`
- `ntdll!RtlReleaseSRWLockShared` at `0x18001fcf4`
- `ntdll!RtlReleaseSRWLockShared` at `0x18001fcf4`
- `ntdll!RtlAcquireSRWLockShared` at `0x18001f9b9`
- `ntdll!RtlAcquireSRWLockShared` at `0x18001f9b9`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180020013`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180020013`

## pseudocode

```c
void __fastcall LRPC_ADDRESS::ProcessIO(LRPC_ADDRESS *this, void *a2)
{
  char *v2; // r15
  int v5; // ebx
  _QWORD *UniqueThread; // rcx
  unsigned __int64 ReservedForNtRpc; // rsi
  __int64 v8; // r14
  _QWORD *v9; // rbx
  int v10; // r12d
  unsigned __int64 v11; // rdx
  __int16 *v12; // rbx
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
  LRPC_ADDRESS *v48; // rcx
  struct RPCP_ALPC_MESSAGE_ATTRIBUTES *v49; // r9
  struct _PORT_MESSAGE *v50; // r8
  unsigned int HeaderSize; // eax
  __int64 v52; // r10
  LRPC_SASSOCIATION *v53; // rsi
  struct RPCP_ALPC_MESSAGE_ATTRIBUTES *v54; // r8
  LRPC_ADDRESS *v55; // rcx
  int v56; // [rsp+20h] [rbp-E0h]
  char v57; // [rsp+40h] [rbp-C0h] BYREF
  char v58; // [rsp+48h] [rbp-B8h] BYREF
  struct RPCP_ALPC_MESSAGE_ATTRIBUTES *v59; // [rsp+50h] [rbp-B0h] BYREF
  char v60; // [rsp+58h] [rbp-A8h] BYREF
  char v61; // [rsp+60h] [rbp-A0h] BYREF
  char v62; // [rsp+68h] [rbp-98h] BYREF
  char v63; // [rsp+70h] [rbp-90h] BYREF
  int v64; // [rsp+78h] [rbp-88h]
  __int64 v65; // [rsp+80h] [rbp-80h] BYREF
  LRPC_ADDRESS *v66; // [rsp+88h] [rbp-78h] BYREF
  __int64 v67; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int64 v68; // [rsp+98h] [rbp-68h] BYREF
  __int128 v69; // [rsp+A0h] [rbp-60h] BYREF
  void *v70; // [rsp+B0h] [rbp-50h]
  LRPC_ADDRESS *v71; // [rsp+B8h] [rbp-48h] BYREF
  __int16 *v72; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int64 v73; // [rsp+C8h] [rbp-38h] BYREF
  LRPC_ADDRESS *v74; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v75; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v76[16]; // [rsp+E0h] [rbp-20h] BYREF
  char *v77; // [rsp+F0h] [rbp-10h]
  __int64 v78; // [rsp+F8h] [rbp-8h]
  char *v79; // [rsp+100h] [rbp+0h]
  __int64 v80; // [rsp+108h] [rbp+8h]
  LRPC_ADDRESS **v81; // [rsp+110h] [rbp+10h]
  __int64 v82; // [rsp+118h] [rbp+18h]
  __int64 *v83; // [rsp+120h] [rbp+20h]
  __int64 v84; // [rsp+128h] [rbp+28h]
  LRPC_ADDRESS **v85; // [rsp+130h] [rbp+30h]
  __int64 v86; // [rsp+138h] [rbp+38h]
  char v87[16]; // [rsp+140h] [rbp+40h] BYREF
  char *v88; // [rsp+150h] [rbp+50h]
  __int64 v89; // [rsp+158h] [rbp+58h]
  char *v90; // [rsp+160h] [rbp+60h]
  __int64 v91; // [rsp+168h] [rbp+68h]
  LRPC_ADDRESS **v92; // [rsp+170h] [rbp+70h]
  __int64 v93; // [rsp+178h] [rbp+78h]
  __int16 **v94; // [rsp+180h] [rbp+80h]
  __int64 v95; // [rsp+188h] [rbp+88h]
  unsigned __int64 *v96; // [rsp+190h] [rbp+90h]
  __int64 v97; // [rsp+198h] [rbp+98h]
  char v98[16]; // [rsp+1A0h] [rbp+A0h] BYREF
  char *v99; // [rsp+1B0h] [rbp+B0h]
  __int64 v100; // [rsp+1B8h] [rbp+B8h]
  char *v101; // [rsp+1C0h] [rbp+C0h]
  __int64 v102; // [rsp+1C8h] [rbp+C8h]
  LRPC_ADDRESS **v103; // [rsp+1D0h] [rbp+D0h]
  __int64 v104; // [rsp+1D8h] [rbp+D8h]
  __int64 *v105; // [rsp+1E0h] [rbp+E0h]
  __int64 v106; // [rsp+1E8h] [rbp+E8h]
  __int128 *v107; // [rsp+1F0h] [rbp+F0h]
  __int64 v108; // [rsp+1F8h] [rbp+F8h]
  _DWORD v109[40]; // [rsp+200h] [rbp+100h] BYREF

  v2 = (char *)this + 424;
  v70 = a2;
  v59 = 0;
  RtlAcquireSRWLockShared((char *)this + 424);
  while ( 1 )
  {
    v5 = *((_DWORD *)this + 73);
    v64 = v5;
    if ( v5 <= 0 )
      break;
    _InterlockedIncrement((volatile signed __int32 *)this + 84);
    v5 = *((_DWORD *)this + 73);
    v64 = v5;
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
  UniqueThread = (_QWORD *)0xABABABABDEDEDEDELL;
  if ( v5 >= 2 )
  {
    v28 = (__int64 *)((char *)this + 296);
    v36 = AlpcRegisterCompletionListWorkerThread(*((_QWORD *)this + 37));
    v38 = v36;
    if ( dword_1800F9624 )
    {
      for ( i = 0; i < 4; ++i )
      {
        if ( `LogEventToEtw'::`2'::EtwEventSubjectFilter[i] == 76 )
          goto LABEL_78;
      }
      if ( (Microsoft_Windows_RPCEnableBits & 8) != 0 )
      {
        v67 = *v28;
        v68 = v36;
        v77 = &v57;
        v66 = this;
        v79 = &v58;
        v81 = &v66;
        v83 = &v67;
        v85 = (LRPC_ADDRESS **)&v68;
        v58 = 43;
        v57 = 76;
        v78 = 1;
        v80 = 1;
        v82 = 8;
        v84 = 8;
        v86 = 8;
        McGenEventWrite_EtwEventWriteTransfer(
          (unsigned int)&RpcEtwGuid_Context,
          (unsigned int)RPCLogEvent,
          v37,
          6,
          (__int64)v76);
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
    UniqueThread = (_QWORD *)0xABABABABDEDEDEDELL;
  }
  v65 = 0;
  v59 = (struct RPCP_ALPC_MESSAGE_ATTRIBUTES *)v109;
  ReservedForNtRpc = (unsigned __int64)NtCurrentTeb()->ReservedForNtRpc;
  if ( ReservedForNtRpc )
  {
    ReservedForNtRpc ^= 0xABABABABDEDEDEDEuLL;
    UniqueThread = NtCurrentTeb()->ClientId.UniqueThread;
    if ( *(_QWORD **)(ReservedForNtRpc + 16) != UniqueThread )
LABEL_57:
      __fastfail(0x1Eu);
  }
  v8 = *((_QWORD *)this + 26);
  if ( ReservedForNtRpc )
  {
    UniqueThread = *(_QWORD **)(ReservedForNtRpc + 80);
    if ( UniqueThread )
    {
      do
      {
        v9 = (_QWORD *)*UniqueThread;
        FreeEEInfoRecord(UniqueThread);
        UniqueThread = v9;
      }
      while ( v9 );
      *(_QWORD *)(ReservedForNtRpc + 80) = 0;
    }
  }
  v65 = 152;
  v109[0] = -100663296;
  v10 = 0;
  v109[1] = 0;
  v69 = 0;
  if ( v8 && (int)NtAlpcQueryInformation(v8, 0, &v69, 16, 0) >= 0 && (v69 & 0x1000000) != 0 )
  {
    v65 = 65280;
    v11 = 65280;
  }
  else
  {
    v65 = 4096;
    v11 = 4096;
  }
  v12 = (__int16 *)BCACHE::Allocate((BCACHE *)UniqueThread, v11);
  if ( !v12 )
  {
    v10 = 1;
    RtlEnterCriticalSection(LrpcEmergencyMessageMutex);
    v12 = (__int16 *)LrpcEmergencyMessage;
  }
  v13 = NtAlpcSendWaitReceivePort(v8, 0, 0, 0, v12, &v65, v109, 0);
  if ( v13 )
  {
    v14 = v13;
  }
  else if ( v12 )
  {
    v14 = v12[1];
  }
  else
  {
    v14 = 0;
  }
  if ( dword_1800F9624 )
  {
    for ( j = 0; j < 4; ++j )
    {
      if ( `LogEventToEtw'::`2'::EtwEventSubjectFilter[j] == 76 )
        goto LABEL_26;
    }
    if ( (Microsoft_Windows_RPCEnableBits & 8) != 0 )
    {
      v66 = (LRPC_ADDRESS *)v14;
      v68 = (unsigned __int64)v12;
      v77 = &v58;
      v67 = v8 | 1;
      v79 = &v57;
      v57 = 75;
      v81 = (LRPC_ADDRESS **)&v68;
      v83 = &v67;
      v85 = &v66;
      v58 = 76;
      v78 = 1;
      v80 = 1;
      v82 = 8;
      v84 = 8;
      v86 = 8;
      McGenEventWrite_EtwEventWriteTransfer(
        (unsigned int)&RpcEtwGuid_Context,
        (unsigned int)RPCLogEvent,
        (unsigned int)&_ImageBase,
        6,
        (__int64)v76);
    }
  }
LABEL_26:
  if ( !v13 )
  {
    v16 = v12 + 2;
    v17 = 0;
    v18 = 1;
    v19 = (unsigned __int8)v12[2];
    v20 = (unsigned __int8)v12[2];
    if ( !v10 )
      goto LABEL_28;
    goto LABEL_29;
  }
  FreeEmergencyOrNormalMessage(v12);
  while ( 1 )
  {
    if ( v64 <= 0 )
      goto LABEL_59;
    v28 = (__int64 *)((char *)this + 296);
    v29 = (unsigned int)AlpcUnregisterCompletionListWorkerThread(*((_QWORD *)this + 37));
    if ( dword_1800F9624 )
    {
      for ( k = 0; k < 4; ++k )
      {
        if ( `LogEventToEtw'::`2'::EtwEventSubjectFilter[k] == 76 )
          goto LABEL_54;
      }
      if ( (Microsoft_Windows_RPCEnableBits & 8) != 0 )
      {
        v75 = *v28;
        *(_QWORD *)&v69 = v29;
        v99 = &v62;
        v74 = this;
        v101 = &v63;
        v103 = &v74;
        v105 = &v75;
        v107 = &v69;
        v63 = 45;
        v62 = 76;
        v100 = 1;
        v102 = 1;
        v104 = 8;
        v106 = 8;
        v108 = 8;
        McGenEventWrite_EtwEventWriteTransfer(
          (unsigned int)&RpcEtwGuid_Context,
          (unsigned int)RPCLogEvent,
          v30,
          6,
          (__int64)v98);
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
    MessageFromCompletionList = AlpcGetMessageFromCompletionList(*v28, &v59);
    v12 = (__int16 *)MessageFromCompletionList;
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
      v21 = v70 != 0 ? 4 : 0;
      if ( dword_1800F9624 )
      {
        for ( m = 0; m < 4; ++m )
        {
          if ( `LogEventToEtw'::`2'::EtwEventSubjectFilter[m] == 65 )
            goto LABEL_36;
        }
        if ( (Microsoft_Windows_RPCEnableBits & 8) != 0 )
        {
          v72 = v12;
          v71 = this;
          v34 = v18 | *((unsigned int *)v59 + 1) | (unsigned int)(2 * v17) | (unsigned __int64)(unsigned int)(v20 << 8);
          v61 = 107;
          v60 = 65;
          v73 = v21 | v34;
          v88 = &v60;
          v89 = 1;
          v90 = &v61;
          v91 = 1;
          v92 = &v71;
          v93 = 8;
          v94 = &v72;
          v96 = &v73;
          v95 = 8;
          v97 = 8;
          McGenEventWrite_EtwEventWriteTransfer(
            (unsigned int)&RpcEtwGuid_Context,
            (unsigned int)RPCLogEvent,
            v21,
            6,
            (__int64)v87);
        }
      }
LABEL_36:
      if ( _InterlockedIncrement((volatile signed __int32 *)this + 100) == *((_DWORD *)this + 101) )
        SetEvent(*((HANDLE *)this + 51));
      v23 = 0;
      if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 101, 0, 0) > 0 )
      {
        if ( v10 )
          goto LABEL_122;
      }
      else
      {
        if ( !v10 )
          goto LABEL_40;
        if ( v19 == 10 )
        {
          LRPC_ADDRESS::RejectNewConnectionRequest(this, (struct _PORT_MESSAGE *)v12, v59);
          RtlLeaveCriticalSection(LrpcEmergencyMessageMutex);
          goto LABEL_45;
        }
        if ( v19 == 5 )
        {
          LRPC_ADDRESS::HandleConnectionClose(0, v59);
          RtlLeaveCriticalSection(LrpcEmergencyMessageMutex);
          goto LABEL_45;
        }
        if ( v19 != 1 )
        {
          if ( v19 != 3 && v19 != 12 )
          {
            v49 = v59;
            v50 = (struct _PORT_MESSAGE *)v12;
            v48 = this;
            v56 = *((_DWORD *)v59 + 1) & 0x40000000;
LABEL_104:
            LRPC_ADDRESS::HandleCommonFailure(v48, 14, v50, v49, v56, 0, 0);
            goto LABEL_122;
          }
LABEL_40:
          if ( v20 == 1 )
          {
            v24 = *((_DWORD *)v12 + 10);
            if ( v24 )
            {
              switch ( v24 )
              {
                case 1:
                  v40 = v59;
                  v41 = this;
                  if ( (*((_DWORD *)v59 + 1) & 0x40000000) != 0 )
                    goto LABEL_106;
                  LRPC_ADDRESS::HandleBindRequest(this, (struct _PORT_MESSAGE *)v12, v59, v17);
                  goto LABEL_86;
                case 5:
                  v40 = v59;
                  v41 = this;
                  if ( (*((_DWORD *)v59 + 1) & 0x40000000) == 0 )
                  {
                    LRPC_ADDRESS::HandleReservedMessageRequest(this, (struct _PORT_MESSAGE *)v12, v59);
                    goto LABEL_86;
                  }
LABEL_106:
                  LRPC_ADDRESS::HandleCommonFailure(v41, 1728, (struct _PORT_MESSAGE *)v12, v40, 1, 0, v17);
                  LRPC_ADDRESS::RpcFreeLrpcAddressBuffer(this, v12);
                  break;
                case 7:
                case 8:
                  v54 = v59;
                  v55 = this;
                  if ( (*((_DWORD *)v59 + 1) & 0x40000000) != 0 )
                    goto LABEL_141;
                  LRPC_ADDRESS::HandleAckOrNackCallback(this, (struct _PORT_MESSAGE *)v12, v59);
                  goto LABEL_45;
                case 9:
                  LRPC_ADDRESS::HandleCallbackRequest(this, (struct _PORT_MESSAGE *)v12, v59, v17);
                  goto LABEL_45;
                case 12:
                case 13:
                  v54 = v59;
                  v55 = this;
                  if ( (*((_DWORD *)v59 + 1) & 0x40000000) != 0 )
                  {
LABEL_141:
                    LRPC_ADDRESS::HandleCommonFailure(v55, 1728, (struct _PORT_MESSAGE *)v12, v54, 1, 0, v17);
LABEL_86:
                    LRPC_ADDRESS::RpcFreeLrpcAddressBuffer(this, v12);
                  }
                  else
                  {
                    LRPC_ADDRESS::HandlePipeAck(this, (struct _PORT_MESSAGE *)v12, v59, v17);
                  }
                  break;
                default:
                  LRPC_ADDRESS::HandleCommonFailure(
                    this,
                    1728,
                    (struct _PORT_MESSAGE *)v12,
                    v59,
                    *((_DWORD *)v59 + 1) & 0x40000000,
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
              LRPC_ADDRESS::HandleRequest(this, (struct _PORT_MESSAGE *)v12, v59, v27, v17);
            }
            goto LABEL_45;
          }
          v42 = v20 - 2;
          if ( !v42 )
          {
            if ( v10 )
            {
              RtlLeaveCriticalSection(LrpcEmergencyMessageMutex);
              LRPC_ADDRESS::HandleReply(this, 14, 0, v59);
            }
            else
            {
              LRPC_ADDRESS::HandleReply(this, 0, (struct _PORT_MESSAGE *)v12, v59);
            }
            goto LABEL_45;
          }
          v43 = v42 - 1;
          if ( !v43 )
          {
            if ( (*((_DWORD *)v59 + 1) & 0x40000000) != 0 )
            {
              LRPC_ADDRESS::HandleCommonFailure(this, 1728, (struct _PORT_MESSAGE *)v12, v59, 1, 0, v17);
              FreeEmergencyOrNormalMessageWithCompletionList(this, v12);
            }
            else
            {
              HeaderSize = RpcpAlpcpGetHeaderSize(*(_DWORD *)v59 & 0xC0000000);
              v53 = *(LRPC_SASSOCIATION **)(HeaderSize + v52);
              if ( (unsigned __int16)v12[1] >= 0x40u )
                LRPC_SASSOCIATION::HandleCancelMessage(*(LRPC_SASSOCIATION **)(HeaderSize + v52), *((_DWORD *)v12 + 13));
              if ( (*v16 & 0x2000) != 0 )
                NtAlpcSendWaitReceivePort(*((_QWORD *)this + 26), 0, v12, 0, 0, 0, 0, 0);
              LRPC_SASSOCIATION::MessageReceived(v53);
              FreeEmergencyOrNormalMessageWithCompletionList(this, v12);
            }
            goto LABEL_45;
          }
          v44 = v43 - 2;
          if ( !v44 )
          {
            LRPC_ADDRESS::HandleConnectionClose(0, v59);
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
              LRPC_ADDRESS::HandleRumpMessage(v23, v59);
              FreeEmergencyOrNormalMessageWithCompletionList(this, v12);
            }
            goto LABEL_45;
          }
          v46 = v59;
          if ( (*((_DWORD *)v59 + 1) & 0x40000000) == 0 )
          {
            if ( !(unsigned int)LRPC_ADDRESS::NewConnectionRequest(this, (struct _PORT_MESSAGE *)v12, v59) )
              goto LABEL_45;
            v46 = v59;
          }
          LRPC_ADDRESS::RejectNewConnectionRequest(this, (struct _PORT_MESSAGE *)v12, v46);
          LRPC_ADDRESS::RpcFreeLrpcAddressBuffer(this, v12);
          goto LABEL_45;
        }
        v47 = *((_DWORD *)v12 + 10);
        v48 = this;
        if ( v47 == 5 )
        {
          if ( (*((_DWORD *)v59 + 1) & 0x40000000) != 0 )
            goto LABEL_116;
          LRPC_ADDRESS::HandleReservedMessageRequest(this, (struct _PORT_MESSAGE *)v12, v59);
LABEL_122:
          RtlLeaveCriticalSection(LrpcEmergencyMessageMutex);
        }
        else
        {
          if ( v47 )
          {
            v49 = v59;
            v50 = (struct _PORT_MESSAGE *)v12;
            if ( (*((_DWORD *)v59 + 1) & 0x40000000) == 0 )
            {
              v56 = 0;
              goto LABEL_104;
            }
LABEL_116:
            LRPC_ADDRESS::HandleCommonFailure(this, 1728, (struct _PORT_MESSAGE *)v12, v59, 1, 0, 0);
            goto LABEL_122;
          }
          LRPC_ADDRESS::HandleRequest(this, (struct _PORT_MESSAGE *)v12, v59, 0, 0);
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
0x18001f970  mov     [rsp-8+arg_18], rbx
0x18001f975  push    rbp
0x18001f976  push    rdi
0x18001f977  push    r13
0x18001f979  push    r14
0x18001f97b  push    r15
0x18001f97d  lea     rbp, [rsp-1B0h]
0x18001f985  sub     rsp, 2B0h
0x18001f98c  mov     rax, cs:__security_cookie
0x18001f993  xor     rax, rsp
0x18001f996  mov     [rbp+1D0h+var_30], rax
0x18001f99d  lea     r15, [rcx+1A8h]
0x18001f9a4  mov     [rbp+1D0h+var_220], rdx
0x18001f9a8  mov     rdi, rcx
0x18001f9ab  xor     r13d, r13d
0x18001f9ae  mov     rcx, r15
0x18001f9b1  mov     [rsp+2D0h+var_280], r13
0x18001f9b6  mov     r14, rdx
0x18001f9b9  call    cs:__imp_RtlAcquireSRWLockShared
0x18001f9bf  mov     ebx, [rdi+124h]
0x18001f9c5  mov     [rsp+2D0h+var_258], ebx
0x18001f9c9  test    ebx, ebx
0x18001f9cb  jg      loc_18001FFA0
0x18001f9d1  mov     [rsp+2D0h+arg_8], rsi
0x18001f9d9  mov     rcx, 0ABABABABDEDEDEDEh
0x18001f9e3  mov     [rsp+2D0h+arg_10], r12
0x18001f9eb  lea     r12, __ImageBase
0x18001f9f2  cmp     ebx, 2
0x18001f9f5  jge     loc_18002001E
0x18001f9fb  lea     rax, [rbp+1D0h+var_D0]
0x18001fa02  mov     [rbp+1D0h+var_250], r13
0x18001fa06  mov     [rsp+2D0h+var_280], rax
0x18001fa0b  mov     rax, gs:30h
0x18001fa14  mov     rsi, [rax+1698h]
0x18001fa1b  test    rsi, rsi
0x18001fa1e  jz      short loc_18001FA3A
0x18001fa20  mov     rax, gs:30h
0x18001fa29  xor     rsi, rcx
0x18001fa2c  mov     rcx, [rax+48h]
0x18001fa30  cmp     [rsi+10h], rcx
0x18001fa34  jnz     loc_18001FCE2
0x18001fa3a  mov     r14, [rdi+0D0h]
0x18001fa41  test    rsi, rsi
0x18001fa44  jz      short loc_18001FA63
0x18001fa46  mov     rcx, [rsi+50h]; lpMem
0x18001fa4a  test    rcx, rcx
0x18001fa4d  jz      short loc_18001FA63
0x18001fa4f  mov     rbx, [rcx]
0x18001fa52  call    FreeEEInfoRecord
0x18001fa57  mov     rcx, rbx
0x18001fa5a  test    rbx, rbx
0x18001fa5d  jnz     short loc_18001FA4F
0x18001fa5f  mov     [rsi+50h], r13
0x18001fa63  mov     [rbp+1D0h+var_250], 98h
0x18001fa6b  xorps   xmm0, xmm0
0x18001fa6e  mov     [rbp+1D0h+var_D0], 0FA000000h
0x18001fa78  mov     r12d, r13d
0x18001fa7b  mov     [rbp+1D0h+var_CC], r13d
0x18001fa82  movups  [rbp+1D0h+var_230], xmm0
0x18001fa86  test    r14, r14
0x18001fa89  jz      short loc_18001FAB6
0x18001fa8b  mov     r9d, 10h
0x18001fa91  mov     [rsp+2D0h+var_2B0], r13
0x18001fa96  lea     r8, [rbp+1D0h+var_230]
0x18001fa9a  xor     edx, edx
0x18001fa9c  mov     rcx, r14
0x18001fa9f  call    cs:__imp_NtAlpcQueryInformation
0x18001faa5  test    eax, eax
0x18001faa7  js      short loc_18001FAB6
0x18001faa9  test    dword ptr [rbp+1D0h+var_230], 1000000h
0x18001fab0  jnz     loc_18002007C
0x18001fab6  mov     [rbp+1D0h+var_250], 1000h
0x18001fabe  mov     edx, 1000h; unsigned __int64
0x18001fac3  call    ?Allocate@BCACHE@@QEAAPEAX_K@Z; BCACHE::Allocate(unsigned __int64)
0x18001fac8  mov     rbx, rax
0x18001facb  test    rax, rax
0x18001face  jz      loc_1800201E1
0x18001fad4  mov     [rsp+2D0h+var_298], r13
0x18001fad9  lea     rax, [rbp+1D0h+var_D0]
0x18001fae0  mov     [rsp+2D0h+var_2A0], rax
0x18001fae5  xor     r9d, r9d
0x18001fae8  lea     rax, [rbp+1D0h+var_250]
0x18001faec  xor     r8d, r8d
0x18001faef  mov     [rsp+2D0h+var_2A8], rax
0x18001faf4  xor     edx, edx
0x18001faf6  mov     rcx, r14
0x18001faf9  mov     [rsp+2D0h+var_2B0], rbx
0x18001fafe  call    cs:__imp_NtAlpcSendWaitReceivePort
0x18001fb04  mov     esi, eax
0x18001fb06  test    eax, eax
0x18001fb08  jnz     loc_180020120
0x18001fb0e  test    rbx, rbx
0x18001fb11  jz      loc_180020602
0x18001fb17  movsx   edx, word ptr [rbx+2]
0x18001fb1b  cmp     cs:dword_1800F9624, r13d
0x18001fb22  jz      short loc_18001FB52
0x18001fb24  mov     ecx, r13d
0x18001fb27  lea     r8, __ImageBase
0x18001fb2e  cmp     ecx, 4
0x18001fb31  jnb     short loc_18001FB45
0x18001fb33  movsxd  rax, ecx
0x18001fb36  cmp     byte ptr [rax+r8+0E1808h], 4Ch ; 'L'
0x18001fb3f  jz      short loc_18001FB52
0x18001fb41  inc     ecx
0x18001fb43  jmp     short loc_18001FB2E
0x18001fb45  test    cs:Microsoft_Windows_RPCEnableBits, 8
0x18001fb4c  jnz     loc_18001FDF6
0x18001fb52  test    esi, esi
0x18001fb54  jnz     loc_18002064F
0x18001fb5a  xor     r10d, r10d
0x18001fb5d  lea     r15, [rbx+4]
0x18001fb61  mov     eax, 0FFh
0x18001fb66  mov     r14d, r10d
0x18001fb69  and     ax, [r15]
0x18001fb6d  mov     r9d, 1
0x18001fb73  movzx   r13d, ax
0x18001fb77  mov     esi, r13d
0x18001fb7a  test    r12d, r12d
0x18001fb7d  jnz     short loc_18001FB82
0x18001fb7f  mov     r9d, r10d
0x18001fb82  mov     rax, [rbp+1D0h+var_220]
0x18001fb86  neg     rax
0x18001fb89  sbb     r8, r8
0x18001fb8c  and     r8d, 4
0x18001fb90  cmp     cs:dword_1800F9624, 0
0x18001fb97  jz      short loc_18001FBC6
0x18001fb99  mov     eax, r10d
0x18001fb9c  cmp     eax, 4
0x18001fb9f  jnb     short loc_18001FBB9
0x18001fba1  movsxd  rcx, eax
0x18001fba4  lea     rdx, __ImageBase
0x18001fbab  cmp     byte ptr [rcx+rdx+0E1808h], 41h ; 'A'
0x18001fbb3  jz      short loc_18001FBC6
0x18001fbb5  inc     eax
0x18001fbb7  jmp     short loc_18001FB9C
0x18001fbb9  test    cs:Microsoft_Windows_RPCEnableBits, 8
0x18001fbc0  jnz     loc_18001FD3B
0x18001fbc6  mov     ecx, 1
0x18001fbcb  lock xadd [rdi+190h], ecx
0x18001fbd3  mov     eax, [rdi+194h]
0x18001fbd9  inc     ecx
0x18001fbdb  cmp     ecx, eax
0x18001fbdd  jz      loc_18002000C
0x18001fbe3  xor     ecx, ecx; this
0x18001fbe5  xor     eax, eax
0x18001fbe7  lock cmpxchg [rdi+194h], ecx
0x18001fbef  test    eax, eax
0x18001fbf1  jg      loc_180020432
0x18001fbf7  test    r12d, r12d
0x18001fbfa  jnz     loc_180020223
0x18001fc00  cmp     esi, 1
0x18001fc03  jnz     loc_18002017B
0x18001fc09  mov     eax, [rbx+28h]
0x18001fc0c  test    eax, eax
0x18001fc0e  jnz     loc_180020127
0x18001fc14  mov     eax, [rdi+1A0h]
0x18001fc1a  mov     edx, eax; unsigned __int64
0x18001fc1c  cmp     eax, 1000h
0x18001fc21  jbe     loc_18001FD31
0x18001fc27  call    ?Allocate@BCACHE@@QEAAPEAX_K@Z; BCACHE::Allocate(unsigned __int64)
0x18001fc2c  mov     r8, [rsp+2D0h+var_280]; struct RPCP_ALPC_MESSAGE_ATTRIBUTES *
0x18001fc31  mov     r9, rax; struct _PORT_MESSAGE *
0x18001fc34  mov     rdx, rbx; struct _PORT_MESSAGE *
0x18001fc37  mov     dword ptr [rsp+2D0h+var_2B0], r14d; int
0x18001fc3c  mov     rcx, rdi; this
0x18001fc3f  call    ?HandleRequest@LRPC_ADDRESS@@AEAAXPEAU_PORT_MESSAGE@@PEAVRPCP_ALPC_MESSAGE_ATTRIBUTES@@0H@Z; LRPC_ADDRESS::HandleRequest(_PORT_MESSAGE *,RPCP_ALPC_MESSAGE_ATTRIBUTES *,_PORT_MESSAGE *,int)
0x18001fc44  xor     r13d, r13d
0x18001fc47  lea     r15, [rdi+1A8h]
0x18001fc4e  cmp     [rsp+2D0h+var_258], 0
0x18001fc53  jle     loc_18001FCF1
0x18001fc59  lea     rsi, [rdi+128h]
0x18001fc60  mov     rcx, [rsi]
0x18001fc63  call    cs:__imp_AlpcUnregisterCompletionListWorkerThread
0x18001fc69  cmp     cs:dword_1800F9624, 0
0x18001fc70  mov     ebx, eax
0x18001fc72  jz      short loc_18001FCA1
0x18001fc74  mov     edx, r13d
0x18001fc77  lea     rax, __ImageBase
0x18001fc7e  cmp     edx, 4
0x18001fc81  jnb     short loc_18001FC94
0x18001fc83  movsxd  rcx, edx
0x18001fc86  cmp     byte ptr [rcx+rax+0E1808h], 4Ch ; 'L'
0x18001fc8e  jz      short loc_18001FCA1
0x18001fc90  inc     edx
0x18001fc92  jmp     short loc_18001FC7E
0x18001fc94  test    cs:Microsoft_Windows_RPCEnableBits, 8
0x18001fc9b  jnz     loc_18001FEED
0x18001fca1  test    ebx, ebx
0x18001fca3  jnz     short loc_18001FCE9
0x18001fca5  mov     rax, gs:30h
0x18001fcae  mov     rbx, [rax+1698h]
0x18001fcb5  test    rbx, rbx
0x18001fcb8  jz      loc_18001FEAE
0x18001fcbe  mov     rax, 0ABABABABDEDEDEDEh
0x18001fcc8  xor     rbx, rax
0x18001fccb  mov     rax, gs:30h
0x18001fcd4  mov     rcx, [rax+48h]
0x18001fcd8  cmp     [rbx+10h], rcx
0x18001fcdc  jz      loc_18001FE8C
0x18001fce2  mov     ecx, 1Eh
0x18001fce7  int     29h; Win8: RtlFailFast(ecx)
0x18001fce9  mov     rcx, rdi; this
0x18001fcec  call    ?UnlockCompletionListZone@LRPC_ADDRESS@@AEAAXXZ; LRPC_ADDRESS::UnlockCompletionListZone(void)
0x18001fcf1  mov     rcx, r15
0x18001fcf4  call    cs:__imp_RtlReleaseSRWLockShared
0x18001fcfa  mov     rsi, [rsp+2D0h+arg_8]
0x18001fd02  mov     r12, [rsp+2D0h+arg_10]
0x18001fd0a  mov     rcx, [rbp+1D0h+var_30]
0x18001fd11  xor     rcx, rsp; StackCookie
0x18001fd14  call    __security_check_cookie
0x18001fd19  mov     rbx, [rsp+2D0h+arg_18]
0x18001fd21  add     rsp, 2B0h
0x18001fd28  pop     r15
0x18001fd2a  pop     r14
0x18001fd2c  pop     r13
0x18001fd2e  pop     rdi
0x18001fd2f  pop     rbp
0x18001fd30  retn
0x18001fd31  mov     edx, 1000h
0x18001fd36  jmp     loc_18001FC27
0x18001fd3b  mov     rax, [rsp+2D0h+var_280]
0x18001fd40  lea     ecx, [r14+r14]
0x18001fd44  mov     edx, esi
0x18001fd46  mov     [rbp+1D0h+var_210], rbx
0x18001fd4a  shl     edx, 8
0x18001fd4d  or      rdx, rcx
0x18001fd50  mov     [rbp+1D0h+var_218], rdi
0x18001fd54  mov     ecx, [rax+4]
0x18001fd57  or      rdx, rcx
0x18001fd5a  mov     eax, r9d
0x18001fd5d  or      rdx, rax
0x18001fd60  mov     [rsp+2D0h+var_270], 6Bh ; 'k'
0x18001fd65  or      rdx, r8
0x18001fd68  mov     [rsp+2D0h+var_278], 41h ; 'A'
0x18001fd6d  lea     rax, [rsp+2D0h+var_278]
0x18001fd72  mov     [rbp+1D0h+var_208], rdx
0x18001fd76  mov     [rbp+1D0h+var_180], rax
0x18001fd7a  lea     rdx, RPCLogEvent
0x18001fd81  lea     rax, [rsp+2D0h+var_270]
0x18001fd86  mov     [rbp+1D0h+var_178], 1
0x18001fd8e  mov     [rbp+1D0h+var_170], rax
0x18001fd92  lea     rcx, RpcEtwGuid_Context
0x18001fd99  lea     rax, [rbp+1D0h+var_218]
0x18001fd9d  mov     [rbp+1D0h+var_168], 1
0x18001fda5  mov     [rbp+1D0h+var_160], rax
0x18001fda9  mov     r9d, 6
0x18001fdaf  lea     rax, [rbp+1D0h+var_210]
0x18001fdb3  mov     [rbp+1D0h+var_158], 8
0x18001fdbb  mov     [rbp+1D0h+var_150], rax
0x18001fdc2  lea     rax, [rbp+1D0h+var_208]
0x18001fdc6  mov     [rbp+1D0h+var_140], rax
0x18001fdcd  lea     rax, [rbp+1D0h+var_190]
0x18001fdd1  mov     [rsp+2D0h+var_2B0], rax
0x18001fdd6  mov     [rbp+1D0h+var_148], 8
0x18001fde1  mov     [rbp+1D0h+var_138], 8
0x18001fdec  call    McGenEventWrite_EtwEventWriteTransfer
0x18001fdf1  jmp     loc_18001FBC6
0x18001fdf6  movsxd  rax, edx
0x18001fdf9  lea     rcx, RpcEtwGuid_Context
0x18001fe00  mov     [rbp+1D0h+var_248], rax
0x18001fe04  lea     rdx, RPCLogEvent
0x18001fe0b  lea     rax, [rsp+2D0h+var_288]
0x18001fe10  mov     [rbp+1D0h+var_238], rbx
0x18001fe14  mov     [rbp+1D0h+var_1E0], rax
0x18001fe18  or      r14, 1
0x18001fe1c  lea     rax, [rsp+2D0h+var_290]
0x18001fe21  mov     [rbp+1D0h+var_240], r14
0x18001fe25  mov     [rbp+1D0h+var_1D0], rax
0x18001fe29  mov     r9d, 6
0x18001fe2f  lea     rax, [rbp+1D0h+var_238]
0x18001fe33  mov     [rsp+2D0h+var_290], 4Bh ; 'K'
0x18001fe38  mov     [rbp+1D0h+var_1C0], rax
0x18001fe3c  lea     rax, [rbp+1D0h+var_240]
0x18001fe40  mov     [rbp+1D0h+var_1B0], rax
0x18001fe44  lea     rax, [rbp+1D0h+var_248]
0x18001fe48  mov     [rbp+1D0h+var_1A0], rax
0x18001fe4c  lea     rax, [rbp+1D0h+var_1F0]
0x18001fe50  mov     [rsp+2D0h+var_2B0], rax
0x18001fe55  mov     [rsp+2D0h+var_288], 4Ch ; 'L'
0x18001fe5a  mov     [rbp+1D0h+var_1D8], 1
0x18001fe62  mov     [rbp+1D0h+var_1C8], 1
0x18001fe6a  mov     [rbp+1D0h+var_1B8], 8
0x18001fe72  mov     [rbp+1D0h+var_1A8], 8
0x18001fe7a  mov     [rbp+1D0h+var_198], 8
0x18001fe82  call    McGenEventWrite_EtwEventWriteTransfer
0x18001fe87  jmp     loc_18001FB52
0x18001fe8c  mov     rcx, [rbx+0C0h]
0x18001fe93  test    rcx, rcx
0x18001fe96  jz      short loc_18001FEAE
0x18001fe98  cmp     dword ptr [rbx+0C8h], 0
0x18001fe9f  jz      short loc_18001FEAE
0x18001fea1  call    cs:__imp_TpCallbackSendPendingAlpcMessage
0x18001fea7  mov     [rbx+0C8h], r13d
0x18001feae  mov     rcx, [rsi]
0x18001feb1  lea     rdx, [rsp+2D0h+var_280]
0x18001feb6  call    cs:__imp_AlpcGetMessageFromCompletionList
0x18001febc  mov     rbx, rax
0x18001febf  test    rax, rax
0x18001fec2  jz      loc_18001FC4E
0x18001fec8  lea     r15, [rax+4]
  ... truncated ...
```
