# LRPC_SCALL::DispatchRequest(int *)

- ea: `0x1800229b0`
- end: `0x180023c90`
- name: `?DispatchRequest@LRPC_SCALL@@QEAAJPEAH@Z`
- size: `4832`
- prototype: `__int64 __fastcall(LRPC_SCALL *__hidden this, int *)`
- caller_count: `2`
- callee_count: `26`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001c140`
- `0x1800362dc`

## callees

- `0x180016ae8`
- `0x1800191d0`
- `0x18001b6c0`
- `0x18001d750`
- `0x180021e18`
- `0x1800229b0`
- `0x180023ca0`
- `0x180025130`
- `0x180027e5c`
- `0x180027f84`
- `0x1800280b0`
- `0x1800283bc`
- `0x18002896c`
- `0x180028a00`
- `0x180077c40`
- `0x180078830`
- `0x18007c7b4`
- `0x18009045c`
- `0x1800905c8`
- `0x180095d70`
- `0x180096930`
- `0x1800a4b8c`
- `0x1800a86a8`
- `0x1800ca025`
- `0x1800ca140`
- `0x1800d2010`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x18002366a`
- `ntdll!EtwEventActivityIdControl` at `0x18002366a`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x1800239ca`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x1800239ca`
- `ntdll!NtSetInformationThread` at `0x180022dc4`
- `ntdll!NtSetInformationThread` at `0x180022dc4`
- `ntdll!RtlReleaseSRWLockShared` at `0x180022f56`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800237fa`
- `ntdll!RtlReleaseSRWLockShared` at `0x180022f56`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800237fa`
- `ntdll!RtlAcquireSRWLockShared` at `0x180022f22`
- `ntdll!RtlAcquireSRWLockShared` at `0x180022f22`
- `ntdll!WinSqmIncrementDWORD` at `0x1800237db`
- `ntdll!WinSqmIncrementDWORD` at `0x1800237db`
- `ntdll!AlpcFreeCompletionListMessage` at `0x180023472`
- `ntdll!AlpcFreeCompletionListMessage` at `0x180023472`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180022a8d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002363f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180022a8d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002363f`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x18002367a`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x1800236d0`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x1800238a0`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x1800238ae`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x1800238b9`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x18002391d`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x18002367a`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x1800236d0`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x1800238a0`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x1800238ae`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x1800238b9`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x18002391d`

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
  unsigned __int32 v24; // esi
  signed __int32 v25; // edi
  unsigned int i; // ecx
  unsigned int j; // ecx
  unsigned int v28; // eax
  int v29; // r8d
  unsigned int k; // ecx
  unsigned __int64 v31; // rdx
  unsigned __int32 v32; // edi
  signed __int32 v33; // edx
  int v34; // eax
  __int64 v35; // rdx
  unsigned int m; // ecx
  struct THREAD *v37; // rax
  int v38; // r8d
  int v39; // r9d
  unsigned __int64 v40; // rbx
  __int64 v41; // rdi
  BCACHE *v42; // rcx
  unsigned int kk; // edx
  PRTL_AVL_TABLE v45; // rsi
  int RightChild; // ecx
  struct _RTL_BALANCED_LINKS *n; // r12
  int v48; // r8d
  unsigned __int32 v49; // esi
  signed __int32 v50; // ebx
  unsigned int ii; // ecx
  int v52; // r9d
  int v53; // r8d
  unsigned __int64 v54; // rdx
  unsigned __int32 v55; // ebx
  signed __int32 v56; // r13d
  unsigned int jj; // ecx
  __int64 v58; // rax
  __int64 v59; // rcx
  __int64 *v60; // rax
  const wchar_t *v61; // rdx
  __int64 v62; // rcx
  __int64 v63; // rax
  unsigned int v64; // eax
  __int64 v65; // rbx
  unsigned int CorrelationId; // eax
  int v67; // edi
  unsigned int v68; // esi
  unsigned __int16 CurrentProcessId; // ax
  __int64 v70; // r11
  signed __int64 v71; // rbx
  unsigned __int64 v72; // r10
  unsigned int v73; // edx
  unsigned int v74; // ebx
  struct RPC_INTERFACE_MANAGER *InterfaceManager; // rax
  struct RPC_INTERFACE_MANAGER *v76; // rsi
  unsigned int v77; // eax
  WAITABLE_INTERLOCKED_INTEGER *v78; // rcx
  struct THREAD *ThreadPointer; // rax
  int v80; // ecx
  char *v81; // rax
  int v82; // r12d
  __int64 v83; // rax
  __int64 v84; // rdx
  unsigned __int64 v85; // rdx
  __int64 v86; // rcx
  __int64 v87; // rcx
  int v88; // r12d
  signed __int32 v89[8]; // [rsp+0h] [rbp-100h] BYREF
  struct tagParam *v90; // [rsp+20h] [rbp-E0h]
  const struct _GUID *v91; // [rsp+28h] [rbp-D8h]
  __int64 v92; // [rsp+30h] [rbp-D0h]
  char v93; // [rsp+40h] [rbp-C0h] BYREF
  char v94; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v95; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v96; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v97; // [rsp+60h] [rbp-A0h] BYREF
  int v98; // [rsp+68h] [rbp-98h] BYREF
  __int64 ThreadInformation; // [rsp+70h] [rbp-90h] BYREF
  int v100; // [rsp+78h] [rbp-88h] BYREF
  int v101; // [rsp+7Ch] [rbp-84h]
  int v102; // [rsp+80h] [rbp-80h] BYREF
  int v103; // [rsp+88h] [rbp-78h] BYREF
  int *v104; // [rsp+90h] [rbp-70h]
  struct _GUID v105; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v106[16]; // [rsp+B0h] [rbp-50h] BYREF
  char *v107; // [rsp+C0h] [rbp-40h]
  __int64 v108; // [rsp+C8h] [rbp-38h]
  char *v109; // [rsp+D0h] [rbp-30h]
  __int64 v110; // [rsp+D8h] [rbp-28h]
  int *v111; // [rsp+E0h] [rbp-20h]
  __int64 v112; // [rsp+E8h] [rbp-18h]
  const wchar_t *v113; // [rsp+F0h] [rbp-10h]
  __int64 v114; // [rsp+F8h] [rbp-8h]
  const wchar_t *v115; // [rsp+100h] [rbp+0h]
  __int64 v116; // [rsp+108h] [rbp+8h]
  const wchar_t *v117; // [rsp+110h] [rbp+10h]
  __int64 v118; // [rsp+118h] [rbp+18h]
  __int64 *v119; // [rsp+120h] [rbp+20h]
  __int64 v120; // [rsp+128h] [rbp+28h]
  __int64 *v121; // [rsp+130h] [rbp+30h]
  __int64 v122; // [rsp+138h] [rbp+38h]
  __int64 *v123; // [rsp+140h] [rbp+40h]
  __int64 v124; // [rsp+148h] [rbp+48h]
  __int128 v125; // [rsp+150h] [rbp+50h] BYREF
  __int64 *v126; // [rsp+160h] [rbp+60h]
  __int64 v127; // [rsp+168h] [rbp+68h]

  v104 = a2;
  v98 = 0;
  v105 = 0;
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
    v70 = *(_QWORD *)(*((_QWORD *)this + 38) + 56LL);
    _InterlockedIncrement((volatile signed __int32 *)(v70 + 328));
    do
    {
      v72 = (MEMORY[0x7FFE0320] * (unsigned __int64)MEMORY[0x7FFE0004]) >> 24;
      v73 = v72 - HIDWORD(*(_QWORD *)(v70 + 328));
      if ( v73 <= 0x7D0 )
        break;
      v71 = *(_QWORD *)(v70 + 328);
    }
    while ( v71 != _InterlockedCompareExchange64(
                     (volatile signed __int64 *)(v70 + 328),
                     ((unsigned __int64)(unsigned int)(v72 - 1000) << 32)
                   | (unsigned int)(1000 * (unsigned __int64)(unsigned int)v71 / v73),
                     v71) );
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
      v65 = **((_QWORD **)this + 39);
      CorrelationId = LRPC_SASSOCIATION::QueryCorrelationId(*((LRPC_SASSOCIATION **)this + 38));
      v67 = *((_DWORD *)this + 133);
      v68 = CorrelationId;
      CurrentProcessId = GetCurrentProcessId();
      v105.Data1 = *(_DWORD *)(v65 + 84);
      v105.Data3 = *((_WORD *)this + 248);
      v105.Data2 = CurrentProcessId;
      *(_DWORD *)v105.Data4 = v67;
      *(_DWORD *)&v105.Data4[4] = v68;
      EtwEventActivityIdControl(2, &v105);
    }
  }
  else
  {
    v7 = **((_QWORD **)this + 39);
    v8 = LRPC_SASSOCIATION::QueryCorrelationId(*((LRPC_SASSOCIATION **)this + 38));
    v9 = *((_DWORD *)this + 133);
    v10 = v8;
    v11 = GetCurrentProcessId();
    v105.Data1 = *(_DWORD *)(v7 + 84);
    v13 = *((unsigned __int16 *)this + 248);
    v105.Data2 = v11;
    v105.Data3 = v13;
    *(_DWORD *)v105.Data4 = v9;
    *(_DWORD *)&v105.Data4[4] = v10;
    if ( Microsoft_Windows_Networking_CorrelationEnabled )
      EtwEx_tidActivityInfoTransfer(v13, v12, (const struct _GUID *)this + 13, &v105, (unsigned __int8)v90, v91, v92);
  }
  v14 = *(_QWORD *)(ReservedForNtRpc + 64);
  ThreadInformation = v14;
  if ( v14 )
  {
    v83 = MEMORY[0x7FFE0320];
    v84 = MEMORY[0x7FFE0004];
    *(_WORD *)(v14 + 2) = 1;
    v85 = (unsigned __int64)(v83 * v84) >> 24;
    *(_DWORD *)(v14 + 4) = v85;
    v6 = *((_QWORD *)this + 40);
    *(_DWORD *)(v6 + 4) = *(_DWORD *)(**((_QWORD **)this + 39) + 84LL);
    *(_DWORD *)(v6 + 16) = *((_DWORD *)this + 133);
    *(_DWORD *)(v6 + 20) = v85;
    *(_WORD *)(v6 + 24) = *((_WORD *)this + 248);
    *(_WORD *)(v6 + 26) = *((_WORD *)this + 252);
    *(_WORD *)(v6 + 2) = *((_WORD *)this + 182);
    *(_BYTE *)(v6 + 1) = 2;
    *(_WORD *)(v6 + 8) = *(_WORD *)(ReservedForNtRpc + 56);
    v86 = *(unsigned int *)(ReservedForNtRpc + 56);
    v87 = (unsigned int)v86 < *((_DWORD *)g_pCellHeap + 10) ? *(_QWORD *)(*((_QWORD *)g_pCellHeap + 4) + 8 * v86) : 0LL;
    *(_WORD *)(v6 + 10) = (v14 - v87) >> 5;
    if ( (*(_DWORD *)(**((_QWORD **)this + 39) + 56LL) & 2) != 0 )
      *(_DWORD *)(v6 + 12) |= 4u;
  }
  if ( g_SqmEnabled )
  {
    v74 = *(__int16 *)(*((_QWORD *)this + 55) + 4LL) & 0xFFFF8000;
    if ( (*(_DWORD *)(**((_QWORD **)this + 39) + 8LL) & 2) == 0 )
      UpdateDataPoint(&RawRpcCallsReceived, 0x49Cu);
    if ( v74 )
    {
      v6 = ++KLRPCCallsReceived;
      if ( (int)KLRPCCallsReceived >= 50000
        && (_DWORD)v6 == _InterlockedCompareExchange(
                           (volatile signed __int32 *)&KLRPCCallsReceived,
                           0,
                           KLRPCCallsReceived) )
      {
        WinSqmIncrementDWORD(0, 1178, v6, 1);
      }
    }
  }
  if ( (Microsoft_Windows_RPCEnableBits & 2) != 0 )
  {
    v58 = *((_QWORD *)this + 38);
    LODWORD(v95) = 0;
    LODWORD(v97) = 20;
    LODWORD(v96) = 6;
    v59 = *(_QWORD *)(v58 + 56);
    v102 = *((_DWORD *)this + 91);
    v60 = (__int64 *)*((_QWORD *)this + 39);
    v61 = *(const wchar_t **)(v59 + 32);
    v103 = 3;
    v108 = 16;
    v62 = *v60;
    v109 = (char *)&v102;
    v107 = (char *)(v62 + 84);
    v113 = L"NULL";
    v110 = 4;
    v111 = &v103;
    v112 = 4;
    v114 = 10;
    if ( v61 )
    {
      v63 = -1;
      do
        v5 = v61[++v63] == 0;
      while ( !v5 );
      v64 = 2 * v63 + 2;
    }
    else
    {
      v64 = 10;
      v61 = L"NULL";
    }
    v116 = v64;
    v115 = v61;
    v119 = &v96;
    v117 = L"NULL";
    v121 = &v97;
    v123 = &v95;
    v118 = 10;
    v120 = 4;
    v122 = 4;
    v124 = 4;
    McGenEventWrite_EtwEventWriteTransfer(
      (unsigned int)&RpcEtwGuid_Context,
      (unsigned int)RpcServerCallStartEvent,
      v6,
      10,
      (__int64)v106);
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
      v24 = _InterlockedIncrement((volatile signed __int32 *)(v22 + 348));
      v25 = _InterlockedIncrement((volatile signed __int32 *)(v22 + 340));
      if ( *(_DWORD *)(v22 + 344) )
        WakeByAddressAll((PVOID)(v22 + 340));
      if ( dword_1800F9624 )
      {
        for ( i = 0; i < 4; ++i )
        {
          if ( `LogEventToEtw'::`2'::EtwEventSubjectFilter[i] == 104 )
            goto LABEL_28;
        }
        if ( (Microsoft_Windows_RPCEnableBits & 8) != 0 )
        {
          v96 = v25;
          v97 = v24;
          v107 = &v93;
          v109 = &v94;
          v111 = (int *)&v95;
          v113 = (const wchar_t *)&v97;
          v115 = (const wchar_t *)&v96;
          v95 = v22;
          v94 = 43;
          v93 = 104;
          v108 = 1;
          v110 = 1;
          v112 = 8;
          v114 = 8;
          v116 = 8;
          McGenEventWrite_EtwEventWriteTransfer(
            (unsigned int)&RpcEtwGuid_Context,
            (unsigned int)RPCLogEvent,
            v6,
            6,
            (__int64)v106);
        }
      }
LABEL_28:
      v15 = (struct _RPC_MESSAGE *)((char *)this + 336);
    }
    _InterlockedIncrement((volatile signed __int32 *)(v22 + 332));
    if ( *(_DWORD *)(v22 + 336) )
      WakeByAddressAll((PVOID)(v22 + 332));
    _InterlockedOr(v89, 0);
    if ( dword_1800F9624 )
    {
      for ( j = 0; j < 4; ++j )
      {
        if ( `LogEventToEtw'::`2'::EtwEventSubjectFilter[j] == 105 )
          goto LABEL_38;
      }
      if ( (Microsoft_Windows_RPCEnableBits & 8) != 0 )
      {
        v96 = *(int *)(v22 + 332);
        v107 = &v93;
        v97 = 0;
        v109 = &v94;
        v95 = v22;
        v111 = (int *)&v95;
        v94 = 43;
        v113 = (const wchar_t *)&v97;
        v115 = (const wchar_t *)&v96;
        v93 = 105;
        v108 = 1;
        v110 = 1;
        v112 = 8;
        v114 = 8;
        v116 = 8;
        McGenEventWrite_EtwEventWriteTransfer(
          (unsigned int)&RpcEtwGuid_Context,
          (unsigned int)RPCLogEvent,
          0,
          6,
          (__int64)v106);
      }
    }
LABEL_38:
    if ( (*(_DWORD *)(v22 + 56) & 1) == 0 )
    {
      v82 = 1732;
      RpcpErrorAddRecord(2u, 1732, 0xAAu, 0, 0);
      if ( !*(_DWORD *)(v22 + 200) )
      {
        v82 = 1717;
        RpcpErrorAddRecord(2u, 1717, 0xABu, 0, 0);
        v15 = (struct _RPC_MESSAGE *)((char *)this + 336);
      }
      (*(void (__fastcall **)(RPC_BINDING_HANDLE, struct _RPC_MESSAGE *))(*(_QWORD *)v15->Handle + 120LL))(
        v15->Handle,
        v15);
      RPC_INTERFACE::EndNullManagerCall((RPC_INTERFACE *)v22);
      if ( (*(_DWORD *)(v22 + 8) & 1) != 0 )
        RPC_INTERFACE::EndAutoListenCall((RPC_INTERFACE *)v22, 1);
      v20 = v82;
      goto LABEL_64;
    }
    v15->ManagerEpv = *(void **)(v22 + 64);
    v28 = RPC_INTERFACE::DispatchToStubWorker((RPC_INTERFACE *)v22, v15, 0, v23, &v98);
    _InterlockedDecrement((volatile signed __int32 *)(v22 + 332));
    v20 = v28;
    if ( *(_DWORD *)(v22 + 336) )
      WakeByAddressAll((PVOID)(v22 + 332));
    _InterlockedOr(v89, 0);
    if ( dword_1800F9624 )
    {
      for ( k = 0; k < 4; ++k )
      {
        if ( `LogEventToEtw'::`2'::EtwEventSubjectFilter[k] == 105 )
          goto LABEL_48;
      }
      if ( (Microsoft_Windows_RPCEnableBits & 8) != 0 )
      {
        v96 = *(int *)(v22 + 332);
        v107 = &v93;
        v97 = 0;
        v109 = &v94;
        v95 = v22;
        v111 = (int *)&v95;
        v94 = 45;
        v113 = (const wchar_t *)&v97;
        v115 = (const wchar_t *)&v96;
        v93 = 105;
        v108 = 1;
        v110 = 1;
        v112 = 8;
        v114 = 8;
        v116 = 8;
        McGenEventWrite_EtwEventWriteTransfer(
          (unsigned int)&RpcEtwGuid_Context,
          (unsigned int)RPCLogEvent,
          v29,
          6,
          (__int64)v106);
      }
    }
LABEL_48:
    if ( (*(_DWORD *)(v22 + 8) & 1) == 0 )
      goto LABEL_64;
    v31 = (unsigned __int64)NtCurrentTeb()->ReservedForNtRpc;
    if ( !v31 || (v31 ^= 0xABABABABDEDEDEDEuLL, *(HANDLE *)(v31 + 16) == NtCurrentTeb()->ClientId.UniqueThread) )
    {
      if ( *(_DWORD *)v31 )
        v32 = 0;
      else
        v32 = _InterlockedDecrement((volatile signed __int32 *)(v22 + 348));
      v33 = _InterlockedExchangeAdd((volatile signed __int32 *)(v22 + 340), 0xFFFFFFFF);
      v34 = *(_DWORD *)(v22 + 344);
      v35 = (unsigned int)(v33 - 1);
      v95 = v35;
      if ( v34 )
      {
        WakeByAddressAll((PVOID)(v22 + 340));
        LODWORD(v35) = v95;
      }
      if ( dword_1800F9624 )
      {
        for ( m = 0; m < 4; ++m )
        {
          if ( `LogEventToEtw'::`2'::EtwEventSubjectFilter[m] == 104 )
            goto LABEL_64;
        }
        if ( (Microsoft_Windows_RPCEnableBits & 8) != 0 )
        {
          v96 = (int)v35;
          v97 = v32;
          v95 = v22;
          v107 = &v93;
          v109 = &v94;
          v111 = (int *)&v95;
          v113 = (const wchar_t *)&v97;
          v115 = (const wchar_t *)&v96;
          v94 = 45;
          v93 = 104;
          v108 = 1;
          v110 = 1;
          v112 = 8;
          v114 = 8;
          v116 = 8;
          McGenEventWrite_EtwEventWriteTransfer(
            (unsigned int)&RpcEtwGuid_Context,
            (unsigned int)RPCLogEvent,
            v29,
            6,
            (__int64)v106);
        }
      }
      goto LABEL_64;
    }
LABEL_16:
    __fastfail(0x1Eu);
  }
  v17 = (int *)*((_QWORD *)this + 39);
  v18 = *(_QWORD *)(v16 + 152);
  v125 = 0;
  v19 = *(_QWORD *)v17;
  if ( v18 == *(_QWORD *)(*(_QWORD *)v17 + 568LL) )
  {
    v101 = v17[3];
    v100 = 0;
    if ( this == (LRPC_SCALL *)-516LL
      || !*((_DWORD *)this + 129) && !*((_DWORD *)this + 130) && !*((_DWORD *)this + 131) && !*((_DWORD *)this + 132) )
    {
      goto LABEL_152;
    }
    RtlAcquireSRWLockShared(&ObjectTable[1].BalancedRoot.LeftChild);
    v45 = ObjectTable;
    RightChild = (int)ObjectTable[1].BalancedRoot.RightChild;
    if ( RightChild )
    {
      if ( RightChild != 1 )
        goto LABEL_95;
      v81 = (char *)RtlLookupElementGenericTableAvl(ObjectTable, (char *)this + 516);
      if ( v81 )
        n = (struct _RTL_BALANCED_LINKS *)(v81 - 32);
      else
        n = 0;
      v45 = ObjectTable;
    }
    else
    {
      for ( n = ObjectTable->BalancedRoot.Parent; n != (struct _RTL_BALANCED_LINKS *)v45; n = n->Parent )
      {
        if ( !memcmp_0(&n[1], (char *)this + 516, 0x10u) )
          goto LABEL_94;
      }
      n = 0;
    }
LABEL_94:
    if ( n )
    {
      v125 = *(_OWORD *)&n[1].RightChild;
      RtlReleaseSRWLockShared(&v45[1].BalancedRoot.LeftChild);
      goto LABEL_152;
    }
LABEL_95:
    RtlReleaseSRWLockShared(&v45[1].BalancedRoot.LeftChild);
    if ( !qword_1800FA420 )
    {
      v125 = 0;
      goto LABEL_97;
    }
    qword_1800FA420((char *)this + 516, &v125, &v100);
    if ( v100 )
    {
LABEL_97:
      if ( v18 == *(_QWORD *)(v19 + 568) )
      {
        if ( (*(_DWORD *)(v19 + 8) & 1) != 0 )
        {
          v49 = _InterlockedIncrement((volatile signed __int32 *)(v19 + 348));
          v50 = _InterlockedIncrement((volatile signed __int32 *)(v19 + 340));
          if ( *(_DWORD *)(v19 + 344) )
            WakeByAddressAll((PVOID)(v19 + 340));
          if ( dword_1800F9624 )
          {
            for ( ii = 0; ii < 4; ++ii )
            {
              if ( `LogEventToEtw'::`2'::EtwEventSubjectFilter[ii] == 104 )
                goto LABEL_108;
            }
            if ( (Microsoft_Windows_RPCEnableBits & 8) != 0 )
            {
              v96 = v50;
              v97 = v49;
              v107 = &v94;
              v109 = &v93;
              v111 = (int *)&v95;
              v113 = (const wchar_t *)&v97;
              v115 = (const wchar_t *)&v96;
              v95 = v19;
              v93 = 43;
              v94 = 104;
              v108 = 1;
              v110 = 1;
              v112 = 8;
              v114 = 8;
              v116 = 8;
              McGenEventWrite_EtwEventWriteTransfer(
                (unsigned int)&RpcEtwGuid_Context,
                (unsigned int)RPCLogEvent,
                v48,
                6,
                (__int64)v106);
            }
          }
        }
LABEL_108:
        RPC_INTERFACE::BeginNullManagerCall((RPC_INTERFACE *)v19);
        if ( (*(_DWORD *)(v19 + 56) & 1) == 0 )
        {
          v88 = 1732;
          RpcpErrorAddRecord(2u, 1732, 0xAAu, 0, 0);
          if ( !*(_DWORD *)(v19 + 200) )
          {
            v88 = 1717;
            RpcpErrorAddRecord(2u, 1717, 0xABu, 0, 0);
          }
          (*(void (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 42) + 120LL))(
            *((_QWORD *)this + 42),
            (char *)this + 336);
          RPC_INTERFACE::EndNullManagerCall((RPC_INTERFACE *)v19);
          if ( (*(_DWORD *)(v19 + 8) & 1) != 0 )
            RPC_INTERFACE::EndAutoListenCall((RPC_INTERFACE *)v19, 1);
          v20 = v88;
          goto LABEL_64;
        }
        v52 = v101;
        *((_QWORD *)this + 49) = *(_QWORD *)(v19 + 64);
        v20 = RPC_INTERFACE::DispatchToStubWorker(
                (RPC_INTERFACE *)v19,
                (struct _RPC_MESSAGE *)((char *)this + 336),
                0,
                v52,
                &v98);
        RPC_INTERFACE::EndNullManagerCall((RPC_INTERFACE *)v19);
        if ( (*(_DWORD *)(v19 + 8) & 1) != 0 )
        {
          v54 = (unsigned __int64)NtCurrentTeb()->ReservedForNtRpc;
          if ( !v54 || (v54 ^= 0xABABABABDEDEDEDEuLL, *(HANDLE *)(v54 + 16) == NtCurrentTeb()->ClientId.UniqueThread) )
          {
            if ( *(_DWORD *)v54 )
              v55 = 0;
            else
              v55 = _InterlockedDecrement((volatile signed __int32 *)(v19 + 348));
            v56 = _InterlockedDecrement((volatile signed __int32 *)(v19 + 340));
            if ( *(_DWORD *)(v19 + 344) )
              WakeByAddressAll((PVOID)(v19 + 340));
            if ( dword_1800F9624 )
            {
              for ( jj = 0; jj < 4; ++jj )
              {
                if ( `LogEventToEtw'::`2'::EtwEventSubjectFilter[jj] == 104 )
                  goto LABEL_64;
              }
              if ( (Microsoft_Windows_RPCEnableBits & 8) != 0 )
              {
                v96 = v56;
                v97 = v55;
                v107 = &v93;
                v109 = &v94;
                v111 = (int *)&v95;
                v113 = (const wchar_t *)&v97;
                v115 = (const wchar_t *)&v96;
                v95 = v19;
                v94 = 45;
                v93 = 104;
                v108 = 1;
                v110 = 1;
                v112 = 8;
                v114 = 8;
                v116 = 8;
                McGenEventWrite_EtwEventWriteTransfer(
                  (unsigned int)&RpcEtwGuid_Context,
                  (unsigned int)RPCLogEvent,
                  v53,
                  6,
                  (__int64)v106);
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
LABEL_152:
    InterfaceManager = RPC_INTERFACE::FindInterfaceManager((RPC_INTERFACE *)v19, (struct RPC_UUID *)&v125);
    v76 = InterfaceManager;
    if ( InterfaceManager && *((_DWORD *)InterfaceManager + 6) )
    {
      *((_QWORD *)this + 49) = *((_QWORD *)InterfaceManager + 2);
      if ( (*(_DWORD *)(v19 + 8) & 1) != 0 )
        RPC_INTERFACE::BeginAutoListenCall((RPC_INTERFACE *)v19, 1);
      WAITABLE_INTERLOCKED_INTEGER::Increment((struct RPC_INTERFACE_MANAGER *)((char *)v76 + 28));
      v77 = RPC_INTERFACE::DispatchToStubWorker(
              (RPC_INTERFACE *)v19,
              (struct _RPC_MESSAGE *)((char *)this + 336),
              0,
              v101,
              &v98);
      v78 = (struct RPC_INTERFACE_MANAGER *)((char *)v76 + 28);
      v20 = v77;
      WAITABLE_INTERLOCKED_INTEGER::Decrement(v78);
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
  v37 = ThreadSelf();
  if ( v37 && *((_QWORD *)v37 + 5) )
  {
    *((_QWORD *)v37 + 5) = 0;
    NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
  }
  if ( (Microsoft_Windows_RPCEnableBits & 2) != 0 )
  {
    LODWORD(v95) = v20;
    v126 = &v95;
    v127 = 4;
    McGenEventWrite_EtwEventWriteTransfer(
      (unsigned int)&RpcEtwGuid_Context,
      (unsigned int)RpcServerCallEndEvent,
      v38,
      2,
      (__int64)&v125);
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
      v80 = v98;
    }
    else
    {
      if ( v20 == 1715 )
      {
        RpcpErrorAddRecord(2u, 1715, 0x14u, 0, 0);
        v20 = 1723;
      }
      RpcpErrorAddRecord(2u, v20, 0x15u, 0, 0);
      v80 = v20;
    }
    v20 = LrpcMapRpcStatus(v80);
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
      *v104 = 1;
    }
  }
  else
  {
    *v104 = 0;
    v40 = *((_QWORD *)this + 55);
    v41 = *(_QWORD *)(*((_QWORD *)this + 38) + 56LL);
    v42 = *(BCACHE **)(v41 + 296);
    if ( v42 && v40 > (unsigned __int64)v42 && v40 < (unsigned __int64)v42 + *(unsigned int *)(v41 + 304) )
    {
      if ( dword_1800F9624 )
      {
        for ( kk = 0; kk < 4; ++kk )
        {
          if ( `LogEventToEtw'::`2'::EtwEventSubjectFilter[kk] == 76 )
            goto LABEL_130;
        }
        if ( (Microsoft_Windows_RPCEnableBits & 8) != 0 )
        {
          LOBYTE(v39) = 98;
          LOBYTE(v38) = 76;
          McTemplateU0uuxxx_EtwEventWriteTransfer((_DWORD)v42, kk, v38, v39, v40, v41, *(_QWORD *)(v41 + 296));
        }
      }
LABEL_130:
      AlpcFreeCompletionListMessage(*(_QWORD *)(v41 + 296), v40);
    }
    else if ( v40 )
    {
      BCACHE::Free(v42, *((void **)this + 55));
    }
    *((_QWORD *)this + 55) = 0;
  }
  return v20;
}

```

## disassembly

```asm
0x1800229b0  mov     [rsp-8+arg_10], rbx
0x1800229b5  push    rbp
0x1800229b6  push    rsi
0x1800229b7  push    rdi
0x1800229b8  push    r12
0x1800229ba  push    r13
0x1800229bc  push    r14
0x1800229be  push    r15
0x1800229c0  lea     rbp, [rsp-80h]
0x1800229c5  sub     rsp, 180h
0x1800229cc  mov     rax, cs:__security_cookie
0x1800229d3  xor     rax, rsp
0x1800229d6  mov     [rbp+0B0h+var_40], rax
0x1800229da  xor     edi, edi
0x1800229dc  mov     [rbp+0B0h+var_120], rdx
0x1800229e0  mov     [rsp+1B0h+var_148], edi
0x1800229e4  xorps   xmm0, xmm0
0x1800229e7  movups  xmmword ptr [rbp+0B0h+var_118.Data1], xmm0
0x1800229eb  mov     rax, gs:30h
0x1800229f4  mov     r15, rcx
0x1800229f7  mov     r14, [rax+1698h]
0x1800229fe  mov     rax, 0ABABABABDEDEDEDEh
0x180022a08  test    r14, r14
0x180022a0b  jz      short loc_180022A27
0x180022a0d  xor     r14, rax
0x180022a10  mov     rax, gs:30h
0x180022a19  mov     rcx, [rax+48h]
0x180022a1d  cmp     [r14+10h], rcx
0x180022a21  jnz     loc_180022B6F
0x180022a27  mov     rax, [r15+130h]
0x180022a2e  mov     r13d, 7FFE0320h
0x180022a34  mov     rcx, [rax+38h]
0x180022a38  mov     r9, [rcx+98h]
0x180022a3f  add     byte ptr [r14+30h], 1
0x180022a44  jz      loc_1800236DB
0x180022a4a  mov     r8d, 10h; Size
0x180022a50  mov     [r14+20h], r15
0x180022a54  lea     rdx, ?g_NullActivityId@@3U_GUID@@B; Buf2
0x180022a5b  mov     [r14], edi
0x180022a5e  lea     rcx, [r15+0D0h]; Buf1
0x180022a65  call    memcmp_0
0x180022a6a  test    eax, eax
0x180022a6c  jz      short loc_180022AC1
0x180022a6e  mov     rax, [r15+138h]
0x180022a75  mov     rcx, [r15+130h]; this
0x180022a7c  mov     rbx, [rax]
0x180022a7f  call    ?QueryCorrelationId@LRPC_SASSOCIATION@@QEAAKXZ; LRPC_SASSOCIATION::QueryCorrelationId(void)
0x180022a84  mov     edi, [r15+214h]
0x180022a8b  mov     esi, eax
0x180022a8d  call    cs:__imp_GetCurrentProcessId
0x180022a93  mov     ecx, [rbx+54h]
0x180022a96  mov     [rbp+0B0h+var_118.Data1], ecx
0x180022a99  movzx   ecx, word ptr [r15+1F0h]; unsigned __int64
0x180022aa1  mov     [rbp+0B0h+var_118.Data2], ax
0x180022aa5  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x180022aab  mov     [rbp+0B0h+var_118.Data3], cx
0x180022aaf  mov     dword ptr [rbp+0B0h+var_118.Data4], edi
0x180022ab2  mov     dword ptr [rbp+0B0h+var_118.Data4+4], esi
0x180022ab5  test    eax, eax
0x180022ab7  jnz     loc_1800235FF
0x180022abd  xor     edi, edi
0x180022abf  jmp     short loc_180022ACF
0x180022ac1  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x180022ac7  test    eax, eax
0x180022ac9  jnz     loc_180023620
0x180022acf  mov     r12, [r14+40h]
0x180022ad3  mov     r9d, 1
0x180022ad9  mov     [rsp+1B0h+ThreadInformation], r12
0x180022ade  test    r12, r12
0x180022ae1  jnz     loc_180023ADB
0x180022ae7  cmp     cs:?g_SqmEnabled@@3HA, 0; int g_SqmEnabled
0x180022aee  jnz     loc_180023771
0x180022af4  test    cs:Microsoft_Windows_RPCEnableBits, 2
0x180022afb  jnz     loc_1800230E1
0x180022b01  cmp     dword ptr [r15+200h], 0
0x180022b09  lea     rsi, [r15+150h]
0x180022b10  mov     rax, [r15+130h]
0x180022b17  lea     r13, ?EtwEventSubjectFilter@?1??LogEventToEtw@@YAXEE_J00@Z@4QBEB; "HbBr"
0x180022b1e  mov     rcx, [rax+38h]
0x180022b22  jz      short loc_180022B76
0x180022b24  mov     rax, [r15+138h]
0x180022b2b  xorps   xmm0, xmm0
0x180022b2e  mov     rbx, [rcx+98h]
0x180022b35  movups  [rbp+0B0h+var_60], xmm0
0x180022b39  mov     rdi, [rax]
0x180022b3c  cmp     rbx, [rdi+238h]
0x180022b43  jz      loc_180022EED
0x180022b49  xor     edi, edi
0x180022b4b  mov     esi, 6B5h
0x180022b50  mov     edx, esi; int
0x180022b52  mov     [rsp+1B0h+var_190], rdi; struct tagParam *
0x180022b57  mov     r8d, 0ADh; unsigned __int16
0x180022b5d  xor     r9d, r9d; int
0x180022b60  mov     ecx, 2; unsigned int
0x180022b65  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x180022b6a  jmp     loc_180022D8C
0x180022b6f  mov     ecx, 1Eh
0x180022b74  int     29h; Win8: RtlFailFast(ecx)
0x180022b76  mov     rdx, [r15+138h]
0x180022b7d  mov     rbx, [rdx]
0x180022b80  mov     rax, [rbx+238h]
0x180022b87  cmp     [rcx+98h], rax
0x180022b8e  jnz     loc_180023928
0x180022b94  mov     eax, [rbx+8]
0x180022b97  mov     r12d, [rdx+0Ch]
0x180022b9b  test    al, 1
0x180022b9d  jz      short loc_180022BFB
0x180022b9f  mov     esi, r9d
0x180022ba2  lock xadd [rbx+15Ch], esi
0x180022baa  inc     esi
0x180022bac  lea     rcx, [rbx+154h]; Address
0x180022bb3  mov     edi, r9d
0x180022bb6  lock xadd [rcx], edi
0x180022bba  mov     eax, [rcx+4]
0x180022bbd  inc     edi
0x180022bbf  test    eax, eax
0x180022bc1  jnz     loc_1800236D0
0x180022bc7  cmp     cs:dword_1800F9624, 0
0x180022bce  jz      short loc_180022BF4
0x180022bd0  xor     edx, edx
0x180022bd2  mov     ecx, edx
0x180022bd4  cmp     ecx, 4
0x180022bd7  jnb     short loc_180022BE7
0x180022bd9  movsxd  rax, ecx
0x180022bdc  cmp     byte ptr [rax+r13], 68h ; 'h'
0x180022be1  jz      short loc_180022BF4
0x180022be3  inc     ecx
0x180022be5  jmp     short loc_180022BD4
0x180022be7  test    cs:Microsoft_Windows_RPCEnableBits, 8
0x180022bee  jnz     loc_180023290
0x180022bf4  lea     rsi, [r15+150h]
0x180022bfb  lea     rdi, [rbx+14Ch]
0x180022c02  lock inc dword ptr [rdi]
0x180022c05  mov     eax, [rdi+4]
0x180022c08  test    eax, eax
0x180022c0a  jnz     loc_180023677
0x180022c10  lock or [rsp+1B0h+var_1B0], 0
0x180022c15  movsxd  rdx, dword ptr [rbx+14Ch]
0x180022c1c  cmp     cs:dword_1800F9624, 0
0x180022c23  jz      short loc_180022C4B
0x180022c25  xor     r8d, r8d
0x180022c28  mov     ecx, r8d
0x180022c2b  cmp     ecx, 4
0x180022c2e  jnb     short loc_180022C3E
0x180022c30  movsxd  rax, ecx
0x180022c33  cmp     byte ptr [rax+r13], 69h ; 'i'
0x180022c38  jz      short loc_180022C4B
0x180022c3a  inc     ecx
0x180022c3c  jmp     short loc_180022C2B
0x180022c3e  test    cs:Microsoft_Windows_RPCEnableBits, 8
0x180022c45  jnz     loc_1800231FB
0x180022c4b  mov     eax, [rbx+38h]
0x180022c4e  test    al, 1
0x180022c50  jz      loc_180023A51
0x180022c56  mov     rax, [rbx+40h]
0x180022c5a  mov     r9d, r12d; int
0x180022c5d  mov     [rsi+38h], rax
0x180022c61  xor     r8d, r8d; unsigned int
0x180022c64  lea     rax, [rsp+1B0h+var_148]
0x180022c69  mov     rdx, rsi; struct _RPC_MESSAGE *
0x180022c6c  mov     rcx, rbx; this
0x180022c6f  mov     [rsp+1B0h+var_190], rax; int *
0x180022c74  call    ?DispatchToStubWorker@RPC_INTERFACE@@AEAAJPEAU_RPC_MESSAGE@@IHPEAJ@Z; RPC_INTERFACE::DispatchToStubWorker(_RPC_MESSAGE *,uint,int,long *)
0x180022c79  lock dec dword ptr [rdi]
0x180022c7c  mov     esi, eax
0x180022c7e  mov     eax, [rdi+4]
0x180022c81  test    eax, eax
0x180022c83  jnz     loc_1800238AB
0x180022c89  lock or [rsp+1B0h+var_1B0], 0
0x180022c8e  movsxd  rdx, dword ptr [rbx+14Ch]
0x180022c95  xor     r12d, r12d
0x180022c98  cmp     cs:dword_1800F9624, r12d
0x180022c9f  jz      short loc_180022CC4
0x180022ca1  mov     ecx, r12d
0x180022ca4  cmp     ecx, 4
0x180022ca7  jnb     short loc_180022CB7
0x180022ca9  movsxd  rax, ecx
0x180022cac  cmp     byte ptr [rax+r13], 69h ; 'i'
0x180022cb1  jz      short loc_180022CC4
0x180022cb3  inc     ecx
0x180022cb5  jmp     short loc_180022CA4
0x180022cb7  test    cs:Microsoft_Windows_RPCEnableBits, 8
0x180022cbe  jnz     loc_18002332A
0x180022cc4  mov     eax, [rbx+8]
0x180022cc7  test    al, 1
0x180022cc9  jz      loc_180022D6D
0x180022ccf  mov     rax, gs:30h
0x180022cd8  mov     rdx, [rax+1698h]
0x180022cdf  test    rdx, rdx
0x180022ce2  jz      short loc_180022D08
0x180022ce4  mov     rax, 0ABABABABDEDEDEDEh
0x180022cee  xor     rdx, rax
0x180022cf1  mov     rax, gs:30h
0x180022cfa  mov     rcx, [rax+48h]
0x180022cfe  cmp     [rdx+10h], rcx
0x180022d02  jnz     loc_180022B6F
0x180022d08  cmp     dword ptr [rdx], 0
0x180022d0b  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x180022d12  jnz     loc_1800230D9
0x180022d18  mov     edi, edx
0x180022d1a  lock xadd [rbx+15Ch], edi
0x180022d22  dec     edi
0x180022d24  lea     rcx, [rbx+154h]; Address
0x180022d2b  lock xadd [rcx], edx
0x180022d2f  mov     eax, [rcx+4]
0x180022d32  dec     edx
0x180022d34  mov     [rsp+1B0h+var_160], rdx
0x180022d39  test    eax, eax
0x180022d3b  jnz     loc_1800238B9
0x180022d41  cmp     cs:dword_1800F9624, 0
0x180022d48  jz      short loc_180022D6D
0x180022d4a  mov     ecx, r12d
0x180022d4d  cmp     ecx, 4
0x180022d50  jnb     short loc_180022D60
0x180022d52  movsxd  rax, ecx
0x180022d55  cmp     byte ptr [rax+r13], 68h ; 'h'
0x180022d5a  jz      short loc_180022D6D
0x180022d5c  inc     ecx
0x180022d5e  jmp     short loc_180022D4D
0x180022d60  test    cs:Microsoft_Windows_RPCEnableBits, 8
0x180022d67  jnz     loc_1800233BF
0x180022d6d  xor     edi, edi
0x180022d6f  jmp     short loc_180022D87
0x180022d71  test    cs:Microsoft_Windows_RPCEnableBits, 8
0x180022d78  jnz     loc_180023544
0x180022d7e  xor     edi, edi
0x180022d80  lea     r13, ?EtwEventSubjectFilter@?1??LogEventToEtw@@YAXEE_J00@Z@4QBEB; "HbBr"
0x180022d87  mov     r12, [rsp+1B0h+ThreadInformation]
0x180022d8c  mov     [r14+20h], rdi
0x180022d90  mov     [r14], edi
0x180022d93  mov     [rsp+1B0h+ThreadInformation], rdi
0x180022d98  call    ?ThreadSelf@@YAPEAVTHREAD@@XZ; ThreadSelf(void)
0x180022d9d  test    rax, rax
0x180022da0  jz      short loc_180022DCA
0x180022da2  cmp     qword ptr [rax+28h], 0
0x180022da7  jz      short loc_180022DCA
0x180022da9  mov     r9d, 8; ThreadInformationLength
0x180022daf  mov     [rax+28h], rdi
0x180022db3  lea     r8, [rsp+1B0h+ThreadInformation]; ThreadInformation
0x180022db8  mov     edx, 5; ThreadInformationClass
0x180022dbd  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180022dc4  call    cs:__imp_NtSetInformationThread
0x180022dca  test    cs:Microsoft_Windows_RPCEnableBits, 2
0x180022dd1  jnz     loc_180022E6C
0x180022dd7  test    r12, r12
0x180022dda  jnz     loc_1800236A9
0x180022de0  test    esi, esi
0x180022de2  jnz     loc_1800238C9
0x180022de8  cmp     qword ptr [r15+18h], 0
0x180022ded  jnz     short loc_180022E58
0x180022def  mov     rax, [rbp+0B0h+var_120]
0x180022df3  mov     [rax], edi
0x180022df5  mov     rax, [r15+130h]
0x180022dfc  mov     rbx, [r15+1B8h]
0x180022e03  mov     rdi, [rax+38h]
0x180022e07  mov     rcx, [rdi+128h]; this
0x180022e0e  test    rcx, rcx
0x180022e11  jnz     loc_180022EA8
0x180022e17  test    rbx, rbx
0x180022e1a  jz      short loc_180022E24
0x180022e1c  mov     rdx, rbx; void *
0x180022e1f  call    ?Free@BCACHE@@QEAAXPEAX@Z; BCACHE::Free(void *)
0x180022e24  mov     qword ptr [r15+1B8h], 0
0x180022e2f  mov     eax, esi
0x180022e31  mov     rcx, [rbp+0B0h+var_40]
0x180022e35  xor     rcx, rsp; StackCookie
0x180022e38  call    __security_check_cookie
0x180022e3d  mov     rbx, [rsp+1B0h+arg_10]
0x180022e45  add     rsp, 180h
0x180022e4c  pop     r15
0x180022e4e  pop     r14
0x180022e50  pop     r13
0x180022e52  pop     r12
0x180022e54  pop     rdi
0x180022e55  pop     rsi
0x180022e56  pop     rbp
0x180022e57  retn
0x180022e58  test    esi, esi
0x180022e5a  jnz     loc_180023C65
0x180022e60  mov     rax, [rbp+0B0h+var_120]
0x180022e64  mov     dword ptr [rax], 1
0x180022e6a  jmp     short loc_180022E2F
0x180022e6c  lea     rax, [rsp+1B0h+var_160]
0x180022e71  mov     dword ptr [rsp+1B0h+var_160], esi
0x180022e75  mov     [rbp+0B0h+var_50], rax
0x180022e79  lea     rdx, RpcServerCallEndEvent
0x180022e80  lea     rax, [rbp+0B0h+var_60]
0x180022e84  mov     [rbp+0B0h+var_48], 4
0x180022e8c  mov     r9d, 2
0x180022e92  mov     [rsp+1B0h+var_190], rax
0x180022e97  lea     rcx, RpcEtwGuid_Context
0x180022e9e  call    McGenEventWrite_EtwEventWriteTransfer
0x180022ea3  jmp     loc_180022DD7
0x180022ea8  cmp     rbx, rcx
0x180022eab  jbe     loc_180022E17
0x180022eb1  mov     eax, [rdi+130h]
0x180022eb7  add     rax, rcx
0x180022eba  cmp     rbx, rax
0x180022ebd  jnb     loc_180022E17
0x180022ec3  cmp     cs:dword_1800F9624, 0
  ... truncated ...
```
