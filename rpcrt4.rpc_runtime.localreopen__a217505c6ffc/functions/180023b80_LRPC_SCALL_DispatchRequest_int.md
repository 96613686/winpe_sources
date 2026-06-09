# LRPC_SCALL::DispatchRequest(int *)

- ea: `0x180023b80`
- end: `0x180024e7f`
- name: `?DispatchRequest@LRPC_SCALL@@QEAAJPEAH@Z`
- size: `4863`
- prototype: `__int64 __fastcall(LRPC_SCALL *__hidden this, int *)`
- caller_count: `2`
- callee_count: `26`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001d170`
- `0x18007a30c`

## callees

- `0x1800162e0`
- `0x180018068`
- `0x18001c6e0`
- `0x18001e7d0`
- `0x180022fb8`
- `0x180023b80`
- `0x180025d70`
- `0x1800263a0`
- `0x180029064`
- `0x180029194`
- `0x1800292c0`
- `0x1800295d8`
- `0x180029b9c`
- `0x180029c38`
- `0x1800778f0`
- `0x1800784f0`
- `0x18007e1dc`
- `0x1800940e4`
- `0x180094650`
- `0x180099594`
- `0x18009a2ac`
- `0x1800a8264`
- `0x1800abfc8`
- `0x1800cec85`
- `0x1800ceda0`
- `0x1800d7010`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x18002485e`
- `ntdll!EtwEventActivityIdControl` at `0x18002485e`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180024bb7`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180024bb7`
- `ntdll!NtSetInformationThread` at `0x180023f9a`
- `ntdll!NtSetInformationThread` at `0x180023f9a`
- `ntdll!RtlReleaseSRWLockShared` at `0x180024139`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800249c9`
- `ntdll!RtlReleaseSRWLockShared` at `0x180024139`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800249c9`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800240ff`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800240ff`
- `ntdll!AlpcFreeCompletionListMessage` at `0x18002465a`
- `ntdll!AlpcFreeCompletionListMessage` at `0x18002465a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180023c5d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002482d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180023c5d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002482d`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x180024874`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x1800248d0`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x180024a75`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x180024a89`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x180024a9a`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x180024b04`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x180024874`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x1800248d0`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x180024a75`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x180024a89`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x180024a9a`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x180024b04`

## pseudocode

```c
__int64 __fastcall LRPC_SCALL::DispatchRequest(LRPC_SCALL *this, int *a2)
{
  unsigned __int64 ReservedForNtRpc; // r14
  __int64 v4; // r9
  bool v5; // zf
  __int64 v6; // r8
  __int64 v7; // rbx
  unsigned int v8; // eax
  int v9; // edi
  unsigned int v10; // esi
  unsigned __int16 v11; // ax
  const struct _EVENT_DESCRIPTOR *v12; // rdx
  unsigned __int64 v13; // rcx
  __int64 v14; // r12
  struct _RPC_MESSAGE *v15; // rsi
  __int64 v16; // rcx
  int *v17; // rax
  __int64 v18; // rbx
  __int64 v19; // rdi
  unsigned int v20; // esi
  _DWORD *v21; // rdx
  __int64 v22; // rbx
  int v23; // r12d
  int v24; // r8d
  unsigned __int32 v25; // esi
  signed __int32 v26; // edi
  unsigned int i; // ecx
  unsigned int j; // ecx
  unsigned int v29; // eax
  int v30; // r8d
  unsigned int k; // ecx
  unsigned __int64 v32; // rdx
  unsigned __int32 v33; // edi
  signed __int32 v34; // edx
  int v35; // eax
  __int64 v36; // rdx
  unsigned int m; // ecx
  struct THREAD *v38; // rax
  int v39; // r8d
  int v40; // r9d
  unsigned __int64 v41; // rbx
  __int64 v42; // rdi
  BCACHE *v43; // rcx
  unsigned int kk; // edx
  PRTL_AVL_TABLE v46; // rsi
  int RightChild; // ecx
  struct _RTL_BALANCED_LINKS *n; // r12
  int v49; // r8d
  unsigned __int32 v50; // esi
  signed __int32 v51; // ebx
  unsigned int ii; // ecx
  int v53; // r9d
  int v54; // r8d
  unsigned __int64 v55; // rdx
  unsigned __int32 v56; // ebx
  signed __int32 v57; // r13d
  unsigned int jj; // ecx
  __int64 v59; // rax
  __int64 v60; // rcx
  __int64 *v61; // rax
  const wchar_t *v62; // rdx
  __int64 v63; // rcx
  __int64 v64; // rax
  unsigned int v65; // eax
  __int64 v66; // rbx
  unsigned int CorrelationId; // eax
  int v68; // edi
  unsigned int v69; // esi
  unsigned __int16 CurrentProcessId; // ax
  __int64 v71; // r11
  signed __int64 v72; // rbx
  unsigned __int64 v73; // r10
  unsigned int v74; // edx
  unsigned int v75; // ebx
  struct RPC_INTERFACE_MANAGER *InterfaceManager; // rax
  struct RPC_INTERFACE_MANAGER *v77; // rsi
  unsigned int v78; // eax
  WAITABLE_INTERLOCKED_INTEGER *v79; // rcx
  struct THREAD *ThreadPointer; // rax
  int v81; // ecx
  char *v82; // rax
  int v83; // r12d
  __int64 v84; // rax
  __int64 v85; // rdx
  unsigned __int64 v86; // rdx
  __int64 v87; // rcx
  __int64 v88; // rcx
  int v89; // r12d
  signed __int32 v90[8]; // [rsp+0h] [rbp-100h] BYREF
  struct tagParam *v91; // [rsp+20h] [rbp-E0h]
  const struct _GUID *v92; // [rsp+28h] [rbp-D8h]
  __int64 v93; // [rsp+30h] [rbp-D0h]
  char v94; // [rsp+40h] [rbp-C0h] BYREF
  char v95; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v96; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v97; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v98; // [rsp+60h] [rbp-A0h] BYREF
  int v99; // [rsp+68h] [rbp-98h] BYREF
  __int64 ThreadInformation; // [rsp+70h] [rbp-90h] BYREF
  int v101; // [rsp+78h] [rbp-88h] BYREF
  int v102; // [rsp+7Ch] [rbp-84h]
  int v103; // [rsp+80h] [rbp-80h] BYREF
  int v104; // [rsp+88h] [rbp-78h] BYREF
  int *v105; // [rsp+90h] [rbp-70h]
  struct _GUID v106; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v107[16]; // [rsp+B0h] [rbp-50h] BYREF
  char *v108; // [rsp+C0h] [rbp-40h]
  __int64 v109; // [rsp+C8h] [rbp-38h]
  char *v110; // [rsp+D0h] [rbp-30h]
  __int64 v111; // [rsp+D8h] [rbp-28h]
  int *v112; // [rsp+E0h] [rbp-20h]
  __int64 v113; // [rsp+E8h] [rbp-18h]
  const wchar_t *v114; // [rsp+F0h] [rbp-10h]
  __int64 v115; // [rsp+F8h] [rbp-8h]
  const wchar_t *v116; // [rsp+100h] [rbp+0h]
  __int64 v117; // [rsp+108h] [rbp+8h]
  const wchar_t *v118; // [rsp+110h] [rbp+10h]
  __int64 v119; // [rsp+118h] [rbp+18h]
  __int64 *v120; // [rsp+120h] [rbp+20h]
  __int64 v121; // [rsp+128h] [rbp+28h]
  __int64 *v122; // [rsp+130h] [rbp+30h]
  __int64 v123; // [rsp+138h] [rbp+38h]
  __int64 *v124; // [rsp+140h] [rbp+40h]
  __int64 v125; // [rsp+148h] [rbp+48h]
  __int128 v126; // [rsp+150h] [rbp+50h] BYREF
  __int64 *v127; // [rsp+160h] [rbp+60h]
  __int64 v128; // [rsp+168h] [rbp+68h]

  v105 = a2;
  v99 = 0;
  v106 = 0;
  ReservedForNtRpc = (unsigned __int64)NtCurrentTeb()->ReservedForNtRpc;
  if ( ReservedForNtRpc )
  {
    ReservedForNtRpc ^= 0xABABABABDEDEDEDEuLL;
    if ( *(HANDLE *)(ReservedForNtRpc + 16) != NtCurrentTeb()->ClientId.UniqueThread )
      goto LABEL_16;
  }
  v4 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 38) + 56LL) + 152LL);
  v5 = (*(_BYTE *)(ReservedForNtRpc + 48))++ == 0xFF;
  if ( v5 )
  {
    v71 = *(_QWORD *)(*((_QWORD *)this + 38) + 56LL);
    _InterlockedIncrement((volatile signed __int32 *)(v71 + 328));
    do
    {
      v73 = (MEMORY[0x7FFE0320] * (unsigned __int64)MEMORY[0x7FFE0004]) >> 24;
      v74 = v73 - HIDWORD(*(_QWORD *)(v71 + 328));
      if ( v74 <= 0x7D0 )
        break;
      v72 = *(_QWORD *)(v71 + 328);
    }
    while ( v72 != _InterlockedCompareExchange64(
                     (volatile signed __int64 *)(v71 + 328),
                     ((unsigned __int64)(unsigned int)(v73 - 1000) << 32)
                   | (unsigned int)(1000 * (unsigned __int64)(unsigned int)v72 / v74),
                     v72) );
    if ( !v4
      && !*(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 38) + 56LL) + 292LL)
      && LRPC_ADDRESS::GetCallBatchesPerUnitOfTime(*(LRPC_ADDRESS **)(*((_QWORD *)this + 38) + 56LL)) > 8 )
    {
      LRPC_ADDRESS::CompletionListNeedsActivating(*(LRPC_ADDRESS **)(*((_QWORD *)this + 38) + 56LL));
    }
  }
  *(_QWORD *)(ReservedForNtRpc + 32) = this;
  *(_DWORD *)ReservedForNtRpc = 0;
  if ( !memcmp_0((char *)this + 208, &g_NullActivityId, 0x10u) )
  {
    if ( Microsoft_Windows_Networking_CorrelationEnabled )
    {
      v66 = **((_QWORD **)this + 39);
      CorrelationId = LRPC_SASSOCIATION::QueryCorrelationId(*((LRPC_SASSOCIATION **)this + 38));
      v68 = *((_DWORD *)this + 133);
      v69 = CorrelationId;
      CurrentProcessId = GetCurrentProcessId();
      v106.Data1 = *(_DWORD *)(v66 + 84);
      v106.Data3 = *((_WORD *)this + 248);
      v106.Data2 = CurrentProcessId;
      *(_DWORD *)v106.Data4 = v68;
      *(_DWORD *)&v106.Data4[4] = v69;
      EtwEventActivityIdControl(2);
    }
  }
  else
  {
    v7 = **((_QWORD **)this + 39);
    v8 = LRPC_SASSOCIATION::QueryCorrelationId(*((LRPC_SASSOCIATION **)this + 38));
    v9 = *((_DWORD *)this + 133);
    v10 = v8;
    v11 = GetCurrentProcessId();
    v106.Data1 = *(_DWORD *)(v7 + 84);
    v13 = *((unsigned __int16 *)this + 248);
    v106.Data2 = v11;
    v106.Data3 = v13;
    *(_DWORD *)v106.Data4 = v9;
    *(_DWORD *)&v106.Data4[4] = v10;
    if ( Microsoft_Windows_Networking_CorrelationEnabled )
      EtwEx_tidActivityInfoTransfer(v13, v12, (const struct _GUID *)this + 13, &v106, (unsigned __int8)v91, v92, v93);
  }
  v14 = *(_QWORD *)(ReservedForNtRpc + 64);
  ThreadInformation = v14;
  if ( v14 )
  {
    v84 = MEMORY[0x7FFE0320];
    v85 = MEMORY[0x7FFE0004];
    *(_WORD *)(v14 + 2) = 1;
    v86 = (unsigned __int64)(v84 * v85) >> 24;
    *(_DWORD *)(v14 + 4) = v86;
    v6 = *((_QWORD *)this + 40);
    *(_DWORD *)(v6 + 4) = *(_DWORD *)(**((_QWORD **)this + 39) + 84LL);
    *(_DWORD *)(v6 + 16) = *((_DWORD *)this + 133);
    *(_DWORD *)(v6 + 20) = v86;
    *(_WORD *)(v6 + 24) = *((_WORD *)this + 248);
    *(_WORD *)(v6 + 26) = *((_WORD *)this + 252);
    *(_WORD *)(v6 + 2) = *((_WORD *)this + 182);
    *(_BYTE *)(v6 + 1) = 2;
    *(_WORD *)(v6 + 8) = *(_WORD *)(ReservedForNtRpc + 56);
    v87 = *(unsigned int *)(ReservedForNtRpc + 56);
    v88 = (unsigned int)v87 < *((_DWORD *)g_pCellHeap + 10) ? *(_QWORD *)(*((_QWORD *)g_pCellHeap + 4) + 8 * v87) : 0LL;
    *(_WORD *)(v6 + 10) = (v14 - v88) >> 5;
    if ( (*(_DWORD *)(**((_QWORD **)this + 39) + 56LL) & 2) != 0 )
      *(_DWORD *)(v6 + 12) |= 4u;
  }
  if ( g_SqmEnabled )
  {
    v75 = *(__int16 *)(*((_QWORD *)this + 55) + 4LL) & 0xFFFF8000;
    if ( (*(_DWORD *)(**((_QWORD **)this + 39) + 8LL) & 2) == 0 )
      UpdateDataPoint(&RawRpcCallsReceived, 0x49Cu);
    if ( v75 )
      UpdateDataPoint(&KLRPCCallsReceived, 0x49Au);
  }
  if ( (Microsoft_Windows_RPCEnableBits & 2) != 0 )
  {
    v59 = *((_QWORD *)this + 38);
    LODWORD(v96) = 0;
    LODWORD(v98) = 20;
    LODWORD(v97) = 6;
    v60 = *(_QWORD *)(v59 + 56);
    v103 = *((_DWORD *)this + 91);
    v61 = (__int64 *)*((_QWORD *)this + 39);
    v62 = *(const wchar_t **)(v60 + 32);
    v104 = 3;
    v109 = 16;
    v63 = *v61;
    v110 = (char *)&v103;
    v108 = (char *)(v63 + 84);
    v114 = L"NULL";
    v111 = 4;
    v112 = &v104;
    v113 = 4;
    v115 = 10;
    if ( v62 )
    {
      v64 = -1;
      do
        v5 = v62[++v64] == 0;
      while ( !v5 );
      v65 = 2 * v64 + 2;
    }
    else
    {
      v65 = 10;
      v62 = L"NULL";
    }
    v117 = v65;
    v116 = v62;
    v120 = &v97;
    v118 = L"NULL";
    v122 = &v98;
    v124 = &v96;
    v119 = 10;
    v121 = 4;
    v123 = 4;
    v125 = 4;
    McGenEventWrite_EtwEventWriteTransfer(
      (unsigned int)&RpcEtwGuid_Context,
      (unsigned int)RpcServerCallStartEvent,
      v6,
      10,
      (__int64)v107);
  }
  v15 = (struct _RPC_MESSAGE *)((char *)this + 336);
  v16 = *(_QWORD *)(*((_QWORD *)this + 38) + 56LL);
  if ( !*((_DWORD *)this + 128) )
  {
    v21 = (_DWORD *)*((_QWORD *)this + 39);
    v22 = *(_QWORD *)v21;
    if ( *(_QWORD *)(v16 + 152) != *(_QWORD *)(*(_QWORD *)v21 + 568LL) )
    {
      v20 = 1717;
      RpcpErrorAddRecord(2u, 1717, 0xACu, 0, 0);
      goto LABEL_65;
    }
    v23 = v21[3];
    if ( (*(_DWORD *)(v22 + 8) & 1) != 0 )
    {
      v24 = 1;
      v25 = _InterlockedIncrement((volatile signed __int32 *)(v22 + 348));
      v26 = _InterlockedIncrement((volatile signed __int32 *)(v22 + 340));
      if ( *(_DWORD *)(v22 + 344) )
        WakeByAddressAll((PVOID)(v22 + 340));
      if ( dword_1800FE624 )
      {
        for ( i = 0; i < 4; ++i )
        {
          if ( `LogEventToEtw'::`2'::EtwEventSubjectFilter[i] == 104 )
            goto LABEL_28;
        }
        if ( (Microsoft_Windows_RPCEnableBits & 8) != 0 )
        {
          v97 = v26;
          v98 = v25;
          v108 = &v94;
          v110 = &v95;
          v112 = (int *)&v96;
          v114 = (const wchar_t *)&v98;
          v116 = (const wchar_t *)&v97;
          v96 = v22;
          v95 = 43;
          v94 = 104;
          v109 = 1;
          v111 = 1;
          v113 = 8;
          v115 = 8;
          v117 = 8;
          McGenEventWrite_EtwEventWriteTransfer(
            (unsigned int)&RpcEtwGuid_Context,
            (unsigned int)RPCLogEvent,
            v24,
            6,
            (__int64)v107);
        }
      }
LABEL_28:
      v15 = (struct _RPC_MESSAGE *)((char *)this + 336);
    }
    _InterlockedIncrement((volatile signed __int32 *)(v22 + 332));
    if ( *(_DWORD *)(v22 + 336) )
      WakeByAddressAll((PVOID)(v22 + 332));
    _InterlockedOr(v90, 0);
    if ( dword_1800FE624 )
    {
      for ( j = 0; j < 4; ++j )
      {
        if ( `LogEventToEtw'::`2'::EtwEventSubjectFilter[j] == 105 )
          goto LABEL_38;
      }
      if ( (Microsoft_Windows_RPCEnableBits & 8) != 0 )
      {
        v97 = *(int *)(v22 + 332);
        v108 = &v94;
        v98 = 0;
        v110 = &v95;
        v96 = v22;
        v112 = (int *)&v96;
        v95 = 43;
        v114 = (const wchar_t *)&v98;
        v116 = (const wchar_t *)&v97;
        v94 = 105;
        v109 = 1;
        v111 = 1;
        v113 = 8;
        v115 = 8;
        v117 = 8;
        McGenEventWrite_EtwEventWriteTransfer(
          (unsigned int)&RpcEtwGuid_Context,
          (unsigned int)RPCLogEvent,
          0,
          6,
          (__int64)v107);
      }
    }
LABEL_38:
    if ( (*(_DWORD *)(v22 + 56) & 1) == 0 )
    {
      v83 = 1732;
      RpcpErrorAddRecord(2u, 1732, 0xAAu, 0, 0);
      if ( !*(_DWORD *)(v22 + 200) )
      {
        v83 = 1717;
        RpcpErrorAddRecord(2u, 1717, 0xABu, 0, 0);
        v15 = (struct _RPC_MESSAGE *)((char *)this + 336);
      }
      (*(void (__fastcall **)(RPC_BINDING_HANDLE, struct _RPC_MESSAGE *))(*(_QWORD *)v15->Handle + 120LL))(
        v15->Handle,
        v15);
      RPC_INTERFACE::EndNullManagerCall((RPC_INTERFACE *)v22);
      if ( (*(_DWORD *)(v22 + 8) & 1) != 0 )
        RPC_INTERFACE::EndAutoListenCall((RPC_INTERFACE *)v22, 1);
      v20 = v83;
      goto LABEL_64;
    }
    v15->ManagerEpv = *(void **)(v22 + 64);
    v29 = RPC_INTERFACE::DispatchToStubWorker((RPC_INTERFACE *)v22, v15, 0, v23, &v99);
    _InterlockedDecrement((volatile signed __int32 *)(v22 + 332));
    v20 = v29;
    if ( *(_DWORD *)(v22 + 336) )
      WakeByAddressAll((PVOID)(v22 + 332));
    _InterlockedOr(v90, 0);
    if ( dword_1800FE624 )
    {
      for ( k = 0; k < 4; ++k )
      {
        if ( `LogEventToEtw'::`2'::EtwEventSubjectFilter[k] == 105 )
          goto LABEL_48;
      }
      if ( (Microsoft_Windows_RPCEnableBits & 8) != 0 )
      {
        v97 = *(int *)(v22 + 332);
        v108 = &v94;
        v98 = 0;
        v110 = &v95;
        v96 = v22;
        v112 = (int *)&v96;
        v95 = 45;
        v114 = (const wchar_t *)&v98;
        v116 = (const wchar_t *)&v97;
        v94 = 105;
        v109 = 1;
        v111 = 1;
        v113 = 8;
        v115 = 8;
        v117 = 8;
        McGenEventWrite_EtwEventWriteTransfer(
          (unsigned int)&RpcEtwGuid_Context,
          (unsigned int)RPCLogEvent,
          v30,
          6,
          (__int64)v107);
      }
    }
LABEL_48:
    if ( (*(_DWORD *)(v22 + 8) & 1) == 0 )
      goto LABEL_64;
    v32 = (unsigned __int64)NtCurrentTeb()->ReservedForNtRpc;
    if ( !v32 || (v32 ^= 0xABABABABDEDEDEDEuLL, *(HANDLE *)(v32 + 16) == NtCurrentTeb()->ClientId.UniqueThread) )
    {
      if ( *(_DWORD *)v32 )
        v33 = 0;
      else
        v33 = _InterlockedDecrement((volatile signed __int32 *)(v22 + 348));
      v34 = _InterlockedExchangeAdd((volatile signed __int32 *)(v22 + 340), 0xFFFFFFFF);
      v35 = *(_DWORD *)(v22 + 344);
      v36 = (unsigned int)(v34 - 1);
      v96 = v36;
      if ( v35 )
      {
        WakeByAddressAll((PVOID)(v22 + 340));
        LODWORD(v36) = v96;
      }
      if ( dword_1800FE624 )
      {
        for ( m = 0; m < 4; ++m )
        {
          if ( `LogEventToEtw'::`2'::EtwEventSubjectFilter[m] == 104 )
            goto LABEL_64;
        }
        if ( (Microsoft_Windows_RPCEnableBits & 8) != 0 )
        {
          v97 = (int)v36;
          v98 = v33;
          v96 = v22;
          v108 = &v94;
          v110 = &v95;
          v112 = (int *)&v96;
          v114 = (const wchar_t *)&v98;
          v116 = (const wchar_t *)&v97;
          v95 = 45;
          v94 = 104;
          v109 = 1;
          v111 = 1;
          v113 = 8;
          v115 = 8;
          v117 = 8;
          McGenEventWrite_EtwEventWriteTransfer(
            (unsigned int)&RpcEtwGuid_Context,
            (unsigned int)RPCLogEvent,
            v30,
            6,
            (__int64)v107);
        }
      }
      goto LABEL_64;
    }
LABEL_16:
    __fastfail(0x1Eu);
  }
  v17 = (int *)*((_QWORD *)this + 39);
  v18 = *(_QWORD *)(v16 + 152);
  v126 = 0;
  v19 = *(_QWORD *)v17;
  if ( v18 == *(_QWORD *)(*(_QWORD *)v17 + 568LL) )
  {
    v102 = v17[3];
    v101 = 0;
    if ( this == (LRPC_SCALL *)-516LL
      || !*((_DWORD *)this + 129) && !*((_DWORD *)this + 130) && !*((_DWORD *)this + 131) && !*((_DWORD *)this + 132) )
    {
      goto LABEL_150;
    }
    RtlAcquireSRWLockShared(&ObjectTable[1].BalancedRoot.LeftChild);
    v46 = ObjectTable;
    RightChild = (int)ObjectTable[1].BalancedRoot.RightChild;
    if ( RightChild )
    {
      if ( RightChild != 1 )
        goto LABEL_95;
      v82 = (char *)RtlLookupElementGenericTableAvl(ObjectTable, (char *)this + 516);
      if ( v82 )
        n = (struct _RTL_BALANCED_LINKS *)(v82 - 32);
      else
        n = 0;
      v46 = ObjectTable;
    }
    else
    {
      for ( n = ObjectTable->BalancedRoot.Parent; n != (struct _RTL_BALANCED_LINKS *)v46; n = n->Parent )
      {
        if ( !memcmp_0(&n[1], (char *)this + 516, 0x10u) )
          goto LABEL_94;
      }
      n = 0;
    }
LABEL_94:
    if ( n )
    {
      v126 = *(_OWORD *)&n[1].RightChild;
      RtlReleaseSRWLockShared(&v46[1].BalancedRoot.LeftChild);
      goto LABEL_150;
    }
LABEL_95:
    RtlReleaseSRWLockShared(&v46[1].BalancedRoot.LeftChild);
    if ( !qword_1800FF420 )
    {
      v126 = 0;
      goto LABEL_97;
    }
    qword_1800FF420((char *)this + 516, &v126, &v101);
    if ( v101 )
    {
LABEL_97:
      if ( v18 == *(_QWORD *)(v19 + 568) )
      {
        if ( (*(_DWORD *)(v19 + 8) & 1) != 0 )
        {
          v50 = _InterlockedIncrement((volatile signed __int32 *)(v19 + 348));
          v51 = _InterlockedIncrement((volatile signed __int32 *)(v19 + 340));
          if ( *(_DWORD *)(v19 + 344) )
            WakeByAddressAll((PVOID)(v19 + 340));
          if ( dword_1800FE624 )
          {
            for ( ii = 0; ii < 4; ++ii )
            {
              if ( `LogEventToEtw'::`2'::EtwEventSubjectFilter[ii] == 104 )
                goto LABEL_108;
            }
            if ( (Microsoft_Windows_RPCEnableBits & 8) != 0 )
            {
              v97 = v51;
              v98 = v50;
              v108 = &v95;
              v110 = &v94;
              v112 = (int *)&v96;
              v114 = (const wchar_t *)&v98;
              v116 = (const wchar_t *)&v97;
              v96 = v19;
              v94 = 43;
              v95 = 104;
              v109 = 1;
              v111 = 1;
              v113 = 8;
              v115 = 8;
              v117 = 8;
              McGenEventWrite_EtwEventWriteTransfer(
                (unsigned int)&RpcEtwGuid_Context,
                (unsigned int)RPCLogEvent,
                v49,
                6,
                (__int64)v107);
            }
          }
        }
LABEL_108:
        RPC_INTERFACE::BeginNullManagerCall((RPC_INTERFACE *)v19);
        if ( (*(_DWORD *)(v19 + 56) & 1) == 0 )
        {
          v89 = 1732;
          RpcpErrorAddRecord(2u, 1732, 0xAAu, 0, 0);
          if ( !*(_DWORD *)(v19 + 200) )
          {
            v89 = 1717;
            RpcpErrorAddRecord(2u, 1717, 0xABu, 0, 0);
          }
          (*(void (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 42) + 120LL))(
            *((_QWORD *)this + 42),
            (char *)this + 336);
          RPC_INTERFACE::EndNullManagerCall((RPC_INTERFACE *)v19);
          if ( (*(_DWORD *)(v19 + 8) & 1) != 0 )
            RPC_INTERFACE::EndAutoListenCall((RPC_INTERFACE *)v19, 1);
          v20 = v89;
          goto LABEL_64;
        }
        v53 = v102;
        *((_QWORD *)this + 49) = *(_QWORD *)(v19 + 64);
        v20 = RPC_INTERFACE::DispatchToStubWorker(
                (RPC_INTERFACE *)v19,
                (struct _RPC_MESSAGE *)((char *)this + 336),
                0,
                v53,
                &v99);
        RPC_INTERFACE::EndNullManagerCall((RPC_INTERFACE *)v19);
        if ( (*(_DWORD *)(v19 + 8) & 1) != 0 )
        {
          v55 = (unsigned __int64)NtCurrentTeb()->ReservedForNtRpc;
          if ( !v55 || (v55 ^= 0xABABABABDEDEDEDEuLL, *(HANDLE *)(v55 + 16) == NtCurrentTeb()->ClientId.UniqueThread) )
          {
            if ( *(_DWORD *)v55 )
              v56 = 0;
            else
              v56 = _InterlockedDecrement((volatile signed __int32 *)(v19 + 348));
            v57 = _InterlockedDecrement((volatile signed __int32 *)(v19 + 340));
            if ( *(_DWORD *)(v19 + 344) )
              WakeByAddressAll((PVOID)(v19 + 340));
            if ( dword_1800FE624 )
            {
              for ( jj = 0; jj < 4; ++jj )
              {
                if ( `LogEventToEtw'::`2'::EtwEventSubjectFilter[jj] == 104 )
                  goto LABEL_64;
              }
              if ( (Microsoft_Windows_RPCEnableBits & 8) != 0 )
              {
                v97 = v57;
                v98 = v56;
                v108 = &v94;
                v110 = &v95;
                v112 = (int *)&v96;
                v114 = (const wchar_t *)&v98;
                v116 = (const wchar_t *)&v97;
                v96 = v19;
                v95 = 45;
                v94 = 104;
                v109 = 1;
                v111 = 1;
                v113 = 8;
                v115 = 8;
                v117 = 8;
                McGenEventWrite_EtwEventWriteTransfer(
                  (unsigned int)&RpcEtwGuid_Context,
                  (unsigned int)RPCLogEvent,
                  v54,
                  6,
                  (__int64)v107);
              }
            }
            goto LABEL_64;
          }
          goto LABEL_16;
        }
      }
      else
      {
        v20 = 1717;
        RpcpErrorAddRecord(2u, 1717, 0xACu, 0, 0);
      }
LABEL_64:
      v14 = ThreadInformation;
      goto LABEL_65;
    }
LABEL_150:
    InterfaceManager = RPC_INTERFACE::FindInterfaceManager((RPC_INTERFACE *)v19, (struct RPC_UUID *)&v126);
    v77 = InterfaceManager;
    if ( InterfaceManager && *((_DWORD *)InterfaceManager + 6) )
    {
      *((_QWORD *)this + 49) = *((_QWORD *)InterfaceManager + 2);
      if ( (*(_DWORD *)(v19 + 8) & 1) != 0 )
        RPC_INTERFACE::BeginAutoListenCall((RPC_INTERFACE *)v19, 1);
      WAITABLE_INTERLOCKED_INTEGER::Increment((struct RPC_INTERFACE_MANAGER *)((char *)v77 + 28));
      v78 = RPC_INTERFACE::DispatchToStubWorker(
              (RPC_INTERFACE *)v19,
              (struct _RPC_MESSAGE *)((char *)this + 336),
              0,
              v102,
              &v99);
      v79 = (struct RPC_INTERFACE_MANAGER *)((char *)v77 + 28);
      v20 = v78;
      WAITABLE_INTERLOCKED_INTEGER::Decrement(v79);
      if ( (*(_DWORD *)(v19 + 8) & 1) != 0 )
      {
        ThreadPointer = RpcpGetThreadPointer();
        RPC_INTERFACE::EndAutoListenCall((RPC_INTERFACE *)v19, *(_DWORD *)ThreadPointer == 0);
      }
      goto LABEL_64;
    }
    if ( (RPC_INTERFACE *)v19 != GlobalManagementInterface )
    {
      v20 = 1717;
      if ( *(_DWORD *)(v19 + 200) )
        v20 = 1732;
      (*(void (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 42) + 120LL))(
        *((_QWORD *)this + 42),
        (char *)this + 336);
      goto LABEL_64;
    }
    goto LABEL_97;
  }
  v20 = 1717;
  RpcpErrorAddRecord(2u, 1717, 0xADu, 0, 0);
LABEL_65:
  *(_QWORD *)(ReservedForNtRpc + 32) = 0;
  *(_DWORD *)ReservedForNtRpc = 0;
  ThreadInformation = 0;
  v38 = ThreadSelf();
  if ( v38 && *((_QWORD *)v38 + 5) )
  {
    *((_QWORD *)v38 + 5) = 0;
    NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
  }
  if ( (Microsoft_Windows_RPCEnableBits & 2) != 0 )
  {
    LODWORD(v96) = v20;
    v127 = &v96;
    v128 = 4;
    McGenEventWrite_EtwEventWriteTransfer(
      (unsigned int)&RpcEtwGuid_Context,
      (unsigned int)RpcServerCallEndEvent,
      v39,
      2,
      (__int64)&v126);
  }
  if ( v14 )
  {
    *(_WORD *)(v14 + 2) = 0;
    *(_DWORD *)(v14 + 4) = (MEMORY[0x7FFE0320] * (unsigned __int64)MEMORY[0x7FFE0004]) >> 24;
  }
  if ( v20 )
  {
    if ( v20 == -1073606642 )
    {
      v81 = v99;
    }
    else
    {
      if ( v20 == 1715 )
      {
        RpcpErrorAddRecord(2u, 1715, 0x14u, 0, 0);
        v20 = 1723;
      }
      RpcpErrorAddRecord(2u, v20, 0x15u, 0, 0);
      v81 = v20;
    }
    v20 = LrpcMapRpcStatus(v81);
  }
  if ( *((_QWORD *)this + 3) )
  {
    if ( v20 )
    {
      REFERENCED_OBJECT::RemoveReference(this);
      LRPC_ADDRESS::RpcFreeLrpcAddressBuffer(*(LRPC_ADDRESS **)(*((_QWORD *)this + 38) + 56LL), *((void **)this + 55));
      *((_QWORD *)this + 55) = 0;
    }
    else
    {
      *v105 = 1;
    }
  }
  else
  {
    *v105 = 0;
    v41 = *((_QWORD *)this + 55);
    v42 = *(_QWORD *)(*((_QWORD *)this + 38) + 56LL);
    v43 = *(BCACHE **)(v42 + 296);
    if ( v43 && v41 > (unsigned __int64)v43 && v41 < (unsigned __int64)v43 + *(unsigned int *)(v42 + 304) )
    {
      if ( dword_1800FE624 )
      {
        for ( kk = 0; kk < 4; ++kk )
        {
          if ( `LogEventToEtw'::`2'::EtwEventSubjectFilter[kk] == 76 )
            goto LABEL_130;
        }
        if ( (Microsoft_Windows_RPCEnableBits & 8) != 0 )
        {
          LOBYTE(v40) = 98;
          LOBYTE(v39) = 76;
          McTemplateU0uuxxx_EtwEventWriteTransfer((_DWORD)v43, kk, v39, v40, v41, v42, *(_QWORD *)(v42 + 296));
        }
      }
LABEL_130:
      AlpcFreeCompletionListMessage(*(_QWORD *)(v42 + 296), v41);
    }
    else if ( v41 )
    {
      BCACHE::Free(v43, *((void **)this + 55));
    }
    *((_QWORD *)this + 55) = 0;
  }
  return v20;
}

```

## disassembly

```asm
0x180023b80  mov     [rsp-8+arg_10], rbx
0x180023b85  push    rbp
0x180023b86  push    rsi
0x180023b87  push    rdi
0x180023b88  push    r12
0x180023b8a  push    r13
0x180023b8c  push    r14
0x180023b8e  push    r15
0x180023b90  lea     rbp, [rsp-80h]
0x180023b95  sub     rsp, 180h
0x180023b9c  mov     rax, cs:__security_cookie
0x180023ba3  xor     rax, rsp
0x180023ba6  mov     [rbp+0B0h+var_40], rax
0x180023baa  xor     edi, edi
0x180023bac  mov     [rbp+0B0h+var_120], rdx
0x180023bb0  mov     [rsp+1B0h+var_148], edi
0x180023bb4  xorps   xmm0, xmm0
0x180023bb7  movups  xmmword ptr [rbp+0B0h+var_118.Data1], xmm0
0x180023bbb  mov     rax, gs:30h
0x180023bc4  mov     r15, rcx
0x180023bc7  mov     r14, [rax+1698h]
0x180023bce  mov     rax, 0ABABABABDEDEDEDEh
0x180023bd8  test    r14, r14
0x180023bdb  jz      short loc_180023BF7
0x180023bdd  xor     r14, rax
0x180023be0  mov     rax, gs:30h
0x180023be9  mov     rcx, [rax+48h]
0x180023bed  cmp     [r14+10h], rcx
0x180023bf1  jnz     loc_180023D3F
0x180023bf7  mov     rax, [r15+130h]
0x180023bfe  mov     r13d, 7FFE0320h
0x180023c04  mov     rcx, [rax+38h]
0x180023c08  mov     r9, [rcx+98h]
0x180023c0f  add     byte ptr [r14+30h], 1
0x180023c14  jz      loc_1800248E1
0x180023c1a  mov     r8d, 10h; Size
0x180023c20  mov     [r14+20h], r15
0x180023c24  lea     rdx, ?g_NullActivityId@@3U_GUID@@B; Buf2
0x180023c2b  mov     [r14], edi
0x180023c2e  lea     rcx, [r15+0D0h]; Buf1
0x180023c35  call    memcmp_0
0x180023c3a  test    eax, eax
0x180023c3c  jz      short loc_180023C97
0x180023c3e  mov     rax, [r15+138h]
0x180023c45  mov     rcx, [r15+130h]; this
0x180023c4c  mov     rbx, [rax]
0x180023c4f  call    ?QueryCorrelationId@LRPC_SASSOCIATION@@QEAAKXZ; LRPC_SASSOCIATION::QueryCorrelationId(void)
0x180023c54  mov     edi, [r15+214h]
0x180023c5b  mov     esi, eax
0x180023c5d  call    cs:__imp_GetCurrentProcessId
0x180023c64  nop     dword ptr [rax+rax+00h]
0x180023c69  mov     ecx, [rbx+54h]
0x180023c6c  mov     [rbp+0B0h+var_118.Data1], ecx
0x180023c6f  movzx   ecx, word ptr [r15+1F0h]; unsigned __int64
0x180023c77  mov     [rbp+0B0h+var_118.Data2], ax
0x180023c7b  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x180023c81  mov     [rbp+0B0h+var_118.Data3], cx
0x180023c85  mov     dword ptr [rbp+0B0h+var_118.Data4], edi
0x180023c88  mov     dword ptr [rbp+0B0h+var_118.Data4+4], esi
0x180023c8b  test    eax, eax
0x180023c8d  jnz     loc_1800247ED
0x180023c93  xor     edi, edi
0x180023c95  jmp     short loc_180023CA5
0x180023c97  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x180023c9d  test    eax, eax
0x180023c9f  jnz     loc_18002480E
0x180023ca5  mov     r12, [r14+40h]
0x180023ca9  mov     [rsp+1B0h+ThreadInformation], r12
0x180023cae  test    r12, r12
0x180023cb1  jnz     loc_180024CCE
0x180023cb7  cmp     cs:?g_SqmEnabled@@3HA, 0; int g_SqmEnabled
0x180023cbe  jnz     loc_180024977
0x180023cc4  test    cs:Microsoft_Windows_RPCEnableBits, 2
0x180023ccb  jnz     loc_1800242CA
0x180023cd1  cmp     dword ptr [r15+200h], 0
0x180023cd9  lea     rsi, [r15+150h]
0x180023ce0  mov     rax, [r15+130h]
0x180023ce7  lea     r13, ?EtwEventSubjectFilter@?1??LogEventToEtw@@YAXEE_J00@Z@4QBEB; "HbBr"
0x180023cee  mov     rcx, [rax+38h]
0x180023cf2  jz      short loc_180023D46
0x180023cf4  mov     rax, [r15+138h]
0x180023cfb  xorps   xmm0, xmm0
0x180023cfe  mov     rbx, [rcx+98h]
0x180023d05  movups  [rbp+0B0h+var_60], xmm0
0x180023d09  mov     rdi, [rax]
0x180023d0c  cmp     rbx, [rdi+238h]
0x180023d13  jz      loc_1800240CA
0x180023d19  xor     edi, edi
0x180023d1b  mov     esi, 6B5h
0x180023d20  mov     edx, esi; int
0x180023d22  mov     [rsp+1B0h+var_190], rdi; struct tagParam *
0x180023d27  mov     r8d, 0ADh; unsigned __int16
0x180023d2d  xor     r9d, r9d; int
0x180023d30  mov     ecx, 2; unsigned int
0x180023d35  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x180023d3a  jmp     loc_180023F62
0x180023d3f  mov     ecx, 1Eh
0x180023d44  int     29h; Win8: RtlFailFast(ecx)
0x180023d46  mov     rdx, [r15+138h]
0x180023d4d  mov     rbx, [rdx]
0x180023d50  mov     rax, [rbx+238h]
0x180023d57  cmp     [rcx+98h], rax
0x180023d5e  jnz     loc_180024B15
0x180023d64  mov     eax, [rbx+8]
0x180023d67  mov     r12d, [rdx+0Ch]
0x180023d6b  test    al, 1
0x180023d6d  jz      short loc_180023DD1
0x180023d6f  mov     r8d, 1
0x180023d75  mov     esi, r8d
0x180023d78  lock xadd [rbx+15Ch], esi
0x180023d80  inc     esi
0x180023d82  lea     rcx, [rbx+154h]; Address
0x180023d89  mov     edi, r8d
0x180023d8c  lock xadd [rcx], edi
0x180023d90  mov     eax, [rcx+4]
0x180023d93  inc     edi
0x180023d95  test    eax, eax
0x180023d97  jnz     loc_1800248D0
0x180023d9d  cmp     cs:dword_1800FE624, 0
0x180023da4  jz      short loc_180023DCA
0x180023da6  xor     edx, edx
0x180023da8  mov     ecx, edx
0x180023daa  cmp     ecx, 4
0x180023dad  jnb     short loc_180023DBD
0x180023daf  movsxd  rax, ecx
0x180023db2  cmp     byte ptr [rax+r13], 68h ; 'h'
0x180023db7  jz      short loc_180023DCA
0x180023db9  inc     ecx
0x180023dbb  jmp     short loc_180023DAA
0x180023dbd  test    cs:Microsoft_Windows_RPCEnableBits, 8
0x180023dc4  jnz     loc_180024478
0x180023dca  lea     rsi, [r15+150h]
0x180023dd1  lea     rdi, [rbx+14Ch]
0x180023dd8  lock inc dword ptr [rdi]
0x180023ddb  mov     eax, [rdi+4]
0x180023dde  test    eax, eax
0x180023de0  jnz     loc_180024871
0x180023de6  lock or [rsp+1B0h+var_1B0], 0
0x180023deb  movsxd  rdx, dword ptr [rbx+14Ch]
0x180023df2  cmp     cs:dword_1800FE624, 0
0x180023df9  jz      short loc_180023E21
0x180023dfb  xor     r8d, r8d
0x180023dfe  mov     ecx, r8d
0x180023e01  cmp     ecx, 4
0x180023e04  jnb     short loc_180023E14
0x180023e06  movsxd  rax, ecx
0x180023e09  cmp     byte ptr [rax+r13], 69h ; 'i'
0x180023e0e  jz      short loc_180023E21
0x180023e10  inc     ecx
0x180023e12  jmp     short loc_180023E01
0x180023e14  test    cs:Microsoft_Windows_RPCEnableBits, 8
0x180023e1b  jnz     loc_1800243E3
0x180023e21  mov     eax, [rbx+38h]
0x180023e24  test    al, 1
0x180023e26  jz      loc_180024C44
0x180023e2c  mov     rax, [rbx+40h]
0x180023e30  mov     r9d, r12d; int
0x180023e33  mov     [rsi+38h], rax
0x180023e37  xor     r8d, r8d; unsigned int
0x180023e3a  lea     rax, [rsp+1B0h+var_148]
0x180023e3f  mov     rdx, rsi; struct _RPC_MESSAGE *
0x180023e42  mov     rcx, rbx; this
0x180023e45  mov     [rsp+1B0h+var_190], rax; int *
0x180023e4a  call    ?DispatchToStubWorker@RPC_INTERFACE@@AEAAJPEAU_RPC_MESSAGE@@IHPEAJ@Z; RPC_INTERFACE::DispatchToStubWorker(_RPC_MESSAGE *,uint,int,long *)
0x180023e4f  lock dec dword ptr [rdi]
0x180023e52  mov     esi, eax
0x180023e54  mov     eax, [rdi+4]
0x180023e57  test    eax, eax
0x180023e59  jnz     loc_180024A86
0x180023e5f  lock or [rsp+1B0h+var_1B0], 0
0x180023e64  movsxd  rdx, dword ptr [rbx+14Ch]
0x180023e6b  xor     r12d, r12d
0x180023e6e  cmp     cs:dword_1800FE624, r12d
0x180023e75  jz      short loc_180023E9A
0x180023e77  mov     ecx, r12d
0x180023e7a  cmp     ecx, 4
0x180023e7d  jnb     short loc_180023E8D
0x180023e7f  movsxd  rax, ecx
0x180023e82  cmp     byte ptr [rax+r13], 69h ; 'i'
0x180023e87  jz      short loc_180023E9A
0x180023e89  inc     ecx
0x180023e8b  jmp     short loc_180023E7A
0x180023e8d  test    cs:Microsoft_Windows_RPCEnableBits, 8
0x180023e94  jnz     loc_180024512
0x180023e9a  mov     eax, [rbx+8]
0x180023e9d  test    al, 1
0x180023e9f  jz      loc_180023F43
0x180023ea5  mov     rax, gs:30h
0x180023eae  mov     rdx, [rax+1698h]
0x180023eb5  test    rdx, rdx
0x180023eb8  jz      short loc_180023EDE
0x180023eba  mov     rax, 0ABABABABDEDEDEDEh
0x180023ec4  xor     rdx, rax
0x180023ec7  mov     rax, gs:30h
0x180023ed0  mov     rcx, [rax+48h]
0x180023ed4  cmp     [rdx+10h], rcx
0x180023ed8  jnz     loc_180023D3F
0x180023ede  cmp     dword ptr [rdx], 0
0x180023ee1  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x180023ee8  jnz     loc_1800242C2
0x180023eee  mov     edi, edx
0x180023ef0  lock xadd [rbx+15Ch], edi
0x180023ef8  dec     edi
0x180023efa  lea     rcx, [rbx+154h]; Address
0x180023f01  lock xadd [rcx], edx
0x180023f05  mov     eax, [rcx+4]
0x180023f08  dec     edx
0x180023f0a  mov     [rsp+1B0h+var_160], rdx
0x180023f0f  test    eax, eax
0x180023f11  jnz     loc_180024A9A
0x180023f17  cmp     cs:dword_1800FE624, 0
0x180023f1e  jz      short loc_180023F43
0x180023f20  mov     ecx, r12d
0x180023f23  cmp     ecx, 4
0x180023f26  jnb     short loc_180023F36
0x180023f28  movsxd  rax, ecx
0x180023f2b  cmp     byte ptr [rax+r13], 68h ; 'h'
0x180023f30  jz      short loc_180023F43
0x180023f32  inc     ecx
0x180023f34  jmp     short loc_180023F23
0x180023f36  test    cs:Microsoft_Windows_RPCEnableBits, 8
0x180023f3d  jnz     loc_1800245A7
0x180023f43  xor     edi, edi
0x180023f45  jmp     short loc_180023F5D
0x180023f47  test    cs:Microsoft_Windows_RPCEnableBits, 8
0x180023f4e  jnz     loc_180024732
0x180023f54  xor     edi, edi
0x180023f56  lea     r13, ?EtwEventSubjectFilter@?1??LogEventToEtw@@YAXEE_J00@Z@4QBEB; "HbBr"
0x180023f5d  mov     r12, [rsp+1B0h+ThreadInformation]
0x180023f62  mov     [r14+20h], rdi
0x180023f66  mov     [r14], edi
0x180023f69  mov     [rsp+1B0h+ThreadInformation], rdi
0x180023f6e  call    ?ThreadSelf@@YAPEAVTHREAD@@XZ; ThreadSelf(void)
0x180023f73  test    rax, rax
0x180023f76  jz      short loc_180023FA6
0x180023f78  cmp     qword ptr [rax+28h], 0
0x180023f7d  jz      short loc_180023FA6
0x180023f7f  mov     r9d, 8; ThreadInformationLength
0x180023f85  mov     [rax+28h], rdi
0x180023f89  lea     r8, [rsp+1B0h+ThreadInformation]; ThreadInformation
0x180023f8e  mov     edx, 5; ThreadInformationClass
0x180023f93  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180023f9a  call    cs:__imp_NtSetInformationThread
0x180023fa1  nop     dword ptr [rax+rax+00h]
0x180023fa6  test    cs:Microsoft_Windows_RPCEnableBits, 2
0x180023fad  jnz     loc_180024049
0x180023fb3  test    r12, r12
0x180023fb6  jnz     loc_1800248A9
0x180023fbc  test    esi, esi
0x180023fbe  jnz     loc_180024AB0
0x180023fc4  cmp     qword ptr [r15+18h], 0
0x180023fc9  jnz     short loc_180024035
0x180023fcb  mov     rax, [rbp+0B0h+var_120]
0x180023fcf  mov     [rax], edi
0x180023fd1  mov     rax, [r15+130h]
0x180023fd8  mov     rbx, [r15+1B8h]
0x180023fdf  mov     rdi, [rax+38h]
0x180023fe3  mov     rcx, [rdi+128h]; this
0x180023fea  test    rcx, rcx
0x180023fed  jnz     loc_180024085
0x180023ff3  test    rbx, rbx
0x180023ff6  jz      short loc_180024000
0x180023ff8  mov     rdx, rbx; void *
0x180023ffb  call    ?Free@BCACHE@@QEAAXPEAX@Z; BCACHE::Free(void *)
0x180024000  mov     qword ptr [r15+1B8h], 0
0x18002400b  mov     eax, esi
0x18002400d  mov     rcx, [rbp+0B0h+var_40]
0x180024011  xor     rcx, rsp; StackCookie
0x180024014  call    __security_check_cookie
0x180024019  mov     rbx, [rsp+1B0h+arg_10]
0x180024021  add     rsp, 180h
0x180024028  pop     r15
0x18002402a  pop     r14
0x18002402c  pop     r13
0x18002402e  pop     r12
0x180024030  pop     rdi
0x180024031  pop     rsi
0x180024032  pop     rbp
0x180024033  retn
0x180024035  test    esi, esi
0x180024037  jnz     loc_180024E54
0x18002403d  mov     rax, [rbp+0B0h+var_120]
0x180024041  mov     dword ptr [rax], 1
0x180024047  jmp     short loc_18002400B
0x180024049  lea     rax, [rsp+1B0h+var_160]
0x18002404e  mov     dword ptr [rsp+1B0h+var_160], esi
0x180024052  mov     [rbp+0B0h+var_50], rax
0x180024056  lea     rdx, RpcServerCallEndEvent
0x18002405d  lea     rax, [rbp+0B0h+var_60]
0x180024061  mov     [rbp+0B0h+var_48], 4
0x180024069  mov     r9d, 2
0x18002406f  mov     [rsp+1B0h+var_190], rax
0x180024074  lea     rcx, RpcEtwGuid_Context
0x18002407b  call    McGenEventWrite_EtwEventWriteTransfer
0x180024080  jmp     loc_180023FB3
0x180024085  cmp     rbx, rcx
0x180024088  jbe     loc_180023FF3
0x18002408e  mov     eax, [rdi+130h]
0x180024094  add     rax, rcx
0x180024097  cmp     rbx, rax
  ... truncated ...
```
