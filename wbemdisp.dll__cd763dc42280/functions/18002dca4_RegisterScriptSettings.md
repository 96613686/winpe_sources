# RegisterScriptSettings

- ea: `0x18002dca4`
- end: `0x18002dd41`
- name: `RegisterScriptSettings`
- size: `157`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002d2c0`

## callees

- `0x18002dca4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002dcf7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002dd29`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002dcf7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002dd29`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002dd34`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002dd34`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x18002dcc4`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x18002dcc4`

## string_xrefs

- `0x18002dd1a`: `Default Impersonation Level`

## pseudocode

```c
__int64 RegisterScriptSettings()
{
  int Data; // [rsp+40h] [rbp+8h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp+10h] BYREF

  phkResult = 0;
  if ( !RegCreateKeyW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Wbem\\Scripting", &phkResult) )
  {
    RegSetValueExW(phkResult, L"Default Namespace", 0, 1u, L"root\\cimv2", 0x16u);
    Data = 3;
    RegSetValueExW(phkResult, L"Default Impersonation Level", 0, 4u, (const BYTE *)&Data, 4u);
    RegCloseKey(phkResult);
  }
  return 0;
}

```

## disassembly

```asm
0x18002dca4  sub     rsp, 38h
0x18002dca8  lea     r8, [rsp+38h+phkResult]; phkResult
0x18002dcad  mov     [rsp+38h+phkResult], 0
0x18002dcb6  lea     rdx, SubKey; "Software\\Microsoft\\Wbem\\Scripting"
0x18002dcbd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002dcc4  call    cs:__imp_RegCreateKeyW
0x18002dcca  test    eax, eax
0x18002dccc  jnz     short loc_18002DD3A
0x18002dcce  mov     rcx, [rsp+38h+phkResult]; hKey
0x18002dcd3  lea     rax, aRootCimv2; "root\\cimv2"
0x18002dcda  mov     [rsp+38h+cbData], 16h; cbData
0x18002dce2  lea     rdx, aDefaultNamespa; "Default Namespace"
0x18002dce9  mov     r9d, 1; dwType
0x18002dcef  mov     [rsp+38h+lpData], rax; lpData
0x18002dcf4  xor     r8d, r8d; Reserved
0x18002dcf7  call    cs:__imp_RegSetValueExW
0x18002dcfd  mov     rcx, [rsp+38h+phkResult]; hKey
0x18002dd02  lea     rax, [rsp+38h+Data]
0x18002dd07  mov     r9d, 4; dwType
0x18002dd0d  mov     [rsp+38h+Data], 3
0x18002dd15  mov     [rsp+38h+cbData], r9d; cbData
0x18002dd1a  lea     rdx, ValueName; "Default Impersonation Level"
0x18002dd21  xor     r8d, r8d; Reserved
0x18002dd24  mov     [rsp+38h+lpData], rax; lpData
0x18002dd29  call    cs:__imp_RegSetValueExW
0x18002dd2f  mov     rcx, [rsp+38h+phkResult]; hKey
0x18002dd34  call    cs:__imp_RegCloseKey
0x18002dd3a  xor     eax, eax
0x18002dd3c  add     rsp, 38h
0x18002dd40  retn
```
