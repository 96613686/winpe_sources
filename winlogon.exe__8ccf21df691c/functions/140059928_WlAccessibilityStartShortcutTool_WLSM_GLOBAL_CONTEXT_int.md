# WlAccessibilityStartShortcutTool(_WLSM_GLOBAL_CONTEXT *,int)

- ea: `0x140059928`
- end: `0x14005a066`
- name: `?WlAccessibilityStartShortcutTool@@YAKPEAU_WLSM_GLOBAL_CONTEXT@@H@Z`
- size: `1854`
- prototype: `__int64 __fastcall(struct _WLSM_GLOBAL_CONTEXT *, int)`
- caller_count: `3`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x140084890`
- `0x140084930`
- `0x1400849d0`

## callees

- `0x1400057f4`
- `0x140006fc0`
- `0x14000d4e0`
- `0x14002d410`
- `0x14003de48`
- `0x140041c34`
- `0x140053720`
- `0x1400544e0`
- `0x140058c7c`
- `0x140058f1c`
- `0x140059000`
- `0x1400590a0`
- `0x140059190`
- `0x1400594a4`
- `0x140059684`
- `0x140059928`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140059d82`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140059d82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140059bc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140059d36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140059d98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140059bc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140059d36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140059d98`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x140059bb9`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x140059bb9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140059d8d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140059e22`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140059e39`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14009eb7c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14009eb8f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140059d8d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140059e22`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140059e39`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14009eb7c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14009eb8f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140059a49`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140059a49`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140059a7b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140059a7b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140059a86`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140059a86`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x140059d28`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x140059d28`
- `ntdll!NtClose` at `0x140059a91`
- `ntdll!NtClose` at `0x140059a91`
- `ntdll!RtlOpenCurrentUser` at `0x140059a03`
- `ntdll!RtlOpenCurrentUser` at `0x140059a03`

## string_xrefs

- `0x140059a3d`: `Control Panel\Accessibility`
- `0x140059aad`: `Control Panel\Accessibility`

## pseudocode

```c
__int64 __fastcall WlAccessibilityStartShortcutTool(struct _WLSM_GLOBAL_CONTEXT *a1, int a2)
{
  unsigned int v4; // edi
  unsigned int started; // ebx
  CUser *v6; // rcx
  __int64 v7; // rdx
  HANDLE v8; // rax
  void *v9; // rbx
  DWORD v10; // edi
  CUser *v11; // rcx
  __int64 v12; // rdx
  BYTE Data[4]; // [rsp+64h] [rbp-F4h] BYREF
  DWORD cbData; // [rsp+68h] [rbp-F0h] BYREF
  DWORD Type; // [rsp+6Ch] [rbp-ECh] BYREF
  HKEY hKey; // [rsp+70h] [rbp-E8h] BYREF
  void *KeyHandle; // [rsp+78h] [rbp-E0h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+80h] [rbp-D8h] BYREF
  struct _WINLOGON_JOB *v20; // [rsp+98h] [rbp-C0h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+A0h] [rbp-B8h] BYREF
  WCHAR CommandLine[20]; // [rsp+110h] [rbp-48h] BYREF

  *(_DWORD *)Data = 1;
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  v4 = *(_DWORD *)(*(_QWORD *)a1 + 176LL);
  switch ( v4 )
  {
    case 0xFFFFFFF7:
      started = WlAccessibilityOnCtrlWinEnter(a1, a2);
      if ( !started )
        return started;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return started;
      }
      v12 = 119;
LABEL_99:
      WPP_SF_d(*((_QWORD *)v11 + 2), v12, WPP_08fbe39dfd5c3ed1d0f5d3aa8d6e811c_Traceguids, started);
      return started;
    case 0xFFFFFFF8:
      started = WlAccessibilityOnWinPlus(a1, a2);
      if ( !started )
        return started;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return started;
      }
      v12 = 118;
      goto LABEL_99;
    case 0xFFFFFFF9:
      started = WlAccessibilityOnSlideToShutDown(a1, a2);
      if ( !started )
        return started;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return started;
      }
      v12 = 117;
      goto LABEL_99;
    case 0xFFFFFFFA:
      started = WlAccessibilityOnTabletLaunchAT(a1, a2);
      if ( !started )
        return started;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return started;
      }
      v12 = 116;
      goto LABEL_99;
    case 0xFFFFFFFB:
    case 0xFFFFFFFC:
    case 0xFFFFFFFD:
      started = WlAccessibilityOnDisplaySwitch(a1, a2);
      if ( !started )
        return started;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return started;
      }
      v12 = 115;
      goto LABEL_99;
    case 0xFFFFFFFE:
      started = WlAccessibilityOnStartOSK(a1, a2);
      if ( !started )
        return started;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return started;
      }
      v12 = 114;
      goto LABEL_99;
    case 0xFFFFFFFF:
      started = WlAccessibilityOnWinU(a1, a2);
      if ( !started )
        return started;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return started;
      }
      v12 = 113;
      goto LABEL_99;
  }
  if ( v4 >= 0xC8 )
  {
    if ( a2 )
    {
      KeyHandle = 0;
      if ( RtlOpenCurrentUser(0x2000000u, &KeyHandle) >= 0 )
      {
        hKey = 0;
        cbData = 4;
        Type = 0;
        if ( !RegOpenKeyExW((HKEY)KeyHandle, L"Control Panel\\Accessibility", 0, 0x20019u, &hKey) )
        {
          RegQueryValueExW(hKey, L"Warning Sounds", 0, &Type, Data, &cbData);
          RegCloseKey(hKey);
        }
        NtClose(KeyHandle);
      }
    }
    else
    {
      CUser::RegQueryDWORD(
        *((CUser **)a1 + 4),
        L"Control Panel\\Accessibility",
        L"Warning Sounds",
        1u,
        (unsigned int *)Data);
    }
    if ( *(_DWORD *)Data )
      ++v4;
  }
  if ( (int)StringCchPrintfW(CommandLine, 0x14u, L"sethc.exe %ld", v4) < 0 )
  {
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 120, WPP_08fbe39dfd5c3ed1d0f5d3aa8d6e811c_Traceguids);
    }
    started = 87;
    goto LABEL_60;
  }
  StartupInfo.cb = 104;
  StartupInfo.dwFlags = 1;
  StartupInfo.wShowWindow = 1;
  if ( a2 )
  {
    StartupInfo.lpDesktop = L"Winsta0\\Winlogon";
    if ( !CreateProcessAsUserW(
            *(HANDLE *)(*(_QWORD *)a1 + 80LL),
            L"sethc.exe",
            CommandLine,
            0,
            0,
            0,
            0x404u,
            0,
            0,
            &StartupInfo,
            &ProcessInformation) )
    {
      started = GetLastError();
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_60;
      }
      v7 = 121;
      goto LABEL_31;
    }
LABEL_37:
    v20 = 0;
    started = StartProcessInJob(&ProcessInformation, 0x493E0u, &v20);
    if ( started )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_60;
      }
      v7 = 123;
      goto LABEL_31;
    }
    if ( a2 && v4 < 0xC8 )
    {
      v8 = OpenProcess(0x100000u, 0, ProcessInformation.dwProcessId);
      v9 = v8;
      if ( !v8 )
      {
        started = GetLastError();
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_60;
        }
        v7 = 124;
        goto LABEL_31;
      }
      v10 = WaitForSingleObject(v8, 0x4E20u);
      CloseHandle(v9);
      if ( v10 == -1 )
      {
        started = GetLastError();
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_60;
        }
        v7 = 125;
        goto LABEL_31;
      }
      if ( v10 == 258
        && WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 126, WPP_08fbe39dfd5c3ed1d0f5d3aa8d6e811c_Traceguids);
      }
    }
    started = 0;
    goto LABEL_60;
  }
  StartupInfo.lpDesktop = 0;
  started = CUser::CreateProcessW(
              *((CUser **)a1 + 4),
              L"sethc.exe",
              CommandLine,
              4,
              &StartupInfo,
              &ProcessInformation,
              0);
  if ( !started )
    goto LABEL_37;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
  {
    goto LABEL_60;
  }
  v7 = 122;
LABEL_31:
  WPP_SF_d(*((_QWORD *)v6 + 2), v7, WPP_08fbe39dfd5c3ed1d0f5d3aa8d6e811c_Traceguids, started);
LABEL_60:
  if ( ProcessInformation.hProcess )
    CloseHandle(ProcessInformation.hProcess);
  if ( ProcessInformation.hThread )
    CloseHandle(ProcessInformation.hThread);
  return started;
}

```

## disassembly

```asm
0x140059928  mov     [rsp+arg_10], rbx
0x14005992d  push    rsi
0x14005992e  push    rdi
0x14005992f  push    r14
0x140059931  sub     rsp, 140h
0x140059938  mov     rax, cs:__security_cookie
0x14005993f  xor     rax, rsp
0x140059942  mov     [rsp+158h+var_20], rax
0x14005994a  mov     esi, edx
0x14005994c  mov     rbx, rcx
0x14005994f  mov     r14d, 1
0x140059955  mov     dword ptr [rsp+158h+Data], r14d
0x14005995a  xor     edx, edx; Val
0x14005995c  lea     r8d, [r14+67h]; Size
0x140059960  lea     rcx, [rsp+158h+StartupInfo]; void *
0x140059968  call    memset_0
0x14005996d  xorps   xmm0, xmm0
0x140059970  xor     eax, eax
0x140059972  movups  xmmword ptr [rsp+158h+ProcessInformation.hProcess], xmm0
0x14005997a  mov     qword ptr [rsp+158h+ProcessInformation.dwProcessId], rax
0x140059982  mov     rax, [rbx]
0x140059985  mov     edi, [rax+0B0h]
0x14005998b  cmp     edi, 0FFFFFFF7h
0x14005998e  jz      loc_140059FF6
0x140059994  cmp     edi, 0FFFFFFF8h
0x140059997  jz      loc_140059FBD
0x14005999d  cmp     edi, 0FFFFFFF9h
0x1400599a0  jz      loc_140059F74
0x1400599a6  cmp     edi, 0FFFFFFFAh
0x1400599a9  jz      loc_140059F28
0x1400599af  cmp     edi, 0FFFFFFFBh
0x1400599b2  jz      loc_140059EDC
0x1400599b8  cmp     edi, 0FFFFFFFCh
0x1400599bb  jz      loc_140059EDC
0x1400599c1  cmp     edi, 0FFFFFFFDh
0x1400599c4  jz      loc_140059EDC
0x1400599ca  cmp     edi, 0FFFFFFFEh
0x1400599cd  jz      loc_140059E90
0x1400599d3  cmp     edi, 0FFFFFFFFh
0x1400599d6  jz      loc_140059E44
0x1400599dc  cmp     edi, 0C8h
0x1400599e2  jb      loc_140059AC7
0x1400599e8  test    esi, esi
0x1400599ea  jz      loc_140059A99
0x1400599f0  mov     [rsp+158h+KeyHandle], 0
0x1400599f9  lea     rdx, [rsp+158h+KeyHandle]; KeyHandle
0x1400599fe  mov     ecx, 2000000h; DesiredAccess
0x140059a03  call    cs:__imp_RtlOpenCurrentUser
0x140059a09  test    eax, eax
0x140059a0b  js      loc_140059ABD
0x140059a11  mov     [rsp+158h+hKey], 0
0x140059a1a  mov     [rsp+158h+cbData], 4
0x140059a22  mov     [rsp+158h+Type], 0
0x140059a2a  lea     rax, [rsp+158h+hKey]
0x140059a2f  mov     [rsp+158h+phkResult], rax; phkResult
0x140059a34  mov     r9d, 20019h; samDesired
0x140059a3a  xor     r8d, r8d; ulOptions
0x140059a3d  lea     rdx, aControlPanelAc; "Control Panel\\Accessibility"
0x140059a44  mov     rcx, [rsp+158h+KeyHandle]; hKey
0x140059a49  call    cs:__imp_RegOpenKeyExW
0x140059a4f  test    eax, eax
0x140059a51  jnz     short loc_140059A8C
0x140059a53  lea     rax, [rsp+158h+cbData]
0x140059a58  mov     [rsp+158h+lpcbData], rax; lpcbData
0x140059a5d  lea     rax, [rsp+158h+Data]
0x140059a62  mov     [rsp+158h+phkResult], rax; lpData
0x140059a67  lea     r9, [rsp+158h+Type]; lpType
0x140059a6c  xor     r8d, r8d; lpReserved
0x140059a6f  lea     rdx, aWarningSounds; "Warning Sounds"
0x140059a76  mov     rcx, [rsp+158h+hKey]; hKey
0x140059a7b  call    cs:__imp_RegQueryValueExW
0x140059a81  mov     rcx, [rsp+158h+hKey]; hKey
0x140059a86  call    cs:__imp_RegCloseKey
0x140059a8c  mov     rcx, [rsp+158h+KeyHandle]; Handle
0x140059a91  call    cs:__imp_NtClose
0x140059a97  jmp     short loc_140059ABD
0x140059a99  lea     rax, [rsp+158h+Data]
0x140059a9e  mov     [rsp+158h+phkResult], rax; unsigned int *
0x140059aa3  mov     r9d, r14d; unsigned int
0x140059aa6  lea     r8, aWarningSounds; "Warning Sounds"
0x140059aad  lea     rdx, aControlPanelAc; "Control Panel\\Accessibility"
0x140059ab4  mov     rcx, [rbx+20h]; this
0x140059ab8  call    ?RegQueryDWORD@CUser@@QEAAKPEBG0KPEAK@Z; CUser::RegQueryDWORD(ushort const *,ushort const *,ulong,ulong *)
0x140059abd  cmp     dword ptr [rsp+158h+Data], 0
0x140059ac2  jz      short loc_140059AC7
0x140059ac4  add     edi, r14d
0x140059ac7  mov     r9d, edi
0x140059aca  lea     r8, aSethcExeLd; "sethc.exe %ld"
0x140059ad1  mov     edx, 14h; unsigned __int64
0x140059ad6  lea     rcx, [rsp+158h+CommandLine]; unsigned __int16 *
0x140059ade  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140059ae3  test    eax, eax
0x140059ae5  jns     short loc_140059B28
0x140059ae7  lea     rax, WPP_GLOBAL_Control
0x140059aee  mov     rcx, cs:WPP_GLOBAL_Control
0x140059af5  cmp     rcx, rax
0x140059af8  jz      short loc_140059B1E
0x140059afa  test    dword ptr [rcx+1Ch], 40000h
0x140059b01  jz      short loc_140059B1E
0x140059b03  cmp     byte ptr [rcx+19h], 2
0x140059b07  jb      short loc_140059B1E
0x140059b09  mov     edx, 78h ; 'x'
0x140059b0e  lea     r8, WPP_08fbe39dfd5c3ed1d0f5d3aa8d6e811c_Traceguids
0x140059b15  mov     rcx, [rcx+10h]
0x140059b19  call    WPP_SF_
0x140059b1e  mov     ebx, 57h ; 'W'
0x140059b23  jmp     loc_140059E11
0x140059b28  mov     [rsp+158h+StartupInfo.cb], 68h ; 'h'
0x140059b33  mov     [rsp+158h+StartupInfo.dwFlags], r14d
0x140059b3b  mov     [rsp+158h+StartupInfo.wShowWindow], r14w
0x140059b44  lea     r8, [rsp+158h+CommandLine]; lpCommandLine
0x140059b4c  lea     rdx, aSethcExe; "sethc.exe"
0x140059b53  test    esi, esi
0x140059b55  jz      loc_140059C1E
0x140059b5b  lea     rax, aWinsta0Winlogo; "Winsta0\\Winlogon"
0x140059b62  mov     [rsp+158h+StartupInfo.lpDesktop], rax
0x140059b6a  mov     rcx, [rbx]
0x140059b6d  lea     rax, [rsp+158h+ProcessInformation]
0x140059b75  mov     [rsp+158h+lpProcessInformation], rax; lpProcessInformation
0x140059b7a  lea     rax, [rsp+158h+StartupInfo]
0x140059b82  mov     [rsp+158h+lpStartupInfo], rax; lpStartupInfo
0x140059b87  mov     [rsp+158h+lpCurrentDirectory], 0; lpCurrentDirectory
0x140059b90  mov     [rsp+158h+lpEnvironment], 0; lpEnvironment
0x140059b99  mov     [rsp+158h+dwCreationFlags], 404h; dwCreationFlags
0x140059ba1  mov     dword ptr [rsp+158h+lpcbData], 0; bInheritHandles
0x140059ba9  mov     [rsp+158h+phkResult], 0; lpThreadAttributes
0x140059bb2  xor     r9d, r9d; lpProcessAttributes
0x140059bb5  mov     rcx, [rcx+50h]; hToken
0x140059bb9  call    cs:__imp_CreateProcessAsUserW
0x140059bbf  test    eax, eax
0x140059bc1  jnz     loc_140059C9D
0x140059bc7  call    cs:__imp_GetLastError
0x140059bcd  mov     ebx, eax
0x140059bcf  mov     [rsp+158h+var_F8], eax
0x140059bd3  lea     rax, WPP_GLOBAL_Control
0x140059bda  mov     rcx, cs:WPP_GLOBAL_Control
0x140059be1  cmp     rcx, rax
0x140059be4  jz      loc_140059E15
0x140059bea  test    dword ptr [rcx+1Ch], 40000h
0x140059bf1  jz      loc_140059E15
0x140059bf7  cmp     byte ptr [rcx+19h], 2
0x140059bfb  jb      loc_140059E15
0x140059c01  mov     edx, 79h ; 'y'
0x140059c06  mov     r9d, ebx
0x140059c09  lea     r8, WPP_08fbe39dfd5c3ed1d0f5d3aa8d6e811c_Traceguids
0x140059c10  mov     rcx, [rcx+10h]
0x140059c14  call    WPP_SF_d
0x140059c19  jmp     loc_140059E15
0x140059c1e  mov     [rsp+158h+StartupInfo.lpDesktop], 0
0x140059c2a  mov     [rsp+158h+dwCreationFlags], 0; int
0x140059c32  lea     rax, [rsp+158h+ProcessInformation]
0x140059c3a  mov     [rsp+158h+lpcbData], rax; LPPROCESS_INFORMATION
0x140059c3f  lea     rax, [rsp+158h+StartupInfo]
0x140059c47  mov     [rsp+158h+phkResult], rax; LPSTARTUPINFOW
0x140059c4c  mov     r9d, 4; unsigned int
0x140059c52  mov     rcx, [rbx+20h]; this
0x140059c56  call    ?CreateProcessW@CUser@@QEAAKPEBGPEAGKPEAU_STARTUPINFOW@@PEAU_PROCESS_INFORMATION@@H@Z; CUser::CreateProcessW(ushort const *,ushort *,ulong,_STARTUPINFOW *,_PROCESS_INFORMATION *,int)
0x140059c5b  mov     ebx, eax
0x140059c5d  mov     [rsp+158h+var_F8], eax
0x140059c61  test    eax, eax
0x140059c63  jz      short loc_140059C9D
0x140059c65  lea     rax, WPP_GLOBAL_Control
0x140059c6c  mov     rcx, cs:WPP_GLOBAL_Control
0x140059c73  cmp     rcx, rax
0x140059c76  jz      loc_140059E15
0x140059c7c  test    dword ptr [rcx+1Ch], 40000h
0x140059c83  jz      loc_140059E15
0x140059c89  cmp     byte ptr [rcx+19h], 2
0x140059c8d  jb      loc_140059E15
0x140059c93  mov     edx, 7Ah ; 'z'
0x140059c98  jmp     loc_140059C06
0x140059c9d  mov     [rsp+158h+var_C0], 0
0x140059ca9  lea     r8, [rsp+158h+var_C0]; struct _WINLOGON_JOB **
0x140059cb1  mov     edx, 493E0h; unsigned int
0x140059cb6  lea     rcx, [rsp+158h+ProcessInformation]; struct _PROCESS_INFORMATION *
0x140059cbe  call    ?StartProcessInJob@@YAKPEAU_PROCESS_INFORMATION@@KPEAPEAU_WINLOGON_JOB@@@Z; StartProcessInJob(_PROCESS_INFORMATION *,ulong,_WINLOGON_JOB * *)
0x140059cc3  mov     ebx, eax
0x140059cc5  mov     [rsp+158h+var_F8], eax
0x140059cc9  test    eax, eax
0x140059ccb  jz      short loc_140059D05
0x140059ccd  lea     rax, WPP_GLOBAL_Control
0x140059cd4  mov     rcx, cs:WPP_GLOBAL_Control
0x140059cdb  cmp     rcx, rax
0x140059cde  jz      loc_140059E15
0x140059ce4  test    dword ptr [rcx+1Ch], 40000h
0x140059ceb  jz      loc_140059E15
0x140059cf1  cmp     byte ptr [rcx+19h], 2
0x140059cf5  jb      loc_140059E15
0x140059cfb  mov     edx, 7Bh ; '{'
0x140059d00  jmp     loc_140059C06
0x140059d05  test    esi, esi
0x140059d07  jz      loc_140059E0F
0x140059d0d  cmp     edi, 0C8h
0x140059d13  jnb     loc_140059E0F
0x140059d19  mov     r8d, [rsp+158h+ProcessInformation.dwProcessId]; dwProcessId
0x140059d21  xor     edx, edx; bInheritHandle
0x140059d23  mov     ecx, 100000h; dwDesiredAccess
0x140059d28  call    cs:__imp_OpenProcess
0x140059d2e  mov     rbx, rax
0x140059d31  test    rax, rax
0x140059d34  jnz     short loc_140059D7A
0x140059d36  call    cs:__imp_GetLastError
0x140059d3c  mov     ebx, eax
0x140059d3e  mov     [rsp+158h+var_F8], eax
0x140059d42  lea     rax, WPP_GLOBAL_Control
0x140059d49  mov     rcx, cs:WPP_GLOBAL_Control
0x140059d50  cmp     rcx, rax
0x140059d53  jz      loc_140059E15
0x140059d59  test    dword ptr [rcx+1Ch], 40000h
0x140059d60  jz      loc_140059E15
0x140059d66  cmp     byte ptr [rcx+19h], 2
0x140059d6a  jb      loc_140059E15
0x140059d70  mov     edx, 7Ch ; '|'
0x140059d75  jmp     loc_140059C06
0x140059d7a  mov     edx, 4E20h; dwMilliseconds
0x140059d7f  mov     rcx, rbx; hHandle
0x140059d82  call    cs:__imp_WaitForSingleObject
0x140059d88  mov     edi, eax
0x140059d8a  mov     rcx, rbx; hObject
0x140059d8d  call    cs:__imp_CloseHandle
0x140059d93  cmp     edi, 0FFFFFFFFh
0x140059d96  jnz     short loc_140059DD0
0x140059d98  call    cs:__imp_GetLastError
0x140059d9e  mov     ebx, eax
0x140059da0  mov     [rsp+158h+var_F8], eax
0x140059da4  lea     rax, WPP_GLOBAL_Control
0x140059dab  mov     rcx, cs:WPP_GLOBAL_Control
0x140059db2  cmp     rcx, rax
0x140059db5  jz      short loc_140059E15
0x140059db7  test    dword ptr [rcx+1Ch], 40000h
0x140059dbe  jz      short loc_140059E15
0x140059dc0  cmp     byte ptr [rcx+19h], 2
0x140059dc4  jb      short loc_140059E15
0x140059dc6  mov     edx, 7Dh ; '}'
0x140059dcb  jmp     loc_140059C06
0x140059dd0  cmp     edi, 102h
0x140059dd6  jnz     short loc_140059E0F
0x140059dd8  lea     rax, WPP_GLOBAL_Control
0x140059ddf  mov     rcx, cs:WPP_GLOBAL_Control
0x140059de6  cmp     rcx, rax
0x140059de9  jz      short loc_140059E0F
0x140059deb  test    dword ptr [rcx+1Ch], 40000h
0x140059df2  jz      short loc_140059E0F
0x140059df4  cmp     byte ptr [rcx+19h], 3
0x140059df8  jb      short loc_140059E0F
0x140059dfa  mov     edx, 7Eh ; '~'
0x140059dff  lea     r8, WPP_08fbe39dfd5c3ed1d0f5d3aa8d6e811c_Traceguids
0x140059e06  mov     rcx, [rcx+10h]
0x140059e0a  call    WPP_SF_
0x140059e0f  xor     ebx, ebx
0x140059e11  mov     [rsp+158h+var_F8], ebx
0x140059e15  mov     rcx, [rsp+158h+ProcessInformation.hProcess]; hObject
0x140059e1d  test    rcx, rcx
0x140059e20  jz      short loc_140059E28
0x140059e22  call    cs:__imp_CloseHandle
0x140059e28  mov     rcx, [rsp+158h+ProcessInformation.hThread]; hObject
0x140059e30  test    rcx, rcx
0x140059e33  jz      loc_14005A040
0x140059e39  call    cs:__imp_CloseHandle
0x140059e3f  jmp     loc_14005A040
0x140059e44  mov     edx, esi; int
0x140059e46  mov     rcx, rbx; struct _WLSM_GLOBAL_CONTEXT *
0x140059e49  call    ?WlAccessibilityOnWinU@@YAKPEAU_WLSM_GLOBAL_CONTEXT@@H@Z; WlAccessibilityOnWinU(_WLSM_GLOBAL_CONTEXT *,int)
0x140059e4e  mov     ebx, eax
0x140059e50  test    eax, eax
0x140059e52  jz      loc_14005A040
0x140059e58  lea     rax, WPP_GLOBAL_Control
0x140059e5f  mov     rcx, cs:WPP_GLOBAL_Control
0x140059e66  cmp     rcx, rax
0x140059e69  jz      loc_14005A040
0x140059e6f  test    dword ptr [rcx+1Ch], 40000h
0x140059e76  jz      loc_14005A040
0x140059e7c  cmp     byte ptr [rcx+19h], 2
0x140059e80  jb      loc_14005A040
0x140059e86  mov     edx, 71h ; 'q'
0x140059e8b  jmp     loc_14005A02D
0x140059e90  mov     edx, esi; int
0x140059e92  mov     rcx, rbx; struct _WLSM_GLOBAL_CONTEXT *
0x140059e95  call    ?WlAccessibilityOnStartOSK@@YAKPEAU_WLSM_GLOBAL_CONTEXT@@H@Z; WlAccessibilityOnStartOSK(_WLSM_GLOBAL_CONTEXT *,int)
0x140059e9a  mov     ebx, eax
0x140059e9c  test    eax, eax
0x140059e9e  jz      loc_14005A040
0x140059ea4  lea     rax, WPP_GLOBAL_Control
0x140059eab  mov     rcx, cs:WPP_GLOBAL_Control
0x140059eb2  cmp     rcx, rax
0x140059eb5  jz      loc_14005A040
0x140059ebb  test    dword ptr [rcx+1Ch], 40000h
0x140059ec2  jz      loc_14005A040
0x140059ec8  cmp     byte ptr [rcx+19h], 2
0x140059ecc  jb      loc_14005A040
0x140059ed2  mov     edx, 72h ; 'r'
0x140059ed7  jmp     loc_14005A02D
0x140059edc  mov     edx, esi; int
0x140059ede  mov     rcx, rbx; struct _WLSM_GLOBAL_CONTEXT *
0x140059ee1  call    ?WlAccessibilityOnDisplaySwitch@@YAKPEAU_WLSM_GLOBAL_CONTEXT@@H@Z; WlAccessibilityOnDisplaySwitch(_WLSM_GLOBAL_CONTEXT *,int)
0x140059ee6  mov     ebx, eax
0x140059ee8  test    eax, eax
0x140059eea  jz      loc_14005A040
0x140059ef0  lea     rax, WPP_GLOBAL_Control
0x140059ef7  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
