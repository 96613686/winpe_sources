# WTSGetListenerSecurityW

- ea: `0x18000b030`
- end: `0x18000b21f`
- name: `WTSGetListenerSecurityW`
- size: `495`
- prototype: `BOOL __stdcall(HANDLE hServer, PVOID pReserved, DWORD Reserved, LPWSTR pListenerName, SECURITY_INFORMATION SecurityInformation, PSECURITY_DESCRIPTOR pSecurityDescriptor, DWORD nLength, LPDWORD lpnLengthNeeded)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000af60`

## callees

- `0x18000b030`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b1f7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b20e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b1f7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b20e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b0a7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b0d1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b145`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b0a7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b0d1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b145`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b110`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b173`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b1d1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b110`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b173`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b1d1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b0dd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b11f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b183`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b1dd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b201`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b0dd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b11f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b183`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b1dd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b201`

## string_xrefs

- `0x18000b107`: `Security`
- `0x18000b1ca`: `Security`
- `0x18000b16c`: `DefaultSecurity`
- `0x18000b1ba`: `DefaultSecurity`

## pseudocode

```c
BOOL __stdcall WTSGetListenerSecurityW(
        HANDLE hServer,
        PVOID pReserved,
        DWORD Reserved,
        LPWSTR pListenerName,
        SECURITY_INFORMATION SecurityInformation,
        PSECURITY_DESCRIPTOR pSecurityDescriptor,
        DWORD nLength,
        LPDWORD lpnLengthNeeded)
{
  BOOL v8; // esi
  LPDWORD v10; // rbx
  LSTATUS v11; // eax
  DWORD v12; // ecx
  LSTATUS v13; // edi
  int v14; // edi
  DWORD v15; // eax
  const WCHAR *v16; // rdx
  LSTATUS v17; // ebx
  DWORD Type; // [rsp+30h] [rbp-28h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-20h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-18h] BYREF
  DWORD cbData; // [rsp+80h] [rbp+28h] BYREF

  v8 = 0;
  phkResult = 0;
  hKey = 0;
  cbData = 0;
  Type = 0;
  if ( __PAIR128__((unsigned __int64)hServer, (unsigned __int64)pReserved) != 0
    || Reserved
    || !pListenerName
    || SecurityInformation != 12
    || (v10 = lpnLengthNeeded) == 0 )
  {
    v12 = 87;
    goto LABEL_24;
  }
  v11 = RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Control\\Terminal Server\\WinStations",
          0,
          0x20019u,
          &hKey);
  if ( v11 )
    goto LABEL_7;
  v13 = RegOpenKeyExW(hKey, pListenerName, 0, 0x20019u, &phkResult);
  RegCloseKey(hKey);
  if ( v13 )
  {
LABEL_9:
    v12 = v13;
    goto LABEL_24;
  }
  v14 = 0;
  if ( RegQueryValueExW(phkResult, L"Security", 0, &Type, 0, &cbData) == 2 )
  {
    RegCloseKey(phkResult);
    v11 = RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"System\\CurrentControlSet\\Control\\Terminal Server\\WinStations",
            0,
            0x20019u,
            &phkResult);
    if ( v11 )
    {
LABEL_7:
      v12 = v11;
LABEL_24:
      SetLastError(v12);
      return v8;
    }
    v13 = RegQueryValueExW(phkResult, L"DefaultSecurity", 0, &Type, 0, &cbData);
    if ( v13 )
    {
      RegCloseKey(phkResult);
      goto LABEL_9;
    }
    v14 = 1;
  }
  v15 = cbData;
  *v10 = cbData;
  if ( nLength >= v15 && pSecurityDescriptor )
  {
    v16 = L"DefaultSecurity";
    if ( !v14 )
      v16 = L"Security";
    v17 = RegQueryValueExW(phkResult, v16, 0, &Type, (LPBYTE)pSecurityDescriptor, &cbData);
    RegCloseKey(phkResult);
    if ( v17 )
    {
      v12 = v17;
      goto LABEL_24;
    }
    return 1;
  }
  else
  {
    SetLastError(0x7Au);
    RegCloseKey(phkResult);
  }
  return v8;
}

```

## disassembly

```asm
0x18000b030  push    rbp
0x18000b032  push    rbx
0x18000b033  push    rsi
0x18000b034  push    rdi
0x18000b035  mov     rbp, rsp
0x18000b038  sub     rsp, 58h
0x18000b03c  xor     esi, esi
0x18000b03e  mov     rdi, r9
0x18000b041  mov     [rbp+var_20], rsi
0x18000b045  mov     [rbp+hKey], rsi
0x18000b049  mov     [rbp+cbData], esi
0x18000b04c  mov     [rbp+Type], esi
0x18000b04f  test    rcx, rcx
0x18000b052  jnz     loc_18000B209
0x18000b058  test    rdx, rdx
0x18000b05b  jnz     loc_18000B209
0x18000b061  test    r8d, r8d
0x18000b064  jnz     loc_18000B209
0x18000b06a  test    r9, r9
0x18000b06d  jz      loc_18000B209
0x18000b073  cmp     [rbp+SecurityInformation], 0Ch
0x18000b077  jnz     loc_18000B209
0x18000b07d  mov     rbx, [rbp+lpnLengthNeeded]
0x18000b081  test    rbx, rbx
0x18000b084  jz      loc_18000B209
0x18000b08a  lea     rax, [rbp+hKey]
0x18000b08e  mov     r9d, 20019h; samDesired
0x18000b094  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\Ter"...
0x18000b09b  mov     [rsp+58h+phkResult], rax; phkResult
0x18000b0a0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000b0a7  call    cs:__imp_RegOpenKeyExW
0x18000b0ad  test    eax, eax
0x18000b0af  jz      short loc_18000B0B8
0x18000b0b1  mov     ecx, eax
0x18000b0b3  jmp     loc_18000B20E
0x18000b0b8  mov     rcx, [rbp+hKey]; hKey
0x18000b0bc  lea     rax, [rbp+var_20]
0x18000b0c0  mov     r9d, 20019h; samDesired
0x18000b0c6  mov     [rsp+58h+phkResult], rax; phkResult
0x18000b0cb  xor     r8d, r8d; ulOptions
0x18000b0ce  mov     rdx, rdi; lpSubKey
0x18000b0d1  call    cs:__imp_RegOpenKeyExW
0x18000b0d7  mov     rcx, [rbp+hKey]; hKey
0x18000b0db  mov     edi, eax
0x18000b0dd  call    cs:__imp_RegCloseKey
0x18000b0e3  test    edi, edi
0x18000b0e5  jz      short loc_18000B0EE
0x18000b0e7  mov     ecx, edi
0x18000b0e9  jmp     loc_18000B20E
0x18000b0ee  mov     rcx, [rbp+var_20]; hKey
0x18000b0f2  lea     rax, [rbp+cbData]
0x18000b0f6  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18000b0fb  lea     r9, [rbp+Type]; lpType
0x18000b0ff  xor     r8d, r8d; lpReserved
0x18000b102  mov     [rsp+58h+phkResult], rsi; lpData
0x18000b107  lea     rdx, ValueName; "Security"
0x18000b10e  xor     edi, edi
0x18000b110  call    cs:__imp_RegQueryValueExW
0x18000b116  cmp     eax, 2
0x18000b119  jnz     short loc_18000B193
0x18000b11b  mov     rcx, [rbp+var_20]; hKey
0x18000b11f  call    cs:__imp_RegCloseKey
0x18000b125  lea     rax, [rbp+var_20]
0x18000b129  mov     r9d, 20019h; samDesired
0x18000b12f  xor     r8d, r8d; ulOptions
0x18000b132  mov     [rsp+58h+phkResult], rax; phkResult
0x18000b137  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\Ter"...
0x18000b13e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000b145  call    cs:__imp_RegOpenKeyExW
0x18000b14b  test    eax, eax
0x18000b14d  jnz     loc_18000B0B1
0x18000b153  mov     rcx, [rbp+var_20]; hKey
0x18000b157  lea     rax, [rbp+cbData]
0x18000b15b  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18000b160  lea     r9, [rbp+Type]; lpType
0x18000b164  xor     r8d, r8d; lpReserved
0x18000b167  mov     [rsp+58h+phkResult], rsi; lpData
0x18000b16c  lea     rdx, aDefaultsecurit; "DefaultSecurity"
0x18000b173  call    cs:__imp_RegQueryValueExW
0x18000b179  mov     edi, eax
0x18000b17b  test    eax, eax
0x18000b17d  jz      short loc_18000B18E
0x18000b17f  mov     rcx, [rbp+var_20]; hKey
0x18000b183  call    cs:__imp_RegCloseKey
0x18000b189  jmp     loc_18000B0E7
0x18000b18e  mov     edi, 1
0x18000b193  mov     eax, [rbp+cbData]
0x18000b196  mov     [rbx], eax
0x18000b198  cmp     [rbp+nLength], eax
0x18000b19b  jb      short loc_18000B1F2
0x18000b19d  mov     rax, [rbp+pSecurityDescriptor]
0x18000b1a1  test    rax, rax
0x18000b1a4  jz      short loc_18000B1F2
0x18000b1a6  lea     rcx, [rbp+cbData]
0x18000b1aa  xor     r8d, r8d; lpReserved
0x18000b1ad  mov     [rsp+58h+lpcbData], rcx; lpcbData
0x18000b1b2  lea     r9, [rbp+Type]; lpType
0x18000b1b6  mov     rcx, [rbp+var_20]; hKey
0x18000b1ba  lea     rdx, aDefaultsecurit; "DefaultSecurity"
0x18000b1c1  mov     [rsp+58h+phkResult], rax; lpData
0x18000b1c6  test    edi, edi
0x18000b1c8  jnz     short loc_18000B1D1
0x18000b1ca  lea     rdx, ValueName; "Security"
0x18000b1d1  call    cs:__imp_RegQueryValueExW
0x18000b1d7  mov     rcx, [rbp+var_20]; hKey
0x18000b1db  mov     ebx, eax
0x18000b1dd  call    cs:__imp_RegCloseKey
0x18000b1e3  test    ebx, ebx
0x18000b1e5  jz      short loc_18000B1EB
0x18000b1e7  mov     ecx, ebx
0x18000b1e9  jmp     short loc_18000B20E
0x18000b1eb  mov     esi, 1
0x18000b1f0  jmp     short loc_18000B214
0x18000b1f2  mov     ecx, 7Ah ; 'z'; dwErrCode
0x18000b1f7  call    cs:__imp_SetLastError
0x18000b1fd  mov     rcx, [rbp+var_20]; hKey
0x18000b201  call    cs:__imp_RegCloseKey
0x18000b207  jmp     short loc_18000B214
0x18000b209  mov     ecx, 57h ; 'W'; dwErrCode
0x18000b20e  call    cs:__imp_SetLastError
0x18000b214  mov     eax, esi
0x18000b216  add     rsp, 58h
0x18000b21a  pop     rdi
0x18000b21b  pop     rsi
0x18000b21c  pop     rbx
0x18000b21d  pop     rbp
0x18000b21e  retn
```
