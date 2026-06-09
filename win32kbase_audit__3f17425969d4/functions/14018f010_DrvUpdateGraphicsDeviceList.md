# DrvUpdateGraphicsDeviceList

- ea: `0x14018f010`
- end: `0x14018fc14`
- name: `DrvUpdateGraphicsDeviceList`
- size: `3076`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `5`
- callee_count: `26`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1400962e0`
- `0x1400d6ab4`
- `0x140194ae0`
- `0x1401cdaa4`
- `0x1401ce2cc`

## callees

- `0x14000d76c`
- `0x14006e970`
- `0x14007ab04`
- `0x1400962b0`
- `0x1400c63c0`
- `0x1400d27e0`
- `0x1400d2a60`
- `0x1400d2ff0`
- `0x1400d34f8`
- `0x1400d4e00`
- `0x1400d565c`
- `0x1400d5750`
- `0x140111520`
- `0x1401618b8`
- `0x14016cc8c`
- `0x14016ec68`
- `0x14017db00`
- `0x140182c2c`
- `0x14018b0a0`
- `0x14018f010`
- `0x14018fc1c`
- `0x1401ad940`
- `0x1401ad994`
- `0x1402388be`
- `0x1402388e0`
- `0x1402389c0`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14018f536`
- `ntoskrnl!ZwClose` at `0x14018f5b6`
- `ntoskrnl!ZwClose` at `0x14018f62a`
- `ntoskrnl!ZwClose` at `0x14018f536`
- `ntoskrnl!ZwClose` at `0x14018f5b6`
- `ntoskrnl!ZwClose` at `0x14018f62a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14018f4eb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14018f4eb`
- `ntoskrnl!RtlQueryRegistryValues` at `0x14018f18d`
- `ntoskrnl!RtlQueryRegistryValues` at `0x14018f18d`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14018f3bd`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14018f3bd`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x14018f362`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x14018f362`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x14018f50a`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x14018f50a`
- `ntoskrnl!swprintf_s` at `0x14018f55b`
- `ntoskrnl!swprintf_s` at `0x14018f88f`
- `ntoskrnl!swprintf_s` at `0x14018f55b`
- `ntoskrnl!swprintf_s` at `0x14018f88f`
- `ntoskrnl!RtlInitUnicodeString` at `0x14018f347`
- `ntoskrnl!RtlInitUnicodeString` at `0x14018f347`
- `ntoskrnl!ObfDereferenceObject` at `0x14018f545`
- `ntoskrnl!ObfDereferenceObject` at `0x14018f545`
- `watchdog!WdLogSingleEntry0` at `0x14018f7c7`
- `watchdog!WdLogSingleEntry0` at `0x14018fa4d`
- `watchdog!WdLogSingleEntry0` at `0x14018fab1`
- `watchdog!WdLogSingleEntry0` at `0x14018face`
- `watchdog!WdLogSingleEntry0` at `0x14018fb66`
- `watchdog!WdLogSingleEntry0` at `0x14018f7c7`
- `watchdog!WdLogSingleEntry0` at `0x14018fa4d`
- `watchdog!WdLogSingleEntry0` at `0x14018fab1`
- `watchdog!WdLogSingleEntry0` at `0x14018face`
- `watchdog!WdLogSingleEntry0` at `0x14018fb66`
- `watchdog!WdLogSingleEntry1` at `0x14018f1de`
- `watchdog!WdLogSingleEntry1` at `0x14018f65b`
- `watchdog!WdLogSingleEntry1` at `0x14018f6e2`
- `watchdog!WdLogSingleEntry1` at `0x14018fbdb`
- `watchdog!WdLogSingleEntry1` at `0x14018f1de`
- `watchdog!WdLogSingleEntry1` at `0x14018f65b`
- `watchdog!WdLogSingleEntry1` at `0x14018f6e2`
- `watchdog!WdLogSingleEntry1` at `0x14018fbdb`
- `watchdog!WdLogSingleEntry2` at `0x14018f082`
- `watchdog!WdLogSingleEntry2` at `0x14018f72c`
- `watchdog!WdLogSingleEntry2` at `0x14018f082`
- `watchdog!WdLogSingleEntry2` at `0x14018f72c`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x14018f1ac`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x14018f95e`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x14018f1ac`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x14018f95e`
- `WIN32K!W32GetSessionState` at `0x14018f098`
- `WIN32K!W32GetSessionState` at `0x14018f917`
- `WIN32K!W32GetSessionState` at `0x14018fa84`
- `WIN32K!W32GetSessionState` at `0x14018f098`
- `WIN32K!W32GetSessionState` at `0x14018f917`
- `WIN32K!W32GetSessionState` at `0x14018fa84`
- `WIN32K!W32GetUserSessionState` at `0x14018f37f`
- `WIN32K!W32GetUserSessionState` at `0x14018f423`
- `WIN32K!W32GetUserSessionState` at `0x14018f467`
- `WIN32K!W32GetUserSessionState` at `0x14018f48c`
- `WIN32K!W32GetUserSessionState` at `0x14018f7dd`
- `WIN32K!W32GetUserSessionState` at `0x14018f8d0`
- `WIN32K!W32GetUserSessionState` at `0x14018f8fe`
- `WIN32K!W32GetUserSessionState` at `0x14018f9ba`
- `WIN32K!W32GetUserSessionState` at `0x14018fa6f`
- `WIN32K!W32GetUserSessionState` at `0x14018f37f`
- `WIN32K!W32GetUserSessionState` at `0x14018f423`
- `WIN32K!W32GetUserSessionState` at `0x14018f467`
- `WIN32K!W32GetUserSessionState` at `0x14018f48c`
- `WIN32K!W32GetUserSessionState` at `0x14018f7dd`
- `WIN32K!W32GetUserSessionState` at `0x14018f8d0`
- `WIN32K!W32GetUserSessionState` at `0x14018f8fe`
- `WIN32K!W32GetUserSessionState` at `0x14018f9ba`
- `WIN32K!W32GetUserSessionState` at `0x14018fa6f`

## pseudocode

```c
__int64 __fastcall DrvUpdateGraphicsDeviceList(__int64 a1, __int64 a2)
{
  __int64 v2; // r14
  _BOOL8 IsConsoleConnection; // r13
  __int64 v4; // rcx
  __int64 v5; // rdi
  int *v6; // r9
  int *v7; // r8
  __int64 *v8; // rdx
  __int64 *v9; // rcx
  _DWORD *v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rdx
  int v13; // r8d
  int v14; // r9d
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 DxgkWin32kInterface; // rax
  int v20; // eax
  unsigned int v21; // eax
  char v22; // bl
  __int64 v23; // rdx
  __int64 v24; // rcx
  const wchar_t *v25; // r9
  int v26; // eax
  __int64 v27; // rbx
  __int64 *v28; // rax
  __int64 v29; // r14
  NTSTATUS DeviceObjectPointer; // eax
  __int64 v31; // rdx
  __int64 v32; // rcx
  struct _FILE_OBJECT *v33; // rax
  __int64 v34; // rsi
  PDEVICE_OBJECT v35; // rcx
  unsigned int *v36; // r12
  __int64 v37; // rdx
  __int64 v38; // rcx
  struct _DEVICE_OBJECT *v39; // rbx
  HANDLE v40; // rax
  unsigned __int16 *v41; // rax
  HANDLE RegistryHandleFromDeviceMap; // rax
  int v43; // eax
  __int64 v44; // rdx
  struct _DEVICE_OBJECT *v45; // rcx
  __int64 v46; // rcx
  __int64 UserSessionState; // rax
  __int64 v48; // rax
  wchar_t *v49; // rcx
  BOOL PruneFlag; // eax
  unsigned int v51; // edx
  __int64 v52; // rdx
  __int64 v53; // rcx
  __int64 v54; // rax
  __int64 v55; // rax
  __int64 v56; // rax
  int v57; // eax
  unsigned int v58; // eax
  __int64 result; // rax
  __int64 v60; // rcx
  __int64 SessionState; // rax
  __int64 v62; // rcx
  int v63; // eax
  __int64 v64; // rcx
  __int64 v65; // rdx
  int v66; // r8d
  int v67; // r9d
  unsigned int v68; // ebx
  PVOID Environment; // [rsp+20h] [rbp-E0h]
  char v70; // [rsp+50h] [rbp-B0h]
  NTSTATUS updated; // [rsp+54h] [rbp-ACh] BYREF
  _BYTE v72[4]; // [rsp+58h] [rbp-A8h] BYREF
  int v73; // [rsp+5Ch] [rbp-A4h]
  unsigned int v74; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v75; // [rsp+64h] [rbp-9Ch] BYREF
  void *DeviceRegKey; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v77[2]; // [rsp+70h] [rbp-90h] BYREF
  PFILE_OBJECT FileObject; // [rsp+78h] [rbp-88h] BYREF
  PDEVICE_OBJECT DeviceObject; // [rsp+80h] [rbp-80h] BYREF
  PVOID P; // [rsp+88h] [rbp-78h] BYREF
  __int128 InputBuffer; // [rsp+90h] [rbp-70h] BYREF
  __int128 v82; // [rsp+A0h] [rbp-60h]
  __int64 v83; // [rsp+B0h] [rbp-50h]
  __int128 v84; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v85; // [rsp+C8h] [rbp-38h]
  struct _UNICODE_STRING DestinationString; // [rsp+D8h] [rbp-28h] BYREF
  struct _RTL_QUERY_REGISTRY_TABLE QueryTable; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v88; // [rsp+128h] [rbp+28h]
  int v89; // [rsp+130h] [rbp+30h]
  __int64 v90; // [rsp+138h] [rbp+38h]
  __int128 v91; // [rsp+140h] [rbp+40h]
  __int128 v92; // [rsp+150h] [rbp+50h]

  v2 = (int)a1;
  v73 = a1;
  v75 = 0;
  DeviceObject = 0;
  FileObject = 0;
  IsConsoleConnection = UserIsConsoleConnection(a1, a2);
  P = 0;
  v83 = 0;
  updated = 0;
  DeviceRegKey = 0;
  InputBuffer = 0;
  v82 = 0;
  WdLogSingleEntry2(4, v2, IsConsoleConnection);
  WdLogGlobalForLineNumber = 9081;
  v5 = *(_QWORD *)(W32GetSessionState(v4) + 88);
  if ( IsConsoleConnection )
  {
    v6 = (int *)(v5 + 1332);
    v7 = (int *)(v5 + 1328);
    v8 = (__int64 *)(v5 + 1296);
    v9 = (__int64 *)(v5 + 1280);
    v10 = (_DWORD *)(v5 + 1268);
  }
  else
  {
    v6 = (int *)(v5 + 1340);
    v7 = (int *)(v5 + 1336);
    v8 = (__int64 *)(v5 + 1288);
    v9 = (__int64 *)(v5 + 1272);
    v10 = (_DWORD *)(v5 + 1264);
  }
  v11 = *v9;
  v12 = *v8;
  v13 = *v7;
  v14 = *v6;
  *(_DWORD *)(v5 + 1172) = *v10;
  *(_QWORD *)(v5 + 1184) = v11;
  *(_QWORD *)(v5 + 1192) = v12;
  *(_DWORD *)(v5 + 1176) = v13;
  *(_DWORD *)(v5 + 1180) = v14;
  if ( IsConsoleConnection )
  {
    v74 = 0;
    QueryTable.QueryRoutine = 0;
    QueryTable.Name = L"MaxObjectNumber";
    QueryTable.Flags = 288;
    QueryTable.EntryContext = &v75;
    QueryTable.DefaultType = 67108868;
    QueryTable.DefaultData = &v74;
    QueryTable.DefaultLength = 4;
    v88 = 0;
    v89 = 0;
    v90 = 0;
    v91 = 0;
    v92 = 0;
    RtlQueryRegistryValues(4u, L"VIDEO", &QueryTable, 0, 0);
  }
  else if ( (unsigned int)UserIsWddmConnectedSession(v11, v12) )
  {
    v74 = 0;
    DxgkWin32kInterface = DxDdGetDxgkWin32kInterface(v18);
    v20 = (*(__int64 (__fastcall **)(unsigned int *, unsigned int *))(DxgkWin32kInterface + 768))(&v74, &v75);
    updated = v20;
    if ( v20 < 0 )
    {
      WdLogSingleEntry1(2, v20);
      WdLogGlobalForLineNumber = 9143;
      v75 = *(_DWORD *)(v5 + 1172);
    }
    v16 = *(unsigned int *)(v5 + 1172);
    v21 = v74;
    if ( v74 <= (unsigned int)v16 )
      v21 = *(_DWORD *)(v5 + 1172);
    else
      *(_DWORD *)(v5 + 1172) = v74;
    if ( v75 >= v21 + 16 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  else
  {
    if ( !UserIsDisconnectConnection(v18, v17) )
      v75 = *(_DWORD *)(v5 + 2936) - 1;
    if ( *(_DWORD *)(v5 + 3000) )
    {
      updated = DrvUpdateRemoteAdapterInfo(0);
      if ( updated < 0 )
        return 0;
    }
  }
  v22 = 0;
  v74 = 1;
  v70 = 0;
  while ( 2 )
  {
    if ( !UserIsDisconnectConnection(v16, v15) && *(_DWORD *)(v5 + 1172) <= v75 )
    {
      if ( !(_DWORD)v2 )
      {
        WdLogSingleEntry0(5);
        WdLogGlobalForLineNumber = 9202;
        return 0;
      }
      if ( (unsigned int)UserIsWddmConnectedSession(v24, v23) )
      {
        if ( IsConsoleConnection )
        {
          v26 = StringCchPrintfW(
                  (unsigned __int16 *)&QueryTable,
                  0x32u,
                  L"\\Device\\Video%d",
                  *(unsigned int *)(v5 + 1172));
          goto LABEL_28;
        }
        v25 = L"RemoteVideo";
      }
      else
      {
        v25 = *(const wchar_t **)(v5 + 2992);
      }
      LODWORD(Environment) = *(_DWORD *)(v5 + 1172);
      v26 = StringCchPrintfW((unsigned __int16 *)&QueryTable, 0x32u, L"\\Device\\%s%d", v25, Environment);
LABEL_28:
      if ( v26 >= 0 )
      {
        v27 = *(_QWORD *)(v5 + 1184);
        v28 = (__int64 *)(v5 + 1296);
        if ( !IsConsoleConnection )
          v28 = (__int64 *)(v5 + 1288);
        v29 = *v28;
        while ( v27 )
        {
          if ( !wcsncmp_0((const wchar_t *)&QueryTable, (const wchar_t *)v27, 0x40u) )
            goto LABEL_63;
          if ( v27 == v29 )
            break;
          v27 = *(_QWORD *)(v27 + 128);
        }
        DestinationString = 0;
        RtlInitUnicodeString(&DestinationString, (PCWSTR)&QueryTable);
        DeviceObjectPointer = IoGetDeviceObjectPointer(&DestinationString, 0, &FileObject, &DeviceObject);
        updated = DeviceObjectPointer;
        if ( DeviceObjectPointer >= 0 )
        {
LABEL_44:
          v22 = v70;
          v34 = PALLOCMEM(304, 1986291527);
          LODWORD(v2) = v73;
          if ( !v34 )
            continue;
          v35 = DeviceObject;
          *(_QWORD *)(v34 + 136) = DeviceObject;
          v36 = (unsigned int *)(v34 + 160);
          v38 = *(unsigned __int16 *)(W32GetUserSessionState(v35, v15) + 68736);
          *(_WORD *)(v34 + 216) = v38;
          *(_QWORD *)(v34 + 264) = 0;
          if ( !IsConsoleConnection )
            *v36 |= 0x4000000u;
          *(_QWORD *)(v34 + 224) = FileObject;
          if ( !IsConsoleConnection && !*(_DWORD *)(W32GetUserSessionState(v38, v37) + 68688)
            || (*(_DWORD *)(v34 + 252) = 0, !IsConsoleConnection) )
          {
            if ( !*(_DWORD *)(W32GetUserSessionState(v38, v37) + 68688) )
            {
              *(_QWORD *)(v34 + 240) = 0xFFFFFFFFLL;
              *(_QWORD *)(v34 + 232) = 0;
              *(_DWORD *)(v34 + 248) = *(_DWORD *)(v5 + 1172);
              goto LABEL_52;
            }
          }
          *((_QWORD *)&InputBuffer + 1) = VideoPortCallout;
          v83 = 0;
          v82 = 0;
          *(_QWORD *)&InputBuffer = v34;
          v43 = GreDeviceIoControlImpl(
                  *(PDEVICE_OBJECT *)(v34 + 136),
                  0x23201Fu,
                  &InputBuffer,
                  0x28u,
                  &InputBuffer,
                  0x28u,
                  v77,
                  1u,
                  1);
          updated = v43;
          if ( v43 >= 0 )
          {
            if ( (_DWORD)v82 )
              *(_DWORD *)(v34 + 160) |= 0x40000000u;
            if ( (v83 & 0xC0000001) == 0 )
            {
              if ( (v83 & 0x20000000) != 0 )
                *v36 |= 0x100000u;
              v45 = *(struct _DEVICE_OBJECT **)(v34 + 136);
              *(_QWORD *)(v34 + 144) = *((_QWORD *)&v82 + 1);
              *(_DWORD *)(v34 + 248) = 0;
              v84 = 0;
              v85 = 0;
              updated = GreDeviceIoControlImpl(v45, 0x232033u, 0, 0, &v84, 0x20u, v77, 1u, 1);
              if ( updated < 0 )
              {
                if ( !IsConsoleConnection )
                  goto LABEL_83;
              }
              else
              {
                if ( (_DWORD)v84 != 2 )
                {
                  WdLogSingleEntry0(1);
                  WdLogGlobalForLineNumber = 9492;
                }
                UserSessionState = W32GetUserSessionState(v46, v44);
                if ( *(_QWORD *)(UserSessionState + 68680) != *((_QWORD *)&v85 + 1) )
                  goto LABEL_83;
                v48 = *((_QWORD *)&v84 + 1);
                if ( !*((_QWORD *)&v84 + 1) )
                  goto LABEL_83;
                *v36 |= 0x800000u;
                *(_QWORD *)(v34 + 232) = v48;
                *(_DWORD *)(v34 + 248) = DWORD1(v84);
                *(_QWORD *)(v34 + 240) = v85;
              }
LABEL_52:
              updated = DrvForceChildDeviceReenumeration(DeviceObject, (struct _DEVICE_RELATIONS **)&P);
              if ( updated >= 0 )
              {
                v39 = (struct _DEVICE_OBJECT *)*((_QWORD *)P + 1);
                ExFreePoolWithTag(P, 0);
                updated = IoOpenDeviceRegistryKey(v39, 2u, 0x2000000u, &DeviceRegKey);
                if ( updated >= 0 )
                {
                  DrvGetDeviceConfigurationInformation((unsigned int *)v34, (WCHAR *)DeviceRegKey, 1);
                  ZwClose(DeviceRegKey);
                }
                ObfDereferenceObject(v39);
              }
              swprintf_s((wchar_t *)v34, 0x20u, (const wchar_t *)&QueryTable);
              ++*(_DWORD *)(v5 + 1172);
              if ( updated >= 0
                || (v40 = DrvGetRegistryHandleFromDeviceMap((unsigned __int16 *)v34, 0, 0, 0, 0, &updated),
                    DeviceRegKey = v40,
                    updated >= 0)
                && (DrvGetDeviceConfigurationInformation((unsigned int *)v34, (WCHAR *)v40, 0),
                    ZwClose(DeviceRegKey),
                    updated >= 0) )
              {
                if ( !*(_QWORD *)(v34 + 208) )
                {
                  v41 = (unsigned __int16 *)PALLOCNOZ(32, 1936876615);
                  *(_QWORD *)(v34 + 208) = v41;
                  if ( v41 )
                  {
                    RegistryHandleFromDeviceMap = DrvGetRegistryHandleFromDeviceMap(
                                                    (unsigned __int16 *)v34,
                                                    0,
                                                    0,
                                                    v41,
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
              v49 = (wchar_t *)(v34 + 64);
              if ( (*v36 & 8) != 0 )
              {
                ++*(_DWORD *)(v5 + 1180);
                swprintf_s(v49, 0x20u, L"\\\\.\\DISPLAYV%d");
              }
              else
              {
                ++*(_DWORD *)(v5 + 1176);
                swprintf_s(v49, 0x20u, L"\\\\.\\DISPLAY%d");
              }
              PruneFlag = DrvGetPruneFlag((struct tagGRAPHICS_DEVICE *)v34);
              v51 = *v36 & 0xFFF7FFFF;
              if ( !PruneFlag )
                v51 = *v36 | 0x80000;
              *v36 = v51;
              if ( (unsigned int)bSetDeviceSessionUsage(v34, 1) )
              {
                if ( IsConsoleConnection )
                  goto LABEL_107;
              }
              else if ( IsConsoleConnection || *(_DWORD *)(W32GetUserSessionState(v16, v15) + 68688) )
              {
                DrvCleanupOneGraphicsDevice((_DWORD *)v34, v15);
                goto LABEL_64;
              }
              if ( !*(_DWORD *)(W32GetUserSessionState(v16, v15) + 68688) )
              {
                v54 = *(_QWORD *)(W32GetSessionState(v53) + 88);
                *(_QWORD *)(v34 + 272) = 0;
                v55 = *(_DWORD *)(v54 + 3000) ? *(_QWORD *)(v54 + 3004) : 0LL;
                *(_QWORD *)(v34 + 288) = v55;
                *(_QWORD *)(v34 + 296) = 0;
                v72[0] = 0;
                v56 = DxDdGetDxgkWin32kInterface(0);
                if ( (*(int (__fastcall **)(__int64, __int64, __int64, __int64, _BYTE *))(v56 + 392))(
                       v34 + 272,
                       v34 + 288,
                       v34 + 296,
                       v34 + 280,
                       v72) >= 0 )
                {
                  v57 = *(_DWORD *)(v34 + 164);
                  if ( v72[0] )
                    v58 = v57 | 4;
                  else
                    v58 = v57 & 0xFFFFFFFB;
                  *(_DWORD *)(v34 + 164) = v58;
                  DrvUpdateRemoteAdapterInfo((struct tagGRAPHICS_DEVICE *)v34);
                }
              }
              if ( !*(_DWORD *)(W32GetUserSessionState(v53, v52) + 68688) && updated < 0 )
              {
                DrvCleanupOneGraphicsDevice((_DWORD *)v34, v15);
                --*(_DWORD *)(v5 + 1176);
                v22 = v70;
                v74 = 0;
                goto LABEL_65;
              }
LABEL_107:
              if ( *(_QWORD *)(v5 + 1184) )
                *(_QWORD *)(*(_QWORD *)(v5 + 1192) + 128LL) = v34;
              else
                *(_QWORD *)(v5 + 1184) = v34;
              *(_QWORD *)(v5 + 1192) = v34;
              if ( (*v36 & 0x800000) != 0 )
                DrvAddAdapterLuid(*(struct _LUID *)(v34 + 240));
              v22 = 1;
              v70 = 1;
              goto LABEL_65;
            }
            updated = -1073741637;
            WdLogSingleEntry2(5, (unsigned int)v83, -1073741637);
            WdLogGlobalForLineNumber = 9445;
          }
          else
          {
            WdLogSingleEntry1(5, v43);
            WdLogGlobalForLineNumber = 9425;
          }
LABEL_83:
          DrvCleanupOneGraphicsDevice((_DWORD *)v34, v44);
          goto LABEL_63;
        }
        if ( !IsConsoleConnection )
        {
          if ( !*(_DWORD *)(W32GetUserSessionState(v32, v31) + 68688) && *(_DWORD *)(v5 + 2936) == 1 )
          {
            v33 = *(struct _FILE_OBJECT **)(v5 + 2944);
            FileObject = v33;
            if ( v33 )
            {
              DeviceObject = IoGetRelatedDeviceObject(v33);
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
            v22 = v70;
            updated = -1073741772;
            goto LABEL_117;
          }
          DeviceObjectPointer = updated;
        }
        WdLogSingleEntry1(5, DeviceObjectPointer);
        WdLogGlobalForLineNumber = 9364;
LABEL_63:
        ++*(_DWORD *)(v5 + 1172);
LABEL_64:
        v22 = v70;
LABEL_65:
        LODWORD(v2) = v73;
        continue;
      }
      return 0;
    }
    break;
  }
  if ( !IsConsoleConnection )
  {
LABEL_117:
    if ( !*(_DWORD *)(W32GetUserSessionState(v24, v23) + 68688) )
    {
      SessionState = W32GetSessionState(v60);
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
    DrvSortGraphicsDeviceList(v62);
  v63 = *(_DWORD *)(v5 + 1172);
  v64 = *(_QWORD *)(v5 + 1184);
  v65 = *(_QWORD *)(v5 + 1192);
  v66 = *(_DWORD *)(v5 + 1176);
  v67 = *(_DWORD *)(v5 + 1180);
  if ( IsConsoleConnection )
  {
    *(_DWORD *)(v5 + 1268) = v63;
    *(_QWORD *)(v5 + 1280) = v64;
    *(_QWORD *)(v5 + 1296) = v65;
    *(_DWORD *)(v5 + 1328) = v66;
    *(_DWORD *)(v5 + 1332) = v67;
  }
  else
  {
    *(_DWORD *)(v5 + 1264) = v63;
    *(_QWORD *)(v5 + 1272) = v64;
    *(_QWORD *)(v5 + 1288) = v65;
    *(_DWORD *)(v5 + 1336) = v66;
    *(_DWORD *)(v5 + 1340) = v67;
    if ( !VerifyRemoteVidPnSourceIdsAreValid(v64) )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 9832;
    }
  }
  P = (PVOID)(unsigned int)Feature_RestrictXpdm_Block3rdPartyDrivers__private_featureState;
  if ( (Feature_RestrictXpdm_Block3rdPartyDrivers__private_featureState & 0x10) == 0 )
  {
    *(_QWORD *)v77 = __PAIR64__(HIDWORD(P), Feature_RestrictXpdm_Block3rdPartyDrivers__private_featureState | 1u);
    wil_details_FeatureReporting_ReportUsageToService(
      Feature_RestrictXpdm_Block3rdPartyDrivers__private_descriptor,
      __PAIR64__(HIDWORD(P), Feature_RestrictXpdm_Block3rdPartyDrivers__private_featureState | 1u),
      3);
    wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(
      *(_QWORD *)v77,
      3,
      Feature_RestrictXpdm_Block3rdPartyDrivers__private_descriptor);
  }
  v68 = v74;
  WdLogSingleEntry1(5, (int)v74);
  result = v68;
  WdLogGlobalForLineNumber = 9858;
  return result;
}

```

## disassembly

```asm
0x14018f010  push    rbp
0x14018f012  push    rbx
0x14018f013  push    rsi
0x14018f014  push    rdi
0x14018f015  push    r12
0x14018f017  push    r13
0x14018f019  push    r14
0x14018f01b  push    r15
0x14018f01d  lea     rbp, [rsp-78h]
0x14018f022  sub     rsp, 178h
0x14018f029  mov     rax, cs:__security_cookie
0x14018f030  xor     rax, rsp
0x14018f033  mov     [rbp+0B0h+var_50], rax
0x14018f037  xor     r15d, r15d
0x14018f03a  movsxd  r14, ecx
0x14018f03d  mov     [rsp+1B0h+var_154], r14d
0x14018f042  mov     [rsp+1B0h+var_14C], r15d
0x14018f047  mov     [rbp+0B0h+DeviceObject], r15
0x14018f04b  mov     [rsp+1B0h+FileObject], r15
0x14018f050  call    UserIsConsoleConnection
0x14018f055  xorps   xmm0, xmm0
0x14018f058  movsxd  r13, eax
0x14018f05b  xor     eax, eax
0x14018f05d  mov     [rbp+0B0h+P], r15
0x14018f061  mov     [rbp+0B0h+var_100], rax
0x14018f065  mov     [rsp+1B0h+var_15C], r15d
0x14018f06a  mov     [rsp+1B0h+DeviceRegKey], r15
0x14018f06f  movups  [rbp+0B0h+InputBuffer], xmm0
0x14018f073  movups  [rbp+0B0h+var_110], xmm0
0x14018f077  lea     ebx, [rax+4]
0x14018f07a  mov     r8, r13
0x14018f07d  mov     ecx, ebx
0x14018f07f  mov     rdx, r14
0x14018f082  call    cs:__imp_WdLogSingleEntry2
0x14018f089  nop     dword ptr [rax+rax+00h]
0x14018f08e  mov     cs:WdLogGlobalForLineNumber, 2379h
0x14018f098  call    cs:__imp_W32GetSessionState
0x14018f09f  nop     dword ptr [rax+rax+00h]
0x14018f0a4  mov     rdi, [rax+58h]
0x14018f0a8  test    r13d, r13d
0x14018f0ab  jz      short loc_14018F0D2
0x14018f0ad  lea     r9, [rdi+534h]
0x14018f0b4  lea     r8, [rdi+530h]
0x14018f0bb  lea     rdx, [rdi+510h]
0x14018f0c2  lea     rcx, [rdi+500h]
0x14018f0c9  lea     rax, [rdi+4F4h]
0x14018f0d0  jmp     short loc_14018F0F5
0x14018f0d2  lea     r9, [rdi+53Ch]
0x14018f0d9  lea     r8, [rdi+538h]
0x14018f0e0  lea     rdx, [rdi+508h]
0x14018f0e7  lea     rcx, [rdi+4F8h]
0x14018f0ee  lea     rax, [rdi+4F0h]
0x14018f0f5  mov     rcx, [rcx]
0x14018f0f8  mov     rdx, [rdx]
0x14018f0fb  mov     r8d, [r8]
0x14018f0fe  mov     r9d, [r9]
0x14018f101  mov     eax, [rax]
0x14018f103  mov     [rdi+494h], eax
0x14018f109  mov     [rdi+4A0h], rcx
0x14018f110  mov     [rdi+4A8h], rdx
0x14018f117  mov     [rdi+498h], r8d
0x14018f11e  mov     [rdi+49Ch], r9d
0x14018f125  test    r13d, r13d
0x14018f128  jz      short loc_14018F19E
0x14018f12a  xorps   xmm0, xmm0
0x14018f12d  mov     [rsp+1B0h+var_150], r15d
0x14018f132  lea     rax, aMaxobjectnumbe; "MaxObjectNumber"
0x14018f139  mov     [rbp+0B0h+QueryTable.QueryRoutine], r15
0x14018f13d  mov     [rbp+0B0h+QueryTable.Name], rax
0x14018f141  lea     r8, [rbp+0B0h+QueryTable]; QueryTable
0x14018f145  lea     rax, [rsp+1B0h+var_14C]
0x14018f14a  mov     [rbp+0B0h+QueryTable.Flags], 120h
0x14018f151  mov     [rbp+0B0h+QueryTable.EntryContext], rax
0x14018f155  lea     rdx, aVideo_0; "VIDEO"
0x14018f15c  lea     rax, [rsp+1B0h+var_150]
0x14018f161  mov     [rbp+0B0h+QueryTable.DefaultType], 4000004h
0x14018f168  xor     r9d, r9d; Context
0x14018f16b  mov     [rbp+0B0h+QueryTable.DefaultData], rax
0x14018f16f  mov     ecx, ebx; RelativeTo
0x14018f171  mov     [rbp+0B0h+QueryTable.DefaultLength], ebx
0x14018f174  mov     [rbp+0B0h+var_88], r15
0x14018f178  mov     [rbp+0B0h+var_80], r15d
0x14018f17c  mov     [rbp+0B0h+var_78], r15
0x14018f180  movups  [rbp+0B0h+var_70], xmm0
0x14018f184  mov     [rsp+1B0h+Environment], r15; Environment
0x14018f189  movups  [rbp+0B0h+var_60], xmm0
0x14018f18d  call    cs:__imp_RtlQueryRegistryValues
0x14018f194  nop     dword ptr [rax+rax+00h]
0x14018f199  jmp     loc_14018F257
0x14018f19e  call    UserIsWddmConnectedSession
0x14018f1a3  test    eax, eax
0x14018f1a5  jz      short loc_14018F226
0x14018f1a7  mov     [rsp+1B0h+var_150], r15d
0x14018f1ac  call    cs:__imp_DxDdGetDxgkWin32kInterface
0x14018f1b3  nop     dword ptr [rax+rax+00h]
0x14018f1b8  lea     rdx, [rsp+1B0h+var_14C]
0x14018f1bd  lea     rcx, [rsp+1B0h+var_150]
0x14018f1c2  mov     rax, [rax+300h]
0x14018f1c9  call    _guard_dispatch_icall
0x14018f1ce  mov     [rsp+1B0h+var_15C], eax
0x14018f1d2  test    eax, eax
0x14018f1d4  jns     short loc_14018F1FE
0x14018f1d6  movsxd  rdx, eax
0x14018f1d9  mov     ecx, 2
0x14018f1de  call    cs:__imp_WdLogSingleEntry1
0x14018f1e5  nop     dword ptr [rax+rax+00h]
0x14018f1ea  mov     cs:WdLogGlobalForLineNumber, 23B7h
0x14018f1f4  mov     eax, [rdi+494h]
0x14018f1fa  mov     [rsp+1B0h+var_14C], eax
0x14018f1fe  mov     ecx, [rdi+494h]
0x14018f204  mov     eax, [rsp+1B0h+var_150]
0x14018f208  cmp     eax, ecx
0x14018f20a  jbe     short loc_14018F214
0x14018f20c  mov     [rdi+494h], eax
0x14018f212  jmp     short loc_14018F216
0x14018f214  mov     eax, ecx
0x14018f216  add     eax, 10h
0x14018f219  cmp     [rsp+1B0h+var_14C], eax
0x14018f21d  jb      short loc_14018F257
0x14018f21f  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14018f224  jmp     short loc_14018F257
0x14018f226  call    UserIsDisconnectConnection
0x14018f22b  test    eax, eax
0x14018f22d  jnz     short loc_14018F23B
0x14018f22f  mov     eax, [rdi+0B78h]
0x14018f235  dec     eax
0x14018f237  mov     [rsp+1B0h+var_14C], eax
0x14018f23b  cmp     [rdi+0BB8h], r15d
0x14018f242  jz      short loc_14018F257
0x14018f244  xor     ecx, ecx; struct tagGRAPHICS_DEVICE *
0x14018f246  call    ?DrvUpdateRemoteAdapterInfo@@YAJPEAUtagGRAPHICS_DEVICE@@@Z; DrvUpdateRemoteAdapterInfo(tagGRAPHICS_DEVICE *)
0x14018f24b  mov     [rsp+1B0h+var_15C], eax
0x14018f24f  test    eax, eax
0x14018f251  js      loc_14018FA63
0x14018f257  mov     bl, r15b
0x14018f25a  mov     [rsp+1B0h+var_150], 1
0x14018f262  mov     [rsp+1B0h+var_160], bl
0x14018f266  mov     rsi, r15
0x14018f269  call    UserIsDisconnectConnection
0x14018f26e  test    eax, eax
0x14018f270  jnz     loc_14018FA6A
0x14018f276  mov     eax, [rsp+1B0h+var_14C]
0x14018f27a  cmp     [rdi+494h], eax
0x14018f280  ja      loc_14018FA6A
0x14018f286  test    r14d, r14d
0x14018f289  jz      loc_14018FA48
0x14018f28f  call    UserIsWddmConnectedSession
0x14018f294  mov     ecx, [rdi+494h]
0x14018f29a  test    eax, eax
0x14018f29c  jnz     short loc_14018F2A7
0x14018f29e  mov     r9, [rdi+0BB0h]
0x14018f2a5  jmp     short loc_14018F2CD
0x14018f2a7  test    r13d, r13d
0x14018f2aa  jz      short loc_14018F2C6
0x14018f2ac  mov     r9d, ecx
0x14018f2af  lea     r8, aDeviceVideoD; "\\Device\\Video%d"
0x14018f2b6  lea     rcx, [rbp+0B0h+QueryTable]; unsigned __int16 *
0x14018f2ba  mov     edx, 32h ; '2'; unsigned __int64
0x14018f2bf  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14018f2c4  jmp     short loc_14018F2E6
0x14018f2c6  lea     r9, aRemotevideo; "RemoteVideo"
0x14018f2cd  mov     dword ptr [rsp+1B0h+Environment], ecx
0x14018f2d1  lea     r8, aDeviceSD; "\\Device\\%s%d"
0x14018f2d8  lea     rcx, [rbp+0B0h+QueryTable]; unsigned __int16 *
0x14018f2dc  mov     edx, 32h ; '2'; unsigned __int64
0x14018f2e1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14018f2e6  test    eax, eax
0x14018f2e8  js      loc_14018FA63
0x14018f2ee  mov     rbx, [rdi+4A0h]
0x14018f2f5  lea     rax, [rdi+510h]
0x14018f2fc  test    r13d, r13d
0x14018f2ff  jnz     short loc_14018F308
0x14018f301  lea     rax, [rdi+508h]
0x14018f308  mov     r14, [rax]
0x14018f30b  jmp     short loc_14018F333
0x14018f30d  mov     r8d, 40h ; '@'; MaxCount
0x14018f313  lea     rcx, [rbp+0B0h+QueryTable]; Str1
0x14018f317  mov     rdx, rbx; Str2
0x14018f31a  call    wcsncmp_0
0x14018f31f  test    eax, eax
0x14018f321  jz      loc_14018F63B
0x14018f327  cmp     rbx, r14
0x14018f32a  jz      short loc_14018F338
0x14018f32c  mov     rbx, [rbx+80h]
0x14018f333  test    rbx, rbx
0x14018f336  jnz     short loc_14018F30D
0x14018f338  xorps   xmm0, xmm0
0x14018f33b  lea     rdx, [rbp+0B0h+QueryTable]; SourceString
0x14018f33f  lea     rcx, [rbp+0B0h+DestinationString]; DestinationString
0x14018f343  movups  xmmword ptr [rbp+0B0h+DestinationString.Length], xmm0
0x14018f347  call    cs:__imp_RtlInitUnicodeString
0x14018f34e  nop     dword ptr [rax+rax+00h]
0x14018f353  lea     r9, [rbp+0B0h+DeviceObject]; DeviceObject
0x14018f357  xor     edx, edx; DesiredAccess
0x14018f359  lea     r8, [rsp+1B0h+FileObject]; FileObject
0x14018f35e  lea     rcx, [rbp+0B0h+DestinationString]; ObjectName
0x14018f362  call    cs:__imp_IoGetDeviceObjectPointer
0x14018f369  nop     dword ptr [rax+rax+00h]
0x14018f36e  mov     [rsp+1B0h+var_15C], eax
0x14018f372  test    eax, eax
0x14018f374  jns     short loc_14018F3EF
0x14018f376  test    r13d, r13d
0x14018f379  jnz     loc_14018F653
0x14018f37f  call    cs:__imp_W32GetUserSessionState
0x14018f386  nop     dword ptr [rax+rax+00h]
0x14018f38b  cmp     [rax+10C50h], r15d
0x14018f392  jnz     loc_14018F64F
0x14018f398  cmp     dword ptr [rdi+0B78h], 1
0x14018f39f  jnz     loc_14018F64F
0x14018f3a5  mov     rax, [rdi+0B80h]
0x14018f3ac  mov     [rsp+1B0h+FileObject], rax
0x14018f3b1  test    rax, rax
0x14018f3b4  jz      loc_14018FA3A
0x14018f3ba  mov     rcx, rax; FileObject
0x14018f3bd  call    cs:__imp_IoGetRelatedDeviceObject
0x14018f3c4  nop     dword ptr [rax+rax+00h]
0x14018f3c9  mov     [rbp+0B0h+DeviceObject], rax
0x14018f3cd  mov     rax, [rsp+1B0h+FileObject]
0x14018f3d2  test    rax, rax
0x14018f3d5  jz      loc_14018FA3A
0x14018f3db  cmp     [rbp+0B0h+DeviceObject], r15
0x14018f3df  jz      loc_14018FA3A
0x14018f3e5  mov     [rsp+1B0h+var_15C], r15d
0x14018f3ea  mov     [rsp+1B0h+FileObject], r15
0x14018f3ef  test    rsi, rsi
0x14018f3f2  jnz     short loc_14018F418
0x14018f3f4  mov     edx, 76646747h
0x14018f3f9  mov     ecx, 130h
0x14018f3fe  call    PALLOCMEM
0x14018f403  mov     bl, [rsp+1B0h+var_160]
0x14018f407  mov     rsi, rax
0x14018f40a  mov     r14d, [rsp+1B0h+var_154]
0x14018f40f  test    rax, rax
0x14018f412  jz      loc_14018F269
0x14018f418  mov     rcx, [rbp+0B0h+DeviceObject]
0x14018f41c  mov     [rsi+88h], rcx
0x14018f423  call    cs:__imp_W32GetUserSessionState
0x14018f42a  nop     dword ptr [rax+rax+00h]
0x14018f42f  lea     r12, [rsi+0A0h]
0x14018f436  movzx   ecx, word ptr [rax+10C80h]
0x14018f43d  mov     [rsi+0D8h], cx
0x14018f444  mov     [rsi+108h], r15
0x14018f44b  test    r13d, r13d
0x14018f44e  jnz     short loc_14018F456
0x14018f450  bts     dword ptr [r12], 1Ah
0x14018f456  mov     rax, [rsp+1B0h+FileObject]
0x14018f45b  mov     [rsi+0E0h], rax
0x14018f462  test    r13d, r13d
0x14018f465  jnz     short loc_14018F47C
0x14018f467  call    cs:__imp_W32GetUserSessionState
0x14018f46e  nop     dword ptr [rax+rax+00h]
0x14018f473  cmp     [rax+10C50h], r15d
0x14018f47a  jz      short loc_14018F48C
0x14018f47c  mov     [rsi+0FCh], r15d
0x14018f483  test    r13d, r13d
0x14018f486  jnz     loc_14018F673
0x14018f48c  call    cs:__imp_W32GetUserSessionState
0x14018f493  nop     dword ptr [rax+rax+00h]
0x14018f498  cmp     [rax+10C50h], r15d
0x14018f49f  jnz     loc_14018F673
0x14018f4a5  mov     rax, cs:qword_1402663E8
0x14018f4ac  mov     r14d, 20h ; ' '
0x14018f4b2  mov     [rsi+0F0h], rax
0x14018f4b9  mov     [rsi+0E8h], r15
0x14018f4c0  mov     eax, [rdi+494h]
0x14018f4c6  mov     [rsi+0F8h], eax
0x14018f4cc  mov     rcx, [rbp+0B0h+DeviceObject]; DeviceObject
0x14018f4d0  lea     rdx, [rbp+0B0h+P]; struct _DEVICE_RELATIONS **
0x14018f4d4  call    ?DrvForceChildDeviceReenumeration@@YAJPEAU_DEVICE_OBJECT@@PEAPEAU_DEVICE_RELATIONS@@@Z; DrvForceChildDeviceReenumeration(_DEVICE_OBJECT *,_DEVICE_RELATIONS * *)
0x14018f4d9  mov     [rsp+1B0h+var_15C], eax
0x14018f4dd  test    eax, eax
0x14018f4df  js      short loc_14018F551
0x14018f4e1  mov     rcx, [rbp+0B0h+P]; P
0x14018f4e5  xor     edx, edx; Tag
0x14018f4e7  mov     rbx, [rcx+8]
0x14018f4eb  call    cs:__imp_ExFreePoolWithTag
0x14018f4f2  nop     dword ptr [rax+rax+00h]
0x14018f4f7  lea     r9, [rsp+1B0h+DeviceRegKey]; DeviceRegKey
0x14018f4fc  mov     edx, 2; DevInstKeyType
0x14018f501  mov     r8d, 2000000h; DesiredAccess
0x14018f507  mov     rcx, rbx; DeviceObject
0x14018f50a  call    cs:__imp_IoOpenDeviceRegistryKey
0x14018f511  nop     dword ptr [rax+rax+00h]
0x14018f516  mov     [rsp+1B0h+var_15C], eax
0x14018f51a  test    eax, eax
0x14018f51c  js      short loc_14018F542
0x14018f51e  mov     rdx, [rsp+1B0h+DeviceRegKey]; Path
0x14018f523  mov     r8d, 1; int
0x14018f529  mov     rcx, rsi; Context
0x14018f52c  call    ?DrvGetDeviceConfigurationInformation@@YAXPEAUtagGRAPHICS_DEVICE@@PEAXH@Z; DrvGetDeviceConfigurationInformation(tagGRAPHICS_DEVICE *,void *,int)
0x14018f531  mov     rcx, [rsp+1B0h+DeviceRegKey]; Handle
0x14018f536  call    cs:__imp_ZwClose
0x14018f53d  nop     dword ptr [rax+rax+00h]
0x14018f542  mov     rcx, rbx; Object
0x14018f545  call    cs:__imp_ObfDereferenceObject
0x14018f54c  nop     dword ptr [rax+rax+00h]
0x14018f551  lea     r8, [rbp+0B0h+QueryTable]; Format
0x14018f555  mov     rdx, r14; SizeInWords
0x14018f558  mov     rcx, rsi; Dst
0x14018f55b  call    cs:__imp_swprintf_s
  ... truncated ...
```
