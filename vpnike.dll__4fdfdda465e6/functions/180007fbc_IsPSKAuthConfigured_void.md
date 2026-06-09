# IsPSKAuthConfigured(void)

- ea: `0x180007fbc`
- end: `0x180008047`
- name: `?IsPSKAuthConfigured@@YAEXZ`
- size: `139`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x180008520`

## callees

- `0x180007fbc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180008029`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180008029`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008034`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008034`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180007ff9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180007ff9`

## string_xrefs

- `0x180007fe6`: `System\CurrentControlSet\Services\rasman\IKEv2`

## pseudocode

```c
bool IsPSKAuthConfigured(void)
{
  int Data; // [rsp+40h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+48h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  hKey = 0;
  Data = 0;
  cbData = 4;
  if ( !RegOpenKeyExA(HKEY_LOCAL_MACHINE, "System\\CurrentControlSet\\Services\\rasman\\IKEv2", 0, 1u, &hKey) )
  {
    RegQueryValueExA(hKey, "IkeAuthTypePsk", 0, 0, (LPBYTE)&Data, &cbData);
    RegCloseKey(hKey);
  }
  return (Data & 2) != 0;
}

```

## disassembly

```asm
0x180007fbc  mov     rax, rsp
0x180007fbf  sub     rsp, 38h
0x180007fc3  mov     qword ptr [rax+18h], 0
0x180007fcb  mov     r9d, 1; samDesired
0x180007fd1  mov     dword ptr [rax+8], 0
0x180007fd8  xor     r8d, r8d; ulOptions
0x180007fdb  mov     dword ptr [rax+10h], 4
0x180007fe2  lea     rax, [rax+18h]
0x180007fe6  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\ra"...
0x180007fed  mov     [rsp+38h+phkResult], rax; phkResult
0x180007ff2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180007ff9  call    cs:__imp_RegOpenKeyExA
0x180007fff  test    eax, eax
0x180008001  jnz     short loc_18000803A
0x180008003  mov     rcx, [rsp+38h+hKey]; hKey
0x180008008  lea     rax, [rsp+38h+cbData]
0x18000800d  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180008012  lea     rdx, ValueName; "IkeAuthTypePsk"
0x180008019  lea     rax, [rsp+38h+Data]
0x18000801e  xor     r9d, r9d; lpType
0x180008021  xor     r8d, r8d; lpReserved
0x180008024  mov     [rsp+38h+phkResult], rax; lpData
0x180008029  call    cs:__imp_RegQueryValueExA
0x18000802f  mov     rcx, [rsp+38h+hKey]; hKey
0x180008034  call    cs:__imp_RegCloseKey
0x18000803a  mov     eax, [rsp+38h+Data]
0x18000803e  shr     eax, 1
0x180008040  and     al, 1
0x180008042  add     rsp, 38h
0x180008046  retn
```
