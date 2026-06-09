# ServiceStarter

- ea: `0x140003cd0`
- end: `0x14000470c`
- name: `ServiceStarter`
- size: `2620`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x140001d10`
- `0x1400023b0`
- `0x1400029e0`
- `0x140003470`
- `0x140003cd0`
- `0x140004f90`
- `0x140009010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004599`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400045c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004599`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400045c6`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x14000430d`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140004572`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1400046bc`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x14000430d`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140004572`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1400046bc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140003f8d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140003f8d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140003ea7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140003f0a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140003ea7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140003f0a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400040d9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140004223`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400044b9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400040d9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140004223`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400044b9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140003d62`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140003d62`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003e59`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003e6f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140004169`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400041ff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003e59`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003e6f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140004169`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400041ff`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140003e29`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000413f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400041d5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140003e29`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000413f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400041d5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140003db5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140003de4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140003db5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140003de4`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x140003e7f`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x140003e7f`
- `ntdll!EtwEventEnabled` at `0x140004361`
- `ntdll!EtwEventEnabled` at `0x1400043e3`
- `ntdll!EtwEventEnabled` at `0x140004361`
- `ntdll!EtwEventEnabled` at `0x1400043e3`
- `ntdll!EtwEventWrite` at `0x1400043ad`
- `ntdll!EtwEventWrite` at `0x140004436`
- `ntdll!EtwEventWrite` at `0x1400043ad`
- `ntdll!EtwEventWrite` at `0x140004436`
- `ntdll!RtlInitializeCriticalSection` at `0x140003f40`
- `ntdll!RtlInitializeCriticalSection` at `0x140003f40`
- `api-ms-win-service-winsvc-l1-1-0!RegisterServiceCtrlHandlerW` at `0x140004588`
- `api-ms-win-service-winsvc-l1-1-0!RegisterServiceCtrlHandlerW` at `0x140004588`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1400045b2`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1400045b2`

## string_xrefs

- `0x140004138`: `ServiceDllUnloadOnStop`
- `0x1400041ce`: `LegacyCOMBehavior`

## pseudocode

```c
void __fastcall ServiceStarter(unsigned int a1, const WCHAR **a2)
{
  const WCHAR *v2; // rbx
  unsigned int v3; // edi
  __int64 v4; // rsi
  __int64 v5; // r14
  BOOL v6; // edi
  __int64 v7; // rdi
  DWORD v8; // r12d
  void (__fastcall *v9)(__int64); // r13
  char v10; // al
  _QWORD *v11; // rax
  const WCHAR *v12; // rcx
  BOOL v13; // r14d
  const WCHAR *v14; // rcx
  BOOL v15; // r14d
  char *v16; // rcx
  __int64 v17; // rax
  bool v18; // zf
  int v19; // eax
  __int64 v20; // rax
  __int64 v21; // rax
  char *v22; // rcx
  __int64 v23; // rax
  int v24; // eax
  SERVICE_STATUS_HANDLE v25; // rax
  DWORD LastError; // eax
  __int64 v27; // rcx
  int v28; // esi
  BYTE v29[4]; // [rsp+38h] [rbp-D0h] BYREF
  DWORD lpcbData; // [rsp+3Ch] [rbp-CCh] BYREF
  DWORD v31; // [rsp+40h] [rbp-C8h] BYREF
  unsigned int v32; // [rsp+44h] [rbp-C4h]
  BYTE Data[4]; // [rsp+48h] [rbp-C0h] BYREF
  DWORD ServiceMainFunctions; // [rsp+4Ch] [rbp-BCh]
  DWORD Type[2]; // [rsp+50h] [rbp-B8h] BYREF
  EVENT_DESCRIPTOR v36; // [rsp+58h] [rbp-B0h] BYREF
  DWORD cbData[2]; // [rsp+68h] [rbp-A0h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp-98h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-90h] BYREF
  struct _SERVICE_STATUS EventDescriptor; // [rsp+80h] [rbp-88h] BYREF
  EVENT_DESCRIPTOR v41; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v42; // [rsp+B0h] [rbp-58h] BYREF
  int v43; // [rsp+B8h] [rbp-50h]
  int v44; // [rsp+BCh] [rbp-4Ch]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+C8h] [rbp-40h] BYREF
  void *v46; // [rsp+D8h] [rbp-30h]
  int v47; // [rsp+E0h] [rbp-28h]
  int v48; // [rsp+E4h] [rbp-24h]
  void *v49; // [rsp+E8h] [rbp-20h]
  int v50; // [rsp+F0h] [rbp-18h]
  int v51; // [rsp+F4h] [rbp-14h]
  __int64 *v52; // [rsp+F8h] [rbp-10h]
  __int64 v53; // [rsp+100h] [rbp-8h]
  EVENT_DESCRIPTOR *v54; // [rsp+108h] [rbp+0h]
  __int64 v55; // [rsp+110h] [rbp+8h]

  v2 = *a2;
  v3 = 0;
  v42 = (__int64)a2;
  v32 = a1;
  *(_QWORD *)&v36.Id = 0;
  *(_QWORD *)&v41.Id = 0;
  *(_QWORD *)&EventDescriptor.dwServiceType = 0;
  if ( !ServiceCount )
    return;
  v4 = -1;
  while ( 1 )
  {
    v5 = 96LL * v3;
    if ( CompareStringOrdinal(v2, -1, *(LPCWCH *)(ServiceArray + v5), -1, 1) == 2 )
      break;
    if ( ++v3 >= ServiceCount )
      return;
  }
  *(_DWORD *)Data = 0;
  phkResult = 0;
  hKey = 0;
  v6 = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Svchost",
          0,
          0x20019u,
          &phkResult)
    && !RegOpenKeyExW(phkResult, v2, 0, 0x20019u, &hKey) )
  {
    Type[0] = 0;
    cbData[0] = 4;
    if ( !RegQueryValueExW(hKey, L"DebugBreak", 0, Type, Data, cbData) )
    {
      if ( Type[0] == 4 )
        v6 = *(_DWORD *)Data != 0;
      else
        *(_DWORD *)Data = 0;
    }
  }
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hKey )
    RegCloseKey(hKey);
  if ( v6 )
    DebugBreak();
  v7 = v5 + ServiceArray;
  if ( !(v5 + ServiceArray) )
    return;
  AcquireSRWLockExclusive((PSRWLOCK)(v7 + 32));
  *(_DWORD *)(v7 + 52) = NtCurrentTeb()->SubProcessTag;
  ServiceMainFunctions = GetServiceMainFunctions(v7, &v36, &v41, &EventDescriptor);
  v8 = ServiceMainFunctions;
  if ( ServiceMainFunctions )
  {
    ReleaseSRWLockExclusive((PSRWLOCK)(v7 + 32));
    goto LABEL_71;
  }
  v9 = *(void (__fastcall **)(__int64))&EventDescriptor.dwServiceType;
  if ( *(_QWORD *)&EventDescriptor.dwServiceType || *(_QWORD *)&v41.Id )
  {
    LOBYTE(v8) = 1;
    AcquireSRWLockExclusive(&g_pSvchostSharedGlobalsLock);
    if ( !g_pSvchostSharedGlobals )
    {
      v10 = dword_14000F224;
      if ( (dword_14000F224 & 1) == 0 )
      {
        dword_14000F228 = 0;
        if ( RtlInitializeCriticalSection(&CriticalSection) < 0 )
          goto LABEL_31;
        v10 = dword_14000F224 | 1;
        dword_14000F224 |= 1u;
      }
      if ( (v10 & 4) != 0 )
        goto LABEL_29;
      if ( (int)ScCreateWellKnownSids() >= 0 )
      {
        dword_14000F224 |= 4u;
LABEL_29:
        v11 = HeapAlloc(g_hHeap, 8u, 0xE0u);
        g_pSvchostSharedGlobals = (__int64)v11;
        if ( v11 )
        {
          *(_DWORD *)v11 = 1;
          v11[1] = NullSid;
          v11[2] = WorldSid;
          v11[3] = LocalSid;
          v11[4] = NetworkSid;
          v11[5] = LocalSystemSid;
          v11[6] = LocalServiceSid;
          v11[7] = NetworkServiceSid;
          v11[8] = BuiltinDomainSid;
          v11[9] = AuthenticatedUserSid;
          v11[10] = AnonymousLogonSid;
          v11[11] = AliasAdminsSid;
          v11[12] = AliasUsersSid;
          v11[13] = AliasGuestsSid;
          v11[14] = AliasPowerUsersSid;
          v11[15] = AliasAccountOpsSid;
          v11[16] = AliasSystemOpsSid;
          v11[17] = AliasPrintOpsSid;
          v11[18] = AliasBackupOpsSid;
          v11[19] = RpcpStartRpcServer;
          v11[20] = RpcpStopRpcServer;
          v11[21] = RpcpStopRpcServerEx;
          v11[26] = SvcRegisterStopCallback;
          v11[27] = SvcUnregisterStopCallback;
          v11[25] = SvcDeprecatedRegisterStopCallback;
        }
      }
    }
LABEL_31:
    ReleaseSRWLockExclusive(&g_pSvchostSharedGlobalsLock);
  }
  v12 = *(const WCHAR **)v7;
  ++*(_DWORD *)(v7 + 48);
  v31 = 0;
  v13 = 0;
  lpcbData = 0;
  *(_DWORD *)v29 = 0;
  *(_QWORD *)&EventDescriptor.dwServiceType = 0;
  if ( !(unsigned int)OpenServiceParametersKey(v12, (PHKEY)&EventDescriptor) )
  {
    lpcbData = 4;
    if ( !RegQueryValueExW(*(HKEY *)&EventDescriptor.dwServiceType, L"ServiceDllUnloadOnStop", 0, &v31, v29, &lpcbData)
      && v31 == 4 )
    {
      v13 = *(_DWORD *)v29 != 0;
    }
  }
  if ( *(_QWORD *)&EventDescriptor.dwServiceType )
    RegCloseKey(*(HKEY *)&EventDescriptor.dwServiceType);
  if ( v13 )
    *(_DWORD *)(v7 + 88) = 1;
  v14 = *(const WCHAR **)v7;
  v31 = 0;
  v15 = 0;
  *(_DWORD *)v29 = 0;
  lpcbData = 0;
  *(_QWORD *)&EventDescriptor.dwServiceType = 0;
  if ( !(unsigned int)OpenServiceParametersKey(v14, (PHKEY)&EventDescriptor) )
  {
    *(_DWORD *)v29 = 4;
    if ( !RegQueryValueExW(
            *(HKEY *)&EventDescriptor.dwServiceType,
            L"LegacyCOMBehavior",
            0,
            &v31,
            (LPBYTE)&lpcbData,
            (LPDWORD)v29)
      && v31 == 4 )
    {
      v15 = lpcbData != 0;
    }
  }
  if ( *(_QWORD *)&EventDescriptor.dwServiceType )
    RegCloseKey(*(HKEY *)&EventDescriptor.dwServiceType);
  if ( v15 )
    ShouldCoUninit = 0;
  ReleaseSRWLockExclusive((PSRWLOCK)(v7 + 32));
  if ( (_BYTE)v8 && g_pSvchostSharedGlobals )
  {
    if ( (unsigned int)dword_14000F000 > 5 )
    {
      v16 = *(char **)v7;
      if ( *(_QWORD *)v7 )
      {
        v17 = -1;
        do
          v18 = *(_WORD *)&v16[2 * v17++ + 2] == 0;
        while ( !v18 );
        v19 = 2 * v17 + 2;
      }
      else
      {
        v16 = "";
        v19 = 2;
      }
      v50 = v19;
      EventDescriptor.dwCurrentState = 5;
      UserData.Ptr = (ULONGLONG)off_14000F008;
      v49 = v16;
      v51 = 0;
      EventDescriptor.dwServiceType = 184549376;
      *(_QWORD *)&EventDescriptor.dwControlsAccepted = 0;
      UserData.Size = *(unsigned __int16 *)off_14000F008;
      v46 = &unk_14000B9CC;
      v48 = 1;
      UserData.Reserved = 2;
      v47 = 32;
      *(_DWORD *)v29 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, (PCEVENT_DESCRIPTOR)&EventDescriptor, 0, 0, 3u, &UserData);
    }
    if ( v9 )
      v9(g_pSvchostSharedGlobals);
    else
      (*(void (__fastcall **)(__int64))&v41.Id)(g_pSvchostSharedGlobals + 8);
  }
  if ( PerfRegHandle && (unsigned __int8)EtwEventEnabled(PerfRegHandle, &SvchostEvt_ServiceMain_Start) )
  {
    v20 = -1;
    do
      v18 = v2[++v20] == 0;
    while ( !v18 );
    v41.Keyword = (unsigned int)(2 * v20 + 2);
    *(_QWORD *)&v41.Id = v2;
    EtwEventWrite(PerfRegHandle, &SvchostEvt_ServiceMain_Start, 1, &v41);
  }
  (*(void (__fastcall **)(_QWORD, __int64))&v36.Id)(v32, v42);
  if ( PerfRegHandle && (unsigned __int8)EtwEventEnabled(PerfRegHandle, "f") )
  {
    v21 = -1;
    do
      v18 = v2[++v21] == 0;
    while ( !v18 );
    v43 = 2 * v21 + 2;
    v42 = (__int64)v2;
    v44 = 0;
    EtwEventWrite(PerfRegHandle, "f", 1, &v42);
  }
  v8 = ServiceMainFunctions;
LABEL_71:
  if ( *(_QWORD *)&v36.Id )
  {
    DecrementDllReferenceCount(v7);
  }
  else
  {
    EventDescriptor.dwCurrentState = 1;
    EventDescriptor.dwControlsAccepted = 1;
    EventDescriptor.dwServiceType = 48;
    *(_QWORD *)&EventDescriptor.dwCheckPoint = 0;
    EventDescriptor.dwWin32ExitCode = v8;
    EventDescriptor.dwServiceSpecificExitCode = 0;
    if ( (unsigned int)dword_14000F000 > 5 )
    {
      if ( v2 )
      {
        v22 = (char *)v2;
        v23 = -1;
        do
          v18 = v2[++v23] == 0;
        while ( !v18 );
        v24 = 2 * v23 + 2;
      }
      else
      {
        v22 = "";
        v24 = 2;
      }
      v50 = v24;
      v49 = v22;
      v51 = 0;
      v53 = 8;
      *(_DWORD *)&v36.Id = 184549376;
      v36.Keyword = 0;
      v42 = v8;
      v52 = &v42;
      *(_DWORD *)&v36.Level = 5;
      UserData.Ptr = (ULONGLONG)off_14000F008;
      UserData.Size = *(unsigned __int16 *)off_14000F008;
      v46 = &unk_14000BBA9;
      UserData.Reserved = 2;
      v47 = 43;
      v48 = 1;
      v32 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &v36, 0, 0, 4u, &UserData);
    }
    v25 = RegisterServiceCtrlHandlerW(v2, DummySvchostCtrlHandler);
    if ( v25 )
    {
      if ( SetServiceStatus(v25, &EventDescriptor) )
        return;
      LastError = GetLastError();
      v27 = 2;
    }
    else
    {
      LastError = GetLastError();
      v27 = 1;
    }
    if ( LastError && (unsigned int)dword_14000F000 > 5 )
    {
      if ( v2 )
      {
        do
          v18 = v2[++v4] == 0;
        while ( !v18 );
        v28 = 2 * v4 + 2;
      }
      else
      {
        v2 = (const WCHAR *)"";
        v28 = 2;
      }
      v42 = v27;
      v52 = &v42;
      v49 = (void *)v2;
      v50 = v28;
      v51 = 0;
      v53 = 8;
      v55 = 8;
      *(_DWORD *)&v41.Id = 184549376;
      v41.Keyword = 0;
      *(_QWORD *)&v36.Id = v8;
      v54 = &v36;
      *(_DWORD *)&v41.Level = 5;
      UserData.Ptr = (ULONGLONG)off_14000F008;
      UserData.Size = *(unsigned __int16 *)off_14000F008;
      v46 = &unk_14000BB61;
      UserData.Reserved = 2;
      v47 = 60;
      v48 = 1;
      v32 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &v41, 0, 0, 5u, &UserData);
    }
  }
}

```

## disassembly

```asm
0x140003cd0  mov     r11, rsp
0x140003cd3  push    rbp
0x140003cd4  push    rbx
0x140003cd5  push    rdi
0x140003cd6  push    r13
0x140003cd8  lea     rbp, [r11-58h]
0x140003cdc  sub     rsp, 138h
0x140003ce3  mov     rax, cs:__security_cookie
0x140003cea  xor     rax, rsp
0x140003ced  mov     [rbp+50h+var_40], rax
0x140003cf1  mov     rbx, [rdx]
0x140003cf4  xor     r13d, r13d
0x140003cf7  cmp     cs:ServiceCount, r13d
0x140003cfe  mov     edi, r13d
0x140003d01  mov     [rbp+50h+var_A8], rdx
0x140003d05  mov     [rsp+150h+var_114], ecx
0x140003d09  mov     qword ptr [rsp+150h+var_100.Id], r13
0x140003d0e  mov     qword ptr [rbp+50h+var_B8.Id], r13
0x140003d12  mov     qword ptr [rsp+150h+EventDescriptor.Id], r13
0x140003d17  jbe     loc_1400046F2
0x140003d1d  mov     [r11+18h], rsi
0x140003d21  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x140003d28  mov     [r11-30h], r14
0x140003d2c  mov     [r11-38h], r15
0x140003d30  mov     r15d, 1
0x140003d36  nop     word ptr [rax+rax+00000000h]
0x140003d40  mov     r8, cs:ServiceArray
0x140003d47  mov     r9d, esi; cchCount2
0x140003d4a  mov     eax, edi
0x140003d4c  mov     edx, esi; cchCount1
0x140003d4e  mov     rcx, rbx; lpString1
0x140003d51  mov     [rsp+150h+bIgnoreCase], r15d; bIgnoreCase
0x140003d56  lea     r14, [rax+rax*2]
0x140003d5a  shl     r14, 5
0x140003d5e  mov     r8, [r8+r14]; lpString2
0x140003d62  call    cs:__imp_CompareStringOrdinal
0x140003d69  nop     dword ptr [rax+rax+00h]
0x140003d6e  cmp     eax, 2
0x140003d71  jz      short loc_140003D82
0x140003d73  inc     edi
0x140003d75  cmp     edi, cs:ServiceCount
0x140003d7b  jb      short loc_140003D40
0x140003d7d  jmp     loc_1400046DA
0x140003d82  lea     rax, [rsp+150h+phkResult]
0x140003d87  mov     dword ptr [rsp+150h+Data], r13d
0x140003d8c  mov     r9d, 20019h; samDesired
0x140003d92  mov     qword ptr [rsp+150h+bIgnoreCase], rax; phkResult
0x140003d97  xor     r8d, r8d; ulOptions
0x140003d9a  mov     [rsp+150h+phkResult], r13
0x140003d9f  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows NT\\Curren"...
0x140003da6  mov     [rsp+150h+hKey], r13
0x140003dab  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140003db2  mov     edi, r13d
0x140003db5  call    cs:__imp_RegOpenKeyExW
0x140003dbc  nop     dword ptr [rax+rax+00h]
0x140003dc1  test    eax, eax
0x140003dc3  jnz     loc_140003E4F
0x140003dc9  mov     rcx, [rsp+150h+phkResult]; hKey
0x140003dce  lea     rax, [rsp+150h+hKey]
0x140003dd3  mov     r9d, 20019h; samDesired
0x140003dd9  mov     qword ptr [rsp+150h+bIgnoreCase], rax; phkResult
0x140003dde  xor     r8d, r8d; ulOptions
0x140003de1  mov     rdx, rbx; lpSubKey
0x140003de4  call    cs:__imp_RegOpenKeyExW
0x140003deb  nop     dword ptr [rax+rax+00h]
0x140003df0  test    eax, eax
0x140003df2  jnz     short loc_140003E4F
0x140003df4  mov     rcx, [rsp+150h+hKey]; hKey
0x140003df9  lea     rax, [rsp+150h+cbData]
0x140003dfe  mov     [rsp+150h+lpcbData], rax; lpcbData
0x140003e03  lea     r9, [rsp+150h+Type]; lpType
0x140003e08  lea     rax, [rsp+150h+Data]
0x140003e0d  mov     [rsp+150h+Type], r13d
0x140003e12  xor     r8d, r8d; lpReserved
0x140003e15  mov     qword ptr [rsp+150h+bIgnoreCase], rax; lpData
0x140003e1a  lea     rdx, aDebugbreak; "DebugBreak"
0x140003e21  mov     [rsp+150h+cbData], 4
0x140003e29  call    cs:__imp_RegQueryValueExW
0x140003e30  nop     dword ptr [rax+rax+00h]
0x140003e35  test    eax, eax
0x140003e37  jnz     short loc_140003E4F
0x140003e39  cmp     [rsp+150h+Type], 4
0x140003e3e  jz      short loc_140003E47
0x140003e40  mov     dword ptr [rsp+150h+Data], r13d
0x140003e45  jmp     short loc_140003E4F
0x140003e47  cmp     dword ptr [rsp+150h+Data], edi
0x140003e4b  cmovnz  edi, r15d
0x140003e4f  mov     rcx, [rsp+150h+phkResult]; hKey
0x140003e54  test    rcx, rcx
0x140003e57  jz      short loc_140003E65
0x140003e59  call    cs:__imp_RegCloseKey
0x140003e60  nop     dword ptr [rax+rax+00h]
0x140003e65  mov     rcx, [rsp+150h+hKey]; hKey
0x140003e6a  test    rcx, rcx
0x140003e6d  jz      short loc_140003E7B
0x140003e6f  call    cs:__imp_RegCloseKey
0x140003e76  nop     dword ptr [rax+rax+00h]
0x140003e7b  test    edi, edi
0x140003e7d  jz      short loc_140003E8B
0x140003e7f  call    cs:__imp_DebugBreak
0x140003e86  nop     dword ptr [rax+rax+00h]
0x140003e8b  mov     rdi, cs:ServiceArray
0x140003e92  add     rdi, r14
0x140003e95  jz      loc_1400046DA
0x140003e9b  lea     rcx, [rdi+20h]; SRWLock
0x140003e9f  mov     [rsp+130h], r12
0x140003ea7  call    cs:__imp_AcquireSRWLockExclusive
0x140003eae  nop     dword ptr [rax+rax+00h]
0x140003eb3  mov     rax, gs:1720h
0x140003ebc  lea     r9, [rsp+150h+EventDescriptor]
0x140003ec1  lea     r8, [rbp+50h+var_B8]
0x140003ec5  mov     [rdi+34h], eax
0x140003ec8  lea     rdx, [rsp+150h+var_100]
0x140003ecd  mov     rcx, rdi
0x140003ed0  call    GetServiceMainFunctions
0x140003ed5  mov     [rsp+150h+var_10C], eax
0x140003ed9  mov     r12d, eax
0x140003edc  lea     r14, _TraceLoggingMetadataEnd
0x140003ee3  test    eax, eax
0x140003ee5  jnz     loc_1400044B5
0x140003eeb  mov     r13, qword ptr [rsp+150h+EventDescriptor.Id]
0x140003ef0  test    r13, r13
0x140003ef3  jnz     short loc_140003EFF
0x140003ef5  cmp     qword ptr [rbp+50h+var_B8.Id], r13
0x140003ef9  jz      loc_1400040E5
0x140003eff  lea     rcx, g_pSvchostSharedGlobalsLock; SRWLock
0x140003f06  movzx   r12d, r15b
0x140003f0a  call    cs:__imp_AcquireSRWLockExclusive
0x140003f11  nop     dword ptr [rax+rax+00h]
0x140003f16  cmp     cs:g_pSvchostSharedGlobals, 0
0x140003f1e  jnz     loc_1400040D2
0x140003f24  mov     eax, cs:dword_14000F224
0x140003f2a  test    r15b, al
0x140003f2d  jnz     short loc_140003F63
0x140003f2f  xor     r14d, r14d
0x140003f32  lea     rcx, CriticalSection; CriticalSection
0x140003f39  mov     cs:dword_14000F228, r14d
0x140003f40  call    cs:__imp_RtlInitializeCriticalSection
0x140003f47  nop     dword ptr [rax+rax+00h]
0x140003f4c  test    eax, eax
0x140003f4e  js      loc_1400040D2
0x140003f54  mov     eax, cs:dword_14000F224
0x140003f5a  or      eax, r15d
0x140003f5d  mov     cs:dword_14000F224, eax
0x140003f63  test    al, 4
0x140003f65  jnz     short loc_140003F7B
0x140003f67  call    ScCreateWellKnownSids
0x140003f6c  test    eax, eax
0x140003f6e  js      loc_1400040D2
0x140003f74  or      cs:dword_14000F224, 4
0x140003f7b  mov     rcx, cs:g_hHeap; hHeap
0x140003f82  mov     edx, 8; dwFlags
0x140003f87  mov     r8d, 0E0h; dwBytes
0x140003f8d  call    cs:__imp_HeapAlloc
0x140003f94  nop     dword ptr [rax+rax+00h]
0x140003f99  mov     cs:g_pSvchostSharedGlobals, rax
0x140003fa0  mov     rdx, rax
0x140003fa3  test    rax, rax
0x140003fa6  jz      loc_1400040D2
0x140003fac  mov     [rax], r15d
0x140003faf  mov     rcx, cs:NullSid
0x140003fb6  mov     [rax+8], rcx
0x140003fba  mov     rcx, cs:WorldSid
0x140003fc1  mov     [rax+10h], rcx
0x140003fc5  mov     rcx, cs:LocalSid
0x140003fcc  mov     [rax+18h], rcx
0x140003fd0  mov     rcx, cs:NetworkSid
0x140003fd7  mov     [rax+20h], rcx
0x140003fdb  mov     rax, cs:LocalSystemSid
0x140003fe2  mov     [rdx+28h], rax
0x140003fe6  mov     rax, cs:LocalServiceSid
0x140003fed  mov     [rdx+30h], rax
0x140003ff1  mov     rax, cs:NetworkServiceSid
0x140003ff8  mov     [rdx+38h], rax
0x140003ffc  mov     rax, cs:BuiltinDomainSid
0x140004003  mov     [rdx+40h], rax
0x140004007  mov     rax, cs:AuthenticatedUserSid
0x14000400e  mov     [rdx+48h], rax
0x140004012  mov     rax, cs:AnonymousLogonSid
0x140004019  mov     [rdx+50h], rax
0x14000401d  mov     rax, cs:AliasAdminsSid
0x140004024  mov     [rdx+58h], rax
0x140004028  mov     rax, cs:AliasUsersSid
0x14000402f  mov     [rdx+60h], rax
0x140004033  mov     rax, cs:AliasGuestsSid
0x14000403a  mov     [rdx+68h], rax
0x14000403e  mov     rax, cs:AliasPowerUsersSid
0x140004045  mov     [rdx+70h], rax
0x140004049  mov     rax, cs:AliasAccountOpsSid
0x140004050  mov     [rdx+78h], rax
0x140004054  mov     rax, cs:AliasSystemOpsSid
0x14000405b  mov     [rdx+80h], rax
0x140004062  mov     rax, cs:AliasPrintOpsSid
0x140004069  mov     [rdx+88h], rax
0x140004070  mov     rax, cs:AliasBackupOpsSid
0x140004077  mov     [rdx+90h], rax
0x14000407e  lea     rax, RpcpStartRpcServer
0x140004085  mov     [rdx+98h], rax
0x14000408c  lea     rax, RpcpStopRpcServer
0x140004093  mov     [rdx+0A0h], rax
0x14000409a  lea     rax, RpcpStopRpcServerEx
0x1400040a1  mov     [rdx+0A8h], rax
0x1400040a8  lea     rax, SvcRegisterStopCallback
0x1400040af  mov     [rdx+0D0h], rax
0x1400040b6  lea     rax, SvcUnregisterStopCallback
0x1400040bd  mov     [rdx+0D8h], rax
0x1400040c4  lea     rax, SvcDeprecatedRegisterStopCallback
0x1400040cb  mov     [rdx+0C8h], rax
0x1400040d2  lea     rcx, g_pSvchostSharedGlobalsLock; SRWLock
0x1400040d9  call    cs:__imp_ReleaseSRWLockExclusive
0x1400040e0  nop     dword ptr [rax+rax+00h]
0x1400040e5  mov     rcx, [rdi]; lpSubKey
0x1400040e8  lea     rdx, [rsp+150h+EventDescriptor]; phkResult
0x1400040ed  inc     dword ptr [rdi+30h]
0x1400040f0  xor     eax, eax
0x1400040f2  mov     [rsp+150h+var_118], eax
0x1400040f6  mov     r14d, eax
0x1400040f9  mov     [rsp+150h+var_11C], eax
0x1400040fd  mov     dword ptr [rsp+150h+var_120], eax
0x140004101  mov     qword ptr [rsp+150h+EventDescriptor.Id], rax
0x140004106  call    OpenServiceParametersKey
0x14000410b  test    eax, eax
0x14000410d  jnz     short loc_14000415F
0x14000410f  mov     rcx, qword ptr [rsp+150h+EventDescriptor.Id]; hKey
0x140004114  lea     rax, [rsp+150h+var_11C]
0x140004119  mov     [rsp+150h+lpcbData], rax; lpcbData
0x14000411e  lea     r9, [rsp+150h+var_118]; lpType
0x140004123  lea     rax, [rsp+150h+var_120]
0x140004128  mov     [rsp+150h+var_11C], 4
0x140004130  xor     r8d, r8d; lpReserved
0x140004133  mov     qword ptr [rsp+150h+bIgnoreCase], rax; lpData
0x140004138  lea     rdx, aServicedllunlo; "ServiceDllUnloadOnStop"
0x14000413f  call    cs:__imp_RegQueryValueExW
0x140004146  nop     dword ptr [rax+rax+00h]
0x14000414b  test    eax, eax
0x14000414d  jnz     short loc_14000415F
0x14000414f  cmp     [rsp+150h+var_118], 4
0x140004154  jnz     short loc_14000415F
0x140004156  cmp     dword ptr [rsp+150h+var_120], r14d
0x14000415b  cmovnz  r14d, r15d
0x14000415f  mov     rcx, qword ptr [rsp+150h+EventDescriptor.Id]; hKey
0x140004164  test    rcx, rcx
0x140004167  jz      short loc_140004175
0x140004169  call    cs:__imp_RegCloseKey
0x140004170  nop     dword ptr [rax+rax+00h]
0x140004175  test    r14d, r14d
0x140004178  jz      short loc_14000417E
0x14000417a  mov     [rdi+58h], r15d
0x14000417e  mov     rcx, [rdi]; lpSubKey
0x140004181  lea     rdx, [rsp+150h+EventDescriptor]; phkResult
0x140004186  xor     eax, eax
0x140004188  mov     [rsp+150h+var_118], eax
0x14000418c  mov     r14d, eax
0x14000418f  mov     dword ptr [rsp+150h+var_120], eax
0x140004193  mov     [rsp+150h+var_11C], eax
0x140004197  mov     qword ptr [rsp+150h+EventDescriptor.Id], rax
0x14000419c  call    OpenServiceParametersKey
0x1400041a1  test    eax, eax
0x1400041a3  jnz     short loc_1400041F5
0x1400041a5  mov     rcx, qword ptr [rsp+150h+EventDescriptor.Id]; hKey
0x1400041aa  lea     rax, [rsp+150h+var_120]
0x1400041af  mov     [rsp+150h+lpcbData], rax; lpcbData
0x1400041b4  lea     r9, [rsp+150h+var_118]; lpType
0x1400041b9  lea     rax, [rsp+150h+var_11C]
0x1400041be  mov     dword ptr [rsp+150h+var_120], 4
0x1400041c6  xor     r8d, r8d; lpReserved
0x1400041c9  mov     qword ptr [rsp+150h+bIgnoreCase], rax; lpData
0x1400041ce  lea     rdx, aLegacycombehav; "LegacyCOMBehavior"
0x1400041d5  call    cs:__imp_RegQueryValueExW
0x1400041dc  nop     dword ptr [rax+rax+00h]
0x1400041e1  test    eax, eax
0x1400041e3  jnz     short loc_1400041F5
0x1400041e5  cmp     [rsp+150h+var_118], 4
0x1400041ea  jnz     short loc_1400041F5
0x1400041ec  cmp     [rsp+150h+var_11C], r14d
0x1400041f1  cmovnz  r14d, r15d
0x1400041f5  mov     rcx, qword ptr [rsp+150h+EventDescriptor.Id]; hKey
0x1400041fa  test    rcx, rcx
0x1400041fd  jz      short loc_14000420B
0x1400041ff  call    cs:__imp_RegCloseKey
0x140004206  nop     dword ptr [rax+rax+00h]
0x14000420b  test    r14d, r14d
0x14000420e  jz      short loc_14000421C
0x140004210  xor     r14d, r14d
0x140004213  mov     cs:ShouldCoUninit, r14d
0x14000421a  jmp     short loc_14000421F
0x14000421c  xor     r14d, r14d
0x14000421f  lea     rcx, [rdi+20h]; SRWLock
0x140004223  call    cs:__imp_ReleaseSRWLockExclusive
0x14000422a  nop     dword ptr [rax+rax+00h]
0x14000422f  test    r12b, r12b
0x140004232  jz      loc_140004347
0x140004238  cmp     cs:g_pSvchostSharedGlobals, 0
0x140004240  jz      loc_140004347
0x140004246  mov     eax, cs:dword_14000F000
0x14000424c  cmp     eax, 5
0x14000424f  jbe     loc_14000431B
0x140004255  mov     rcx, [rdi]
0x140004258  test    rcx, rcx
0x14000425b  jz      short loc_140004275
  ... truncated ...
```
