# Theming::SetSoundRedirectionPath(ushort const *)

- ea: `0x1800d79f4`
- end: `0x1800d7c4a`
- name: `?SetSoundRedirectionPath@Theming@@YAXPEBG@Z`
- size: `598`
- prototype: `void __fastcall(BYTE *lpData, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18011e83c`

## callees

- `0x1800d79f4`
- `0x1800d7c50`
- `0x1803bc514`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800d7b86`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800d7bf0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800d7b86`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800d7bf0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d7b6d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d7bd6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d7b6d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d7bd6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800d7a67`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800d7afd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800d7a67`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800d7afd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800d7a99`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800d7b30`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800d7a99`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800d7b30`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d7ab0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d7b95`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d7c03`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d7ab0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d7b95`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d7c03`

## string_xrefs

- `0x1800d7c30`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\dynamic_config.h`
- `0x1806f2514`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\dynamic_config.h`
- `0x1806f252d`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\dynamic_config.h`

## pseudocode

```c
void __fastcall Theming::SetSoundRedirectionPath(BYTE *lpData, const unsigned __int16 *a2)
{
  __int64 v3; // r14
  __int64 v4; // rsi
  HKEY *phkResult; // rax
  unsigned int Key; // eax
  __int64 v7; // rdx
  HKEY *v8; // rax
  unsigned int v9; // eax
  __int64 v10; // rdx
  HKEY *v11; // rax
  HKEY *v12; // rax
  unsigned int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // rdx
  unsigned int dwOptions; // [rsp+20h] [rbp-30h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-30h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  HKEY hKey; // [rsp+70h] [rbp+20h] BYREF

  hKey = 0;
  if ( lpData )
  {
    v3 = -1;
    v4 = -1;
    do
      ++v4;
    while ( *(_WORD *)&lpData[2 * v4] );
    phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(
                          &hKey,
                          a2);
    Key = RegCreateKeyExW(HKEY_CURRENT_USER, L"AppEvents\\schemes", 0, 0, 0, 2u, 0, phkResult, 0);
    if ( Key )
    {
      v15 = 20;
    }
    else
    {
      Key = RegSetValueExW(hKey, L"packagebase", 0, 1u, lpData, 2 * v4 + 2);
      if ( !Key )
        goto LABEL_6;
      v15 = 38;
    }
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)v15,
      (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\dynamic_config.h",
      (const char *)Key,
      dwOptions);
LABEL_6:
    if ( hKey )
      RegCloseKey(hKey);
    do
      ++v3;
    while ( *(_WORD *)&lpData[2 * v3] );
    hKey = 0;
    v8 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(
                   &hKey,
                   v7);
    v9 = RegCreateKeyExW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\Windows\\CurrentVersion\\EditionOverrides",
           0,
           0,
           0,
           2u,
           0,
           v8,
           0);
    if ( v9 )
    {
      v10 = 20;
    }
    else
    {
      v9 = RegSetValueExW(hKey, L"packagebase", 0, 1u, lpData, 2 * v3 + 2);
      if ( !v9 )
        goto LABEL_14;
      v10 = 38;
    }
    goto LABEL_27;
  }
  v12 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(
                  &hKey,
                  a2);
  v13 = RegOpenKeyExW(HKEY_CURRENT_USER, L"AppEvents\\schemes", 0, 2u, v12);
  if ( v13 )
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0x1D,
      (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\dynamic_config.h",
      (const char *)v13,
      dwOptionsb);
  else
    RegDeleteValueW(hKey, L"packagebase");
  if ( hKey )
    RegCloseKey(hKey);
  hKey = 0;
  v11 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(
                  &hKey,
                  v14);
  v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows\\CurrentVersion\\EditionOverrides", 0, 2u, v11);
  if ( !v9 )
  {
    RegDeleteValueW(hKey, L"packagebase");
    goto LABEL_14;
  }
  v10 = 29;
LABEL_27:
  wil::details::in1diag3::_Log_Win32(
    retaddr,
    (void *)v10,
    (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\dynamic_config.h",
    (const char *)v9,
    dwOptionsa);
LABEL_14:
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x1800d79f4  mov     [rsp-18h+arg_8], rsi
0x1800d79f9  mov     [rsp-18h+arg_10], rdi
0x1800d79fe  push    rbp
0x1800d79ff  push    r12
0x1800d7a01  push    r14
0x1800d7a03  mov     rbp, rsp
0x1800d7a06  sub     rsp, 50h
0x1800d7a0a  xor     r12d, r12d
0x1800d7a0d  mov     rdi, rcx
0x1800d7a10  mov     [rbp+hKey], r12
0x1800d7a14  test    rcx, rcx
0x1800d7a17  jz      loc_1800D7BB1
0x1800d7a1d  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800d7a21  mov     rsi, r14
0x1800d7a24  inc     rsi
0x1800d7a27  cmp     [rcx+rsi*2], r12w
0x1800d7a2c  jnz     short loc_1800D7A24
0x1800d7a2e  lea     rcx, [rbp+hKey]
0x1800d7a32  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1800d7a37  mov     [rsp+50h+lpdwDisposition], r12; lpdwDisposition
0x1800d7a3c  lea     rdx, aAppeventsSchem; "AppEvents\\schemes"
0x1800d7a43  mov     [rsp+50h+phkResult], rax; phkResult
0x1800d7a48  xor     r9d, r9d; lpClass
0x1800d7a4b  mov     [rsp+50h+lpSecurityAttributes], r12; lpSecurityAttributes
0x1800d7a50  xor     r8d, r8d; Reserved
0x1800d7a53  mov     [rsp+50h+samDesired], 2; samDesired
0x1800d7a5b  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800d7a62  mov     [rsp+50h+dwOptions], r12d; unsigned int
0x1800d7a67  call    cs:__imp_RegCreateKeyExW
0x1800d7a6d  test    eax, eax
0x1800d7a6f  jnz     loc_1800D7C0E
0x1800d7a75  mov     rcx, [rbp+hKey]; hKey
0x1800d7a79  lea     eax, ds:2[rsi*2]
0x1800d7a80  mov     [rsp+50h+samDesired], eax; cbData
0x1800d7a84  lea     rdx, aPackagebase; "packagebase"
0x1800d7a8b  mov     r9d, 1; dwType
0x1800d7a91  mov     qword ptr [rsp+50h+dwOptions], rdi; lpData
0x1800d7a96  xor     r8d, r8d; Reserved
0x1800d7a99  call    cs:__imp_RegSetValueExW
0x1800d7a9f  test    eax, eax
0x1800d7aa1  jnz     loc_1800D7C18
0x1800d7aa7  mov     rcx, [rbp+hKey]; hKey
0x1800d7aab  test    rcx, rcx
0x1800d7aae  jz      short loc_1800D7AB6
0x1800d7ab0  call    cs:__imp_RegCloseKey
0x1800d7ab6  inc     r14
0x1800d7ab9  cmp     [rdi+r14*2], r12w
0x1800d7abe  jnz     short loc_1800D7AB6
0x1800d7ac0  lea     rcx, [rbp+hKey]
0x1800d7ac4  mov     [rbp+hKey], r12
0x1800d7ac8  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1800d7acd  mov     [rsp+50h+lpdwDisposition], r12; lpdwDisposition
0x1800d7ad2  lea     rdx, aSoftwareMicros_94; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800d7ad9  mov     [rsp+50h+phkResult], rax; phkResult
0x1800d7ade  xor     r9d, r9d; lpClass
0x1800d7ae1  mov     [rsp+50h+lpSecurityAttributes], r12; lpSecurityAttributes
0x1800d7ae6  xor     r8d, r8d; Reserved
0x1800d7ae9  mov     [rsp+50h+samDesired], 2; samDesired
0x1800d7af1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800d7af8  mov     [rsp+50h+dwOptions], r12d; dwOptions
0x1800d7afd  call    cs:__imp_RegCreateKeyExW
0x1800d7b03  test    eax, eax
0x1800d7b05  jnz     loc_1800D7C22
0x1800d7b0b  mov     rcx, [rbp+hKey]; hKey
0x1800d7b0f  lea     eax, ds:2[r14*2]
0x1800d7b17  mov     [rsp+50h+samDesired], eax; cbData
0x1800d7b1b  lea     rdx, aPackagebase; "packagebase"
0x1800d7b22  mov     r9d, 1; dwType
0x1800d7b28  mov     qword ptr [rsp+50h+dwOptions], rdi; unsigned int
0x1800d7b2d  xor     r8d, r8d; Reserved
0x1800d7b30  call    cs:__imp_RegSetValueExW
0x1800d7b36  test    eax, eax
0x1800d7b38  jz      short loc_1800D7B8C
0x1800d7b3a  mov     edx, 26h ; '&'; void *
0x1800d7b3f  jmp     loc_1806F2529
0x1800d7b44  lea     rcx, [rbp+hKey]
0x1800d7b48  mov     [rbp+hKey], r12
0x1800d7b4c  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1800d7b51  mov     r9d, 2; samDesired
0x1800d7b57  mov     qword ptr [rsp+50h+dwOptions], rax; phkResult
0x1800d7b5c  xor     r8d, r8d; ulOptions
0x1800d7b5f  lea     rdx, aSoftwareMicros_94; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800d7b66  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800d7b6d  call    cs:__imp_RegOpenKeyExW
0x1800d7b73  test    eax, eax
0x1800d7b75  jnz     loc_1800D7C43
0x1800d7b7b  mov     rcx, [rbp+hKey]; hKey
0x1800d7b7f  lea     rdx, aPackagebase; "packagebase"
0x1800d7b86  call    cs:__imp_RegDeleteValueW
0x1800d7b8c  mov     rcx, [rbp+hKey]; hKey
0x1800d7b90  test    rcx, rcx
0x1800d7b93  jz      short loc_1800D7B9B
0x1800d7b95  call    cs:__imp_RegCloseKey
0x1800d7b9b  lea     r11, [rsp+50h+var_s0]
0x1800d7ba0  mov     rsi, [r11+28h]
0x1800d7ba4  mov     rdi, [r11+30h]
0x1800d7ba8  mov     rsp, r11
0x1800d7bab  pop     r14
0x1800d7bad  pop     r12
0x1800d7baf  pop     rbp
0x1800d7bb0  retn
0x1800d7bb1  lea     rcx, [rbp+hKey]
0x1800d7bb5  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1800d7bba  mov     r9d, 2; samDesired
0x1800d7bc0  mov     qword ptr [rsp+50h+dwOptions], rax; unsigned int
0x1800d7bc5  xor     r8d, r8d; ulOptions
0x1800d7bc8  lea     rdx, aAppeventsSchem; "AppEvents\\schemes"
0x1800d7bcf  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800d7bd6  call    cs:__imp_RegOpenKeyExW
0x1800d7bdc  mov     edi, 1Dh
0x1800d7be1  test    eax, eax
0x1800d7be3  jnz     short loc_1800D7C2C
0x1800d7be5  mov     rcx, [rbp+hKey]; hKey
0x1800d7be9  lea     rdx, aPackagebase; "packagebase"
0x1800d7bf0  call    cs:__imp_RegDeleteValueW
0x1800d7bf6  mov     rcx, [rbp+hKey]; hKey
0x1800d7bfa  test    rcx, rcx
0x1800d7bfd  jz      loc_1800D7B44
0x1800d7c03  call    cs:__imp_RegCloseKey
0x1800d7c09  jmp     loc_1800D7B44
0x1800d7c0e  mov     edx, 14h; void *
0x1800d7c13  jmp     loc_1806F2510
0x1800d7c18  mov     edx, 26h ; '&'
0x1800d7c1d  jmp     loc_1806F2510
0x1800d7c22  mov     edx, 14h
0x1800d7c27  jmp     loc_1806F2529
0x1800d7c2c  mov     rcx, [rbp+18h]; this
0x1800d7c30  lea     r8, aShellcommondes_5; "ShellCommonDesktopBase\\Internal\\Shell"...
0x1800d7c37  mov     r9d, eax; char *
0x1800d7c3a  mov     edx, edi; void *
0x1800d7c3c  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x1800d7c41  jmp     short loc_1800D7BF6
0x1800d7c43  mov     edx, edi
0x1800d7c45  jmp     loc_1806F2529
0x1806f2510  mov     rcx, [rbp+18h]; this
0x1806f2514  lea     r8, aShellcommondes_5; "ShellCommonDesktopBase\\Internal\\Shell"...
0x1806f251b  mov     r9d, eax; char *
0x1806f251e  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x1806f2523  nop
0x1806f2524  jmp     loc_1800D7AA7
0x1806f2529  mov     rcx, [rbp+18h]; this
0x1806f252d  lea     r8, aShellcommondes_5; "ShellCommonDesktopBase\\Internal\\Shell"...
0x1806f2534  mov     r9d, eax; char *
0x1806f2537  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x1806f253c  nop
0x1806f253d  jmp     loc_1800D7B8C
```
