# CThemeManagerAPIRequest::InitializeServerChangeNumber(void)

- ea: `0x18000b3dc`
- end: `0x18000b4c8`
- name: `?InitializeServerChangeNumber@CThemeManagerAPIRequest@@SAJXZ`
- size: `236`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000db00`

## callees

- `0x18000b3dc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b417`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b417`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b4b0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b4b0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b451`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b451`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000b4a6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000b4a6`

## pseudocode

```c
__int64 CThemeManagerAPIRequest::InitializeServerChangeNumber(void)
{
  LSTATUS v0; // ebx
  LSTATUS v1; // edx
  unsigned int v2; // ecx
  unsigned int Data; // [rsp+50h] [rbp+18h] BYREF
  DWORD Type; // [rsp+58h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+30h] BYREF

  Data = CThemeManagerAPIRequest::s_dwServerChangeNumber;
  hKey = 0;
  v0 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\ThemeManager", 0, 3u, &hKey);
  if ( v0 )
  {
    v1 = 2;
  }
  else
  {
    Type = 0;
    cbData = 4;
    v1 = RegQueryValueExW(hKey, L"ServerChangeNumber", 0, &Type, (LPBYTE)&Data, &cbData);
    if ( !v1 && Type != 4 )
      v1 = 13;
  }
  v2 = (unsigned __int16)(Data + 1);
  Data = v2;
  if ( !v0 )
  {
    if ( v1 != 13 )
      RegSetValueExW(hKey, L"ServerChangeNumber", 0, 4u, (const BYTE *)&Data, 4u);
    RegCloseKey(hKey);
    v2 = Data;
  }
  CThemeManagerAPIRequest::s_dwServerChangeNumber = v2;
  return 0;
}

```

## disassembly

```asm
0x18000b3dc  push    rbp
0x18000b3de  push    rbx
0x18000b3df  mov     rbp, rsp
0x18000b3e2  sub     rsp, 38h
0x18000b3e6  mov     eax, cs:?s_dwServerChangeNumber@CThemeManagerAPIRequest@@0KA; ulong CThemeManagerAPIRequest::s_dwServerChangeNumber
0x18000b3ec  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18000b3f3  mov     [rbp+Data], eax
0x18000b3f6  mov     r9d, 3; samDesired
0x18000b3fc  lea     rax, [rbp+hKey]
0x18000b400  mov     [rbp+hKey], 0
0x18000b408  xor     r8d, r8d; ulOptions
0x18000b40b  mov     [rsp+38h+phkResult], rax; phkResult
0x18000b410  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000b417  call    cs:__imp_RegOpenKeyExW
0x18000b41d  mov     ebx, eax
0x18000b41f  test    eax, eax
0x18000b421  jnz     short loc_18000B468
0x18000b423  mov     rcx, [rbp+hKey]; hKey
0x18000b427  lea     r9, [rbp+Type]; lpType
0x18000b42b  mov     [rbp+Type], eax
0x18000b42e  lea     rdx, ?s_szServerChangeNumberValue@CThemeManagerAPIRequest@@0QBGB; "ServerChangeNumber"
0x18000b435  lea     rax, [rbp+cbData]
0x18000b439  mov     [rbp+cbData], 4
0x18000b440  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18000b445  xor     r8d, r8d; lpReserved
0x18000b448  lea     rax, [rbp+Data]
0x18000b44c  mov     [rsp+38h+phkResult], rax; lpData
0x18000b451  call    cs:__imp_RegQueryValueExW
0x18000b457  mov     edx, eax
0x18000b459  test    eax, eax
0x18000b45b  jnz     short loc_18000B46D
0x18000b45d  cmp     [rbp+Type], 4
0x18000b461  jz      short loc_18000B46D
0x18000b463  lea     edx, [rbx+0Dh]
0x18000b466  jmp     short loc_18000B46D
0x18000b468  mov     edx, 2
0x18000b46d  movzx   eax, word ptr [rbp+Data]
0x18000b471  inc     ax
0x18000b474  movzx   ecx, ax
0x18000b477  mov     [rbp+Data], ecx
0x18000b47a  test    ebx, ebx
0x18000b47c  jnz     short loc_18000B4B9
0x18000b47e  cmp     edx, 0Dh
0x18000b481  jz      short loc_18000B4AC
0x18000b483  mov     rcx, [rbp+hKey]; hKey
0x18000b487  lea     rax, [rbp+Data]
0x18000b48b  mov     dword ptr [rsp+38h+lpcbData], 4; cbData
0x18000b493  lea     r9d, [rbx+4]; dwType
0x18000b497  xor     r8d, r8d; Reserved
0x18000b49a  mov     [rsp+38h+phkResult], rax; lpData
0x18000b49f  lea     rdx, ?s_szServerChangeNumberValue@CThemeManagerAPIRequest@@0QBGB; "ServerChangeNumber"
0x18000b4a6  call    cs:__imp_RegSetValueExW
0x18000b4ac  mov     rcx, [rbp+hKey]; hKey
0x18000b4b0  call    cs:__imp_RegCloseKey
0x18000b4b6  mov     ecx, [rbp+Data]
0x18000b4b9  mov     cs:?s_dwServerChangeNumber@CThemeManagerAPIRequest@@0KA, ecx; ulong CThemeManagerAPIRequest::s_dwServerChangeNumber
0x18000b4bf  xor     eax, eax
0x18000b4c1  add     rsp, 38h
0x18000b4c5  pop     rbx
0x18000b4c6  pop     rbp
0x18000b4c7  retn
```
