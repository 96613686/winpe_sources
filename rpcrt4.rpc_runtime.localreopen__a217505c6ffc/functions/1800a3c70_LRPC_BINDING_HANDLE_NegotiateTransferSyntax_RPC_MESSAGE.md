# LRPC_BINDING_HANDLE::NegotiateTransferSyntax(_RPC_MESSAGE *)

- ea: `0x1800a3c70`
- end: `0x1800a4772`
- name: `?NegotiateTransferSyntax@LRPC_BINDING_HANDLE@@UEAAJPEAU_RPC_MESSAGE@@@Z`
- size: `2818`
- prototype: `__int64 __fastcall(LRPC_BINDING_HANDLE *__hidden this, struct _RPC_MESSAGE *)`
- caller_count: `0`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001aa68`
- `0x1800217d0`
- `0x180022e80`
- `0x180022fb8`
- `0x180026c60`
- `0x180026df0`
- `0x1800295d8`
- `0x180029fc0`
- `0x18002af84`
- `0x18002b04c`
- `0x18002b9fc`
- `0x180031efc`
- `0x180072390`
- `0x18007dfc0`
- `0x1800a3c70`
- `0x1800ceda0`
- `0x1800d7010`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x1800a404e`
- `ntdll!EtwEventActivityIdControl` at `0x1800a4451`
- `ntdll!EtwEventActivityIdControl` at `0x1800a404e`
- `ntdll!EtwEventActivityIdControl` at `0x1800a4451`
- `ntdll!RtlInitializeCriticalSectionAndSpinCount` at `0x1800a3eae`
- `ntdll!RtlInitializeCriticalSectionAndSpinCount` at `0x1800a40cf`
- `ntdll!RtlInitializeCriticalSectionAndSpinCount` at `0x1800a3eae`
- `ntdll!RtlInitializeCriticalSectionAndSpinCount` at `0x1800a40cf`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a3d30`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a3d94`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a3e38`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a3f09`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a4265`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a42dd`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a44a4`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a46dd`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a3d30`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a3d94`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a3e38`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a3f09`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a4265`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a42dd`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a44a4`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a46dd`
- `ntdll!RtlEnterCriticalSection` at `0x1800a3ccf`
- `ntdll!RtlEnterCriticalSection` at `0x1800a3d74`
- `ntdll!RtlEnterCriticalSection` at `0x1800a3fe4`
- `ntdll!RtlEnterCriticalSection` at `0x1800a4127`
- `ntdll!RtlEnterCriticalSection` at `0x1800a3ccf`
- `ntdll!RtlEnterCriticalSection` at `0x1800a3d74`
- `ntdll!RtlEnterCriticalSection` at `0x1800a3fe4`
- `ntdll!RtlEnterCriticalSection` at `0x1800a4127`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a3e6d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a3fc4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a3e6d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a3fc4`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x1800a43a1`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x1800a43a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a3ce0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a3ce0`

## pseudocode

```c
__int64 __fastcall LRPC_BINDING_HANDLE::NegotiateTransferSyntax(LRPC_BINDING_HANDLE *this, struct _RPC_MESSAGE *a2)
{
  __int64 v2; // r13
  struct LRPC_CCALL *Alignment; // rbx
  struct _RPC_MESSAGE *v4; // r14
  DWORD CurrentThreadId; // eax
  __int64 *v7; // r10
  unsigned int v8; // ecx
  DWORD v9; // r11d
  unsigned int v10; // r8d
  __int64 v11; // r9
  unsigned int v12; // edx
  bool v13; // zf
  int v14; // r15d
  BCACHE *v15; // rcx
  __int64 v16; // rax
  unsigned __int64 ReservedForNtRpc; // rdx
  __int64 v18; // rax
  int v19; // r15d
  unsigned __int64 v20; // r12
  struct _RTL_CRITICAL_SECTION *v21; // rax
  struct _RTL_CRITICAL_SECTION *v22; // rdi
  unsigned int v23; // edi
  _QWORD *v25; // r14
  _QWORD *v26; // rdx
  _QWORD *v27; // rdi
  LRPC_BINDING_HANDLE **v28; // rcx
  _QWORD *v29; // r8
  _QWORD *v30; // rax
  struct LRPC_CAUSAL_FLOW *v31; // rax
  struct LRPC_CAUSAL_FLOW *v32; // rdi
  _QWORD *v33; // r12
  _QWORD *v34; // rax
  __int64 v35; // rcx
  int v36; // r15d
  struct _LIST_ENTRY *v37; // rdx
  LRPC_BINDING_HANDLE *Flink; // rdi
  struct _LIST_ENTRY *Blink; // rcx
  struct _LIST_ENTRY *v40; // rax
  struct _LIST_ENTRY *v41; // rax
  _QWORD *v42; // rax
  __int64 v43; // rdx
  __int64 v44; // rax
  int v45; // edi
  LRPC_CASSOCIATION *v46; // rdi
  __int64 v47; // rdx
  union _SLIST_HEADER *v48; // rdx
  PSLIST_ENTRY v49; // rax
  int v50; // eax
  int v51; // edx
  int v52; // edi
  __int16 v53; // cx
  __int64 v54; // rax
  signed __int32 v55[8]; // [rsp+0h] [rbp-100h] BYREF
  struct LRPC_CCALL **v56; // [rsp+28h] [rbp-D8h]
  int v57; // [rsp+30h] [rbp-D0h]
  int v58; // [rsp+40h] [rbp-C0h] BYREF
  int v59; // [rsp+44h] [rbp-BCh]
  char v60; // [rsp+48h] [rbp-B8h] BYREF
  char v61; // [rsp+50h] [rbp-B0h] BYREF
  int v62; // [rsp+58h] [rbp-A8h]
  struct LRPC_CCALL *v63; // [rsp+60h] [rbp-A0h] BYREF
  struct _RPC_MESSAGE *v64; // [rsp+68h] [rbp-98h]
  struct LRPC_CAUSAL_FLOW *v65; // [rsp+70h] [rbp-90h]
  struct _LIST_ENTRY v66; // [rsp+78h] [rbp-88h] BYREF
  char v67[8]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v68; // [rsp+90h] [rbp-70h] BYREF
  LRPC_BINDING_HANDLE *v69; // [rsp+98h] [rbp-68h] BYREF
  __int64 v70; // [rsp+A0h] [rbp-60h] BYREF
  char v71[16]; // [rsp+B0h] [rbp-50h] BYREF
  char *v72; // [rsp+C0h] [rbp-40h]
  __int64 v73; // [rsp+C8h] [rbp-38h]
  char *v74; // [rsp+D0h] [rbp-30h]
  __int64 v75; // [rsp+D8h] [rbp-28h]
  LRPC_BINDING_HANDLE **v76; // [rsp+E0h] [rbp-20h]
  __int64 v77; // [rsp+E8h] [rbp-18h]
  __int64 *v78; // [rsp+F0h] [rbp-10h]
  __int64 v79; // [rsp+F8h] [rbp-8h]
  __int64 *v80; // [rsp+100h] [rbp+0h]
  __int64 v81; // [rsp+108h] [rbp+8h]

  LODWORD(v2) = 0;
  v64 = a2;
  Alignment = 0;
  v4 = a2;
  v63 = 0;
  v58 = 0;
  v65 = 0;
  v62 = 0;
  if ( *((_QWORD *)this + 78) )
  {
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 304));
    v58 = 0;
    CurrentThreadId = GetCurrentThreadId();
    v7 = (__int64 *)*((_QWORD *)this + 78);
    v8 = 0;
    v9 = CurrentThreadId;
    v10 = *((_DWORD *)v7 + 2);
    while ( v8 < v10 )
    {
      v11 = *v7;
      while ( 1 )
      {
        v12 = v8 + 1;
        Alignment = *(struct LRPC_CCALL **)(v11 + 8LL * v8);
        if ( Alignment )
          break;
        ++v8;
        if ( v12 >= v10 )
          goto LABEL_7;
      }
      v18 = *((_QWORD *)Alignment + 74);
      v63 = *(struct LRPC_CCALL **)(v11 + 8LL * v8);
      if ( *(_DWORD *)(v18 + 200) == v9 )
      {
        v19 = 0;
        v59 = 0;
        LODWORD(v20) = 0;
        RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 304));
        goto LABEL_120;
      }
      ++v8;
    }
LABEL_7:
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 304));
    Alignment = 0;
    v63 = 0;
  }
  v13 = (v4->RpcFlags & 0x8000) == 0;
  v14 = v4->RpcFlags & 0x8000;
  v59 = v14;
  if ( !v13 )
  {
    if ( (*((_DWORD *)this + 124) & 1) != 0 )
      goto LABEL_14;
    if ( LrpcAsyncInitialized )
    {
LABEL_13:
      v58 = 0;
LABEL_14:
      if ( (v4->RpcFlags & 0x2000) != 0 )
        goto LABEL_48;
      v16 = *((_QWORD *)this + 8);
      if ( v16 )
      {
        if ( *(_QWORD *)(v16 + 72) )
          goto LABEL_48;
      }
      ReservedForNtRpc = (unsigned __int64)NtCurrentTeb()->ReservedForNtRpc;
      if ( ReservedForNtRpc )
      {
        ReservedForNtRpc ^= 0xABABABABDEDEDEDEuLL;
        if ( *(HANDLE *)(ReservedForNtRpc + 16) != NtCurrentTeb()->ClientId.UniqueThread )
          __fastfail(0x1Eu);
      }
      v25 = (_QWORD *)(ReservedForNtRpc + 160);
      v26 = *(_QWORD **)(ReservedForNtRpc + 160);
      if ( v26 != v25 )
      {
        do
        {
          v27 = (_QWORD *)*v26;
          v28 = (LRPC_BINDING_HANDLE **)(v26 - 8);
          v65 = (struct LRPC_CAUSAL_FLOW *)(v26 - 8);
          _InterlockedOr(v55, 0);
          if ( *((_DWORD *)v26 - 12) == 1 )
          {
            v29 = (_QWORD *)v26[1];
            if ( (_QWORD *)*v29 != v26 || (v30 = (_QWORD *)*v26, *(_QWORD **)(*v26 + 8LL) != v26) )
            {
              RpcpReportFatalError(21, v26);
              JUMPOUT(0x1800A4771LL);
            }
            if ( v30 )
            {
              *v29 = v30;
              v30[1] = v29;
            }
            v26[1] = 0;
            *v26 = 0;
            (*((void (__fastcall **)(LRPC_BINDING_HANDLE **))*v28 + 4))(v28);
          }
          else if ( v28[17] == this )
          {
            v58 = 0;
            goto LABEL_48;
          }
          v26 = v27;
        }
        while ( v27 != v25 );
      }
      if ( LsaAlloc )
        v31 = (struct LRPC_CAUSAL_FLOW *)LsaAlloc(0x90u);
      else
        v31 = (struct LRPC_CAUSAL_FLOW *)HeapAlloc(hRpcHeap, 0, 0x90u);
      v65 = v31;
      v32 = v31;
      LogEvent(0x48u, 0x43u, v31, hRpcHeap, 0x90u, (int)v56, v57);
      if ( v32 )
      {
        *((_DWORD *)v32 + 2) = -1985229329;
        v33 = (_QWORD *)((char *)v32 + 24);
        *((_QWORD *)v32 + 3) = 0;
        *(_QWORD *)v32 = &LRPC_CAUSAL_FLOW::`vftable';
        *((_DWORD *)v32 + 4) = 1;
        *((_DWORD *)v32 + 14) = 0;
        *((_DWORD *)v32 + 3) = 2;
        *((_DWORD *)v32 + 10) = 0;
        *((_QWORD *)v32 + 4) = 0;
        RtlInitializeCriticalSectionAndSpinCount((PRTL_CRITICAL_SECTION)v32 + 2, 0);
        *((_QWORD *)v32 + 17) = this;
        *((_QWORD *)v32 + 16) = (char *)v32 + 120;
        *((_QWORD *)v32 + 15) = (char *)v32 + 120;
        *((_DWORD *)v32 + 4) = 2;
        _InterlockedOr(v55, 0);
        *((_QWORD *)v32 + 8) = 0;
        v34 = (_QWORD *)((char *)v32 + 64);
        *((_QWORD *)v32 + 9) = 0;
        v35 = *v25;
        if ( *(_QWORD **)(*v25 + 8LL) != v25 )
          goto LABEL_76;
        *v34 = v35;
        *((_QWORD *)v32 + 9) = v25;
        *(_QWORD *)(v35 + 8) = v34;
        *v25 = v34;
        RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 304));
        v36 = *((_DWORD *)this + 99);
        v66.Blink = &v66;
        v37 = (struct _LIST_ENTRY *)*((_QWORD *)this + 75);
        v66.Flink = &v66;
        if ( v37 != (struct _LIST_ENTRY *)((char *)this + 600) )
        {
          do
          {
            Flink = (LRPC_BINDING_HANDLE *)v37->Flink;
            _InterlockedOr(v55, 0);
            if ( LODWORD(v37[-1].Blink) == 1 )
            {
              Blink = v37->Blink;
              if ( Blink->Flink != v37 || (v40 = v37->Flink, v37->Flink->Blink != v37) )
              {
                RpcpReportFatalError(21, v37);
                __debugbreak();
              }
              if ( v40 )
              {
                Blink->Flink = v40;
                v40->Blink = Blink;
              }
              v37->Blink = 0;
              v37->Flink = 0;
              if ( v36 < 5 )
              {
                ((void (__fastcall *)(struct _LIST_ENTRY **))v37[-2].Blink[2].Flink)(&v37[-2].Blink);
              }
              else
              {
                v37[7].Flink = 0;
                v41 = v66.Flink;
                if ( v66.Flink->Blink != &v66 )
                  goto LABEL_76;
                v37->Flink = v66.Flink;
                v37->Blink = &v66;
                v41->Blink = v37;
                v66.Flink = v37;
              }
              --*((_DWORD *)this + 148);
            }
            v37 = (struct _LIST_ENTRY *)Flink;
          }
          while ( Flink != (LRPC_BINDING_HANDLE *)((char *)this + 600) );
          v32 = v65;
        }
        if ( v36 >= 5 )
          LRPC_CASSOCIATION::SendCausalFlowListForCleanup(*((LRPC_CASSOCIATION **)this + 61), &v66);
        if ( *((int *)this + 99) >= 9 )
          *((_QWORD *)v32 + 6) = _InterlockedIncrement64((volatile signed __int64 *)(*((_QWORD *)this + 61) + 320LL));
        v42 = (_QWORD *)((char *)this + 600);
        v43 = *((_QWORD *)this + 75);
        if ( *(LRPC_BINDING_HANDLE **)(v43 + 8) != (LRPC_BINDING_HANDLE *)((char *)this + 600) )
LABEL_76:
          __fastfail(3u);
        *v33 = v43;
        v33[1] = v42;
        *(_QWORD *)(v43 + 8) = v33;
        *v42 = v33;
        ++*((_DWORD *)this + 148);
        RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 304));
        v14 = v59;
        v58 = 0;
LABEL_48:
        LODWORD(v20) = v2;
        goto LABEL_49;
      }
      return 14;
    }
    RtlEnterCriticalSection(&GlobalMutex);
    if ( LrpcAsyncInitialized )
    {
      RtlLeaveCriticalSection(&GlobalMutex);
      goto LABEL_13;
    }
    if ( !LrpcEmergencyMessageMutex )
    {
      if ( LsaAlloc )
        v21 = (struct _RTL_CRITICAL_SECTION *)LsaAlloc(0x28u);
      else
        v21 = (struct _RTL_CRITICAL_SECTION *)HeapAlloc(hRpcHeap, 0, 0x28u);
      v22 = v21;
      LogEvent(0x48u, 0x43u, v21, hRpcHeap, 0x28u, (int)v56, v57);
      if ( !v22 )
      {
        LrpcEmergencyMessageMutex = 0;
        v23 = 14;
        goto LABEL_34;
      }
      RtlInitializeCriticalSectionAndSpinCount(v22, 0);
      LrpcEmergencyMessageMutex = v22;
    }
    if ( LrpcEmergencyMessage || (LrpcEmergencyMessage = BCACHE::Allocate(v15, 0x1000u)) != 0 )
    {
      v23 = 0;
      LrpcAsyncInitialized = 1;
    }
    else
    {
      v23 = 14;
    }
LABEL_34:
    RtlLeaveCriticalSection(&GlobalMutex);
    v58 = v23;
    if ( v23 )
      return v23;
    goto LABEL_14;
  }
  v44 = *((_QWORD *)this + 8);
  if ( !v44 )
    goto LABEL_48;
  v2 = *(_QWORD *)(v44 + 96);
  if ( !v2 )
    goto LABEL_48;
  v20 = (MEMORY[0x7FFE0320] * (unsigned __int64)MEMORY[0x7FFE0004]) >> 24;
  while ( 1 )
  {
LABEL_49:
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 304));
    if ( *((int *)this + 99) >= 9 )
    {
      v46 = (LRPC_CASSOCIATION *)*((_QWORD *)this + 61);
      if ( v14 )
      {
        if ( (*((_DWORD *)this + 124) & 1) == 0 )
        {
          v58 = LRPC_BASE_BINDING_HANDLE::EnableAsyncIfNecessary(this);
          if ( v58 )
            goto LABEL_131;
        }
      }
      if ( !Alignment )
      {
        v47 = 528;
        if ( v14 )
          v47 = 560;
        v48 = (union _SLIST_HEADER *)((char *)this + v47);
        Alignment = (struct LRPC_CCALL *)v48->Alignment;
        if ( v48->Alignment
          && Alignment == (struct LRPC_CCALL *)_InterlockedCompareExchange64(
                                                 (volatile signed __int64 *)v48,
                                                 0,
                                                 (signed __int64)Alignment) )
        {
          v63 = Alignment;
LABEL_99:
          v58 = LRPC_CCALL::ReinitCachedCall(
                  Alignment,
                  (struct _RPC_CLIENT_INTERFACE *)v64->RpcInterfaceInformation,
                  v65);
          if ( v58 )
          {
            (*(void (__fastcall **)(struct LRPC_CCALL *, __int64))(*(_QWORD *)Alignment + 8LL))(Alignment, 1);
LABEL_101:
            Alignment = 0;
            goto LABEL_131;
          }
        }
        else
        {
          v49 = InterlockedPopEntrySList(v48 + 1);
          if ( v49 )
          {
            Alignment = (struct LRPC_CCALL *)&v49[-37];
            v63 = (struct LRPC_CCALL *)&v49[-37];
            if ( v49 != (PSLIST_ENTRY)592 )
              goto LABEL_99;
          }
          else
          {
            v63 = 0;
          }
          v58 = LRPC_CASSOCIATION::AllocateCall(v46, v64, v20, this, v65, &v63);
          if ( v58 )
            goto LABEL_101;
          Alignment = v63;
        }
        if ( dword_1800FE624 )
        {
          EtwEventActivityIdControl(1);
          v45 = v59;
        }
        else
        {
          v45 = v59;
          *((GUID *)Alignment + 13) = g_NullActivityId;
        }
LABEL_109:
        RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 304));
        v19 = 0;
        if ( !v45 && !v62 )
        {
          v58 = LRPC_CCALL::RegisterCallForCancels(Alignment);
          if ( v58 )
            goto LABEL_132;
          v62 = 1;
        }
LABEL_113:
        v50 = LRPC_BIND_CCALL::Bind(Alignment, v45, 0, 0, *((struct LRPC_BINDING **)this + 79));
        v58 = v50;
        if ( dword_1800FE624 )
        {
          v51 = 0;
          while ( `LogEventToEtw'::`2'::EtwEventSubjectFilter[v51] != 104 )
          {
            if ( (unsigned int)++v51 >= 4 )
            {
              if ( (Microsoft_Windows_RPCEnableBits & 8) != 0 )
              {
                v68 = v50;
                v70 = 0;
                v72 = &v60;
                v69 = this;
                v74 = &v61;
                v76 = &v69;
                v78 = &v70;
                v80 = &v68;
                v61 = 111;
                v60 = 104;
                v73 = 1;
                v75 = 1;
                v77 = 8;
                v79 = 8;
                v81 = 8;
                McGenEventWrite_EtwEventWriteTransfer(
                  (unsigned int)&RpcEtwGuid_Context,
                  (unsigned int)RPCLogEvent,
                  (unsigned int)"HbBr",
                  6,
                  (__int64)v71);
              }
              goto LABEL_119;
            }
          }
        }
        goto LABEL_119;
      }
      v45 = v59;
      v19 = 1;
      v58 = LRPC_BASE_BINDING_HANDLE::DriveStateForward(this, v59, v2, Alignment);
      if ( !v58 )
        goto LABEL_109;
    }
    else
    {
      if ( !Alignment )
      {
        v58 = LRPC_BINDING_HANDLE::AllocateCall(this, v64, v20, v65, &v63);
        if ( v58 )
          goto LABEL_101;
        Alignment = v63;
        if ( dword_1800FE624 )
          EtwEventActivityIdControl(1);
        else
          *((GUID *)v63 + 13) = g_NullActivityId;
      }
      RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 304));
      if ( !v14 && !v62 )
      {
        v58 = LRPC_CCALL::RegisterCallForCancels(Alignment);
        if ( v58 )
          goto LABEL_133;
        v62 = 1;
      }
      v45 = v59;
      v19 = 0;
      v58 = LRPC_BASE_BINDING_HANDLE::DriveStateForward(this, v59, v2, Alignment);
      if ( !v58 )
        goto LABEL_113;
    }
LABEL_119:
    v4 = v64;
LABEL_120:
    v52 = v58;
    if ( !v58 )
      break;
    if ( v58 == -1073606632 )
    {
      v4->Handle = Alignment;
      v58 = 0;
      goto LABEL_130;
    }
    v53 = *(_WORD *)(*(__int64 (__fastcall **)(LRPC_BINDING_HANDLE *, char *, int *, struct LRPC_CCALL *))(*(_QWORD *)this + 464LL))(
                      this,
                      v67,
                      &v58,
                      Alignment);
    if ( !HIBYTE(v53) )
    {
      if ( !(_BYTE)v53 )
        (*(void (__fastcall **)(LRPC_BINDING_HANDLE *, _QWORD, struct LRPC_CCALL *))(*(_QWORD *)this + 480LL))(
          this,
          (unsigned int)v58,
          Alignment);
      goto LABEL_130;
    }
    v58 = (*(__int64 (__fastcall **)(LRPC_BINDING_HANDLE *, _QWORD, struct LRPC_CCALL *))(*(_QWORD *)this + 472LL))(
            this,
            (unsigned int)v58,
            Alignment);
    if ( v58 )
      goto LABEL_130;
    RpcpErrorAddRecord(2u, v52, 0x4F6u, 0, 0);
    v14 = v59;
  }
  v54 = *((_QWORD *)Alignment + 79) + 24LL;
  v4->Handle = Alignment;
  v13 = v59 == 0;
  v4->TransferSyntax = (PRPC_SYNTAX_IDENTIFIER)v54;
  *((_QWORD *)this + 79) = *((_QWORD *)Alignment + 79);
  if ( !v13 )
  {
    _InterlockedOr((volatile signed __int32 *)Alignment + 72, 0x100u);
    (*(void (__fastcall **)(struct LRPC_CCALL *))(*(_QWORD *)Alignment + 32LL))(Alignment);
  }
LABEL_130:
  if ( !v19 )
    goto LABEL_132;
LABEL_131:
  RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 304));
LABEL_132:
  v14 = v59;
LABEL_133:
  if ( v58 )
  {
    if ( Alignment )
    {
      if ( v14 )
        (*(void (__fastcall **)(struct LRPC_CCALL *))(*(_QWORD *)Alignment + 32LL))(Alignment);
      else
        LRPC_CCALL::UnregisterCallForCancels(Alignment);
      (*(void (__fastcall **)(struct LRPC_CCALL *))(*(_QWORD *)Alignment + 32LL))(Alignment);
    }
  }
  else
  {
    *((_DWORD *)Alignment + 67) = 1;
  }
  return (unsigned int)v58;
}

```

## disassembly

```asm
0x1800a3c70  mov     [rsp-8+arg_10], rbx
0x1800a3c75  push    rbp
0x1800a3c76  push    rsi
0x1800a3c77  push    rdi
0x1800a3c78  push    r12
0x1800a3c7a  push    r13
0x1800a3c7c  push    r14
0x1800a3c7e  push    r15
0x1800a3c80  lea     rbp, [rsp-20h]
0x1800a3c85  sub     rsp, 120h
0x1800a3c8c  mov     rax, cs:__security_cookie
0x1800a3c93  xor     rax, rsp
0x1800a3c96  mov     [rbp+50h+var_40], rax
0x1800a3c9a  xor     r13d, r13d
0x1800a3c9d  mov     [rsp+150h+var_E8], rdx
0x1800a3ca2  mov     ebx, r13d
0x1800a3ca5  mov     r14, rdx
0x1800a3ca8  mov     rsi, rcx
0x1800a3cab  mov     [rsp+150h+var_F0], rbx
0x1800a3cb0  mov     [rsp+150h+var_110], r13d
0x1800a3cb5  mov     [rsp+150h+var_E0], r13
0x1800a3cba  mov     [rsp+150h+var_F8], r13d
0x1800a3cbf  cmp     [rcx+270h], r13
0x1800a3cc6  jz      short loc_1800A3D44
0x1800a3cc8  add     rcx, 130h; CriticalSection
0x1800a3ccf  call    cs:__imp_RtlEnterCriticalSection
0x1800a3cd6  nop     dword ptr [rax+rax+00h]
0x1800a3cdb  mov     [rsp+150h+var_110], r13d
0x1800a3ce0  call    cs:__imp_GetCurrentThreadId
0x1800a3ce7  nop     dword ptr [rax+rax+00h]
0x1800a3cec  mov     r10, [rsi+270h]
0x1800a3cf3  mov     ecx, r13d
0x1800a3cf6  mov     r11d, eax
0x1800a3cf9  mov     r8d, [r10+8]
0x1800a3cfd  nop     dword ptr [rax]
0x1800a3d00  cmp     ecx, r8d
0x1800a3d03  jnb     short loc_1800A3D29
0x1800a3d05  mov     r9, [r10]
0x1800a3d08  nop     dword ptr [rax+rax+00000000h]
0x1800a3d10  mov     eax, ecx
0x1800a3d12  lea     edx, [rcx+1]
0x1800a3d15  mov     rbx, [r9+rax*8]
0x1800a3d19  test    rbx, rbx
0x1800a3d1c  jnz     loc_1800A3E0A
0x1800a3d22  mov     ecx, edx
0x1800a3d24  cmp     edx, r8d
0x1800a3d27  jb      short loc_1800A3D10
0x1800a3d29  lea     rcx, [rsi+130h]; CriticalSection
0x1800a3d30  call    cs:__imp_RtlLeaveCriticalSection
0x1800a3d37  nop     dword ptr [rax+rax+00h]
0x1800a3d3c  mov     rbx, r13
0x1800a3d3f  mov     [rsp+150h+var_F0], rbx
0x1800a3d44  mov     r15d, [r14+48h]
0x1800a3d48  and     r15d, 8000h
0x1800a3d4f  mov     [rsp+150h+var_10C], r15d
0x1800a3d54  jz      loc_1800A4291
0x1800a3d5a  mov     eax, [rsi+1F0h]
0x1800a3d60  test    al, 1
0x1800a3d62  jnz     short loc_1800A3DA5
0x1800a3d64  cmp     cs:?LrpcAsyncInitialized@@3HA, r13d; int LrpcAsyncInitialized
0x1800a3d6b  jnz     short loc_1800A3DA0
0x1800a3d6d  lea     rcx, ?GlobalMutex@@3PADA; CriticalSection
0x1800a3d74  call    cs:__imp_RtlEnterCriticalSection
0x1800a3d7b  nop     dword ptr [rax+rax+00h]
0x1800a3d80  cmp     cs:?LrpcAsyncInitialized@@3HA, r13d; int LrpcAsyncInitialized
0x1800a3d87  jz      loc_1800A3E49
0x1800a3d8d  lea     rcx, ?GlobalMutex@@3PADA; CriticalSection
0x1800a3d94  call    cs:__imp_RtlLeaveCriticalSection
0x1800a3d9b  nop     dword ptr [rax+rax+00h]
0x1800a3da0  mov     [rsp+150h+var_110], r13d
0x1800a3da5  test    dword ptr [r14+48h], 2000h
0x1800a3dad  jnz     loc_1800A3FDA
0x1800a3db3  mov     rax, [rsi+40h]
0x1800a3db7  test    rax, rax
0x1800a3dba  jz      short loc_1800A3DC6
0x1800a3dbc  cmp     [rax+48h], r13
0x1800a3dc0  jnz     loc_1800A3FDA
0x1800a3dc6  mov     rax, gs:30h
0x1800a3dcf  mov     rdx, [rax+1698h]
0x1800a3dd6  test    rdx, rdx
0x1800a3dd9  jz      loc_1800A3F28
0x1800a3ddf  mov     rax, 0ABABABABDEDEDEDEh
0x1800a3de9  xor     rdx, rax
0x1800a3dec  mov     rax, gs:30h
0x1800a3df5  mov     rcx, [rax+48h]
0x1800a3df9  cmp     [rdx+10h], rcx
0x1800a3dfd  jz      loc_1800A3F28
0x1800a3e03  mov     ecx, 1Eh
0x1800a3e08  int     29h; Win8: RtlFailFast(ecx)
0x1800a3e0a  mov     rax, [rbx+250h]
0x1800a3e11  mov     [rsp+150h+var_F0], rbx
0x1800a3e16  cmp     [rax+0C8h], r11d
0x1800a3e1d  jz      short loc_1800A3E26
0x1800a3e1f  mov     ecx, edx
0x1800a3e21  jmp     loc_1800A3D00
0x1800a3e26  xor     r15d, r15d
0x1800a3e29  mov     [rsp+150h+var_10C], r13d
0x1800a3e2e  lea     rcx, [rsi+130h]; CriticalSection
0x1800a3e35  mov     r12d, r13d
0x1800a3e38  call    cs:__imp_RtlLeaveCriticalSection
0x1800a3e3f  nop     dword ptr [rax+rax+00h]
0x1800a3e44  jmp     loc_1800A45D3
0x1800a3e49  cmp     cs:?LrpcEmergencyMessageMutex@@3PEAVMUTEX@@EA, r13; MUTEX * LrpcEmergencyMessageMutex
0x1800a3e50  jnz     short loc_1800A3EC1
0x1800a3e52  mov     rax, cs:?LsaAlloc@@3P6APEAX_K@ZEA; void * (*LsaAlloc)(unsigned __int64)
0x1800a3e59  test    rax, rax
0x1800a3e5c  jnz     short loc_1800A3E7B
0x1800a3e5e  mov     rcx, cs:?hRpcHeap@@3PEAXEA; hHeap
0x1800a3e65  xor     edx, edx; dwFlags
0x1800a3e67  mov     r8d, 28h ; '('; dwBytes
0x1800a3e6d  call    cs:__imp_HeapAlloc
0x1800a3e74  nop     dword ptr [rax+rax+00h]
0x1800a3e79  jmp     short loc_1800A3E85
0x1800a3e7b  mov     ecx, 28h ; '('
0x1800a3e80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3e85  mov     r9, cs:?hRpcHeap@@3PEAXEA; void *
0x1800a3e8c  mov     r8, rax; void *
0x1800a3e8f  mov     dl, 43h ; 'C'; unsigned __int8
0x1800a3e91  mov     [rsp+150h+var_130], 28h ; '('; unsigned __int64
0x1800a3e9a  mov     cl, 48h ; 'H'; unsigned __int8
0x1800a3e9c  mov     rdi, rax
0x1800a3e9f  call    ?LogEvent@@YAXEEPEAX0_KHH@Z; LogEvent(uchar,uchar,void *,void *,unsigned __int64,int,int)
0x1800a3ea4  test    rdi, rdi
0x1800a3ea7  jz      short loc_1800A3EE7
0x1800a3ea9  xor     edx, edx; SpinCount
0x1800a3eab  mov     rcx, rdi; CriticalSection
0x1800a3eae  call    cs:__imp_RtlInitializeCriticalSectionAndSpinCount
0x1800a3eb5  nop     dword ptr [rax+rax+00h]
0x1800a3eba  mov     cs:?LrpcEmergencyMessageMutex@@3PEAVMUTEX@@EA, rdi; MUTEX * LrpcEmergencyMessageMutex
0x1800a3ec1  cmp     cs:?LrpcEmergencyMessage@@3PEAXEA, r13; void * LrpcEmergencyMessage
0x1800a3ec8  jnz     short loc_1800A3EF5
0x1800a3eca  mov     edx, 1000h; unsigned __int64
0x1800a3ecf  call    ?Allocate@BCACHE@@QEAAPEAX_K@Z; BCACHE::Allocate(unsigned __int64)
0x1800a3ed4  mov     cs:?LrpcEmergencyMessage@@3PEAXEA, rax; void * LrpcEmergencyMessage
0x1800a3edb  test    rax, rax
0x1800a3ede  jnz     short loc_1800A3EF5
0x1800a3ee0  mov     edi, 0Eh
0x1800a3ee5  jmp     short loc_1800A3F02
0x1800a3ee7  mov     cs:?LrpcEmergencyMessageMutex@@3PEAVMUTEX@@EA, r13; MUTEX * LrpcEmergencyMessageMutex
0x1800a3eee  mov     edi, 0Eh
0x1800a3ef3  jmp     short loc_1800A3F02
0x1800a3ef5  mov     edi, r13d
0x1800a3ef8  mov     cs:?LrpcAsyncInitialized@@3HA, 1; int LrpcAsyncInitialized
0x1800a3f02  lea     rcx, ?GlobalMutex@@3PADA; CriticalSection
0x1800a3f09  call    cs:__imp_RtlLeaveCriticalSection
0x1800a3f10  nop     dword ptr [rax+rax+00h]
0x1800a3f15  mov     [rsp+150h+var_110], edi
0x1800a3f19  test    edi, edi
0x1800a3f1b  jz      loc_1800A3DA5
0x1800a3f21  mov     eax, edi
0x1800a3f23  jmp     loc_1800A4734
0x1800a3f28  lea     r14, [rdx+0A0h]
0x1800a3f2f  mov     rdx, [r14]
0x1800a3f32  cmp     rdx, r14
0x1800a3f35  jz      short loc_1800A3FA5
0x1800a3f37  nop     word ptr [rax+rax+00000000h]
0x1800a3f40  mov     rdi, [rdx]
0x1800a3f43  lea     rcx, [rdx-40h]
0x1800a3f47  mov     [rsp+150h+var_E0], rcx
0x1800a3f4c  lock or [rsp+150h+var_150], r13d
0x1800a3f51  mov     eax, [rcx+10h]
0x1800a3f54  cmp     eax, 1
0x1800a3f57  jnz     short loc_1800A3F94
0x1800a3f59  mov     r8, [rdx+8]
0x1800a3f5d  cmp     [r8], rdx
0x1800a3f60  jnz     loc_1800A4767
0x1800a3f66  mov     rax, [rdx]
0x1800a3f69  cmp     [rax+8], rdx
0x1800a3f6d  jnz     loc_1800A4767
0x1800a3f73  test    rax, rax
0x1800a3f76  jz      short loc_1800A3F7F
0x1800a3f78  mov     [r8], rax
0x1800a3f7b  mov     [rax+8], r8
0x1800a3f7f  mov     [rdx+8], r13
0x1800a3f83  mov     [rdx], r13
0x1800a3f86  mov     rax, [rcx]
0x1800a3f89  mov     rax, [rax+20h]
0x1800a3f8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3f92  jmp     short loc_1800A3F9D
0x1800a3f94  cmp     [rcx+88h], rsi
0x1800a3f9b  jz      short loc_1800A3FD5
0x1800a3f9d  mov     rdx, rdi
0x1800a3fa0  cmp     rdi, r14
0x1800a3fa3  jnz     short loc_1800A3F40
0x1800a3fa5  mov     rax, cs:?LsaAlloc@@3P6APEAX_K@ZEA; void * (*LsaAlloc)(unsigned __int64)
0x1800a3fac  test    rax, rax
0x1800a3faf  jnz     loc_1800A405F
0x1800a3fb5  mov     rcx, cs:?hRpcHeap@@3PEAXEA; hHeap
0x1800a3fbc  xor     edx, edx; dwFlags
0x1800a3fbe  mov     r8d, 90h; dwBytes
0x1800a3fc4  call    cs:__imp_HeapAlloc
0x1800a3fcb  nop     dword ptr [rax+rax+00h]
0x1800a3fd0  jmp     loc_1800A4069
0x1800a3fd5  mov     [rsp+150h+var_110], r13d
0x1800a3fda  mov     r12d, r13d
0x1800a3fdd  lea     rcx, [rsi+130h]; CriticalSection
0x1800a3fe4  call    cs:__imp_RtlEnterCriticalSection
0x1800a3feb  nop     dword ptr [rax+rax+00h]
0x1800a3ff0  cmp     dword ptr [rsi+18Ch], 9
0x1800a3ff7  jge     loc_1800A433C
0x1800a3ffd  test    rbx, rbx
0x1800a4000  jnz     loc_1800A42D6
0x1800a4006  mov     r9, [rsp+150h+var_E0]; struct LRPC_CAUSAL_FLOW *
0x1800a400b  lea     rax, [rsp+150h+var_F0]
0x1800a4010  mov     rdx, [rsp+150h+var_E8]; struct _RPC_MESSAGE *
0x1800a4015  mov     r8d, r12d; unsigned int
0x1800a4018  mov     rcx, rsi; this
0x1800a401b  mov     [rsp+150h+var_130], rax; struct LRPC_CCALL **
0x1800a4020  call    ?AllocateCall@LRPC_BINDING_HANDLE@@QEAAJPEAU_RPC_MESSAGE@@KPEAVLRPC_CAUSAL_FLOW@@PEAPEAVLRPC_CCALL@@@Z; LRPC_BINDING_HANDLE::AllocateCall(_RPC_MESSAGE *,ulong,LRPC_CAUSAL_FLOW *,LRPC_CCALL * *)
0x1800a4025  mov     [rsp+150h+var_110], eax
0x1800a4029  test    eax, eax
0x1800a402b  jnz     loc_1800A43F8
0x1800a4031  cmp     cs:dword_1800FE624, eax
0x1800a4037  mov     rbx, [rsp+150h+var_F0]
0x1800a403c  jz      loc_1800A42C8
0x1800a4042  lea     rdx, [rbx+0D0h]
0x1800a4049  mov     ecx, 1
0x1800a404e  call    cs:__imp_EtwEventActivityIdControl
0x1800a4055  nop     dword ptr [rax+rax+00h]
0x1800a405a  jmp     loc_1800A42D6
0x1800a405f  mov     ecx, 90h
0x1800a4064  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a4069  mov     r9, cs:?hRpcHeap@@3PEAXEA; void *
0x1800a4070  mov     r8, rax; void *
0x1800a4073  mov     dl, 43h ; 'C'; unsigned __int8
0x1800a4075  mov     [rsp+150h+var_E0], rax
0x1800a407a  mov     cl, 48h ; 'H'; unsigned __int8
0x1800a407c  mov     [rsp+150h+var_130], 90h; unsigned __int64
0x1800a4085  mov     rdi, rax
0x1800a4088  call    ?LogEvent@@YAXEEPEAX0_KHH@Z; LogEvent(uchar,uchar,void *,void *,unsigned __int64,int,int)
0x1800a408d  test    rdi, rdi
0x1800a4090  jz      loc_1800A4287
0x1800a4096  lea     rax, ??_7LRPC_CAUSAL_FLOW@@6B@; const LRPC_CAUSAL_FLOW::`vftable'
0x1800a409d  mov     dword ptr [rdi+8], 89ABCDEFh
0x1800a40a4  lea     r12, [rdi+18h]
0x1800a40a8  xor     edx, edx; SpinCount
0x1800a40aa  lea     rcx, [rdi+50h]; CriticalSection
0x1800a40ae  mov     [r12], r13
0x1800a40b2  mov     [rdi], rax
0x1800a40b5  mov     dword ptr [rdi+10h], 1
0x1800a40bc  mov     [rdi+38h], r13d
0x1800a40c0  mov     dword ptr [rdi+0Ch], 2
0x1800a40c7  mov     [rdi+28h], r13d
0x1800a40cb  mov     [rdi+20h], r13
0x1800a40cf  call    cs:__imp_RtlInitializeCriticalSectionAndSpinCount
0x1800a40d6  nop     dword ptr [rax+rax+00h]
0x1800a40db  lea     rax, [rdi+78h]
0x1800a40df  mov     [rdi+88h], rsi
0x1800a40e6  mov     [rax+8], rax
0x1800a40ea  mov     [rax], rax
0x1800a40ed  mov     dword ptr [rdi+10h], 2
0x1800a40f4  lock or [rsp+150h+var_150], r13d
0x1800a40f9  mov     [rdi+40h], r13
0x1800a40fd  lea     rax, [rdi+40h]
0x1800a4101  mov     [rdi+48h], r13
0x1800a4105  mov     rcx, [r14]
0x1800a4108  cmp     [rcx+8], r14
0x1800a410c  jnz     loc_1800A4280
0x1800a4112  mov     [rax], rcx
0x1800a4115  mov     [rax+8], r14
0x1800a4119  mov     [rcx+8], rax
0x1800a411d  lea     rcx, [rsi+130h]; CriticalSection
0x1800a4124  mov     [r14], rax
0x1800a4127  call    cs:__imp_RtlEnterCriticalSection
0x1800a412e  nop     dword ptr [rax+rax+00h]
0x1800a4133  mov     r15d, [rsi+18Ch]
0x1800a413a  lea     rax, [rsp+150h+var_D8]
0x1800a413f  lea     r14, [rsi+258h]
0x1800a4146  mov     [rbp+50h+var_D8.Blink], rax
0x1800a414a  mov     rdx, [r14]
0x1800a414d  lea     rax, [rsp+150h+var_D8]
0x1800a4152  mov     [rsp+150h+var_D8.Flink], rax
0x1800a4157  cmp     rdx, r14
0x1800a415a  jz      loc_1800A41FC
0x1800a4160  mov     rdi, [rdx]
0x1800a4163  lock or [rsp+150h+var_150], r13d
0x1800a4168  mov     eax, [rdx-8]
0x1800a416b  cmp     eax, 1
0x1800a416e  jnz     short loc_1800A41EB
0x1800a4170  mov     rcx, [rdx+8]
0x1800a4174  cmp     [rcx], rdx
0x1800a4177  jnz     loc_1800A475C
0x1800a417d  mov     rax, [rdx]
0x1800a4180  cmp     [rax+8], rdx
0x1800a4184  jnz     loc_1800A475C
0x1800a418a  test    rax, rax
0x1800a418d  jz      short loc_1800A4196
0x1800a418f  mov     [rcx], rax
0x1800a4192  mov     [rax+8], rcx
0x1800a4196  xor     eax, eax
0x1800a4198  mov     [rdx+8], rax
0x1800a419c  mov     [rdx], rax
0x1800a419f  cmp     r15d, 5
0x1800a41a3  jl      short loc_1800A41D4
0x1800a41a5  mov     [rdx+70h], rax
0x1800a41a9  lea     rcx, [rsp+150h+var_D8]
0x1800a41ae  mov     rax, [rsp+150h+var_D8.Flink]
0x1800a41b3  cmp     [rax+8], rcx
0x1800a41b7  jnz     loc_1800A4280
0x1800a41bd  mov     [rdx], rax
  ... truncated ...
```
