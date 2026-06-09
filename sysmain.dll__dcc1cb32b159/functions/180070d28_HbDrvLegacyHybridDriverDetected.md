# HbDrvLegacyHybridDriverDetected

- ea: `0x180070d28`
- end: `0x180070e2e`
- name: `HbDrvLegacyHybridDriverDetected`
- size: `262`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180064170`

## callees

- `0x180070d28`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180070e10`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180070e1f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180070e10`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180070e1f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180070d9e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180070df5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180070d9e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180070df5`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x180070d6c`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x180070dc7`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x180070d6c`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x180070dc7`

## string_xrefs

- `0x180070d56`: `System\CurrentControlSet\Services\storahci\Parameters\Device`

## pseudocode

```c
_BOOL8 HbDrvLegacyHybridDriverDetected()
{
  BOOL v0; // ebx
  HKEY hKey; // [rsp+30h] [rbp-18h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+18h] BYREF
  int Data; // [rsp+68h] [rbp+20h] BYREF
  DWORD Type; // [rsp+70h] [rbp+28h] BYREF
  HKEY phkResult; // [rsp+78h] [rbp+30h] BYREF

  Data = 0;
  Type = 0;
  phkResult = 0;
  hKey = 0;
  cbData = 4;
  v0 = RegOpenKeyW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\storahci\\Parameters\\Device", &phkResult) >= 0
    && !RegQueryValueExW(phkResult, L"AllowDeviceHybridInfo", 0, &Type, (LPBYTE)&Data, &cbData)
    && cbData == 4
    && Type == 4
    && Data
    && RegOpenKeyW(HKEY_LOCAL_MACHINE, L"System\\Setup", &hKey) >= 0
    && RegQueryValueExW(hKey, L"Upgrade", 0, &Type, (LPBYTE)&Data, &cbData) != 2;
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hKey )
    RegCloseKey(hKey);
  return v0;
}

```

## disassembly

```asm
0x180070d28  push    rbp
0x180070d2a  push    rbx
0x180070d2b  mov     rbp, rsp
0x180070d2e  sub     rsp, 48h
0x180070d32  mov     rbx, 0FFFFFFFF80000002h
0x180070d39  mov     [rbp+Data], 0
0x180070d40  mov     rcx, rbx; hKey
0x180070d43  mov     [rbp+Type], 0
0x180070d4a  lea     r8, [rbp+phkResult]; phkResult
0x180070d4e  mov     [rbp+phkResult], 0
0x180070d56  lea     rdx, aSystemCurrentc_5; "System\\CurrentControlSet\\Services\\st"...
0x180070d5d  mov     [rbp+hKey], 0
0x180070d65  mov     [rbp+cbData], 4
0x180070d6c  call    cs:__imp_RegOpenKeyW
0x180070d72  test    eax, eax
0x180070d74  js      loc_180070E05
0x180070d7a  mov     rcx, [rbp+phkResult]; hKey
0x180070d7e  lea     rax, [rbp+cbData]
0x180070d82  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180070d87  lea     r9, [rbp+Type]; lpType
0x180070d8b  lea     rax, [rbp+Data]
0x180070d8f  xor     r8d, r8d; lpReserved
0x180070d92  lea     rdx, aAllowdevicehyb; "AllowDeviceHybridInfo"
0x180070d99  mov     [rsp+48h+lpData], rax; lpData
0x180070d9e  call    cs:__imp_RegQueryValueExW
0x180070da4  test    eax, eax
0x180070da6  jnz     short loc_180070E05
0x180070da8  cmp     [rbp+cbData], 4
0x180070dac  jnz     short loc_180070E05
0x180070dae  cmp     [rbp+Type], 4
0x180070db2  jnz     short loc_180070E05
0x180070db4  cmp     [rbp+Data], eax
0x180070db7  jz      short loc_180070E05
0x180070db9  lea     r8, [rbp+hKey]; phkResult
0x180070dbd  mov     rcx, rbx; hKey
0x180070dc0  lea     rdx, aSystemSetup; "System\\Setup"
0x180070dc7  call    cs:__imp_RegOpenKeyW
0x180070dcd  test    eax, eax
0x180070dcf  js      short loc_180070E05
0x180070dd1  mov     rcx, [rbp+hKey]; hKey
0x180070dd5  lea     rax, [rbp+cbData]
0x180070dd9  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180070dde  lea     r9, [rbp+Type]; lpType
0x180070de2  lea     rax, [rbp+Data]
0x180070de6  xor     r8d, r8d; lpReserved
0x180070de9  lea     rdx, aUpgrade; "Upgrade"
0x180070df0  mov     [rsp+48h+lpData], rax; lpData
0x180070df5  call    cs:__imp_RegQueryValueExW
0x180070dfb  xor     ebx, ebx
0x180070dfd  cmp     eax, 2
0x180070e00  setnz   bl
0x180070e03  jmp     short loc_180070E07
0x180070e05  xor     ebx, ebx
0x180070e07  mov     rcx, [rbp+phkResult]; hKey
0x180070e0b  test    rcx, rcx
0x180070e0e  jz      short loc_180070E16
0x180070e10  call    cs:__imp_RegCloseKey
0x180070e16  mov     rcx, [rbp+hKey]; hKey
0x180070e1a  test    rcx, rcx
0x180070e1d  jz      short loc_180070E25
0x180070e1f  call    cs:__imp_RegCloseKey
0x180070e25  mov     eax, ebx
0x180070e27  add     rsp, 48h
0x180070e2b  pop     rbx
0x180070e2c  pop     rbp
0x180070e2d  retn
```
