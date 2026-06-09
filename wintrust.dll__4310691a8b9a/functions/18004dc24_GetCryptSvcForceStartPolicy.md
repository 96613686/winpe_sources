# GetCryptSvcForceStartPolicy

- ea: `0x18004dc24`
- end: `0x18004dcc9`
- name: `GetCryptSvcForceStartPolicy`
- size: `165`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180005920`

## callees

- `0x18004dc24`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004dc9e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004dc9e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004dc70`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004dc70`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004dcba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004dcba`

## pseudocode

```c
__int64 GetCryptSvcForceStartPolicy()
{
  unsigned int v0; // ebx
  unsigned int Data; // [rsp+50h] [rbp+18h] BYREF
  DWORD Type; // [rsp+58h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+30h] BYREF

  hKey = 0;
  Type = 0;
  Data = 0;
  cbData = 4;
  v0 = 1;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Cryptography\\CatalogDB", 0, 0x20019u, &hKey) )
  {
    if ( !RegQueryValueExW(hKey, L"CryptSvcForceStartPolicy", 0, &Type, (LPBYTE)&Data, &cbData)
      && Type == 4
      && Data <= 2 )
    {
      v0 = Data;
    }
    RegCloseKey(hKey);
  }
  return v0;
}

```

## disassembly

```asm
0x18004dc24  push    rbp
0x18004dc26  push    rbx
0x18004dc27  mov     rbp, rsp
0x18004dc2a  sub     rsp, 38h
0x18004dc2e  lea     rax, [rbp+hKey]
0x18004dc32  mov     [rbp+hKey], 0
0x18004dc3a  mov     r9d, 20019h; samDesired
0x18004dc40  mov     [rsp+38h+phkResult], rax; phkResult
0x18004dc45  xor     r8d, r8d; ulOptions
0x18004dc48  mov     [rbp+Type], 0
0x18004dc4f  lea     rdx, aSoftwareMicros_10; "Software\\Microsoft\\Cryptography\\Cata"...
0x18004dc56  mov     [rbp+Data], 0
0x18004dc5d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004dc64  mov     [rbp+cbData], 4
0x18004dc6b  mov     ebx, 1
0x18004dc70  call    cs:__imp_RegOpenKeyExW
0x18004dc76  test    eax, eax
0x18004dc78  jnz     short loc_18004DCC0
0x18004dc7a  mov     rcx, [rbp+hKey]; hKey
0x18004dc7e  lea     rax, [rbp+cbData]
0x18004dc82  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18004dc87  lea     r9, [rbp+Type]; lpType
0x18004dc8b  lea     rax, [rbp+Data]
0x18004dc8f  xor     r8d, r8d; lpReserved
0x18004dc92  lea     rdx, aCryptsvcforces; "CryptSvcForceStartPolicy"
0x18004dc99  mov     [rsp+38h+phkResult], rax; lpData
0x18004dc9e  call    cs:__imp_RegQueryValueExW
0x18004dca4  test    eax, eax
0x18004dca6  jnz     short loc_18004DCB6
0x18004dca8  cmp     [rbp+Type], 4
0x18004dcac  jnz     short loc_18004DCB6
0x18004dcae  cmp     [rbp+Data], 2
0x18004dcb2  cmovbe  ebx, [rbp+Data]
0x18004dcb6  mov     rcx, [rbp+hKey]; hKey
0x18004dcba  call    cs:__imp_RegCloseKey
0x18004dcc0  mov     eax, ebx
0x18004dcc2  add     rsp, 38h
0x18004dcc6  pop     rbx
0x18004dcc7  pop     rbp
0x18004dcc8  retn
```
