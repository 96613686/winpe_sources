# WTSSetListenerSecurityW

- ea: `0x18000b3e0`
- end: `0x18000b541`
- name: `WTSSetListenerSecurityW`
- size: `353`
- prototype: `BOOL __stdcall(HANDLE hServer, PVOID pReserved, DWORD Reserved, LPWSTR pListenerName, SECURITY_INFORMATION SecurityInformation, PSECURITY_DESCRIPTOR pSecurityDescriptor)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000b330`

## callees

- `0x18000b3e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b514`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b530`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b514`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b530`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b4a1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b4c8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b4a1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b4c8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000b508`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000b508`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b4d4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b51e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b4d4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b51e`
- `REGAPI!RegWinStationSetSecurityW` at `0x18000b46c`
- `REGAPI!RegWinStationSetSecurityW` at `0x18000b46c`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18000b448`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18000b448`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18000b4e5`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18000b4e5`

## string_xrefs

- `0x18000b4ef`: `Security`

## pseudocode

```c
BOOL __stdcall WTSSetListenerSecurityW(
        HANDLE hServer,
        PVOID pReserved,
        DWORD Reserved,
        LPWSTR pListenerName,
        SECURITY_INFORMATION SecurityInformation,
        PSECURITY_DESCRIPTOR pSecurityDescriptor)
{
  BOOL v6; // ebx
  PSECURITY_DESCRIPTOR v8; // rdi
  DWORD v9; // eax
  DWORD v10; // ecx
  LSTATUS v11; // esi
  DWORD cbData; // eax
  LSTATUS v13; // eax
  DWORD dwRevision; // [rsp+30h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-20h] BYREF
  HKEY phkResult; // [rsp+40h] [rbp-18h] BYREF
  WORD pControl; // [rsp+80h] [rbp+28h] BYREF

  v6 = 0;
  pControl = 0;
  dwRevision = 0;
  phkResult = 0;
  hKey = 0;
  if ( __PAIR128__((unsigned __int64)hServer, (unsigned __int64)pReserved) != 0
    || Reserved
    || !pListenerName
    || SecurityInformation != 12
    || (v8 = pSecurityDescriptor) == 0 )
  {
    v10 = 87;
    goto LABEL_18;
  }
  if ( GetSecurityDescriptorControl(pSecurityDescriptor, &pControl, &dwRevision) )
  {
    if ( (pControl & 0x8000u) == 0 )
    {
      v9 = RegWinStationSetSecurityW(0, pListenerName, v8, 0);
      if ( v9 )
      {
        v10 = v9;
LABEL_18:
        SetLastError(v10);
        return v6;
      }
      return 1;
    }
    if ( !RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"System\\CurrentControlSet\\Control\\Terminal Server\\WinStations",
            0,
            0x20006u,
            &hKey) )
    {
      v11 = RegOpenKeyExW(hKey, pListenerName, 0, 0x20006u, &phkResult);
      RegCloseKey(hKey);
      if ( v11 )
      {
        v10 = v11;
        goto LABEL_18;
      }
      cbData = GetSecurityDescriptorLength(v8);
      v13 = RegSetValueExW(phkResult, L"Security", 0, 3u, (const BYTE *)v8, cbData);
      if ( v13 )
        SetLastError(v13);
      RegCloseKey(phkResult);
      return 1;
    }
  }
  return v6;
}

```

## disassembly

```asm
0x18000b3e0  push    rbp
0x18000b3e2  push    rbx
0x18000b3e3  push    rsi
0x18000b3e4  push    rdi
0x18000b3e5  mov     rbp, rsp
0x18000b3e8  sub     rsp, 58h
0x18000b3ec  xor     eax, eax
0x18000b3ee  xor     ebx, ebx
0x18000b3f0  mov     [rbp+pControl], ax
0x18000b3f4  mov     rsi, r9
0x18000b3f7  mov     [rbp+dwRevision], eax
0x18000b3fa  mov     [rbp+var_18], rax
0x18000b3fe  mov     [rbp+hKey], rax
0x18000b402  test    rcx, rcx
0x18000b405  jnz     loc_18000B52B
0x18000b40b  test    rdx, rdx
0x18000b40e  jnz     loc_18000B52B
0x18000b414  test    r8d, r8d
0x18000b417  jnz     loc_18000B52B
0x18000b41d  test    r9, r9
0x18000b420  jz      loc_18000B52B
0x18000b426  cmp     [rbp+SecurityInformation], 0Ch
0x18000b42a  jnz     loc_18000B52B
0x18000b430  mov     rdi, [rbp+pSecurityDescriptor]
0x18000b434  test    rdi, rdi
0x18000b437  jz      loc_18000B52B
0x18000b43d  lea     r8, [rbp+dwRevision]; lpdwRevision
0x18000b441  mov     rcx, rdi; pSecurityDescriptor
0x18000b444  lea     rdx, [rbp+pControl]; pControl
0x18000b448  call    cs:__imp_GetSecurityDescriptorControl
0x18000b44e  test    eax, eax
0x18000b450  jz      loc_18000B536
0x18000b456  mov     eax, 8000h
0x18000b45b  test    [rbp+pControl], ax
0x18000b45f  jnz     short loc_18000B481
0x18000b461  xor     r9d, r9d
0x18000b464  mov     r8, rdi
0x18000b467  mov     rdx, rsi
0x18000b46a  xor     ecx, ecx
0x18000b46c  call    cs:__imp_RegWinStationSetSecurityW
0x18000b472  test    eax, eax
0x18000b474  jz      loc_18000B524
0x18000b47a  mov     ecx, eax
0x18000b47c  jmp     loc_18000B530
0x18000b481  lea     rax, [rbp+hKey]
0x18000b485  mov     r9d, 20006h; samDesired
0x18000b48b  xor     r8d, r8d; ulOptions
0x18000b48e  mov     [rsp+58h+phkResult], rax; phkResult
0x18000b493  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\Ter"...
0x18000b49a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000b4a1  call    cs:__imp_RegOpenKeyExW
0x18000b4a7  test    eax, eax
0x18000b4a9  jnz     loc_18000B536
0x18000b4af  mov     rcx, [rbp+hKey]; hKey
0x18000b4b3  lea     rax, [rbp+var_18]
0x18000b4b7  mov     r9d, 20006h; samDesired
0x18000b4bd  mov     [rsp+58h+phkResult], rax; phkResult
0x18000b4c2  xor     r8d, r8d; ulOptions
0x18000b4c5  mov     rdx, rsi; lpSubKey
0x18000b4c8  call    cs:__imp_RegOpenKeyExW
0x18000b4ce  mov     rcx, [rbp+hKey]; hKey
0x18000b4d2  mov     esi, eax
0x18000b4d4  call    cs:__imp_RegCloseKey
0x18000b4da  test    esi, esi
0x18000b4dc  jz      short loc_18000B4E2
0x18000b4de  mov     ecx, esi
0x18000b4e0  jmp     short loc_18000B530
0x18000b4e2  mov     rcx, rdi; pSecurityDescriptor
0x18000b4e5  call    cs:__imp_GetSecurityDescriptorLength
0x18000b4eb  mov     rcx, [rbp+var_18]; hKey
0x18000b4ef  lea     rdx, ValueName; "Security"
0x18000b4f6  mov     [rsp+58h+cbData], eax; cbData
0x18000b4fa  mov     r9d, 3; dwType
0x18000b500  xor     r8d, r8d; Reserved
0x18000b503  mov     [rsp+58h+phkResult], rdi; lpData
0x18000b508  call    cs:__imp_RegSetValueExW
0x18000b50e  test    eax, eax
0x18000b510  jz      short loc_18000B51A
0x18000b512  mov     ecx, eax; dwErrCode
0x18000b514  call    cs:__imp_SetLastError
0x18000b51a  mov     rcx, [rbp+var_18]; hKey
0x18000b51e  call    cs:__imp_RegCloseKey
0x18000b524  mov     ebx, 1
0x18000b529  jmp     short loc_18000B536
0x18000b52b  mov     ecx, 57h ; 'W'; dwErrCode
0x18000b530  call    cs:__imp_SetLastError
0x18000b536  mov     eax, ebx
0x18000b538  add     rsp, 58h
0x18000b53c  pop     rdi
0x18000b53d  pop     rsi
0x18000b53e  pop     rbx
0x18000b53f  pop     rbp
0x18000b540  retn
```
