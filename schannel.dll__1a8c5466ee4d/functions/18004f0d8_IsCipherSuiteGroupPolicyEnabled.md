# IsCipherSuiteGroupPolicyEnabled

- ea: `0x18004f0d8`
- end: `0x18004f176`
- name: `IsCipherSuiteGroupPolicyEnabled`
- size: `158`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180044528`

## callees

- `0x18004f0d8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004f168`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004f168`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004f14c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004f14c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004f116`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004f116`

## string_xrefs

- `0x18004f103`: `Software\Policies\Microsoft\Cryptography\Configuration\SSL\00010002`

## pseudocode

```c
__int64 IsCipherSuiteGroupPolicyEnabled()
{
  unsigned int v0; // ebx
  DWORD Type; // [rsp+40h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+48h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  hKey = 0;
  cbData = 0;
  Type = 0;
  v0 = 1;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Policies\\Microsoft\\Cryptography\\Configuration\\SSL\\00010002",
          0,
          0x20119u,
          &hKey)
    && (RegQueryValueExW(hKey, L"Functions", 0, &Type, 0, &cbData) || Type != 1) )
  {
    v0 = 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v0;
}

```

## disassembly

```asm
0x18004f0d8  mov     rax, rsp
0x18004f0db  push    rbx
0x18004f0dc  sub     rsp, 30h
0x18004f0e0  mov     qword ptr [rax+18h], 0
0x18004f0e8  mov     r9d, 20119h; samDesired
0x18004f0ee  mov     dword ptr [rax+10h], 0
0x18004f0f5  xor     r8d, r8d; ulOptions
0x18004f0f8  mov     dword ptr [rax+8], 0
0x18004f0ff  lea     rax, [rax+18h]
0x18004f103  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Cryptogr"...
0x18004f10a  mov     [rsp+38h+phkResult], rax; phkResult
0x18004f10f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004f116  call    cs:__imp_RegOpenKeyExW
0x18004f11c  mov     ebx, 1
0x18004f121  test    eax, eax
0x18004f123  jnz     short loc_18004F15E
0x18004f125  mov     rcx, [rsp+38h+hKey]; hKey
0x18004f12a  lea     rax, [rsp+38h+cbData]
0x18004f12f  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18004f134  lea     r9, [rsp+38h+Type]; lpType
0x18004f139  xor     r8d, r8d; lpReserved
0x18004f13c  mov     [rsp+38h+phkResult], 0; lpData
0x18004f145  lea     rdx, aFunctions; "Functions"
0x18004f14c  call    cs:__imp_RegQueryValueExW
0x18004f152  test    eax, eax
0x18004f154  jnz     short loc_18004F15C
0x18004f156  cmp     [rsp+38h+Type], ebx
0x18004f15a  jz      short loc_18004F15E
0x18004f15c  xor     ebx, ebx
0x18004f15e  mov     rcx, [rsp+38h+hKey]; hKey
0x18004f163  test    rcx, rcx
0x18004f166  jz      short loc_18004F16E
0x18004f168  call    cs:__imp_RegCloseKey
0x18004f16e  mov     eax, ebx
0x18004f170  add     rsp, 30h
0x18004f174  pop     rbx
0x18004f175  retn
```
