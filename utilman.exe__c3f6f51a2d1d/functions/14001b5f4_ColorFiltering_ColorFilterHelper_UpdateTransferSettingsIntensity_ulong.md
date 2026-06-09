# ColorFiltering::ColorFilterHelper::UpdateTransferSettingsIntensity(ulong)

- ea: `0x14001b5f4`
- end: `0x14001b770`
- name: `?UpdateTransferSettingsIntensity@ColorFilterHelper@ColorFiltering@@SAXK@Z`
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
- `0x14001b5f4`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14001b732`
- `ADVAPI32!RegOpenKeyExW` at `0x14001b732`
- `ADVAPI32!RegCloseKey` at `0x14001b62e`
- `ADVAPI32!RegCloseKey` at `0x14001b6f4`
- `ADVAPI32!RegCloseKey` at `0x14001b62e`
- `ADVAPI32!RegCloseKey` at `0x14001b6f4`
- `ADVAPI32!RegSetValueExW` at `0x14001b6bb`
- `ADVAPI32!RegSetValueExW` at `0x14001b6bb`
- `ADVAPI32!RegCreateKeyExW` at `0x14001b68b`
- `ADVAPI32!RegCreateKeyExW` at `0x14001b68b`
- `ADVAPI32!RegDeleteTreeW` at `0x14001b74d`
- `ADVAPI32!RegDeleteTreeW` at `0x14001b74d`

## string_xrefs

- `0x14001b724`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig\`
- `0x14001b67d`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig\colorfiltering`

## pseudocode

```c
void __fastcall ColorFiltering::ColorFilterHelper::UpdateTransferSettingsIntensity(int a1)
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
      RegSetValueExW(hKey, L"Intensity", 0, 4u, (const BYTE *)&Data, 4u);
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
0x14001b5f4  mov     [rsp-8+arg_18], rbx
0x14001b5f9  push    rbp
0x14001b5fa  mov     rbp, rsp
0x14001b5fd  sub     rsp, 50h
0x14001b601  mov     [rbp+Data], ecx
0x14001b604  call    ?IsActive@ColorFilterHelper@ColorFiltering@@SA_NXZ; ColorFiltering::ColorFilterHelper::IsActive(void)
0x14001b609  test    al, al
0x14001b60b  jz      loc_14001B6D7
0x14001b611  mov     [rbp+hKey], 0
0x14001b619  mov     rbx, [rbp+hKey]
0x14001b61d  test    rbx, rbx
0x14001b620  jz      short loc_14001B644
0x14001b622  lea     rcx, [rbp+arg_10]; this
0x14001b626  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14001b62b  mov     rcx, rbx; hKey
0x14001b62e  call    cs:__imp_RegCloseKey
0x14001b635  nop     dword ptr [rax+rax+00h]
0x14001b63a  lea     rcx, [rbp+arg_10]; this
0x14001b63e  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14001b643  nop
0x14001b644  mov     [rbp+hKey], 0
0x14001b64c  mov     [rsp+50h+lpdwDisposition], 0; lpdwDisposition
0x14001b655  lea     rax, [rbp+hKey]
0x14001b659  mov     [rsp+50h+phkResult], rax; phkResult
0x14001b65e  mov     [rsp+50h+lpSecurityAttributes], 0; lpSecurityAttributes
0x14001b667  mov     [rsp+50h+samDesired], 3; samDesired
0x14001b66f  mov     [rsp+50h+dwOptions], 1; dwOptions
0x14001b677  xor     r9d, r9d; lpClass
0x14001b67a  xor     r8d, r8d; Reserved
0x14001b67d  lea     rdx, aSoftwareMicros_12; "Software\\Microsoft\\Windows NT\\Curren"...
0x14001b684  mov     rcx, 0FFFFFFFF80000001h; hKey
0x14001b68b  call    cs:__imp_RegCreateKeyExW
0x14001b692  nop     dword ptr [rax+rax+00h]
0x14001b697  test    eax, eax
0x14001b699  jnz     short loc_14001B6C8
0x14001b69b  lea     r9d, [rax+4]; dwType
0x14001b69f  mov     [rsp+50h+samDesired], r9d; cbData
0x14001b6a4  lea     rax, [rbp+Data]
0x14001b6a8  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x14001b6ad  xor     r8d, r8d; Reserved
0x14001b6b0  lea     rdx, aIntensity; "Intensity"
0x14001b6b7  mov     rcx, [rbp+hKey]; hKey
0x14001b6bb  call    cs:__imp_RegSetValueExW
0x14001b6c2  nop     dword ptr [rax+rax+00h]
0x14001b6c7  nop
0x14001b6c8  lea     rcx, [rbp+hKey]
0x14001b6cc  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14001b6d1  nop
0x14001b6d2  jmp     loc_14001B764
0x14001b6d7  mov     [rbp+hKey], 0
0x14001b6df  mov     rbx, [rbp+hKey]
0x14001b6e3  test    rbx, rbx
0x14001b6e6  jz      short loc_14001B70A
0x14001b6e8  lea     rcx, [rbp+arg_10]; this
0x14001b6ec  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14001b6f1  mov     rcx, rbx; hKey
0x14001b6f4  call    cs:__imp_RegCloseKey
0x14001b6fb  nop     dword ptr [rax+rax+00h]
0x14001b700  lea     rcx, [rbp+arg_10]; this
0x14001b704  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14001b709  nop
0x14001b70a  mov     [rbp+hKey], 0
0x14001b712  lea     rax, [rbp+hKey]
0x14001b716  mov     qword ptr [rsp+50h+dwOptions], rax; phkResult
0x14001b71b  mov     r9d, 0F003Fh; samDesired
0x14001b721  xor     r8d, r8d; ulOptions
0x14001b724  lea     rdx, aSoftwareMicros_14; "Software\\Microsoft\\Windows NT\\Curren"...
0x14001b72b  mov     rcx, 0FFFFFFFF80000001h; hKey
0x14001b732  call    cs:__imp_RegOpenKeyExW
0x14001b739  nop     dword ptr [rax+rax+00h]
0x14001b73e  test    eax, eax
0x14001b740  jnz     short loc_14001B75A
0x14001b742  lea     rdx, aColorfiltering_0; "colorfiltering"
0x14001b749  mov     rcx, [rbp+hKey]; hKey
0x14001b74d  call    cs:__imp_RegDeleteTreeW
0x14001b754  nop     dword ptr [rax+rax+00h]
0x14001b759  nop
0x14001b75a  lea     rcx, [rbp+hKey]
0x14001b75e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14001b763  nop
0x14001b764  mov     rbx, [rsp+50h+arg_18]
0x14001b769  add     rsp, 50h
0x14001b76d  pop     rbp
0x14001b76e  retn
```
