# SystemMonitoringThreadProc(void *)

- ea: `0x180002fc0`
- end: `0x1800034db`
- name: `?SystemMonitoringThreadProc@@YAKPEAX@Z`
- size: `1307`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002e30`
- `0x180002fc0`
- `0x1800037ac`
- `0x180003920`
- `0x180008e48`
- `0x1800202e8`
- `0x180022cb0`
- `0x1800284b8`
- `0x18003b824`
- `0x18003fc30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800030a5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180003110`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800030a5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180003110`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180003261`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180003261`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800030b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000311e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800031d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000326c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800030b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000311e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800031d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000326c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800031f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003487`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800034ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800031f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003487`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800034ac`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003189`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003189`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003496`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003496`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1800031a5`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180003343`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18000342e`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1800031a5`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180003343`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18000342e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000331a`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000331a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180003079`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800032f7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180003079`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800032f7`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180002feb`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180002feb`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800034b2`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800034b2`
- `USERENV!UnregisterGPNotification` at `0x18000347e`
- `USERENV!UnregisterGPNotification` at `0x18000347e`
- `USERENV!RegisterGPNotification` at `0x1800031ca`
- `USERENV!RegisterGPNotification` at `0x1800031ca`

## pseudocode

```c
__int64 __fastcall SystemMonitoringThreadProc(PVOID Parameter)
{
  HRESULT v1; // eax
  signed int v2; // ebx
  HANDLE v3; // r12
  HANDLE EventW; // r13
  signed int v5; // eax
  signed int LastError; // eax
  int v7; // edi
  signed int v8; // eax
  unsigned int v9; // edi
  DWORD v10; // eax
  unsigned __int16 *v11; // rdx
  struct CWmiEventManagerAvFw *v12; // rcx
  DWORD v13; // eax
  DWORD v14; // eax
  DWORD v15; // eax
  const unsigned __int16 *v16; // rdx
  _FILETIME v17; // rax
  HKEY v18; // rcx
  int v19; // eax
  int v20; // edi
  int v21; // eax
  int StatusRegistryOnly; // [rsp+30h] [rbp-39h]
  HKEY hKey; // [rsp+38h] [rbp-31h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp-29h] BYREF
  struct _FILETIME v26; // [rsp+48h] [rbp-21h] BYREF
  HANDLE Handles[4]; // [rsp+50h] [rbp-19h] BYREF

  v1 = CoInitializeEx(0, 0);
  v2 = v1;
  if ( v1 < 0 )
  {
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        WPP_c81c3ae13a39328400a46a9fe4e4d5f2_Traceguids,
        (unsigned int)v1);
    }
    return (unsigned __int16)v2;
  }
  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_c81c3ae13a39328400a46a9fe4e4d5f2_Traceguids);
  hKey = 0;
  v3 = 0;
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  if ( g_hEventSessionLogonEvent )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    if ( EventW )
    {
      v3 = CreateEventW(0, 0, 0, 0);
      if ( v3 )
      {
        if ( !RegOpenKeyExW(
                HKEY_LOCAL_MACHINE,
                L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System",
                0,
                0x11u,
                &hKey) )
          RegNotifyChangeKeyValue(hKey, 0, 4u, EventW, 1);
      }
      else
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          v2 = (unsigned __int16)LastError | 0x80070000;
        else
          v2 = LastError;
        if ( v2 >= 0 )
          v2 = -2147467259;
        if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            14,
            WPP_c81c3ae13a39328400a46a9fe4e4d5f2_Traceguids,
            (unsigned int)LastError);
        }
      }
    }
    else
    {
      v5 = GetLastError();
      if ( v5 > 0 )
        v2 = (unsigned __int16)v5 | 0x80070000;
      else
        v2 = v5;
      if ( v2 >= 0 )
        v2 = -2147467259;
      if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          WPP_c81c3ae13a39328400a46a9fe4e4d5f2_Traceguids,
          (unsigned int)v5);
      }
    }
  }
  else
  {
    EventW = 0;
    v2 = -2147483638;
  }
  StatusRegistryOnly = CLuaSettingsChecktoid::GetStatusRegistryOnly(L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System");
  v7 = StatusRegistryOnly;
  if ( v2 >= 0 )
  {
    if ( !RegisterGPNotification(v3, 1) )
    {
      v8 = GetLastError();
      v9 = v8;
      if ( v8 > 0 )
        v2 = (unsigned __int16)v8 | 0x80070000;
      else
        v2 = v8;
      CloseHandle(v3);
      v3 = 0;
      if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_c81c3ae13a39328400a46a9fe4e4d5f2_Traceguids, v9);
      }
      v7 = StatusRegistryOnly;
    }
    if ( v2 >= 0 )
    {
      Handles[0] = g_hShutdownThreadNotify;
      Handles[1] = g_hEventSessionLogonEvent;
      Handles[2] = v3;
      Handles[3] = EventW;
      while ( 1 )
      {
        while ( 1 )
        {
          if ( !g_bRunning )
            goto LABEL_81;
          v10 = WaitForMultipleObjectsEx(4u, Handles, 0, 0xFFFFFFFF, 1);
          if ( v10 == -1 )
          {
            v13 = GetLastError();
            v12 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_c81c3ae13a39328400a46a9fe4e4d5f2_Traceguids, v13);
            }
            goto LABEL_72;
          }
          if ( v10 )
            break;
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_c81c3ae13a39328400a46a9fe4e4d5f2_Traceguids);
          }
LABEL_72:
          v20 = 0;
          if ( !hKey && CUtil::ReCreateRegistryNotifyKey((HKEY)v12, v11, &hKey) >= 0 )
          {
            RegNotifyChangeKeyValue(hKey, 0, 4u, EventW, 1);
            v21 = CLuaSettingsChecktoid::GetStatusRegistryOnly(L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System");
            if ( v21 != StatusRegistryOnly )
            {
              StatusRegistryOnly = v21;
              v20 = 1;
            }
          }
          if ( (unsigned int)PollForChanges() || v20 )
            CAlertStatus::FireNotificationEvents(g_pAlertStatus, 0);
          v7 = StatusRegistryOnly;
        }
        v14 = v10 - 1;
        if ( !v14 )
        {
          if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_c81c3ae13a39328400a46a9fe4e4d5f2_Traceguids);
          }
          if ( (unsigned int)PollForChanges() )
            CAlertStatus::FireNotificationEvents(g_pAlertStatus, 0);
          goto LABEL_72;
        }
        v15 = v14 - 1;
        if ( !v15 )
        {
          if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_c81c3ae13a39328400a46a9fe4e4d5f2_Traceguids);
          }
          if ( (unsigned int)WscDSA_FeatureIsEnabled() )
            WscDSA_ChangeDefaultByPolicy(v12, (struct CThirdPartyManager *)v11);
          goto LABEL_72;
        }
        if ( v15 != 1 )
          goto LABEL_72;
        if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_c81c3ae13a39328400a46a9fe4e4d5f2_Traceguids);
        }
        v26 = 0;
        GetSystemTimeAsFileTime(&v26);
        v17 = SystemTimeAsFileTime;
        SystemTimeAsFileTime = v26;
        v18 = (HKEY)(*(_QWORD *)&v26 - *(_QWORD *)&v17);
        if ( *(_QWORD *)&v26 - *(_QWORD *)&v17 < 0x989680u )
          Sleep(0x7D0u);
        if ( CUtil::ReCreateRegistryNotifyKey(v18, v16, &hKey) >= 0 )
        {
          RegNotifyChangeKeyValue(hKey, 0, 4u, EventW, 1);
          v19 = CLuaSettingsChecktoid::GetStatusRegistryOnly(L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System");
          if ( v19 != v7 )
          {
            v7 = v19;
            StatusRegistryOnly = v19;
            CAlertStatus::FireNotificationEvents(g_pAlertStatus, 0);
          }
        }
      }
    }
  }
LABEL_81:
  if ( v3 )
  {
    UnregisterGPNotification(v3);
    CloseHandle(v3);
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( EventW )
    CloseHandle(EventW);
  CoUninitialize();
  return (unsigned __int16)v2;
}

```

## disassembly

```asm
0x180002fc0  push    rbp
0x180002fc2  push    rbx
0x180002fc3  push    rsi
0x180002fc4  push    rdi
0x180002fc5  push    r12
0x180002fc7  push    r13
0x180002fc9  push    r14
0x180002fcb  push    r15
0x180002fcd  lea     rbp, [rsp-1Fh]
0x180002fd2  sub     rsp, 88h
0x180002fd9  mov     rax, cs:__security_cookie
0x180002fe0  xor     rax, rsp
0x180002fe3  mov     [rbp+57h+var_50], rax
0x180002fe7  xor     edx, edx; dwCoInit
0x180002fe9  xor     ecx, ecx; pvReserved
0x180002feb  call    cs:__imp_CoInitializeEx
0x180002ff1  xor     edi, edi
0x180002ff3  mov     ebx, eax
0x180002ff5  test    eax, eax
0x180002ff7  jns     short loc_180003039
0x180002ff9  mov     rcx, cs:WPP_GLOBAL_Control
0x180003000  lea     rsi, WPP_GLOBAL_Control
0x180003007  cmp     rcx, rsi
0x18000300a  jz      loc_1800034B8
0x180003010  lea     r14d, [rdi+1]
0x180003014  test    [rcx+1Ch], r14b
0x180003018  jz      loc_1800034B8
0x18000301e  mov     rcx, [rcx+10h]
0x180003022  lea     edx, [rdi+0Bh]
0x180003025  mov     r9d, eax
0x180003028  lea     r8, WPP_c81c3ae13a39328400a46a9fe4e4d5f2_Traceguids
0x18000302f  call    WPP_SF_d
0x180003034  jmp     loc_1800034B8
0x180003039  mov     rcx, cs:WPP_GLOBAL_Control
0x180003040  lea     rsi, WPP_GLOBAL_Control
0x180003047  lea     r15, WPP_c81c3ae13a39328400a46a9fe4e4d5f2_Traceguids
0x18000304e  cmp     rcx, rsi
0x180003051  jz      short loc_18000306A
0x180003053  test    byte ptr [rcx+1Ch], 8
0x180003057  jz      short loc_18000306A
0x180003059  mov     rcx, [rcx+10h]
0x18000305d  mov     edx, 0Ch
0x180003062  mov     r8, r15
0x180003065  call    WPP_SF_
0x18000306a  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000306e  mov     [rbp+57h+hKey], rdi
0x180003072  mov     r12, rdi
0x180003075  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], rdi
0x180003079  call    cs:__imp_GetSystemTimeAsFileTime
0x18000307f  cmp     cs:?g_hEventSessionLogonEvent@@3PEAXEA, rdi; void * g_hEventSessionLogonEvent
0x180003086  mov     r14d, 1
0x18000308c  jnz     short loc_18000309B
0x18000308e  mov     r13, rdi
0x180003091  mov     ebx, 8000000Ah
0x180003096  jmp     loc_1800031AB
0x18000309b  xor     r9d, r9d; lpName
0x18000309e  xor     r8d, r8d; bInitialState
0x1800030a1  xor     edx, edx; bManualReset
0x1800030a3  xor     ecx, ecx; lpEventAttributes
0x1800030a5  call    cs:__imp_CreateEventW
0x1800030ab  mov     r13, rax
0x1800030ae  test    rax, rax
0x1800030b1  jnz     short loc_180003106
0x1800030b3  call    cs:__imp_GetLastError
0x1800030b9  test    eax, eax
0x1800030bb  jg      short loc_1800030C1
0x1800030bd  mov     ebx, eax
0x1800030bf  jmp     short loc_1800030CA
0x1800030c1  movzx   ebx, ax
0x1800030c4  or      ebx, 80070000h
0x1800030ca  test    ebx, ebx
0x1800030cc  mov     ecx, 80004005h
0x1800030d1  cmovns  ebx, ecx
0x1800030d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800030db  cmp     rcx, rsi
0x1800030de  jz      loc_1800031AB
0x1800030e4  test    [rcx+1Ch], r14b
0x1800030e8  jz      short loc_1800030FE
0x1800030ea  mov     rcx, [rcx+10h]
0x1800030ee  mov     edx, 0Dh
0x1800030f3  mov     r9d, eax
0x1800030f6  mov     r8, r15
0x1800030f9  call    WPP_SF_d
0x1800030fe  test    ebx, ebx
0x180003100  js      loc_1800031AB
0x180003106  xor     r9d, r9d; lpName
0x180003109  xor     r8d, r8d; bInitialState
0x18000310c  xor     edx, edx; bManualReset
0x18000310e  xor     ecx, ecx; lpEventAttributes
0x180003110  call    cs:__imp_CreateEventW
0x180003116  mov     r12, rax
0x180003119  test    rax, rax
0x18000311c  jnz     short loc_180003169
0x18000311e  call    cs:__imp_GetLastError
0x180003124  test    eax, eax
0x180003126  jg      short loc_18000312C
0x180003128  mov     ebx, eax
0x18000312a  jmp     short loc_180003135
0x18000312c  movzx   ebx, ax
0x18000312f  or      ebx, 80070000h
0x180003135  test    ebx, ebx
0x180003137  mov     ecx, 80004005h
0x18000313c  cmovns  ebx, ecx
0x18000313f  mov     rcx, cs:WPP_GLOBAL_Control
0x180003146  cmp     rcx, rsi
0x180003149  jz      short loc_1800031AB
0x18000314b  test    [rcx+1Ch], r14b
0x18000314f  jz      short loc_180003165
0x180003151  mov     rcx, [rcx+10h]
0x180003155  mov     edx, 0Eh
0x18000315a  mov     r9d, eax
0x18000315d  mov     r8, r15
0x180003160  call    WPP_SF_d
0x180003165  test    ebx, ebx
0x180003167  js      short loc_1800031AB
0x180003169  lea     rax, [rbp+57h+hKey]
0x18000316d  mov     r9d, 11h; samDesired
0x180003173  xor     r8d, r8d; ulOptions
0x180003176  mov     [rsp+0C0h+phkResult], rax; phkResult
0x18000317b  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180003182  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180003189  call    cs:__imp_RegOpenKeyExW
0x18000318f  test    eax, eax
0x180003191  jnz     short loc_1800031AB
0x180003193  mov     rcx, [rbp+57h+hKey]; hKey
0x180003197  lea     r8d, [rax+4]; dwNotifyFilter
0x18000319b  mov     r9, r13; hEvent
0x18000319e  mov     dword ptr [rsp+0C0h+phkResult], r14d; fAsynchronous
0x1800031a3  xor     edx, edx; bWatchSubtree
0x1800031a5  call    cs:__imp_RegNotifyChangeKeyValue
0x1800031ab  lea     rcx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800031b2  call    ?GetStatusRegistryOnly@CLuaSettingsChecktoid@@SAKPEBG@Z; CLuaSettingsChecktoid::GetStatusRegistryOnly(ushort const *)
0x1800031b7  mov     [rbp+57h+var_90], eax
0x1800031ba  mov     edi, eax
0x1800031bc  test    ebx, ebx
0x1800031be  js      loc_180003476
0x1800031c4  mov     edx, r14d; bMachine
0x1800031c7  mov     rcx, r12; hEvent
0x1800031ca  call    cs:__imp_RegisterGPNotification
0x1800031d0  test    eax, eax
0x1800031d2  jnz     short loc_180003222
0x1800031d4  call    cs:__imp_GetLastError
0x1800031da  mov     edi, eax
0x1800031dc  test    eax, eax
0x1800031de  jg      short loc_1800031E4
0x1800031e0  mov     ebx, eax
0x1800031e2  jmp     short loc_1800031ED
0x1800031e4  movzx   ebx, di
0x1800031e7  or      ebx, 80070000h
0x1800031ed  mov     rcx, r12; hObject
0x1800031f0  call    cs:__imp_CloseHandle
0x1800031f6  xor     r12d, r12d
0x1800031f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180003200  cmp     rcx, rsi
0x180003203  jz      short loc_18000321F
0x180003205  test    [rcx+1Ch], r14b
0x180003209  jz      short loc_18000321F
0x18000320b  mov     rcx, [rcx+10h]
0x18000320f  lea     edx, [r12+0Fh]
0x180003214  mov     r9d, edi
0x180003217  mov     r8, r15
0x18000321a  call    WPP_SF_d
0x18000321f  mov     edi, [rbp+57h+var_90]
0x180003222  test    ebx, ebx
0x180003224  js      loc_180003476
0x18000322a  mov     rax, cs:?g_hShutdownThreadNotify@@3PEAXEA; void * g_hShutdownThreadNotify
0x180003231  mov     [rbp+57h+Handles], rax
0x180003235  mov     rax, cs:?g_hEventSessionLogonEvent@@3PEAXEA; void * g_hEventSessionLogonEvent
0x18000323c  mov     [rbp+57h+var_68], rax
0x180003240  mov     [rbp+57h+var_60], r12
0x180003244  mov     [rbp+57h+var_58], r13
0x180003248  jmp     loc_180003469
0x18000324d  xor     r8d, r8d; bWaitAll
0x180003250  mov     dword ptr [rsp+0C0h+phkResult], r14d; bAlertable
0x180003255  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180003259  lea     rdx, [rbp+57h+Handles]; lpHandles
0x18000325d  lea     ecx, [r8+4]; nCount
0x180003261  call    cs:__imp_WaitForMultipleObjectsEx
0x180003267  cmp     eax, 0FFFFFFFFh
0x18000326a  jnz     short loc_1800032A5
0x18000326c  call    cs:__imp_GetLastError
0x180003272  mov     rcx, cs:WPP_GLOBAL_Control
0x180003279  cmp     rcx, rsi
0x18000327c  jz      loc_180003407
0x180003282  test    [rcx+1Ch], r14b
0x180003286  jz      loc_180003407
0x18000328c  mov     rcx, [rcx+10h]
0x180003290  mov     edx, 10h
0x180003295  mov     r9d, eax
0x180003298  mov     r8, r15
0x18000329b  call    WPP_SF_d
0x1800032a0  jmp     loc_180003407
0x1800032a5  test    eax, eax
0x1800032a7  jz      loc_1800033E4
0x1800032ad  sub     eax, r14d
0x1800032b0  jz      loc_1800033A8
0x1800032b6  sub     eax, r14d
0x1800032b9  jz      loc_180003375
0x1800032bf  cmp     eax, r14d
0x1800032c2  jnz     loc_180003407
0x1800032c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800032cf  cmp     rcx, rsi
0x1800032d2  jz      short loc_1800032EB
0x1800032d4  test    byte ptr [rcx+1Ch], 4
0x1800032d8  jz      short loc_1800032EB
0x1800032da  mov     rcx, [rcx+10h]
0x1800032de  mov     edx, 14h
0x1800032e3  mov     r8, r15
0x1800032e6  call    WPP_SF_
0x1800032eb  lea     rcx, [rbp+57h+var_78]; lpSystemTimeAsFileTime
0x1800032ef  mov     qword ptr [rbp+57h+var_78.dwLowDateTime], 0
0x1800032f7  call    cs:__imp_GetSystemTimeAsFileTime
0x1800032fd  mov     rcx, qword ptr [rbp+57h+var_78.dwLowDateTime]
0x180003301  mov     rax, qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x180003305  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], rcx
0x180003309  sub     rcx, rax
0x18000330c  cmp     rcx, 989680h
0x180003313  jnb     short loc_180003320
0x180003315  mov     ecx, 7D0h; dwMilliseconds
0x18000331a  call    cs:__imp_Sleep
0x180003320  lea     r8, [rbp+57h+hKey]; HKEY *
0x180003324  call    ?ReCreateRegistryNotifyKey@CUtil@@SAJPEAUHKEY__@@PEBGPEAPEAU2@@Z; CUtil::ReCreateRegistryNotifyKey(HKEY__ *,ushort const *,HKEY__ * *)
0x180003329  test    eax, eax
0x18000332b  js      loc_180003469
0x180003331  mov     rcx, [rbp+57h+hKey]; hKey
0x180003335  xor     edx, edx; bWatchSubtree
0x180003337  mov     r9, r13; hEvent
0x18000333a  mov     dword ptr [rsp+0C0h+phkResult], r14d; fAsynchronous
0x18000333f  lea     r8d, [rdx+4]; dwNotifyFilter
0x180003343  call    cs:__imp_RegNotifyChangeKeyValue
0x180003349  lea     rcx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180003350  call    ?GetStatusRegistryOnly@CLuaSettingsChecktoid@@SAKPEBG@Z; CLuaSettingsChecktoid::GetStatusRegistryOnly(ushort const *)
0x180003355  cmp     eax, edi
0x180003357  jz      loc_180003469
0x18000335d  mov     rcx, cs:?g_pAlertStatus@@3PEAVCAlertStatus@@EA; lpCriticalSection
0x180003364  xor     edx, edx; int
0x180003366  mov     edi, eax
0x180003368  mov     [rbp+57h+var_90], eax
0x18000336b  call    ?FireNotificationEvents@CAlertStatus@@QEAAXH@Z; CAlertStatus::FireNotificationEvents(int)
0x180003370  jmp     loc_180003469
0x180003375  mov     rcx, cs:WPP_GLOBAL_Control
0x18000337c  cmp     rcx, rsi
0x18000337f  jz      short loc_180003398
0x180003381  test    byte ptr [rcx+1Ch], 4
0x180003385  jz      short loc_180003398
0x180003387  mov     rcx, [rcx+10h]
0x18000338b  mov     edx, 13h
0x180003390  mov     r8, r15
0x180003393  call    WPP_SF_
0x180003398  call    ?WscDSA_FeatureIsEnabled@@YAHXZ; WscDSA_FeatureIsEnabled(void)
0x18000339d  test    eax, eax
0x18000339f  jz      short loc_180003407
0x1800033a1  call    ?WscDSA_ChangeDefaultByPolicy@@YAJPEAVCWmiEventManagerAvFw@@PEAVCThirdPartyManager@@@Z; WscDSA_ChangeDefaultByPolicy(CWmiEventManagerAvFw *,CThirdPartyManager *)
0x1800033a6  jmp     short loc_180003407
0x1800033a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800033af  cmp     rcx, rsi
0x1800033b2  jz      short loc_1800033CB
0x1800033b4  test    byte ptr [rcx+1Ch], 4
0x1800033b8  jz      short loc_1800033CB
0x1800033ba  mov     rcx, [rcx+10h]
0x1800033be  mov     edx, 12h
0x1800033c3  mov     r8, r15
0x1800033c6  call    WPP_SF_
0x1800033cb  call    ?PollForChanges@@YAHXZ; PollForChanges(void)
0x1800033d0  test    eax, eax
0x1800033d2  jz      short loc_180003407
0x1800033d4  mov     rcx, cs:?g_pAlertStatus@@3PEAVCAlertStatus@@EA; lpCriticalSection
0x1800033db  xor     edx, edx; int
0x1800033dd  call    ?FireNotificationEvents@CAlertStatus@@QEAAXH@Z; CAlertStatus::FireNotificationEvents(int)
0x1800033e2  jmp     short loc_180003407
0x1800033e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800033eb  cmp     rcx, rsi
0x1800033ee  jz      short loc_180003407
0x1800033f0  test    byte ptr [rcx+1Ch], 4
0x1800033f4  jz      short loc_180003407
0x1800033f6  mov     rcx, [rcx+10h]
0x1800033fa  mov     edx, 11h
0x1800033ff  mov     r8, r15
0x180003402  call    WPP_SF_
0x180003407  xor     edi, edi
0x180003409  cmp     [rbp+57h+hKey], rdi
0x18000340d  jnz     short loc_18000344B
0x18000340f  lea     r8, [rbp+57h+hKey]; HKEY *
0x180003413  call    ?ReCreateRegistryNotifyKey@CUtil@@SAJPEAUHKEY__@@PEBGPEAPEAU2@@Z; CUtil::ReCreateRegistryNotifyKey(HKEY__ *,ushort const *,HKEY__ * *)
0x180003418  test    eax, eax
0x18000341a  js      short loc_18000344B
0x18000341c  mov     rcx, [rbp+57h+hKey]; hKey
0x180003420  lea     r8d, [rdi+4]; dwNotifyFilter
0x180003424  mov     r9, r13; hEvent
0x180003427  mov     dword ptr [rsp+0C0h+phkResult], r14d; fAsynchronous
0x18000342c  xor     edx, edx; bWatchSubtree
0x18000342e  call    cs:__imp_RegNotifyChangeKeyValue
0x180003434  lea     rcx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000343b  call    ?GetStatusRegistryOnly@CLuaSettingsChecktoid@@SAKPEBG@Z; CLuaSettingsChecktoid::GetStatusRegistryOnly(ushort const *)
0x180003440  cmp     eax, [rbp+57h+var_90]
0x180003443  jz      short loc_18000344B
0x180003445  mov     [rbp+57h+var_90], eax
0x180003448  mov     edi, r14d
0x18000344b  call    ?PollForChanges@@YAHXZ; PollForChanges(void)
0x180003450  test    eax, eax
  ... truncated ...
```
