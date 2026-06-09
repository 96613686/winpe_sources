# ColorFiltering::ColorFilterHelper::UpdateTransferSettingsActive(bool)

- ea: `0x14001b16c`
- end: `0x14001b2e6`
- name: `?UpdateTransferSettingsActive@ColorFilterHelper@ColorFiltering@@SAX_N@Z`
- size: `378`
- prototype: `void __fastcall(bool)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140019a74`

## callees

- `0x1400045a0`
- `0x140004ba4`
- `0x140013d0c`
- `0x14001b16c`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14001b2a8`
- `ADVAPI32!RegOpenKeyExW` at `0x14001b2a8`
- `ADVAPI32!RegCloseKey` at `0x14001b1a4`
- `ADVAPI32!RegCloseKey` at `0x14001b26a`
- `ADVAPI32!RegCloseKey` at `0x14001b1a4`
- `ADVAPI32!RegCloseKey` at `0x14001b26a`
- `ADVAPI32!RegSetValueExW` at `0x14001b231`
- `ADVAPI32!RegSetValueExW` at `0x14001b231`
- `ADVAPI32!RegCreateKeyExW` at `0x14001b201`
- `ADVAPI32!RegCreateKeyExW` at `0x14001b201`
- `ADVAPI32!RegDeleteTreeW` at `0x14001b2c3`
- `ADVAPI32!RegDeleteTreeW` at `0x14001b2c3`

## string_xrefs

- `0x14001b29a`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig\`
- `0x14001b1f3`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig\colorfiltering`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ColorFiltering::ColorFilterHelper::UpdateTransferSettingsActive(unsigned __int8 a1)
{
  int Data; // [rsp+60h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+18h] BYREF

  Data = a1;
  if ( a1 )
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
      RegSetValueExW(hKey, L"Active", 0, 4u, (const BYTE *)&Data, 4u);
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
0x14001b16c  mov     [rsp-8+arg_18], rbx
0x14001b171  push    rbp
0x14001b172  mov     rbp, rsp
0x14001b175  sub     rsp, 50h
0x14001b179  movzx   eax, cl
0x14001b17c  mov     [rbp+Data], eax
0x14001b17f  test    cl, cl
0x14001b181  jz      loc_14001B24D
0x14001b187  mov     [rbp+hKey], 0
0x14001b18f  mov     rbx, [rbp+hKey]
0x14001b193  test    rbx, rbx
0x14001b196  jz      short loc_14001B1BA
0x14001b198  lea     rcx, [rbp+arg_10]; this
0x14001b19c  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14001b1a1  mov     rcx, rbx; hKey
0x14001b1a4  call    cs:__imp_RegCloseKey
0x14001b1ab  nop     dword ptr [rax+rax+00h]
0x14001b1b0  lea     rcx, [rbp+arg_10]; this
0x14001b1b4  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14001b1b9  nop
0x14001b1ba  mov     [rbp+hKey], 0
0x14001b1c2  mov     [rsp+50h+lpdwDisposition], 0; lpdwDisposition
0x14001b1cb  lea     rax, [rbp+hKey]
0x14001b1cf  mov     [rsp+50h+phkResult], rax; phkResult
0x14001b1d4  mov     [rsp+50h+lpSecurityAttributes], 0; lpSecurityAttributes
0x14001b1dd  mov     [rsp+50h+samDesired], 3; samDesired
0x14001b1e5  mov     [rsp+50h+dwOptions], 1; dwOptions
0x14001b1ed  xor     r9d, r9d; lpClass
0x14001b1f0  xor     r8d, r8d; Reserved
0x14001b1f3  lea     rdx, aSoftwareMicros_12; "Software\\Microsoft\\Windows NT\\Curren"...
0x14001b1fa  mov     rcx, 0FFFFFFFF80000001h; hKey
0x14001b201  call    cs:__imp_RegCreateKeyExW
0x14001b208  nop     dword ptr [rax+rax+00h]
0x14001b20d  test    eax, eax
0x14001b20f  jnz     short loc_14001B23E
0x14001b211  lea     r9d, [rax+4]; dwType
0x14001b215  mov     [rsp+50h+samDesired], r9d; cbData
0x14001b21a  lea     rax, [rbp+Data]
0x14001b21e  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x14001b223  xor     r8d, r8d; Reserved
0x14001b226  lea     rdx, aActive; "Active"
0x14001b22d  mov     rcx, [rbp+hKey]; hKey
0x14001b231  call    cs:__imp_RegSetValueExW
0x14001b238  nop     dword ptr [rax+rax+00h]
0x14001b23d  nop
0x14001b23e  lea     rcx, [rbp+hKey]
0x14001b242  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14001b247  nop
0x14001b248  jmp     loc_14001B2DA
0x14001b24d  mov     [rbp+hKey], 0
0x14001b255  mov     rbx, [rbp+hKey]
0x14001b259  test    rbx, rbx
0x14001b25c  jz      short loc_14001B280
0x14001b25e  lea     rcx, [rbp+arg_10]; this
0x14001b262  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14001b267  mov     rcx, rbx; hKey
0x14001b26a  call    cs:__imp_RegCloseKey
0x14001b271  nop     dword ptr [rax+rax+00h]
0x14001b276  lea     rcx, [rbp+arg_10]; this
0x14001b27a  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14001b27f  nop
0x14001b280  mov     [rbp+hKey], 0
0x14001b288  lea     rax, [rbp+hKey]
0x14001b28c  mov     qword ptr [rsp+50h+dwOptions], rax; phkResult
0x14001b291  mov     r9d, 0F003Fh; samDesired
0x14001b297  xor     r8d, r8d; ulOptions
0x14001b29a  lea     rdx, aSoftwareMicros_14; "Software\\Microsoft\\Windows NT\\Curren"...
0x14001b2a1  mov     rcx, 0FFFFFFFF80000001h; hKey
0x14001b2a8  call    cs:__imp_RegOpenKeyExW
0x14001b2af  nop     dword ptr [rax+rax+00h]
0x14001b2b4  test    eax, eax
0x14001b2b6  jnz     short loc_14001B2D0
0x14001b2b8  lea     rdx, aColorfiltering_0; "colorfiltering"
0x14001b2bf  mov     rcx, [rbp+hKey]; hKey
0x14001b2c3  call    cs:__imp_RegDeleteTreeW
0x14001b2ca  nop     dword ptr [rax+rax+00h]
0x14001b2cf  nop
0x14001b2d0  lea     rcx, [rbp+hKey]
0x14001b2d4  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14001b2d9  nop
0x14001b2da  mov     rbx, [rsp+50h+arg_18]
0x14001b2df  add     rsp, 50h
0x14001b2e3  pop     rbp
0x14001b2e4  retn
```
