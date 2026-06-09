# GpModeCleanup(void)

- ea: `0x140006fb8`
- end: `0x14000759b`
- name: `?GpModeCleanup@@YAJXZ`
- size: `1507`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x14000c488`

## callees

- `0x140001a63`
- `0x140006fb8`
- `0x14000b84c`
- `0x14000d25c`
- `0x14000e280`
- `0x14000e4c4`
- `0x140013490`
- `0x140014910`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14000736a`
- `ADVAPI32!RegCloseKey` at `0x140007546`
- `ADVAPI32!RegCloseKey` at `0x14000755b`
- `ADVAPI32!RegCloseKey` at `0x140007570`
- `ADVAPI32!RegCloseKey` at `0x14000736a`
- `ADVAPI32!RegCloseKey` at `0x140007546`
- `ADVAPI32!RegCloseKey` at `0x14000755b`
- `ADVAPI32!RegCloseKey` at `0x140007570`
- `ADVAPI32!RegOpenKeyExW` at `0x14000705d`
- `ADVAPI32!RegOpenKeyExW` at `0x1400071d7`
- `ADVAPI32!RegOpenKeyExW` at `0x140007235`
- `ADVAPI32!RegOpenKeyExW` at `0x14000730c`
- `ADVAPI32!RegOpenKeyExW` at `0x14000705d`
- `ADVAPI32!RegOpenKeyExW` at `0x1400071d7`
- `ADVAPI32!RegOpenKeyExW` at `0x140007235`
- `ADVAPI32!RegOpenKeyExW` at `0x14000730c`
- `ADVAPI32!ConvertSidToStringSidW` at `0x14000717e`
- `ADVAPI32!ConvertSidToStringSidW` at `0x14000717e`
- `ADVAPI32!RegDeleteValueW` at `0x140007267`
- `ADVAPI32!RegDeleteValueW` at `0x140007267`
- `ADVAPI32!RegEnumKeyW` at `0x1400072ca`
- `ADVAPI32!RegEnumKeyW` at `0x1400072ca`
- `ADVAPI32!RegQueryValueExW` at `0x140007357`
- `ADVAPI32!RegQueryValueExW` at `0x140007357`
- `ADVAPI32!RegDeleteKeyW` at `0x14000739b`
- `ADVAPI32!RegDeleteKeyW` at `0x14000739b`
- `KERNEL32!CloseHandle` at `0x14000751c`
- `KERNEL32!CloseHandle` at `0x14000751c`
- `KERNEL32!GetCurrentProcessId` at `0x1400070bd`
- `KERNEL32!GetCurrentProcessId` at `0x1400070bd`
- `KERNEL32!LocalFree` at `0x140007502`
- `KERNEL32!LocalFree` at `0x140007531`
- `KERNEL32!LocalFree` at `0x140007502`
- `KERNEL32!LocalFree` at `0x140007531`
- `KERNEL32!ProcessIdToSessionId` at `0x1400070ca`
- `KERNEL32!ProcessIdToSessionId` at `0x1400070ca`
- `KERNEL32!GetLastError` at `0x1400070d4`
- `KERNEL32!GetLastError` at `0x140007114`
- `KERNEL32!GetLastError` at `0x140007188`
- `KERNEL32!GetLastError` at `0x1400070d4`
- `KERNEL32!GetLastError` at `0x140007114`
- `KERNEL32!GetLastError` at `0x140007188`
- `msvcrt!_wcsicmp` at `0x140007388`
- `msvcrt!_wcsicmp` at `0x140007388`
- `WTSAPI32!WTSQueryUserToken` at `0x14000710a`
- `WTSAPI32!WTSQueryUserToken` at `0x14000710a`

## string_xrefs

- `0x14000707b`: `Failed to open machine appmgmt key`
- `0x140007098`: `SeTcbPrivilege`
- `0x1400070af`: `Failed to set privilege: SE_TCB_NAME`
- `0x1400070eb`: `Failed: ProcessIdToSessionId()`
- `0x14000712e`: `Failed: WTSQueryUserToken() with Session Id %u`
- `0x14000719f`: `Failed: ConvertSidToStringSid()`
- `0x1400071f6`: `Failed to open key HKEY_USER\%ls`
- `0x14000724a`: `Failed to open current user appmgmt key`
- `0x14000728a`: `Deleted registry value: %ls\%ls\%ls`
- `0x140007496`: `Failed to delete registry value: %ls\%ls\%ls`
- `0x140007447`: `Failed to open subkey: %ls`
- `0x1400073cc`: `Failed to delete key: %ls\%ls\%ls`
- `0x1400073fb`: `Deleted key: %ls\%ls\%ls`

## pseudocode

```c
__int64 GpModeCleanup(void)
{
  LSTATUS v0; // eax
  signed int v1; // ebx
  const char *v2; // r8
  __int64 v3; // rdx
  DWORD CurrentProcessId; // eax
  signed int LastError; // eax
  signed int v6; // eax
  unsigned int v7; // r8d
  signed int v8; // eax
  LSTATUS v9; // eax
  LSTATUS v10; // eax
  LSTATUS v11; // eax
  LPWSTR v12; // rsi
  LPWSTR v13; // r9
  DWORD i; // r12d
  LSTATUS v15; // eax
  LSTATUS v16; // eax
  LSTATUS v17; // r15d
  LSTATUS v18; // eax
  const char *v19; // r8
  __int64 v20; // rdx
  LPWSTR v21; // r9
  void *v22; // rdi
  WCHAR *lpcbData; // [rsp+28h] [rbp-D8h]
  LPWSTR StringSid; // [rsp+30h] [rbp-D0h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-C8h] BYREF
  DWORD pSessionId[2]; // [rsp+40h] [rbp-C0h] BYREF
  HKEY v28; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cbData; // [rsp+50h] [rbp-B0h] BYREF
  void *phToken; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  DWORD Type; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int8 Sid[80]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Name[512]; // [rsp+C0h] [rbp-40h] BYREF
  wchar_t Data[512]; // [rsp+4C0h] [rbp+3C0h] BYREF

  phkResult = 0;
  v28 = 0;
  hKey = 0;
  memset_0(Name, 0, sizeof(Name));
  memset_0(Data, 0, sizeof(Data));
  cbData = 0;
  Type = 0;
  StringSid = 0;
  phToken = 0;
  if ( !dword_140020190 )
  {
    pSessionId[0] = 0;
    v1 = EnablePrivilege(L"SeTcbPrivilege");
    if ( v1 >= 0 )
    {
      CurrentProcessId = GetCurrentProcessId();
      if ( !ProcessIdToSessionId(CurrentProcessId, pSessionId) )
      {
        LastError = GetLastError();
        v1 = LastError;
        if ( LastError > 0 )
          v1 = (unsigned __int16)LastError | 0x80070000;
        v2 = "Failed: ProcessIdToSessionId()";
        v3 = 1970;
        if ( v1 >= 0 )
          v1 = -2147467259;
        goto LABEL_6;
      }
      if ( !WTSQueryUserToken(pSessionId[0], &phToken) )
      {
        v6 = GetLastError();
        v1 = v6;
        if ( v6 > 0 )
          v1 = (unsigned __int16)v6 | 0x80070000;
        if ( v1 >= 0 )
          v1 = -2147467259;
        WusaLogDebugEventA(L"GpModeCleanup", 1973, "Failed: WTSQueryUserToken() with Session Id %u", pSessionId[0]);
        goto LABEL_74;
      }
      memset_0(Sid, 0, 0x48u);
      WusaGetUserSID(phToken, Sid, v7);
      if ( !ConvertSidToStringSidW(Sid, &StringSid) )
      {
        v8 = GetLastError();
        v1 = v8;
        if ( v8 > 0 )
          v1 = (unsigned __int16)v8 | 0x80070000;
        v2 = "Failed: ConvertSidToStringSid()";
        v3 = 1979;
        if ( v1 >= 0 )
          v1 = -2147467259;
        goto LABEL_6;
      }
      v9 = RegOpenKeyExW(HKEY_USERS, StringSid, 0, 0xF003Fu, &hKey);
      v1 = v9;
      if ( v9 > 0 )
        v1 = (unsigned __int16)v9 | 0x80070000;
      if ( v1 >= 0 )
      {
        v10 = RegOpenKeyExW(
                hKey,
                L"Software\\Microsoft\\Windows\\CurrentVersion\\Group Policy\\AppMgmt",
                0,
                0xF003Fu,
                &phkResult);
        v1 = v10;
        if ( v10 > 0 )
          v1 = (unsigned __int16)v10 | 0x80070000;
        if ( v1 >= 0 )
          goto LABEL_35;
        WusaLogDebugEventA(L"GpModeCleanup", 1987, "Failed to open current user appmgmt key");
      }
      else
      {
        WusaLogDebugEventA(L"GpModeCleanup", 1983, "Failed to open key HKEY_USER\\%ls", StringSid);
      }
    }
    else
    {
      WusaLogDebugEventA(L"GpModeCleanup", 1967, "Failed to set privilege: SE_TCB_NAME");
    }
LABEL_74:
    *(_QWORD *)pSessionId = 0;
    WusaGetErrorMessage(v1, (unsigned __int16 **)pSessionId);
    v22 = *(void **)pSessionId;
    WusaLogDebugEventA(L"GpModeCleanup", 2058, "Exit with error code 0X%x (%ls)", v1, *(const wchar_t **)pSessionId);
    if ( v22 )
      LocalFree(v22);
    goto LABEL_76;
  }
  v0 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Group Policy\\AppMgmt",
         0,
         0xF003Fu,
         &phkResult);
  v1 = v0;
  if ( v0 > 0 )
    v1 = (unsigned __int16)v0 | 0x80070000;
  if ( v1 < 0 )
  {
    v2 = "Failed to open machine appmgmt key";
    v3 = 1960;
LABEL_6:
    WusaLogDebugEventA(L"GpModeCleanup", v3, v2);
    goto LABEL_74;
  }
LABEL_35:
  v11 = RegDeleteValueW(phkResult, String2);
  if ( v11 )
  {
    if ( v11 == 2 )
      goto LABEL_76;
    if ( v11 > 0 )
      v1 = (unsigned __int16)v11 | 0x80070000;
    else
      v1 = v11;
    v21 = L"HKLM";
    v19 = "Failed to delete registry value: %ls\\%ls\\%ls";
    lpcbData = (WCHAR *)String2;
    if ( !dword_140020190 )
      v21 = StringSid;
    v20 = 1999;
LABEL_72:
    WusaLogDebugEventA(
      L"GpModeCleanup",
      v20,
      v19,
      v21,
      L"Software\\Microsoft\\Windows\\CurrentVersion\\Group Policy\\AppMgmt",
      lpcbData);
    goto LABEL_74;
  }
  v12 = L"HKLM";
  v13 = L"HKLM";
  if ( !dword_140020190 )
    v13 = StringSid;
  WusaLogDebugEventA(
    L"GpModeCleanup",
    1994,
    "Deleted registry value: %ls\\%ls\\%ls",
    v13,
    L"Software\\Microsoft\\Windows\\CurrentVersion\\Group Policy\\AppMgmt",
    String2);
  for ( i = 0; ; ++i )
  {
    v15 = RegEnumKeyW(phkResult, i, Name, 0x200u);
    if ( v15 == 259 )
      break;
    if ( v15 > 0 )
      v1 = (unsigned __int16)v15 | 0x80070000;
    else
      v1 = v15;
    if ( v1 < 0 )
    {
      WusaLogDebugEventA(
        L"GpModeCleanup",
        2013,
        "Failed: RegEumKey() %ls",
        L"Software\\Microsoft\\Windows\\CurrentVersion\\Group Policy\\AppMgmt");
      goto LABEL_74;
    }
    v16 = RegOpenKeyExW(phkResult, Name, 0, 0x20019u, &v28);
    v1 = v16;
    if ( v16 > 0 )
      v1 = (unsigned __int16)v16 | 0x80070000;
    if ( v1 < 0 )
    {
      WusaLogDebugEventA(L"GpModeCleanup", 2018, "Failed to open subkey: %ls", Name);
      goto LABEL_74;
    }
    cbData = 1024;
    v17 = RegQueryValueExW(v28, L"Product ID", 0, &Type, (LPBYTE)Data, &cbData);
    if ( v28 )
      RegCloseKey(v28);
    v28 = 0;
    if ( v17 )
    {
      if ( v17 != 2 )
      {
        WusaLogDebugEventA(L"GpModeCleanup", 2041, "Failed to query string value: %ls", L"Product ID");
        break;
      }
    }
    else if ( !_wcsicmp(Data, String2) )
    {
      v18 = RegDeleteKeyW(phkResult, Name);
      v1 = v18;
      if ( v18 > 0 )
        v1 = (unsigned __int16)v18 | 0x80070000;
      lpcbData = Name;
      if ( v1 < 0 )
      {
        v19 = "Failed to delete key: %ls\\%ls\\%ls";
        v20 = 2052;
        if ( !dword_140020190 )
          v12 = StringSid;
        v21 = v12;
        goto LABEL_72;
      }
      if ( !dword_140020190 )
        v12 = StringSid;
      WusaLogDebugEventA(
        L"GpModeCleanup",
        2053,
        "Deleted key: %ls\\%ls\\%ls",
        v12,
        L"Software\\Microsoft\\Windows\\CurrentVersion\\Group Policy\\AppMgmt",
        Name);
      break;
    }
  }
LABEL_76:
  UninstallWrapperMsi(phToken);
  if ( phToken )
  {
    CloseHandle(phToken);
    phToken = 0;
  }
  if ( StringSid )
  {
    LocalFree(StringSid);
    StringSid = 0;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v28 )
  {
    RegCloseKey(v28);
    v28 = 0;
  }
  if ( phkResult )
    RegCloseKey(phkResult);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x140006fb8  push    rbp
0x140006fba  push    rbx
0x140006fbb  push    rsi
0x140006fbc  push    rdi
0x140006fbd  push    r12
0x140006fbf  push    r13
0x140006fc1  push    r14
0x140006fc3  push    r15
0x140006fc5  lea     rbp, [rsp-7D8h]
0x140006fcd  sub     rsp, 8D8h
0x140006fd4  mov     rax, cs:__security_cookie
0x140006fdb  xor     rax, rsp
0x140006fde  mov     [rbp+810h+var_50], rax
0x140006fe5  xor     r13d, r13d
0x140006fe8  lea     rcx, [rbp+810h+Name]; void *
0x140006fec  xor     edx, edx; Val
0x140006fee  mov     [rsp+910h+var_8D8], r13
0x140006ff3  mov     r8d, 400h; Size
0x140006ff9  mov     [rsp+910h+var_8C8], r13
0x140006ffe  mov     [rsp+910h+hKey], r13
0x140007003  call    memset_0
0x140007008  xor     edx, edx; Val
0x14000700a  lea     rcx, [rbp+810h+Data]; void *
0x140007011  mov     r8d, 400h; Size
0x140007017  call    memset_0
0x14000701c  cmp     cs:dword_140020190, r13d
0x140007023  mov     [rsp+910h+cbData], r13d
0x140007028  mov     [rsp+910h+Type], r13d
0x14000702d  mov     [rsp+910h+StringSid], r13
0x140007032  mov     [rsp+910h+phToken], r13
0x140007037  jz      short loc_140007098
0x140007039  lea     rax, [rsp+910h+var_8D8]
0x14000703e  mov     r9d, 0F003Fh; samDesired
0x140007044  lea     r14, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x14000704b  mov     [rsp+910h+phkResult], rax; phkResult
0x140007050  mov     rdx, r14; lpSubKey
0x140007053  xor     r8d, r8d; ulOptions
0x140007056  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000705d  call    cs:__imp_RegOpenKeyExW
0x140007063  mov     ebx, eax
0x140007065  mov     edi, 80070000h
0x14000706a  test    eax, eax
0x14000706c  jle     short loc_140007073
0x14000706e  movzx   ebx, ax
0x140007071  or      ebx, edi
0x140007073  test    ebx, ebx
0x140007075  jns     loc_14000725B
0x14000707b  lea     r8, aFailedToOpenMa; "Failed to open machine appmgmt key"
0x140007082  mov     edx, 7A8h
0x140007087  lea     rcx, aGpmodecleanup; "GpModeCleanup"
0x14000708e  call    WusaLogDebugEventA
0x140007093  jmp     loc_1400074C4
0x140007098  lea     rcx, Name; "SeTcbPrivilege"
0x14000709f  mov     [rsp+910h+pSessionId], r13d
0x1400070a4  call    ?EnablePrivilege@@YAJPEBG@Z; EnablePrivilege(ushort const *)
0x1400070a9  mov     ebx, eax
0x1400070ab  test    eax, eax
0x1400070ad  jns     short loc_1400070BD
0x1400070af  lea     r8, aFailedToSetPri; "Failed to set privilege: SE_TCB_NAME"
0x1400070b6  mov     edx, 7AFh
0x1400070bb  jmp     short loc_140007087
0x1400070bd  call    cs:__imp_GetCurrentProcessId
0x1400070c3  mov     ecx, eax; dwProcessId
0x1400070c5  lea     rdx, [rsp+910h+pSessionId]; pSessionId
0x1400070ca  call    cs:__imp_ProcessIdToSessionId
0x1400070d0  test    eax, eax
0x1400070d2  jnz     short loc_140007101
0x1400070d4  call    cs:__imp_GetLastError
0x1400070da  mov     ebx, eax
0x1400070dc  test    eax, eax
0x1400070de  jle     short loc_1400070E9
0x1400070e0  movzx   ebx, ax
0x1400070e3  or      ebx, 80070000h
0x1400070e9  test    ebx, ebx
0x1400070eb  lea     r8, aFailedProcessi; "Failed: ProcessIdToSessionId()"
0x1400070f2  mov     eax, 80004005h
0x1400070f7  mov     edx, 7B2h
0x1400070fc  cmovns  ebx, eax
0x1400070ff  jmp     short loc_140007087
0x140007101  mov     ecx, [rsp+910h+pSessionId]; SessionId
0x140007105  lea     rdx, [rsp+910h+phToken]; phToken
0x14000710a  call    cs:__imp_WTSQueryUserToken
0x140007110  test    eax, eax
0x140007112  jnz     short loc_140007155
0x140007114  call    cs:__imp_GetLastError
0x14000711a  mov     ebx, eax
0x14000711c  test    eax, eax
0x14000711e  jle     short loc_140007129
0x140007120  movzx   ebx, ax
0x140007123  or      ebx, 80070000h
0x140007129  mov     r9d, [rsp+910h+pSessionId]
0x14000712e  lea     r8, aFailedWtsquery; "Failed: WTSQueryUserToken() with Sessio"...
0x140007135  test    ebx, ebx
0x140007137  lea     rcx, aGpmodecleanup; "GpModeCleanup"
0x14000713e  mov     eax, 80004005h
0x140007143  mov     edx, 7B5h
0x140007148  cmovns  ebx, eax
0x14000714b  call    WusaLogDebugEventA
0x140007150  jmp     loc_1400074C4
0x140007155  xor     edx, edx; Val
0x140007157  lea     rcx, [rsp+910h+Sid]; void *
0x14000715c  lea     r8d, [rdx+48h]; Size
0x140007160  call    memset_0
0x140007165  mov     rcx, [rsp+910h+phToken]; void *
0x14000716a  lea     rdx, [rsp+910h+Sid]; unsigned __int8 *
0x14000716f  call    ?WusaGetUserSID@@YAJPEAXPEAEK@Z; WusaGetUserSID(void *,uchar *,ulong)
0x140007174  lea     rdx, [rsp+910h+StringSid]; StringSid
0x140007179  lea     rcx, [rsp+910h+Sid]; Sid
0x14000717e  call    cs:__imp_ConvertSidToStringSidW
0x140007184  test    eax, eax
0x140007186  jnz     short loc_1400071B8
0x140007188  call    cs:__imp_GetLastError
0x14000718e  mov     ebx, eax
0x140007190  test    eax, eax
0x140007192  jle     short loc_14000719D
0x140007194  movzx   ebx, ax
0x140007197  or      ebx, 80070000h
0x14000719d  test    ebx, ebx
0x14000719f  lea     r8, aFailedConverts; "Failed: ConvertSidToStringSid()"
0x1400071a6  mov     eax, 80004005h
0x1400071ab  mov     edx, 7BBh
0x1400071b0  cmovns  ebx, eax
0x1400071b3  jmp     loc_140007087
0x1400071b8  mov     rdx, [rsp+910h+StringSid]; lpSubKey
0x1400071bd  lea     rax, [rsp+910h+hKey]
0x1400071c2  mov     r9d, 0F003Fh; samDesired
0x1400071c8  mov     [rsp+910h+phkResult], rax; phkResult
0x1400071cd  xor     r8d, r8d; ulOptions
0x1400071d0  mov     rcx, 0FFFFFFFF80000003h; hKey
0x1400071d7  call    cs:__imp_RegOpenKeyExW
0x1400071dd  mov     ebx, eax
0x1400071df  mov     edi, 80070000h
0x1400071e4  test    eax, eax
0x1400071e6  jle     short loc_1400071ED
0x1400071e8  movzx   ebx, ax
0x1400071eb  or      ebx, edi
0x1400071ed  test    ebx, ebx
0x1400071ef  jns     short loc_140007213
0x1400071f1  mov     r9, [rsp+910h+StringSid]
0x1400071f6  lea     r8, aFailedToOpenKe; "Failed to open key HKEY_USER\\%ls"
0x1400071fd  mov     edx, 7BFh
0x140007202  lea     rcx, aGpmodecleanup; "GpModeCleanup"
0x140007209  call    WusaLogDebugEventA
0x14000720e  jmp     loc_1400074C4
0x140007213  mov     rcx, [rsp+910h+hKey]; hKey
0x140007218  lea     rax, [rsp+910h+var_8D8]
0x14000721d  lea     r14, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x140007224  mov     [rsp+910h+phkResult], rax; phkResult
0x140007229  mov     rdx, r14; lpSubKey
0x14000722c  mov     r9d, 0F003Fh; samDesired
0x140007232  xor     r8d, r8d; ulOptions
0x140007235  call    cs:__imp_RegOpenKeyExW
0x14000723b  mov     ebx, eax
0x14000723d  test    eax, eax
0x14000723f  jle     short loc_140007246
0x140007241  movzx   ebx, ax
0x140007244  or      ebx, edi
0x140007246  test    ebx, ebx
0x140007248  jns     short loc_14000725B
0x14000724a  lea     r8, aFailedToOpenCu; "Failed to open current user appmgmt key"
0x140007251  mov     edx, 7C3h
0x140007256  jmp     loc_140007087
0x14000725b  mov     rdx, cs:String2; lpValueName
0x140007262  mov     rcx, [rsp+910h+var_8D8]; hKey
0x140007267  call    cs:__imp_RegDeleteValueW
0x14000726d  test    eax, eax
0x14000726f  jnz     loc_140007467
0x140007275  cmp     cs:dword_140020190, r13d
0x14000727c  lea     rsi, aHklm; "HKLM"
0x140007283  mov     rax, cs:String2
0x14000728a  lea     r8, aDeletedRegistr; "Deleted registry value: %ls\\%ls\\%ls"
0x140007291  mov     [rsp+910h+lpcbData], rax
0x140007296  lea     rcx, aGpmodecleanup; "GpModeCleanup"
0x14000729d  mov     r9, rsi
0x1400072a0  mov     [rsp+910h+phkResult], r14
0x1400072a5  cmovz   r9, [rsp+910h+StringSid]
0x1400072ab  mov     edx, 7CAh
0x1400072b0  call    WusaLogDebugEventA
0x1400072b5  mov     r12d, r13d
0x1400072b8  mov     rcx, [rsp+910h+var_8D8]; hKey
0x1400072bd  lea     r8, [rbp+810h+Name]; lpName
0x1400072c1  mov     r9d, 200h; cchName
0x1400072c7  mov     edx, r12d; dwIndex
0x1400072ca  call    cs:__imp_RegEnumKeyW
0x1400072d0  cmp     eax, 103h
0x1400072d5  jz      loc_1400074C0
0x1400072db  test    eax, eax
0x1400072dd  jg      short loc_1400072E3
0x1400072df  mov     ebx, eax
0x1400072e1  jmp     short loc_1400072E8
0x1400072e3  movzx   ebx, ax
0x1400072e6  or      ebx, edi
0x1400072e8  test    ebx, ebx
0x1400072ea  js      loc_140007453
0x1400072f0  mov     rcx, [rsp+910h+var_8D8]; hKey
0x1400072f5  lea     rax, [rsp+910h+var_8C8]
0x1400072fa  mov     r9d, 20019h; samDesired
0x140007300  mov     [rsp+910h+phkResult], rax; phkResult
0x140007305  xor     r8d, r8d; ulOptions
0x140007308  lea     rdx, [rbp+810h+Name]; lpSubKey
0x14000730c  call    cs:__imp_RegOpenKeyExW
0x140007312  mov     ebx, eax
0x140007314  test    eax, eax
0x140007316  jle     short loc_14000731D
0x140007318  movzx   ebx, ax
0x14000731b  or      ebx, edi
0x14000731d  test    ebx, ebx
0x14000731f  js      loc_14000743E
0x140007325  mov     rcx, [rsp+910h+var_8C8]; hKey
0x14000732a  lea     rax, [rsp+910h+cbData]
0x14000732f  mov     [rsp+910h+lpcbData], rax; lpcbData
0x140007334  lea     r9, [rsp+910h+Type]; lpType
0x140007339  lea     rax, [rbp+810h+Data]
0x140007340  mov     [rsp+910h+cbData], 400h
0x140007348  xor     r8d, r8d; lpReserved
0x14000734b  mov     [rsp+910h+phkResult], rax; lpData
0x140007350  lea     rdx, aProductId; "Product ID"
0x140007357  call    cs:__imp_RegQueryValueExW
0x14000735d  mov     rcx, [rsp+910h+var_8C8]; hKey
0x140007362  mov     r15d, eax
0x140007365  test    rcx, rcx
0x140007368  jz      short loc_140007370
0x14000736a  call    cs:__imp_RegCloseKey
0x140007370  mov     [rsp+910h+var_8C8], r13
0x140007375  test    r15d, r15d
0x140007378  jnz     short loc_1400073E6
0x14000737a  mov     rdx, cs:String2; String2
0x140007381  lea     rcx, [rbp+810h+Data]; String1
0x140007388  call    cs:__imp__wcsicmp
0x14000738e  test    eax, eax
0x140007390  jnz     short loc_1400073EC
0x140007392  mov     rcx, [rsp+910h+var_8D8]; hKey
0x140007397  lea     rdx, [rbp+810h+Name]; lpSubKey
0x14000739b  call    cs:__imp_RegDeleteKeyW
0x1400073a1  mov     ebx, eax
0x1400073a3  test    eax, eax
0x1400073a5  jle     short loc_1400073AC
0x1400073a7  movzx   ebx, ax
0x1400073aa  or      ebx, edi
0x1400073ac  lea     rax, [rbp+810h+Name]
0x1400073b0  mov     [rsp+910h+lpcbData], rax
0x1400073b5  lea     rcx, aGpmodecleanup; "GpModeCleanup"
0x1400073bc  mov     [rsp+910h+phkResult], r14
0x1400073c1  test    ebx, ebx
0x1400073c3  jns     short loc_1400073F4
0x1400073c5  cmp     cs:dword_140020190, r13d
0x1400073cc  lea     r8, aFailedToDelete_1; "Failed to delete key: %ls\\%ls\\%ls"
0x1400073d3  mov     edx, 804h
0x1400073d8  cmovz   rsi, [rsp+910h+StringSid]
0x1400073de  mov     r9, rsi
0x1400073e1  jmp     loc_1400074B9
0x1400073e6  cmp     r15d, 2
0x1400073ea  jnz     short loc_14000741A
0x1400073ec  inc     r12d
0x1400073ef  jmp     loc_1400072B8
0x1400073f4  cmp     cs:dword_140020190, r13d
0x1400073fb  lea     r8, aDeletedKeyLsLs; "Deleted key: %ls\\%ls\\%ls"
0x140007402  mov     edx, 805h
0x140007407  cmovz   rsi, [rsp+910h+StringSid]
0x14000740d  mov     r9, rsi
0x140007410  call    WusaLogDebugEventA
0x140007415  jmp     loc_140007508
0x14000741a  lea     r9, aProductId; "Product ID"
0x140007421  mov     edx, 7F9h
0x140007426  lea     r8, aFailedToQueryS_0; "Failed to query string value: %ls"
0x14000742d  lea     rcx, aGpmodecleanup; "GpModeCleanup"
0x140007434  call    WusaLogDebugEventA
0x140007439  jmp     loc_140007508
0x14000743e  lea     r9, [rbp+810h+Name]
0x140007442  mov     edx, 7E2h
0x140007447  lea     r8, aFailedToOpenSu; "Failed to open subkey: %ls"
0x14000744e  jmp     loc_140007202
0x140007453  mov     r9, r14
0x140007456  lea     r8, aFailedRegeumke; "Failed: RegEumKey() %ls"
0x14000745d  mov     edx, 7DDh
0x140007462  jmp     loc_140007202
0x140007467  cmp     eax, 2
0x14000746a  jz      short loc_1400074C0
0x14000746c  test    eax, eax
0x14000746e  jg      short loc_140007474
0x140007470  mov     ebx, eax
0x140007472  jmp     short loc_140007479
0x140007474  movzx   ebx, ax
0x140007477  or      ebx, edi
0x140007479  test    ebx, ebx
0x14000747b  jns     loc_140007508
0x140007481  mov     rax, cs:String2
0x140007488  lea     r9, aHklm; "HKLM"
0x14000748f  cmp     cs:dword_140020190, r13d
0x140007496  lea     r8, aFailedToDelete; "Failed to delete registry value: %ls\\%"...
0x14000749d  mov     [rsp+910h+lpcbData], rax
0x1400074a2  lea     rcx, aGpmodecleanup; "GpModeCleanup"
0x1400074a9  cmovz   r9, [rsp+910h+StringSid]
0x1400074af  mov     edx, 7CFh
0x1400074b4  mov     [rsp+910h+phkResult], r14
0x1400074b9  call    WusaLogDebugEventA
0x1400074be  jmp     short loc_1400074C4
0x1400074c0  test    ebx, ebx
0x1400074c2  jns     short loc_140007508
0x1400074c4  lea     rdx, [rsp+910h+pSessionId]; unsigned __int16 **
  ... truncated ...
```
