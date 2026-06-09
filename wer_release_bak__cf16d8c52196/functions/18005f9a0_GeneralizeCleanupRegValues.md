# GeneralizeCleanupRegValues

- ea: `0x18005f9a0`
- end: `0x18005fa5d`
- name: `GeneralizeCleanupRegValues`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005fc60`

## callees

- `0x18001c6d8`
- `0x18001f8c8`
- `0x18005f9a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18005f9f7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18005fa48`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18005f9f7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18005fa48`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005f9dc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005fa2d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005f9dc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005fa2d`

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
0x18005f9a0  sub     rsp, 38h
0x18005f9a4  lea     rcx, [rsp+38h+hKey]
0x18005f9a9  mov     [rsp+38h+arg_8], 0
0x18005f9b2  mov     [rsp+38h+hKey], 0
0x18005f9bb  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x18005f9c0  mov     r9d, 2; samDesired
0x18005f9c6  mov     [rsp+38h+phkResult], rax; phkResult
0x18005f9cb  xor     r8d, r8d; ulOptions
0x18005f9ce  lea     rdx, aSoftwareMicros_20; "SOFTWARE\\Microsoft\\SQMClient"
0x18005f9d5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005f9dc  call    cs:__imp_RegOpenKeyExW
0x18005f9e2  test    eax, eax
0x18005f9e4  jnz     short loc_18005F9FD
0x18005f9e6  mov     rcx, [rsp+38h+hKey]; hKey
0x18005f9eb  test    rcx, rcx
0x18005f9ee  jz      short loc_18005F9FD
0x18005f9f0  lea     rdx, aMachineid; "MachineID"
0x18005f9f7  call    cs:__imp_RegDeleteValueW
0x18005f9fd  lea     rcx, [rsp+38h+hKey]
0x18005fa02  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x18005fa07  lea     rcx, [rsp+38h+arg_8]
0x18005fa0c  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x18005fa11  mov     r9d, 2; samDesired
0x18005fa17  mov     [rsp+38h+phkResult], rax; phkResult
0x18005fa1c  xor     r8d, r8d; ulOptions
0x18005fa1f  lea     rdx, aSoftwareMicros_25; "Software\\Microsoft\\Windows\\Windows E"...
0x18005fa26  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005fa2d  call    cs:__imp_RegOpenKeyExW
0x18005fa33  test    eax, eax
0x18005fa35  jnz     short loc_18005FA4E
0x18005fa37  mov     rcx, [rsp+38h+arg_8]; hKey
0x18005fa3c  test    rcx, rcx
0x18005fa3f  jz      short loc_18005FA4E
0x18005fa41  lea     rdx, aNewuserdefault; "NewUserDefaultConsent"
0x18005fa48  call    cs:__imp_RegDeleteValueW
0x18005fa4e  lea     rcx, [rsp+38h+arg_8]
0x18005fa53  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x18005fa58  add     rsp, 38h
0x18005fa5c  retn
```
