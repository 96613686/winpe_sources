# UmpoImportScheme

- ea: `0x180012254`
- end: `0x180012576`
- name: `UmpoImportScheme`
- size: `802`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180014ad0`

## callees

- `0x180003370`
- `0x180003560`
- `0x18000abb0`
- `0x18000f3dc`
- `0x180010070`
- `0x180011c1c`
- `0x180012254`
- `0x18001257c`
- `0x180012864`
- `0x180013984`
- `0x180013df8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800124a2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800124a2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001232c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180012435`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001232c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180012435`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800123e3`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800124dc`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800123e3`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800124dc`
- `api-ms-win-core-registry-l1-1-0!RegLoadAppKeyW` at `0x180012393`
- `api-ms-win-core-registry-l1-1-0!RegLoadAppKeyW` at `0x180012393`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001248b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800124c0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012543`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001248b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800124c0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012543`

## pseudocode

```c
__int64 __fastcall UmpoImportScheme(__int64 a1, __int64 a2)
{
  LSTATUS v4; // ebx
  char v5; // r14
  char v6; // r15
  HKEY v7; // rdx
  HKEY v9; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v10; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v11; // [rsp+5Ch] [rbp-A4h] BYREF
  HKEY v12; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp-90h] BYREF
  WCHAR SubKey[40]; // [rsp+80h] [rbp-80h] BYREF
  wchar_t pszDest[264]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR File[264]; // [rsp+2E0h] [rbp+1E0h] BYREF

  v10 = 0;
  phkResult = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  v11 = 0;
  v12 = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  v9 = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  if ( UmpoFullPowerPlanSupportDisabled )
  {
    v4 = 50;
  }
  else
  {
    v5 = 0;
    v6 = 0;
    v4 = UmpoInternalOpenUserPowerKey(&hKey, 0x20006u);
    if ( !v4 )
    {
      UmpoInternalConvertGuidToStringBuffer(a2, SubKey);
      v4 = RegCreateKeyExW(hKey, SubKey, 0, 0, 0, 0x2001Fu, 0, &phkResult, 0);
      if ( !v4 )
      {
        UmpoInternalSetPrivilegeAttribute(18, 2, &v11);
        UmpoInternalSetPrivilegeAttribute(17, 2, &v10);
        v5 = 1;
        v4 = UmpoCopyToTemp(a1, File);
        if ( !v4 )
        {
          v6 = 1;
          v4 = RegLoadAppKeyW(File, &v12, 0x20019u, 0, 0);
          if ( !v4 )
          {
            v4 = StringCchPrintfW(
                   pszDest,
                   0x104u,
                   L"%s\\%s",
                   L"System\\CurrentControlSet\\Control\\Power\\PowerSettings\\StagingImport",
                   SubKey);
            if ( v4 >= 0 )
            {
              v4 = RegDeleteKeyExW(HKEY_LOCAL_MACHINE, pszDest, 0, 0);
              if ( (v4 & 0xFFFFFFFD) != 0 )
              {
                MicrosoftTelemetryAssertTriggeredNoArgs();
              }
              else
              {
                v4 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, pszDest, 0, 0, 0, 0x2001Fu, 0, &v9, 0);
                if ( !v4 )
                {
                  v7 = v9;
                  if ( v9 == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
                  {
                    MicrosoftTelemetryAssertTriggeredNoArgs();
                    v7 = v9;
                  }
                  v4 = UmpoInternalSanitizeSchemeImport(v12, v7, 0);
                  if ( !v4 )
                    v4 = UmpoInternalSanitizeSchemeImport(v9, phkResult, 0);
                }
              }
            }
          }
        }
      }
    }
    if ( (unsigned __int64)v12 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      RegCloseKey(v12);
      v12 = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
    }
    if ( v9 != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    {
      if ( RegDeleteTreeW(v9, 0) )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      if ( (unsigned __int64)v9 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        RegCloseKey(v9);
        v9 = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
      }
      if ( RegDeleteKeyExW(HKEY_LOCAL_MACHINE, pszDest, 0, 0) )
        MicrosoftTelemetryAssertTriggeredNoArgs();
    }
    if ( v6 && (unsigned int)UmpoImportTempDirectoryCleanup(File) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( v5 )
    {
      UmpoInternalSetPrivilegeAttribute(17, v10, 0);
      UmpoInternalSetPrivilegeAttribute(18, v11, 0);
    }
  }
  UmpoInternalCloseUserPowerKey(hKey);
  if ( (unsigned __int64)phkResult - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    RegCloseKey(phkResult);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180012254  mov     [rsp-8+arg_10], rbx
0x180012259  mov     [rsp-8+arg_18], rsi
0x18001225e  push    rbp
0x18001225f  push    rdi
0x180012260  push    r13
0x180012262  push    r14
0x180012264  push    r15
0x180012266  lea     rbp, [rsp-400h]
0x18001226e  sub     rsp, 500h
0x180012275  mov     rax, cs:__security_cookie
0x18001227c  xor     rax, rsp
0x18001227f  mov     [rbp+420h+var_30], rax
0x180012286  or      r13, 0FFFFFFFFFFFFFFFFh
0x18001228a  mov     [rsp+520h+var_4C8], 0
0x180012292  cmp     cs:UmpoFullPowerPlanSupportDisabled, 0
0x180012299  mov     rdi, rdx
0x18001229c  mov     rsi, rcx
0x18001229f  mov     [rsp+520h+var_4B0], r13
0x1800122a4  mov     [rsp+520h+var_4C4], 0
0x1800122ac  mov     [rsp+520h+var_4C0], r13
0x1800122b1  mov     [rsp+520h+var_4D0], r13
0x1800122b6  mov     [rsp+520h+hKey], r13
0x1800122bb  jz      short loc_1800122C6
0x1800122bd  lea     ebx, [r13+33h]
0x1800122c1  jmp     loc_18001252A
0x1800122c6  xor     r8d, r8d
0x1800122c9  lea     rcx, [rsp+520h+hKey]; phkResult
0x1800122ce  mov     edx, 20006h; samDesired
0x1800122d3  xor     r14b, r14b
0x1800122d6  xor     r15b, r15b
0x1800122d9  call    UmpoInternalOpenUserPowerKey
0x1800122de  mov     ebx, eax
0x1800122e0  test    eax, eax
0x1800122e2  jnz     loc_18001247C
0x1800122e8  lea     rdx, [rbp+420h+SubKey]
0x1800122ec  mov     rcx, rdi
0x1800122ef  call    UmpoInternalConvertGuidToStringBuffer
0x1800122f4  mov     rcx, [rsp+520h+hKey]; hKey
0x1800122f9  lea     rax, [rsp+520h+var_4B0]
0x1800122fe  mov     [rsp+520h+lpdwDisposition], 0; lpdwDisposition
0x180012307  lea     rdx, [rbp+420h+SubKey]; lpSubKey
0x18001230b  mov     [rsp+520h+phkResult], rax; phkResult
0x180012310  mov     edi, 2001Fh
0x180012315  mov     [rsp+520h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18001231e  xor     r9d, r9d; lpClass
0x180012321  mov     [rsp+520h+samDesired], edi; samDesired
0x180012325  xor     r8d, r8d; Reserved
0x180012328  mov     [rsp+520h+dwOptions], ebx; dwOptions
0x18001232c  call    cs:__imp_RegCreateKeyExW
0x180012332  mov     ebx, eax
0x180012334  test    eax, eax
0x180012336  jnz     loc_18001247C
0x18001233c  lea     ebx, [rax+2]
0x18001233f  mov     edx, ebx
0x180012341  lea     r8, [rsp+520h+var_4C4]
0x180012346  lea     ecx, [rax+12h]
0x180012349  call    UmpoInternalSetPrivilegeAttribute
0x18001234e  lea     r8, [rsp+520h+var_4C8]
0x180012353  mov     edx, ebx
0x180012355  lea     ecx, [rbx+0Fh]
0x180012358  call    UmpoInternalSetPrivilegeAttribute
0x18001235d  lea     rdx, [rbp+420h+File]
0x180012364  mov     rcx, rsi
0x180012367  mov     r14b, 1
0x18001236a  call    UmpoCopyToTemp
0x18001236f  mov     ebx, eax
0x180012371  test    eax, eax
0x180012373  jnz     loc_18001247C
0x180012379  xor     r9d, r9d; dwOptions
0x18001237c  mov     [rsp+520h+dwOptions], eax; Reserved
0x180012380  lea     r8d, [rdi-6]; samDesired
0x180012384  mov     r15b, r14b
0x180012387  lea     rdx, [rsp+520h+var_4C0]; phkResult
0x18001238c  lea     rcx, [rbp+420h+File]; lpFile
0x180012393  call    cs:__imp_RegLoadAppKeyW
0x180012399  mov     ebx, eax
0x18001239b  test    eax, eax
0x18001239d  jnz     loc_18001247C
0x1800123a3  lea     rax, [rbp+420h+SubKey]
0x1800123a7  mov     edx, 104h; cchDest
0x1800123ac  lea     r9, aSystemCurrentc_5; "System\\CurrentControlSet\\Control\\Pow"...
0x1800123b3  mov     qword ptr [rsp+520h+dwOptions], rax
0x1800123b8  lea     r8, aSS; "%s\\%s"
0x1800123bf  lea     rcx, [rbp+420h+pszDest]; pszDest
0x1800123c3  call    StringCchPrintfW
0x1800123c8  mov     ebx, eax
0x1800123ca  test    eax, eax
0x1800123cc  js      loc_18001247C
0x1800123d2  xor     r9d, r9d; Reserved
0x1800123d5  lea     rdx, [rbp+420h+pszDest]; lpSubKey
0x1800123d9  xor     r8d, r8d; samDesired
0x1800123dc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800123e3  call    cs:__imp_RegDeleteKeyExW
0x1800123e9  mov     ebx, eax
0x1800123eb  test    eax, 0FFFFFFFDh
0x1800123f0  jz      short loc_1800123FC
0x1800123f2  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800123f7  jmp     loc_18001247C
0x1800123fc  mov     [rsp+520h+lpdwDisposition], 0; lpdwDisposition
0x180012405  lea     rax, [rsp+520h+var_4D0]
0x18001240a  mov     [rsp+520h+phkResult], rax; phkResult
0x18001240f  lea     rdx, [rbp+420h+pszDest]; lpSubKey
0x180012413  mov     [rsp+520h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18001241c  xor     r9d, r9d; lpClass
0x18001241f  mov     [rsp+520h+samDesired], edi; samDesired
0x180012423  xor     r8d, r8d; Reserved
0x180012426  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001242d  mov     [rsp+520h+dwOptions], 0; dwOptions
0x180012435  call    cs:__imp_RegCreateKeyExW
0x18001243b  mov     ebx, eax
0x18001243d  test    eax, eax
0x18001243f  jnz     short loc_18001247C
0x180012441  mov     rdx, [rsp+520h+var_4D0]
0x180012446  cmp     rdx, r13
0x180012449  jnz     short loc_180012455
0x18001244b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180012450  mov     rdx, [rsp+520h+var_4D0]
0x180012455  mov     rcx, [rsp+520h+var_4C0]
0x18001245a  xor     r8d, r8d
0x18001245d  call    UmpoInternalSanitizeSchemeImport
0x180012462  mov     ebx, eax
0x180012464  test    eax, eax
0x180012466  jnz     short loc_18001247C
0x180012468  mov     rdx, [rsp+520h+var_4B0]
0x18001246d  xor     r8d, r8d
0x180012470  mov     rcx, [rsp+520h+var_4D0]
0x180012475  call    UmpoInternalSanitizeSchemeImport
0x18001247a  mov     ebx, eax
0x18001247c  mov     rcx, [rsp+520h+var_4C0]; hKey
0x180012481  lea     rax, [rcx-1]
0x180012485  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180012489  ja      short loc_180012496
0x18001248b  call    cs:__imp_RegCloseKey
0x180012491  mov     [rsp+520h+var_4C0], r13
0x180012496  mov     rcx, [rsp+520h+var_4D0]; hKey
0x18001249b  cmp     rcx, r13
0x18001249e  jz      short loc_1800124EB
0x1800124a0  xor     edx, edx; lpSubKey
0x1800124a2  call    cs:__imp_RegDeleteTreeW
0x1800124a8  test    eax, eax
0x1800124aa  jz      short loc_1800124B1
0x1800124ac  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800124b1  mov     rcx, [rsp+520h+var_4D0]; hKey
0x1800124b6  lea     rax, [rcx-1]
0x1800124ba  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800124be  ja      short loc_1800124CB
0x1800124c0  call    cs:__imp_RegCloseKey
0x1800124c6  mov     [rsp+520h+var_4D0], r13
0x1800124cb  xor     r9d, r9d; Reserved
0x1800124ce  lea     rdx, [rbp+420h+pszDest]; lpSubKey
0x1800124d2  xor     r8d, r8d; samDesired
0x1800124d5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800124dc  call    cs:__imp_RegDeleteKeyExW
0x1800124e2  test    eax, eax
0x1800124e4  jz      short loc_1800124EB
0x1800124e6  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800124eb  test    r15b, r15b
0x1800124ee  jz      short loc_180012505
0x1800124f0  lea     rcx, [rbp+420h+File]; pszSrc
0x1800124f7  call    UmpoImportTempDirectoryCleanup
0x1800124fc  test    eax, eax
0x1800124fe  jz      short loc_180012505
0x180012500  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180012505  test    r14b, r14b
0x180012508  jz      short loc_18001252A
0x18001250a  mov     edx, [rsp+520h+var_4C8]
0x18001250e  xor     r8d, r8d
0x180012511  lea     ecx, [r8+11h]
0x180012515  call    UmpoInternalSetPrivilegeAttribute
0x18001251a  mov     edx, [rsp+520h+var_4C4]
0x18001251e  xor     r8d, r8d
0x180012521  lea     ecx, [r8+12h]
0x180012525  call    UmpoInternalSetPrivilegeAttribute
0x18001252a  mov     rcx, [rsp+520h+hKey]
0x18001252f  call    UmpoInternalCloseUserPowerKey
0x180012534  mov     rcx, [rsp+520h+var_4B0]; hKey
0x180012539  lea     rax, [rcx-1]
0x18001253d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180012541  ja      short loc_180012549
0x180012543  call    cs:__imp_RegCloseKey
0x180012549  mov     eax, ebx
0x18001254b  mov     rcx, [rbp+420h+var_30]
0x180012552  xor     rcx, rsp; StackCookie
0x180012555  call    __security_check_cookie
0x18001255a  lea     r11, [rsp+520h+var_20]
0x180012562  mov     rbx, [r11+40h]
0x180012566  mov     rsi, [r11+48h]
0x18001256a  mov     rsp, r11
0x18001256d  pop     r15
0x18001256f  pop     r14
0x180012571  pop     r13
0x180012573  pop     rdi
0x180012574  pop     rbp
0x180012575  retn
```
