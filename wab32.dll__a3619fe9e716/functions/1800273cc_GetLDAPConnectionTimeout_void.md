# GetLDAPConnectionTimeout(void)

- ea: `0x1800273cc`
- end: `0x18002748e`
- name: `?GetLDAPConnectionTimeout@@YAKXZ`
- size: `194`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180029834`

## callees

- `0x1800273cc`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x180027404`
- `ADVAPI32!RegOpenKeyExW` at `0x180027404`
- `ADVAPI32!RegCloseKey` at `0x18002747f`
- `ADVAPI32!RegCloseKey` at `0x18002747f`
- `ADVAPI32!RegSetValueExW` at `0x180027475`
- `ADVAPI32!RegSetValueExW` at `0x180027475`
- `ADVAPI32!RegQueryValueExW` at `0x18002743f`
- `ADVAPI32!RegQueryValueExW` at `0x18002743f`

## pseudocode

```c
__int64 GetLDAPConnectionTimeout(void)
{
  unsigned int Data; // [rsp+40h] [rbp+10h] BYREF
  DWORD cbData; // [rsp+48h] [rbp+18h] BYREF
  DWORD Type; // [rsp+50h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+28h] BYREF

  Data = 0;
  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\WAB", 0, 0xF003Fu, &hKey) )
  {
    Type = 0;
    Data = 0;
    cbData = 4;
    if ( RegQueryValueExW(hKey, L"LDAP Connection Timeout", 0, &Type, (LPBYTE)&Data, &cbData) )
    {
      Data = 10;
      RegSetValueExW(hKey, L"LDAP Connection Timeout", 0, 4u, (const BYTE *)&Data, 4u);
    }
    RegCloseKey(hKey);
  }
  return Data;
}

```

## disassembly

```asm
0x1800273cc  push    rbp
0x1800273ce  mov     rbp, rsp
0x1800273d1  sub     rsp, 30h
0x1800273d5  lea     rax, [rbp+hKey]
0x1800273d9  mov     [rbp+Data], 0
0x1800273e0  mov     r9d, 0F003Fh; samDesired
0x1800273e6  mov     [rsp+30h+phkResult], rax; phkResult
0x1800273eb  xor     r8d, r8d; ulOptions
0x1800273ee  mov     [rbp+hKey], 0
0x1800273f6  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\WAB"
0x1800273fd  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180027404  call    cs:__imp_RegOpenKeyExW
0x18002740a  test    eax, eax
0x18002740c  jnz     short loc_180027485
0x18002740e  mov     rcx, [rbp+hKey]; hKey
0x180027412  lea     r9, [rbp+Type]; lpType
0x180027416  mov     [rbp+Type], eax
0x180027419  lea     rdx, aLdapConnection; "LDAP Connection Timeout"
0x180027420  mov     [rbp+Data], eax
0x180027423  xor     r8d, r8d; lpReserved
0x180027426  lea     rax, [rbp+cbData]
0x18002742a  mov     [rbp+cbData], 4
0x180027431  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180027436  lea     rax, [rbp+Data]
0x18002743a  mov     [rsp+30h+phkResult], rax; lpData
0x18002743f  call    cs:__imp_RegQueryValueExW
0x180027445  test    eax, eax
0x180027447  jz      short loc_18002747B
0x180027449  mov     rcx, [rbp+hKey]; hKey
0x18002744d  lea     rax, [rbp+Data]
0x180027451  mov     dword ptr [rsp+30h+lpcbData], 4; cbData
0x180027459  lea     rdx, aLdapConnection; "LDAP Connection Timeout"
0x180027460  mov     r9d, 4; dwType
0x180027466  mov     [rsp+30h+phkResult], rax; lpData
0x18002746b  xor     r8d, r8d; Reserved
0x18002746e  mov     [rbp+Data], 0Ah
0x180027475  call    cs:__imp_RegSetValueExW
0x18002747b  mov     rcx, [rbp+hKey]; hKey
0x18002747f  call    cs:__imp_RegCloseKey
0x180027485  mov     eax, [rbp+Data]
0x180027488  add     rsp, 30h
0x18002748c  pop     rbp
0x18002748d  retn
```
