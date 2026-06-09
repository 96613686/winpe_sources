# LRPC_BINDING_HANDLE::NegotiateTransferSyntax(_RPC_MESSAGE *)

- ea: `0x1800a05d0`
- end: `0x1800a105b`
- name: `?NegotiateTransferSyntax@LRPC_BINDING_HANDLE@@UEAAJPEAU_RPC_MESSAGE@@@Z`
- size: `2699`
- prototype: `__int64 __fastcall(LRPC_BINDING_HANDLE *__hidden this, struct _RPC_MESSAGE *)`
- caller_count: `0`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180019ae4`
- `0x1800206a0`
- `0x180021ce0`
- `0x180021e18`
- `0x180025a80`
- `0x180025c00`
- `0x1800283bc`
- `0x180028d70`
- `0x180029cc4`
- `0x180029d80`
- `0x18002a758`
- `0x180031760`
- `0x18006f850`
- `0x18007c3f4`
- `0x1800a05d0`
- `0x1800ca140`
- `0x1800d2010`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x1800a0962`
- `ntdll!EtwEventActivityIdControl` at `0x1800a0d4f`
- `ntdll!EtwEventActivityIdControl` at `0x1800a0962`
- `ntdll!EtwEventActivityIdControl` at `0x1800a0d4f`
- `ntdll!RtlInitializeCriticalSectionAndSpinCount` at `0x1800a07e0`
- `ntdll!RtlInitializeCriticalSectionAndSpinCount` at `0x1800a09dd`
- `ntdll!RtlInitializeCriticalSectionAndSpinCount` at `0x1800a07e0`
- `ntdll!RtlInitializeCriticalSectionAndSpinCount` at `0x1800a09dd`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a0680`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a06d8`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a0776`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a0835`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a0b75`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a0be7`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a0d9c`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a0fcd`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a0680`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a06d8`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a0776`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a0835`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a0b75`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a0be7`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a0d9c`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a0fcd`
- `ntdll!RtlEnterCriticalSection` at `0x1800a062f`
- `ntdll!RtlEnterCriticalSection` at `0x1800a06be`
- `ntdll!RtlEnterCriticalSection` at `0x1800a08fe`
- `ntdll!RtlEnterCriticalSection` at `0x1800a0a2f`
- `ntdll!RtlEnterCriticalSection` at `0x1800a062f`
- `ntdll!RtlEnterCriticalSection` at `0x1800a06be`
- `ntdll!RtlEnterCriticalSection` at `0x1800a08fe`
- `ntdll!RtlEnterCriticalSection` at `0x1800a0a2f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a07a5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a08e4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a07a5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a08e4`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x1800a0ca5`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x1800a0ca5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a063a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a063a`

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
              JUMPOUT(0x1800A105ALL);
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
        if ( dword_1800F9624 )
        {
          EtwEventActivityIdControl(1, (char *)Alignment + 208);
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
        if ( dword_1800F9624 )
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
        if ( dword_1800F9624 )
          EtwEventActivityIdControl(1, (char *)v63 + 208);
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
0x1800a05d0  mov     [rsp-8+arg_10], rbx
0x1800a05d5  push    rbp
0x1800a05d6  push    rsi
0x1800a05d7  push    rdi
0x1800a05d8  push    r12
0x1800a05da  push    r13
0x1800a05dc  push    r14
0x1800a05de  push    r15
0x1800a05e0  lea     rbp, [rsp-20h]
0x1800a05e5  sub     rsp, 120h
0x1800a05ec  mov     rax, cs:__security_cookie
0x1800a05f3  xor     rax, rsp
0x1800a05f6  mov     [rbp+50h+var_40], rax
0x1800a05fa  xor     r13d, r13d
0x1800a05fd  mov     [rsp+150h+var_E8], rdx
0x1800a0602  mov     ebx, r13d
0x1800a0605  mov     r14, rdx
0x1800a0608  mov     rsi, rcx
0x1800a060b  mov     [rsp+150h+var_F0], rbx
0x1800a0610  mov     [rsp+150h+var_110], r13d
0x1800a0615  mov     [rsp+150h+var_E0], r13
0x1800a061a  mov     [rsp+150h+var_F8], r13d
0x1800a061f  cmp     [rcx+270h], r13
0x1800a0626  jz      short loc_1800A068E
0x1800a0628  add     rcx, 130h; CriticalSection
0x1800a062f  call    cs:__imp_RtlEnterCriticalSection
0x1800a0635  mov     [rsp+150h+var_110], r13d
0x1800a063a  call    cs:__imp_GetCurrentThreadId
0x1800a0640  mov     r10, [rsi+270h]
0x1800a0647  mov     ecx, r13d
0x1800a064a  mov     r11d, eax
0x1800a064d  mov     r8d, [r10+8]
0x1800a0651  cmp     ecx, r8d
0x1800a0654  jnb     short loc_1800A0679
0x1800a0656  mov     r9, [r10]
0x1800a0659  nop     dword ptr [rax+00000000h]
0x1800a0660  mov     eax, ecx
0x1800a0662  lea     edx, [rcx+1]
0x1800a0665  mov     rbx, [r9+rax*8]
0x1800a0669  test    rbx, rbx
0x1800a066c  jnz     loc_1800A0748
0x1800a0672  mov     ecx, edx
0x1800a0674  cmp     edx, r8d
0x1800a0677  jb      short loc_1800A0660
0x1800a0679  lea     rcx, [rsi+130h]; CriticalSection
0x1800a0680  call    cs:__imp_RtlLeaveCriticalSection
0x1800a0686  mov     rbx, r13
0x1800a0689  mov     [rsp+150h+var_F0], rbx
0x1800a068e  mov     r15d, [r14+48h]
0x1800a0692  and     r15d, 8000h
0x1800a0699  mov     [rsp+150h+var_10C], r15d
0x1800a069e  jz      loc_1800A0B9B
0x1800a06a4  mov     eax, [rsi+1F0h]
0x1800a06aa  test    al, 1
0x1800a06ac  jnz     short loc_1800A06E3
0x1800a06ae  cmp     cs:?LrpcAsyncInitialized@@3HA, r13d; int LrpcAsyncInitialized
0x1800a06b5  jnz     short loc_1800A06DE
0x1800a06b7  lea     rcx, ?GlobalMutex@@3PADA; CriticalSection
0x1800a06be  call    cs:__imp_RtlEnterCriticalSection
0x1800a06c4  cmp     cs:?LrpcAsyncInitialized@@3HA, r13d; int LrpcAsyncInitialized
0x1800a06cb  jz      loc_1800A0781
0x1800a06d1  lea     rcx, ?GlobalMutex@@3PADA; CriticalSection
0x1800a06d8  call    cs:__imp_RtlLeaveCriticalSection
0x1800a06de  mov     [rsp+150h+var_110], r13d
0x1800a06e3  test    dword ptr [r14+48h], 2000h
0x1800a06eb  jnz     loc_1800A08F4
0x1800a06f1  mov     rax, [rsi+40h]
0x1800a06f5  test    rax, rax
0x1800a06f8  jz      short loc_1800A0704
0x1800a06fa  cmp     [rax+48h], r13
0x1800a06fe  jnz     loc_1800A08F4
0x1800a0704  mov     rax, gs:30h
0x1800a070d  mov     rdx, [rax+1698h]
0x1800a0714  test    rdx, rdx
0x1800a0717  jz      loc_1800A084E
0x1800a071d  mov     rax, 0ABABABABDEDEDEDEh
0x1800a0727  xor     rdx, rax
0x1800a072a  mov     rax, gs:30h
0x1800a0733  mov     rcx, [rax+48h]
0x1800a0737  cmp     [rdx+10h], rcx
0x1800a073b  jz      loc_1800A084E
0x1800a0741  mov     ecx, 1Eh
0x1800a0746  int     29h; Win8: RtlFailFast(ecx)
0x1800a0748  mov     rax, [rbx+250h]
0x1800a074f  mov     [rsp+150h+var_F0], rbx
0x1800a0754  cmp     [rax+0C8h], r11d
0x1800a075b  jz      short loc_1800A0764
0x1800a075d  mov     ecx, edx
0x1800a075f  jmp     loc_1800A0651
0x1800a0764  xor     r15d, r15d
0x1800a0767  mov     [rsp+150h+var_10C], r13d
0x1800a076c  lea     rcx, [rsi+130h]; CriticalSection
0x1800a0773  mov     r12d, r13d
0x1800a0776  call    cs:__imp_RtlLeaveCriticalSection
0x1800a077c  jmp     loc_1800A0EC3
0x1800a0781  cmp     cs:?LrpcEmergencyMessageMutex@@3PEAVMUTEX@@EA, r13; MUTEX * LrpcEmergencyMessageMutex
0x1800a0788  jnz     short loc_1800A07ED
0x1800a078a  mov     rax, cs:?LsaAlloc@@3P6APEAX_K@ZEA; void * (*LsaAlloc)(unsigned __int64)
0x1800a0791  test    rax, rax
0x1800a0794  jnz     short loc_1800A07AD
0x1800a0796  mov     rcx, cs:?hRpcHeap@@3PEAXEA; hHeap
0x1800a079d  xor     edx, edx; dwFlags
0x1800a079f  mov     r8d, 28h ; '('; dwBytes
0x1800a07a5  call    cs:__imp_HeapAlloc
0x1800a07ab  jmp     short loc_1800A07B7
0x1800a07ad  mov     ecx, 28h ; '('
0x1800a07b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a07b7  mov     r9, cs:?hRpcHeap@@3PEAXEA; void *
0x1800a07be  mov     r8, rax; void *
0x1800a07c1  mov     dl, 43h ; 'C'; unsigned __int8
0x1800a07c3  mov     [rsp+150h+var_130], 28h ; '('; unsigned __int64
0x1800a07cc  mov     cl, 48h ; 'H'; unsigned __int8
0x1800a07ce  mov     rdi, rax
0x1800a07d1  call    ?LogEvent@@YAXEEPEAX0_KHH@Z; LogEvent(uchar,uchar,void *,void *,unsigned __int64,int,int)
0x1800a07d6  test    rdi, rdi
0x1800a07d9  jz      short loc_1800A0813
0x1800a07db  xor     edx, edx; SpinCount
0x1800a07dd  mov     rcx, rdi; CriticalSection
0x1800a07e0  call    cs:__imp_RtlInitializeCriticalSectionAndSpinCount
0x1800a07e6  mov     cs:?LrpcEmergencyMessageMutex@@3PEAVMUTEX@@EA, rdi; MUTEX * LrpcEmergencyMessageMutex
0x1800a07ed  cmp     cs:?LrpcEmergencyMessage@@3PEAXEA, r13; void * LrpcEmergencyMessage
0x1800a07f4  jnz     short loc_1800A0821
0x1800a07f6  mov     edx, 1000h; unsigned __int64
0x1800a07fb  call    ?Allocate@BCACHE@@QEAAPEAX_K@Z; BCACHE::Allocate(unsigned __int64)
0x1800a0800  mov     cs:?LrpcEmergencyMessage@@3PEAXEA, rax; void * LrpcEmergencyMessage
0x1800a0807  test    rax, rax
0x1800a080a  jnz     short loc_1800A0821
0x1800a080c  mov     edi, 0Eh
0x1800a0811  jmp     short loc_1800A082E
0x1800a0813  mov     cs:?LrpcEmergencyMessageMutex@@3PEAVMUTEX@@EA, r13; MUTEX * LrpcEmergencyMessageMutex
0x1800a081a  mov     edi, 0Eh
0x1800a081f  jmp     short loc_1800A082E
0x1800a0821  mov     edi, r13d
0x1800a0824  mov     cs:?LrpcAsyncInitialized@@3HA, 1; int LrpcAsyncInitialized
0x1800a082e  lea     rcx, ?GlobalMutex@@3PADA; CriticalSection
0x1800a0835  call    cs:__imp_RtlLeaveCriticalSection
0x1800a083b  mov     [rsp+150h+var_110], edi
0x1800a083f  test    edi, edi
0x1800a0841  jz      loc_1800A06E3
0x1800a0847  mov     eax, edi
0x1800a0849  jmp     loc_1800A101E
0x1800a084e  lea     r14, [rdx+0A0h]
0x1800a0855  mov     rdx, [r14]
0x1800a0858  cmp     rdx, r14
0x1800a085b  jz      short loc_1800A08C5
0x1800a085d  nop     dword ptr [rax]
0x1800a0860  mov     rdi, [rdx]
0x1800a0863  lea     rcx, [rdx-40h]
0x1800a0867  mov     [rsp+150h+var_E0], rcx
0x1800a086c  lock or [rsp+150h+var_150], r13d
0x1800a0871  mov     eax, [rcx+10h]
0x1800a0874  cmp     eax, 1
0x1800a0877  jnz     short loc_1800A08B4
0x1800a0879  mov     r8, [rdx+8]
0x1800a087d  cmp     [r8], rdx
0x1800a0880  jnz     loc_1800A1050
0x1800a0886  mov     rax, [rdx]
0x1800a0889  cmp     [rax+8], rdx
0x1800a088d  jnz     loc_1800A1050
0x1800a0893  test    rax, rax
0x1800a0896  jz      short loc_1800A089F
0x1800a0898  mov     [r8], rax
0x1800a089b  mov     [rax+8], r8
0x1800a089f  mov     [rdx+8], r13
0x1800a08a3  mov     [rdx], r13
0x1800a08a6  mov     rax, [rcx]
0x1800a08a9  mov     rax, [rax+20h]
0x1800a08ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a08b2  jmp     short loc_1800A08BD
0x1800a08b4  cmp     [rcx+88h], rsi
0x1800a08bb  jz      short loc_1800A08EF
0x1800a08bd  mov     rdx, rdi
0x1800a08c0  cmp     rdi, r14
0x1800a08c3  jnz     short loc_1800A0860
0x1800a08c5  mov     rax, cs:?LsaAlloc@@3P6APEAX_K@ZEA; void * (*LsaAlloc)(unsigned __int64)
0x1800a08cc  test    rax, rax
0x1800a08cf  jnz     loc_1800A096D
0x1800a08d5  mov     rcx, cs:?hRpcHeap@@3PEAXEA; hHeap
0x1800a08dc  xor     edx, edx; dwFlags
0x1800a08de  mov     r8d, 90h; dwBytes
0x1800a08e4  call    cs:__imp_HeapAlloc
0x1800a08ea  jmp     loc_1800A0977
0x1800a08ef  mov     [rsp+150h+var_110], r13d
0x1800a08f4  mov     r12d, r13d
0x1800a08f7  lea     rcx, [rsi+130h]; CriticalSection
0x1800a08fe  call    cs:__imp_RtlEnterCriticalSection
0x1800a0904  cmp     dword ptr [rsi+18Ch], 9
0x1800a090b  jge     loc_1800A0C40
0x1800a0911  test    rbx, rbx
0x1800a0914  jnz     loc_1800A0BE0
0x1800a091a  mov     r9, [rsp+150h+var_E0]; struct LRPC_CAUSAL_FLOW *
0x1800a091f  lea     rax, [rsp+150h+var_F0]
0x1800a0924  mov     rdx, [rsp+150h+var_E8]; struct _RPC_MESSAGE *
0x1800a0929  mov     r8d, r12d; unsigned int
0x1800a092c  mov     rcx, rsi; this
0x1800a092f  mov     [rsp+150h+var_130], rax; struct LRPC_CCALL **
0x1800a0934  call    ?AllocateCall@LRPC_BINDING_HANDLE@@QEAAJPEAU_RPC_MESSAGE@@KPEAVLRPC_CAUSAL_FLOW@@PEAPEAVLRPC_CCALL@@@Z; LRPC_BINDING_HANDLE::AllocateCall(_RPC_MESSAGE *,ulong,LRPC_CAUSAL_FLOW *,LRPC_CCALL * *)
0x1800a0939  mov     [rsp+150h+var_110], eax
0x1800a093d  test    eax, eax
0x1800a093f  jnz     loc_1800A0CF6
0x1800a0945  cmp     cs:dword_1800F9624, eax
0x1800a094b  mov     rbx, [rsp+150h+var_F0]
0x1800a0950  jz      loc_1800A0BD2
0x1800a0956  lea     rdx, [rbx+0D0h]
0x1800a095d  mov     ecx, 1
0x1800a0962  call    cs:__imp_EtwEventActivityIdControl
0x1800a0968  jmp     loc_1800A0BE0
0x1800a096d  mov     ecx, 90h
0x1800a0972  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0977  mov     r9, cs:?hRpcHeap@@3PEAXEA; void *
0x1800a097e  mov     r8, rax; void *
0x1800a0981  mov     dl, 43h ; 'C'; unsigned __int8
0x1800a0983  mov     [rsp+150h+var_E0], rax
0x1800a0988  mov     cl, 48h ; 'H'; unsigned __int8
0x1800a098a  mov     [rsp+150h+var_130], 90h; unsigned __int64
0x1800a0993  mov     rdi, rax
0x1800a0996  call    ?LogEvent@@YAXEEPEAX0_KHH@Z; LogEvent(uchar,uchar,void *,void *,unsigned __int64,int,int)
0x1800a099b  test    rdi, rdi
0x1800a099e  jz      loc_1800A0B91
0x1800a09a4  lea     rax, ??_7LRPC_CAUSAL_FLOW@@6B@; const LRPC_CAUSAL_FLOW::`vftable'
0x1800a09ab  mov     dword ptr [rdi+8], 89ABCDEFh
0x1800a09b2  lea     r12, [rdi+18h]
0x1800a09b6  xor     edx, edx; SpinCount
0x1800a09b8  lea     rcx, [rdi+50h]; CriticalSection
0x1800a09bc  mov     [r12], r13
0x1800a09c0  mov     [rdi], rax
0x1800a09c3  mov     dword ptr [rdi+10h], 1
0x1800a09ca  mov     [rdi+38h], r13d
0x1800a09ce  mov     dword ptr [rdi+0Ch], 2
0x1800a09d5  mov     [rdi+28h], r13d
0x1800a09d9  mov     [rdi+20h], r13
0x1800a09dd  call    cs:__imp_RtlInitializeCriticalSectionAndSpinCount
0x1800a09e3  lea     rax, [rdi+78h]
0x1800a09e7  mov     [rdi+88h], rsi
0x1800a09ee  mov     [rax+8], rax
0x1800a09f2  mov     [rax], rax
0x1800a09f5  mov     dword ptr [rdi+10h], 2
0x1800a09fc  lock or [rsp+150h+var_150], r13d
0x1800a0a01  mov     [rdi+40h], r13
0x1800a0a05  lea     rax, [rdi+40h]
0x1800a0a09  mov     [rdi+48h], r13
0x1800a0a0d  mov     rcx, [r14]
0x1800a0a10  cmp     [rcx+8], r14
0x1800a0a14  jnz     loc_1800A0B8A
0x1800a0a1a  mov     [rax], rcx
0x1800a0a1d  mov     [rax+8], r14
0x1800a0a21  mov     [rcx+8], rax
0x1800a0a25  lea     rcx, [rsi+130h]; CriticalSection
0x1800a0a2c  mov     [r14], rax
0x1800a0a2f  call    cs:__imp_RtlEnterCriticalSection
0x1800a0a35  mov     r15d, [rsi+18Ch]
0x1800a0a3c  lea     rax, [rsp+150h+var_D8]
0x1800a0a41  lea     r14, [rsi+258h]
0x1800a0a48  mov     [rbp+50h+var_D8.Blink], rax
0x1800a0a4c  mov     rdx, [r14]
0x1800a0a4f  lea     rax, [rsp+150h+var_D8]
0x1800a0a54  mov     [rsp+150h+var_D8.Flink], rax
0x1800a0a59  cmp     rdx, r14
0x1800a0a5c  jz      loc_1800A0B0C
0x1800a0a62  nop     dword ptr [rax+00h]
0x1800a0a66  nop     word ptr [rax+rax+00000000h]
0x1800a0a70  mov     rdi, [rdx]
0x1800a0a73  lock or [rsp+150h+var_150], r13d
0x1800a0a78  mov     eax, [rdx-8]
0x1800a0a7b  cmp     eax, 1
0x1800a0a7e  jnz     short loc_1800A0AFB
0x1800a0a80  mov     rcx, [rdx+8]
0x1800a0a84  cmp     [rcx], rdx
0x1800a0a87  jnz     loc_1800A1045
0x1800a0a8d  mov     rax, [rdx]
0x1800a0a90  cmp     [rax+8], rdx
0x1800a0a94  jnz     loc_1800A1045
0x1800a0a9a  test    rax, rax
0x1800a0a9d  jz      short loc_1800A0AA6
0x1800a0a9f  mov     [rcx], rax
0x1800a0aa2  mov     [rax+8], rcx
0x1800a0aa6  xor     eax, eax
0x1800a0aa8  mov     [rdx+8], rax
0x1800a0aac  mov     [rdx], rax
0x1800a0aaf  cmp     r15d, 5
0x1800a0ab3  jl      short loc_1800A0AE4
0x1800a0ab5  mov     [rdx+70h], rax
0x1800a0ab9  lea     rcx, [rsp+150h+var_D8]
0x1800a0abe  mov     rax, [rsp+150h+var_D8.Flink]
0x1800a0ac3  cmp     [rax+8], rcx
0x1800a0ac7  jnz     loc_1800A0B8A
0x1800a0acd  mov     [rdx], rax
0x1800a0ad0  lea     rcx, [rsp+150h+var_D8]
0x1800a0ad5  mov     [rdx+8], rcx
0x1800a0ad9  mov     [rax+8], rdx
0x1800a0add  mov     [rsp+150h+var_D8.Flink], rdx
0x1800a0ae2  jmp     short loc_1800A0AF5
0x1800a0ae4  mov     rax, [rdx-18h]
0x1800a0ae8  lea     rcx, [rdx-18h]
0x1800a0aec  mov     rax, [rax+20h]
0x1800a0af0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0af5  dec     dword ptr [rsi+250h]
0x1800a0afb  mov     rdx, rdi
0x1800a0afe  cmp     rdi, r14
0x1800a0b01  jnz     loc_1800A0A70
  ... truncated ...
```
