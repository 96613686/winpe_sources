# PublisherManifestConfig::ReadConfig(_GUID const &)

- ea: `0x180009710`
- end: `0x180009877`
- name: `?ReadConfig@PublisherManifestConfig@@UEAAKAEBU_GUID@@@Z`
- size: `359`
- prototype: `__int64 __fastcall(wchar_t **this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009570`

## callees

- `0x180009710`
- `0x180009880`
- `0x180009a34`
- `0x180009af4`
- `0x1800207c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009771`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009839`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009771`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009839`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009792`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000986c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009792`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000986c`

## pseudocode

```c
__int64 __fastcall PublisherManifestConfig::ReadConfig(wchar_t **this, const struct _GUID *a2)
{
  unsigned int RegistryString; // ebx
  PublisherManifestConfig *v5; // rcx
  PublisherManifestConfig *v6; // rcx
  PublisherManifestConfig *v7; // rcx
  PublisherManifestConfig *v8; // rcx
  HKEY phkResult; // [rsp+30h] [rbp-29h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-21h] BYREF
  WCHAR SubKey[48]; // [rsp+40h] [rbp-19h] BYREF

  hKey = 0;
  phkResult = 0;
  PublisherManifestConfig::GuidToStr((PublisherManifestConfig *)this, a2, SubKey);
  RegistryString = RegOpenKeyExW(
                     HKEY_LOCAL_MACHINE,
                     L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WINEVT\\Publishers",
                     0,
                     0x20119u,
                     &hKey);
  if ( RegistryString
    || (RegistryString = RegOpenKeyExW(hKey, SubKey, 0, 0x20119u, &phkResult)) != 0
    || (RegistryString = PublisherManifestConfig::ReadRegistryString(v7, phkResult, &pszFormat, this + 1)) != 0
    || (RegistryString = PublisherManifestConfig::ReadRegistryString(v8, phkResult, L"ResourceFileName", this + 2)) != 0
    || (RegistryString = PublisherManifestConfig::ReadRegistryString(v5, phkResult, L"MessageFileName", this + 4)) != 0
    || (RegistryString = PublisherManifestConfig::ReadRegistryString(v6, phkResult, L"ParameterFileName", this + 3)) != 0 )
  {
    PublisherManifestConfig::Free((PublisherManifestConfig *)this);
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  return RegistryString;
}

```

## disassembly

```asm
0x180009710  mov     [rsp-8+arg_10], rbx
0x180009715  mov     [rsp-8+arg_18], rdi
0x18000971a  push    rbp
0x18000971b  lea     rbp, [rsp-57h]
0x180009720  sub     rsp, 0B0h
0x180009727  mov     rax, cs:__security_cookie
0x18000972e  xor     rax, rsp
0x180009731  mov     [rbp+57h+var_10], rax
0x180009735  lea     r8, [rbp+57h+SubKey]; wchar_t *
0x180009739  mov     [rbp+57h+hKey], 0
0x180009741  mov     rdi, rcx
0x180009744  mov     [rbp+57h+var_80], 0
0x18000974c  call    ?GuidToStr@PublisherManifestConfig@@AEBAPEA_WAEBU_GUID@@PEA_W@Z; PublisherManifestConfig::GuidToStr(_GUID const &,wchar_t *)
0x180009751  lea     rdx, [rbp+57h+hKey]
0x180009755  mov     r9d, 20119h; samDesired
0x18000975b  mov     [rsp+0B0h+phkResult], rdx; phkResult
0x180009760  xor     r8d, r8d; ulOptions
0x180009763  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18000976a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180009771  call    cs:__imp_RegOpenKeyExW
0x180009777  mov     ebx, eax
0x180009779  test    eax, eax
0x18000977b  jz      loc_18000981F
0x180009781  mov     rcx, rdi; this
0x180009784  call    ?Free@PublisherManifestConfig@@AEAAXXZ; PublisherManifestConfig::Free(void)
0x180009789  mov     rcx, [rbp+57h+hKey]; hKey
0x18000978d  test    rcx, rcx
0x180009790  jz      short loc_180009798
0x180009792  call    cs:__imp_RegCloseKey
0x180009798  mov     rcx, [rbp+57h+var_80]; hKey
0x18000979c  test    rcx, rcx
0x18000979f  jnz     loc_18000986C
0x1800097a5  mov     eax, ebx
0x1800097a7  mov     rcx, [rbp+57h+var_10]
0x1800097ab  xor     rcx, rsp; StackCookie
0x1800097ae  call    __security_check_cookie
0x1800097b3  lea     r11, [rsp+0B0h+var_s0]
0x1800097bb  mov     rbx, [r11+20h]
0x1800097bf  mov     rdi, [r11+28h]
0x1800097c3  mov     rsp, r11
0x1800097c6  pop     rbp
0x1800097c7  retn
0x1800097c8  mov     rdx, [rbp+57h+var_80]; HKEY
0x1800097cc  lea     r9, [rdi+10h]; wchar_t **
0x1800097d0  lea     r8, aResourcefilena; "ResourceFileName"
0x1800097d7  call    ?ReadRegistryString@PublisherManifestConfig@@AEBAKPEAUHKEY__@@PEB_WAEAPEA_W@Z; PublisherManifestConfig::ReadRegistryString(HKEY__ *,wchar_t const *,wchar_t * &)
0x1800097dc  mov     ebx, eax
0x1800097de  test    eax, eax
0x1800097e0  jnz     short loc_180009781
0x1800097e2  mov     rdx, [rbp+57h+var_80]; HKEY
0x1800097e6  lea     r9, [rdi+20h]; wchar_t **
0x1800097ea  lea     r8, aMessagefilenam; "MessageFileName"
0x1800097f1  call    ?ReadRegistryString@PublisherManifestConfig@@AEBAKPEAUHKEY__@@PEB_WAEAPEA_W@Z; PublisherManifestConfig::ReadRegistryString(HKEY__ *,wchar_t const *,wchar_t * &)
0x1800097f6  mov     ebx, eax
0x1800097f8  test    eax, eax
0x1800097fa  jnz     short loc_180009781
0x1800097fc  mov     rdx, [rbp+57h+var_80]; HKEY
0x180009800  lea     r9, [rdi+18h]; wchar_t **
0x180009804  lea     r8, aParameterfilen; "ParameterFileName"
0x18000980b  call    ?ReadRegistryString@PublisherManifestConfig@@AEBAKPEAUHKEY__@@PEB_WAEAPEA_W@Z; PublisherManifestConfig::ReadRegistryString(HKEY__ *,wchar_t const *,wchar_t * &)
0x180009810  mov     ebx, eax
0x180009812  test    eax, eax
0x180009814  jz      loc_180009789
0x18000981a  jmp     loc_180009781
0x18000981f  mov     rcx, [rbp+57h+hKey]; hKey
0x180009823  lea     rax, [rbp+57h+var_80]
0x180009827  mov     r9d, 20119h; samDesired
0x18000982d  mov     [rsp+0B0h+phkResult], rax; phkResult
0x180009832  xor     r8d, r8d; ulOptions
0x180009835  lea     rdx, [rbp+57h+SubKey]; lpSubKey
0x180009839  call    cs:__imp_RegOpenKeyExW
0x18000983f  mov     ebx, eax
0x180009841  test    eax, eax
0x180009843  jnz     loc_180009781
0x180009849  mov     rdx, [rbp+57h+var_80]; HKEY
0x18000984d  lea     r9, [rdi+8]; wchar_t **
0x180009851  lea     r8, pszFormat; wchar_t *
0x180009858  call    ?ReadRegistryString@PublisherManifestConfig@@AEBAKPEAUHKEY__@@PEB_WAEAPEA_W@Z; PublisherManifestConfig::ReadRegistryString(HKEY__ *,wchar_t const *,wchar_t * &)
0x18000985d  mov     ebx, eax
0x18000985f  test    eax, eax
0x180009861  jnz     loc_180009781
0x180009867  jmp     loc_1800097C8
0x18000986c  call    cs:__imp_RegCloseKey
0x180009872  jmp     loc_1800097A5
```
