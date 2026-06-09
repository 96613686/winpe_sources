# StartTetheringService(int)

- ea: `0x18000b888`
- end: `0x18000bd39`
- name: `?StartTetheringService@@YAKH@Z`
- size: `1201`
- prototype: `unsigned int __fastcall(int)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, service_task`

## callers

- `0x18000b370`

## callees

- `0x18000299c`
- `0x18000b774`
- `0x18000b888`
- `0x18000bd50`
- `0x18000bf4c`
- `0x18000bf74`
- `0x18000bfb4`
- `0x18000c5fc`
- `0x1800145d8`
- `0x18001935c`
- `0x180019b4c`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000b9fb`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000ba43`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000b9fb`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000ba43`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000bbb8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000bbb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ba0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ba55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bc3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ba0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ba55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bc3d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18000bc19`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18000bc19`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bafc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bb30`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bafc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bb30`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18000bb17`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18000bb17`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18000bc8c`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18000bc8c`
- `ntdll!RtlNtStatusToDosError` at `0x18000bcb1`
- `ntdll!RtlNtStatusToDosError` at `0x18000bcb1`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall StartTetheringService(int a1, __int64 a2, __int64 a3, __int64 a4)
{
  TetheringServiceTelemetry *v5; // rcx
  TetheringService *v6; // rax
  TetheringService *v7; // rbx
  unsigned int v8; // ebx
  TetheringServiceTelemetry *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r9
  DWORD LastError; // eax
  __int64 v13; // r8
  TetheringServiceTelemetry *v14; // rcx
  __int64 v16; // r8
  DWORD v17; // eax
  NTSTATUS v18; // eax
  TetheringServiceTelemetry *v19; // rcx
  signed int v20; // eax

  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      LOBYTE(a4) = a1 != 0;
      WPP_SF_c(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_44e4735379a936cf4f13ce357ad19005_Traceguids, a4);
      v5 = WPP_GLOBAL_Control;
    }
    if ( v5 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 8) != 0 )
    {
      LOBYTE(a4) = a1 != 0;
      WPP_SF_c(*((_QWORD *)v5 + 2), 13, &WPP_44e4735379a936cf4f13ce357ad19005_Traceguids, a4);
    }
  }
  v6 = (TetheringService *)operator new(0x768u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v6 )
    v7 = TetheringService::TetheringService(v6);
  else
    v7 = 0;
  if ( v7 )
  {
    if ( *(_QWORD *)g_pTetheringSessionId.Data4 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)g_pTetheringSessionId.Data4 + 16LL))(*(_QWORD *)g_pTetheringSessionId.Data4);
    *(_QWORD *)g_pTetheringSessionId.Data4 = v7;
    v8 = TetheringService::Initialize(v7);
    if ( a1 )
      TetheringService::InitializeBluetooth(*(TetheringService **)g_pTetheringSessionId.Data4);
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_44e4735379a936cf4f13ce357ad19005_Traceguids, v8);
      v9 = WPP_GLOBAL_Control;
    }
    if ( v8 )
      goto LABEL_22;
    g_StopHandles = CreateEventW(0, 1, 0, 0);
    if ( !g_StopHandles )
    {
      LastError = GetLastError();
      v8 = LastError;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_39;
      }
      v10 = 38;
      goto LABEL_37;
    }
    hEvent = CreateEventW(0, 0, 0, 0);
    if ( !hEvent )
    {
      LastError = GetLastError();
      v8 = LastError;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_39;
      }
      v10 = 39;
      goto LABEL_37;
    }
    SetTetheringServiceStatus(2u, 0, v13);
    LastError = (*((__int64 (__fastcall **)(HANDLE *, const WCHAR *, HANDLE, void (__fastcall *)(void *), _QWORD, int))g_TetheringSvcHostGlobalData
                 + 24))(
                  &WaitHandle,
                  L"icssvc",
                  g_StopHandles,
                  InitiateStopTetheringService,
                  0,
                  24);
    v8 = LastError;
    if ( LastError )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_39;
      }
      v10 = 40;
LABEL_37:
      v11 = LastError;
LABEL_38:
      WPP_SF_d(*((_QWORD *)v9 + 2), v10, &WPP_44e4735379a936cf4f13ce357ad19005_Traceguids, v11);
      goto LABEL_39;
    }
    TetheringSvcRpcServerInitialize();
    g_ServiceStatus.dwControlsAccepted = 129;
    SetTetheringServiceStatus(4u, 0, v16);
    SetEvent(hEvent);
    g_Environment.Version = 3;
    g_Environment.Pool = 0;
    g_Environment.CleanupGroup = 0;
    g_Environment.CleanupGroupCancelCallback = 0;
    *(_OWORD *)&g_Environment.RaceDll = 0;
    g_Environment.FinalizationCallback = 0;
    g_Environment.u.Flags = 0;
    g_Environment.CallbackPriority = TP_CALLBACK_PRIORITY_NORMAL;
    g_Environment.Size = 72;
    g_ProcessOutOfBandEntitelmentCheckBackgroundWork = CreateThreadpoolWork(
                                                         OutOfBandEntitlementCheckBackgroundProcessing,
                                                         0,
                                                         &g_Environment);
    if ( !g_ProcessOutOfBandEntitelmentCheckBackgroundWork
      && WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v17 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_44e4735379a936cf4f13ce357ad19005_Traceguids, v17);
    }
    v18 = RtlSubscribeWnfStateChangeNotification(
            &g_pWnfSharingChanged,
            WNF_SHR_SHARING_CHANGED,
            0,
            HandleWnfSharingChangedCallback,
            0,
            0,
            0,
            1);
    if ( v18 < 0 )
    {
      g_pWnfSharingChanged = 0;
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
        return 0;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      {
LABEL_63:
        if ( v19 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)v19 + 28) & 4) != 0 )
          {
            WPP_SF_(*((_QWORD *)v19 + 2), 43, &WPP_44e4735379a936cf4f13ce357ad19005_Traceguids);
            v19 = WPP_GLOBAL_Control;
          }
          if ( v19 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v19 + 28) & 8) != 0 )
            WPP_SF_(*((_QWORD *)v19 + 2), 44, &WPP_44e4735379a936cf4f13ce357ad19005_Traceguids);
        }
        return 0;
      }
      v20 = RtlNtStatusToDosError(v18);
      if ( v20 > 0 )
        v20 = (unsigned __int16)v20 | 0x80070000;
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        42,
        &WPP_44e4735379a936cf4f13ce357ad19005_Traceguids,
        (unsigned int)v20);
    }
    v19 = WPP_GLOBAL_Control;
    goto LABEL_63;
  }
  v8 = 14;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_44e4735379a936cf4f13ce357ad19005_Traceguids, 14);
      v9 = WPP_GLOBAL_Control;
    }
LABEL_22:
    if ( v9 == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control || (*((_BYTE *)v9 + 28) & 1) == 0 )
      goto LABEL_39;
    v10 = 37;
    v11 = v8;
    goto LABEL_38;
  }
LABEL_39:
  if ( g_StopHandles )
  {
    CloseHandle(g_StopHandles);
    g_StopHandles = 0;
  }
  if ( WaitHandle )
  {
    UnregisterWaitEx(WaitHandle, 0);
    WaitHandle = 0;
  }
  if ( hEvent )
  {
    CloseHandle(hEvent);
    hEvent = 0;
  }
  UninitializeTetheringSvc();
  g_ErrorCode = v8;
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_44e4735379a936cf4f13ce357ad19005_Traceguids, v8);
      v14 = WPP_GLOBAL_Control;
    }
    if ( v14 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)v14 + 2), 46, &WPP_44e4735379a936cf4f13ce357ad19005_Traceguids);
  }
  return v8;
}

```

## disassembly

```asm
0x18000b888  mov     [rsp+arg_0], rbx
0x18000b88d  mov     [rsp+arg_10], rbp
0x18000b892  push    rsi
0x18000b893  push    rdi
0x18000b894  push    r14
0x18000b896  sub     rsp, 40h
0x18000b89a  mov     edi, ecx
0x18000b89c  lea     rbp, WPP_GLOBAL_Control
0x18000b8a3  xor     esi, esi
0x18000b8a5  lea     r14, WPP_44e4735379a936cf4f13ce357ad19005_Traceguids
0x18000b8ac  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b8b3  cmp     rcx, rbp
0x18000b8b6  jz      short loc_18000B8FC
0x18000b8b8  test    byte ptr [rcx+1Ch], 8
0x18000b8bc  jz      short loc_18000B8DA
0x18000b8be  test    edi, edi
0x18000b8c0  setnz   r9b
0x18000b8c4  lea     edx, [rsi+24h]
0x18000b8c7  mov     r8, r14
0x18000b8ca  mov     rcx, [rcx+10h]
0x18000b8ce  call    WPP_SF_c
0x18000b8d3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b8da  cmp     rcx, rbp
0x18000b8dd  jz      short loc_18000B8FC
0x18000b8df  test    byte ptr [rcx+1Ch], 8
0x18000b8e3  jz      short loc_18000B8FC
0x18000b8e5  test    edi, edi
0x18000b8e7  setnz   r9b
0x18000b8eb  mov     edx, 0Dh
0x18000b8f0  mov     r8, r14
0x18000b8f3  mov     rcx, [rcx+10h]
0x18000b8f7  call    WPP_SF_c
0x18000b8fc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000b903  mov     ecx, 768h; unsigned __int64
0x18000b908  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000b90d  mov     [rsp+58h+arg_8], rax
0x18000b912  test    rax, rax
0x18000b915  jz      short loc_18000B924
0x18000b917  mov     rcx, rax; this
0x18000b91a  call    ??0TetheringService@@QEAA@XZ; TetheringService::TetheringService(void)
0x18000b91f  mov     rbx, rax
0x18000b922  jmp     short loc_18000B927
0x18000b924  mov     rbx, rsi
0x18000b927  test    rbx, rbx
0x18000b92a  jnz     short loc_18000B965
0x18000b92c  mov     ebx, 0Eh
0x18000b931  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b938  cmp     rcx, rbp
0x18000b93b  jz      loc_18000BAF0
0x18000b941  test    byte ptr [rcx+1Ch], 8
0x18000b945  jz      loc_18000B9CF
0x18000b94b  mov     edx, ebx
0x18000b94d  mov     r9d, ebx
0x18000b950  mov     r8, r14
0x18000b953  mov     rcx, [rcx+10h]
0x18000b957  call    WPP_SF_d
0x18000b95c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b963  jmp     short loc_18000B9CF
0x18000b965  mov     rcx, qword ptr cs:?g_pTetheringSessionId@@3PEAU_GUID@@EA.Data4; _GUID * g_pTetheringSessionId ...
0x18000b96c  test    rcx, rcx
0x18000b96f  jz      short loc_18000B97D
0x18000b971  mov     rax, [rcx]
0x18000b974  mov     rax, [rax+10h]
0x18000b978  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b97d  mov     qword ptr cs:?g_pTetheringSessionId@@3PEAU_GUID@@EA.Data4, rbx; _GUID * g_pTetheringSessionId ...
0x18000b984  mov     rcx, rbx; this
0x18000b987  call    ?Initialize@TetheringService@@QEAAJXZ; TetheringService::Initialize(void)
0x18000b98c  mov     ebx, eax
0x18000b98e  test    edi, edi
0x18000b990  jz      short loc_18000B99E
0x18000b992  mov     rcx, qword ptr cs:?g_pTetheringSessionId@@3PEAU_GUID@@EA.Data4; this
0x18000b999  call    ?InitializeBluetooth@TetheringService@@QEAAJXZ; TetheringService::InitializeBluetooth(void)
0x18000b99e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b9a5  cmp     rcx, rbp
0x18000b9a8  jz      short loc_18000B9CB
0x18000b9aa  test    byte ptr [rcx+1Ch], 8
0x18000b9ae  jz      short loc_18000B9CB
0x18000b9b0  mov     edx, 0Fh
0x18000b9b5  mov     r9d, ebx
0x18000b9b8  mov     r8, r14
0x18000b9bb  mov     rcx, [rcx+10h]
0x18000b9bf  call    WPP_SF_d
0x18000b9c4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b9cb  test    ebx, ebx
0x18000b9cd  jz      short loc_18000B9EF
0x18000b9cf  cmp     rcx, rbp
0x18000b9d2  jz      loc_18000BAF0
0x18000b9d8  test    byte ptr [rcx+1Ch], 1
0x18000b9dc  jz      loc_18000BAF0
0x18000b9e2  mov     edx, 25h ; '%'
0x18000b9e7  mov     r9d, ebx
0x18000b9ea  jmp     loc_18000BAE4
0x18000b9ef  xor     r9d, r9d; lpName
0x18000b9f2  xor     r8d, r8d; bInitialState
0x18000b9f5  lea     edx, [r9+1]; bManualReset
0x18000b9f9  xor     ecx, ecx; lpEventAttributes
0x18000b9fb  call    cs:__imp_CreateEventW
0x18000ba01  mov     cs:?g_StopHandles@@3U_GLOBAL_STOP_HANDLES@@A, rax; _GLOBAL_STOP_HANDLES g_StopHandles
0x18000ba08  test    rax, rax
0x18000ba0b  jnz     short loc_18000BA39
0x18000ba0d  call    cs:__imp_GetLastError
0x18000ba13  mov     ebx, eax
0x18000ba15  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ba1c  cmp     rcx, rbp
0x18000ba1f  jz      loc_18000BAF0
0x18000ba25  test    byte ptr [rcx+1Ch], 1
0x18000ba29  jz      loc_18000BAF0
0x18000ba2f  mov     edx, 26h ; '&'
0x18000ba34  jmp     loc_18000BAE1
0x18000ba39  xor     r9d, r9d; lpName
0x18000ba3c  xor     r8d, r8d; bInitialState
0x18000ba3f  xor     edx, edx; bManualReset
0x18000ba41  xor     ecx, ecx; lpEventAttributes
0x18000ba43  call    cs:__imp_CreateEventW
0x18000ba49  mov     cs:hEvent, rax
0x18000ba50  test    rax, rax
0x18000ba53  jnz     short loc_18000BA7A
0x18000ba55  call    cs:__imp_GetLastError
0x18000ba5b  mov     ebx, eax
0x18000ba5d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ba64  cmp     rcx, rbp
0x18000ba67  jz      loc_18000BAF0
0x18000ba6d  test    byte ptr [rcx+1Ch], 1
0x18000ba71  jz      short loc_18000BAF0
0x18000ba73  mov     edx, 27h ; '''
0x18000ba78  jmp     short loc_18000BAE1
0x18000ba7a  xor     edx, edx; unsigned int
0x18000ba7c  lea     ecx, [rdx+2]; unsigned int
0x18000ba7f  call    ?SetTetheringServiceStatus@@YAXKK@Z; SetTetheringServiceStatus(ulong,ulong)
0x18000ba84  mov     rax, cs:?g_TetheringSvcHostGlobalData@@3PEBU_SVCHOST_GLOBAL_DATA@@EB; _SVCHOST_GLOBAL_DATA const * const g_TetheringSvcHostGlobalData
0x18000ba8b  mov     dword ptr [rsp+58h+var_30], 18h
0x18000ba93  mov     [rsp+58h+var_38], rsi
0x18000ba98  lea     r9, ?InitiateStopTetheringService@@YAXPEAXE@Z; InitiateStopTetheringService(void *,uchar)
0x18000ba9f  mov     r8, cs:?g_StopHandles@@3U_GLOBAL_STOP_HANDLES@@A; _GLOBAL_STOP_HANDLES g_StopHandles
0x18000baa6  lea     rdx, ServiceName; "icssvc"
0x18000baad  lea     rcx, WaitHandle
0x18000bab4  mov     rax, [rax+0C0h]
0x18000babb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bac0  mov     ebx, eax
0x18000bac2  test    eax, eax
0x18000bac4  jz      loc_18000BB98
0x18000baca  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bad1  cmp     rcx, rbp
0x18000bad4  jz      short loc_18000BAF0
0x18000bad6  test    byte ptr [rcx+1Ch], 1
0x18000bada  jz      short loc_18000BAF0
0x18000badc  mov     edx, 28h ; '('
0x18000bae1  mov     r9d, eax
0x18000bae4  mov     r8, r14
0x18000bae7  mov     rcx, [rcx+10h]
0x18000baeb  call    WPP_SF_d
0x18000baf0  mov     rcx, cs:?g_StopHandles@@3U_GLOBAL_STOP_HANDLES@@A; hObject
0x18000baf7  test    rcx, rcx
0x18000bafa  jz      short loc_18000BB09
0x18000bafc  call    cs:__imp_CloseHandle
0x18000bb02  mov     cs:?g_StopHandles@@3U_GLOBAL_STOP_HANDLES@@A, rsi; _GLOBAL_STOP_HANDLES g_StopHandles
0x18000bb09  mov     rcx, cs:WaitHandle; WaitHandle
0x18000bb10  test    rcx, rcx
0x18000bb13  jz      short loc_18000BB24
0x18000bb15  xor     edx, edx; CompletionEvent
0x18000bb17  call    cs:__imp_UnregisterWaitEx
0x18000bb1d  mov     cs:WaitHandle, rsi
0x18000bb24  mov     rcx, cs:hEvent; hObject
0x18000bb2b  test    rcx, rcx
0x18000bb2e  jz      short loc_18000BB3D
0x18000bb30  call    cs:__imp_CloseHandle
0x18000bb36  mov     cs:hEvent, rsi
0x18000bb3d  call    ?UninitializeTetheringSvc@@YAXXZ; UninitializeTetheringSvc(void)
0x18000bb42  mov     cs:?g_ErrorCode@@3KA, ebx; ulong g_ErrorCode
0x18000bb48  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bb4f  cmp     rcx, rbp
0x18000bb52  jz      short loc_18000BB91
0x18000bb54  test    byte ptr [rcx+1Ch], 1
0x18000bb58  jz      short loc_18000BB75
0x18000bb5a  mov     edx, 2Dh ; '-'
0x18000bb5f  mov     r9d, ebx
0x18000bb62  mov     r8, r14
0x18000bb65  mov     rcx, [rcx+10h]
0x18000bb69  call    WPP_SF_d
0x18000bb6e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bb75  cmp     rcx, rbp
0x18000bb78  jz      short loc_18000BB91
0x18000bb7a  test    byte ptr [rcx+1Ch], 8
0x18000bb7e  jz      short loc_18000BB91
0x18000bb80  mov     edx, 2Eh ; '.'
0x18000bb85  mov     r8, r14
0x18000bb88  mov     rcx, [rcx+10h]
0x18000bb8c  call    WPP_SF_
0x18000bb91  mov     eax, ebx
0x18000bb93  jmp     loc_18000BD26
0x18000bb98  call    ?TetheringSvcRpcServerInitialize@@YAKXZ; TetheringSvcRpcServerInitialize(void)
0x18000bb9d  mov     cs:?g_ServiceStatus@@3U_SERVICE_STATUS@@A.dwControlsAccepted, 81h; _SERVICE_STATUS g_ServiceStatus ...
0x18000bba7  xor     edx, edx; unsigned int
0x18000bba9  lea     ecx, [rdx+4]; unsigned int
0x18000bbac  call    ?SetTetheringServiceStatus@@YAXKK@Z; SetTetheringServiceStatus(ulong,ulong)
0x18000bbb1  mov     rcx, cs:hEvent; hEvent
0x18000bbb8  call    cs:__imp_SetEvent
0x18000bbbe  mov     cs:?g_Environment@@3U_TP_CALLBACK_ENVIRON_V3@@A.Version, 3; _TP_CALLBACK_ENVIRON_V3 g_Environment ...
0x18000bbc8  mov     cs:?g_Environment@@3U_TP_CALLBACK_ENVIRON_V3@@A.Pool, rsi; _TP_CALLBACK_ENVIRON_V3 g_Environment ...
0x18000bbcf  mov     cs:?g_Environment@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroup, rsi; _TP_CALLBACK_ENVIRON_V3 g_Environment ...
0x18000bbd6  mov     cs:?g_Environment@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroupCancelCallback, rsi; _TP_CALLBACK_ENVIRON_V3 g_Environment ...
0x18000bbdd  xorps   xmm0, xmm0
0x18000bbe0  movdqa  xmmword ptr cs:?g_Environment@@3U_TP_CALLBACK_ENVIRON_V3@@A.RaceDll, xmm0; _TP_CALLBACK_ENVIRON_V3 g_Environment ...
0x18000bbe8  mov     cs:?g_Environment@@3U_TP_CALLBACK_ENVIRON_V3@@A.FinalizationCallback, rsi; _TP_CALLBACK_ENVIRON_V3 g_Environment ...
0x18000bbef  mov     dword ptr cs:?g_Environment@@3U_TP_CALLBACK_ENVIRON_V3@@A.u, esi; _TP_CALLBACK_ENVIRON_V3 g_Environment ...
0x18000bbf5  mov     cs:?g_Environment@@3U_TP_CALLBACK_ENVIRON_V3@@A.CallbackPriority, 1; _TP_CALLBACK_ENVIRON_V3 g_Environment ...
0x18000bbff  mov     cs:?g_Environment@@3U_TP_CALLBACK_ENVIRON_V3@@A.Size, 48h ; 'H'; _TP_CALLBACK_ENVIRON_V3 g_Environment ...
0x18000bc09  lea     r8, ?g_Environment@@3U_TP_CALLBACK_ENVIRON_V3@@A; pcbe
0x18000bc10  xor     edx, edx; pv
0x18000bc12  lea     rcx, ?OutOfBandEntitlementCheckBackgroundProcessing@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18000bc19  call    cs:__imp_CreateThreadpoolWork
0x18000bc1f  mov     cs:?g_ProcessOutOfBandEntitelmentCheckBackgroundWork@@3PEAU_TP_WORK@@EA, rax; _TP_WORK * g_ProcessOutOfBandEntitelmentCheckBackgroundWork
0x18000bc26  test    rax, rax
0x18000bc29  jnz     short loc_18000BC5E
0x18000bc2b  mov     rax, cs:WPP_GLOBAL_Control
0x18000bc32  cmp     rax, rbp
0x18000bc35  jz      short loc_18000BC5E
0x18000bc37  test    byte ptr [rax+1Ch], 2
0x18000bc3b  jz      short loc_18000BC5E
0x18000bc3d  call    cs:__imp_GetLastError
0x18000bc43  mov     edx, 29h ; ')'
0x18000bc48  mov     r9d, eax
0x18000bc4b  mov     r8, r14
0x18000bc4e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bc55  mov     rcx, [rcx+10h]
0x18000bc59  call    WPP_SF_d
0x18000bc5e  mov     [rsp+58h+var_20], 1
0x18000bc66  mov     [rsp+58h+var_28], esi
0x18000bc6a  mov     [rsp+58h+var_30], rsi
0x18000bc6f  mov     [rsp+58h+var_38], rsi
0x18000bc74  lea     r9, HandleWnfSharingChangedCallback
0x18000bc7b  xor     r8d, r8d
0x18000bc7e  mov     rdx, cs:WNF_SHR_SHARING_CHANGED
0x18000bc85  lea     rcx, ?g_pWnfSharingChanged@@3PEAU_WNF_USER_SUBSCRIPTION@@EA; _WNF_USER_SUBSCRIPTION * g_pWnfSharingChanged
0x18000bc8c  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x18000bc92  test    eax, eax
0x18000bc94  jns     short loc_18000BCDE
0x18000bc96  mov     cs:?g_pWnfSharingChanged@@3PEAU_WNF_USER_SUBSCRIPTION@@EA, rsi; _WNF_USER_SUBSCRIPTION * g_pWnfSharingChanged
0x18000bc9d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bca4  cmp     rcx, rbp
0x18000bca7  jz      short loc_18000BD24
0x18000bca9  test    byte ptr [rcx+1Ch], 2
0x18000bcad  jz      short loc_18000BCE5
0x18000bcaf  mov     ecx, eax; Status
0x18000bcb1  call    cs:__imp_RtlNtStatusToDosError
0x18000bcb7  test    eax, eax
0x18000bcb9  jle     short loc_18000BCC3
0x18000bcbb  movzx   eax, ax
0x18000bcbe  or      eax, 80070000h
0x18000bcc3  mov     edx, 2Ah ; '*'
0x18000bcc8  mov     r9d, eax
0x18000bccb  mov     r8, r14
0x18000bcce  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bcd5  mov     rcx, [rcx+10h]
0x18000bcd9  call    WPP_SF_d
0x18000bcde  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bce5  cmp     rcx, rbp
0x18000bce8  jz      short loc_18000BD24
0x18000bcea  test    byte ptr [rcx+1Ch], 4
0x18000bcee  jz      short loc_18000BD08
0x18000bcf0  mov     edx, 2Bh ; '+'
0x18000bcf5  mov     r8, r14
0x18000bcf8  mov     rcx, [rcx+10h]
0x18000bcfc  call    WPP_SF_
0x18000bd01  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bd08  cmp     rcx, rbp
0x18000bd0b  jz      short loc_18000BD24
0x18000bd0d  test    byte ptr [rcx+1Ch], 8
0x18000bd11  jz      short loc_18000BD24
0x18000bd13  mov     edx, 2Ch ; ','
0x18000bd18  mov     r8, r14
0x18000bd1b  mov     rcx, [rcx+10h]
0x18000bd1f  call    WPP_SF_
0x18000bd24  xor     eax, eax
0x18000bd26  mov     rbx, [rsp+58h+arg_0]
0x18000bd2b  mov     rbp, [rsp+58h+arg_10]
0x18000bd30  add     rsp, 40h
0x18000bd34  pop     r14
0x18000bd36  pop     rdi
0x18000bd37  pop     rsi
0x18000bd38  retn
```
