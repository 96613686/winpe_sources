# InitiateStopTetheringService(void *,uchar)

- ea: `0x18000ae30`
- end: `0x18000b0de`
- name: `?InitiateStopTetheringService@@YAXPEAXE@Z`
- size: `686`
- prototype: `void __fastcall(void *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18000ae30`
- `0x18000b774`
- `0x18000bd50`
- `0x18000bf4c`
- `0x18000c1c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b07c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b07c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ae92`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ae92`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ae78`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ae78`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000aefd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000aefd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18000aef0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18000aef0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000afc0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b000`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000afc0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b000`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18000af80`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18000af80`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000aed0`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000aed0`

## pseudocode

```c
void __fastcall InitiateStopTetheringService(void *a1)
{
  struct _WNF_USER_SUBSCRIPTION *v1; // rax
  TetheringServiceTelemetry *v2; // rcx
  TetheringServiceTelemetry *v3; // rcx

  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_44e4735379a936cf4f13ce357ad19005_Traceguids);
  }
  EnterCriticalSection(&g_csSvcLock);
  g_fSvcShuttingDown = 1;
  LeaveCriticalSection(&g_csSvcLock);
  v1 = g_pWnfSharingChanged;
  if ( g_pWnfSharingChanged )
  {
    if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_44e4735379a936cf4f13ce357ad19005_Traceguids);
      v1 = g_pWnfSharingChanged;
    }
    RtlUnsubscribeWnfNotificationWaitForCompletion(v1);
    g_pWnfSharingChanged = 0;
  }
  if ( g_ProcessOutOfBandEntitelmentCheckBackgroundWork )
  {
    WaitForThreadpoolWorkCallbacks(g_ProcessOutOfBandEntitelmentCheckBackgroundWork, 1);
    CloseThreadpoolWork(g_ProcessOutOfBandEntitelmentCheckBackgroundWork);
    g_ProcessOutOfBandEntitelmentCheckBackgroundWork = 0;
  }
  if ( _InterlockedCompareExchange(&g_Stopping, 1, 0) )
  {
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_44e4735379a936cf4f13ce357ad19005_Traceguids);
        v2 = WPP_GLOBAL_Control;
      }
      if ( v2 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)v2 + 2), 29, &WPP_44e4735379a936cf4f13ce357ad19005_Traceguids);
    }
  }
  else
  {
    if ( WaitHandle )
    {
      UnregisterWaitEx(WaitHandle, 0);
      WaitHandle = 0;
      if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_44e4735379a936cf4f13ce357ad19005_Traceguids);
      }
    }
    if ( g_StopHandles )
    {
      CloseHandle(g_StopHandles);
      g_StopHandles = 0;
      if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_44e4735379a936cf4f13ce357ad19005_Traceguids);
      }
    }
    if ( hEvent )
    {
      CloseHandle(hEvent);
      hEvent = 0;
      if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_44e4735379a936cf4f13ce357ad19005_Traceguids);
      }
    }
    UninitializeTetheringSvc();
    if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_44e4735379a936cf4f13ce357ad19005_Traceguids);
    }
    g_TetheringSvcHostGlobalData = 0;
    SetTetheringServiceStatus(1u, g_ErrorCode);
    DeleteCriticalSection(&g_csSvcLock);
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_44e4735379a936cf4f13ce357ad19005_Traceguids);
        v3 = WPP_GLOBAL_Control;
      }
      if ( v3 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)v3 + 2), 35, &WPP_44e4735379a936cf4f13ce357ad19005_Traceguids);
    }
    WppCleanupUm();
  }
}

```

## disassembly

```asm
0x18000ae30  mov     [rsp+arg_0], rsi
0x18000ae35  mov     [rsp+arg_8], rdi
0x18000ae3a  push    r15
0x18000ae3c  sub     rsp, 20h
0x18000ae40  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ae47  lea     rdi, WPP_GLOBAL_Control
0x18000ae4e  lea     rsi, WPP_44e4735379a936cf4f13ce357ad19005_Traceguids
0x18000ae55  cmp     rcx, rdi
0x18000ae58  jz      short loc_18000AE71
0x18000ae5a  test    byte ptr [rcx+1Ch], 8
0x18000ae5e  jz      short loc_18000AE71
0x18000ae60  mov     rcx, [rcx+10h]
0x18000ae64  mov     edx, 1Ah
0x18000ae69  mov     r8, rsi
0x18000ae6c  call    WPP_SF_
0x18000ae71  lea     rcx, ?g_csSvcLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000ae78  call    cs:__imp_EnterCriticalSection
0x18000ae7e  mov     r15d, 1
0x18000ae84  lea     rcx, ?g_csSvcLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000ae8b  mov     cs:?g_fSvcShuttingDown@@3_NA, r15b; bool g_fSvcShuttingDown
0x18000ae92  call    cs:__imp_LeaveCriticalSection
0x18000ae98  mov     rax, cs:?g_pWnfSharingChanged@@3PEAU_WNF_USER_SUBSCRIPTION@@EA; _WNF_USER_SUBSCRIPTION * g_pWnfSharingChanged
0x18000ae9f  test    rax, rax
0x18000aea2  jz      short loc_18000AEE1
0x18000aea4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aeab  cmp     rcx, rdi
0x18000aeae  jz      short loc_18000AECD
0x18000aeb0  test    byte ptr [rcx+1Ch], 4
0x18000aeb4  jz      short loc_18000AECD
0x18000aeb6  mov     rcx, [rcx+10h]
0x18000aeba  lea     edx, [r15+1Ah]
0x18000aebe  mov     r8, rsi
0x18000aec1  call    WPP_SF_
0x18000aec6  mov     rax, cs:?g_pWnfSharingChanged@@3PEAU_WNF_USER_SUBSCRIPTION@@EA; _WNF_USER_SUBSCRIPTION * g_pWnfSharingChanged
0x18000aecd  mov     rcx, rax
0x18000aed0  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18000aed6  mov     cs:?g_pWnfSharingChanged@@3PEAU_WNF_USER_SUBSCRIPTION@@EA, 0; _WNF_USER_SUBSCRIPTION * g_pWnfSharingChanged
0x18000aee1  mov     rcx, cs:?g_ProcessOutOfBandEntitelmentCheckBackgroundWork@@3PEAU_TP_WORK@@EA; pwk
0x18000aee8  test    rcx, rcx
0x18000aeeb  jz      short loc_18000AF0E
0x18000aeed  mov     edx, r15d; fCancelPendingCallbacks
0x18000aef0  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18000aef6  mov     rcx, cs:?g_ProcessOutOfBandEntitelmentCheckBackgroundWork@@3PEAU_TP_WORK@@EA; pwk
0x18000aefd  call    cs:__imp_CloseThreadpoolWork
0x18000af03  mov     cs:?g_ProcessOutOfBandEntitelmentCheckBackgroundWork@@3PEAU_TP_WORK@@EA, 0; _TP_WORK * g_ProcessOutOfBandEntitelmentCheckBackgroundWork
0x18000af0e  xor     eax, eax
0x18000af10  lock cmpxchg cs:?g_Stopping@@3HA, r15d; int g_Stopping
0x18000af19  jz      short loc_18000AF72
0x18000af1b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000af22  cmp     rcx, rdi
0x18000af25  jz      loc_18000B0CD
0x18000af2b  test    byte ptr [rcx+1Ch], 4
0x18000af2f  jz      short loc_18000AF49
0x18000af31  mov     rcx, [rcx+10h]
0x18000af35  mov     edx, 1Ch
0x18000af3a  mov     r8, rsi
0x18000af3d  call    WPP_SF_
0x18000af42  mov     rcx, cs:WPP_GLOBAL_Control
0x18000af49  cmp     rcx, rdi
0x18000af4c  jz      loc_18000B0CD
0x18000af52  test    byte ptr [rcx+1Ch], 8
0x18000af56  jz      loc_18000B0CD
0x18000af5c  mov     rcx, [rcx+10h]
0x18000af60  mov     edx, 1Dh
0x18000af65  mov     r8, rsi
0x18000af68  call    WPP_SF_
0x18000af6d  jmp     loc_18000B0CD
0x18000af72  mov     rcx, cs:WaitHandle; WaitHandle
0x18000af79  test    rcx, rcx
0x18000af7c  jz      short loc_18000AFB4
0x18000af7e  xor     edx, edx; CompletionEvent
0x18000af80  call    cs:__imp_UnregisterWaitEx
0x18000af86  mov     cs:WaitHandle, 0
0x18000af91  mov     rcx, cs:WPP_GLOBAL_Control
0x18000af98  cmp     rcx, rdi
0x18000af9b  jz      short loc_18000AFB4
0x18000af9d  test    byte ptr [rcx+1Ch], 4
0x18000afa1  jz      short loc_18000AFB4
0x18000afa3  mov     rcx, [rcx+10h]
0x18000afa7  mov     edx, 1Eh
0x18000afac  mov     r8, rsi
0x18000afaf  call    WPP_SF_
0x18000afb4  mov     rcx, cs:?g_StopHandles@@3U_GLOBAL_STOP_HANDLES@@A; hObject
0x18000afbb  test    rcx, rcx
0x18000afbe  jz      short loc_18000AFF4
0x18000afc0  call    cs:__imp_CloseHandle
0x18000afc6  mov     cs:?g_StopHandles@@3U_GLOBAL_STOP_HANDLES@@A, 0; _GLOBAL_STOP_HANDLES g_StopHandles
0x18000afd1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000afd8  cmp     rcx, rdi
0x18000afdb  jz      short loc_18000AFF4
0x18000afdd  test    byte ptr [rcx+1Ch], 4
0x18000afe1  jz      short loc_18000AFF4
0x18000afe3  mov     rcx, [rcx+10h]
0x18000afe7  mov     edx, 1Fh
0x18000afec  mov     r8, rsi
0x18000afef  call    WPP_SF_
0x18000aff4  mov     rcx, cs:hEvent; hObject
0x18000affb  test    rcx, rcx
0x18000affe  jz      short loc_18000B034
0x18000b000  call    cs:__imp_CloseHandle
0x18000b006  mov     cs:hEvent, 0
0x18000b011  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b018  cmp     rcx, rdi
0x18000b01b  jz      short loc_18000B034
0x18000b01d  test    byte ptr [rcx+1Ch], 4
0x18000b021  jz      short loc_18000B034
0x18000b023  mov     rcx, [rcx+10h]
0x18000b027  mov     edx, 20h ; ' '
0x18000b02c  mov     r8, rsi
0x18000b02f  call    WPP_SF_
0x18000b034  call    ?UninitializeTetheringSvc@@YAXXZ; UninitializeTetheringSvc(void)
0x18000b039  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b040  cmp     rcx, rdi
0x18000b043  jz      short loc_18000B05C
0x18000b045  test    byte ptr [rcx+1Ch], 4
0x18000b049  jz      short loc_18000B05C
0x18000b04b  mov     rcx, [rcx+10h]
0x18000b04f  mov     edx, 21h ; '!'
0x18000b054  mov     r8, rsi
0x18000b057  call    WPP_SF_
0x18000b05c  mov     edx, cs:?g_ErrorCode@@3KA; unsigned int
0x18000b062  mov     ecx, r15d; unsigned int
0x18000b065  mov     cs:?g_TetheringSvcHostGlobalData@@3PEBU_SVCHOST_GLOBAL_DATA@@EB, 0; _SVCHOST_GLOBAL_DATA const * const g_TetheringSvcHostGlobalData
0x18000b070  call    ?SetTetheringServiceStatus@@YAXKK@Z; SetTetheringServiceStatus(ulong,ulong)
0x18000b075  lea     rcx, ?g_csSvcLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000b07c  call    cs:__imp_DeleteCriticalSection
0x18000b082  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b089  cmp     rcx, rdi
0x18000b08c  jz      short loc_18000B0C8
0x18000b08e  test    byte ptr [rcx+1Ch], 8
0x18000b092  jz      short loc_18000B0AC
0x18000b094  mov     rcx, [rcx+10h]
0x18000b098  mov     edx, 22h ; '"'
0x18000b09d  mov     r8, rsi
0x18000b0a0  call    WPP_SF_
0x18000b0a5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b0ac  cmp     rcx, rdi
0x18000b0af  jz      short loc_18000B0C8
0x18000b0b1  test    byte ptr [rcx+1Ch], 8
0x18000b0b5  jz      short loc_18000B0C8
0x18000b0b7  mov     rcx, [rcx+10h]
0x18000b0bb  mov     edx, 23h ; '#'
0x18000b0c0  mov     r8, rsi
0x18000b0c3  call    WPP_SF_
0x18000b0c8  call    WppCleanupUm
0x18000b0cd  mov     rsi, [rsp+28h+arg_0]
0x18000b0d2  mov     rdi, [rsp+28h+arg_8]
0x18000b0d7  add     rsp, 20h
0x18000b0db  pop     r15
0x18000b0dd  retn
```
