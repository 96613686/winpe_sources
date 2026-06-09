# GeneralizeCleanupRegValues

- ea: `0x180062174`
- end: `0x18006224a`
- name: `GeneralizeCleanupRegValues`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180062470`

## callees

- `0x18001cb20`
- `0x1800201f0`
- `0x180062174`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800621d1`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18006222e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800621d1`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18006222e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800621b0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006220d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800621b0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006220d`

## pseudocode

```c
__int64 GeneralizeCleanupRegValues()
{
  HKEY *phkResult; // rax
  HKEY *v1; // rax
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF
  HKEY v4; // [rsp+48h] [rbp+10h] BYREF

  v4 = 0;
  hKey = 0;
  phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\SQMClient", 0, 2u, phkResult) && hKey )
    RegDeleteValueW(hKey, L"MachineID");
  tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  v1 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v4);
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Consent", 0, 2u, v1)
    && v4 )
  {
    RegDeleteValueW(v4, L"NewUserDefaultConsent");
  }
  return tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v4);
}

```

## disassembly

```asm
0x180062174  sub     rsp, 38h
0x180062178  lea     rcx, [rsp+38h+hKey]
0x18006217d  mov     [rsp+38h+arg_8], 0
0x180062186  mov     [rsp+38h+hKey], 0
0x18006218f  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x180062194  mov     r9d, 2; samDesired
0x18006219a  mov     [rsp+38h+phkResult], rax; phkResult
0x18006219f  xor     r8d, r8d; ulOptions
0x1800621a2  lea     rdx, aSoftwareMicros_21; "SOFTWARE\\Microsoft\\SQMClient"
0x1800621a9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800621b0  call    cs:__imp_RegOpenKeyExW
0x1800621b7  nop     dword ptr [rax+rax+00h]
0x1800621bc  test    eax, eax
0x1800621be  jnz     short loc_1800621DD
0x1800621c0  mov     rcx, [rsp+38h+hKey]; hKey
0x1800621c5  test    rcx, rcx
0x1800621c8  jz      short loc_1800621DD
0x1800621ca  lea     rdx, aMachineid; "MachineID"
0x1800621d1  call    cs:__imp_RegDeleteValueW
0x1800621d8  nop     dword ptr [rax+rax+00h]
0x1800621dd  lea     rcx, [rsp+38h+hKey]
0x1800621e2  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x1800621e7  lea     rcx, [rsp+38h+arg_8]
0x1800621ec  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x1800621f1  mov     r9d, 2; samDesired
0x1800621f7  mov     [rsp+38h+phkResult], rax; phkResult
0x1800621fc  xor     r8d, r8d; ulOptions
0x1800621ff  lea     rdx, aSoftwareMicros_26; "Software\\Microsoft\\Windows\\Windows E"...
0x180062206  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006220d  call    cs:__imp_RegOpenKeyExW
0x180062214  nop     dword ptr [rax+rax+00h]
0x180062219  test    eax, eax
0x18006221b  jnz     short loc_18006223A
0x18006221d  mov     rcx, [rsp+38h+arg_8]; hKey
0x180062222  test    rcx, rcx
0x180062225  jz      short loc_18006223A
0x180062227  lea     rdx, aNewuserdefault; "NewUserDefaultConsent"
0x18006222e  call    cs:__imp_RegDeleteValueW
0x180062235  nop     dword ptr [rax+rax+00h]
0x18006223a  lea     rcx, [rsp+38h+arg_8]
0x18006223f  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x180062244  add     rsp, 38h
0x180062248  retn
```
