# IsSysprepComplete

- ea: `0x180011e44`
- end: `0x180011eef`
- name: `IsSysprepComplete`
- size: `171`
- prototype: `_BOOL8()`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000a6b0`

## callees

- `0x180011e44`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011ecc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011ecc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180011ec0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180011ec0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011e8b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011e8b`

## string_xrefs

- `0x180011e6f`: `System\Setup\Status\ChildCompletion`

## pseudocode

```c
_BOOL8 IsSysprepComplete()
{
  LSTATUS v0; // ebx
  DWORD cbData; // [rsp+50h] [rbp+18h] BYREF
  DWORD Type; // [rsp+58h] [rbp+20h] BYREF
  int Data; // [rsp+60h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+30h] BYREF

  hKey = 0;
  Type = 0;
  cbData = 0;
  Data = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\Setup\\Status\\ChildCompletion", 0, 1u, &hKey) )
    return 0;
  cbData = 4;
  v0 = RegQueryValueExW(hKey, L"setup.exe", 0, &Type, (LPBYTE)&Data, &cbData);
  RegCloseKey(hKey);
  return !v0 && Type == 4 && Data != 0;
}

```

## disassembly

```asm
0x180011e44  push    rbp
0x180011e46  push    rbx
0x180011e47  mov     rbp, rsp
0x180011e4a  sub     rsp, 38h
0x180011e4e  lea     rax, [rbp+hKey]
0x180011e52  mov     [rbp+hKey], 0
0x180011e5a  mov     r9d, 1; samDesired
0x180011e60  mov     [rsp+38h+phkResult], rax; phkResult
0x180011e65  xor     r8d, r8d; ulOptions
0x180011e68  mov     [rbp+Type], 0
0x180011e6f  lea     rdx, aSystemSetupSta; "System\\Setup\\Status\\ChildCompletion"
0x180011e76  mov     [rbp+cbData], 0
0x180011e7d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180011e84  mov     [rbp+Data], 0
0x180011e8b  call    cs:__imp_RegOpenKeyExW
0x180011e91  test    eax, eax
0x180011e93  jnz     short loc_180011EE6
0x180011e95  mov     rcx, [rbp+hKey]; hKey
0x180011e99  lea     rax, [rbp+cbData]
0x180011e9d  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180011ea2  lea     r9, [rbp+Type]; lpType
0x180011ea6  lea     rax, [rbp+Data]
0x180011eaa  mov     [rbp+cbData], 4
0x180011eb1  xor     r8d, r8d; lpReserved
0x180011eb4  mov     [rsp+38h+phkResult], rax; lpData
0x180011eb9  lea     rdx, aSetupExe; "setup.exe"
0x180011ec0  call    cs:__imp_RegQueryValueExW
0x180011ec6  mov     rcx, [rbp+hKey]; hKey
0x180011eca  mov     ebx, eax
0x180011ecc  call    cs:__imp_RegCloseKey
0x180011ed2  test    ebx, ebx
0x180011ed4  jnz     short loc_180011EE6
0x180011ed6  cmp     [rbp+Type], 4
0x180011eda  jnz     short loc_180011EE6
0x180011edc  xor     eax, eax
0x180011ede  cmp     [rbp+Data], eax
0x180011ee1  setnz   al
0x180011ee4  jmp     short loc_180011EE8
0x180011ee6  xor     eax, eax
0x180011ee8  add     rsp, 38h
0x180011eec  pop     rbx
0x180011eed  pop     rbp
0x180011eee  retn
```
