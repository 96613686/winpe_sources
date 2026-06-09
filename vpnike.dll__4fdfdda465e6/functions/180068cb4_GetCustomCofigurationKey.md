# GetCustomCofigurationKey

- ea: `0x180068cb4`
- end: `0x180068d52`
- name: `GetCustomCofigurationKey`
- size: `158`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x180067234`
- `0x180068e78`

## callees

- `0x180068cb4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180068d29`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180068d29`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180068d45`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180068d45`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180068cf1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180068cf1`

## string_xrefs

- `0x180068cde`: `System\CurrentControlSet\Services\rasman\IKEv2`

## pseudocode

```c
HKEY GetCustomCofigurationKey()
{
  DWORD cbData; // [rsp+40h] [rbp+8h] BYREF
  int Data; // [rsp+48h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  hKey = 0;
  Data = 0;
  cbData = 0;
  if ( !RegOpenKeyExA(HKEY_LOCAL_MACHINE, "System\\CurrentControlSet\\Services\\rasman\\IKEv2", 0, 1u, &hKey) )
  {
    cbData = 4;
    if ( !RegQueryValueExA(hKey, "CustomParams", 0, 0, (LPBYTE)&Data, &cbData) && Data )
      return hKey;
    RegCloseKey(hKey);
  }
  return 0;
}

```

## disassembly

```asm
0x180068cb4  mov     rax, rsp
0x180068cb7  sub     rsp, 38h
0x180068cbb  mov     qword ptr [rax+18h], 0
0x180068cc3  mov     r9d, 1; samDesired
0x180068cc9  mov     dword ptr [rax+10h], 0
0x180068cd0  xor     r8d, r8d; ulOptions
0x180068cd3  mov     dword ptr [rax+8], 0
0x180068cda  lea     rax, [rax+18h]
0x180068cde  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\ra"...
0x180068ce5  mov     [rsp+38h+phkResult], rax; phkResult
0x180068cea  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180068cf1  call    cs:__imp_RegOpenKeyExA
0x180068cf7  test    eax, eax
0x180068cf9  jnz     short loc_180068D4B
0x180068cfb  mov     rcx, [rsp+38h+hKey]; hKey
0x180068d00  lea     rax, [rsp+38h+cbData]
0x180068d05  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180068d0a  lea     rdx, aCustomparams; "CustomParams"
0x180068d11  lea     rax, [rsp+38h+Data]
0x180068d16  mov     [rsp+38h+cbData], 4
0x180068d1e  xor     r9d, r9d; lpType
0x180068d21  mov     [rsp+38h+phkResult], rax; lpData
0x180068d26  xor     r8d, r8d; lpReserved
0x180068d29  call    cs:__imp_RegQueryValueExA
0x180068d2f  test    eax, eax
0x180068d31  jnz     short loc_180068D40
0x180068d33  cmp     [rsp+38h+Data], eax
0x180068d37  jz      short loc_180068D40
0x180068d39  mov     rax, [rsp+38h+hKey]
0x180068d3e  jmp     short loc_180068D4D
0x180068d40  mov     rcx, [rsp+38h+hKey]; hKey
0x180068d45  call    cs:__imp_RegCloseKey
0x180068d4b  xor     eax, eax
0x180068d4d  add     rsp, 38h
0x180068d51  retn
```
