# DrvUpdateGraphicsDeviceList

- ea: `0x14018c750`
- end: `0x14018d354`
- name: `DrvUpdateGraphicsDeviceList`
- size: `3076`
- prototype: ``
- caller_count: `5`
- callee_count: `26`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14002bfc0`
- `0x1400bb7e0`
- `0x1401017cc`
- `0x1401cd284`
- `0x1401cdaac`

## callees

- `0x14002aa70`
- `0x140040394`
- `0x1400630e0`
- `0x14009202c`
- `0x1400bb7b0`
- `0x1400c37a0`
- `0x1400c3a20`
- `0x1400c3fb0`
- `0x1400c44b8`
- `0x1400c5dc0`
- `0x1400c661c`
- `0x1400c6710`
- `0x14010f2b0`
- `0x14015e96c`
- `0x140169ddc`
- `0x14016c5a8`
- `0x14017b360`
- `0x14018076c`
- `0x140188600`
- `0x14018c750`
- `0x14018d35c`
- `0x1401b404c`
- `0x1401ba240`
- `0x140238aee`
- `0x140238b10`
- `0x140238bf0`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14018cc76`
- `ntoskrnl!ZwClose` at `0x14018ccf6`
- `ntoskrnl!ZwClose` at `0x14018cd6a`
- `ntoskrnl!ZwClose` at `0x14018cc76`
- `ntoskrnl!ZwClose` at `0x14018ccf6`
- `ntoskrnl!ZwClose` at `0x14018cd6a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14018cc2b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14018cc2b`
- `ntoskrnl!RtlQueryRegistryValues` at `0x14018c8cd`
- `ntoskrnl!RtlQueryRegistryValues` at `0x14018c8cd`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14018cafd`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14018cafd`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x14018caa2`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x14018caa2`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x14018cc4a`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x14018cc4a`
- `ntoskrnl!swprintf_s` at `0x14018cc9b`
- `ntoskrnl!swprintf_s` at `0x14018cfcf`
- `ntoskrnl!swprintf_s` at `0x14018cc9b`
- `ntoskrnl!swprintf_s` at `0x14018cfcf`
- `ntoskrnl!RtlInitUnicodeString` at `0x14018ca87`
- `ntoskrnl!RtlInitUnicodeString` at `0x14018ca87`
- `ntoskrnl!ObfDereferenceObject` at `0x14018cc85`
- `ntoskrnl!ObfDereferenceObject` at `0x14018cc85`
- `watchdog!WdLogSingleEntry0` at `0x14018cf07`
- `watchdog!WdLogSingleEntry0` at `0x14018d18d`
- `watchdog!WdLogSingleEntry0` at `0x14018d1f1`
- `watchdog!WdLogSingleEntry0` at `0x14018d20e`
- `watchdog!WdLogSingleEntry0` at `0x14018d2a6`
- `watchdog!WdLogSingleEntry0` at `0x14018cf07`
- `watchdog!WdLogSingleEntry0` at `0x14018d18d`
- `watchdog!WdLogSingleEntry0` at `0x14018d1f1`
- `watchdog!WdLogSingleEntry0` at `0x14018d20e`
- `watchdog!WdLogSingleEntry0` at `0x14018d2a6`
- `watchdog!WdLogSingleEntry1` at `0x14018c91e`
- `watchdog!WdLogSingleEntry1` at `0x14018cd9b`
- `watchdog!WdLogSingleEntry1` at `0x14018ce22`
- `watchdog!WdLogSingleEntry1` at `0x14018d31b`
- `watchdog!WdLogSingleEntry1` at `0x14018c91e`
- `watchdog!WdLogSingleEntry1` at `0x14018cd9b`
- `watchdog!WdLogSingleEntry1` at `0x14018ce22`
- `watchdog!WdLogSingleEntry1` at `0x14018d31b`
- `watchdog!WdLogSingleEntry2` at `0x14018c7c2`
- `watchdog!WdLogSingleEntry2` at `0x14018ce6c`
- `watchdog!WdLogSingleEntry2` at `0x14018c7c2`
- `watchdog!WdLogSingleEntry2` at `0x14018ce6c`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x14018c8ec`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x14018d09e`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x14018c8ec`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x14018d09e`
- `WIN32K!W32GetSessionState` at `0x14018c7d8`
- `WIN32K!W32GetSessionState` at `0x14018d057`
- `WIN32K!W32GetSessionState` at `0x14018d1c4`
- `WIN32K!W32GetSessionState` at `0x14018c7d8`
- `WIN32K!W32GetSessionState` at `0x14018d057`
- `WIN32K!W32GetSessionState` at `0x14018d1c4`
- `WIN32K!W32GetUserSessionState` at `0x14018cabf`
- `WIN32K!W32GetUserSessionState` at `0x14018cb63`
- `WIN32K!W32GetUserSessionState` at `0x14018cba7`
- `WIN32K!W32GetUserSessionState` at `0x14018cbcc`
- `WIN32K!W32GetUserSessionState` at `0x14018cf1d`
- `WIN32K!W32GetUserSessionState` at `0x14018d010`
- `WIN32K!W32GetUserSessionState` at `0x14018d03e`
- `WIN32K!W32GetUserSessionState` at `0x14018d0fa`
- `WIN32K!W32GetUserSessionState` at `0x14018d1af`
- `WIN32K!W32GetUserSessionState` at `0x14018cabf`
- `WIN32K!W32GetUserSessionState` at `0x14018cb63`
- `WIN32K!W32GetUserSessionState` at `0x14018cba7`
- `WIN32K!W32GetUserSessionState` at `0x14018cbcc`
- `WIN32K!W32GetUserSessionState` at `0x14018cf1d`
- `WIN32K!W32GetUserSessionState` at `0x14018d010`
- `WIN32K!W32GetUserSessionState` at `0x14018d03e`
- `WIN32K!W32GetUserSessionState` at `0x14018d0fa`
- `WIN32K!W32GetUserSessionState` at `0x14018d1af`

## pseudocode

```c
__int64 __fastcall DrvUpdateGraphicsDeviceList(__int64 a1)
{
  __int64 v1; // r14
  __int64 IsConsoleConnection; // r13
  __int64 v3; // rcx
  __int64 v4; // rdi
  int *v5; // r9
  int *v6; // r8
  __int64 *v7; // rdx
  __int64 *v8; // rcx
  _DWORD *v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rdx
  int v12; // r8d
  int v13; // r9d
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 DxgkWin32kInterface; // rax
  int v18; // eax
  __int64 v19; // rdx
  __int64 v20; // rcx
  unsigned int v21; // eax
  char v22; // bl
  __int64 v23; // rcx
  const wchar_t *v24; // r9
  int v25; // eax
  __int64 v26; // rbx
  __int64 *v27; // rax
  __int64 v28; // r14
  NTSTATUS DeviceObjectPointer; // eax
  __int64 v30; // rcx
  struct _FILE_OBJECT *v31; // rax
  __int64 v32; // rsi
  PDEVICE_OBJECT v33; // rcx
  unsigned int *v34; // r12
  __int64 v35; // rcx
  struct _DEVICE_OBJECT *v36; // rbx
  HANDLE v37; // rax
  unsigned __int16 *v38; // rax
  HANDLE RegistryHandleFromDeviceMap; // rax
  int v40; // eax
  struct _DEVICE_OBJECT *v41; // rcx
  __int64 v42; // rcx
  __int64 UserSessionState; // rax
  __int64 v44; // rax
  wchar_t *v45; // rcx
  int PruneFlag; // eax
  unsigned int v47; // edx
  __int64 v48; // rcx
  __int64 v49; // rcx
  __int64 v50; // rax
  __int64 v51; // rdx
  __int64 v52; // r8
  __int64 v53; // rax
  __int64 v54; // rax
  int v55; // eax
  unsigned int v56; // eax
  __int64 result; // rax
  __int64 v58; // rcx
  __int64 SessionState; // rax
  int v60; // eax
  __int64 v61; // rcx
  __int64 v62; // rdx
  int v63; // r8d
  int v64; // r9d
  unsigned int v65; // ebx
  PVOID Environment; // [rsp+20h] [rbp-E0h]
  char v67; // [rsp+50h] [rbp-B0h]
  NTSTATUS updated; // [rsp+54h] [rbp-ACh] BYREF
  _BYTE v69[4]; // [rsp+58h] [rbp-A8h] BYREF
  int v70; // [rsp+5Ch] [rbp-A4h]
  unsigned int v71; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v72; // [rsp+64h] [rbp-9Ch] BYREF
  void *DeviceRegKey; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v74[2]; // [rsp+70h] [rbp-90h] BYREF
  PFILE_OBJECT FileObject; // [rsp+78h] [rbp-88h] BYREF
  PDEVICE_OBJECT DeviceObject; // [rsp+80h] [rbp-80h] BYREF
  PVOID P; // [rsp+88h] [rbp-78h] BYREF
  __int128 InputBuffer; // [rsp+90h] [rbp-70h] BYREF
  __int128 v79; // [rsp+A0h] [rbp-60h]
  __int64 v80; // [rsp+B0h] [rbp-50h]
  __int128 v81; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v82; // [rsp+C8h] [rbp-38h]
  struct _UNICODE_STRING DestinationString; // [rsp+D8h] [rbp-28h] BYREF
  struct _RTL_QUERY_REGISTRY_TABLE QueryTable; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v85; // [rsp+128h] [rbp+28h]
  int v86; // [rsp+130h] [rbp+30h]
  __int64 v87; // [rsp+138h] [rbp+38h]
  __int128 v88; // [rsp+140h] [rbp+40h]
  __int128 v89; // [rsp+150h] [rbp+50h]

  v1 = (int)a1;
  v70 = a1;
  v72 = 0;
  DeviceObject = 0;
  FileObject = 0;
  IsConsoleConnection = (int)UserIsConsoleConnection(a1);
  P = 0;
  v80 = 0;
  updated = 0;
  DeviceRegKey = 0;
  InputBuffer = 0;
  v79 = 0;
  WdLogSingleEntry2(4, v1, IsConsoleConnection);
  WdLogGlobalForLineNumber = 9081;
  v4 = *(_QWORD *)(W32GetSessionState(v3) + 88);
  if ( (_DWORD)IsConsoleConnection )
  {
    v5 = (int *)(v4 + 1332);
    v6 = (int *)(v4 + 1328);
    v7 = (__int64 *)(v4 + 1296);
    v8 = (__int64 *)(v4 + 1280);
    v9 = (_DWORD *)(v4 + 1268);
  }
  else
  {
    v5 = (int *)(v4 + 1340);
    v6 = (int *)(v4 + 1336);
    v7 = (__int64 *)(v4 + 1288);
    v8 = (__int64 *)(v4 + 1272);
    v9 = (_DWORD *)(v4 + 1264);
  }
  v10 = *v8;
  v11 = *v7;
  v12 = *v6;
  v13 = *v5;
  *(_DWORD *)(v4 + 1172) = *v9;
  *(_QWORD *)(v4 + 1184) = v10;
  *(_QWORD *)(v4 + 1192) = v11;
  *(_DWORD *)(v4 + 1176) = v12;
  *(_DWORD *)(v4 + 1180) = v13;
  if ( (_DWORD)IsConsoleConnection )
  {
    v71 = 0;
    QueryTable.QueryRoutine = 0;
    QueryTable.Name = L"MaxObjectNumber";
    QueryTable.Flags = 288;
    QueryTable.EntryContext = &v72;
    QueryTable.DefaultType = 67108868;
    QueryTable.DefaultData = &v71;
    QueryTable.DefaultLength = 4;
    v85 = 0;
    v86 = 0;
    v87 = 0;
    v88 = 0;
    v89 = 0;
    RtlQueryRegistryValues(4u, L"VIDEO", &QueryTable, 0, 0);
  }
  else if ( (unsigned int)UserIsWddmConnectedSession() )
  {
    v71 = 0;
    DxgkWin32kInterface = DxDdGetDxgkWin32kInterface(v15, v14, v16);
    v18 = (*(__int64 (__fastcall **)(unsigned int *, unsigned int *))(DxgkWin32kInterface + 768))(&v71, &v72);
    updated = v18;
    if ( v18 < 0 )
    {
      WdLogSingleEntry1(2, v18);
      WdLogGlobalForLineNumber = 9143;
      v72 = *(_DWORD *)(v4 + 1172);
    }
    v20 = *(unsigned int *)(v4 + 1172);
    v21 = v71;
    if ( v71 <= (unsigned int)v20 )
      v21 = *(_DWORD *)(v4 + 1172);
    else
      *(_DWORD *)(v4 + 1172) = v71;
    if ( v72 >= v21 + 16 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v20, v19);
  }
  else
  {
    if ( !(unsigned int)UserIsDisconnectConnection() )
      v72 = *(_DWORD *)(v4 + 2936) - 1;
    if ( *(_DWORD *)(v4 + 3000) )
    {
      updated = DrvUpdateRemoteAdapterInfo(0);
      if ( updated < 0 )
        return 0;
    }
  }
  v22 = 0;
  v71 = 1;
  v67 = 0;
  while ( 2 )
  {
    if ( !(unsigned int)UserIsDisconnectConnection() && *(_DWORD *)(v4 + 1172) <= v72 )
    {
      if ( !(_DWORD)v1 )
      {
        WdLogSingleEntry0(5);
        WdLogGlobalForLineNumber = 9202;
        return 0;
      }
      if ( (unsigned int)UserIsWddmConnectedSession() )
      {
        if ( (_DWORD)IsConsoleConnection )
        {
          v25 = StringCchPrintfW(
                  (unsigned __int16 *)&QueryTable,
                  0x32u,
                  L"\\Device\\Video%d",
                  *(unsigned int *)(v4 + 1172));
          goto LABEL_28;
        }
        v24 = L"RemoteVideo";
      }
      else
      {
        v24 = *(const wchar_t **)(v4 + 2992);
      }
      LODWORD(Environment) = *(_DWORD *)(v4 + 1172);
      v25 = StringCchPrintfW((unsigned __int16 *)&QueryTable, 0x32u, L"\\Device\\%s%d", v24, Environment);
LABEL_28:
      if ( v25 >= 0 )
      {
        v26 = *(_QWORD *)(v4 + 1184);
        v27 = (__int64 *)(v4 + 1296);
        if ( !(_DWORD)IsConsoleConnection )
          v27 = (__int64 *)(v4 + 1288);
        v28 = *v27;
        while ( v26 )
        {
          if ( !wcsncmp_0((const wchar_t *)&QueryTable, (const wchar_t *)v26, 0x40u) )
            goto LABEL_63;
          if ( v26 == v28 )
            break;
          v26 = *(_QWORD *)(v26 + 128);
        }
        DestinationString = 0;
        RtlInitUnicodeString(&DestinationString, (PCWSTR)&QueryTable);
        DeviceObjectPointer = IoGetDeviceObjectPointer(&DestinationString, 0, &FileObject, &DeviceObject);
        updated = DeviceObjectPointer;
        if ( DeviceObjectPointer >= 0 )
        {
LABEL_44:
          v22 = v67;
          v32 = PALLOCMEM(304, 1986291527);
          LODWORD(v1) = v70;
          if ( !v32 )
            continue;
          v33 = DeviceObject;
          *(_QWORD *)(v32 + 136) = DeviceObject;
          v34 = (unsigned int *)(v32 + 160);
          v35 = *(unsigned __int16 *)(W32GetUserSessionState(v33) + 68736);
          *(_WORD *)(v32 + 216) = v35;
          *(_QWORD *)(v32 + 264) = 0;
          if ( !(_DWORD)IsConsoleConnection )
            *v34 |= 0x4000000u;
          *(_QWORD *)(v32 + 224) = FileObject;
          if ( !(_DWORD)IsConsoleConnection && !*(_DWORD *)(W32GetUserSessionState(v35) + 68688)
            || (*(_DWORD *)(v32 + 252) = 0, !(_DWORD)IsConsoleConnection) )
          {
            if ( !*(_DWORD *)(W32GetUserSessionState(v35) + 68688) )
            {
              *(_QWORD *)(v32 + 240) = 0xFFFFFFFFLL;
              *(_QWORD *)(v32 + 232) = 0;
              *(_DWORD *)(v32 + 248) = *(_DWORD *)(v4 + 1172);
              goto LABEL_52;
            }
          }
          *((_QWORD *)&InputBuffer + 1) = VideoPortCallout;
          v80 = 0;
          v79 = 0;
          *(_QWORD *)&InputBuffer = v32;
          v40 = GreDeviceIoControlImpl(
                  *(PDEVICE_OBJECT *)(v32 + 136),
                  0x23201Fu,
                  &InputBuffer,
                  0x28u,
                  &InputBuffer,
                  0x28u,
                  v74,
                  1u,
                  1);
          updated = v40;
          if ( v40 >= 0 )
          {
            if ( (_DWORD)v79 )
              *(_DWORD *)(v32 + 160) |= 0x40000000u;
            if ( (v80 & 0xC0000001) == 0 )
            {
              if ( (v80 & 0x20000000) != 0 )
                *v34 |= 0x100000u;
              v41 = *(struct _DEVICE_OBJECT **)(v32 + 136);
              *(_QWORD *)(v32 + 144) = *((_QWORD *)&v79 + 1);
              *(_DWORD *)(v32 + 248) = 0;
              v81 = 0;
              v82 = 0;
              updated = GreDeviceIoControlImpl(v41, 0x232033u, 0, 0, &v81, 0x20u, v74, 1u, 1);
              if ( updated < 0 )
              {
                if ( !(_DWORD)IsConsoleConnection )
                  goto LABEL_83;
              }
              else
              {
                if ( (_DWORD)v81 != 2 )
                {
                  WdLogSingleEntry0(1);
                  WdLogGlobalForLineNumber = 9492;
                }
                UserSessionState = W32GetUserSessionState(v42);
                if ( *(_QWORD *)(UserSessionState + 68680) != *((_QWORD *)&v82 + 1) )
                  goto LABEL_83;
                v44 = *((_QWORD *)&v81 + 1);
                if ( !*((_QWORD *)&v81 + 1) )
                  goto LABEL_83;
                *v34 |= 0x800000u;
                *(_QWORD *)(v32 + 232) = v44;
                *(_DWORD *)(v32 + 248) = DWORD1(v81);
                *(_QWORD *)(v32 + 240) = v82;
              }
LABEL_52:
              updated = DrvForceChildDeviceReenumeration(DeviceObject, (struct _DEVICE_RELATIONS **)&P);
              if ( updated >= 0 )
              {
                v36 = (struct _DEVICE_OBJECT *)*((_QWORD *)P + 1);
                ExFreePoolWithTag(P, 0);
                updated = IoOpenDeviceRegistryKey(v36, 2u, 0x2000000u, &DeviceRegKey);
                if ( updated >= 0 )
                {
                  DrvGetDeviceConfigurationInformation((unsigned int *)v32, (WCHAR *)DeviceRegKey, 1);
                  ZwClose(DeviceRegKey);
                }
                ObfDereferenceObject(v36);
              }
              swprintf_s((wchar_t *)v32, 0x20u, (const wchar_t *)&QueryTable);
              ++*(_DWORD *)(v4 + 1172);
              if ( updated >= 0
                || (v37 = DrvGetRegistryHandleFromDeviceMap((unsigned __int16 *)v32, 0, 0, 0, 0, &updated),
                    DeviceRegKey = v37,
                    updated >= 0)
                && (DrvGetDeviceConfigurationInformation((unsigned int *)v32, (WCHAR *)v37, 0),
                    ZwClose(DeviceRegKey),
                    updated >= 0) )
              {
                if ( !*(_QWORD *)(v32 + 208) )
                {
                  v38 = (unsigned __int16 *)PALLOCNOZ(32, 1936876615);
                  *(_QWORD *)(v32 + 208) = v38;
                  if ( v38 )
                  {
                    RegistryHandleFromDeviceMap = DrvGetRegistryHandleFromDeviceMap(
                                                    (unsigned __int16 *)v32,
                                                    0,
                                                    0,
                                                    v38,
                                                    0x10u,
                                                    &updated);
                    DeviceRegKey = RegistryHandleFromDeviceMap;
                    if ( RegistryHandleFromDeviceMap )
                      ZwClose(RegistryHandleFromDeviceMap);
                  }
                  else
                  {
                    updated = -1073741670;
                  }
                }
              }
              v45 = (wchar_t *)(v32 + 64);
              if ( (*v34 & 8) != 0 )
              {
                ++*(_DWORD *)(v4 + 1180);
                swprintf_s(v45, 0x20u, L"\\\\.\\DISPLAYV%d");
              }
              else
              {
                ++*(_DWORD *)(v4 + 1176);
                swprintf_s(v45, 0x20u, L"\\\\.\\DISPLAY%d");
              }
              PruneFlag = DrvGetPruneFlag((struct tagGRAPHICS_DEVICE *)v32);
              v47 = *v34 & 0xFFF7FFFF;
              if ( !PruneFlag )
                v47 = *v34 | 0x80000;
              *v34 = v47;
              if ( (unsigned int)bSetDeviceSessionUsage(v32, 1) )
              {
                if ( (_DWORD)IsConsoleConnection )
                  goto LABEL_107;
              }
              else if ( (_DWORD)IsConsoleConnection || *(_DWORD *)(W32GetUserSessionState(v48) + 68688) )
              {
                DrvCleanupOneGraphicsDevice((PVOID)v32);
                goto LABEL_64;
              }
              if ( !*(_DWORD *)(W32GetUserSessionState(v48) + 68688) )
              {
                v50 = *(_QWORD *)(W32GetSessionState(v49) + 88);
                *(_QWORD *)(v32 + 272) = 0;
                v53 = *(_DWORD *)(v50 + 3000) ? *(_QWORD *)(v50 + 3004) : 0LL;
                *(_QWORD *)(v32 + 288) = v53;
                *(_QWORD *)(v32 + 296) = 0;
                v69[0] = 0;
                v54 = DxDdGetDxgkWin32kInterface(0, v51, v52);
                if ( (*(int (__fastcall **)(__int64, __int64, __int64, __int64, _BYTE *))(v54 + 392))(
                       v32 + 272,
                       v32 + 288,
                       v32 + 296,
                       v32 + 280,
                       v69) >= 0 )
                {
                  v55 = *(_DWORD *)(v32 + 164);
                  if ( v69[0] )
                    v56 = v55 | 4;
                  else
                    v56 = v55 & 0xFFFFFFFB;
                  *(_DWORD *)(v32 + 164) = v56;
                  DrvUpdateRemoteAdapterInfo((struct tagGRAPHICS_DEVICE *)v32);
                }
              }
              if ( !*(_DWORD *)(W32GetUserSessionState(v49) + 68688) && updated < 0 )
              {
                DrvCleanupOneGraphicsDevice((PVOID)v32);
                --*(_DWORD *)(v4 + 1176);
                v22 = v67;
                v71 = 0;
                goto LABEL_65;
              }
LABEL_107:
              if ( *(_QWORD *)(v4 + 1184) )
                *(_QWORD *)(*(_QWORD *)(v4 + 1192) + 128LL) = v32;
              else
                *(_QWORD *)(v4 + 1184) = v32;
              *(_QWORD *)(v4 + 1192) = v32;
              if ( (*v34 & 0x800000) != 0 )
                DrvAddAdapterLuid(*(struct _LUID *)(v32 + 240));
              v22 = 1;
              v67 = 1;
              goto LABEL_65;
            }
            updated = -1073741637;
            WdLogSingleEntry2(5, (unsigned int)v80, -1073741637);
            WdLogGlobalForLineNumber = 9445;
          }
          else
          {
            WdLogSingleEntry1(5, v40);
            WdLogGlobalForLineNumber = 9425;
          }
LABEL_83:
          DrvCleanupOneGraphicsDevice((PVOID)v32);
          goto LABEL_63;
        }
        if ( !(_DWORD)IsConsoleConnection )
        {
          if ( !*(_DWORD *)(W32GetUserSessionState(v30) + 68688) && *(_DWORD *)(v4 + 2936) == 1 )
          {
            v31 = *(struct _FILE_OBJECT **)(v4 + 2944);
            FileObject = v31;
            if ( v31 )
            {
              DeviceObject = IoGetRelatedDeviceObject(v31);
              if ( FileObject )
              {
                if ( DeviceObject )
                {
                  updated = 0;
                  FileObject = 0;
                  goto LABEL_44;
                }
              }
            }
            v22 = v67;
            updated = -1073741772;
            goto LABEL_117;
          }
          DeviceObjectPointer = updated;
        }
        WdLogSingleEntry1(5, DeviceObjectPointer);
        WdLogGlobalForLineNumber = 9364;
LABEL_63:
        ++*(_DWORD *)(v4 + 1172);
LABEL_64:
        v22 = v67;
LABEL_65:
        LODWORD(v1) = v70;
        continue;
      }
      return 0;
    }
    break;
  }
  if ( !(_DWORD)IsConsoleConnection )
  {
LABEL_117:
    if ( !*(_DWORD *)(W32GetUserSessionState(v23) + 68688) )
    {
      SessionState = W32GetSessionState(v58);
      DrvUpdateRemoteDriverFlags((struct tagREMOTE_CONTEXT *)(*(_QWORD *)(SessionState + 88) + 2936LL));
    }
  }
  if ( (unsigned int)DrvSetDisconnectedGraphicsDevice(IsConsoleConnection) )
  {
    WdLogSingleEntry0(5);
    WdLogGlobalForLineNumber = 9805;
  }
  else
  {
    WdLogSingleEntry0(5);
    WdLogGlobalForLineNumber = 9808;
  }
  if ( v22 )
    DrvSortGraphicsDeviceList();
  v60 = *(_DWORD *)(v4 + 1172);
  v61 = *(_QWORD *)(v4 + 1184);
  v62 = *(_QWORD *)(v4 + 1192);
  v63 = *(_DWORD *)(v4 + 1176);
  v64 = *(_DWORD *)(v4 + 1180);
  if ( (_DWORD)IsConsoleConnection )
  {
    *(_DWORD *)(v4 + 1268) = v60;
    *(_QWORD *)(v4 + 1280) = v61;
    *(_QWORD *)(v4 + 1296) = v62;
    *(_DWORD *)(v4 + 1328) = v63;
    *(_DWORD *)(v4 + 1332) = v64;
  }
  else
  {
    *(_DWORD *)(v4 + 1264) = v60;
    *(_QWORD *)(v4 + 1272) = v61;
    *(_QWORD *)(v4 + 1288) = v62;
    *(_DWORD *)(v4 + 1336) = v63;
    *(_DWORD *)(v4 + 1340) = v64;
    if ( !(unsigned int)VerifyRemoteVidPnSourceIdsAreValid() )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 9832;
    }
  }
  P = (PVOID)(unsigned int)Feature_RestrictXpdm_Block3rdPartyDrivers__private_featureState;
  if ( (Feature_RestrictXpdm_Block3rdPartyDrivers__private_featureState & 0x10) == 0 )
  {
    *(_QWORD *)v74 = __PAIR64__(HIDWORD(P), Feature_RestrictXpdm_Block3rdPartyDrivers__private_featureState | 1u);
    wil_details_FeatureReporting_ReportUsageToService(
      Feature_RestrictXpdm_Block3rdPartyDrivers__private_descriptor,
      __PAIR64__(HIDWORD(P), Feature_RestrictXpdm_Block3rdPartyDrivers__private_featureState | 1u),
      3,
      1);
    wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(
      *(_QWORD *)v74,
      3,
      Feature_RestrictXpdm_Block3rdPartyDrivers__private_descriptor);
  }
  v65 = v71;
  WdLogSingleEntry1(5, (int)v71);
  result = v65;
  WdLogGlobalForLineNumber = 9858;
  return result;
}

```

## disassembly

```asm
0x14018c750  push    rbp
0x14018c752  push    rbx
0x14018c753  push    rsi
0x14018c754  push    rdi
0x14018c755  push    r12
0x14018c757  push    r13
0x14018c759  push    r14
0x14018c75b  push    r15
0x14018c75d  lea     rbp, [rsp-78h]
0x14018c762  sub     rsp, 178h
0x14018c769  mov     rax, cs:__security_cookie
0x14018c770  xor     rax, rsp
0x14018c773  mov     [rbp+0B0h+var_50], rax
0x14018c777  xor     r15d, r15d
0x14018c77a  movsxd  r14, ecx
0x14018c77d  mov     [rsp+1B0h+var_154], r14d
0x14018c782  mov     [rsp+1B0h+var_14C], r15d
0x14018c787  mov     [rbp+0B0h+DeviceObject], r15
0x14018c78b  mov     [rsp+1B0h+FileObject], r15
0x14018c790  call    UserIsConsoleConnection
0x14018c795  xorps   xmm0, xmm0
0x14018c798  movsxd  r13, eax
0x14018c79b  xor     eax, eax
0x14018c79d  mov     [rbp+0B0h+P], r15
0x14018c7a1  mov     [rbp+0B0h+var_100], rax
0x14018c7a5  mov     [rsp+1B0h+var_15C], r15d
0x14018c7aa  mov     [rsp+1B0h+DeviceRegKey], r15
0x14018c7af  movups  [rbp+0B0h+InputBuffer], xmm0
0x14018c7b3  movups  [rbp+0B0h+var_110], xmm0
0x14018c7b7  lea     ebx, [rax+4]
0x14018c7ba  mov     r8, r13
0x14018c7bd  mov     ecx, ebx
0x14018c7bf  mov     rdx, r14
0x14018c7c2  call    cs:__imp_WdLogSingleEntry2
0x14018c7c9  nop     dword ptr [rax+rax+00h]
0x14018c7ce  mov     cs:WdLogGlobalForLineNumber, 2379h
0x14018c7d8  call    cs:__imp_W32GetSessionState
0x14018c7df  nop     dword ptr [rax+rax+00h]
0x14018c7e4  mov     rdi, [rax+58h]
0x14018c7e8  test    r13d, r13d
0x14018c7eb  jz      short loc_14018C812
0x14018c7ed  lea     r9, [rdi+534h]
0x14018c7f4  lea     r8, [rdi+530h]
0x14018c7fb  lea     rdx, [rdi+510h]
0x14018c802  lea     rcx, [rdi+500h]
0x14018c809  lea     rax, [rdi+4F4h]
0x14018c810  jmp     short loc_14018C835
0x14018c812  lea     r9, [rdi+53Ch]
0x14018c819  lea     r8, [rdi+538h]
0x14018c820  lea     rdx, [rdi+508h]
0x14018c827  lea     rcx, [rdi+4F8h]
0x14018c82e  lea     rax, [rdi+4F0h]
0x14018c835  mov     rcx, [rcx]
0x14018c838  mov     rdx, [rdx]
0x14018c83b  mov     r8d, [r8]
0x14018c83e  mov     r9d, [r9]
0x14018c841  mov     eax, [rax]
0x14018c843  mov     [rdi+494h], eax
0x14018c849  mov     [rdi+4A0h], rcx
0x14018c850  mov     [rdi+4A8h], rdx
0x14018c857  mov     [rdi+498h], r8d
0x14018c85e  mov     [rdi+49Ch], r9d
0x14018c865  test    r13d, r13d
0x14018c868  jz      short loc_14018C8DE
0x14018c86a  xorps   xmm0, xmm0
0x14018c86d  mov     [rsp+1B0h+var_150], r15d
0x14018c872  lea     rax, aMaxobjectnumbe; "MaxObjectNumber"
0x14018c879  mov     [rbp+0B0h+QueryTable.QueryRoutine], r15
0x14018c87d  mov     [rbp+0B0h+QueryTable.Name], rax
0x14018c881  lea     r8, [rbp+0B0h+QueryTable]; QueryTable
0x14018c885  lea     rax, [rsp+1B0h+var_14C]
0x14018c88a  mov     [rbp+0B0h+QueryTable.Flags], 120h
0x14018c891  mov     [rbp+0B0h+QueryTable.EntryContext], rax
0x14018c895  lea     rdx, aVideo_0; "VIDEO"
0x14018c89c  lea     rax, [rsp+1B0h+var_150]
0x14018c8a1  mov     [rbp+0B0h+QueryTable.DefaultType], 4000004h
0x14018c8a8  xor     r9d, r9d; Context
0x14018c8ab  mov     [rbp+0B0h+QueryTable.DefaultData], rax
0x14018c8af  mov     ecx, ebx; RelativeTo
0x14018c8b1  mov     [rbp+0B0h+QueryTable.DefaultLength], ebx
0x14018c8b4  mov     [rbp+0B0h+var_88], r15
0x14018c8b8  mov     [rbp+0B0h+var_80], r15d
0x14018c8bc  mov     [rbp+0B0h+var_78], r15
0x14018c8c0  movups  [rbp+0B0h+var_70], xmm0
0x14018c8c4  mov     [rsp+1B0h+Environment], r15; Environment
0x14018c8c9  movups  [rbp+0B0h+var_60], xmm0
0x14018c8cd  call    cs:__imp_RtlQueryRegistryValues
0x14018c8d4  nop     dword ptr [rax+rax+00h]
0x14018c8d9  jmp     loc_14018C997
0x14018c8de  call    UserIsWddmConnectedSession
0x14018c8e3  test    eax, eax
0x14018c8e5  jz      short loc_14018C966
0x14018c8e7  mov     [rsp+1B0h+var_150], r15d
0x14018c8ec  call    cs:__imp_DxDdGetDxgkWin32kInterface
0x14018c8f3  nop     dword ptr [rax+rax+00h]
0x14018c8f8  lea     rdx, [rsp+1B0h+var_14C]
0x14018c8fd  lea     rcx, [rsp+1B0h+var_150]
0x14018c902  mov     rax, [rax+300h]
0x14018c909  call    _guard_dispatch_icall
0x14018c90e  mov     [rsp+1B0h+var_15C], eax
0x14018c912  test    eax, eax
0x14018c914  jns     short loc_14018C93E
0x14018c916  movsxd  rdx, eax
0x14018c919  mov     ecx, 2
0x14018c91e  call    cs:__imp_WdLogSingleEntry1
0x14018c925  nop     dword ptr [rax+rax+00h]
0x14018c92a  mov     cs:WdLogGlobalForLineNumber, 23B7h
0x14018c934  mov     eax, [rdi+494h]
0x14018c93a  mov     [rsp+1B0h+var_14C], eax
0x14018c93e  mov     ecx, [rdi+494h]
0x14018c944  mov     eax, [rsp+1B0h+var_150]
0x14018c948  cmp     eax, ecx
0x14018c94a  jbe     short loc_14018C954
0x14018c94c  mov     [rdi+494h], eax
0x14018c952  jmp     short loc_14018C956
0x14018c954  mov     eax, ecx
0x14018c956  add     eax, 10h
0x14018c959  cmp     [rsp+1B0h+var_14C], eax
0x14018c95d  jb      short loc_14018C997
0x14018c95f  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14018c964  jmp     short loc_14018C997
0x14018c966  call    UserIsDisconnectConnection
0x14018c96b  test    eax, eax
0x14018c96d  jnz     short loc_14018C97B
0x14018c96f  mov     eax, [rdi+0B78h]
0x14018c975  dec     eax
0x14018c977  mov     [rsp+1B0h+var_14C], eax
0x14018c97b  cmp     [rdi+0BB8h], r15d
0x14018c982  jz      short loc_14018C997
0x14018c984  xor     ecx, ecx; struct tagGRAPHICS_DEVICE *
0x14018c986  call    ?DrvUpdateRemoteAdapterInfo@@YAJPEAUtagGRAPHICS_DEVICE@@@Z; DrvUpdateRemoteAdapterInfo(tagGRAPHICS_DEVICE *)
0x14018c98b  mov     [rsp+1B0h+var_15C], eax
0x14018c98f  test    eax, eax
0x14018c991  js      loc_14018D1A3
0x14018c997  mov     bl, r15b
0x14018c99a  mov     [rsp+1B0h+var_150], 1
0x14018c9a2  mov     [rsp+1B0h+var_160], bl
0x14018c9a6  mov     rsi, r15
0x14018c9a9  call    UserIsDisconnectConnection
0x14018c9ae  test    eax, eax
0x14018c9b0  jnz     loc_14018D1AA
0x14018c9b6  mov     eax, [rsp+1B0h+var_14C]
0x14018c9ba  cmp     [rdi+494h], eax
0x14018c9c0  ja      loc_14018D1AA
0x14018c9c6  test    r14d, r14d
0x14018c9c9  jz      loc_14018D188
0x14018c9cf  call    UserIsWddmConnectedSession
0x14018c9d4  mov     ecx, [rdi+494h]
0x14018c9da  test    eax, eax
0x14018c9dc  jnz     short loc_14018C9E7
0x14018c9de  mov     r9, [rdi+0BB0h]
0x14018c9e5  jmp     short loc_14018CA0D
0x14018c9e7  test    r13d, r13d
0x14018c9ea  jz      short loc_14018CA06
0x14018c9ec  mov     r9d, ecx
0x14018c9ef  lea     r8, aDeviceVideoD; "\\Device\\Video%d"
0x14018c9f6  lea     rcx, [rbp+0B0h+QueryTable]; unsigned __int16 *
0x14018c9fa  mov     edx, 32h ; '2'; unsigned __int64
0x14018c9ff  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14018ca04  jmp     short loc_14018CA26
0x14018ca06  lea     r9, aRemotevideo; "RemoteVideo"
0x14018ca0d  mov     dword ptr [rsp+1B0h+Environment], ecx
0x14018ca11  lea     r8, aDeviceSD; "\\Device\\%s%d"
0x14018ca18  lea     rcx, [rbp+0B0h+QueryTable]; unsigned __int16 *
0x14018ca1c  mov     edx, 32h ; '2'; unsigned __int64
0x14018ca21  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14018ca26  test    eax, eax
0x14018ca28  js      loc_14018D1A3
0x14018ca2e  mov     rbx, [rdi+4A0h]
0x14018ca35  lea     rax, [rdi+510h]
0x14018ca3c  test    r13d, r13d
0x14018ca3f  jnz     short loc_14018CA48
0x14018ca41  lea     rax, [rdi+508h]
0x14018ca48  mov     r14, [rax]
0x14018ca4b  jmp     short loc_14018CA73
0x14018ca4d  mov     r8d, 40h ; '@'; MaxCount
0x14018ca53  lea     rcx, [rbp+0B0h+QueryTable]; Str1
0x14018ca57  mov     rdx, rbx; Str2
0x14018ca5a  call    wcsncmp_0
0x14018ca5f  test    eax, eax
0x14018ca61  jz      loc_14018CD7B
0x14018ca67  cmp     rbx, r14
0x14018ca6a  jz      short loc_14018CA78
0x14018ca6c  mov     rbx, [rbx+80h]
0x14018ca73  test    rbx, rbx
0x14018ca76  jnz     short loc_14018CA4D
0x14018ca78  xorps   xmm0, xmm0
0x14018ca7b  lea     rdx, [rbp+0B0h+QueryTable]; SourceString
0x14018ca7f  lea     rcx, [rbp+0B0h+DestinationString]; DestinationString
0x14018ca83  movups  xmmword ptr [rbp+0B0h+DestinationString.Length], xmm0
0x14018ca87  call    cs:__imp_RtlInitUnicodeString
0x14018ca8e  nop     dword ptr [rax+rax+00h]
0x14018ca93  lea     r9, [rbp+0B0h+DeviceObject]; DeviceObject
0x14018ca97  xor     edx, edx; DesiredAccess
0x14018ca99  lea     r8, [rsp+1B0h+FileObject]; FileObject
0x14018ca9e  lea     rcx, [rbp+0B0h+DestinationString]; ObjectName
0x14018caa2  call    cs:__imp_IoGetDeviceObjectPointer
0x14018caa9  nop     dword ptr [rax+rax+00h]
0x14018caae  mov     [rsp+1B0h+var_15C], eax
0x14018cab2  test    eax, eax
0x14018cab4  jns     short loc_14018CB2F
0x14018cab6  test    r13d, r13d
0x14018cab9  jnz     loc_14018CD93
0x14018cabf  call    cs:__imp_W32GetUserSessionState
0x14018cac6  nop     dword ptr [rax+rax+00h]
0x14018cacb  cmp     [rax+10C50h], r15d
0x14018cad2  jnz     loc_14018CD8F
0x14018cad8  cmp     dword ptr [rdi+0B78h], 1
0x14018cadf  jnz     loc_14018CD8F
0x14018cae5  mov     rax, [rdi+0B80h]
0x14018caec  mov     [rsp+1B0h+FileObject], rax
0x14018caf1  test    rax, rax
0x14018caf4  jz      loc_14018D17A
0x14018cafa  mov     rcx, rax; FileObject
0x14018cafd  call    cs:__imp_IoGetRelatedDeviceObject
0x14018cb04  nop     dword ptr [rax+rax+00h]
0x14018cb09  mov     [rbp+0B0h+DeviceObject], rax
0x14018cb0d  mov     rax, [rsp+1B0h+FileObject]
0x14018cb12  test    rax, rax
0x14018cb15  jz      loc_14018D17A
0x14018cb1b  cmp     [rbp+0B0h+DeviceObject], r15
0x14018cb1f  jz      loc_14018D17A
0x14018cb25  mov     [rsp+1B0h+var_15C], r15d
0x14018cb2a  mov     [rsp+1B0h+FileObject], r15
0x14018cb2f  test    rsi, rsi
0x14018cb32  jnz     short loc_14018CB58
0x14018cb34  mov     edx, 76646747h
0x14018cb39  mov     ecx, 130h
0x14018cb3e  call    PALLOCMEM
0x14018cb43  mov     bl, [rsp+1B0h+var_160]
0x14018cb47  mov     rsi, rax
0x14018cb4a  mov     r14d, [rsp+1B0h+var_154]
0x14018cb4f  test    rax, rax
0x14018cb52  jz      loc_14018C9A9
0x14018cb58  mov     rcx, [rbp+0B0h+DeviceObject]
0x14018cb5c  mov     [rsi+88h], rcx
0x14018cb63  call    cs:__imp_W32GetUserSessionState
0x14018cb6a  nop     dword ptr [rax+rax+00h]
0x14018cb6f  lea     r12, [rsi+0A0h]
0x14018cb76  movzx   ecx, word ptr [rax+10C80h]
0x14018cb7d  mov     [rsi+0D8h], cx
0x14018cb84  mov     [rsi+108h], r15
0x14018cb8b  test    r13d, r13d
0x14018cb8e  jnz     short loc_14018CB96
0x14018cb90  bts     dword ptr [r12], 1Ah
0x14018cb96  mov     rax, [rsp+1B0h+FileObject]
0x14018cb9b  mov     [rsi+0E0h], rax
0x14018cba2  test    r13d, r13d
0x14018cba5  jnz     short loc_14018CBBC
0x14018cba7  call    cs:__imp_W32GetUserSessionState
0x14018cbae  nop     dword ptr [rax+rax+00h]
0x14018cbb3  cmp     [rax+10C50h], r15d
0x14018cbba  jz      short loc_14018CBCC
0x14018cbbc  mov     [rsi+0FCh], r15d
0x14018cbc3  test    r13d, r13d
0x14018cbc6  jnz     loc_14018CDB3
0x14018cbcc  call    cs:__imp_W32GetUserSessionState
0x14018cbd3  nop     dword ptr [rax+rax+00h]
0x14018cbd8  cmp     [rax+10C50h], r15d
0x14018cbdf  jnz     loc_14018CDB3
0x14018cbe5  mov     rax, cs:qword_1402666E8
0x14018cbec  mov     r14d, 20h ; ' '
0x14018cbf2  mov     [rsi+0F0h], rax
0x14018cbf9  mov     [rsi+0E8h], r15
0x14018cc00  mov     eax, [rdi+494h]
0x14018cc06  mov     [rsi+0F8h], eax
0x14018cc0c  mov     rcx, [rbp+0B0h+DeviceObject]; DeviceObject
0x14018cc10  lea     rdx, [rbp+0B0h+P]; struct _DEVICE_RELATIONS **
0x14018cc14  call    ?DrvForceChildDeviceReenumeration@@YAJPEAU_DEVICE_OBJECT@@PEAPEAU_DEVICE_RELATIONS@@@Z; DrvForceChildDeviceReenumeration(_DEVICE_OBJECT *,_DEVICE_RELATIONS * *)
0x14018cc19  mov     [rsp+1B0h+var_15C], eax
0x14018cc1d  test    eax, eax
0x14018cc1f  js      short loc_14018CC91
0x14018cc21  mov     rcx, [rbp+0B0h+P]; P
0x14018cc25  xor     edx, edx; Tag
0x14018cc27  mov     rbx, [rcx+8]
0x14018cc2b  call    cs:__imp_ExFreePoolWithTag
0x14018cc32  nop     dword ptr [rax+rax+00h]
0x14018cc37  lea     r9, [rsp+1B0h+DeviceRegKey]; DeviceRegKey
0x14018cc3c  mov     edx, 2; DevInstKeyType
0x14018cc41  mov     r8d, 2000000h; DesiredAccess
0x14018cc47  mov     rcx, rbx; DeviceObject
0x14018cc4a  call    cs:__imp_IoOpenDeviceRegistryKey
0x14018cc51  nop     dword ptr [rax+rax+00h]
0x14018cc56  mov     [rsp+1B0h+var_15C], eax
0x14018cc5a  test    eax, eax
0x14018cc5c  js      short loc_14018CC82
0x14018cc5e  mov     rdx, [rsp+1B0h+DeviceRegKey]; Path
0x14018cc63  mov     r8d, 1; int
0x14018cc69  mov     rcx, rsi; Context
0x14018cc6c  call    ?DrvGetDeviceConfigurationInformation@@YAXPEAUtagGRAPHICS_DEVICE@@PEAXH@Z; DrvGetDeviceConfigurationInformation(tagGRAPHICS_DEVICE *,void *,int)
0x14018cc71  mov     rcx, [rsp+1B0h+DeviceRegKey]; Handle
0x14018cc76  call    cs:__imp_ZwClose
0x14018cc7d  nop     dword ptr [rax+rax+00h]
0x14018cc82  mov     rcx, rbx; Object
0x14018cc85  call    cs:__imp_ObfDereferenceObject
0x14018cc8c  nop     dword ptr [rax+rax+00h]
0x14018cc91  lea     r8, [rbp+0B0h+QueryTable]; Format
0x14018cc95  mov     rdx, r14; SizeInWords
0x14018cc98  mov     rcx, rsi; Dst
0x14018cc9b  call    cs:__imp_swprintf_s
  ... truncated ...
```
