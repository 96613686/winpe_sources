# GetLDAPNextServerID(ulong)

- ea: `0x180027494`
- end: `0x18002755b`
- name: `?GetLDAPNextServerID@@YAKK@Z`
- size: `199`
- prototype: `unsigned int __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800277e4`

## callees

- `0x180027494`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x1800274ca`
- `ADVAPI32!RegOpenKeyExW` at `0x1800274ca`
- `ADVAPI32!RegCloseKey` at `0x18002754c`
- `ADVAPI32!RegCloseKey` at `0x18002754c`
- `ADVAPI32!RegSetValueExW` at `0x180027542`
- `ADVAPI32!RegSetValueExW` at `0x180027542`
- `ADVAPI32!RegQueryValueExW` at `0x180027505`
- `ADVAPI32!RegQueryValueExW` at `0x180027505`

## pseudocode

```c
__int64 __fastcall GetLDAPNextServerID()
{
  unsigned int v0; // ebx
  unsigned int Data; // [rsp+50h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+58h] [rbp+20h] BYREF
  DWORD Type; // [rsp+60h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+30h] BYREF

  v0 = 0;
  Data = 0;
  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\WAB", 0, 0xF003Fu, &hKey) )
  {
    Data = 0;
    Type = 0;
    cbData = 4;
    v0 = 500;
    if ( !RegQueryValueExW(hKey, L"Server ID", 0, &Type, (LPBYTE)&Data, &cbData) )
      v0 = Data;
    Data = v0 + 1;
    RegSetValueExW(hKey, L"Server ID", 0, 4u, (const BYTE *)&Data, 4u);
    RegCloseKey(hKey);
  }
  return v0;
}

```

## disassembly

```asm
0x180027494  mov     [rsp-10h+Data], ecx
0x180027498  push    rbp
0x180027499  push    rbx
0x18002749a  mov     rbp, rsp
0x18002749d  sub     rsp, 38h
0x1800274a1  xor     ebx, ebx
0x1800274a3  lea     rax, [rbp+hKey]
0x1800274a7  mov     r9d, 0F003Fh; samDesired
0x1800274ad  mov     [rbp+Data], ebx
0x1800274b0  xor     r8d, r8d; ulOptions
0x1800274b3  mov     [rbp+hKey], rbx
0x1800274b7  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\WAB"
0x1800274be  mov     [rsp+38h+phkResult], rax; phkResult
0x1800274c3  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800274ca  call    cs:__imp_RegOpenKeyExW
0x1800274d0  test    eax, eax
0x1800274d2  jnz     short loc_180027552
0x1800274d4  mov     rcx, [rbp+hKey]; hKey
0x1800274d8  lea     rax, [rbp+cbData]
0x1800274dc  mov     [rsp+38h+lpcbData], rax; lpcbData
0x1800274e1  lea     r9, [rbp+Type]; lpType
0x1800274e5  lea     rax, [rbp+Data]
0x1800274e9  mov     [rbp+Data], ebx
0x1800274ec  xor     r8d, r8d; lpReserved
0x1800274ef  mov     [rsp+38h+phkResult], rax; lpData
0x1800274f4  lea     rdx, aServerId; "Server ID"
0x1800274fb  mov     [rbp+Type], ebx
0x1800274fe  mov     [rbp+cbData], 4
0x180027505  call    cs:__imp_RegQueryValueExW
0x18002750b  mov     ebx, 1F4h
0x180027510  test    eax, eax
0x180027512  jnz     short loc_180027517
0x180027514  mov     ebx, [rbp+Data]
0x180027517  lea     ecx, [rbx+1]
0x18002751a  mov     dword ptr [rsp+38h+lpcbData], 4; cbData
0x180027522  mov     [rbp+Data], ecx
0x180027525  lea     rax, [rbp+Data]
0x180027529  mov     rcx, [rbp+hKey]; hKey
0x18002752d  lea     rdx, aServerId; "Server ID"
0x180027534  mov     r9d, 4; dwType
0x18002753a  mov     [rsp+38h+phkResult], rax; lpData
0x18002753f  xor     r8d, r8d; Reserved
0x180027542  call    cs:__imp_RegSetValueExW
0x180027548  mov     rcx, [rbp+hKey]; hKey
0x18002754c  call    cs:__imp_RegCloseKey
0x180027552  mov     eax, ebx
0x180027554  add     rsp, 38h
0x180027558  pop     rbx
0x180027559  pop     rbp
0x18002755a  retn
```
