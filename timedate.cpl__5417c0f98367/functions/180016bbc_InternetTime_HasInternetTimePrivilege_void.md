# InternetTime_HasInternetTimePrivilege(void)

- ea: `0x180016bbc`
- end: `0x180016cc3`
- name: `?InternetTime_HasInternetTimePrivilege@@YAJXZ`
- size: `263`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18001d1d0`

## callees

- `0x180016bbc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016bf8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016bf8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180016c4d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180016c9e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180016c4d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180016c9e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016c0b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016c5c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016cad`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016c0b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016c5c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016cad`

## string_xrefs

- `0x180016be3`: `System\CurrentControlSet\Services\W32Time\Parameters`

## pseudocode

```c
__int64 InternetTime_HasInternetTimePrivilege(void)
{
  unsigned int v0; // ebx
  HKEY hKey; // [rsp+60h] [rbp+8h] BYREF

  hKey = 0;
  v0 = 1;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Services\\W32Time\\Parameters",
          0,
          0x20006u,
          &hKey) )
  {
    RegCloseKey(hKey);
    if ( !RegCreateKeyExW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\DateTime",
            0,
            0,
            0,
            0x20006u,
            0,
            &hKey,
            0) )
    {
      RegCloseKey(hKey);
      if ( !RegCreateKeyExW(
              HKEY_LOCAL_MACHINE,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\DateTime\\Servers",
              0,
              0,
              0,
              0x20006u,
              0,
              &hKey,
              0) )
      {
        RegCloseKey(hKey);
        return 0;
      }
    }
  }
  return v0;
}

```

## disassembly

```asm
0x180016bbc  mov     r11, rsp
0x180016bbf  mov     [r11+10h], rbx
0x180016bc3  push    r14
0x180016bc5  sub     rsp, 50h
0x180016bc9  lea     rax, [r11+8]
0x180016bcd  mov     qword ptr [r11+8], 0
0x180016bd5  mov     r14, 0FFFFFFFF80000002h
0x180016bdc  mov     [r11-38h], rax
0x180016be0  mov     rcx, r14; hKey
0x180016be3  lea     rdx, aSystemCurrentc_1; "System\\CurrentControlSet\\Services\\W3"...
0x180016bea  mov     r9d, 20006h; samDesired
0x180016bf0  xor     r8d, r8d; ulOptions
0x180016bf3  mov     ebx, 1
0x180016bf8  call    cs:__imp_RegOpenKeyExW
0x180016bfe  test    eax, eax
0x180016c00  jnz     loc_180016CB5
0x180016c06  mov     rcx, [rsp+58h+hKey]; hKey
0x180016c0b  call    cs:__imp_RegCloseKey
0x180016c11  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x180016c1a  lea     rax, [rsp+58h+hKey]
0x180016c1f  mov     [rsp+58h+phkResult], rax; phkResult
0x180016c24  lea     rdx, pszPrefix; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180016c2b  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180016c34  xor     r9d, r9d; lpClass
0x180016c37  mov     [rsp+58h+samDesired], 20006h; samDesired
0x180016c3f  xor     r8d, r8d; Reserved
0x180016c42  mov     rcx, r14; hKey
0x180016c45  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180016c4d  call    cs:__imp_RegCreateKeyExW
0x180016c53  test    eax, eax
0x180016c55  jnz     short loc_180016CB5
0x180016c57  mov     rcx, [rsp+58h+hKey]; hKey
0x180016c5c  call    cs:__imp_RegCloseKey
0x180016c62  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x180016c6b  lea     rax, [rsp+58h+hKey]
0x180016c70  mov     [rsp+58h+phkResult], rax; phkResult
0x180016c75  lea     rdx, pszSubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180016c7c  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180016c85  xor     r9d, r9d; lpClass
0x180016c88  mov     [rsp+58h+samDesired], 20006h; samDesired
0x180016c90  xor     r8d, r8d; Reserved
0x180016c93  mov     rcx, r14; hKey
0x180016c96  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180016c9e  call    cs:__imp_RegCreateKeyExW
0x180016ca4  test    eax, eax
0x180016ca6  jnz     short loc_180016CB5
0x180016ca8  mov     rcx, [rsp+58h+hKey]; hKey
0x180016cad  call    cs:__imp_RegCloseKey
0x180016cb3  xor     ebx, ebx
0x180016cb5  mov     eax, ebx
0x180016cb7  mov     rbx, [rsp+58h+arg_8]
0x180016cbc  add     rsp, 50h
0x180016cc0  pop     r14
0x180016cc2  retn
```
