# ColorFiltering::ColorFilterHelper::UpdateTransferSettingsGain(ulong)

- ea: `0x14001b470`
- end: `0x14001b5ec`
- name: `?UpdateTransferSettingsGain@ColorFilterHelper@ColorFiltering@@SAXK@Z`
- size: `380`
- prototype: `void __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14001aa78`

## callees

- `0x1400045a0`
- `0x140004ba4`
- `0x140013d0c`
- `0x140019a74`
- `0x14001b470`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14001b5ae`
- `ADVAPI32!RegOpenKeyExW` at `0x14001b5ae`
- `ADVAPI32!RegCloseKey` at `0x14001b4aa`
- `ADVAPI32!RegCloseKey` at `0x14001b570`
- `ADVAPI32!RegCloseKey` at `0x14001b4aa`
- `ADVAPI32!RegCloseKey` at `0x14001b570`
- `ADVAPI32!RegSetValueExW` at `0x14001b537`
- `ADVAPI32!RegSetValueExW` at `0x14001b537`
- `ADVAPI32!RegCreateKeyExW` at `0x14001b507`
- `ADVAPI32!RegCreateKeyExW` at `0x14001b507`
- `ADVAPI32!RegDeleteTreeW` at `0x14001b5c9`
- `ADVAPI32!RegDeleteTreeW` at `0x14001b5c9`

## string_xrefs

- `0x14001b5a0`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig\`
- `0x14001b4f9`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig\colorfiltering`

## pseudocode

```c
void __fastcall ColorFiltering::ColorFilterHelper::UpdateTransferSettingsGain(int a1)
{
  int Data; // [rsp+60h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+18h] BYREF

  Data = a1;
  if ( ColorFiltering::ColorFilterHelper::IsActive() )
  {
    hKey = 0;
    if ( !RegCreateKeyExW(
            HKEY_CURRENT_USER,
            L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Accessibility\\ATConfig\\colorfiltering",
            0,
            0,
            1u,
            3u,
            0,
            &hKey,
            0) )
      RegSetValueExW(hKey, L"Gain", 0, 4u, (const BYTE *)&Data, 4u);
  }
  else
  {
    hKey = 0;
    if ( !RegOpenKeyExW(
            HKEY_CURRENT_USER,
            L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Accessibility\\ATConfig\\",
            0,
            0xF003Fu,
            &hKey) )
      RegDeleteTreeW(hKey, L"colorfiltering");
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
}

```

## disassembly

```asm
0x14001b470  mov     [rsp-8+arg_18], rbx
0x14001b475  push    rbp
0x14001b476  mov     rbp, rsp
0x14001b479  sub     rsp, 50h
0x14001b47d  mov     [rbp+Data], ecx
0x14001b480  call    ?IsActive@ColorFilterHelper@ColorFiltering@@SA_NXZ; ColorFiltering::ColorFilterHelper::IsActive(void)
0x14001b485  test    al, al
0x14001b487  jz      loc_14001B553
0x14001b48d  mov     [rbp+hKey], 0
0x14001b495  mov     rbx, [rbp+hKey]
0x14001b499  test    rbx, rbx
0x14001b49c  jz      short loc_14001B4C0
0x14001b49e  lea     rcx, [rbp+arg_10]; this
0x14001b4a2  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14001b4a7  mov     rcx, rbx; hKey
0x14001b4aa  call    cs:__imp_RegCloseKey
0x14001b4b1  nop     dword ptr [rax+rax+00h]
0x14001b4b6  lea     rcx, [rbp+arg_10]; this
0x14001b4ba  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14001b4bf  nop
0x14001b4c0  mov     [rbp+hKey], 0
0x14001b4c8  mov     [rsp+50h+lpdwDisposition], 0; lpdwDisposition
0x14001b4d1  lea     rax, [rbp+hKey]
0x14001b4d5  mov     [rsp+50h+phkResult], rax; phkResult
0x14001b4da  mov     [rsp+50h+lpSecurityAttributes], 0; lpSecurityAttributes
0x14001b4e3  mov     [rsp+50h+samDesired], 3; samDesired
0x14001b4eb  mov     [rsp+50h+dwOptions], 1; dwOptions
0x14001b4f3  xor     r9d, r9d; lpClass
0x14001b4f6  xor     r8d, r8d; Reserved
0x14001b4f9  lea     rdx, aSoftwareMicros_12; "Software\\Microsoft\\Windows NT\\Curren"...
0x14001b500  mov     rcx, 0FFFFFFFF80000001h; hKey
0x14001b507  call    cs:__imp_RegCreateKeyExW
0x14001b50e  nop     dword ptr [rax+rax+00h]
0x14001b513  test    eax, eax
0x14001b515  jnz     short loc_14001B544
0x14001b517  lea     r9d, [rax+4]; dwType
0x14001b51b  mov     [rsp+50h+samDesired], r9d; cbData
0x14001b520  lea     rax, [rbp+Data]
0x14001b524  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x14001b529  xor     r8d, r8d; Reserved
0x14001b52c  lea     rdx, aGain; "Gain"
0x14001b533  mov     rcx, [rbp+hKey]; hKey
0x14001b537  call    cs:__imp_RegSetValueExW
0x14001b53e  nop     dword ptr [rax+rax+00h]
0x14001b543  nop
0x14001b544  lea     rcx, [rbp+hKey]
0x14001b548  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14001b54d  nop
0x14001b54e  jmp     loc_14001B5E0
0x14001b553  mov     [rbp+hKey], 0
0x14001b55b  mov     rbx, [rbp+hKey]
0x14001b55f  test    rbx, rbx
0x14001b562  jz      short loc_14001B586
0x14001b564  lea     rcx, [rbp+arg_10]; this
0x14001b568  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14001b56d  mov     rcx, rbx; hKey
0x14001b570  call    cs:__imp_RegCloseKey
0x14001b577  nop     dword ptr [rax+rax+00h]
0x14001b57c  lea     rcx, [rbp+arg_10]; this
0x14001b580  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14001b585  nop
0x14001b586  mov     [rbp+hKey], 0
0x14001b58e  lea     rax, [rbp+hKey]
0x14001b592  mov     qword ptr [rsp+50h+dwOptions], rax; phkResult
0x14001b597  mov     r9d, 0F003Fh; samDesired
0x14001b59d  xor     r8d, r8d; ulOptions
0x14001b5a0  lea     rdx, aSoftwareMicros_14; "Software\\Microsoft\\Windows NT\\Curren"...
0x14001b5a7  mov     rcx, 0FFFFFFFF80000001h; hKey
0x14001b5ae  call    cs:__imp_RegOpenKeyExW
0x14001b5b5  nop     dword ptr [rax+rax+00h]
0x14001b5ba  test    eax, eax
0x14001b5bc  jnz     short loc_14001B5D6
0x14001b5be  lea     rdx, aColorfiltering_0; "colorfiltering"
0x14001b5c5  mov     rcx, [rbp+hKey]; hKey
0x14001b5c9  call    cs:__imp_RegDeleteTreeW
0x14001b5d0  nop     dword ptr [rax+rax+00h]
0x14001b5d5  nop
0x14001b5d6  lea     rcx, [rbp+hKey]
0x14001b5da  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14001b5df  nop
0x14001b5e0  mov     rbx, [rsp+50h+arg_18]
0x14001b5e5  add     rsp, 50h
0x14001b5e9  pop     rbp
0x14001b5ea  retn
```
