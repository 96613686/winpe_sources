# GetDefaultUibcSetting

- ea: `0x180061d1c`
- end: `0x180061e5b`
- name: `GetDefaultUibcSetting`
- size: `319`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180043b80`

## callees

- `0x180061d1c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180061d93`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180061e1f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180061d93`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180061e1f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180061d58`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180061de4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180061d58`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180061de4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180061db6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180061e42`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180061db6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180061e42`

## pseudocode

```c
bool __fastcall GetDefaultUibcSetting(char *a1)
{
  char v2; // bl
  bool v3; // di
  DWORD Type; // [rsp+60h] [rbp+28h] BYREF
  DWORD cbData; // [rsp+68h] [rbp+30h] BYREF
  int Data; // [rsp+70h] [rbp+38h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+40h] BYREF

  hKey = 0;
  v2 = 0;
  v3 = 0;
  if ( RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System", 0, 1u, &hKey) )
    goto LABEL_18;
  Type = 0;
  Data = 0;
  cbData = 4;
  if ( !RegQueryValueExW(hKey, L"UIBCEnabledByDefault", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 && cbData == 4 )
  {
    v2 = 1;
    v3 = Data != 0;
  }
  RegCloseKey(hKey);
  if ( !v2 )
  {
LABEL_18:
    if ( !RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System",
            0,
            1u,
            &hKey) )
    {
      Type = 0;
      Data = 0;
      cbData = 4;
      if ( !RegQueryValueExW(hKey, L"UIBCEnabledByDefault", 0, &Type, (LPBYTE)&Data, &cbData)
        && Type == 4
        && cbData == 4 )
      {
        v2 = 1;
        v3 = Data != 0;
      }
      RegCloseKey(hKey);
    }
  }
  if ( a1 )
    *a1 = v2;
  return v3;
}

```

## disassembly

```asm
0x180061d1c  push    rbp
0x180061d1e  push    rbx
0x180061d1f  push    rsi
0x180061d20  push    rdi
0x180061d21  mov     rbp, rsp
0x180061d24  sub     rsp, 38h
0x180061d28  mov     rsi, rcx
0x180061d2b  mov     [rbp+hKey], 0
0x180061d33  lea     rax, [rbp+hKey]
0x180061d37  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180061d3e  mov     r9d, 1; samDesired
0x180061d44  mov     [rsp+38h+phkResult], rax; phkResult
0x180061d49  xor     r8d, r8d; ulOptions
0x180061d4c  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180061d53  xor     bl, bl
0x180061d55  xor     dil, dil
0x180061d58  call    cs:__imp_RegOpenKeyExW
0x180061d5e  test    eax, eax
0x180061d60  jnz     short loc_180061DC4
0x180061d62  mov     rcx, [rbp+hKey]; hKey
0x180061d66  lea     r9, [rbp+Type]; lpType
0x180061d6a  mov     [rbp+Type], eax
0x180061d6d  lea     rdx, ValueName; "UIBCEnabledByDefault"
0x180061d74  mov     [rbp+Data], eax
0x180061d77  xor     r8d, r8d; lpReserved
0x180061d7a  lea     rax, [rbp+cbData]
0x180061d7e  mov     [rbp+cbData], 4
0x180061d85  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180061d8a  lea     rax, [rbp+Data]
0x180061d8e  mov     [rsp+38h+phkResult], rax; lpData
0x180061d93  call    cs:__imp_RegQueryValueExW
0x180061d99  test    eax, eax
0x180061d9b  jnz     short loc_180061DB2
0x180061d9d  cmp     [rbp+Type], 4
0x180061da1  jnz     short loc_180061DB2
0x180061da3  cmp     [rbp+cbData], 4
0x180061da7  jnz     short loc_180061DB2
0x180061da9  cmp     [rbp+Data], eax
0x180061dac  mov     bl, 1
0x180061dae  setnz   dil
0x180061db2  mov     rcx, [rbp+hKey]; hKey
0x180061db6  call    cs:__imp_RegCloseKey
0x180061dbc  test    bl, bl
0x180061dbe  jnz     loc_180061E48
0x180061dc4  lea     rax, [rbp+hKey]
0x180061dc8  mov     r9d, 1; samDesired
0x180061dce  xor     r8d, r8d; ulOptions
0x180061dd1  mov     [rsp+38h+phkResult], rax; phkResult
0x180061dd6  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180061ddd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180061de4  call    cs:__imp_RegOpenKeyExW
0x180061dea  test    eax, eax
0x180061dec  jnz     short loc_180061E48
0x180061dee  mov     rcx, [rbp+hKey]; hKey
0x180061df2  lea     r9, [rbp+Type]; lpType
0x180061df6  mov     [rbp+Type], eax
0x180061df9  lea     rdx, ValueName; "UIBCEnabledByDefault"
0x180061e00  mov     [rbp+Data], eax
0x180061e03  xor     r8d, r8d; lpReserved
0x180061e06  lea     rax, [rbp+cbData]
0x180061e0a  mov     [rbp+cbData], 4
0x180061e11  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180061e16  lea     rax, [rbp+Data]
0x180061e1a  mov     [rsp+38h+phkResult], rax; lpData
0x180061e1f  call    cs:__imp_RegQueryValueExW
0x180061e25  test    eax, eax
0x180061e27  jnz     short loc_180061E3E
0x180061e29  cmp     [rbp+Type], 4
0x180061e2d  jnz     short loc_180061E3E
0x180061e2f  cmp     [rbp+cbData], 4
0x180061e33  jnz     short loc_180061E3E
0x180061e35  cmp     [rbp+Data], eax
0x180061e38  mov     bl, 1
0x180061e3a  setnz   dil
0x180061e3e  mov     rcx, [rbp+hKey]; hKey
0x180061e42  call    cs:__imp_RegCloseKey
0x180061e48  test    rsi, rsi
0x180061e4b  jz      short loc_180061E4F
0x180061e4d  mov     [rsi], bl
0x180061e4f  mov     al, dil
0x180061e52  add     rsp, 38h
0x180061e56  pop     rdi
0x180061e57  pop     rsi
0x180061e58  pop     rbx
0x180061e59  pop     rbp
0x180061e5a  retn
```
