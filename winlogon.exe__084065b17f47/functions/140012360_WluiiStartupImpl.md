# WluiiStartupImpl

- ea: `0x140012360`
- end: `0x1400129ea`
- name: `WluiiStartupImpl`
- size: `1674`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140010330`
- `0x140010514`
- `0x140010b10`
- `0x140012220`

## callees

- `0x14000d4e0`
- `0x140012360`
- `0x140053720`
- `0x14005d714`
- `0x14009a9d8`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400129e2`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400129e2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140012479`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140012479`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001248b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400124b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400127e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001248b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400124b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400127e4`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x14001279c`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x14001279c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140012428`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140012428`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x1400127da`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x1400127da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400125c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140012821`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400125c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140012821`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x140012900`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x140012900`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140012590`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140012590`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1400128c8`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1400128c8`
- `RPCRT4!RpcStringFreeW` at `0x140012641`
- `RPCRT4!RpcStringFreeW` at `0x140012641`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1400129cd`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1400129cd`
- `RPCRT4!RpcStringBindingComposeW` at `0x1400128ac`
- `RPCRT4!RpcStringBindingComposeW` at `0x1400128ac`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x140012849`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x140012849`
- `ntdll!NtCreateWnfStateName` at `0x1400124e9`
- `ntdll!NtCreateWnfStateName` at `0x1400124e9`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x14001252e`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x14001252e`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1400125af`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1400125af`
- `ntdll!RtlPublishWnfStateData` at `0x140012562`
- `ntdll!RtlPublishWnfStateData` at `0x140012562`
- `ntdll!EtwEventEnabled` at `0x1400123e8`
- `ntdll!EtwEventEnabled` at `0x1400125e8`
- `ntdll!EtwEventEnabled` at `0x14001266e`
- `ntdll!EtwEventEnabled` at `0x1400123e8`
- `ntdll!EtwEventEnabled` at `0x1400125e8`
- `ntdll!EtwEventEnabled` at `0x14001266e`
- `ntdll!EtwEventWrite` at `0x140012406`
- `ntdll!EtwEventWrite` at `0x140012606`
- `ntdll!EtwEventWrite` at `0x14001268c`
- `ntdll!EtwEventWrite` at `0x140012406`
- `ntdll!EtwEventWrite` at `0x140012606`
- `ntdll!EtwEventWrite` at `0x14001268c`
- `ntdll!RtlGetActiveConsoleId` at `0x140012853`
- `ntdll!RtlGetActiveConsoleId` at `0x140012853`
- `ntdll!RtlNtStatusToDosError` at `0x1400124f5`
- `ntdll!RtlNtStatusToDosError` at `0x14001253a`
- `ntdll!RtlNtStatusToDosError` at `0x14001256e`
- `ntdll!RtlNtStatusToDosError` at `0x1400124f5`
- `ntdll!RtlNtStatusToDosError` at `0x14001253a`
- `ntdll!RtlNtStatusToDosError` at `0x14001256e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1400124ac`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1400124ac`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x140012949`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x140012949`
- `api-ms-win-rtcore-ntuser-private-l1-1-2!RegisterLogonProcess` at `0x140012830`
- `api-ms-win-rtcore-ntuser-private-l1-1-2!RegisterLogonProcess` at `0x140012830`

## string_xrefs

- `0x1400126f4`: `"%s" /flags:0x%lx /state0:0x%lx /state1:0x%lx /testclientprocessid:0x%08x`

## pseudocode

```c
__int64 __fastcall WluiiStartupImpl(unsigned int a1, void *a2, DWORD *a3)
{
  int v6; // esi
  DWORD CurrentProcessId; // edi
  ULONG LastError; // ebx
  NTSTATUS WnfStateName; // eax
  NTSTATUS v10; // eax
  int v12; // eax
  WCHAR *v13; // rcx
  BOOL v14; // eax
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rcx
  int v18; // eax
  BOOL bInheritHandles[2]; // [rsp+28h] [rbp-E0h]
  DWORD dwCreationFlags[2]; // [rsp+30h] [rbp-D8h]
  LPVOID lpEnvironment; // [rsp+38h] [rbp-D0h]
  LPCWSTR lpCurrentDirectory; // [rsp+40h] [rbp-C8h]
  DWORD cbSid[2]; // [rsp+68h] [rbp-A0h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+70h] [rbp-98h] BYREF
  RPC_WSTR String; // [rsp+78h] [rbp-90h] BYREF
  _SID_NAME_USE peUse; // [rsp+80h] [rbp-88h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+88h] [rbp-80h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+A8h] [rbp-60h] BYREF
  DWORD cchName[2]; // [rsp+118h] [rbp+10h] BYREF
  RPC_SECURITY_QOS SecurityQOS; // [rsp+120h] [rbp+18h] BYREF
  struct _SECURITY_ATTRIBUTES EventAttributes; // [rsp+130h] [rbp+28h] BYREF
  _BYTE pSid[80]; // [rsp+158h] [rbp+50h] BYREF
  unsigned __int16 ObjUuid[40]; // [rsp+1A8h] [rbp+A0h] BYREF
  WCHAR CommandLine[256]; // [rsp+1F8h] [rbp+F0h] BYREF
  unsigned __int16 ServerPrincName[280]; // [rsp+3F8h] [rbp+2F0h] BYREF
  WCHAR Name[264]; // [rsp+628h] [rbp+520h] BYREF

  *a3 = 0;
  String = 0;
  memset(&StartupInfo, 0, sizeof(StartupInfo));
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  SecurityQOS = 0;
  if ( g_TraceRegHandle && (unsigned __int8)EtwEventEnabled(g_TraceRegHandle, WLEvt_WluiServerStartup_Start) )
    EtwEventWrite(g_TraceRegHandle, WLEvt_WluiServerStartup_Start, 0, 0);
  if ( (a1 & 0x40000000) != 0 )
  {
    v6 = 1;
    CurrentProcessId = GetCurrentProcessId();
  }
  else
  {
    v6 = 0;
    CurrentProcessId = 0;
  }
  String = 0;
  if ( a1 )
  {
    *(_QWORD *)cchName = 0;
    _wnfState = 0;
    *(_QWORD *)&EventAttributes.nLength = 24;
    *(_QWORD *)&EventAttributes.bInheritHandle = 1;
    SecurityDescriptor = 0;
    EventAttributes.lpSecurityDescriptor = 0;
    ServerReadyEvent = CreateEventW(&EventAttributes, 1, 0, 0);
    if ( ServerReadyEvent )
    {
      if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
             L"D:(A;;GA;;;SY)(A;;1;;;AU)",
             1u,
             &SecurityDescriptor,
             0) )
      {
        WnfStateName = NtCreateWnfStateName(cchName, 2, 0, 0, 0, 4, SecurityDescriptor);
        if ( WnfStateName < 0
          || (WnfStateName = RtlSubscribeWnfStateChangeNotification(
                               &_wnfSubscription,
                               *(_QWORD *)cchName,
                               0,
                               ServerStateChangedWnfCallback,
                               0,
                               0,
                               0,
                               1),
              WnfStateName < 0) )
        {
          LastError = RtlNtStatusToDosError(WnfStateName);
        }
        else
        {
          cbSid[0] = 1;
          v10 = RtlPublishWnfStateData(*(_QWORD *)cchName, 0, cbSid, 4, 0);
          if ( v10 >= 0 )
          {
            LastError = 0;
            _wnfState = *(struct _WNF_STATE_NAME *)cchName;
          }
          else
          {
            LastError = RtlNtStatusToDosError(v10);
          }
        }
      }
      else
      {
        LastError = GetLastError();
      }
    }
    else
    {
      LastError = GetLastError();
    }
    if ( SecurityDescriptor )
    {
      LocalFree(SecurityDescriptor);
      SecurityDescriptor = 0;
    }
    if ( LastError )
    {
      if ( _wnfSubscription )
      {
        RtlUnsubscribeWnfNotificationWaitForCompletion();
        _wnfSubscription = 0;
      }
      if ( ServerReadyEvent )
      {
        CloseHandle(ServerReadyEvent);
        ServerReadyEvent = 0;
      }
      goto LABEL_25;
    }
    if ( v6 )
    {
      LODWORD(lpCurrentDirectory) = _wnfState.Data[1];
      LODWORD(lpEnvironment) = _wnfState.Data[0];
      dwCreationFlags[0] = CurrentProcessId;
      bInheritHandles[0] = dword_1400D3468;
      v12 = StringCchPrintfW(
              CommandLine,
              0x100u,
              L"\"%s\" /flags:0x%lx /state0:0x%lx /state1:0x%lx /testclientprocessid:0x%08x",
              L"LogonUI.exe",
              *(_QWORD *)bInheritHandles,
              *(_QWORD *)dwCreationFlags,
              lpEnvironment,
              lpCurrentDirectory);
    }
    else
    {
      LODWORD(lpEnvironment) = _wnfState.Data[1];
      dwCreationFlags[0] = _wnfState.Data[0];
      bInheritHandles[0] = dword_1400D3468;
      v12 = StringCchPrintfW(
              CommandLine,
              0x100u,
              L"\"%s\" /flags:0x%lx /state0:0x%lx /state1:0x%lx",
              L"LogonUI.exe",
              *(_QWORD *)bInheritHandles,
              *(_QWORD *)dwCreationFlags,
              lpEnvironment);
    }
    if ( v12 < 0 )
    {
      LastError = 122;
LABEL_25:
      if ( g_TraceRegHandle && (unsigned __int8)EtwEventEnabled(g_TraceRegHandle, WLEvt_WluiServerStartupFailure) )
        EtwEventWrite(g_TraceRegHandle, WLEvt_WluiServerStartupFailure, 0, 0);
      goto LABEL_28;
    }
    v13 = L"Winsta0\\Winlogon";
    StartupInfo.hStdError = 0;
    *(_OWORD *)&StartupInfo.cb = 0;
    if ( v6 )
      v13 = 0;
    StartupInfo.cb = 104;
    memset(&StartupInfo.lpTitle, 0, 72);
    StartupInfo.lpDesktop = v13;
    if ( a2 )
      v14 = CreateProcessAsUserW(a2, 0, CommandLine, 0, 0, 1, 0, 0, 0, &StartupInfo, &ProcessInformation);
    else
      v14 = CreateProcessW(0, CommandLine, 0, 0, 1, 0, 0, 0, &StartupInfo, &ProcessInformation);
    if ( !v14 )
    {
      LastError = GetLastError();
      if ( !LastError )
        goto LABEL_28;
      goto LABEL_25;
    }
    hTargetProcessHandle = ProcessInformation.hProcess;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_HangDetectionOnLogonUICallouts2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_HangDetectionOnLogonUICallouts2>::GetImpl'::`2'::impl) )
      dword_1400D346C = ProcessInformation.dwProcessId;
    CloseHandle(ProcessInformation.hThread);
    v15 = *(_QWORD *)&ProcessInformation.dwProcessId;
    *a3 = ProcessInformation.dwProcessId;
    RegisterLogonProcess(v15, 0);
  }
  if ( !v6 )
  {
    CurrentProcessId = NtCurrentPeb()->SessionId;
    if ( CurrentProcessId == (unsigned int)RtlGetCurrentServiceSessionId() )
      CurrentProcessId = RtlGetActiveConsoleId(v17, v16);
  }
  v18 = StringCchPrintfW(ObjUuid, 0x25u, L"3BDB59A0-D736-4D44-9074-C1EE%08X", CurrentProcessId);
  LastError = 0;
  if ( v18 < 0 )
    LastError = (unsigned __int16)v18;
  if ( LastError )
    goto LABEL_25;
  LastError = RpcStringBindingComposeW(ObjUuid, (RPC_WSTR)L"ncalrpc", 0, 0, 0, &String);
  if ( LastError )
    goto LABEL_25;
  LastError = RpcBindingFromStringBindingW(String, &Binding);
  if ( LastError )
    goto LABEL_25;
  if ( !v6 )
  {
    ServerPrincName[272] = 0;
    cbSid[0] = 68;
    if ( CreateWellKnownSid(WinLocalSystemSid, 0, pSid, cbSid) )
    {
      cchName[0] = 257;
      LODWORD(SecurityDescriptor) = 16;
      peUse = 0;
      if ( LookupAccountSidLocalW(pSid, Name, cchName, (LPWSTR)&EventAttributes, (LPDWORD)&SecurityDescriptor, &peUse) )
      {
        if ( (int)StringCchPrintfW(ServerPrincName, 0x111u, L"%s\\%s", &EventAttributes, Name) >= 0 )
        {
          SecurityQOS.Version = 1;
          *(_QWORD *)&SecurityQOS.Capabilities = 1;
          SecurityQOS.ImpersonationType = 2;
          while ( 1 )
          {
            LastError = RpcBindingSetAuthInfoExW(Binding, ServerPrincName, 6u, 0xAu, 0, 0, &SecurityQOS);
            if ( !LastError )
              break;
            Sleep(0x12Cu);
          }
        }
      }
    }
  }
LABEL_28:
  if ( String )
    RpcStringFreeW(&String);
  if ( LastError )
    WluiiShutdownImpl(a1);
  if ( g_TraceRegHandle && (unsigned __int8)EtwEventEnabled(g_TraceRegHandle, WLEvt_WluiServerStartup_Stop) )
    EtwEventWrite(g_TraceRegHandle, WLEvt_WluiServerStartup_Stop, 0, 0);
  return LastError;
}

```

## disassembly

```asm
0x140012360  mov     r11, rsp
0x140012363  push    rbp
0x140012364  push    rbx
0x140012365  lea     rbp, [r11-778h]
0x14001236c  sub     rsp, 868h
0x140012373  mov     rax, cs:__security_cookie
0x14001237a  xor     rax, rsp
0x14001237d  mov     [rbp+770h+var_40], rax
0x140012384  xorps   xmm0, xmm0
0x140012387  mov     [r11-20h], r12
0x14001238b  mov     [r11-28h], r13
0x14001238f  xor     eax, eax
0x140012391  xor     r13d, r13d
0x140012394  mov     [r11-30h], r14
0x140012398  mov     [r8], r13d
0x14001239b  mov     r12d, ecx
0x14001239e  mov     rcx, cs:?g_TraceRegHandle@@3_KA; unsigned __int64 g_TraceRegHandle
0x1400123a5  mov     r14, rdx
0x1400123a8  mov     [r11-38h], r15
0x1400123ac  mov     r15, r8
0x1400123af  mov     [rbp+770h+StartupInfo.hStdError], rax
0x1400123b3  mov     qword ptr [rbp+770h+ProcessInformation.dwProcessId], rax
0x1400123b7  mov     [rsp+870h+String], r13
0x1400123bc  movups  xmmword ptr [rbp+770h+StartupInfo.cb], xmm0
0x1400123c0  movups  xmmword ptr [rbp+770h+StartupInfo.lpDesktop], xmm0
0x1400123c4  movups  xmmword ptr [rbp+770h+StartupInfo.dwX], xmm0
0x1400123c8  movups  xmmword ptr [rbp+770h+StartupInfo.dwXCountChars], xmm0
0x1400123cc  movups  xmmword ptr [rbp+770h+StartupInfo.wShowWindow], xmm0
0x1400123d0  movups  xmmword ptr [rbp+770h+StartupInfo.hStdInput], xmm0
0x1400123d4  movups  xmmword ptr [rbp+770h+ProcessInformation.hProcess], xmm0
0x1400123d8  movups  xmmword ptr [rbp+770h+SecurityQOS.Version], xmm0
0x1400123dc  test    rcx, rcx
0x1400123df  jz      short loc_14001240C
0x1400123e1  lea     rdx, WLEvt_WluiServerStartup_Start
0x1400123e8  call    cs:__imp_EtwEventEnabled
0x1400123ee  test    al, al
0x1400123f0  jz      short loc_14001240C
0x1400123f2  mov     rcx, cs:?g_TraceRegHandle@@3_KA; unsigned __int64 g_TraceRegHandle
0x1400123f9  lea     rdx, WLEvt_WluiServerStartup_Start
0x140012400  xor     r9d, r9d
0x140012403  xor     r8d, r8d
0x140012406  call    cs:__imp_EtwEventWrite
0x14001240c  mov     [rsp+870h+arg_0], rsi
0x140012414  mov     [rsp+860h], rdi
0x14001241c  bt      r12d, 1Eh
0x140012421  jnb     short loc_140012432
0x140012423  mov     esi, 1
0x140012428  call    cs:__imp_GetCurrentProcessId
0x14001242e  mov     edi, eax
0x140012430  jmp     short loc_140012438
0x140012432  mov     esi, r13d
0x140012435  mov     edi, r13d
0x140012438  mov     [rsp+870h+String], r13
0x14001243d  test    r12d, r12d
0x140012440  jz      loc_140012836
0x140012446  xor     r9d, r9d; lpName
0x140012449  mov     qword ptr [rbp+770h+cchName], r13
0x14001244d  xor     r8d, r8d; bInitialState
0x140012450  mov     cs:?_wnfState@@3U_WNF_STATE_NAME@@A, r13; _WNF_STATE_NAME _wnfState
0x140012457  mov     edx, 1; bManualReset
0x14001245c  mov     qword ptr [rbp+770h+EventAttributes.nLength], 18h
0x140012464  lea     rcx, [rbp+770h+EventAttributes]; lpEventAttributes
0x140012468  mov     qword ptr [rbp+770h+EventAttributes.bInheritHandle], 1
0x140012470  mov     [rsp+870h+SecurityDescriptor], r13
0x140012475  mov     [rbp+770h+EventAttributes.lpSecurityDescriptor], r13
0x140012479  call    cs:__imp_CreateEventW
0x14001247f  mov     cs:?ServerReadyEvent@@3PEAXEA, rax; void * ServerReadyEvent
0x140012486  test    rax, rax
0x140012489  jnz     short loc_140012498
0x14001248b  call    cs:__imp_GetLastError
0x140012491  mov     ebx, eax
0x140012493  jmp     loc_140012586
0x140012498  xor     r9d, r9d; SecurityDescriptorSize
0x14001249b  lea     r8, [rsp+870h+SecurityDescriptor]; SecurityDescriptor
0x1400124a0  mov     edx, 1; StringSDRevision
0x1400124a5  lea     rcx, StringSecurityDescriptor; "D:(A;;GA;;;SY)(A;;1;;;AU)"
0x1400124ac  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1400124b2  test    eax, eax
0x1400124b4  jnz     short loc_1400124C3
0x1400124b6  call    cs:__imp_GetLastError
0x1400124bc  mov     ebx, eax
0x1400124be  jmp     loc_140012586
0x1400124c3  mov     rax, [rsp+870h+SecurityDescriptor]
0x1400124c8  lea     rcx, [rbp+770h+cchName]
0x1400124cc  mov     [rsp+870h+lpEnvironment], rax
0x1400124d1  xor     r9d, r9d
0x1400124d4  mov     [rsp+870h+dwCreationFlags], 4
0x1400124dc  xor     r8d, r8d
0x1400124df  mov     edx, 2
0x1400124e4  mov     qword ptr [rsp+870h+bInheritHandles], r13
0x1400124e9  call    cs:__imp_NtCreateWnfStateName
0x1400124ef  test    eax, eax
0x1400124f1  jns     short loc_140012502
0x1400124f3  mov     ecx, eax; Status
0x1400124f5  call    cs:__imp_RtlNtStatusToDosError
0x1400124fb  mov     ebx, eax
0x1400124fd  jmp     loc_140012586
0x140012502  mov     rdx, qword ptr [rbp+770h+cchName]
0x140012506  lea     r9, ServerStateChangedWnfCallback
0x14001250d  mov     dword ptr [rsp+870h+lpCurrentDirectory], 1
0x140012515  lea     rcx, ?_wnfSubscription@@3PEAU_WNF_USER_SUBSCRIPTION@@EA; _WNF_USER_SUBSCRIPTION * _wnfSubscription
0x14001251c  mov     dword ptr [rsp+870h+lpEnvironment], r13d
0x140012521  xor     r8d, r8d
0x140012524  mov     qword ptr [rsp+870h+dwCreationFlags], r13
0x140012529  mov     qword ptr [rsp+870h+bInheritHandles], r13
0x14001252e  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x140012534  test    eax, eax
0x140012536  jns     short loc_140012544
0x140012538  mov     ecx, eax; Status
0x14001253a  call    cs:__imp_RtlNtStatusToDosError
0x140012540  mov     ebx, eax
0x140012542  jmp     short loc_140012586
0x140012544  mov     rcx, qword ptr [rbp+770h+cchName]
0x140012548  lea     r8, [rsp+870h+cbSid]
0x14001254d  mov     r9d, 4
0x140012553  mov     [rsp+870h+cbSid], 1
0x14001255b  xor     edx, edx
0x14001255d  mov     qword ptr [rsp+870h+bInheritHandles], r13
0x140012562  call    cs:__imp_RtlPublishWnfStateData
0x140012568  test    eax, eax
0x14001256a  jns     short loc_140012578
0x14001256c  mov     ecx, eax; Status
0x14001256e  call    cs:__imp_RtlNtStatusToDosError
0x140012574  mov     ebx, eax
0x140012576  jmp     short loc_140012586
0x140012578  mov     rax, qword ptr [rbp+770h+cchName]
0x14001257c  mov     ebx, r13d
0x14001257f  mov     cs:?_wnfState@@3U_WNF_STATE_NAME@@A, rax; _WNF_STATE_NAME _wnfState
0x140012586  mov     rcx, [rsp+870h+SecurityDescriptor]; hMem
0x14001258b  test    rcx, rcx
0x14001258e  jz      short loc_14001259B
0x140012590  call    cs:__imp_LocalFree
0x140012596  mov     [rsp+870h+SecurityDescriptor], r13
0x14001259b  test    ebx, ebx
0x14001259d  jz      loc_1400126AD
0x1400125a3  mov     rcx, cs:?_wnfSubscription@@3PEAU_WNF_USER_SUBSCRIPTION@@EA; _WNF_USER_SUBSCRIPTION * _wnfSubscription
0x1400125aa  test    rcx, rcx
0x1400125ad  jz      short loc_1400125BC
0x1400125af  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x1400125b5  mov     cs:?_wnfSubscription@@3PEAU_WNF_USER_SUBSCRIPTION@@EA, r13; _WNF_USER_SUBSCRIPTION * _wnfSubscription
0x1400125bc  mov     rcx, cs:?ServerReadyEvent@@3PEAXEA; hObject
0x1400125c3  test    rcx, rcx
0x1400125c6  jz      short loc_1400125D5
0x1400125c8  call    cs:__imp_CloseHandle
0x1400125ce  mov     cs:?ServerReadyEvent@@3PEAXEA, r13; void * ServerReadyEvent
0x1400125d5  mov     rcx, cs:?g_TraceRegHandle@@3_KA; unsigned __int64 g_TraceRegHandle
0x1400125dc  test    rcx, rcx
0x1400125df  jz      short loc_14001260C
0x1400125e1  lea     rdx, WLEvt_WluiServerStartupFailure
0x1400125e8  call    cs:__imp_EtwEventEnabled
0x1400125ee  test    al, al
0x1400125f0  jz      short loc_14001260C
0x1400125f2  mov     rcx, cs:?g_TraceRegHandle@@3_KA; unsigned __int64 g_TraceRegHandle
0x1400125f9  lea     rdx, WLEvt_WluiServerStartupFailure
0x140012600  xor     r9d, r9d
0x140012603  xor     r8d, r8d
0x140012606  call    cs:__imp_EtwEventWrite
0x14001260c  cmp     [rsp+870h+String], 0
0x140012612  mov     r15, [rsp+870h+var_30]
0x14001261a  mov     r14, [rsp+870h+var_28]
0x140012622  mov     r13, [rsp+870h+var_20]
0x14001262a  mov     rdi, [rsp+860h]
0x140012632  mov     rsi, [rsp+870h+arg_0]
0x14001263a  jz      short loc_140012647
0x14001263c  lea     rcx, [rsp+870h+String]; String
0x140012641  call    cs:__imp_RpcStringFreeW
0x140012647  test    ebx, ebx
0x140012649  jz      short loc_140012653
0x14001264b  mov     ecx, r12d
0x14001264e  call    WluiiShutdownImpl
0x140012653  mov     rcx, cs:?g_TraceRegHandle@@3_KA; unsigned __int64 g_TraceRegHandle
0x14001265a  mov     r12, [rsp+870h+var_18]
0x140012662  test    rcx, rcx
0x140012665  jz      short loc_140012692
0x140012667  lea     rdx, WLEvt_WluiServerStartup_Stop
0x14001266e  call    cs:__imp_EtwEventEnabled
0x140012674  test    al, al
0x140012676  jz      short loc_140012692
0x140012678  mov     rcx, cs:?g_TraceRegHandle@@3_KA; unsigned __int64 g_TraceRegHandle
0x14001267f  lea     rdx, WLEvt_WluiServerStartup_Stop
0x140012686  xor     r9d, r9d
0x140012689  xor     r8d, r8d
0x14001268c  call    cs:__imp_EtwEventWrite
0x140012692  mov     eax, ebx
0x140012694  mov     rcx, [rbp+770h+var_40]
0x14001269b  xor     rcx, rsp; StackCookie
0x14001269e  call    __security_check_cookie
0x1400126a3  add     rsp, 868h
0x1400126aa  pop     rbx
0x1400126ab  pop     rbp
0x1400126ac  retn
0x1400126ad  mov     eax, dword ptr cs:?_wnfState@@3U_WNF_STATE_NAME@@A+4; _WNF_STATE_NAME _wnfState
0x1400126b3  lea     r9, aLogonuiExe_0; "LogonUI.exe"
0x1400126ba  lea     rcx, [rbp+770h+CommandLine]; unsigned __int16 *
0x1400126c1  mov     edx, 100h; unsigned __int64
0x1400126c6  test    esi, esi
0x1400126c8  jnz     short loc_1400126F0
0x1400126ca  mov     dword ptr [rsp+870h+lpEnvironment], eax
0x1400126ce  lea     r8, aSFlags0xLxStat_0; "\"%s\" /flags:0x%lx /state0:0x%lx /stat"...
0x1400126d5  mov     eax, dword ptr cs:?_wnfState@@3U_WNF_STATE_NAME@@A; _WNF_STATE_NAME _wnfState
0x1400126db  mov     [rsp+870h+dwCreationFlags], eax
0x1400126df  mov     eax, cs:dword_1400D3468
0x1400126e5  mov     [rsp+870h+bInheritHandles], eax
0x1400126e9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400126ee  jmp     short loc_140012718
0x1400126f0  mov     dword ptr [rsp+870h+lpCurrentDirectory], eax
0x1400126f4  lea     r8, aSFlags0xLxStat; "\"%s\" /flags:0x%lx /state0:0x%lx /stat"...
0x1400126fb  mov     eax, dword ptr cs:?_wnfState@@3U_WNF_STATE_NAME@@A; _WNF_STATE_NAME _wnfState
0x140012701  mov     dword ptr [rsp+870h+lpEnvironment], eax
0x140012705  mov     eax, cs:dword_1400D3468
0x14001270b  mov     [rsp+870h+dwCreationFlags], edi
0x14001270f  mov     [rsp+870h+bInheritHandles], eax
0x140012713  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140012718  test    eax, eax
0x14001271a  jns     short loc_140012726
0x14001271c  mov     ebx, 7Ah ; 'z'
0x140012721  jmp     loc_1400125D5
0x140012726  xorps   xmm0, xmm0
0x140012729  lea     rcx, aWinsta0Winlogo; "Winsta0\\Winlogon"
0x140012730  xor     eax, eax
0x140012732  test    esi, esi
0x140012734  mov     [rbp+770h+StartupInfo.hStdError], rax
0x140012738  movups  xmmword ptr [rbp+770h+StartupInfo.cb], xmm0
0x14001273c  cmovnz  rcx, r13
0x140012740  mov     [rbp+770h+StartupInfo.cb], 68h ; 'h'
0x140012747  xor     r9d, r9d; lpProcessAttributes
0x14001274a  lea     rax, [rbp+770h+ProcessInformation]
0x14001274e  movups  xmmword ptr [rbp+770h+StartupInfo.lpDesktop], xmm0
0x140012752  mov     [rbp+770h+StartupInfo.lpDesktop], rcx
0x140012756  movups  xmmword ptr [rbp+770h+StartupInfo.dwX], xmm0
0x14001275a  movups  xmmword ptr [rbp+770h+StartupInfo.dwXCountChars], xmm0
0x14001275e  movups  xmmword ptr [rbp+770h+StartupInfo.wShowWindow], xmm0
0x140012762  movups  xmmword ptr [rbp+770h+StartupInfo.hStdInput], xmm0
0x140012766  test    r14, r14
0x140012769  jnz     short loc_1400127A4
0x14001276b  mov     [rsp+870h+lpProcessInformation], rax; lpProcessInformation
0x140012770  lea     rdx, [rbp+770h+CommandLine]; lpCommandLine
0x140012777  lea     rax, [rbp+770h+StartupInfo]
0x14001277b  xor     r8d, r8d; lpProcessAttributes
0x14001277e  mov     [rsp+870h+lpStartupInfo], rax; lpStartupInfo
0x140012783  xor     ecx, ecx; lpApplicationName
0x140012785  mov     [rsp+870h+lpCurrentDirectory], r13; lpCurrentDirectory
0x14001278a  mov     [rsp+870h+lpEnvironment], r13; lpEnvironment
0x14001278f  mov     [rsp+870h+dwCreationFlags], r13d; dwCreationFlags
0x140012794  mov     [rsp+870h+bInheritHandles], 1; bInheritHandles
0x14001279c  call    cs:__imp_CreateProcessW
0x1400127a2  jmp     short loc_1400127E0
0x1400127a4  mov     [rsp+50h], rax; lpProcessInformation
0x1400127a9  lea     r8, [rbp+770h+CommandLine]; lpCommandLine
0x1400127b0  lea     rax, [rbp+770h+StartupInfo]
0x1400127b4  xor     edx, edx; lpApplicationName
0x1400127b6  mov     [rsp+870h+lpProcessInformation], rax; lpStartupInfo
0x1400127bb  mov     rcx, r14; hToken
0x1400127be  mov     [rsp+870h+lpStartupInfo], r13; lpCurrentDirectory
0x1400127c3  mov     [rsp+870h+lpCurrentDirectory], r13; lpEnvironment
0x1400127c8  mov     dword ptr [rsp+870h+lpEnvironment], r13d; dwCreationFlags
0x1400127cd  mov     [rsp+870h+dwCreationFlags], 1; bInheritHandles
0x1400127d5  mov     qword ptr [rsp+870h+bInheritHandles], r13; lpThreadAttributes
0x1400127da  call    cs:__imp_CreateProcessAsUserW
0x1400127e0  test    eax, eax
0x1400127e2  jnz     short loc_1400127F9
0x1400127e4  call    cs:__imp_GetLastError
0x1400127ea  mov     ebx, eax
0x1400127ec  test    eax, eax
0x1400127ee  jz      loc_14001260C
0x1400127f4  jmp     loc_1400125D5
0x1400127f9  mov     rax, [rbp+770h+ProcessInformation.hProcess]
0x1400127fd  mov     cs:hTargetProcessHandle, rax
0x140012804  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_HangDetectionOnLogonUICallouts2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_HangDetectionOnLogonUICallouts2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_HangDetectionOnLogonUICallouts2> `wil::Feature<__WilFeatureTraits_Feature_HangDetectionOnLogonUICallouts2>::GetImpl(void)'::`2'::impl
0x14001280b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_HangDetectionOnLogonUICallouts2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_HangDetectionOnLogonUICallouts2>::__private_IsEnabled(void)
0x140012810  test    al, al
0x140012812  jz      short loc_14001281D
0x140012814  mov     eax, [rbp+770h+ProcessInformation.dwProcessId]
0x140012817  mov     cs:dword_1400D346C, eax
0x14001281d  mov     rcx, [rbp+770h+ProcessInformation.hThread]; hObject
0x140012821  call    cs:__imp_CloseHandle
0x140012827  mov     rcx, qword ptr [rbp+770h+ProcessInformation.dwProcessId]
0x14001282b  xor     edx, edx
0x14001282d  mov     [r15], ecx
0x140012830  call    cs:__imp_RegisterLogonProcess
0x140012836  test    esi, esi
0x140012838  jnz     short loc_14001285B
0x14001283a  mov     rax, gs:60h
0x140012843  mov     edi, [rax+2C0h]
0x140012849  call    cs:__imp_RtlGetCurrentServiceSessionId
0x14001284f  cmp     edi, eax
0x140012851  jnz     short loc_14001285B
0x140012853  call    cs:__imp_RtlGetActiveConsoleId
0x140012859  mov     edi, eax
0x14001285b  mov     r9d, edi
0x14001285e  lea     r8, a3bdb59a0D7364d; "3BDB59A0-D736-4D44-9074-C1EE%08X"
0x140012865  mov     edx, 25h ; '%'; unsigned __int64
0x14001286a  lea     rcx, [rbp+770h+ObjUuid]; unsigned __int16 *
0x140012871  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140012876  test    eax, eax
0x140012878  movzx   ecx, ax
0x14001287b  mov     ebx, r13d
0x14001287e  cmovs   ebx, ecx
0x140012881  test    ebx, ebx
0x140012883  jnz     loc_1400125D5
  ... truncated ...
```
