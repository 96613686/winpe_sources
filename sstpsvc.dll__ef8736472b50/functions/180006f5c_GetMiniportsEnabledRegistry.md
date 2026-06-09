# GetMiniportsEnabledRegistry

- ea: `0x180006f5c`
- end: `0x18000709d`
- name: `GetMiniportsEnabledRegistry`
- size: `321`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180006290`
- `0x180008ac0`

## callees

- `0x180006f5c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180007076`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180007076`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007086`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007086`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180007048`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180007048`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006fa4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006fa4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180006feb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180006feb`

## string_xrefs

- `0x180006f8f`: `SYSTEM\CurrentControlSet\Services\RasMan\Parameters`
- `0x18000701b`: `SYSTEM\CurrentControlSet\Services\RasMan\Parameters`
- `0x180006fe4`: `MiniportsInstalled`
- `0x180007064`: `MiniportsInstalled`

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
0x180006f5c  push    rbp
0x180006f5e  push    rbx
0x180006f5f  mov     rbp, rsp
0x180006f62  sub     rsp, 58h
0x180006f66  lea     rax, [rbp+hKey]
0x180006f6a  mov     [rbp+hKey], 0
0x180006f72  mov     ebx, 4
0x180006f77  mov     [rsp+58h+phkResult], rax; phkResult
0x180006f7c  mov     r9d, 2001Fh; samDesired
0x180006f82  mov     [rbp+Type], ebx
0x180006f85  xor     r8d, r8d; ulOptions
0x180006f88  mov     [rbp+Data], 0FFFFh
0x180006f8f  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x180006f96  mov     [rbp+cbData], 0
0x180006f9d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180006fa4  call    cs:__imp_RegOpenKeyExW
0x180006fab  nop     dword ptr [rax+rax+00h]
0x180006fb0  cmp     eax, 491h
0x180006fb5  jz      short loc_180007009
0x180006fb7  cmp     eax, 2
0x180006fba  jz      short loc_180007009
0x180006fbc  test    eax, eax
0x180006fbe  jnz     loc_180007082
0x180006fc4  mov     rcx, [rbp+hKey]; hKey
0x180006fc8  lea     rax, [rbp+cbData]
0x180006fcc  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180006fd1  lea     r9, [rbp+Type]; lpType
0x180006fd5  lea     rax, [rbp+Data]
0x180006fd9  mov     [rbp+cbData], ebx
0x180006fdc  xor     r8d, r8d; lpReserved
0x180006fdf  mov     [rsp+58h+phkResult], rax; lpData
0x180006fe4  lea     rdx, ValueName; "MiniportsInstalled"
0x180006feb  call    cs:__imp_RegQueryValueExW
0x180006ff2  nop     dword ptr [rax+rax+00h]
0x180006ff7  cmp     eax, 2
0x180006ffa  jnz     loc_180007082
0x180007000  mov     [rbp+Data], 0FFFFh
0x180007007  jmp     short loc_180007058
0x180007009  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x180007012  lea     rax, [rbp+hKey]
0x180007016  mov     [rsp+58h+var_20], rax; phkResult
0x18000701b  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x180007022  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18000702b  xor     r9d, r9d; lpClass
0x18000702e  mov     dword ptr [rsp+58h+lpcbData], 0F003Fh; samDesired
0x180007036  xor     r8d, r8d; Reserved
0x180007039  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180007040  mov     dword ptr [rsp+58h+phkResult], 0; dwOptions
0x180007048  call    cs:__imp_RegCreateKeyExW
0x18000704f  nop     dword ptr [rax+rax+00h]
0x180007054  test    eax, eax
0x180007056  jnz     short loc_180007082
0x180007058  mov     rcx, [rbp+hKey]; hKey
0x18000705c  lea     rax, [rbp+Data]
0x180007060  mov     dword ptr [rsp+58h+lpcbData], ebx; cbData
0x180007064  lea     rdx, ValueName; "MiniportsInstalled"
0x18000706b  mov     r9d, ebx; dwType
0x18000706e  mov     [rsp+58h+phkResult], rax; lpData
0x180007073  xor     r8d, r8d; Reserved
0x180007076  call    cs:__imp_RegSetValueExW
0x18000707d  nop     dword ptr [rax+rax+00h]
0x180007082  mov     rcx, [rbp+hKey]; hKey
0x180007086  call    cs:__imp_RegCloseKey
0x18000708d  nop     dword ptr [rax+rax+00h]
0x180007092  mov     eax, [rbp+Data]
0x180007095  add     rsp, 58h
0x180007099  pop     rbx
0x18000709a  pop     rbp
0x18000709b  retn
```
