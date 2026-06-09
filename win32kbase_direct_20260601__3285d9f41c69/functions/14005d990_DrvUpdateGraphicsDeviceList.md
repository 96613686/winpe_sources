# DrvUpdateGraphicsDeviceList

- ea: `0x14005d990`
- end: `0x14005e594`
- name: `DrvUpdateGraphicsDeviceList`
- size: `3076`
- prototype: ``
- caller_count: `5`
- callee_count: `26`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140035240`
- `0x14005e5a0`
- `0x1400fd03c`
- `0x1401ccd24`
- `0x1401cd54c`

## callees

- `0x14000dc4c`
- `0x140033cf0`
- `0x1400492a4`
- `0x14005d990`
- `0x1400a8ed0`
- `0x1400a9150`
- `0x1400a96e0`
- `0x1400a9be8`
- `0x1400ab4f0`
- `0x1400abd4c`
- `0x1400abe40`
- `0x1400ae870`
- `0x14010bd30`
- `0x140110520`
- `0x14015f35c`
- `0x14016a5dc`
- `0x14016cd48`
- `0x14017bec0`
- `0x1401810bc`
- `0x140189760`
- `0x140192dac`
- `0x1401b3aec`
- `0x1401b9ce0`
- `0x14023813e`
- `0x140238160`
- `0x140238240`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14005deb6`
- `ntoskrnl!ZwClose` at `0x14005df36`
- `ntoskrnl!ZwClose` at `0x14005dfaa`
- `ntoskrnl!ZwClose` at `0x14005deb6`
- `ntoskrnl!ZwClose` at `0x14005df36`
- `ntoskrnl!ZwClose` at `0x14005dfaa`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005de6b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005de6b`
- `ntoskrnl!RtlQueryRegistryValues` at `0x14005db0d`
- `ntoskrnl!RtlQueryRegistryValues` at `0x14005db0d`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14005dd3d`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14005dd3d`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x14005dce2`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x14005dce2`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x14005de8a`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x14005de8a`
- `ntoskrnl!swprintf_s` at `0x14005dedb`
- `ntoskrnl!swprintf_s` at `0x14005e20f`
- `ntoskrnl!swprintf_s` at `0x14005dedb`
- `ntoskrnl!swprintf_s` at `0x14005e20f`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005dcc7`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005dcc7`
- `ntoskrnl!ObfDereferenceObject` at `0x14005dec5`
- `ntoskrnl!ObfDereferenceObject` at `0x14005dec5`
- `watchdog!WdLogSingleEntry0` at `0x14005e147`
- `watchdog!WdLogSingleEntry0` at `0x14005e3cd`
- `watchdog!WdLogSingleEntry0` at `0x14005e431`
- `watchdog!WdLogSingleEntry0` at `0x14005e44e`
- `watchdog!WdLogSingleEntry0` at `0x14005e4e6`
- `watchdog!WdLogSingleEntry0` at `0x14005e147`
- `watchdog!WdLogSingleEntry0` at `0x14005e3cd`
- `watchdog!WdLogSingleEntry0` at `0x14005e431`
- `watchdog!WdLogSingleEntry0` at `0x14005e44e`
- `watchdog!WdLogSingleEntry0` at `0x14005e4e6`
- `watchdog!WdLogSingleEntry1` at `0x14005db5e`
- `watchdog!WdLogSingleEntry1` at `0x14005dfdb`
- `watchdog!WdLogSingleEntry1` at `0x14005e062`
- `watchdog!WdLogSingleEntry1` at `0x14005e55b`
- `watchdog!WdLogSingleEntry1` at `0x14005db5e`
- `watchdog!WdLogSingleEntry1` at `0x14005dfdb`
- `watchdog!WdLogSingleEntry1` at `0x14005e062`
- `watchdog!WdLogSingleEntry1` at `0x14005e55b`
- `watchdog!WdLogSingleEntry2` at `0x14005da02`
- `watchdog!WdLogSingleEntry2` at `0x14005e0ac`
- `watchdog!WdLogSingleEntry2` at `0x14005da02`
- `watchdog!WdLogSingleEntry2` at `0x14005e0ac`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x14005db2c`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x14005e2de`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x14005db2c`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x14005e2de`
- `WIN32K!W32GetSessionState` at `0x14005da18`
- `WIN32K!W32GetSessionState` at `0x14005e297`
- `WIN32K!W32GetSessionState` at `0x14005e404`
- `WIN32K!W32GetSessionState` at `0x14005da18`
- `WIN32K!W32GetSessionState` at `0x14005e297`
- `WIN32K!W32GetSessionState` at `0x14005e404`
- `WIN32K!W32GetUserSessionState` at `0x14005dcff`
- `WIN32K!W32GetUserSessionState` at `0x14005dda3`
- `WIN32K!W32GetUserSessionState` at `0x14005dde7`
- `WIN32K!W32GetUserSessionState` at `0x14005de0c`
- `WIN32K!W32GetUserSessionState` at `0x14005e15d`
- `WIN32K!W32GetUserSessionState` at `0x14005e250`
- `WIN32K!W32GetUserSessionState` at `0x14005e27e`
- `WIN32K!W32GetUserSessionState` at `0x14005e33a`
- `WIN32K!W32GetUserSessionState` at `0x14005e3ef`
- `WIN32K!W32GetUserSessionState` at `0x14005dcff`
- `WIN32K!W32GetUserSessionState` at `0x14005dda3`
- `WIN32K!W32GetUserSessionState` at `0x14005dde7`
- `WIN32K!W32GetUserSessionState` at `0x14005de0c`
- `WIN32K!W32GetUserSessionState` at `0x14005e15d`
- `WIN32K!W32GetUserSessionState` at `0x14005e250`
- `WIN32K!W32GetUserSessionState` at `0x14005e27e`
- `WIN32K!W32GetUserSessionState` at `0x14005e33a`
- `WIN32K!W32GetUserSessionState` at `0x14005e3ef`

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
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // r8
  const wchar_t *v26; // r9
  int v27; // eax
  __int64 v28; // rbx
  __int64 *v29; // rax
  __int64 v30; // r14
  NTSTATUS DeviceObjectPointer; // eax
  __int64 v32; // rdx
  __int64 v33; // rcx
  __int64 v34; // r8
  struct _FILE_OBJECT *v35; // rax
  __int64 v36; // rdx
  __int64 v37; // rsi
  __int64 v38; // r8
  PDEVICE_OBJECT v39; // rcx
  unsigned int *v40; // r12
  __int64 v41; // rdx
  __int64 v42; // rcx
  __int64 v43; // r8
  struct _DEVICE_OBJECT *v44; // rbx
  HANDLE v45; // rax
  unsigned __int16 *v46; // rax
  HANDLE RegistryHandleFromDeviceMap; // rax
  int v48; // eax
  struct _DEVICE_OBJECT *v49; // rcx
  __int64 v50; // rdx
  __int64 v51; // rcx
  __int64 v52; // r8
  __int64 UserSessionState; // rax
  __int64 v54; // rax
  wchar_t *v55; // rcx
  int PruneFlag; // eax
  unsigned int v57; // edx
  __int64 v58; // rdx
  __int64 v59; // rcx
  __int64 v60; // r8
  __int64 v61; // rdx
  __int64 v62; // rcx
  __int64 v63; // r8
  __int64 v64; // rax
  __int64 v65; // rdx
  __int64 v66; // r8
  __int64 v67; // rax
  __int64 v68; // rax
  int v69; // eax
  unsigned int v70; // eax
  __int64 result; // rax
  __int64 v72; // rcx
  __int64 SessionState; // rax
  int v74; // eax
  __int64 v75; // rcx
  __int64 v76; // rdx
  int v77; // r8d
  int v78; // r9d
  unsigned int v79; // ebx
  PVOID Environment; // [rsp+20h] [rbp-E0h]
  char v81; // [rsp+50h] [rbp-B0h]
  NTSTATUS updated; // [rsp+54h] [rbp-ACh] BYREF
  _BYTE v83[4]; // [rsp+58h] [rbp-A8h] BYREF
  int v84; // [rsp+5Ch] [rbp-A4h]
  unsigned int v85; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v86; // [rsp+64h] [rbp-9Ch] BYREF
  void *DeviceRegKey; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v88[2]; // [rsp+70h] [rbp-90h] BYREF
  PFILE_OBJECT FileObject; // [rsp+78h] [rbp-88h] BYREF
  PDEVICE_OBJECT DeviceObject; // [rsp+80h] [rbp-80h] BYREF
  PVOID P; // [rsp+88h] [rbp-78h] BYREF
  __int128 InputBuffer; // [rsp+90h] [rbp-70h] BYREF
  __int128 v93; // [rsp+A0h] [rbp-60h]
  __int64 v94; // [rsp+B0h] [rbp-50h]
  __int128 v95; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v96; // [rsp+C8h] [rbp-38h]
  struct _UNICODE_STRING DestinationString; // [rsp+D8h] [rbp-28h] BYREF
  struct _RTL_QUERY_REGISTRY_TABLE QueryTable; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v99; // [rsp+128h] [rbp+28h]
  int v100; // [rsp+130h] [rbp+30h]
  __int64 v101; // [rsp+138h] [rbp+38h]
  __int128 v102; // [rsp+140h] [rbp+40h]
  __int128 v103; // [rsp+150h] [rbp+50h]

  v1 = (int)a1;
  v84 = a1;
  v86 = 0;
  DeviceObject = 0;
  FileObject = 0;
  IsConsoleConnection = (int)UserIsConsoleConnection(a1);
  P = 0;
  v94 = 0;
  updated = 0;
  DeviceRegKey = 0;
  InputBuffer = 0;
  v93 = 0;
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
    v85 = 0;
    QueryTable.QueryRoutine = 0;
    QueryTable.Name = L"MaxObjectNumber";
    QueryTable.Flags = 288;
    QueryTable.EntryContext = &v86;
    QueryTable.DefaultType = 67108868;
    QueryTable.DefaultData = &v85;
    QueryTable.DefaultLength = 4;
    v99 = 0;
    v100 = 0;
    v101 = 0;
    v102 = 0;
    v103 = 0;
    RtlQueryRegistryValues(4u, L"VIDEO", &QueryTable, 0, 0);
  }
  else if ( (unsigned int)UserIsWddmConnectedSession() )
  {
    v85 = 0;
    DxgkWin32kInterface = DxDdGetDxgkWin32kInterface(v15, v14, v16);
    v18 = (*(__int64 (__fastcall **)(unsigned int *, unsigned int *))(DxgkWin32kInterface + 768))(&v85, &v86);
    updated = v18;
    if ( v18 < 0 )
    {
      WdLogSingleEntry1(2, v18);
      WdLogGlobalForLineNumber = 9143;
      v86 = *(_DWORD *)(v4 + 1172);
    }
    v20 = *(unsigned int *)(v4 + 1172);
    v21 = v85;
    if ( v85 <= (unsigned int)v20 )
      v21 = *(_DWORD *)(v4 + 1172);
    else
      *(_DWORD *)(v4 + 1172) = v85;
    if ( v86 >= v21 + 16 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v20, v19);
  }
  else
  {
    if ( !(unsigned int)UserIsDisconnectConnection() )
      v86 = *(_DWORD *)(v4 + 2936) - 1;
    if ( *(_DWORD *)(v4 + 3000) )
    {
      updated = DrvUpdateRemoteAdapterInfo(0);
      if ( updated < 0 )
        return 0;
    }
  }
  v22 = 0;
  v85 = 1;
  v81 = 0;
  while ( 2 )
  {
    if ( !(unsigned int)UserIsDisconnectConnection() && *(_DWORD *)(v4 + 1172) <= v86 )
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
          v27 = StringCchPrintfW(
                  (unsigned __int16 *)&QueryTable,
                  0x32u,
                  L"\\Device\\Video%d",
                  *(unsigned int *)(v4 + 1172));
          goto LABEL_28;
        }
        v26 = L"RemoteVideo";
      }
      else
      {
        v26 = *(const wchar_t **)(v4 + 2992);
      }
      LODWORD(Environment) = *(_DWORD *)(v4 + 1172);
      v27 = StringCchPrintfW((unsigned __int16 *)&QueryTable, 0x32u, L"\\Device\\%s%d", v26, Environment);
LABEL_28:
      if ( v27 >= 0 )
      {
        v28 = *(_QWORD *)(v4 + 1184);
        v29 = (__int64 *)(v4 + 1296);
        if ( !(_DWORD)IsConsoleConnection )
          v29 = (__int64 *)(v4 + 1288);
        v30 = *v29;
        while ( v28 )
        {
          if ( !wcsncmp_0((const wchar_t *)&QueryTable, (const wchar_t *)v28, 0x40u) )
            goto LABEL_63;
          if ( v28 == v30 )
            break;
          v28 = *(_QWORD *)(v28 + 128);
        }
        DestinationString = 0;
        RtlInitUnicodeString(&DestinationString, (PCWSTR)&QueryTable);
        DeviceObjectPointer = IoGetDeviceObjectPointer(&DestinationString, 0, &FileObject, &DeviceObject);
        updated = DeviceObjectPointer;
        if ( DeviceObjectPointer >= 0 )
        {
LABEL_44:
          v22 = v81;
          v37 = PALLOCMEM(304, 1986291527);
          LODWORD(v1) = v84;
          if ( !v37 )
            continue;
          v39 = DeviceObject;
          *(_QWORD *)(v37 + 136) = DeviceObject;
          v40 = (unsigned int *)(v37 + 160);
          v42 = *(unsigned __int16 *)(W32GetUserSessionState(v39, v36, v38) + 68736);
          *(_WORD *)(v37 + 216) = v42;
          *(_QWORD *)(v37 + 264) = 0;
          if ( !(_DWORD)IsConsoleConnection )
            *v40 |= 0x4000000u;
          *(_QWORD *)(v37 + 224) = FileObject;
          if ( !(_DWORD)IsConsoleConnection && !*(_DWORD *)(W32GetUserSessionState(v42, v41, v43) + 68688)
            || (*(_DWORD *)(v37 + 252) = 0, !(_DWORD)IsConsoleConnection) )
          {
            if ( !*(_DWORD *)(W32GetUserSessionState(v42, v41, v43) + 68688) )
            {
              *(_QWORD *)(v37 + 240) = 0xFFFFFFFFLL;
              *(_QWORD *)(v37 + 232) = 0;
              *(_DWORD *)(v37 + 248) = *(_DWORD *)(v4 + 1172);
              goto LABEL_52;
            }
          }
          *((_QWORD *)&InputBuffer + 1) = VideoPortCallout;
          v94 = 0;
          v93 = 0;
          *(_QWORD *)&InputBuffer = v37;
          v48 = GreDeviceIoControlImpl(
                  *(PDEVICE_OBJECT *)(v37 + 136),
                  0x23201Fu,
                  &InputBuffer,
                  0x28u,
                  &InputBuffer,
                  0x28u,
                  v88,
                  1u,
                  1);
          updated = v48;
          if ( v48 >= 0 )
          {
            if ( (_DWORD)v93 )
              *(_DWORD *)(v37 + 160) |= 0x40000000u;
            if ( (v94 & 0xC0000001) == 0 )
            {
              if ( (v94 & 0x20000000) != 0 )
                *v40 |= 0x100000u;
              v49 = *(struct _DEVICE_OBJECT **)(v37 + 136);
              *(_QWORD *)(v37 + 144) = *((_QWORD *)&v93 + 1);
              *(_DWORD *)(v37 + 248) = 0;
              v95 = 0;
              v96 = 0;
              updated = GreDeviceIoControlImpl(v49, 0x232033u, 0, 0, &v95, 0x20u, v88, 1u, 1);
              if ( updated < 0 )
              {
                if ( !(_DWORD)IsConsoleConnection )
                  goto LABEL_83;
              }
              else
              {
                if ( (_DWORD)v95 != 2 )
                {
                  WdLogSingleEntry0(1);
                  WdLogGlobalForLineNumber = 9492;
                }
                UserSessionState = W32GetUserSessionState(v51, v50, v52);
                if ( *(_QWORD *)(UserSessionState + 68680) != *((_QWORD *)&v96 + 1) )
                  goto LABEL_83;
                v54 = *((_QWORD *)&v95 + 1);
                if ( !*((_QWORD *)&v95 + 1) )
                  goto LABEL_83;
                *v40 |= 0x800000u;
                *(_QWORD *)(v37 + 232) = v54;
                *(_DWORD *)(v37 + 248) = DWORD1(v95);
                *(_QWORD *)(v37 + 240) = v96;
              }
LABEL_52:
              updated = DrvForceChildDeviceReenumeration(DeviceObject, (struct _DEVICE_RELATIONS **)&P);
              if ( updated >= 0 )
              {
                v44 = (struct _DEVICE_OBJECT *)*((_QWORD *)P + 1);
                ExFreePoolWithTag(P, 0);
                updated = IoOpenDeviceRegistryKey(v44, 2u, 0x2000000u, &DeviceRegKey);
                if ( updated >= 0 )
                {
                  DrvGetDeviceConfigurationInformation((unsigned int *)v37, (WCHAR *)DeviceRegKey, 1);
                  ZwClose(DeviceRegKey);
                }
                ObfDereferenceObject(v44);
              }
              swprintf_s((wchar_t *)v37, 0x20u, (const wchar_t *)&QueryTable);
              ++*(_DWORD *)(v4 + 1172);
              if ( updated >= 0
                || (v45 = DrvGetRegistryHandleFromDeviceMap((unsigned __int16 *)v37, 0, 0, 0, 0, &updated),
                    DeviceRegKey = v45,
                    updated >= 0)
                && (DrvGetDeviceConfigurationInformation((unsigned int *)v37, (WCHAR *)v45, 0),
                    ZwClose(DeviceRegKey),
                    updated >= 0) )
              {
                if ( !*(_QWORD *)(v37 + 208) )
                {
                  v46 = (unsigned __int16 *)PALLOCNOZ(32, 1936876615);
                  *(_QWORD *)(v37 + 208) = v46;
                  if ( v46 )
                  {
                    RegistryHandleFromDeviceMap = DrvGetRegistryHandleFromDeviceMap(
                                                    (unsigned __int16 *)v37,
                                                    0,
                                                    0,
                                                    v46,
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
              v55 = (wchar_t *)(v37 + 64);
              if ( (*v40 & 8) != 0 )
              {
                ++*(_DWORD *)(v4 + 1180);
                swprintf_s(v55, 0x20u, L"\\\\.\\DISPLAYV%d");
              }
              else
              {
                ++*(_DWORD *)(v4 + 1176);
                swprintf_s(v55, 0x20u, L"\\\\.\\DISPLAY%d");
              }
              PruneFlag = DrvGetPruneFlag((struct tagGRAPHICS_DEVICE *)v37);
              v57 = *v40 & 0xFFF7FFFF;
              if ( !PruneFlag )
                v57 = *v40 | 0x80000;
              *v40 = v57;
              if ( (unsigned int)bSetDeviceSessionUsage(v37, 1) )
              {
                if ( (_DWORD)IsConsoleConnection )
                  goto LABEL_107;
              }
              else if ( (_DWORD)IsConsoleConnection || *(_DWORD *)(W32GetUserSessionState(v59, v58, v60) + 68688) )
              {
                DrvCleanupOneGraphicsDevice((PVOID)v37);
                goto LABEL_64;
              }
              if ( !*(_DWORD *)(W32GetUserSessionState(v59, v58, v60) + 68688) )
              {
                v64 = *(_QWORD *)(W32GetSessionState(v62) + 88);
                *(_QWORD *)(v37 + 272) = 0;
                v67 = *(_DWORD *)(v64 + 3000) ? *(_QWORD *)(v64 + 3004) : 0LL;
                *(_QWORD *)(v37 + 288) = v67;
                *(_QWORD *)(v37 + 296) = 0;
                v83[0] = 0;
                v68 = DxDdGetDxgkWin32kInterface(0, v65, v66);
                if ( (*(int (__fastcall **)(__int64, __int64, __int64, __int64, _BYTE *))(v68 + 392))(
                       v37 + 272,
                       v37 + 288,
                       v37 + 296,
                       v37 + 280,
                       v83) >= 0 )
                {
                  v69 = *(_DWORD *)(v37 + 164);
                  if ( v83[0] )
                    v70 = v69 | 4;
                  else
                    v70 = v69 & 0xFFFFFFFB;
                  *(_DWORD *)(v37 + 164) = v70;
                  DrvUpdateRemoteAdapterInfo((struct tagGRAPHICS_DEVICE *)v37);
                }
              }
              if ( !*(_DWORD *)(W32GetUserSessionState(v62, v61, v63) + 68688) && updated < 0 )
              {
                DrvCleanupOneGraphicsDevice((PVOID)v37);
                --*(_DWORD *)(v4 + 1176);
                v22 = v81;
                v85 = 0;
                goto LABEL_65;
              }
LABEL_107:
              if ( *(_QWORD *)(v4 + 1184) )
                *(_QWORD *)(*(_QWORD *)(v4 + 1192) + 128LL) = v37;
              else
                *(_QWORD *)(v4 + 1184) = v37;
              *(_QWORD *)(v4 + 1192) = v37;
              if ( (*v40 & 0x800000) != 0 )
                DrvAddAdapterLuid(*(struct _LUID *)(v37 + 240));
              v22 = 1;
              v81 = 1;
              goto LABEL_65;
            }
            updated = -1073741637;
            WdLogSingleEntry2(5, (unsigned int)v94, -1073741637);
            WdLogGlobalForLineNumber = 9445;
          }
          else
          {
            WdLogSingleEntry1(5, v48);
            WdLogGlobalForLineNumber = 9425;
          }
LABEL_83:
          DrvCleanupOneGraphicsDevice((PVOID)v37);
          goto LABEL_63;
        }
        if ( !(_DWORD)IsConsoleConnection )
        {
          if ( !*(_DWORD *)(W32GetUserSessionState(v33, v32, v34) + 68688) && *(_DWORD *)(v4 + 2936) == 1 )
          {
            v35 = *(struct _FILE_OBJECT **)(v4 + 2944);
            FileObject = v35;
            if ( v35 )
            {
              DeviceObject = IoGetRelatedDeviceObject(v35);
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
            v22 = v81;
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
        v22 = v81;
LABEL_65:
        LODWORD(v1) = v84;
        continue;
      }
      return 0;
    }
    break;
  }
  if ( !(_DWORD)IsConsoleConnection )
  {
LABEL_117:
    if ( !*(_DWORD *)(W32GetUserSessionState(v24, v23, v25) + 68688) )
    {
      SessionState = W32GetSessionState(v72);
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
  v74 = *(_DWORD *)(v4 + 1172);
  v75 = *(_QWORD *)(v4 + 1184);
  v76 = *(_QWORD *)(v4 + 1192);
  v77 = *(_DWORD *)(v4 + 1176);
  v78 = *(_DWORD *)(v4 + 1180);
  if ( (_DWORD)IsConsoleConnection )
  {
    *(_DWORD *)(v4 + 1268) = v74;
    *(_QWORD *)(v4 + 1280) = v75;
    *(_QWORD *)(v4 + 1296) = v76;
    *(_DWORD *)(v4 + 1328) = v77;
    *(_DWORD *)(v4 + 1332) = v78;
  }
  else
  {
    *(_DWORD *)(v4 + 1264) = v74;
    *(_QWORD *)(v4 + 1272) = v75;
    *(_QWORD *)(v4 + 1288) = v76;
    *(_DWORD *)(v4 + 1336) = v77;
    *(_DWORD *)(v4 + 1340) = v78;
    if ( !(unsigned int)VerifyRemoteVidPnSourceIdsAreValid() )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 9832;
    }
  }
  P = (PVOID)(unsigned int)Feature_RestrictXpdm_Block3rdPartyDrivers__private_featureState;
  if ( (Feature_RestrictXpdm_Block3rdPartyDrivers__private_featureState & 0x10) == 0 )
  {
    *(_QWORD *)v88 = __PAIR64__(HIDWORD(P), Feature_RestrictXpdm_Block3rdPartyDrivers__private_featureState | 1u);
    wil_details_FeatureReporting_ReportUsageToService(
      Feature_RestrictXpdm_Block3rdPartyDrivers__private_descriptor,
      __PAIR64__(HIDWORD(P), Feature_RestrictXpdm_Block3rdPartyDrivers__private_featureState | 1u),
      3,
      1);
    wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(
      *(_QWORD *)v88,
      3,
      Feature_RestrictXpdm_Block3rdPartyDrivers__private_descriptor);
  }
  v79 = v85;
  WdLogSingleEntry1(5, (int)v85);
  result = v79;
  WdLogGlobalForLineNumber = 9858;
  return result;
}

```

## disassembly

```asm
0x14005d990  push    rbp
0x14005d992  push    rbx
0x14005d993  push    rsi
0x14005d994  push    rdi
0x14005d995  push    r12
0x14005d997  push    r13
0x14005d999  push    r14
0x14005d99b  push    r15
0x14005d99d  lea     rbp, [rsp-78h]
0x14005d9a2  sub     rsp, 178h
0x14005d9a9  mov     rax, cs:__security_cookie
0x14005d9b0  xor     rax, rsp
0x14005d9b3  mov     [rbp+0B0h+var_50], rax
0x14005d9b7  xor     r15d, r15d
0x14005d9ba  movsxd  r14, ecx
0x14005d9bd  mov     [rsp+1B0h+var_154], r14d
0x14005d9c2  mov     [rsp+1B0h+var_14C], r15d
0x14005d9c7  mov     [rbp+0B0h+DeviceObject], r15
0x14005d9cb  mov     [rsp+1B0h+FileObject], r15
0x14005d9d0  call    UserIsConsoleConnection
0x14005d9d5  xorps   xmm0, xmm0
0x14005d9d8  movsxd  r13, eax
0x14005d9db  xor     eax, eax
0x14005d9dd  mov     [rbp+0B0h+P], r15
0x14005d9e1  mov     [rbp+0B0h+var_100], rax
0x14005d9e5  mov     [rsp+1B0h+var_15C], r15d
0x14005d9ea  mov     [rsp+1B0h+DeviceRegKey], r15
0x14005d9ef  movups  [rbp+0B0h+InputBuffer], xmm0
0x14005d9f3  movups  [rbp+0B0h+var_110], xmm0
0x14005d9f7  lea     ebx, [rax+4]
0x14005d9fa  mov     r8, r13
0x14005d9fd  mov     ecx, ebx
0x14005d9ff  mov     rdx, r14
0x14005da02  call    cs:__imp_WdLogSingleEntry2
0x14005da09  nop     dword ptr [rax+rax+00h]
0x14005da0e  mov     cs:WdLogGlobalForLineNumber, 2379h
0x14005da18  call    cs:__imp_W32GetSessionState
0x14005da1f  nop     dword ptr [rax+rax+00h]
0x14005da24  mov     rdi, [rax+58h]
0x14005da28  test    r13d, r13d
0x14005da2b  jz      short loc_14005DA52
0x14005da2d  lea     r9, [rdi+534h]
0x14005da34  lea     r8, [rdi+530h]
0x14005da3b  lea     rdx, [rdi+510h]
0x14005da42  lea     rcx, [rdi+500h]
0x14005da49  lea     rax, [rdi+4F4h]
0x14005da50  jmp     short loc_14005DA75
0x14005da52  lea     r9, [rdi+53Ch]
0x14005da59  lea     r8, [rdi+538h]
0x14005da60  lea     rdx, [rdi+508h]
0x14005da67  lea     rcx, [rdi+4F8h]
0x14005da6e  lea     rax, [rdi+4F0h]
0x14005da75  mov     rcx, [rcx]
0x14005da78  mov     rdx, [rdx]
0x14005da7b  mov     r8d, [r8]
0x14005da7e  mov     r9d, [r9]
0x14005da81  mov     eax, [rax]
0x14005da83  mov     [rdi+494h], eax
0x14005da89  mov     [rdi+4A0h], rcx
0x14005da90  mov     [rdi+4A8h], rdx
0x14005da97  mov     [rdi+498h], r8d
0x14005da9e  mov     [rdi+49Ch], r9d
0x14005daa5  test    r13d, r13d
0x14005daa8  jz      short loc_14005DB1E
0x14005daaa  xorps   xmm0, xmm0
0x14005daad  mov     [rsp+1B0h+var_150], r15d
0x14005dab2  lea     rax, aMaxobjectnumbe; "MaxObjectNumber"
0x14005dab9  mov     [rbp+0B0h+QueryTable.QueryRoutine], r15
0x14005dabd  mov     [rbp+0B0h+QueryTable.Name], rax
0x14005dac1  lea     r8, [rbp+0B0h+QueryTable]; QueryTable
0x14005dac5  lea     rax, [rsp+1B0h+var_14C]
0x14005daca  mov     [rbp+0B0h+QueryTable.Flags], 120h
0x14005dad1  mov     [rbp+0B0h+QueryTable.EntryContext], rax
0x14005dad5  lea     rdx, Path; "VIDEO"
0x14005dadc  lea     rax, [rsp+1B0h+var_150]
0x14005dae1  mov     [rbp+0B0h+QueryTable.DefaultType], 4000004h
0x14005dae8  xor     r9d, r9d; Context
0x14005daeb  mov     [rbp+0B0h+QueryTable.DefaultData], rax
0x14005daef  mov     ecx, ebx; RelativeTo
0x14005daf1  mov     [rbp+0B0h+QueryTable.DefaultLength], ebx
0x14005daf4  mov     [rbp+0B0h+var_88], r15
0x14005daf8  mov     [rbp+0B0h+var_80], r15d
0x14005dafc  mov     [rbp+0B0h+var_78], r15
0x14005db00  movups  [rbp+0B0h+var_70], xmm0
0x14005db04  mov     [rsp+1B0h+Environment], r15; Environment
0x14005db09  movups  [rbp+0B0h+var_60], xmm0
0x14005db0d  call    cs:__imp_RtlQueryRegistryValues
0x14005db14  nop     dword ptr [rax+rax+00h]
0x14005db19  jmp     loc_14005DBD7
0x14005db1e  call    UserIsWddmConnectedSession
0x14005db23  test    eax, eax
0x14005db25  jz      short loc_14005DBA6
0x14005db27  mov     [rsp+1B0h+var_150], r15d
0x14005db2c  call    cs:__imp_DxDdGetDxgkWin32kInterface
0x14005db33  nop     dword ptr [rax+rax+00h]
0x14005db38  lea     rdx, [rsp+1B0h+var_14C]
0x14005db3d  lea     rcx, [rsp+1B0h+var_150]
0x14005db42  mov     rax, [rax+300h]
0x14005db49  call    _guard_dispatch_icall
0x14005db4e  mov     [rsp+1B0h+var_15C], eax
0x14005db52  test    eax, eax
0x14005db54  jns     short loc_14005DB7E
0x14005db56  movsxd  rdx, eax
0x14005db59  mov     ecx, 2
0x14005db5e  call    cs:__imp_WdLogSingleEntry1
0x14005db65  nop     dword ptr [rax+rax+00h]
0x14005db6a  mov     cs:WdLogGlobalForLineNumber, 23B7h
0x14005db74  mov     eax, [rdi+494h]
0x14005db7a  mov     [rsp+1B0h+var_14C], eax
0x14005db7e  mov     ecx, [rdi+494h]
0x14005db84  mov     eax, [rsp+1B0h+var_150]
0x14005db88  cmp     eax, ecx
0x14005db8a  jbe     short loc_14005DB94
0x14005db8c  mov     [rdi+494h], eax
0x14005db92  jmp     short loc_14005DB96
0x14005db94  mov     eax, ecx
0x14005db96  add     eax, 10h
0x14005db99  cmp     [rsp+1B0h+var_14C], eax
0x14005db9d  jb      short loc_14005DBD7
0x14005db9f  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14005dba4  jmp     short loc_14005DBD7
0x14005dba6  call    UserIsDisconnectConnection
0x14005dbab  test    eax, eax
0x14005dbad  jnz     short loc_14005DBBB
0x14005dbaf  mov     eax, [rdi+0B78h]
0x14005dbb5  dec     eax
0x14005dbb7  mov     [rsp+1B0h+var_14C], eax
0x14005dbbb  cmp     [rdi+0BB8h], r15d
0x14005dbc2  jz      short loc_14005DBD7
0x14005dbc4  xor     ecx, ecx; struct tagGRAPHICS_DEVICE *
0x14005dbc6  call    ?DrvUpdateRemoteAdapterInfo@@YAJPEAUtagGRAPHICS_DEVICE@@@Z; DrvUpdateRemoteAdapterInfo(tagGRAPHICS_DEVICE *)
0x14005dbcb  mov     [rsp+1B0h+var_15C], eax
0x14005dbcf  test    eax, eax
0x14005dbd1  js      loc_14005E3E3
0x14005dbd7  mov     bl, r15b
0x14005dbda  mov     [rsp+1B0h+var_150], 1
0x14005dbe2  mov     [rsp+1B0h+var_160], bl
0x14005dbe6  mov     rsi, r15
0x14005dbe9  call    UserIsDisconnectConnection
0x14005dbee  test    eax, eax
0x14005dbf0  jnz     loc_14005E3EA
0x14005dbf6  mov     eax, [rsp+1B0h+var_14C]
0x14005dbfa  cmp     [rdi+494h], eax
0x14005dc00  ja      loc_14005E3EA
0x14005dc06  test    r14d, r14d
0x14005dc09  jz      loc_14005E3C8
0x14005dc0f  call    UserIsWddmConnectedSession
0x14005dc14  mov     ecx, [rdi+494h]
0x14005dc1a  test    eax, eax
0x14005dc1c  jnz     short loc_14005DC27
0x14005dc1e  mov     r9, [rdi+0BB0h]
0x14005dc25  jmp     short loc_14005DC4D
0x14005dc27  test    r13d, r13d
0x14005dc2a  jz      short loc_14005DC46
0x14005dc2c  mov     r9d, ecx
0x14005dc2f  lea     r8, aDeviceVideoD; "\\Device\\Video%d"
0x14005dc36  lea     rcx, [rbp+0B0h+QueryTable]; unsigned __int16 *
0x14005dc3a  mov     edx, 32h ; '2'; unsigned __int64
0x14005dc3f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14005dc44  jmp     short loc_14005DC66
0x14005dc46  lea     r9, aRemotevideo; "RemoteVideo"
0x14005dc4d  mov     dword ptr [rsp+1B0h+Environment], ecx
0x14005dc51  lea     r8, aDeviceSD; "\\Device\\%s%d"
0x14005dc58  lea     rcx, [rbp+0B0h+QueryTable]; unsigned __int16 *
0x14005dc5c  mov     edx, 32h ; '2'; unsigned __int64
0x14005dc61  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14005dc66  test    eax, eax
0x14005dc68  js      loc_14005E3E3
0x14005dc6e  mov     rbx, [rdi+4A0h]
0x14005dc75  lea     rax, [rdi+510h]
0x14005dc7c  test    r13d, r13d
0x14005dc7f  jnz     short loc_14005DC88
0x14005dc81  lea     rax, [rdi+508h]
0x14005dc88  mov     r14, [rax]
0x14005dc8b  jmp     short loc_14005DCB3
0x14005dc8d  mov     r8d, 40h ; '@'; MaxCount
0x14005dc93  lea     rcx, [rbp+0B0h+QueryTable]; Str1
0x14005dc97  mov     rdx, rbx; Str2
0x14005dc9a  call    wcsncmp_0
0x14005dc9f  test    eax, eax
0x14005dca1  jz      loc_14005DFBB
0x14005dca7  cmp     rbx, r14
0x14005dcaa  jz      short loc_14005DCB8
0x14005dcac  mov     rbx, [rbx+80h]
0x14005dcb3  test    rbx, rbx
0x14005dcb6  jnz     short loc_14005DC8D
0x14005dcb8  xorps   xmm0, xmm0
0x14005dcbb  lea     rdx, [rbp+0B0h+QueryTable]; SourceString
0x14005dcbf  lea     rcx, [rbp+0B0h+DestinationString]; DestinationString
0x14005dcc3  movups  xmmword ptr [rbp+0B0h+DestinationString.Length], xmm0
0x14005dcc7  call    cs:__imp_RtlInitUnicodeString
0x14005dcce  nop     dword ptr [rax+rax+00h]
0x14005dcd3  lea     r9, [rbp+0B0h+DeviceObject]; DeviceObject
0x14005dcd7  xor     edx, edx; DesiredAccess
0x14005dcd9  lea     r8, [rsp+1B0h+FileObject]; FileObject
0x14005dcde  lea     rcx, [rbp+0B0h+DestinationString]; ObjectName
0x14005dce2  call    cs:__imp_IoGetDeviceObjectPointer
0x14005dce9  nop     dword ptr [rax+rax+00h]
0x14005dcee  mov     [rsp+1B0h+var_15C], eax
0x14005dcf2  test    eax, eax
0x14005dcf4  jns     short loc_14005DD6F
0x14005dcf6  test    r13d, r13d
0x14005dcf9  jnz     loc_14005DFD3
0x14005dcff  call    cs:__imp_W32GetUserSessionState
0x14005dd06  nop     dword ptr [rax+rax+00h]
0x14005dd0b  cmp     [rax+10C50h], r15d
0x14005dd12  jnz     loc_14005DFCF
0x14005dd18  cmp     dword ptr [rdi+0B78h], 1
0x14005dd1f  jnz     loc_14005DFCF
0x14005dd25  mov     rax, [rdi+0B80h]
0x14005dd2c  mov     [rsp+1B0h+FileObject], rax
0x14005dd31  test    rax, rax
0x14005dd34  jz      loc_14005E3BA
0x14005dd3a  mov     rcx, rax; FileObject
0x14005dd3d  call    cs:__imp_IoGetRelatedDeviceObject
0x14005dd44  nop     dword ptr [rax+rax+00h]
0x14005dd49  mov     [rbp+0B0h+DeviceObject], rax
0x14005dd4d  mov     rax, [rsp+1B0h+FileObject]
0x14005dd52  test    rax, rax
0x14005dd55  jz      loc_14005E3BA
0x14005dd5b  cmp     [rbp+0B0h+DeviceObject], r15
0x14005dd5f  jz      loc_14005E3BA
0x14005dd65  mov     [rsp+1B0h+var_15C], r15d
0x14005dd6a  mov     [rsp+1B0h+FileObject], r15
0x14005dd6f  test    rsi, rsi
0x14005dd72  jnz     short loc_14005DD98
0x14005dd74  mov     edx, 76646747h
0x14005dd79  mov     ecx, 130h
0x14005dd7e  call    PALLOCMEM
0x14005dd83  mov     bl, [rsp+1B0h+var_160]
0x14005dd87  mov     rsi, rax
0x14005dd8a  mov     r14d, [rsp+1B0h+var_154]
0x14005dd8f  test    rax, rax
0x14005dd92  jz      loc_14005DBE9
0x14005dd98  mov     rcx, [rbp+0B0h+DeviceObject]
0x14005dd9c  mov     [rsi+88h], rcx
0x14005dda3  call    cs:__imp_W32GetUserSessionState
0x14005ddaa  nop     dword ptr [rax+rax+00h]
0x14005ddaf  lea     r12, [rsi+0A0h]
0x14005ddb6  movzx   ecx, word ptr [rax+10C80h]
0x14005ddbd  mov     [rsi+0D8h], cx
0x14005ddc4  mov     [rsi+108h], r15
0x14005ddcb  test    r13d, r13d
0x14005ddce  jnz     short loc_14005DDD6
0x14005ddd0  bts     dword ptr [r12], 1Ah
0x14005ddd6  mov     rax, [rsp+1B0h+FileObject]
0x14005dddb  mov     [rsi+0E0h], rax
0x14005dde2  test    r13d, r13d
0x14005dde5  jnz     short loc_14005DDFC
0x14005dde7  call    cs:__imp_W32GetUserSessionState
0x14005ddee  nop     dword ptr [rax+rax+00h]
0x14005ddf3  cmp     [rax+10C50h], r15d
0x14005ddfa  jz      short loc_14005DE0C
0x14005ddfc  mov     [rsi+0FCh], r15d
0x14005de03  test    r13d, r13d
0x14005de06  jnz     loc_14005DFF3
0x14005de0c  call    cs:__imp_W32GetUserSessionState
0x14005de13  nop     dword ptr [rax+rax+00h]
0x14005de18  cmp     [rax+10C50h], r15d
0x14005de1f  jnz     loc_14005DFF3
0x14005de25  mov     rax, cs:qword_1402654D8
0x14005de2c  mov     r14d, 20h ; ' '
0x14005de32  mov     [rsi+0F0h], rax
0x14005de39  mov     [rsi+0E8h], r15
0x14005de40  mov     eax, [rdi+494h]
0x14005de46  mov     [rsi+0F8h], eax
0x14005de4c  mov     rcx, [rbp+0B0h+DeviceObject]; DeviceObject
0x14005de50  lea     rdx, [rbp+0B0h+P]; struct _DEVICE_RELATIONS **
0x14005de54  call    ?DrvForceChildDeviceReenumeration@@YAJPEAU_DEVICE_OBJECT@@PEAPEAU_DEVICE_RELATIONS@@@Z; DrvForceChildDeviceReenumeration(_DEVICE_OBJECT *,_DEVICE_RELATIONS * *)
0x14005de59  mov     [rsp+1B0h+var_15C], eax
0x14005de5d  test    eax, eax
0x14005de5f  js      short loc_14005DED1
0x14005de61  mov     rcx, [rbp+0B0h+P]; P
0x14005de65  xor     edx, edx; Tag
0x14005de67  mov     rbx, [rcx+8]
0x14005de6b  call    cs:__imp_ExFreePoolWithTag
0x14005de72  nop     dword ptr [rax+rax+00h]
0x14005de77  lea     r9, [rsp+1B0h+DeviceRegKey]; DeviceRegKey
0x14005de7c  mov     edx, 2; DevInstKeyType
0x14005de81  mov     r8d, 2000000h; DesiredAccess
0x14005de87  mov     rcx, rbx; DeviceObject
0x14005de8a  call    cs:__imp_IoOpenDeviceRegistryKey
0x14005de91  nop     dword ptr [rax+rax+00h]
0x14005de96  mov     [rsp+1B0h+var_15C], eax
0x14005de9a  test    eax, eax
0x14005de9c  js      short loc_14005DEC2
0x14005de9e  mov     rdx, [rsp+1B0h+DeviceRegKey]; Path
0x14005dea3  mov     r8d, 1; int
0x14005dea9  mov     rcx, rsi; Context
0x14005deac  call    ?DrvGetDeviceConfigurationInformation@@YAXPEAUtagGRAPHICS_DEVICE@@PEAXH@Z; DrvGetDeviceConfigurationInformation(tagGRAPHICS_DEVICE *,void *,int)
0x14005deb1  mov     rcx, [rsp+1B0h+DeviceRegKey]; Handle
0x14005deb6  call    cs:__imp_ZwClose
0x14005debd  nop     dword ptr [rax+rax+00h]
0x14005dec2  mov     rcx, rbx; Object
0x14005dec5  call    cs:__imp_ObfDereferenceObject
0x14005decc  nop     dword ptr [rax+rax+00h]
0x14005ded1  lea     r8, [rbp+0B0h+QueryTable]; Format
0x14005ded5  mov     rdx, r14; SizeInWords
0x14005ded8  mov     rcx, rsi; Dst
0x14005dedb  call    cs:__imp_swprintf_s
  ... truncated ...
```
