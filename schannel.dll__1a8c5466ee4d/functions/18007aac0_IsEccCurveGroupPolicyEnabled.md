# IsEccCurveGroupPolicyEnabled

- ea: `0x18007aac0`
- end: `0x18007ab61`
- name: `IsEccCurveGroupPolicyEnabled`
- size: `161`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180044528`

## callees

- `0x18007aac0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007ab53`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007ab53`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007ab2f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007ab2f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007aafe`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007aafe`

## string_xrefs

- `0x18007aaeb`: `Software\Policies\Microsoft\Cryptography\Configuration\SSL\00010002`

## pseudocode

```c
_BOOL8 IsEccCurveGroupPolicyEnabled()
{
  BOOL v0; // ebx
  DWORD Type; // [rsp+40h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+48h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  hKey = 0;
  cbData = 0;
  Type = 0;
  v0 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Policies\\Microsoft\\Cryptography\\Configuration\\SSL\\00010002",
         0,
         0x20119u,
         &hKey)
    || !RegQueryValueExW(hKey, L"EccCurves", 0, &Type, 0, &cbData) && Type == 7;
  if ( hKey )
    RegCloseKey(hKey);
  return v0;
}

```

## disassembly

```asm
0x18007aac0  mov     rax, rsp
0x18007aac3  push    rbx
0x18007aac4  sub     rsp, 30h
0x18007aac8  mov     qword ptr [rax+18h], 0
0x18007aad0  mov     r9d, 20119h; samDesired
0x18007aad6  mov     dword ptr [rax+10h], 0
0x18007aadd  xor     r8d, r8d; ulOptions
0x18007aae0  mov     dword ptr [rax+8], 0
0x18007aae7  lea     rax, [rax+18h]
0x18007aaeb  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Cryptogr"...
0x18007aaf2  mov     [rsp+38h+phkResult], rax; phkResult
0x18007aaf7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007aafe  call    cs:__imp_RegOpenKeyExW
0x18007ab04  test    eax, eax
0x18007ab06  jnz     short loc_18007AB44
0x18007ab08  mov     rcx, [rsp+38h+hKey]; hKey
0x18007ab0d  lea     rax, [rsp+38h+cbData]
0x18007ab12  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18007ab17  lea     r9, [rsp+38h+Type]; lpType
0x18007ab1c  xor     r8d, r8d; lpReserved
0x18007ab1f  mov     [rsp+38h+phkResult], 0; lpData
0x18007ab28  lea     rdx, aEcccurves; "EccCurves"
0x18007ab2f  call    cs:__imp_RegQueryValueExW
0x18007ab35  test    eax, eax
0x18007ab37  jnz     short loc_18007AB40
0x18007ab39  cmp     [rsp+38h+Type], 7
0x18007ab3e  jz      short loc_18007AB44
0x18007ab40  xor     ebx, ebx
0x18007ab42  jmp     short loc_18007AB49
0x18007ab44  mov     ebx, 1
0x18007ab49  mov     rcx, [rsp+38h+hKey]; hKey
0x18007ab4e  test    rcx, rcx
0x18007ab51  jz      short loc_18007AB59
0x18007ab53  call    cs:__imp_RegCloseKey
0x18007ab59  mov     eax, ebx
0x18007ab5b  add     rsp, 30h
0x18007ab5f  pop     rbx
0x18007ab60  retn
```
