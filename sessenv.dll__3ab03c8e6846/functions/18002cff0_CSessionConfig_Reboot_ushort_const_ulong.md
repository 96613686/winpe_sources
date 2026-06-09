# CSessionConfig::Reboot(ushort const *,ulong)

- ea: `0x18002cff0`
- end: `0x18002d3c6`
- name: `?Reboot@CSessionConfig@@AEAAJPEBGK@Z`
- size: `982`
- prototype: `int(CSessionConfig *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18002c890`

## callees

- `0x180003f30`
- `0x18001a280`
- `0x18001ace4`
- `0x18002cd18`
- `0x18002cff0`
- `0x18002d8c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d337`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d337`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d08a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d166`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d08a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d166`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002d0e9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002d1c2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002d237`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002d2a6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002d0e9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002d1c2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002d237`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002d2a6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d13a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d396`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d13a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d396`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002d359`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002d359`
- `api-ms-win-core-shutdown-l1-1-0!InitiateSystemShutdownExW` at `0x18002d32d`
- `api-ms-win-core-shutdown-l1-1-0!InitiateSystemShutdownExW` at `0x18002d32d`

## string_xrefs

- `0x18002d36b`: `CSessionConfig::Reboot`
- `0x18002d0ad`: `RegOpenKeyEx failed failed: 0x%x in %s`
- `0x18002d120`: `IMAGE_STATE_COMPLETE`
- `0x18002d15c`: `System\CurrentControlSet\Control\Terminal Server\ConfigTasks`
- `0x18002d2fe`: `EnablePrivilege failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CSessionConfig::Reboot(CSessionConfig *this, WCHAR *a2)
{
  LSTATUS v3; // eax
  signed int v4; // ebx
  const char *v5; // rdx
  LSTATUS v6; // eax
  LSTATUS v7; // eax
  const unsigned __int16 *v8; // rdx
  CSessionConfig *v9; // rcx
  LSTATUS v10; // eax
  LSTATUS v11; // eax
  LSTATUS v12; // eax
  int v13; // eax
  signed int LastError; // eax
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  BYTE v18[4]; // [rsp+38h] [rbp-C8h] BYREF
  BYTE v19[4]; // [rsp+3Ch] [rbp-C4h] BYREF
  BYTE v20[4]; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t Data[256]; // [rsp+50h] [rbp-B0h] BYREF

  hKey = 0;
  Type = 0;
  cbData = 0;
  *(_DWORD *)v19 = 0;
  *(_DWORD *)v20 = 0;
  *(_DWORD *)v18 = 1;
  _DbgPrintMessage(1, "shutdown reason = 0x%08X\n", 0);
  v3 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Setup\\State",
         0,
         0x20019u,
         &hKey);
  v4 = v3;
  if ( (v3 & 0xFFFFFFFD) != 0 )
  {
    if ( v3 > 0 )
      v4 = (unsigned __int16)v3 | 0x80070000;
    if ( v4 < 0 )
      goto LABEL_5;
  }
  cbData = 512;
  v6 = RegQueryValueExW(hKey, L"ImageState", 0, &Type, (LPBYTE)Data, &cbData);
  v4 = v6;
  if ( v6 == 2 )
    goto LABEL_7;
  if ( v6 )
  {
    if ( v6 > 0 )
      v4 = (unsigned __int16)v6 | 0x80070000;
    if ( v4 < 0 )
    {
      v5 = "RegQueryValueEx ImageState failed failed: 0x%x in %s";
      goto LABEL_59;
    }
  }
  if ( Type != 1 || wcsicmp(Data, L"IMAGE_STATE_COMPLETE") )
    goto LABEL_7;
  RegCloseKey(hKey);
  hKey = 0;
  v7 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Control\\Terminal Server\\ConfigTasks",
         0,
         0x20019u,
         &hKey);
  v4 = v7;
  if ( v7 )
  {
    if ( v7 != 2 )
    {
      if ( v7 > 0 )
        v4 = (unsigned __int16)v7 | 0x80070000;
      if ( v4 < 0 )
      {
LABEL_5:
        v5 = "RegOpenKeyEx failed failed: 0x%x in %s";
LABEL_59:
        _DbgPrintMessage(8, v5, (unsigned int)v4, "CSessionConfig::Reboot");
        goto LABEL_60;
      }
    }
  }
  else
  {
    cbData = 4;
    v10 = RegQueryValueExW(hKey, L"AutoReboot", 0, &Type, v20, &cbData);
    v4 = v10;
    if ( v10 && v10 != 2 && v10 != 234 )
    {
      if ( v10 > 0 )
        v4 = (unsigned __int16)v10 | 0x80070000;
      if ( v4 < 0 )
      {
        v5 = "RegQueryValueEx AutoReboot failed failed: 0x%x in %s";
        goto LABEL_59;
      }
    }
    if ( Type != 4 )
      *(_DWORD *)v20 = 0;
    cbData = 4;
    v11 = RegQueryValueExW(hKey, L"Timeout", 0, &Type, v19, &cbData);
    v4 = v11;
    if ( v11 && v11 != 2 && v11 != 234 )
    {
      if ( v11 > 0 )
        v4 = (unsigned __int16)v11 | 0x80070000;
      if ( v4 < 0 )
      {
        v5 = "RegQueryValueEx Timeout failed failed: 0x%x in %s";
        goto LABEL_59;
      }
    }
    if ( Type != 4 )
      *(_DWORD *)v19 = 0;
    cbData = 4;
    v12 = RegQueryValueExW(hKey, L"ForceShutdown", 0, &Type, v18, &cbData);
    v4 = v12;
    if ( v12 && v12 != 2 && v12 != 234 )
    {
      if ( v12 > 0 )
        v4 = (unsigned __int16)v12 | 0x80070000;
      if ( v4 < 0 )
      {
        v5 = "RegQueryValueEx ForceShutdown failed failed: 0x%x in %s";
        goto LABEL_59;
      }
    }
    if ( Type != 4 )
      *(_DWORD *)v18 = 1;
  }
  if ( !*(_DWORD *)v20 )
  {
LABEL_7:
    v4 = 0;
  }
  else
  {
    v13 = CSessionConfig::EnablePrivilege(v9, v8);
    v4 = v13;
    if ( v13 >= 0 )
    {
      while ( !InitiateSystemShutdownExW(0, a2, *(DWORD *)v19, *(_DWORD *)v18 == 1, 1, 0) )
      {
        LastError = GetLastError();
        if ( LastError != 21 )
        {
          v4 = LastError > 0 ? (unsigned __int16)LastError | 0x80070000 : LastError;
          if ( v4 < 0 )
          {
            v5 = "InitiateSystemShutdownEx failed: 0x%x in %s";
            goto LABEL_59;
          }
        }
        Sleep(0x64u);
      }
    }
    else
    {
      _DbgPrintMessage(8, "EnablePrivilege failed: 0x%x in %s", (unsigned int)v13, "CSessionConfig::Reboot");
    }
  }
LABEL_60:
  TraceLoggingWriteRebootEvent(v4, *(unsigned int *)v20, *(unsigned int *)v19, *(unsigned int *)v18);
  RegCloseKey(hKey);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18002cff0  mov     [rsp-8+arg_0], rbx
0x18002cff5  mov     [rsp-8+arg_10], rdi
0x18002cffa  push    rbp
0x18002cffb  push    r12
0x18002cffd  push    r15
0x18002cfff  lea     rbp, [rsp-160h]
0x18002d007  sub     rsp, 260h
0x18002d00e  mov     rax, cs:__security_cookie
0x18002d015  xor     rax, rsp
0x18002d018  mov     [rbp+170h+var_20], rax
0x18002d01f  xor     r8d, r8d
0x18002d022  mov     [rsp+270h+hKey], 0
0x18002d02b  mov     rdi, rdx
0x18002d02e  mov     [rsp+270h+Type], 0
0x18002d036  lea     rdx, aShutdownReason; "shutdown reason = 0x%08X\n"
0x18002d03d  mov     [rsp+270h+cbData], 0
0x18002d045  mov     dword ptr [rsp+270h+var_234], 0
0x18002d04d  lea     ecx, [r8+1]; int
0x18002d051  mov     dword ptr [rsp+270h+var_230], 0
0x18002d059  mov     dword ptr [rsp+270h+var_238], 1
0x18002d061  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002d066  lea     rax, [rsp+270h+hKey]
0x18002d06b  mov     r12, 0FFFFFFFF80000002h
0x18002d072  mov     rcx, r12; hKey
0x18002d075  mov     [rsp+270h+phkResult], rax; phkResult
0x18002d07a  mov     r9d, 20019h; samDesired
0x18002d080  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18002d087  xor     r8d, r8d; ulOptions
0x18002d08a  call    cs:__imp_RegOpenKeyExW
0x18002d090  mov     ebx, eax
0x18002d092  mov     r15d, 80070000h
0x18002d098  test    eax, 0FFFFFFFDh
0x18002d09d  jz      short loc_18002D0B9
0x18002d09f  test    eax, eax
0x18002d0a1  jle     short loc_18002D0A9
0x18002d0a3  movzx   ebx, ax
0x18002d0a6  or      ebx, r15d
0x18002d0a9  test    ebx, ebx
0x18002d0ab  jns     short loc_18002D0B9
0x18002d0ad  lea     rdx, aRegopenkeyexFa_0; "RegOpenKeyEx failed failed: 0x%x in %s"
0x18002d0b4  jmp     loc_18002D368
0x18002d0b9  mov     rcx, [rsp+270h+hKey]; hKey
0x18002d0be  lea     rax, [rsp+270h+cbData]
0x18002d0c3  mov     [rsp+270h+lpcbData], rax; lpcbData
0x18002d0c8  lea     r9, [rsp+270h+Type]; lpType
0x18002d0cd  lea     rax, [rsp+270h+Data]
0x18002d0d2  mov     [rsp+270h+cbData], 200h
0x18002d0da  xor     r8d, r8d; lpReserved
0x18002d0dd  mov     [rsp+270h+phkResult], rax; lpData
0x18002d0e2  lea     rdx, aImagestate; "ImageState"
0x18002d0e9  call    cs:__imp_RegQueryValueExW
0x18002d0ef  mov     ebx, eax
0x18002d0f1  cmp     eax, 2
0x18002d0f4  jnz     short loc_18002D0FD
0x18002d0f6  xor     ebx, ebx
0x18002d0f8  jmp     loc_18002D37C
0x18002d0fd  test    eax, eax
0x18002d0ff  jz      short loc_18002D119
0x18002d101  jle     short loc_18002D109
0x18002d103  movzx   ebx, ax
0x18002d106  or      ebx, r15d
0x18002d109  test    ebx, ebx
0x18002d10b  jns     short loc_18002D119
0x18002d10d  lea     rdx, aRegqueryvaluee_0; "RegQueryValueEx ImageState failed faile"...
0x18002d114  jmp     loc_18002D368
0x18002d119  cmp     [rsp+270h+Type], 1
0x18002d11e  jnz     short loc_18002D0F6
0x18002d120  lea     rdx, aImageStateComp; "IMAGE_STATE_COMPLETE"
0x18002d127  lea     rcx, [rsp+270h+Data]; String1
0x18002d12c  call    _wcsicmp
0x18002d131  test    eax, eax
0x18002d133  jnz     short loc_18002D0F6
0x18002d135  mov     rcx, [rsp+270h+hKey]; hKey
0x18002d13a  call    cs:__imp_RegCloseKey
0x18002d140  lea     rax, [rsp+270h+hKey]
0x18002d145  mov     [rsp+270h+hKey], 0
0x18002d14e  mov     r9d, 20019h; samDesired
0x18002d154  mov     [rsp+270h+phkResult], rax; phkResult
0x18002d159  xor     r8d, r8d; ulOptions
0x18002d15c  lea     rdx, aSystemCurrentc_3; "System\\CurrentControlSet\\Control\\Ter"...
0x18002d163  mov     rcx, r12; hKey
0x18002d166  call    cs:__imp_RegOpenKeyExW
0x18002d16c  mov     ebx, eax
0x18002d16e  test    eax, eax
0x18002d170  jz      short loc_18002D192
0x18002d172  cmp     eax, 2
0x18002d175  jz      loc_18002D2E5
0x18002d17b  test    eax, eax
0x18002d17d  jle     short loc_18002D185
0x18002d17f  movzx   ebx, ax
0x18002d182  or      ebx, r15d
0x18002d185  test    ebx, ebx
0x18002d187  jns     loc_18002D2E5
0x18002d18d  jmp     loc_18002D0AD
0x18002d192  mov     rcx, [rsp+270h+hKey]; hKey
0x18002d197  lea     rax, [rsp+270h+cbData]
0x18002d19c  mov     [rsp+270h+lpcbData], rax; lpcbData
0x18002d1a1  lea     r9, [rsp+270h+Type]; lpType
0x18002d1a6  lea     rax, [rsp+270h+var_230]
0x18002d1ab  mov     [rsp+270h+cbData], 4
0x18002d1b3  xor     r8d, r8d; lpReserved
0x18002d1b6  mov     [rsp+270h+phkResult], rax; lpData
0x18002d1bb  lea     rdx, aAutoreboot; "AutoReboot"
0x18002d1c2  call    cs:__imp_RegQueryValueExW
0x18002d1c8  mov     ebx, eax
0x18002d1ca  mov     r12d, 0EAh
0x18002d1d0  test    eax, eax
0x18002d1d2  jz      short loc_18002D1F8
0x18002d1d4  cmp     eax, 2
0x18002d1d7  jz      short loc_18002D1F8
0x18002d1d9  cmp     eax, r12d
0x18002d1dc  jz      short loc_18002D1F8
0x18002d1de  test    eax, eax
0x18002d1e0  jle     short loc_18002D1E8
0x18002d1e2  movzx   ebx, ax
0x18002d1e5  or      ebx, r15d
0x18002d1e8  test    ebx, ebx
0x18002d1ea  jns     short loc_18002D1F8
0x18002d1ec  lea     rdx, aRegqueryvaluee_2; "RegQueryValueEx AutoReboot failed faile"...
0x18002d1f3  jmp     loc_18002D368
0x18002d1f8  cmp     [rsp+270h+Type], 4
0x18002d1fd  jz      short loc_18002D207
0x18002d1ff  mov     dword ptr [rsp+270h+var_230], 0
0x18002d207  mov     rcx, [rsp+270h+hKey]; hKey
0x18002d20c  lea     rax, [rsp+270h+cbData]
0x18002d211  mov     [rsp+270h+lpcbData], rax; lpcbData
0x18002d216  lea     r9, [rsp+270h+Type]; lpType
0x18002d21b  lea     rax, [rsp+270h+var_234]
0x18002d220  mov     [rsp+270h+cbData], 4
0x18002d228  xor     r8d, r8d; lpReserved
0x18002d22b  mov     [rsp+270h+phkResult], rax; lpData
0x18002d230  lea     rdx, aTimeout; "Timeout"
0x18002d237  call    cs:__imp_RegQueryValueExW
0x18002d23d  mov     ebx, eax
0x18002d23f  test    eax, eax
0x18002d241  jz      short loc_18002D267
0x18002d243  cmp     eax, 2
0x18002d246  jz      short loc_18002D267
0x18002d248  cmp     eax, r12d
0x18002d24b  jz      short loc_18002D267
0x18002d24d  test    eax, eax
0x18002d24f  jle     short loc_18002D257
0x18002d251  movzx   ebx, ax
0x18002d254  or      ebx, r15d
0x18002d257  test    ebx, ebx
0x18002d259  jns     short loc_18002D267
0x18002d25b  lea     rdx, aRegqueryvaluee_11; "RegQueryValueEx Timeout failed failed: "...
0x18002d262  jmp     loc_18002D368
0x18002d267  cmp     [rsp+270h+Type], 4
0x18002d26c  jz      short loc_18002D276
0x18002d26e  mov     dword ptr [rsp+270h+var_234], 0
0x18002d276  mov     rcx, [rsp+270h+hKey]; hKey
0x18002d27b  lea     rax, [rsp+270h+cbData]
0x18002d280  mov     [rsp+270h+lpcbData], rax; lpcbData
0x18002d285  lea     r9, [rsp+270h+Type]; lpType
0x18002d28a  lea     rax, [rsp+270h+var_238]
0x18002d28f  mov     [rsp+270h+cbData], 4
0x18002d297  xor     r8d, r8d; lpReserved
0x18002d29a  mov     [rsp+270h+phkResult], rax; lpData
0x18002d29f  lea     rdx, aForceshutdown; "ForceShutdown"
0x18002d2a6  call    cs:__imp_RegQueryValueExW
0x18002d2ac  mov     ebx, eax
0x18002d2ae  test    eax, eax
0x18002d2b0  jz      short loc_18002D2D6
0x18002d2b2  cmp     eax, 2
0x18002d2b5  jz      short loc_18002D2D6
0x18002d2b7  cmp     eax, r12d
0x18002d2ba  jz      short loc_18002D2D6
0x18002d2bc  test    eax, eax
0x18002d2be  jle     short loc_18002D2C6
0x18002d2c0  movzx   ebx, ax
0x18002d2c3  or      ebx, r15d
0x18002d2c6  test    ebx, ebx
0x18002d2c8  jns     short loc_18002D2D6
0x18002d2ca  lea     rdx, aRegqueryvaluee; "RegQueryValueEx ForceShutdown failed fa"...
0x18002d2d1  jmp     loc_18002D368
0x18002d2d6  cmp     [rsp+270h+Type], 4
0x18002d2db  jz      short loc_18002D2E5
0x18002d2dd  mov     dword ptr [rsp+270h+var_238], 1
0x18002d2e5  cmp     dword ptr [rsp+270h+var_230], 0
0x18002d2ea  jz      loc_18002D0F6
0x18002d2f0  call    ?EnablePrivilege@CSessionConfig@@AEAAJPEBG@Z; CSessionConfig::EnablePrivilege(ushort const *)
0x18002d2f5  mov     ebx, eax
0x18002d2f7  test    eax, eax
0x18002d2f9  jns     short loc_18002D307
0x18002d2fb  mov     r8d, eax
0x18002d2fe  lea     rdx, aEnableprivileg; "EnablePrivilege failed: 0x%x in %s"
0x18002d305  jmp     short loc_18002D36B
0x18002d307  mov     r8d, dword ptr [rsp+270h+var_234]; dwTimeout
0x18002d30c  xor     r9d, r9d
0x18002d30f  cmp     dword ptr [rsp+270h+var_238], 1
0x18002d314  mov     rdx, rdi; lpMessage
0x18002d317  mov     dword ptr [rsp+270h+lpcbData], 0; dwReason
0x18002d31f  setz    r9b; bForceAppsClosed
0x18002d323  mov     dword ptr [rsp+270h+phkResult], 1; bRebootAfterShutdown
0x18002d32b  xor     ecx, ecx; lpMachineName
0x18002d32d  call    cs:__imp_InitiateSystemShutdownExW
0x18002d333  test    eax, eax
0x18002d335  jnz     short loc_18002D37C
0x18002d337  call    cs:__imp_GetLastError
0x18002d33d  cmp     eax, 15h
0x18002d340  jz      short loc_18002D354
0x18002d342  test    eax, eax
0x18002d344  jg      short loc_18002D34A
0x18002d346  mov     ebx, eax
0x18002d348  jmp     short loc_18002D350
0x18002d34a  movzx   ebx, ax
0x18002d34d  or      ebx, r15d
0x18002d350  test    ebx, ebx
0x18002d352  js      short loc_18002D361
0x18002d354  mov     ecx, 64h ; 'd'; dwMilliseconds
0x18002d359  call    cs:__imp_Sleep
0x18002d35f  jmp     short loc_18002D307
0x18002d361  lea     rdx, aInitiatesystem_0; "InitiateSystemShutdownEx failed: 0x%x i"...
0x18002d368  mov     r8d, ebx
0x18002d36b  lea     r9, aCsessionconfig_1; "CSessionConfig::Reboot"
0x18002d372  mov     ecx, 8; int
0x18002d377  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002d37c  mov     r9d, dword ptr [rsp+270h+var_238]; unsigned int
0x18002d381  mov     ecx, ebx; unsigned int
0x18002d383  mov     r8d, dword ptr [rsp+270h+var_234]; unsigned int
0x18002d388  mov     edx, dword ptr [rsp+270h+var_230]; unsigned int
0x18002d38c  call    ?TraceLoggingWriteRebootEvent@@YAXKKKK@Z; TraceLoggingWriteRebootEvent(ulong,ulong,ulong,ulong)
0x18002d391  mov     rcx, [rsp+270h+hKey]; hKey
0x18002d396  call    cs:__imp_RegCloseKey
0x18002d39c  mov     eax, ebx
0x18002d39e  mov     rcx, [rbp+170h+var_20]
0x18002d3a5  xor     rcx, rsp; StackCookie
0x18002d3a8  call    __security_check_cookie
0x18002d3ad  lea     r11, [rsp+270h+var_10]
0x18002d3b5  mov     rbx, [r11+20h]
0x18002d3b9  mov     rdi, [r11+30h]
0x18002d3bd  mov     rsp, r11
0x18002d3c0  pop     r15
0x18002d3c2  pop     r12
0x18002d3c4  pop     rbp
0x18002d3c5  retn
```
