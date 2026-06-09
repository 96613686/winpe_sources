# ServiceMain(ulong,ushort const * *)

- ea: `0x18000b370`
- end: `0x18000b679`
- name: `?ServiceMain@@YAXKPEAPEBG@Z`
- size: `777`
- prototype: `void __fastcall(__int64, const unsigned __int16 **)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, service_task`

## callees

- `0x180003088`
- `0x18000a040`
- `0x18000ac64`
- `0x18000b370`
- `0x18000b774`
- `0x18000b888`
- `0x18000bf4c`
- `0x18000bf74`
- `0x18000c1c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000b47c`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000b47c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b61d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b61d`
- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x18000b467`
- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x18000b467`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000b3d6`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000b3d6`
- `ntdll!RtlPublishWnfStateData` at `0x18000b54c`
- `ntdll!RtlPublishWnfStateData` at `0x18000b54c`

## pseudocode

```c
void __fastcall ServiceMain(__int64 a1, const unsigned __int16 **a2)
{
  ULONG64 *v2; // rbx
  const GUID **v3; // rdi
  const GUID *v4; // r8
  TetheringServiceTelemetry *v5; // rcx
  int v6; // ebx
  int v7; // eax
  TetheringServiceTelemetry *v8; // rcx
  __int64 v9; // rdx
  TetheringServiceTelemetry *v10; // rcx
  const struct wil::FailureInfo *v11; // rdx
  int v12; // [rsp+40h] [rbp-79h] BYREF
  struct _TRACE_GUID_REGISTRATION TraceGuidReg; // [rsp+48h] [rbp-71h] BYREF
  _BYTE v14[160]; // [rsp+60h] [rbp-59h] BYREF
  int v15; // [rsp+130h] [rbp+77h] BYREF
  int v16; // [rsp+138h] [rbp+7Fh] BYREF

  g_ServiceStatus.dwServiceType = 32;
  g_StopServiceEventSet = 0;
  g_Stopping = 0;
  g_ErrorCode = 0;
  g_fSvcShuttingDown = 0;
  *(_OWORD *)&g_ServiceStatus.dwWin32ExitCode = 0;
  *(_QWORD *)&g_ServiceStatus.dwCurrentState = 2;
  hServiceStatus = RegisterServiceCtrlHandlerExW(L"icssvc", (LPHANDLER_FUNCTION_EX)ServiceHandler, 0);
  if ( !hServiceStatus )
  {
    *(_OWORD *)&g_ServiceStatus.dwServiceType = 0;
    *(_OWORD *)&g_ServiceStatus.dwWin32ExitCode = 0;
    return;
  }
  qword_180041DF8 = 0;
  v2 = (ULONG64 *)&WPP_MAIN_CB;
  WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_TetheringService;
  WPP_GLOBAL_Control = (TetheringServiceTelemetry *)&WPP_MAIN_CB;
  v3 = (const GUID **)&WPP_REGISTRATION_GUIDS;
  WPP_MAIN_CB = 0;
  qword_180041E00 = 1;
  do
  {
    v4 = *v3;
    TraceGuidReg.Guid = v4;
    ++v3;
    TraceGuidReg.RegHandle = 0;
    v2[4] = (ULONG64)v4;
    RegisterTraceGuidsW(WppControlCallback, v2, v4, 1u, &TraceGuidReg, 0, 0, v2 + 1);
    v2 = (ULONG64 *)*v2;
  }
  while ( v2 );
  InitializeCriticalSection(&g_csSvcLock);
  if ( wil::details::g_pfnLoggingCallback && (char *)wil::details::g_pfnLoggingCallback != (char *)ResultLoggingCallback )
  {
    memset_0(v14, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v14, v11);
  }
  wil::details::g_pfnLoggingCallback = (__int64 (__fastcall *)(_QWORD))ResultLoggingCallback;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, &WPP_44e4735379a936cf4f13ce357ad19005_Traceguids);
  }
  v12 = 0;
  v16 = 0;
  LOBYTE(v15) = 0;
  v6 = 0;
  v7 = wil::wnf_query_nothrow<unsigned long>(v5, &v15, &v16, &v12);
  if ( v7 >= 0 )
  {
    if ( !(_BYTE)v15 || v16 != 1 )
      goto LABEL_23;
    if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_44e4735379a936cf4f13ce357ad19005_Traceguids);
    }
    v6 = 1;
    v15 = 0;
    v7 = RtlPublishWnfStateData(WNF_TETH_AUTOSTART_BLUETOOTH, 0, &v15, 4, 0) | 0x10000000;
    if ( v7 >= 0 )
      goto LABEL_23;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_23;
    }
    v9 = 58;
    goto LABEL_22;
  }
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v9 = 59;
LABEL_22:
    WPP_SF_d(*((_QWORD *)v8 + 2), v9, &WPP_44e4735379a936cf4f13ce357ad19005_Traceguids, (unsigned int)v7);
  }
LABEL_23:
  if ( StartTetheringService(v6) )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, &WPP_44e4735379a936cf4f13ce357ad19005_Traceguids);
        v10 = WPP_GLOBAL_Control;
      }
      if ( v10 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)v10 + 2), 62, &WPP_44e4735379a936cf4f13ce357ad19005_Traceguids);
    }
    WppCleanupUm();
    DeleteCriticalSection(&g_csSvcLock);
    SetTetheringServiceStatus(1u, g_ErrorCode);
  }
  else if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, &WPP_44e4735379a936cf4f13ce357ad19005_Traceguids);
  }
}

```

## disassembly

```asm
0x18000b370  mov     [rsp-8+arg_0], rbx
0x18000b375  mov     [rsp-8+arg_8], rsi
0x18000b37a  push    rbp
0x18000b37b  push    rdi
0x18000b37c  push    r14
0x18000b37e  lea     rbp, [rsp-47h]
0x18000b383  sub     rsp, 100h
0x18000b38a  xor     esi, esi
0x18000b38c  mov     cs:?g_ServiceStatus@@3U_SERVICE_STATUS@@A.dwServiceType, 20h ; ' '; _SERVICE_STATUS g_ServiceStatus ...
0x18000b396  xorps   xmm0, xmm0
0x18000b399  mov     cs:?g_StopServiceEventSet@@3HA, esi; int g_StopServiceEventSet
0x18000b39f  xor     r8d, r8d; lpContext
0x18000b3a2  mov     cs:?g_Stopping@@3HA, esi; int g_Stopping
0x18000b3a8  lea     rdx, ?ServiceHandler@@YAKKKPEAX0@Z; lpHandlerProc
0x18000b3af  mov     cs:?g_ErrorCode@@3KA, esi; ulong g_ErrorCode
0x18000b3b5  lea     rcx, ServiceName; "icssvc"
0x18000b3bc  mov     cs:?g_fSvcShuttingDown@@3_NA, sil; bool g_fSvcShuttingDown
0x18000b3c3  movdqu  xmmword ptr cs:?g_ServiceStatus@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, xmm0; _SERVICE_STATUS g_ServiceStatus ...
0x18000b3cb  mov     qword ptr cs:?g_ServiceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 2; _SERVICE_STATUS g_ServiceStatus ...
0x18000b3d6  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x18000b3dc  mov     cs:hServiceStatus, rax
0x18000b3e3  test    rax, rax
0x18000b3e6  jz      loc_18000B635
0x18000b3ec  lea     rax, WPP_ThisDir_CTLGUID_TetheringService
0x18000b3f3  mov     cs:qword_180041DF8, rsi
0x18000b3fa  lea     rbx, WPP_MAIN_CB
0x18000b401  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x18000b408  mov     cs:WPP_GLOBAL_Control, rbx
0x18000b40f  lea     rdi, WPP_REGISTRATION_GUIDS
0x18000b416  mov     cs:WPP_MAIN_CB, rsi
0x18000b41d  mov     cs:qword_180041E00, 1
0x18000b428  mov     r8, [rdi]; ControlGuid
0x18000b42b  lea     rax, [rbx+8]
0x18000b42f  mov     [rsp+110h+RegistrationHandle], rax; RegistrationHandle
0x18000b434  lea     rcx, WppControlCallback; RequestAddress
0x18000b43b  mov     [rsp+110h+MofResourceName], rsi; MofResourceName
0x18000b440  lea     rax, [rbp+57h+var_C8]
0x18000b444  mov     [rbp+57h+var_C8.Guid], r8
0x18000b448  lea     rdi, [rdi+8]
0x18000b44c  mov     [rbp+57h+var_C8.RegHandle], rsi
0x18000b450  mov     r9d, 1; GuidCount
0x18000b456  mov     [rsp+110h+MofImagePath], rsi; MofImagePath
0x18000b45b  mov     rdx, rbx; RequestContext
0x18000b45e  mov     [rsp+110h+TraceGuidReg], rax; TraceGuidReg
0x18000b463  mov     [rbx+20h], r8
0x18000b467  call    cs:__imp_RegisterTraceGuidsW
0x18000b46d  mov     rbx, [rbx]
0x18000b470  test    rbx, rbx
0x18000b473  jnz     short loc_18000B428
0x18000b475  lea     rcx, ?g_csSvcLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000b47c  call    cs:__imp_InitializeCriticalSection
0x18000b482  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000b489  lea     rcx, ?ResultLoggingCallback@@YAXAEBUFailureInfo@wil@@@Z; ResultLoggingCallback(wil::FailureInfo const &)
0x18000b490  test    rax, rax
0x18000b493  jz      short loc_18000B49E
0x18000b495  cmp     rax, rcx
0x18000b498  jnz     loc_18000B65E
0x18000b49e  mov     cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA, rcx
0x18000b4a5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b4ac  lea     rdi, WPP_GLOBAL_Control
0x18000b4b3  lea     r14, WPP_44e4735379a936cf4f13ce357ad19005_Traceguids
0x18000b4ba  cmp     rcx, rdi
0x18000b4bd  jz      short loc_18000B4D6
0x18000b4bf  test    byte ptr [rcx+1Ch], 8
0x18000b4c3  jz      short loc_18000B4D6
0x18000b4c5  mov     rcx, [rcx+10h]
0x18000b4c9  mov     edx, 38h ; '8'
0x18000b4ce  mov     r8, r14
0x18000b4d1  call    WPP_SF_
0x18000b4d6  lea     r9, [rbp+57h+var_D0]
0x18000b4da  mov     [rbp+57h+var_D0], esi
0x18000b4dd  lea     r8, [rbp+57h+arg_18]
0x18000b4e1  mov     [rbp+57h+arg_18], esi
0x18000b4e4  lea     rdx, [rbp+57h+arg_10]
0x18000b4e8  mov     byte ptr [rbp+57h+arg_10], sil
0x18000b4ec  mov     ebx, esi
0x18000b4ee  call    ??$wnf_query_nothrow@K@wil@@YAJAEBU_WNF_STATE_NAME@@PEA_NPEAKPEAUWNF_CHANGE_STAMP_STRUCT@0@@Z; wil::wnf_query_nothrow<ulong>(_WNF_STATE_NAME const &,bool *,ulong *,wil::WNF_CHANGE_STAMP_STRUCT *)
0x18000b4f3  test    eax, eax
0x18000b4f5  js      short loc_18000B56F
0x18000b4f7  cmp     byte ptr [rbp+57h+arg_10], sil
0x18000b4fb  jz      loc_18000B595
0x18000b501  cmp     [rbp+57h+arg_18], 1
0x18000b505  jnz     loc_18000B595
0x18000b50b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b512  cmp     rcx, rdi
0x18000b515  jz      short loc_18000B52E
0x18000b517  test    byte ptr [rcx+1Ch], 4
0x18000b51b  jz      short loc_18000B52E
0x18000b51d  mov     rcx, [rcx+10h]
0x18000b521  mov     edx, 39h ; '9'
0x18000b526  mov     r8, r14
0x18000b529  call    WPP_SF_
0x18000b52e  mov     rcx, cs:WNF_TETH_AUTOSTART_BLUETOOTH
0x18000b535  lea     r8, [rbp+57h+arg_10]
0x18000b539  mov     ebx, 1
0x18000b53e  mov     [rbp+57h+arg_10], esi
0x18000b541  xor     edx, edx
0x18000b543  mov     [rsp+110h+TraceGuidReg], rsi
0x18000b548  lea     r9d, [rbx+3]
0x18000b54c  call    cs:__imp_RtlPublishWnfStateData
0x18000b552  or      eax, 10000000h
0x18000b557  jge     short loc_18000B595
0x18000b559  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b560  cmp     rcx, rdi
0x18000b563  jz      short loc_18000B595
0x18000b565  test    [rcx+1Ch], bl
0x18000b568  jz      short loc_18000B595
0x18000b56a  lea     edx, [rbx+39h]
0x18000b56d  jmp     short loc_18000B586
0x18000b56f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b576  cmp     rcx, rdi
0x18000b579  jz      short loc_18000B595
0x18000b57b  test    byte ptr [rcx+1Ch], 2
0x18000b57f  jz      short loc_18000B595
0x18000b581  mov     edx, 3Bh ; ';'
0x18000b586  mov     rcx, [rcx+10h]
0x18000b58a  mov     r9d, eax
0x18000b58d  mov     r8, r14
0x18000b590  call    WPP_SF_d
0x18000b595  mov     ecx, ebx; int
0x18000b597  call    ?StartTetheringService@@YAKH@Z; StartTetheringService(int)
0x18000b59c  test    eax, eax
0x18000b59e  jnz     short loc_18000B5CB
0x18000b5a0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b5a7  cmp     rcx, rdi
0x18000b5aa  jz      loc_18000B646
0x18000b5b0  test    byte ptr [rcx+1Ch], 4
0x18000b5b4  jz      loc_18000B646
0x18000b5ba  mov     rcx, [rcx+10h]
0x18000b5be  lea     edx, [rax+3Ch]
0x18000b5c1  mov     r8, r14
0x18000b5c4  call    WPP_SF_
0x18000b5c9  jmp     short loc_18000B646
0x18000b5cb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b5d2  cmp     rcx, rdi
0x18000b5d5  jz      short loc_18000B611
0x18000b5d7  test    byte ptr [rcx+1Ch], 8
0x18000b5db  jz      short loc_18000B5F5
0x18000b5dd  mov     rcx, [rcx+10h]
0x18000b5e1  mov     edx, 3Dh ; '='
0x18000b5e6  mov     r8, r14
0x18000b5e9  call    WPP_SF_
0x18000b5ee  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b5f5  cmp     rcx, rdi
0x18000b5f8  jz      short loc_18000B611
0x18000b5fa  test    byte ptr [rcx+1Ch], 4
0x18000b5fe  jz      short loc_18000B611
0x18000b600  mov     rcx, [rcx+10h]
0x18000b604  mov     edx, 3Eh ; '>'
0x18000b609  mov     r8, r14
0x18000b60c  call    WPP_SF_
0x18000b611  call    WppCleanupUm
0x18000b616  lea     rcx, ?g_csSvcLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000b61d  call    cs:__imp_DeleteCriticalSection
0x18000b623  mov     edx, cs:?g_ErrorCode@@3KA; unsigned int
0x18000b629  mov     ecx, 1; unsigned int
0x18000b62e  call    ?SetTetheringServiceStatus@@YAXKK@Z; SetTetheringServiceStatus(ulong,ulong)
0x18000b633  jmp     short loc_18000B646
0x18000b635  xorps   xmm0, xmm0
0x18000b638  movups  xmmword ptr cs:?g_ServiceStatus@@3U_SERVICE_STATUS@@A.dwServiceType, xmm0; _SERVICE_STATUS g_ServiceStatus ...
0x18000b63f  movups  xmmword ptr cs:?g_ServiceStatus@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, xmm0; _SERVICE_STATUS g_ServiceStatus ...
0x18000b646  lea     r11, [rsp+110h+var_10]
0x18000b64e  mov     rbx, [r11+20h]
0x18000b652  mov     rsi, [r11+28h]
0x18000b656  mov     rsp, r11
0x18000b659  pop     r14
0x18000b65b  pop     rdi
0x18000b65c  pop     rbp
0x18000b65d  retn
0x18000b65e  xor     edx, edx; Val
0x18000b660  lea     rcx, [rbp+57h+var_B0]; void *
0x18000b664  mov     r8d, 98h; Size
0x18000b66a  call    memset_0
0x18000b66f  lea     rcx, [rbp+57h+var_B0]; this
0x18000b673  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
