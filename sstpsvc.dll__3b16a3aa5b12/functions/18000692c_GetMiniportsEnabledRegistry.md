# GetMiniportsEnabledRegistry

- ea: `0x18000692c`
- end: `0x180006a4a`
- name: `GetMiniportsEnabledRegistry`
- size: `286`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180005d50`
- `0x1800081c0`

## callees

- `0x18000692c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180006a30`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180006a30`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006a3a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006a3a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180006a08`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180006a08`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006974`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006974`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800069b5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800069b5`

## string_xrefs

- `0x18000695f`: `SYSTEM\CurrentControlSet\Services\RasMan\Parameters`
- `0x1800069db`: `SYSTEM\CurrentControlSet\Services\RasMan\Parameters`
- `0x1800069ae`: `MiniportsInstalled`
- `0x180006a1e`: `MiniportsInstalled`

## pseudocode

```c
__int64 GetMiniportsEnabledRegistry()
{
  LSTATUS v0; // eax
  unsigned int Data; // [rsp+70h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+78h] [rbp+20h] BYREF
  DWORD Type; // [rsp+80h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+30h] BYREF

  hKey = 0;
  Type = 4;
  Data = 0xFFFF;
  cbData = 0;
  v0 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Services\\RasMan\\Parameters", 0, 0x2001Fu, &hKey);
  if ( v0 == 1169 || v0 == 2 )
  {
    if ( !RegCreateKeyExW(
            HKEY_LOCAL_MACHINE,
            L"SYSTEM\\CurrentControlSet\\Services\\RasMan\\Parameters",
            0,
            0,
            0,
            0xF003Fu,
            0,
            &hKey,
            0) )
      goto LABEL_7;
  }
  else if ( !v0 )
  {
    cbData = 4;
    if ( RegQueryValueExW(hKey, L"MiniportsInstalled", 0, &Type, (LPBYTE)&Data, &cbData) == 2 )
    {
      Data = 0xFFFF;
LABEL_7:
      RegSetValueExW(hKey, L"MiniportsInstalled", 0, 4u, (const BYTE *)&Data, 4u);
    }
  }
  RegCloseKey(hKey);
  return Data;
}

```

## disassembly

```asm
0x18000692c  push    rbp
0x18000692e  push    rbx
0x18000692f  mov     rbp, rsp
0x180006932  sub     rsp, 58h
0x180006936  lea     rax, [rbp+hKey]
0x18000693a  mov     [rbp+hKey], 0
0x180006942  mov     ebx, 4
0x180006947  mov     [rsp+58h+phkResult], rax; phkResult
0x18000694c  mov     r9d, 2001Fh; samDesired
0x180006952  mov     [rbp+Type], ebx
0x180006955  xor     r8d, r8d; ulOptions
0x180006958  mov     [rbp+Data], 0FFFFh
0x18000695f  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x180006966  mov     [rbp+cbData], 0
0x18000696d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180006974  call    cs:__imp_RegOpenKeyExW
0x18000697a  cmp     eax, 491h
0x18000697f  jz      short loc_1800069C9
0x180006981  cmp     eax, 2
0x180006984  jz      short loc_1800069C9
0x180006986  test    eax, eax
0x180006988  jnz     loc_180006A36
0x18000698e  mov     rcx, [rbp+hKey]; hKey
0x180006992  lea     rax, [rbp+cbData]
0x180006996  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18000699b  lea     r9, [rbp+Type]; lpType
0x18000699f  lea     rax, [rbp+Data]
0x1800069a3  mov     [rbp+cbData], ebx
0x1800069a6  xor     r8d, r8d; lpReserved
0x1800069a9  mov     [rsp+58h+phkResult], rax; lpData
0x1800069ae  lea     rdx, ValueName; "MiniportsInstalled"
0x1800069b5  call    cs:__imp_RegQueryValueExW
0x1800069bb  cmp     eax, 2
0x1800069be  jnz     short loc_180006A36
0x1800069c0  mov     [rbp+Data], 0FFFFh
0x1800069c7  jmp     short loc_180006A12
0x1800069c9  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x1800069d2  lea     rax, [rbp+hKey]
0x1800069d6  mov     [rsp+58h+var_20], rax; phkResult
0x1800069db  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x1800069e2  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800069eb  xor     r9d, r9d; lpClass
0x1800069ee  mov     dword ptr [rsp+58h+lpcbData], 0F003Fh; samDesired
0x1800069f6  xor     r8d, r8d; Reserved
0x1800069f9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180006a00  mov     dword ptr [rsp+58h+phkResult], 0; dwOptions
0x180006a08  call    cs:__imp_RegCreateKeyExW
0x180006a0e  test    eax, eax
0x180006a10  jnz     short loc_180006A36
0x180006a12  mov     rcx, [rbp+hKey]; hKey
0x180006a16  lea     rax, [rbp+Data]
0x180006a1a  mov     dword ptr [rsp+58h+lpcbData], ebx; cbData
0x180006a1e  lea     rdx, ValueName; "MiniportsInstalled"
0x180006a25  mov     r9d, ebx; dwType
0x180006a28  mov     [rsp+58h+phkResult], rax; lpData
0x180006a2d  xor     r8d, r8d; Reserved
0x180006a30  call    cs:__imp_RegSetValueExW
0x180006a36  mov     rcx, [rbp+hKey]; hKey
0x180006a3a  call    cs:__imp_RegCloseKey
0x180006a40  mov     eax, [rbp+Data]
0x180006a43  add     rsp, 58h
0x180006a47  pop     rbx
0x180006a48  pop     rbp
0x180006a49  retn
```
