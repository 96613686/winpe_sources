# InternalNotifyExecute(void *,WLNOTIFICATION_ID,_WLN_CLIENT_PARAMS *,void (*)(void *,ushort const *),void *,ushort *)

- ea: `0x1400403d8`
- end: `0x140041189`
- name: `?InternalNotifyExecute@@YAKPEAXW4WLNOTIFICATION_ID@@PEAT_WLN_CLIENT_PARAMS@@P6AX0PEBG@Z0PEAG@Z`
- size: `3505`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `16`
- callee_count: `30`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140017240`
- `0x140040284`
- `0x1400402b8`
- `0x140047370`
- `0x14004c400`
- `0x1400500f0`
- `0x140052c20`
- `0x1400625d0`
- `0x140063660`
- `0x140063ba0`
- `0x1400640c0`
- `0x14006e220`
- `0x140071140`
- `0x1400714b0`
- `0x140084e20`
- `0x140085320`

## callees

- `0x1400057f4`
- `0x14000fb30`
- `0x140013050`
- `0x140025d50`
- `0x1400269f0`
- `0x1400295f0`
- `0x14002ec10`
- `0x140034700`
- `0x1400360a0`
- `0x140037b84`
- `0x140039e98`
- `0x14003a5d0`
- `0x14003af90`
- `0x14003ca4c`
- `0x1400403d8`
- `0x140041c34`
- `0x1400491e0`
- `0x140049440`
- `0x14004df08`
- `0x140053720`
- `0x1400544e0`
- `0x14005f43c`
- `0x1400916dc`
- `0x140091d08`
- `0x14009244c`
- `0x1400926d8`
- `0x1400928b0`
- `0x1400928ec`
- `0x140092950`
- `0x1400a1010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140040fb3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140040fb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140040bcc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140040bcc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14004052d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14004060e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14004052d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14004060e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14004056b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140040648`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14004056b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140040648`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400405d7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004066a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400405d7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004066a`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x1400404e9`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x1400404e9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140040c4e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140040c4e`
- `ntdll!TpSetTimer` at `0x140040ba1`
- `ntdll!TpSetTimer` at `0x140040ba1`
- `ntdll!WinSqmAddToStream` at `0x140040867`
- `ntdll!WinSqmAddToStream` at `0x140040a4f`
- `ntdll!WinSqmAddToStream` at `0x140040b16`
- `ntdll!WinSqmAddToStream` at `0x140040d21`
- `ntdll!WinSqmAddToStream` at `0x140040867`
- `ntdll!WinSqmAddToStream` at `0x140040a4f`
- `ntdll!WinSqmAddToStream` at `0x140040b16`
- `ntdll!WinSqmAddToStream` at `0x140040d21`
- `ext-ms-win-session-winsta-l1-1-4!WinStationSetLastWinlogonNotification` at `0x140040bc2`
- `ext-ms-win-session-winsta-l1-1-4!WinStationSetLastWinlogonNotification` at `0x140040bc2`

## string_xrefs

- `0x140040fa8`: `TrustedInstaller`
- `0x140040bd7`: `lsm.dll`

## pseudocode

```c
__int64 __fastcall InternalNotifyExecute(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        void (__fastcall *a4)(_QWORD, unsigned __int16 *),
        __int64 a5,
        __int64 a6)
{
  __int64 v6; // r13
  unsigned int v8; // r14d
  unsigned int v9; // ebx
  int v10; // edx
  int v11; // esi
  __int64 v12; // r8
  const wchar_t *v13; // rcx
  __int64 v14; // rdx
  struct _NOTIFICATION_CLIENT_DEF *v15; // rcx
  unsigned int v16; // r9d
  const struct _EVENT_DESCRIPTOR *v17; // rcx
  unsigned __int64 v18; // rax
  __int64 v19; // rdx
  __int64 v20; // r9
  CUser *v21; // rcx
  __int64 v22; // rdx
  CUser *v23; // rcx
  __int64 v24; // rdx
  unsigned int v25; // r9d
  __int64 v26; // rcx
  __int64 v27; // r8
  DWORD LastError; // eax
  int v29; // ebx
  const struct _EVENT_DESCRIPTOR *v30; // rcx
  unsigned int v31; // eax
  unsigned int v32; // eax
  unsigned int v33; // eax
  unsigned int v34; // eax
  unsigned int v35; // eax
  unsigned int v36; // eax
  unsigned int v37; // eax
  unsigned int v38; // eax
  int v39; // eax
  CUser *v40; // rcx
  unsigned int v41; // eax
  unsigned int v43; // [rsp+30h] [rbp-308h] BYREF
  int v44; // [rsp+34h] [rbp-304h]
  int v45; // [rsp+38h] [rbp-300h] BYREF
  unsigned int v46; // [rsp+3Ch] [rbp-2FCh] BYREF
  BYTE Data[4]; // [rsp+40h] [rbp-2F8h] BYREF
  int v48; // [rsp+44h] [rbp-2F4h]
  DWORD cbData; // [rsp+48h] [rbp-2F0h] BYREF
  HKEY hKey[2]; // [rsp+50h] [rbp-2E8h] BYREF
  DWORD Type; // [rsp+60h] [rbp-2D8h] BYREF
  int v52; // [rsp+64h] [rbp-2D4h]
  int v53; // [rsp+68h] [rbp-2D0h]
  int v54; // [rsp+6Ch] [rbp-2CCh]
  DWORD v55; // [rsp+70h] [rbp-2C8h] BYREF
  __int64 v56; // [rsp+78h] [rbp-2C0h] BYREF
  void (__fastcall *v57)(_QWORD, unsigned __int16 *); // [rsp+80h] [rbp-2B8h]
  int v58; // [rsp+88h] [rbp-2B0h]
  __int64 v59; // [rsp+90h] [rbp-2A8h]
  __int64 v60; // [rsp+98h] [rbp-2A0h]
  struct _OSVERSIONINFOW VersionInformation; // [rsp+A0h] [rbp-298h] BYREF
  char v62; // [rsp+1BAh] [rbp-17Eh]
  __int128 v63; // [rsp+1C0h] [rbp-178h] BYREF
  __int128 v64; // [rsp+1D0h] [rbp-168h]
  __int128 v65; // [rsp+1E0h] [rbp-158h]
  unsigned __int16 v66[128]; // [rsp+1F0h] [rbp-148h] BYREF

  v57 = (void (__fastcall *)(_QWORD, unsigned __int16 *))a4;
  v60 = a3;
  v6 = (int)a2;
  v59 = a6;
  v8 = 0;
  v43 = 0;
  v9 = 0;
  v46 = 0;
  v45 = 1;
  v48 = (a2 & 0xFFFFFFFD) == 0;
  if ( !a1 || *(_DWORD *)a1 != 88 || a2 >= *(_DWORD *)(a1 + 16) )
    return 160;
  v54 = 0;
  _mm_lfence();
  WLEventWrite(&WLEvt_NotifyExecute_Start, a2);
  if ( (!(_DWORD)v6 || (unsigned int)(v6 - 2) <= 1) && !dword_1400D3268 )
  {
    hKey[0] = 0;
    memset_0(&VersionInformation, 0, 0x11Cu);
    cbData = 0;
    *(_DWORD *)Data = 0;
    Type = 0;
    dword_1400D3268 = 64;
    VersionInformation.dwOSVersionInfoSize = 284;
    if ( GetVersionExW(&VersionInformation) && v62 == 1 )
    {
      v11 = 16;
      dword_1400D3268 = 16;
    }
    else
    {
      v11 = 16;
    }
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon", 0, 1u, hKey) )
    {
      cbData = 4;
      if ( !RegQueryValueExW(hKey[0], L"UIVerbosityLevel", 0, &Type, Data, &cbData) )
      {
        if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            79,
            WPP_c4e026e548883477c15208e9f0c6fcb8_Traceguids,
            *(unsigned int *)Data);
        }
        dword_1400D3268 = *(_DWORD *)Data;
      }
      RegCloseKey(hKey[0]);
    }
    if ( !RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System",
            0,
            1u,
            hKey) )
    {
      cbData = 4;
      if ( !RegQueryValueExW(hKey[0], L"VerboseStatus", 0, &Type, Data, &cbData) )
      {
        if ( *(_DWORD *)Data )
          v11 = 64;
        dword_1400D3268 = v11;
      }
      RegCloseKey(hKey[0]);
    }
  }
  *(_DWORD *)(a1 + 48) = v6;
  *(_QWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 64) = 0;
  *(_DWORD *)(a1 + 72) = -1;
  v53 = 0;
LABEL_26:
  if ( v8 < *(_DWORD *)(*(_QWORD *)(a1 + 24) + 16 * v6) )
  {
    v63 = 0;
    v64 = 0;
    v65 = 0;
    Timer::Timer((Timer *)hKey, v10);
    DWORD2(v63) = v6;
    LODWORD(v63) = 1;
    v12 = *(_QWORD *)(a1 + 24);
    v13 = *(const wchar_t **)(*(_QWORD *)(v12 + 16 * v6 + 8) + 8LL * v8);
    if ( !v13 || !*v13 )
      v13 = L"(null)";
    *((_QWORD *)&v64 + 1) = v13;
    LODWORD(v64) = 2;
    WLEventWrite(
      &WLEvt_NotifySubscriber_Start,
      v6,
      *(const unsigned __int16 **)(*(_QWORD *)(v12 + 16 * v6 + 8) + 8LL * v8));
    v14 = *(_QWORD *)(a1 + 24);
    *(_QWORD *)(a1 + 56) = *(_QWORD *)(*(_QWORD *)(v14 + 16 * v6 + 8) + 8LL * v8);
    *(_DWORD *)(a1 + 72) = -1;
    GetSubscriberDisplayName(
      (struct _NOTIFICATION_CLIENT_DEF *)a1,
      *(struct _NOTIFICATION_COMPONENT **)(*(_QWORD *)(v14 + 16 * v6 + 8) + 8LL * v8));
    if ( v57 && (unsigned int)dword_1400D3268 >= 0x20 )
    {
      ConstructInitialMessageForSubscriber(
        v15,
        *(struct _NOTIFICATION_COMPONENT **)(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 16 * v6 + 8) + 8LL * v8),
        v66,
        v16);
      v57(0, v66);
    }
    v43 = ConnectToSubscriber(
            (struct _NOTIFICATION_CLIENT_DEF *)a1,
            *(struct _NOTIFICATION_COMPONENT **)(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 16 * v6 + 8) + 8LL * v8),
            v48,
            &v46,
            &v45,
            (struct _NOTIFICATION_COMPONENT **)(a1 + 64));
    *(_DWORD *)(a1 + 72) = v43;
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WinlogonNotifySubscriberRefactor>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WinlogonNotifySubscriberRefactor>::GetImpl'::`2'::impl) )
    {
      if ( v43 )
      {
        WLEventWrite(
          v17,
          v6,
          v43,
          *(const unsigned __int16 **)(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 16 * v6 + 8) + 8LL * v8));
        WLEventWrite(
          &WLEvt_NotifySubscriber_Stop,
          v6,
          *(const unsigned __int16 **)(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 16 * v6 + 8) + 8LL * v8));
        Timer::Stop((Timer *)hKey);
        DWORD2(v65) = Timer::ElapsedULONG((Timer *)hKey);
        LODWORD(v65) = 1;
        WinSqmAddToStream(0, 6416, 3, &v63);
        v20 = *(_QWORD *)(a1 + 24);
        *(_QWORD *)(a1 + 64) = *(_QWORD *)(*(_QWORD *)(v20 + 16 * v6 + 8) + 8LL * v8);
        if ( v45 )
          goto LABEL_136;
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_150;
        }
        v22 = 86;
        goto LABEL_42;
      }
      goto LABEL_59;
    }
    if ( v43 )
    {
      v18 = v43 - 1702;
      if ( (unsigned int)v18 > 0x33 || (v19 = 0x8000003108001LL, !_bittest64(&v19, v18)) )
      {
        LogConnectToSubscriberFailure(
          v43,
          (unsigned int)v6,
          *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 16 * v6 + 8) + 8LL * v8));
        Timer::Stop((Timer *)hKey);
        DWORD2(v65) = Timer::ElapsedULONG((Timer *)hKey);
        LODWORD(v65) = 1;
        WinSqmAddToStream(0, 6416, 3, &v63);
        v20 = *(_QWORD *)(a1 + 24);
        *(_QWORD *)(a1 + 64) = *(_QWORD *)(*(_QWORD *)(v20 + 16 * v6 + 8) + 8LL * v8);
        if ( v45 )
          goto LABEL_136;
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_150;
        }
        v22 = 80;
        goto LABEL_42;
      }
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          82,
          WPP_c4e026e548883477c15208e9f0c6fcb8_Traceguids,
          *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 16 * v6 + 8) + 8LL * v8));
      }
      FreeRpcBinding(*(struct _NOTIFICATION_COMPONENT **)(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 16 * v6 + 8) + 8LL * v8));
      v25 = ConnectToSubscriber(
              (struct _NOTIFICATION_CLIENT_DEF *)a1,
              *(struct _NOTIFICATION_COMPONENT **)(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 16 * v6 + 8) + 8LL * v8),
              v48,
              &v46,
              &v45,
              (struct _NOTIFICATION_COMPONENT **)(a1 + 64));
      v43 = v25;
      *(_DWORD *)(a1 + 72) = v25;
      if ( v25 )
      {
        if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            84,
            WPP_c4e026e548883477c15208e9f0c6fcb8_Traceguids,
            *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 16 * v6 + 8) + 8LL * v8));
          v25 = v43;
        }
        LogConnectToSubscriberFailure(
          v25,
          (unsigned int)v6,
          *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 16 * v6 + 8) + 8LL * v8));
        Timer::Stop((Timer *)hKey);
        DWORD2(v65) = Timer::ElapsedULONG((Timer *)hKey);
        LODWORD(v65) = 1;
        WinSqmAddToStream(0, 6416, 3, &v63);
        v20 = *(_QWORD *)(a1 + 24);
        *(_QWORD *)(a1 + 64) = *(_QWORD *)(*(_QWORD *)(v20 + 16 * v6 + 8) + 8LL * v8);
        if ( v45 )
          goto LABEL_136;
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_150;
        }
        v22 = 85;
LABEL_42:
        WPP_SF_S(
          *((_QWORD *)v21 + 2),
          v22,
          WPP_c4e026e548883477c15208e9f0c6fcb8_Traceguids,
          *(_QWORD *)(*(_QWORD *)(v20 + 16 * v6 + 8) + 8LL * v8));
        goto LABEL_150;
      }
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        goto LABEL_59;
      }
      v24 = 83;
    }
    else
    {
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        goto LABEL_59;
      }
      v24 = 81;
    }
    WPP_SF_S(
      *((_QWORD *)v23 + 2),
      v24,
      WPP_c4e026e548883477c15208e9f0c6fcb8_Traceguids,
      *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 16 * v6 + 8) + 8LL * v8));
LABEL_59:
    v52 = 0;
    while ( 1 )
    {
      v66[0] = 0;
      v44 = 0;
      *(_DWORD *)(a1 + 76) = 0;
      v26 = *(_QWORD *)(a1 + 80);
      if ( v26 )
      {
        v56 = -600000000;
        TpSetTimer(v26, &v56, 0, 0);
      }
      v27 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 16 * v6 + 8) + 8LL * v8);
      if ( !(unsigned __int8)WinStationSetLastWinlogonNotification(
                               (unsigned int)v6,
                               v27 + 34,
                               *(unsigned int *)(v27 + 596)) )
      {
        LastError = GetLastError();
        MicrosoftTelemetryAssertTriggeredArgs("lsm.dll", LastError, 0);
      }
      WinlogonNotifyProvider::SubscriberNotificationStarted<unsigned short (&)[257],unsigned short const * const &>(
        *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 16 * v6 + 8) + 8LL * v8) + 34LL,
        &off_1400A2090[*(int *)(a1 + 48)]);
      v43 = CallNotificationSubscriber(
              *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 16 * v6 + 8) + 8LL * v8),
              (unsigned int)v6,
              v60,
              v66,
              v59);
      ResetHungSubscriberWarning((struct _NOTIFICATION_CLIENT_DEF *)a1);
      v29 = 60000 - *(_DWORD *)(a1 + 76);
      v55 = v29 + GetTickCount();
      WinlogonNotifyProvider::SubscriberNotificationComplete<unsigned short (&)[257],unsigned short const * const &,unsigned int &>(
        *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 16 * v6 + 8) + 8LL * v8) + 34LL,
        &off_1400A2090[*(int *)(a1 + 48)],
        &v55);
      v31 = v43;
      *(_DWORD *)(a1 + 72) = v43;
      if ( v31 )
      {
        v32 = v31 - 997;
        if ( !v32 )
        {
          WLEventWrite(
            v30,
            v6,
            *(const unsigned __int16 **)(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 16 * v6 + 8) + 8LL * v8),
            v66);
          if ( v66[0] )
            v57(0, v66);
          if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_SS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              87,
              (unsigned int)WPP_c4e026e548883477c15208e9f0c6fcb8_Traceguids,
              *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 16 * v6 + 8) + 8LL * v8),
              (__int64)v66);
          }
          v39 = 1;
          v44 = 1;
          goto LABEL_90;
        }
        v33 = v32 - 644;
        if ( v33 )
        {
          v34 = v33 - 61;
          if ( v34
            && (v35 = v34 - 15) != 0
            && (v36 = v35 - 5) != 0
            && (v37 = v36 - 4) != 0
            && (v38 = v37 - 1) != 0
            && v38 != 26 )
          {
            v45 = 0;
          }
          else
          {
            v45 = 0;
            if ( v52 )
            {
              if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_S(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  88,
                  WPP_c4e026e548883477c15208e9f0c6fcb8_Traceguids,
                  *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 16 * v6 + 8) + 8LL * v8));
              }
            }
            else
            {
              if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_S(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  89,
                  WPP_c4e026e548883477c15208e9f0c6fcb8_Traceguids,
                  *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 16 * v6 + 8) + 8LL * v8));
              }
              FreeRpcBinding(*(struct _NOTIFICATION_COMPONENT **)(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 16 * v6 + 8)
                                                                + 8LL * v8));
              v41 = ConnectToSubscriber(
                      (struct _NOTIFICATION_CLIENT_DEF *)a1,
                      *(struct _NOTIFICATION_COMPONENT **)(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 16 * v6 + 8) + 8LL * v8),
                      v48,
                      &v46,
                      &v45,
                      (struct _NOTIFICATION_COMPONENT **)(a1 + 64));
              v43 = v41;
              *(_DWORD *)(a1 + 72) = v41;
              if ( !v41 )
              {
                if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
                {
                  WPP_SF_S(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    90,
                    WPP_c4e026e548883477c15208e9f0c6fcb8_Traceguids,
                    *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 16 * v6 + 8) + 8LL * v8));
                }
                v44 = 1;
              }
              v52 = 1;
            }
          }
        }
        else if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_NotifyCreateSessionReturnValueFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_NotifyCreateSessionReturnValueFix>::GetImpl'::`2'::impl)
               && !(_DWORD)v6
               && !(unsigned int)_o__wcsicmp(
                                   *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 16 * v6 + 8) + 8LL * v8),
                                   L"TrustedInstaller") )
        {
          v54 = 1;
          v58 = 1;
        }
      }
      v39 = v44;
LABEL_90:
      if ( !v39 )
      {
        DWORD2(v65) = Timer::ElapsedULONG((Timer *)hKey);
        LODWORD(v65) = 1;
        WinSqmAddToStream(0, 6416, 3, &v63);
        WLEventWrite(
          &WLEvt_NotifySubscriber_Stop,
          v6,
          *(const unsigned __int16 **)(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 16 * v6 + 8) + 8LL * v8));
        if ( v43 )
        {
          NotifyReportEvent(
            2,
            v48 != 0 ? -2147477644 : -2147477647,
            4,
            &v43,
            1,
            *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 16 * v6 + 8) + 8LL * v8));
          FreeRpcBinding(*(struct _NOTIFICATION_COMPONENT **)(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 16 * v6 + 8) + 8LL * v8));
          if ( v48 && !v45 )
          {
            v40 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_SSl(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                91,
                (unsigned int)off_1400A2090,
                *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 16 * v6 + 8) + 8LL * v8),
                (__int64)off_1400A2090[v6],
                v43);
              v40 = WPP_GLOBAL_Control;
            }
            if ( !v46 || v46 == 1753 )
            {
              if ( v40 != (CUser *)&WPP_GLOBAL_Control && (*((_BYTE *)v40 + 28) & 1) != 0 && *((_BYTE *)v40 + 25) >= 4u )
                WPP_SF_DD(*((_QWORD *)v40 + 2), 92, WPP_c4e026e548883477c15208e9f0c6fcb8_Traceguids, v46);
              v46 = v43;
              *(_QWORD *)(a1 + 64) = *(_QWORD *)(a1 + 56);
            }
            goto LABEL_150;
          }
          if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_SSl(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              93,
              (unsigned int)off_1400A2090,
              *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 16 * v6 + 8) + 8LL * v8),
              (__int64)off_1400A2090[v6],
              v43);
          }
        }
LABEL_136:
        v8 = ++v53;
        v9 = v46;
        goto LABEL_26;
      }
    }
  }
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 94, WPP_c4e026e548883477c15208e9f0c6fcb8_Traceguids, v9);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_NotifyCreateSessionReturnValueFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_NotifyCreateSessionReturnValueFix>::GetImpl'::`2'::impl)
    && v54
    && v9 != 1753 )
  {
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 95, WPP_c4e026e548883477c15208e9f0c6fcb8_Traceguids);
    }
    v9 = 1641;
    v46 = 1641;
  }
  v43 = v9;
LABEL_150:
  WLEventWrite(&WLEvt_NotifyExecute_Stop, v6);
  return v43;
}

```

## disassembly

```asm
0x1400403d8  push    rbx
0x1400403da  push    rsi
0x1400403db  push    rdi
0x1400403dc  push    r12
0x1400403de  push    r13
0x1400403e0  push    r14
0x1400403e2  push    r15
0x1400403e4  sub     rsp, 300h
0x1400403eb  mov     rax, cs:__security_cookie
0x1400403f2  xor     rax, rsp
0x1400403f5  mov     [rsp+338h+var_48], rax
0x1400403fd  mov     [rsp+338h+var_2B8], r9
0x140040405  mov     [rsp+338h+var_2A0], r8
0x14004040d  movsxd  r13, edx
0x140040410  mov     rdi, rcx
0x140040413  mov     rax, [rsp+338h+arg_28]
0x14004041b  mov     [rsp+338h+var_2A8], rax
0x140040423  xor     r14d, r14d
0x140040426  mov     [rsp+338h+var_308], r14d
0x14004042b  mov     ebx, r14d
0x14004042e  mov     [rsp+338h+var_2FC], ebx
0x140040432  lea     r12d, [r14+1]
0x140040436  mov     [rsp+338h+var_300], r12d
0x14004043b  test    r13d, 0FFFFFFFDh
0x140040442  mov     eax, r14d
0x140040445  setz    al
0x140040448  mov     [rsp+338h+var_2F4], eax
0x14004044c  test    rcx, rcx
0x14004044f  jz      loc_140041161
0x140040455  cmp     dword ptr [rcx], 58h ; 'X'
0x140040458  jnz     loc_140041161
0x14004045e  cmp     r13d, [rcx+10h]
0x140040462  jnb     loc_140041161
0x140040468  mov     eax, r14d
0x14004046b  mov     [rsp+338h+var_2CC], eax
0x14004046f  lfence
0x140040472  mov     edx, r13d; unsigned int
0x140040475  lea     rcx, WLEvt_NotifyExecute_Start; struct _EVENT_DESCRIPTOR *
0x14004047c  call    ?WLEventWrite@@YAXAEBU_EVENT_DESCRIPTOR@@K@Z; WLEventWrite(_EVENT_DESCRIPTOR const &,ulong)
0x140040481  nop
0x140040482  mov     ecx, r13d
0x140040485  test    r13d, r13d
0x140040488  jz      short loc_140040498
0x14004048a  sub     ecx, 2
0x14004048d  jz      short loc_140040498
0x14004048f  cmp     ecx, r12d
0x140040492  jnz     loc_140040672
0x140040498  cmp     cs:dword_1400D3268, r14d
0x14004049f  jnz     loc_140040672
0x1400404a5  mov     [rsp+338h+hKey], r14
0x1400404aa  mov     esi, 11Ch
0x1400404af  mov     r8d, esi; Size
0x1400404b2  xor     edx, edx; Val
0x1400404b4  lea     rcx, [rsp+338h+VersionInformation]; void *
0x1400404bc  call    memset_0
0x1400404c1  mov     [rsp+338h+cbData], r14d
0x1400404c6  mov     dword ptr [rsp+338h+Data], r14d
0x1400404cb  mov     [rsp+338h+Type], r14d
0x1400404d0  mov     cs:dword_1400D3268, 40h ; '@'
0x1400404da  mov     [rsp+338h+VersionInformation.dwOSVersionInfoSize], esi
0x1400404e1  lea     rcx, [rsp+338h+VersionInformation]; lpVersionInformation
0x1400404e9  call    cs:__imp_GetVersionExW
0x1400404ef  test    eax, eax
0x1400404f1  jz      short loc_14004050A
0x1400404f3  cmp     [rsp+338h+var_17E], r12b
0x1400404fb  jnz     short loc_14004050A
0x1400404fd  mov     esi, 10h
0x140040502  mov     cs:dword_1400D3268, esi
0x140040508  jmp     short loc_14004050F
0x14004050a  mov     esi, 10h
0x14004050f  lea     rax, [rsp+338h+hKey]
0x140040514  mov     [rsp+338h+phkResult], rax; phkResult
0x140040519  mov     r9d, r12d; samDesired
0x14004051c  xor     r8d, r8d; ulOptions
0x14004051f  lea     rdx, aSoftwareMicros_48; "Software\\Microsoft\\Windows NT\\Curren"...
0x140040526  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14004052d  call    cs:__imp_RegOpenKeyExW
0x140040533  test    eax, eax
0x140040535  jnz     loc_1400405DF
0x14004053b  mov     [rsp+338h+cbData], 4
0x140040543  lea     rax, [rsp+338h+cbData]
0x140040548  mov     [rsp+338h+lpcbData], rax; lpcbData
0x14004054d  lea     rax, [rsp+338h+Data]
0x140040552  mov     [rsp+338h+phkResult], rax; lpData
0x140040557  lea     r9, [rsp+338h+Type]; lpType
0x14004055c  xor     r8d, r8d; lpReserved
0x14004055f  lea     rdx, aUiverbositylev; "UIVerbosityLevel"
0x140040566  mov     rcx, [rsp+338h+hKey]; hKey
0x14004056b  call    cs:__imp_RegQueryValueExW
0x140040571  test    eax, eax
0x140040573  jnz     short loc_1400405C4
0x140040575  lea     r15, WPP_GLOBAL_Control
0x14004057c  mov     rcx, cs:WPP_GLOBAL_Control
0x140040583  cmp     rcx, r15
0x140040586  jz      short loc_1400405B1
0x140040588  test    [rcx+1Ch], r12b
0x14004058c  jz      short loc_1400405B1
0x14004058e  cmp     byte ptr [rcx+19h], 4
0x140040592  jb      short loc_1400405B1
0x140040594  lea     edx, [rax+4Fh]
0x140040597  mov     r9d, dword ptr [rsp+338h+Data]
0x14004059c  lea     r12, WPP_c4e026e548883477c15208e9f0c6fcb8_Traceguids
0x1400405a3  mov     r8, r12
0x1400405a6  mov     rcx, [rcx+10h]
0x1400405aa  call    WPP_SF_d
0x1400405af  jmp     short loc_1400405B8
0x1400405b1  lea     r12, WPP_c4e026e548883477c15208e9f0c6fcb8_Traceguids
0x1400405b8  mov     eax, dword ptr [rsp+338h+Data]
0x1400405bc  mov     cs:dword_1400D3268, eax
0x1400405c2  jmp     short loc_1400405D2
0x1400405c4  lea     r15, WPP_GLOBAL_Control
0x1400405cb  lea     r12, WPP_c4e026e548883477c15208e9f0c6fcb8_Traceguids
0x1400405d2  mov     rcx, [rsp+338h+hKey]; hKey
0x1400405d7  call    cs:__imp_RegCloseKey
0x1400405dd  jmp     short loc_1400405ED
0x1400405df  lea     r15, WPP_GLOBAL_Control
0x1400405e6  lea     r12, WPP_c4e026e548883477c15208e9f0c6fcb8_Traceguids
0x1400405ed  lea     rax, [rsp+338h+hKey]
0x1400405f2  mov     [rsp+338h+phkResult], rax; phkResult
0x1400405f7  mov     r9d, 1; samDesired
0x1400405fd  xor     r8d, r8d; ulOptions
0x140040600  lea     rdx, aSoftwareMicros_10; "Software\\Microsoft\\Windows\\CurrentVe"...
0x140040607  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14004060e  call    cs:__imp_RegOpenKeyExW
0x140040614  test    eax, eax
0x140040616  jnz     short loc_140040680
0x140040618  mov     [rsp+338h+cbData], 4
0x140040620  lea     rax, [rsp+338h+cbData]
0x140040625  mov     [rsp+338h+lpcbData], rax; lpcbData
0x14004062a  lea     rax, [rsp+338h+Data]
0x14004062f  mov     [rsp+338h+phkResult], rax; lpData
0x140040634  lea     r9, [rsp+338h+Type]; lpType
0x140040639  xor     r8d, r8d; lpReserved
0x14004063c  lea     rdx, aVerbosestatus; "VerboseStatus"
0x140040643  mov     rcx, [rsp+338h+hKey]; hKey
0x140040648  call    cs:__imp_RegQueryValueExW
0x14004064e  test    eax, eax
0x140040650  jnz     short loc_140040665
0x140040652  cmp     dword ptr [rsp+338h+Data], r14d
0x140040657  mov     eax, 40h ; '@'
0x14004065c  cmovnz  esi, eax
0x14004065f  mov     cs:dword_1400D3268, esi
0x140040665  mov     rcx, [rsp+338h+hKey]; hKey
0x14004066a  call    cs:__imp_RegCloseKey
0x140040670  jmp     short loc_140040680
0x140040672  lea     r15, WPP_GLOBAL_Control
0x140040679  lea     r12, WPP_c4e026e548883477c15208e9f0c6fcb8_Traceguids
0x140040680  mov     [rdi+30h], r13d
0x140040684  mov     [rdi+38h], r14
0x140040688  mov     [rdi+40h], r14
0x14004068c  mov     dword ptr [rdi+48h], 0FFFFFFFFh
0x140040693  mov     [rsp+338h+var_2D0], r14d
0x140040698  mov     rsi, r13
0x14004069b  add     rsi, rsi
0x14004069e  mov     rax, [rdi+18h]
0x1400406a2  cmp     r14d, [rax+rsi*8]
0x1400406a6  jnb     loc_1400410CA
0x1400406ac  xorps   xmm0, xmm0
0x1400406af  movups  [rsp+338h+var_178], xmm0
0x1400406b7  movups  [rsp+338h+var_168], xmm0
0x1400406bf  movups  [rsp+338h+var_158], xmm0
0x1400406c7  lea     rcx, [rsp+338h+hKey]; this
0x1400406cc  call    ??0Timer@@QEAA@H@Z; Timer::Timer(int)
0x1400406d1  mov     dword ptr [rsp+338h+var_178+8], r13d
0x1400406d9  mov     dword ptr [rsp+338h+var_178], 1
0x1400406e4  mov     r8, [rdi+18h]
0x1400406e8  mov     r14d, r14d
0x1400406eb  mov     rax, [r8+rsi*8+8]
0x1400406f0  mov     rcx, [rax+r14*8]
0x1400406f4  xor     eax, eax
0x1400406f6  test    rcx, rcx
0x1400406f9  jz      short loc_140040700
0x1400406fb  cmp     [rcx], ax
0x1400406fe  jnz     short loc_140040707
0x140040700  lea     rcx, aNull_0; "(null)"
0x140040707  mov     qword ptr [rsp+338h+var_168+8], rcx
0x14004070f  mov     ebx, 2
0x140040714  mov     dword ptr [rsp+338h+var_168], ebx
0x14004071b  mov     r8, [r8+rsi*8+8]
0x140040720  mov     r8, [r8+r14*8]; unsigned __int16 *
0x140040724  mov     edx, r13d; unsigned int
0x140040727  lea     rcx, WLEvt_NotifySubscriber_Start; struct _EVENT_DESCRIPTOR *
0x14004072e  call    ?WLEventWrite@@YAXAEBU_EVENT_DESCRIPTOR@@KPEBG@Z; WLEventWrite(_EVENT_DESCRIPTOR const &,ulong,ushort const *)
0x140040733  mov     rdx, [rdi+18h]
0x140040737  mov     rax, [rdx+rsi*8+8]
0x14004073c  mov     rcx, [rax+r14*8]
0x140040740  mov     [rdi+38h], rcx
0x140040744  mov     dword ptr [rdi+48h], 0FFFFFFFFh
0x14004074b  mov     rdx, [rdx+rsi*8+8]
0x140040750  mov     rdx, [rdx+r14*8]; struct _NOTIFICATION_COMPONENT *
0x140040754  mov     rcx, rdi; struct _NOTIFICATION_CLIENT_DEF *
0x140040757  call    ?GetSubscriberDisplayName@@YAXPEAU_NOTIFICATION_CLIENT_DEF@@PEAU_NOTIFICATION_COMPONENT@@@Z; GetSubscriberDisplayName(_NOTIFICATION_CLIENT_DEF *,_NOTIFICATION_COMPONENT *)
0x14004075c  cmp     [rsp+338h+var_2B8], 0
0x140040765  jz      short loc_1400407A1
0x140040767  cmp     cs:dword_1400D3268, 20h ; ' '
0x14004076e  jb      short loc_1400407A1
0x140040770  mov     rax, [rdi+18h]
0x140040774  mov     rdx, [rax+rsi*8+8]
0x140040779  lea     r8, [rsp+338h+var_148]; unsigned __int16 *
0x140040781  mov     rdx, [rdx+r14*8]; struct _NOTIFICATION_COMPONENT *
0x140040785  call    ?ConstructInitialMessageForSubscriber@@YAXPEAU_NOTIFICATION_CLIENT_DEF@@PEAU_NOTIFICATION_COMPONENT@@PEAGK@Z; ConstructInitialMessageForSubscriber(_NOTIFICATION_CLIENT_DEF *,_NOTIFICATION_COMPONENT *,ushort *,ulong)
0x14004078a  lea     rdx, [rsp+338h+var_148]
0x140040792  xor     ecx, ecx
0x140040794  mov     rax, [rsp+338h+var_2B8]
0x14004079c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400407a1  mov     rax, [rdi+18h]
0x1400407a5  mov     rdx, [rax+rsi*8+8]
0x1400407aa  lea     rcx, [rdi+40h]
0x1400407ae  mov     [rsp+338h+lpcbData], rcx; struct _NOTIFICATION_COMPONENT **
0x1400407b3  lea     rax, [rsp+338h+var_300]
0x1400407b8  mov     [rsp+338h+phkResult], rax; int *
0x1400407bd  lea     r9, [rsp+338h+var_2FC]; unsigned int *
0x1400407c2  mov     r8d, [rsp+338h+var_2F4]; int
0x1400407c7  mov     rdx, [rdx+r14*8]; struct _NOTIFICATION_COMPONENT *
0x1400407cb  mov     rcx, rdi; struct _NOTIFICATION_CLIENT_DEF *
0x1400407ce  call    ?ConnectToSubscriber@@YAKPEAU_NOTIFICATION_CLIENT_DEF@@PEAU_NOTIFICATION_COMPONENT@@HPEAKPEAHPEAPEAU2@@Z; ConnectToSubscriber(_NOTIFICATION_CLIENT_DEF *,_NOTIFICATION_COMPONENT *,int,ulong *,int *,_NOTIFICATION_COMPONENT * *)
0x1400407d3  mov     [rsp+338h+var_308], eax
0x1400407d7  mov     [rdi+48h], eax
0x1400407da  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WinlogonNotifySubscriberRefactor@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WinlogonNotifySubscriberRefactor@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WinlogonNotifySubscriberRefactor> `wil::Feature<__WilFeatureTraits_Feature_WinlogonNotifySubscriberRefactor>::GetImpl(void)'::`2'::impl
0x1400407e1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WinlogonNotifySubscriberRefactor@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WinlogonNotifySubscriberRefactor>::__private_IsEnabled(void)
0x1400407e6  test    al, al
0x1400407e8  jz      loc_140040A9E
0x1400407ee  mov     ecx, [rsp+338h+var_308]
0x1400407f2  test    ecx, ecx
0x1400407f4  jz      loc_1400408CF
0x1400407fa  lea     eax, [rcx-6A6h]
0x140040800  cmp     eax, 33h ; '3'
0x140040803  ja      short loc_140040819
0x140040805  mov     rdx, 8000003108001h
0x14004080f  bt      rdx, rax
0x140040813  jb      loc_1400408CB
0x140040819  mov     rax, [rdi+18h]
0x14004081d  mov     r8, [rax+rsi*8+8]
0x140040822  mov     r8, [r8+r14*8]
0x140040826  mov     edx, r13d
0x140040829  call    ?LogConnectToSubscriberFailure@@YAXKW4WLNOTIFICATION_ID@@PEAG@Z; LogConnectToSubscriberFailure(ulong,WLNOTIFICATION_ID,ushort *)
0x14004082e  lea     rcx, [rsp+338h+hKey]; this
0x140040833  call    ?Stop@Timer@@QEAA_KXZ; Timer::Stop(void)
0x140040838  lea     rcx, [rsp+338h+hKey]; this
0x14004083d  call    ?ElapsedULONG@Timer@@QEAAKXZ; Timer::ElapsedULONG(void)
0x140040842  mov     dword ptr [rsp+338h+var_158+8], eax
0x140040849  mov     dword ptr [rsp+338h+var_158], 1
0x140040854  lea     r9, [rsp+338h+var_178]
0x14004085c  mov     edx, 1910h
0x140040861  xor     ecx, ecx
0x140040863  lea     r8d, [rcx+3]
0x140040867  call    cs:__imp_WinSqmAddToStream
0x14004086d  mov     r9, [rdi+18h]
0x140040871  mov     rax, [r9+rsi*8+8]
0x140040876  mov     rcx, [rax+r14*8]
0x14004087a  mov     [rdi+40h], rcx
0x14004087e  xor     eax, eax
0x140040880  cmp     [rsp+338h+var_300], eax
0x140040884  jnz     short loc_1400408C6
0x140040886  mov     rcx, cs:WPP_GLOBAL_Control
0x14004088d  cmp     rcx, r15
0x140040890  jz      loc_14004114C
0x140040896  test    byte ptr [rcx+1Ch], 1
0x14004089a  jz      loc_14004114C
0x1400408a0  cmp     [rcx+19h], bl
0x1400408a3  jb      loc_14004114C
0x1400408a9  lea     edx, [rax+50h]
0x1400408ac  mov     r9, [r9+rsi*8+8]
0x1400408b1  mov     r9, [r9+r14*8]
0x1400408b5  mov     r8, r12
0x1400408b8  mov     rcx, [rcx+10h]
0x1400408bc  call    WPP_SF_S
0x1400408c1  jmp     loc_14004114C
0x1400408c6  jmp     loc_1400410B4
0x1400408cb  test    ecx, ecx
0x1400408cd  jnz     short loc_1400408FD
0x1400408cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400408d6  cmp     rcx, r15
0x1400408d9  jz      loc_1400409B8
0x1400408df  test    byte ptr [rcx+1Ch], 1
0x1400408e3  jz      loc_1400409B8
0x1400408e9  cmp     byte ptr [rcx+19h], 4
0x1400408ed  jb      loc_1400409B8
0x1400408f3  mov     edx, 51h ; 'Q'
0x1400408f8  jmp     loc_14004099F
0x1400408fd  mov     rcx, cs:WPP_GLOBAL_Control
0x140040904  cmp     rcx, r15
0x140040907  jz      short loc_140040932
0x140040909  test    byte ptr [rcx+1Ch], 1
0x14004090d  jz      short loc_140040932
0x14004090f  cmp     [rcx+19h], bl
0x140040912  jb      short loc_140040932
0x140040914  mov     rax, [rdi+18h]
0x140040918  mov     r9, [rax+rsi*8+8]
0x14004091d  mov     edx, 52h ; 'R'
0x140040922  mov     r9, [r9+r14*8]
0x140040926  mov     r8, r12
0x140040929  mov     rcx, [rcx+10h]
0x14004092d  call    WPP_SF_S
0x140040932  mov     rax, [rdi+18h]
0x140040936  mov     rcx, [rax+rsi*8+8]
0x14004093b  mov     rcx, [rcx+r14*8]; struct _NOTIFICATION_COMPONENT *
0x14004093f  call    ?FreeRpcBinding@@YAXPEAU_NOTIFICATION_COMPONENT@@@Z; FreeRpcBinding(_NOTIFICATION_COMPONENT *)
0x140040944  mov     rax, [rdi+18h]
0x140040948  mov     rdx, [rax+rsi*8+8]
  ... truncated ...
```
