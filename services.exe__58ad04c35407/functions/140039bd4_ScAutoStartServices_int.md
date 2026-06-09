# ScAutoStartServices(int *)

- ea: `0x140039bd4`
- end: `0x14003a2ee`
- name: `?ScAutoStartServices@@YAKPEAH@Z`
- size: `1818`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `25`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1400848e0`

## callees

- `0x1400010e0`
- `0x140003e54`
- `0x140004c58`
- `0x140005600`
- `0x1400070d0`
- `0x14000bcc4`
- `0x140010064`
- `0x1400188fc`
- `0x14001f99c`
- `0x14002303c`
- `0x14002bf90`
- `0x140030d50`
- `0x14003118c`
- `0x140032cd8`
- `0x140034234`
- `0x140038698`
- `0x140039bd4`
- `0x14003a2f4`
- `0x14004130c`
- `0x140041778`
- `0x140042dd0`
- `0x140042ffc`
- `0x1400430b0`
- `0x1400575b0`
- `0x140079d10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140039e22`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140039e7c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140039e22`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140039e7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140039e31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140039e8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140039e31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140039e8b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14003a10f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14003a10f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003a01e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003a030`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003a03f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003a01e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003a030`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003a03f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x140039cab`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x14003a13f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x14003a250`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x140039cab`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x14003a13f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x14003a250`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x140039f90`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x140039f90`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x14003a1e8`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x14003a1e8`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x14003a109`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x14003a109`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x14003a21b`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x14003a21b`
- `ntdll!NtClose` at `0x140039df0`
- `ntdll!NtClose` at `0x140039df0`
- `ntdll!RtlNtStatusToDosError` at `0x140039df8`
- `ntdll!RtlNtStatusToDosError` at `0x140039df8`
- `ntdll!NtSetEvent` at `0x14003a198`
- `ntdll!NtSetEvent` at `0x14003a198`
- `ntdll!RtlPublishWnfStateData` at `0x140039ca5`
- `ntdll!RtlPublishWnfStateData` at `0x14003a139`
- `ntdll!RtlPublishWnfStateData` at `0x140039ca5`
- `ntdll!RtlPublishWnfStateData` at `0x14003a139`

## string_xrefs

- `0x140039f65`: `TrustedInstaller`
- `0x140039ee6`: `FontCache`
- `0x140039ef4`: `DispBrokerDesktopSvc`

## pseudocode

```c
__int64 __fastcall ScAutoStartServices(int *a1)
{
  __int64 v2; // r8
  ULONGLONG TickCount64; // r15
  __int64 v4; // rcx
  unsigned int started; // eax
  __int64 v6; // rdx
  __int64 v7; // rcx
  unsigned int v8; // r8d
  unsigned int v9; // ebx
  PRPC_ASYNC_STATE v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rcx
  unsigned int v13; // r8d
  HANDLE v14; // r8
  NTSTATUS v15; // eax
  DWORD v16; // eax
  DWORD v17; // esi
  int v18; // r14d
  DWORD LastError; // eax
  PRPC_ASYNC_STATE v20; // rcx
  unsigned int v21; // ebx
  wchar_t *v22; // rdi
  unsigned int v23; // eax
  unsigned int v24; // eax
  DWORD v25; // eax
  __int64 v26; // r8
  int v27; // ecx
  ULONGLONG v28; // r8
  int v29; // ecx
  __int64 v30; // r8
  ULONGLONG v31; // r8
  int v32; // ecx
  __int64 v33; // r8
  int v35; // [rsp+40h] [rbp-59h] BYREF
  __int64 v36; // [rsp+48h] [rbp-51h] BYREF
  HANDLE Handle; // [rsp+50h] [rbp-49h] BYREF
  _QWORD v38[3]; // [rsp+58h] [rbp-41h] BYREF
  wchar_t *String2[3]; // [rsp+70h] [rbp-29h]
  HANDLE Handles[2]; // [rsp+88h] [rbp-11h] BYREF
  HANDLE hObject; // [rsp+98h] [rbp-1h]

  v35 = 0;
  hObject = 0;
  Handle = 0;
  v38[0] = v38;
  v38[1] = v38;
  *(_OWORD *)Handles = 0;
  v38[2] = 0;
  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->StubInfo, 22, WPP_21b4c565b436346f75e2b704ea64e4ae_Traceguids);
  ScAutoStartInProgress = 1;
  ScLogStatusChange(0, &SCMEvt_Autostart_Start, 0);
  ScLogStatusChange(0, &SCMEvt_PerfCriticalAutostart_Start, 0);
  v35 = 1;
  RtlPublishWnfStateData(WNF_SCM_AUTOSTART_STATE, 0, &v35, 4, 0);
  TickCount64 = GetTickCount64();
  if ( (unsigned int)dword_1400BA2A0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400BA2A0, 0x400000000000LL, v2) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v4,
      qword_1400AECE0,
      0,
      0);
  ScStartServiceByName((wchar_t *)L"PlugPlay", 0);
  ScStartServiceByName((wchar_t *)L"Power", 0);
  if ( g_hProviderEvent )
    ScHandleProviderChange(g_hProviderEvent, 0);
  ScGetBootAndSystemDriverState();
  started = ScStartOObeServices(a1);
  v9 = started;
  if ( started )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
    {
      v11 = 23;
LABEL_13:
      WPP_SF_d(v10->StubInfo, v11, WPP_21b4c565b436346f75e2b704ea64e4ae_Traceguids, started);
    }
  }
  else
  {
    started = ScStartStagedBootServices(v7, v6, v8);
    v9 = started;
    if ( !started )
    {
      _InterlockedExchange((volatile __int32 *)&g_dwRunningAutostartLoop, 1);
      _InterlockedExchange((volatile __int32 *)&g_dwRunningAutostartPhase1Loop, 1);
      if ( (unsigned int)SetupInProgress(0, 0)
        && (v9 = ScRegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\Setup\\AllowStart", v13, 0x20019u, (HKEY *)&Handle)) != 0 )
      {
        v14 = 0;
        Handle = 0;
      }
      else
      {
        v14 = Handle;
      }
      CServiceDatabase::GetAutoStartServices(v12, v38, v14);
      if ( Handle )
      {
        v15 = NtClose(Handle);
        RtlNtStatusToDosError(v15);
      }
      ScStartEarlySetOfServices(v38);
      if ( (unsigned int)ScIsPrimitiveServicingRunLevelRequested() )
      {
        Handles[0] = CreateEventW(0, 1, 0, L"Global\\SC_BOOT_SERVICING_DONE");
        if ( Handles[0] )
        {
          v17 = 3;
          v18 = 0;
          hObject = CreateEventW(0, 1, 0, L"Global\\SC_BOOT_SERVICING_INITIATING_RESTART");
          if ( hObject )
          {
            v20 = WPP_GLOBAL_Control;
          }
          else
          {
            LastError = GetLastError();
            v20 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
              && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 2) != 0 )
            {
              WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 26, WPP_21b4c565b436346f75e2b704ea64e4ae_Traceguids, LastError);
              v20 = WPP_GLOBAL_Control;
            }
            v17 = 2;
          }
          if ( v20 != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(v20->UserInfo) & 4) != 0 )
            WPP_SF_(v20->StubInfo, 27, WPP_21b4c565b436346f75e2b704ea64e4ae_Traceguids);
          v21 = 0;
          String2[0] = L"FontCache";
          String2[1] = L"DispBrokerDesktopSvc";
          String2[2] = L"CoreMessagingRegistrar";
          do
          {
            v22 = String2[v21];
            v23 = ScStartServiceByName(v22, 0);
            if ( v23
              && WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
              && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 2) != 0 )
            {
              WPP_SF_Sd(
                WPP_GLOBAL_Control->StubInfo,
                28,
                (unsigned int)WPP_21b4c565b436346f75e2b704ea64e4ae_Traceguids,
                (_DWORD)v22,
                v23);
            }
            ++v21;
          }
          while ( v21 < 3 );
          v24 = ScStartServiceByName((wchar_t *)L"TrustedInstaller", &Handles[1]);
          if ( v24 || !Handles[1] )
          {
            if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
              && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
            {
              WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 32, WPP_21b4c565b436346f75e2b704ea64e4ae_Traceguids, v24);
            }
          }
          else
          {
            v25 = WaitForMultipleObjects(v17, Handles, 0, 0xFFFFFFFF);
            if ( v25 == 2 )
            {
              if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) != 0 )
              {
                WPP_SF_(WPP_GLOBAL_Control->StubInfo, 29, WPP_21b4c565b436346f75e2b704ea64e4ae_Traceguids);
              }
              v18 = 1;
            }
            else if ( v25 )
            {
              if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
              {
                WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 30, WPP_21b4c565b436346f75e2b704ea64e4ae_Traceguids, v25);
              }
            }
            else if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                   && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) != 0 )
            {
              WPP_SF_S(
                WPP_GLOBAL_Control->StubInfo,
                31,
                WPP_21b4c565b436346f75e2b704ea64e4ae_Traceguids,
                L"Global\\SC_BOOT_SERVICING_DONE");
            }
            CloseHandle(Handles[1]);
          }
          v9 = 0;
          CloseHandle(Handles[0]);
          if ( hObject )
            CloseHandle(hObject);
          if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->StubInfo, 33, WPP_21b4c565b436346f75e2b704ea64e4ae_Traceguids);
          }
          if ( v18 )
          {
            if ( (unsigned int)dword_1400BA2A0 > 5
              && (unsigned __int8)tlgKeywordOn(&dword_1400BA2A0, 0x400000000000LL, v26) )
            {
              v36 = 0x1000000;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
                v27,
                (unsigned int)word_1400AEC9A,
                0,
                0,
                (__int64)&v36);
            }
            goto LABEL_84;
          }
        }
        else
        {
          v16 = GetLastError();
          if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 2) != 0 )
          {
            WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 25, WPP_21b4c565b436346f75e2b704ea64e4ae_Traceguids, v16);
          }
          v9 = 0;
        }
      }
      RtlAcquireSRWLockExclusive(&g_TriggerRegistrationLock);
      GetCurrentThreadId();
      ScRegisterServicesForTriggerAction(4u);
      v35 = 2;
      RtlPublishWnfStateData(WNF_SCM_AUTOSTART_STATE, 0, &v35, 4, 0);
      v28 = GetTickCount64();
      if ( (unsigned int)dword_1400BA2A0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400BA2A0, 0x400000000000LL, v28) )
      {
        v36 = v30 - TickCount64;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
          v29,
          (unsigned int)byte_1400AEC65,
          0,
          0,
          (__int64)&v36);
      }
      NtSetEvent(g_hAutoStartPhase1Event, 0);
      _InterlockedExchange((volatile __int32 *)&g_dwRunningAutostartPhase1Loop, 0);
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->StubInfo, 34, WPP_21b4c565b436346f75e2b704ea64e4ae_Traceguids);
      ScUpdateAndPublishScmGlobalState(0x30u);
      ScRegisterServicesForTriggerAction(2u);
      g_BootTriggerRegistrationComplete = 1;
      RtlReleaseSRWLockExclusive(&g_TriggerRegistrationLock);
      v36 = 0;
      RtlSubscribeWnfStateChangeNotification(
        &v36,
        WNF_PO_SYSTEM_TIME_CHANGED,
        0,
        ScSystemTimeChangedCallback,
        0,
        0,
        0,
        0);
      ScStartMedic();
      ScStartPhase2Services(v38);
      _InterlockedExchange((volatile __int32 *)&g_dwRunningAutostartLoop, 0);
      ScLogStatusChange(0, &SCMEvt_Autostart_Stop, 0);
      ScAutoStartInProgress = 0;
      v31 = GetTickCount64();
      if ( (unsigned int)dword_1400BA2A0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400BA2A0, 0x200000000000LL, v31) )
      {
        v36 = v33 - TickCount64;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
          v32,
          (unsigned int)byte_1400AEC31,
          0,
          0,
          (__int64)&v36);
      }
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->StubInfo, 35, WPP_21b4c565b436346f75e2b704ea64e4ae_Traceguids);
      goto LABEL_84;
    }
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
    {
      v11 = 24;
      goto LABEL_13;
    }
  }
LABEL_84:
  utl::list<Microsoft::WRL::ComPtr<CServiceRecord>,utl::allocator<Microsoft::WRL::ComPtr<CServiceRecord>>>::clear(v38);
  return v9;
}

```

## disassembly

```asm
0x140039bd4  push    rbp
0x140039bd6  push    rbx
0x140039bd7  push    rsi
0x140039bd8  push    rdi
0x140039bd9  push    r12
0x140039bdb  push    r13
0x140039bdd  push    r14
0x140039bdf  push    r15
0x140039be1  lea     rbp, [rsp-1Fh]
0x140039be6  sub     rsp, 0B8h
0x140039bed  mov     rax, cs:__security_cookie
0x140039bf4  xor     rax, rsp
0x140039bf7  mov     [rbp+57h+var_50], rax
0x140039bfb  xor     r12d, r12d
0x140039bfe  xorps   xmm0, xmm0
0x140039c01  xor     eax, eax
0x140039c03  mov     [rbp+57h+var_B0], r12d
0x140039c07  mov     [rbp+57h+hObject], rax
0x140039c0b  mov     rbx, rcx
0x140039c0e  lea     rax, [rbp+57h+var_98]
0x140039c12  mov     [rbp+57h+Handle], r12
0x140039c16  mov     [rbp+57h+var_98], rax
0x140039c1a  lea     rax, [rbp+57h+var_98]
0x140039c1e  mov     [rbp+57h+var_90], rax
0x140039c22  movups  xmmword ptr [rbp+57h+Handles], xmm0
0x140039c26  mov     [rbp+57h+var_88], r12
0x140039c2a  mov     rcx, cs:WPP_GLOBAL_Control
0x140039c31  lea     r13, WPP_GLOBAL_Control
0x140039c38  lea     r14d, [r12+4]
0x140039c3d  lea     rdi, WPP_21b4c565b436346f75e2b704ea64e4ae_Traceguids
0x140039c44  cmp     rcx, r13
0x140039c47  jz      short loc_140039C60
0x140039c49  test    [rcx+1Ch], r14b
0x140039c4d  jz      short loc_140039C60
0x140039c4f  mov     rcx, [rcx+10h]
0x140039c53  lea     edx, [r12+16h]
0x140039c58  mov     r8, rdi
0x140039c5b  call    WPP_SF_
0x140039c60  mov     esi, 1
0x140039c65  lea     rdx, SCMEvt_Autostart_Start; struct _EVENT_DESCRIPTOR *
0x140039c6c  xor     r8d, r8d; unsigned __int16 *
0x140039c6f  mov     cs:?ScAutoStartInProgress@@3HA, esi; int ScAutoStartInProgress
0x140039c75  xor     ecx, ecx; struct CServiceRecord *
0x140039c77  call    ?ScLogStatusChange@@YAXPEAVCServiceRecord@@PEBU_EVENT_DESCRIPTOR@@PEBG@Z; ScLogStatusChange(CServiceRecord *,_EVENT_DESCRIPTOR const *,ushort const *)
0x140039c7c  xor     r8d, r8d; unsigned __int16 *
0x140039c7f  lea     rdx, SCMEvt_PerfCriticalAutostart_Start; struct _EVENT_DESCRIPTOR *
0x140039c86  xor     ecx, ecx; struct CServiceRecord *
0x140039c88  call    ?ScLogStatusChange@@YAXPEAVCServiceRecord@@PEBU_EVENT_DESCRIPTOR@@PEBG@Z; ScLogStatusChange(CServiceRecord *,_EVENT_DESCRIPTOR const *,ushort const *)
0x140039c8d  mov     rcx, cs:WNF_SCM_AUTOSTART_STATE
0x140039c94  lea     r8, [rbp+57h+var_B0]
0x140039c98  mov     r9d, r14d
0x140039c9b  mov     [rbp+57h+var_B0], esi
0x140039c9e  xor     edx, edx
0x140039ca0  mov     [rsp+0F0h+var_D0], r12
0x140039ca5  call    cs:__imp_RtlPublishWnfStateData
0x140039cab  call    cs:__imp_GetTickCount64
0x140039cb1  mov     r15, rax
0x140039cb4  mov     eax, cs:dword_1400BA2A0
0x140039cba  cmp     eax, 5
0x140039cbd  jbe     short loc_140039CEB
0x140039cbf  mov     rdx, 400000000000h
0x140039cc9  lea     rcx, dword_1400BA2A0
0x140039cd0  call    _tlgKeywordOn
0x140039cd5  test    al, al
0x140039cd7  jz      short loc_140039CEB
0x140039cd9  xor     r9d, r9d
0x140039cdc  lea     rdx, qword_1400AECE0
0x140039ce3  xor     r8d, r8d
0x140039ce6  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x140039ceb  xor     edx, edx; void **
0x140039ced  lea     rcx, aPlugplay; "PlugPlay"
0x140039cf4  call    ?ScStartServiceByName@@YAKPEAGPEAPEAX@Z; ScStartServiceByName(ushort *,void * *)
0x140039cf9  xor     edx, edx; void **
0x140039cfb  lea     rcx, aPower; "Power"
0x140039d02  call    ?ScStartServiceByName@@YAKPEAGPEAPEAX@Z; ScStartServiceByName(ushort *,void * *)
0x140039d07  mov     rcx, cs:?g_hProviderEvent@@3PEAXEA; PVOID
0x140039d0e  test    rcx, rcx
0x140039d11  jz      short loc_140039D1A
0x140039d13  xor     edx, edx; BOOLEAN
0x140039d15  call    ?ScHandleProviderChange@@YAXPEAXE@Z; ScHandleProviderChange(void *,uchar)
0x140039d1a  call    ?ScGetBootAndSystemDriverState@@YAXXZ; ScGetBootAndSystemDriverState(void)
0x140039d1f  mov     rcx, rbx; int *
0x140039d22  call    ?ScStartOObeServices@@YAKPEAH@Z; ScStartOObeServices(int *)
0x140039d27  mov     ebx, eax
0x140039d29  test    eax, eax
0x140039d2b  jz      short loc_140039D60
0x140039d2d  mov     rcx, cs:WPP_GLOBAL_Control
0x140039d34  cmp     rcx, r13
0x140039d37  jz      loc_14003A2C3
0x140039d3d  test    [rcx+1Ch], sil
0x140039d41  jz      loc_14003A2C3
0x140039d47  mov     edx, 17h
0x140039d4c  mov     rcx, [rcx+10h]
0x140039d50  mov     r9d, eax
0x140039d53  mov     r8, rdi
0x140039d56  call    WPP_SF_d
0x140039d5b  jmp     loc_14003A2C3
0x140039d60  call    ?ScStartStagedBootServices@@YAKXZ; ScStartStagedBootServices(void)
0x140039d65  mov     ebx, eax
0x140039d67  test    eax, eax
0x140039d69  jz      short loc_140039D8C
0x140039d6b  mov     rcx, cs:WPP_GLOBAL_Control
0x140039d72  cmp     rcx, r13
0x140039d75  jz      loc_14003A2C3
0x140039d7b  test    [rcx+1Ch], sil
0x140039d7f  jz      loc_14003A2C3
0x140039d85  mov     edx, 18h
0x140039d8a  jmp     short loc_140039D4C
0x140039d8c  mov     eax, esi
0x140039d8e  mov     ecx, esi
0x140039d90  xchg    eax, cs:?g_dwRunningAutostartLoop@@3KC; ulong volatile g_dwRunningAutostartLoop
0x140039d96  xchg    ecx, cs:?g_dwRunningAutostartPhase1Loop@@3KC; ulong volatile g_dwRunningAutostartPhase1Loop
0x140039d9c  xor     ecx, ecx
0x140039d9e  xor     edx, edx
0x140039da0  call    SetupInProgress
0x140039da5  test    eax, eax
0x140039da7  jz      short loc_140039DDA
0x140039da9  lea     rax, [rbp+57h+Handle]
0x140039dad  mov     r9d, 20019h; unsigned int
0x140039db3  lea     rdx, aSystemSetupAll; "System\\Setup\\AllowStart"
0x140039dba  mov     [rsp+0F0h+var_D0], rax; HKEY *
0x140039dbf  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x140039dc6  call    ?ScRegOpenKeyExW@@YAKPEAUHKEY__@@PEBGKKPEAPEAU1@@Z; ScRegOpenKeyExW(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x140039dcb  mov     ebx, eax
0x140039dcd  test    eax, eax
0x140039dcf  jz      short loc_140039DDA
0x140039dd1  mov     r8, r12
0x140039dd4  mov     [rbp+57h+Handle], r12
0x140039dd8  jmp     short loc_140039DDE
0x140039dda  mov     r8, [rbp+57h+Handle]
0x140039dde  lea     rdx, [rbp+57h+var_98]
0x140039de2  call    ?GetAutoStartServices@CServiceDatabase@@QEAAXAEAV?$list@V?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@@utl@@@utl@@PEAUHKEY__@@@Z; CServiceDatabase::GetAutoStartServices(utl::list<Microsoft::WRL::ComPtr<CServiceRecord>,utl::allocator<Microsoft::WRL::ComPtr<CServiceRecord>>> &,HKEY__ *)
0x140039de7  mov     rcx, [rbp+57h+Handle]; Handle
0x140039deb  test    rcx, rcx
0x140039dee  jz      short loc_140039DFE
0x140039df0  call    cs:__imp_NtClose
0x140039df6  mov     ecx, eax; Status
0x140039df8  call    cs:__imp_RtlNtStatusToDosError
0x140039dfe  lea     rcx, [rbp+57h+var_98]
0x140039e02  call    ?ScStartEarlySetOfServices@@YAKAEAV?$list@V?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@@utl@@@utl@@@Z; ScStartEarlySetOfServices(utl::list<Microsoft::WRL::ComPtr<CServiceRecord>,utl::allocator<Microsoft::WRL::ComPtr<CServiceRecord>>> &)
0x140039e07  call    ?ScIsPrimitiveServicingRunLevelRequested@@YAHXZ; ScIsPrimitiveServicingRunLevelRequested(void)
0x140039e0c  test    eax, eax
0x140039e0e  jz      loc_14003A102
0x140039e14  lea     r9, aGlobalScBootSe; "Global\\SC_BOOT_SERVICING_DONE"
0x140039e1b  xor     r8d, r8d; bInitialState
0x140039e1e  mov     edx, esi; bManualReset
0x140039e20  xor     ecx, ecx; lpEventAttributes
0x140039e22  call    cs:__imp_CreateEventW
0x140039e28  mov     [rbp+57h+Handles], rax
0x140039e2c  test    rax, rax
0x140039e2f  jnz     short loc_140039E65
0x140039e31  call    cs:__imp_GetLastError
0x140039e37  mov     rcx, cs:WPP_GLOBAL_Control
0x140039e3e  cmp     rcx, r13
0x140039e41  jz      short loc_140039E5D
0x140039e43  test    byte ptr [rcx+1Ch], 2
0x140039e47  jz      short loc_140039E5D
0x140039e49  mov     rcx, [rcx+10h]
0x140039e4d  mov     edx, 19h
0x140039e52  mov     r9d, eax
0x140039e55  mov     r8, rdi
0x140039e58  call    WPP_SF_d
0x140039e5d  mov     ebx, r12d
0x140039e60  jmp     loc_14003A102
0x140039e65  mov     esi, 3
0x140039e6a  lea     r9, aGlobalScBootSe_0; "Global\\SC_BOOT_SERVICING_INITIATING_RE"...
0x140039e71  xor     r8d, r8d; bInitialState
0x140039e74  xor     ecx, ecx; lpEventAttributes
0x140039e76  mov     r14d, r12d
0x140039e79  lea     edx, [rsi-2]; bManualReset
0x140039e7c  call    cs:__imp_CreateEventW
0x140039e82  mov     [rbp+57h+hObject], rax
0x140039e86  test    rax, rax
0x140039e89  jnz     short loc_140039EC3
0x140039e8b  call    cs:__imp_GetLastError
0x140039e91  mov     rcx, cs:WPP_GLOBAL_Control
0x140039e98  cmp     rcx, r13
0x140039e9b  jz      short loc_140039EBC
0x140039e9d  test    byte ptr [rcx+1Ch], 2
0x140039ea1  jz      short loc_140039EBC
0x140039ea3  mov     rcx, [rcx+10h]
0x140039ea7  lea     edx, [rsi+17h]
0x140039eaa  mov     r9d, eax
0x140039ead  mov     r8, rdi
0x140039eb0  call    WPP_SF_d
0x140039eb5  mov     rcx, cs:WPP_GLOBAL_Control
0x140039ebc  mov     esi, 2
0x140039ec1  jmp     short loc_140039ECA
0x140039ec3  mov     rcx, cs:WPP_GLOBAL_Control
0x140039eca  cmp     rcx, r13
0x140039ecd  jz      short loc_140039EE6
0x140039ecf  test    byte ptr [rcx+1Ch], 4
0x140039ed3  jz      short loc_140039EE6
0x140039ed5  mov     rcx, [rcx+10h]
0x140039ed9  mov     edx, 1Bh
0x140039ede  mov     r8, rdi
0x140039ee1  call    WPP_SF_
0x140039ee6  lea     rax, aFontcache; "FontCache"
0x140039eed  mov     ebx, r12d
0x140039ef0  mov     [rbp+57h+String2], rax
0x140039ef4  lea     rax, aDispbrokerdesk; "DispBrokerDesktopSvc"
0x140039efb  mov     [rbp+57h+var_78], rax
0x140039eff  lea     rax, aCoremessagingr; "CoreMessagingRegistrar"
0x140039f06  mov     [rbp+57h+var_70], rax
0x140039f0a  movsxd  rax, ebx
0x140039f0d  xor     edx, edx; void **
0x140039f0f  mov     rdi, [rbp+rax*8+57h+String2]
0x140039f14  mov     rcx, rdi; String2
0x140039f17  call    ?ScStartServiceByName@@YAKPEAGPEAPEAX@Z; ScStartServiceByName(ushort *,void * *)
0x140039f1c  test    eax, eax
0x140039f1e  jz      short loc_140039F53
0x140039f20  mov     rcx, cs:WPP_GLOBAL_Control
0x140039f27  cmp     rcx, r13
0x140039f2a  jz      short loc_140039F53
0x140039f2c  test    byte ptr [rcx+1Ch], 2
0x140039f30  jz      short loc_140039F53
0x140039f32  mov     rcx, [rcx+10h]
0x140039f36  mov     r9, rdi
0x140039f39  lea     rdi, WPP_21b4c565b436346f75e2b704ea64e4ae_Traceguids
0x140039f40  mov     dword ptr [rsp+0F0h+var_D0], eax
0x140039f44  mov     r8, rdi
0x140039f47  mov     edx, 1Ch
0x140039f4c  call    WPP_SF_Sd
0x140039f51  jmp     short loc_140039F5A
0x140039f53  lea     rdi, WPP_21b4c565b436346f75e2b704ea64e4ae_Traceguids
0x140039f5a  inc     ebx
0x140039f5c  cmp     ebx, 3
0x140039f5f  jb      short loc_140039F0A
0x140039f61  lea     rdx, [rbp+57h+Handles+8]; void **
0x140039f65  lea     rcx, aTrustedinstall; "TrustedInstaller"
0x140039f6c  call    ?ScStartServiceByName@@YAKPEAGPEAPEAX@Z; ScStartServiceByName(ushort *,void * *)
0x140039f71  test    eax, eax
0x140039f73  jnz     loc_14003A0C6
0x140039f79  cmp     [rbp+57h+Handles+8], r12
0x140039f7d  jz      loc_14003A0C6
0x140039f83  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x140039f87  lea     rdx, [rbp+57h+Handles]; lpHandles
0x140039f8b  xor     r8d, r8d; bWaitAll
0x140039f8e  mov     ecx, esi; nCount
0x140039f90  call    cs:__imp_WaitForMultipleObjects
0x140039f96  cmp     eax, 2
0x140039f99  jnz     short loc_140039FC4
0x140039f9b  mov     rcx, cs:WPP_GLOBAL_Control
0x140039fa2  cmp     rcx, r13
0x140039fa5  jz      short loc_140039FBC
0x140039fa7  test    byte ptr [rcx+1Ch], 4
0x140039fab  jz      short loc_140039FBC
0x140039fad  mov     rcx, [rcx+10h]
0x140039fb1  lea     edx, [rax+1Bh]
0x140039fb4  mov     r8, rdi
0x140039fb7  call    WPP_SF_
0x140039fbc  mov     r14d, 1
0x140039fc2  jmp     short loc_14003A01A
0x140039fc4  test    eax, eax
0x140039fc6  jz      short loc_140039FF0
0x140039fc8  mov     rcx, cs:WPP_GLOBAL_Control
0x140039fcf  cmp     rcx, r13
0x140039fd2  jz      short loc_14003A01A
0x140039fd4  test    byte ptr [rcx+1Ch], 1
0x140039fd8  jz      short loc_14003A01A
0x140039fda  mov     rcx, [rcx+10h]
0x140039fde  mov     edx, 1Eh
0x140039fe3  mov     r9d, eax
0x140039fe6  mov     r8, rdi
0x140039fe9  call    WPP_SF_d
0x140039fee  jmp     short loc_14003A01A
0x140039ff0  mov     rcx, cs:WPP_GLOBAL_Control
0x140039ff7  cmp     rcx, r13
0x140039ffa  jz      short loc_14003A01A
0x140039ffc  test    byte ptr [rcx+1Ch], 4
0x14003a000  jz      short loc_14003A01A
0x14003a002  mov     rcx, [rcx+10h]
0x14003a006  lea     r9, aGlobalScBootSe; "Global\\SC_BOOT_SERVICING_DONE"
0x14003a00d  mov     edx, 1Fh
0x14003a012  mov     r8, rdi
0x14003a015  call    WPP_SF_S
0x14003a01a  mov     rcx, [rbp+57h+Handles+8]; hObject
0x14003a01e  call    cs:__imp_CloseHandle
0x14003a024  mov     esi, 1
0x14003a029  mov     rcx, [rbp+57h+Handles]; hObject
0x14003a02d  mov     ebx, r12d
0x14003a030  call    cs:__imp_CloseHandle
0x14003a036  mov     rcx, [rbp+57h+hObject]; hObject
0x14003a03a  test    rcx, rcx
0x14003a03d  jz      short loc_14003A045
0x14003a03f  call    cs:__imp_CloseHandle
0x14003a045  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a04c  cmp     rcx, r13
0x14003a04f  jz      short loc_14003A068
0x14003a051  test    byte ptr [rcx+1Ch], 4
0x14003a055  jz      short loc_14003A068
0x14003a057  mov     rcx, [rcx+10h]
0x14003a05b  mov     edx, 21h ; '!'
0x14003a060  mov     r8, rdi
0x14003a063  call    WPP_SF_
0x14003a068  test    r14d, r14d
0x14003a06b  jz      loc_14003A0FC
0x14003a071  mov     eax, cs:dword_1400BA2A0
0x14003a077  cmp     eax, 5
0x14003a07a  jbe     loc_14003A2C3
  ... truncated ...
```
