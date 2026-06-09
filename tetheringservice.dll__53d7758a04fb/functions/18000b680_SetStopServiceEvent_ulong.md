# SetStopServiceEvent(ulong)

- ea: `0x18000b680`
- end: `0x18000b76e`
- name: `?SetStopServiceEvent@@YAXK@Z`
- size: `238`
- prototype: `void __fastcall()`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000b280`
- `0x18001c6a0`

## callees

- `0x18000b680`
- `0x18000b774`
- `0x18000bf4c`
- `0x18000bf74`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000b6f3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000b6f3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000b73b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000b73b`

## pseudocode

```c
void __fastcall SetStopServiceEvent()
{
  TetheringServiceTelemetry *v0; // rcx
  __int64 v1; // rdx

  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_44e4735379a936cf4f13ce357ad19005_Traceguids, 0);
  }
  if ( _InterlockedCompareExchange(&g_StopServiceEventSet, 1, 0) )
  {
    v0 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      v1 = 23;
LABEL_14:
      WPP_SF_(*((_QWORD *)v0 + 2), v1, &WPP_44e4735379a936cf4f13ce357ad19005_Traceguids);
    }
  }
  else
  {
    WaitForSingleObject(hEvent, 0xFFFFFFFF);
    if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_44e4735379a936cf4f13ce357ad19005_Traceguids);
    }
    g_ServiceStatus.dwControlsAccepted = 1024;
    SetTetheringServiceStatus(3u, 0);
    SetEvent(g_StopHandles);
    v0 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      v1 = 25;
      goto LABEL_14;
    }
  }
}

```

## disassembly

```asm
0x18000b680  push    rbx
0x18000b682  sub     rsp, 20h
0x18000b686  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b68d  lea     rbx, WPP_GLOBAL_Control
0x18000b694  cmp     rcx, rbx
0x18000b697  jz      short loc_18000B6B7
0x18000b699  test    byte ptr [rcx+1Ch], 8
0x18000b69d  jz      short loc_18000B6B7
0x18000b69f  mov     rcx, [rcx+10h]
0x18000b6a3  lea     r8, WPP_44e4735379a936cf4f13ce357ad19005_Traceguids
0x18000b6aa  mov     edx, 16h
0x18000b6af  xor     r9d, r9d
0x18000b6b2  call    WPP_SF_d
0x18000b6b7  mov     ecx, 1
0x18000b6bc  xor     eax, eax
0x18000b6be  lock cmpxchg cs:?g_StopServiceEventSet@@3HA, ecx; int g_StopServiceEventSet
0x18000b6c6  jz      short loc_18000B6E9
0x18000b6c8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b6cf  cmp     rcx, rbx
0x18000b6d2  jz      loc_18000B768
0x18000b6d8  test    byte ptr [rcx+1Ch], 8
0x18000b6dc  jz      loc_18000B768
0x18000b6e2  mov     edx, 17h
0x18000b6e7  jmp     short loc_18000B758
0x18000b6e9  mov     rcx, cs:hEvent; hHandle
0x18000b6f0  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000b6f3  call    cs:__imp_WaitForSingleObject
0x18000b6f9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b700  cmp     rcx, rbx
0x18000b703  jz      short loc_18000B720
0x18000b705  test    byte ptr [rcx+1Ch], 4
0x18000b709  jz      short loc_18000B720
0x18000b70b  mov     rcx, [rcx+10h]
0x18000b70f  lea     r8, WPP_44e4735379a936cf4f13ce357ad19005_Traceguids
0x18000b716  mov     edx, 18h
0x18000b71b  call    WPP_SF_
0x18000b720  xor     edx, edx; unsigned int
0x18000b722  mov     cs:?g_ServiceStatus@@3U_SERVICE_STATUS@@A.dwControlsAccepted, 400h; _SERVICE_STATUS g_ServiceStatus ...
0x18000b72c  lea     ecx, [rdx+3]; unsigned int
0x18000b72f  call    ?SetTetheringServiceStatus@@YAXKK@Z; SetTetheringServiceStatus(ulong,ulong)
0x18000b734  mov     rcx, cs:?g_StopHandles@@3U_GLOBAL_STOP_HANDLES@@A; hEvent
0x18000b73b  call    cs:__imp_SetEvent
0x18000b741  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b748  cmp     rcx, rbx
0x18000b74b  jz      short loc_18000B768
0x18000b74d  test    byte ptr [rcx+1Ch], 8
0x18000b751  jz      short loc_18000B768
0x18000b753  mov     edx, 19h
0x18000b758  mov     rcx, [rcx+10h]
0x18000b75c  lea     r8, WPP_44e4735379a936cf4f13ce357ad19005_Traceguids
0x18000b763  call    WPP_SF_
0x18000b768  add     rsp, 20h
0x18000b76c  pop     rbx
0x18000b76d  retn
```
