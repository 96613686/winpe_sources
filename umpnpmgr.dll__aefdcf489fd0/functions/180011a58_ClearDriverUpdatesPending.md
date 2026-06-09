# ClearDriverUpdatesPending

- ea: `0x180011a58`
- end: `0x180011ab2`
- name: `ClearDriverUpdatesPending`
- size: `90`
- prototype: `LSTATUS()`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18000ea20`

## callees

- `0x180011a58`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011aa7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011aa7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180011a9c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180011a9c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011a86`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011a86`

## string_xrefs

- `0x180011a78`: `SYSTEM\CurrentControlSet\Services\DeviceInstall\Parameters`
- `0x180011a95`: `DriverUpdatesPending`

## pseudocode

```c
LSTATUS ClearDriverUpdatesPending()
{
  LSTATUS result; // eax
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  hKey = 0;
  result = RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"SYSTEM\\CurrentControlSet\\Services\\DeviceInstall\\Parameters",
             0,
             2u,
             &hKey);
  if ( !result )
  {
    RegDeleteValueW(hKey, L"DriverUpdatesPending");
    return RegCloseKey(hKey);
  }
  return result;
}

```

## disassembly

```asm
0x180011a58  sub     rsp, 38h
0x180011a5c  lea     rax, [rsp+38h+hKey]
0x180011a61  mov     [rsp+38h+hKey], 0
0x180011a6a  mov     r9d, 2; samDesired
0x180011a70  mov     [rsp+38h+phkResult], rax; phkResult
0x180011a75  xor     r8d, r8d; ulOptions
0x180011a78  lea     rdx, aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Services\\De"...
0x180011a7f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180011a86  call    cs:__imp_RegOpenKeyExW
0x180011a8c  test    eax, eax
0x180011a8e  jnz     short loc_180011AAD
0x180011a90  mov     rcx, [rsp+38h+hKey]; hKey
0x180011a95  lea     rdx, aDriverupdatesp; "DriverUpdatesPending"
0x180011a9c  call    cs:__imp_RegDeleteValueW
0x180011aa2  mov     rcx, [rsp+38h+hKey]; hKey
0x180011aa7  call    cs:__imp_RegCloseKey
0x180011aad  add     rsp, 38h
0x180011ab1  retn
```
