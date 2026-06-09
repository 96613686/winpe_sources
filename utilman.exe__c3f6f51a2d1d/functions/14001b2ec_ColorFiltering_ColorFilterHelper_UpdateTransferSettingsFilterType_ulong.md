# ColorFiltering::ColorFilterHelper::UpdateTransferSettingsFilterType(ulong)

- ea: `0x14001b2ec`
- end: `0x14001b468`
- name: `?UpdateTransferSettingsFilterType@ColorFilterHelper@ColorFiltering@@SAXK@Z`
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
- `0x14001b2ec`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14001b42a`
- `ADVAPI32!RegOpenKeyExW` at `0x14001b42a`
- `ADVAPI32!RegCloseKey` at `0x14001b326`
- `ADVAPI32!RegCloseKey` at `0x14001b3ec`
- `ADVAPI32!RegCloseKey` at `0x14001b326`
- `ADVAPI32!RegCloseKey` at `0x14001b3ec`
- `ADVAPI32!RegSetValueExW` at `0x14001b3b3`
- `ADVAPI32!RegSetValueExW` at `0x14001b3b3`
- `ADVAPI32!RegCreateKeyExW` at `0x14001b383`
- `ADVAPI32!RegCreateKeyExW` at `0x14001b383`
- `ADVAPI32!RegDeleteTreeW` at `0x14001b445`
- `ADVAPI32!RegDeleteTreeW` at `0x14001b445`

## string_xrefs

- `0x14001b41c`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig\`
- `0x14001b375`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig\colorfiltering`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ColorFiltering::ColorFilterHelper::UpdateTransferSettingsFilterType(int a1)
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
      RegSetValueExW(hKey, L"FilterType", 0, 4u, (const BYTE *)&Data, 4u);
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
0x14001b2ec  mov     [rsp-8+arg_18], rbx
0x14001b2f1  push    rbp
0x14001b2f2  mov     rbp, rsp
0x14001b2f5  sub     rsp, 50h
0x14001b2f9  mov     [rbp+Data], ecx
0x14001b2fc  call    ?IsActive@ColorFilterHelper@ColorFiltering@@SA_NXZ; ColorFiltering::ColorFilterHelper::IsActive(void)
0x14001b301  test    al, al
0x14001b303  jz      loc_14001B3CF
0x14001b309  mov     [rbp+hKey], 0
0x14001b311  mov     rbx, [rbp+hKey]
0x14001b315  test    rbx, rbx
0x14001b318  jz      short loc_14001B33C
0x14001b31a  lea     rcx, [rbp+arg_10]; this
0x14001b31e  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14001b323  mov     rcx, rbx; hKey
0x14001b326  call    cs:__imp_RegCloseKey
0x14001b32d  nop     dword ptr [rax+rax+00h]
0x14001b332  lea     rcx, [rbp+arg_10]; this
0x14001b336  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14001b33b  nop
0x14001b33c  mov     [rbp+hKey], 0
0x14001b344  mov     [rsp+50h+lpdwDisposition], 0; lpdwDisposition
0x14001b34d  lea     rax, [rbp+hKey]
0x14001b351  mov     [rsp+50h+phkResult], rax; phkResult
0x14001b356  mov     [rsp+50h+lpSecurityAttributes], 0; lpSecurityAttributes
0x14001b35f  mov     [rsp+50h+samDesired], 3; samDesired
0x14001b367  mov     [rsp+50h+dwOptions], 1; dwOptions
0x14001b36f  xor     r9d, r9d; lpClass
0x14001b372  xor     r8d, r8d; Reserved
0x14001b375  lea     rdx, aSoftwareMicros_12; "Software\\Microsoft\\Windows NT\\Curren"...
0x14001b37c  mov     rcx, 0FFFFFFFF80000001h; hKey
0x14001b383  call    cs:__imp_RegCreateKeyExW
0x14001b38a  nop     dword ptr [rax+rax+00h]
0x14001b38f  test    eax, eax
0x14001b391  jnz     short loc_14001B3C0
0x14001b393  lea     r9d, [rax+4]; dwType
0x14001b397  mov     [rsp+50h+samDesired], r9d; cbData
0x14001b39c  lea     rax, [rbp+Data]
0x14001b3a0  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x14001b3a5  xor     r8d, r8d; Reserved
0x14001b3a8  lea     rdx, aFiltertype; "FilterType"
0x14001b3af  mov     rcx, [rbp+hKey]; hKey
0x14001b3b3  call    cs:__imp_RegSetValueExW
0x14001b3ba  nop     dword ptr [rax+rax+00h]
0x14001b3bf  nop
0x14001b3c0  lea     rcx, [rbp+hKey]
0x14001b3c4  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14001b3c9  nop
0x14001b3ca  jmp     loc_14001B45C
0x14001b3cf  mov     [rbp+hKey], 0
0x14001b3d7  mov     rbx, [rbp+hKey]
0x14001b3db  test    rbx, rbx
0x14001b3de  jz      short loc_14001B402
0x14001b3e0  lea     rcx, [rbp+arg_10]; this
0x14001b3e4  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14001b3e9  mov     rcx, rbx; hKey
0x14001b3ec  call    cs:__imp_RegCloseKey
0x14001b3f3  nop     dword ptr [rax+rax+00h]
0x14001b3f8  lea     rcx, [rbp+arg_10]; this
0x14001b3fc  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14001b401  nop
0x14001b402  mov     [rbp+hKey], 0
0x14001b40a  lea     rax, [rbp+hKey]
0x14001b40e  mov     qword ptr [rsp+50h+dwOptions], rax; phkResult
0x14001b413  mov     r9d, 0F003Fh; samDesired
0x14001b419  xor     r8d, r8d; ulOptions
0x14001b41c  lea     rdx, aSoftwareMicros_14; "Software\\Microsoft\\Windows NT\\Curren"...
0x14001b423  mov     rcx, 0FFFFFFFF80000001h; hKey
0x14001b42a  call    cs:__imp_RegOpenKeyExW
0x14001b431  nop     dword ptr [rax+rax+00h]
0x14001b436  test    eax, eax
0x14001b438  jnz     short loc_14001B452
0x14001b43a  lea     rdx, aColorfiltering_0; "colorfiltering"
0x14001b441  mov     rcx, [rbp+hKey]; hKey
0x14001b445  call    cs:__imp_RegDeleteTreeW
0x14001b44c  nop     dword ptr [rax+rax+00h]
0x14001b451  nop
0x14001b452  lea     rcx, [rbp+hKey]
0x14001b456  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14001b45b  nop
0x14001b45c  mov     rbx, [rsp+50h+arg_18]
0x14001b461  add     rsp, 50h
0x14001b465  pop     rbp
0x14001b466  retn
```
