# OSDeploymentInformationFactory::ShutdownJITCOMServer(void)

- ea: `0x18001c230`
- end: `0x18001c31c`
- name: `?ShutdownJITCOMServer@OSDeploymentInformationFactory@@QEAAXXZ`
- size: `236`
- prototype: `void __fastcall(OSDeploymentInformationFactory *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180016b58`
- `0x1800272ac`

## callees

- `0x18001c230`
- `0x1800311f4`
- `0x180042630`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c29e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c303`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c29e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c303`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c272`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c2ce`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c272`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c2ce`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18001c28e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18001c2ea`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18001c28e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18001c2ea`

## string_xrefs

- `0x18001c2c0`: `Software\Classes\CLSID`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall OSDeploymentInformationFactory::ShutdownJITCOMServer(WCHAR *this)
{
  unsigned int v2; // edx
  HKEY hKey; // [rsp+30h] [rbp-18h] BYREF

  hKey = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Classes\\AppID", 0, 0x20006u, &hKey) >= 0 )
    RegDeleteKeyExW(hKey, this + 196, 0, 0);
  if ( hKey )
    RegCloseKey(hKey);
  hKey = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Classes\\CLSID", 0, 0x20006u, &hKey) >= 0 )
    RegDeleteKeyExW(hKey, this + 149, 0, 0);
  CWuaClassFactoryBase::UnregisterClassFactory((CWuaClassFactoryBase *)this, v2);
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x18001c230  push    rbx
0x18001c232  sub     rsp, 40h
0x18001c236  mov     rax, cs:__security_cookie
0x18001c23d  xor     rax, rsp
0x18001c240  mov     [rsp+48h+var_10], rax
0x18001c245  mov     rbx, rcx
0x18001c248  mov     [rsp+48h+hKey], 0
0x18001c251  lea     rax, [rsp+48h+hKey]
0x18001c256  mov     [rsp+48h+phkResult], rax; phkResult
0x18001c25b  mov     r9d, 20006h; samDesired
0x18001c261  xor     r8d, r8d; ulOptions
0x18001c264  lea     rdx, SubKey; "Software\\Classes\\AppID"
0x18001c26b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001c272  call    cs:__imp_RegOpenKeyExW
0x18001c278  test    eax, eax
0x18001c27a  js      short loc_18001C294
0x18001c27c  lea     rdx, [rbx+188h]; lpSubKey
0x18001c283  xor     r9d, r9d; Reserved
0x18001c286  xor     r8d, r8d; samDesired
0x18001c289  mov     rcx, [rsp+48h+hKey]; hKey
0x18001c28e  call    cs:__imp_RegDeleteKeyExW
0x18001c294  mov     rcx, [rsp+48h+hKey]; hKey
0x18001c299  test    rcx, rcx
0x18001c29c  jz      short loc_18001C2A4
0x18001c29e  call    cs:__imp_RegCloseKey
0x18001c2a4  mov     [rsp+48h+hKey], 0
0x18001c2ad  lea     rax, [rsp+48h+hKey]
0x18001c2b2  mov     [rsp+48h+phkResult], rax; phkResult
0x18001c2b7  mov     r9d, 20006h; samDesired
0x18001c2bd  xor     r8d, r8d; ulOptions
0x18001c2c0  lea     rdx, aSoftwareClasse; "Software\\Classes\\CLSID"
0x18001c2c7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001c2ce  call    cs:__imp_RegOpenKeyExW
0x18001c2d4  test    eax, eax
0x18001c2d6  js      short loc_18001C2F0
0x18001c2d8  lea     rdx, [rbx+12Ah]; lpSubKey
0x18001c2df  xor     r9d, r9d; Reserved
0x18001c2e2  xor     r8d, r8d; samDesired
0x18001c2e5  mov     rcx, [rsp+48h+hKey]; hKey
0x18001c2ea  call    cs:__imp_RegDeleteKeyExW
0x18001c2f0  mov     rcx, rbx; this
0x18001c2f3  call    ?UnregisterClassFactory@CWuaClassFactoryBase@@QEAAJK@Z; CWuaClassFactoryBase::UnregisterClassFactory(ulong)
0x18001c2f8  nop
0x18001c2f9  mov     rcx, [rsp+48h+hKey]; hKey
0x18001c2fe  test    rcx, rcx
0x18001c301  jz      short loc_18001C309
0x18001c303  call    cs:__imp_RegCloseKey
0x18001c309  mov     rcx, [rsp+48h+var_10]
0x18001c30e  xor     rcx, rsp; StackCookie
0x18001c311  call    __security_check_cookie
0x18001c316  add     rsp, 40h
0x18001c31a  pop     rbx
0x18001c31b  retn
```
