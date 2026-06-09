# UpdateLDAPClientTraceSettingsFromKey

- ea: `0x180029c10`
- end: `0x180029d20`
- name: `UpdateLDAPClientTraceSettingsFromKey`
- size: `272`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x180029be0`

## callees

- `0x180029c10`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180029cfa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180029cfa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029d12`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029d12`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180029c87`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180029c87`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180029c53`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180029c53`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180029cd2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180029cd2`

## pseudocode

```c
LSTATUS __fastcall UpdateLDAPClientTraceSettingsFromKey(__int64 a1)
{
  LSTATUS result; // eax
  DWORD Type; // [rsp+50h] [rbp+10h] BYREF
  int v3; // [rsp+54h] [rbp+14h]
  int pvData; // [rsp+58h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+60h] [rbp+20h] BYREF

  v3 = HIDWORD(a1);
  Type = 0;
  pvData = 0;
  hKey = 0;
  result = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, &g_pszProcessKeyName, 0, 0x20019u, &hKey) )
  {
    if ( RegQueryValueExW(hKey, L"Pid", 0, &Type, 0, 0)
      || Type == 4
      && (Type = 4, !RegGetValueW(hKey, 0, L"Pid", 0x10u, 0, &pvData, &Type))
      && pvData == GetCurrentProcessId() )
    {
      result = 1;
    }
  }
  g_fTracingOn = result;
  if ( hKey )
    return RegCloseKey(hKey);
  return result;
}

```

## disassembly

```asm
0x180029c10  mov     qword ptr [rsp-8+Type], rcx
0x180029c15  push    rbp
0x180029c16  mov     rbp, rsp
0x180029c19  sub     rsp, 40h
0x180029c1d  lea     rax, [rbp+hKey]
0x180029c21  mov     [rbp+Type], 0
0x180029c28  mov     r9d, 20019h; samDesired
0x180029c2e  mov     [rsp+40h+phkResult], rax; phkResult
0x180029c33  xor     r8d, r8d; ulOptions
0x180029c36  mov     [rbp+pvData], 0
0x180029c3d  lea     rdx, ?g_pszProcessKeyName@@3PAGA; lpSubKey
0x180029c44  mov     [rbp+hKey], 0
0x180029c4c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180029c53  call    cs:__imp_RegOpenKeyExW
0x180029c5a  nop     dword ptr [rax+rax+00h]
0x180029c5f  test    eax, eax
0x180029c61  jnz     short loc_180029CE2
0x180029c63  mov     rcx, [rbp+hKey]; hKey
0x180029c67  lea     r9, [rbp+Type]; lpType
0x180029c6b  mov     [rsp+40h+lpcbData], 0; lpcbData
0x180029c74  lea     rdx, Value; "Pid"
0x180029c7b  xor     r8d, r8d; lpReserved
0x180029c7e  mov     [rsp+40h+phkResult], 0; lpData
0x180029c87  call    cs:__imp_RegQueryValueExW
0x180029c8e  nop     dword ptr [rax+rax+00h]
0x180029c93  test    eax, eax
0x180029c95  jnz     short loc_180029D0B
0x180029c97  cmp     [rbp+Type], 4
0x180029c9b  jnz     short loc_180029CE2
0x180029c9d  mov     rcx, [rbp+hKey]; hkey
0x180029ca1  lea     rax, [rbp+Type]
0x180029ca5  mov     [rsp+40h+pcbData], rax; pcbData
0x180029caa  lea     r8, Value; "Pid"
0x180029cb1  lea     rax, [rbp+pvData]
0x180029cb5  mov     [rbp+Type], 4
0x180029cbc  mov     [rsp+40h+lpcbData], rax; pvData
0x180029cc1  mov     r9d, 10h; dwFlags
0x180029cc7  xor     edx, edx; lpSubKey
0x180029cc9  mov     [rsp+40h+phkResult], 0; pdwType
0x180029cd2  call    cs:__imp_RegGetValueW
0x180029cd9  nop     dword ptr [rax+rax+00h]
0x180029cde  test    eax, eax
0x180029ce0  jz      short loc_180029CFA
0x180029ce2  xor     eax, eax
0x180029ce4  mov     rcx, [rbp+hKey]; hKey
0x180029ce8  mov     cs:g_fTracingOn, eax
0x180029cee  test    rcx, rcx
0x180029cf1  jnz     short loc_180029D12
0x180029cf3  add     rsp, 40h
0x180029cf7  pop     rbp
0x180029cf8  retn
0x180029cfa  call    cs:__imp_GetCurrentProcessId
0x180029d01  nop     dword ptr [rax+rax+00h]
0x180029d06  cmp     [rbp+pvData], eax
0x180029d09  jnz     short loc_180029CE2
0x180029d0b  mov     eax, 1
0x180029d10  jmp     short loc_180029CE4
0x180029d12  call    cs:__imp_RegCloseKey
0x180029d19  nop     dword ptr [rax+rax+00h]
0x180029d1e  jmp     short loc_180029CF3
```
