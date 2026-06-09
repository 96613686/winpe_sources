# GetPreshutdownTimeout

- ea: `0x180011c8c`
- end: `0x180011d32`
- name: `GetPreshutdownTimeout`
- size: `166`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18000ea20`

## callees

- `0x180011c8c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011d14`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011d14`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180011d08`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180011d08`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011cd3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011cd3`

## string_xrefs

- `0x180011cb7`: `SYSTEM\CurrentControlSet\Services\DeviceInstall`

## pseudocode

```c
__int64 GetPreshutdownTimeout()
{
  LSTATUS v0; // ebx
  DWORD cbData; // [rsp+50h] [rbp+18h] BYREF
  DWORD Type; // [rsp+58h] [rbp+20h] BYREF
  unsigned int Data; // [rsp+60h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+30h] BYREF

  hKey = 0;
  Type = 0;
  cbData = 0;
  Data = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Services\\DeviceInstall", 0, 1u, &hKey) )
    return Data;
  cbData = 4;
  v0 = RegQueryValueExW(hKey, L"PreshutdownTimeout", 0, &Type, (LPBYTE)&Data, &cbData);
  RegCloseKey(hKey);
  if ( !v0 && Type == 4 )
    return Data;
  else
    return 0;
}

```

## disassembly

```asm
0x180011c8c  push    rbp
0x180011c8e  push    rbx
0x180011c8f  mov     rbp, rsp
0x180011c92  sub     rsp, 38h
0x180011c96  lea     rax, [rbp+hKey]
0x180011c9a  mov     [rbp+hKey], 0
0x180011ca2  mov     r9d, 1; samDesired
0x180011ca8  mov     [rsp+38h+phkResult], rax; phkResult
0x180011cad  xor     r8d, r8d; ulOptions
0x180011cb0  mov     [rbp+Type], 0
0x180011cb7  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\De"...
0x180011cbe  mov     [rbp+cbData], 0
0x180011cc5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180011ccc  mov     [rbp+Data], 0
0x180011cd3  call    cs:__imp_RegOpenKeyExW
0x180011cd9  test    eax, eax
0x180011cdb  jnz     short loc_180011D28
0x180011cdd  mov     rcx, [rbp+hKey]; hKey
0x180011ce1  lea     rax, [rbp+cbData]
0x180011ce5  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180011cea  lea     r9, [rbp+Type]; lpType
0x180011cee  lea     rax, [rbp+Data]
0x180011cf2  mov     [rbp+cbData], 4
0x180011cf9  xor     r8d, r8d; lpReserved
0x180011cfc  mov     [rsp+38h+phkResult], rax; lpData
0x180011d01  lea     rdx, aPreshutdowntim; "PreshutdownTimeout"
0x180011d08  call    cs:__imp_RegQueryValueExW
0x180011d0e  mov     rcx, [rbp+hKey]; hKey
0x180011d12  mov     ebx, eax
0x180011d14  call    cs:__imp_RegCloseKey
0x180011d1a  test    ebx, ebx
0x180011d1c  jnz     short loc_180011D24
0x180011d1e  cmp     [rbp+Type], 4
0x180011d22  jz      short loc_180011D28
0x180011d24  xor     eax, eax
0x180011d26  jmp     short loc_180011D2B
0x180011d28  mov     eax, [rbp+Data]
0x180011d2b  add     rsp, 38h
0x180011d2f  pop     rbx
0x180011d30  pop     rbp
0x180011d31  retn
```
