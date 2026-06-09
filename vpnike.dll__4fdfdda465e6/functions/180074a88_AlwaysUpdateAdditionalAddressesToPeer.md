# AlwaysUpdateAdditionalAddressesToPeer

- ea: `0x180074a88`
- end: `0x180074b20`
- name: `AlwaysUpdateAdditionalAddressesToPeer`
- size: `152`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180002e70`

## callees

- `0x180074a88`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180074b0d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180074b0d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180074afd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180074afd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180074acb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180074acb`

## string_xrefs

- `0x180074a9e`: `SYSTEM\CurrentControlSet\Services\RemoteAccess\Parameters\Ikev2`
- `0x180074af1`: `AlwaysUpdateAdditionalAddressesToPeer`

## pseudocode

```c
bool AlwaysUpdateAdditionalAddressesToPeer()
{
  int Data; // [rsp+40h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+48h] [rbp+10h] BYREF
  DWORD Type; // [rsp+50h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+20h] BYREF

  hKey = 0;
  cbData = 4;
  Type = 4;
  Data = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SYSTEM\\CurrentControlSet\\Services\\RemoteAccess\\Parameters\\Ikev2",
          0,
          0x20019u,
          &hKey) )
    RegQueryValueExW(hKey, L"AlwaysUpdateAdditionalAddressesToPeer", 0, &Type, (LPBYTE)&Data, &cbData);
  if ( hKey )
    RegCloseKey(hKey);
  return Data != 0;
}

```

## disassembly

```asm
0x180074a88  sub     rsp, 38h
0x180074a8c  mov     eax, 4
0x180074a91  mov     [rsp+38h+hKey], 0
0x180074a9a  mov     [rsp+38h+cbData], eax
0x180074a9e  lea     rdx, aSystemCurrentc_5; "SYSTEM\\CurrentControlSet\\Services\\Re"...
0x180074aa5  mov     [rsp+38h+Type], eax
0x180074aa9  mov     r9d, 20019h; samDesired
0x180074aaf  lea     rax, [rsp+38h+hKey]
0x180074ab4  mov     [rsp+38h+Data], 0
0x180074abc  xor     r8d, r8d; ulOptions
0x180074abf  mov     [rsp+38h+phkResult], rax; phkResult
0x180074ac4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180074acb  call    cs:__imp_RegOpenKeyExW
0x180074ad1  test    eax, eax
0x180074ad3  jnz     short loc_180074B03
0x180074ad5  mov     rcx, [rsp+38h+hKey]; hKey
0x180074ada  lea     rax, [rsp+38h+cbData]
0x180074adf  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180074ae4  lea     r9, [rsp+38h+Type]; lpType
0x180074ae9  lea     rax, [rsp+38h+Data]
0x180074aee  xor     r8d, r8d; lpReserved
0x180074af1  lea     rdx, aAlwaysupdatead; "AlwaysUpdateAdditionalAddressesToPeer"
0x180074af8  mov     [rsp+38h+phkResult], rax; lpData
0x180074afd  call    cs:__imp_RegQueryValueExW
0x180074b03  mov     rcx, [rsp+38h+hKey]; hKey
0x180074b08  test    rcx, rcx
0x180074b0b  jz      short loc_180074B13
0x180074b0d  call    cs:__imp_RegCloseKey
0x180074b13  cmp     [rsp+38h+Data], 0
0x180074b18  setnz   al
0x180074b1b  add     rsp, 38h
0x180074b1f  retn
```
