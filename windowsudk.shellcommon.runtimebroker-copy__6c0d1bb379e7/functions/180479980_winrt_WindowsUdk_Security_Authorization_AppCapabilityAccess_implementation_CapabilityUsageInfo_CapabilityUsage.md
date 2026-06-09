# _winrt::WindowsUdk::Security::Authorization::AppCapabilityAccess::implementation::CapabilityUsageInfo::CapabilityUsageInfo_::_1_::catch$64

- ea: `0x180479980`
- end: `0x180479b70`
- name: `_winrt::WindowsUdk::Security::Authorization::AppCapabilityAccess::implementation::CapabilityUsageInfo::CapabilityUsageInfo_::_1_::catch$64`
- size: `496`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18000fea0`
- `0x180010940`
- `0x180011e64`
- `0x180011f98`
- `0x18002ecb0`
- `0x1800795e4`
- `0x18015d898`
- `0x18046bdb8`
- `0x180479980`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180479b22`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180479b22`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180479a3e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180479ac4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180479a3e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180479ac4`

## string_xrefs

- `0x180479a30`: `Software\Microsoft\Windows\CurrentVersion\CapabilityAccessManager\Capabilities\Location`
- `0x180479ab6`: `Software\Microsoft\Windows\CurrentVersion\CapabilityAccessManager\Capabilities\Microphone`
- `0x180479a56`: `shellcommon\undockeddevkit\libs\windowsudk.security.authorization.appcapabilityaccess\security.authorization.appcapabilityaccess.capabilityusageinfo.cpp`
- `0x180479ad8`: `shellcommon\undockeddevkit\libs\windowsudk.security.authorization.appcapabilityaccess\security.authorization.appcapabilityaccess.capabilityusageinfo.cpp`
- `0x180479b36`: `shellcommon\undockeddevkit\libs\windowsudk.security.authorization.appcapabilityaccess\security.authorization.appcapabilityaccess.capabilityusageinfo.cpp`

## pseudocode

```c
__int64 __fastcall winrt::WindowsUdk::Security::Authorization::AppCapabilityAccess::implementation::CapabilityUsageInfo::CapabilityUsageInfo_::_1_::catch_64(
        __int64 a1,
        __int64 a2)
{
  __int64 v4; // rbx
  HKEY *phkResult; // rax
  unsigned int Key; // eax
  HKEY *v7; // rax
  unsigned int v8; // eax
  unsigned int ValueW; // eax
  unsigned int dwOptions; // [rsp+20h] [rbp-48h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-48h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-48h]

  if ( *(_DWORD *)(*(_QWORD *)(a2 + 216) + 12LL) == -2147024809 )
    return 0;
  MicrosoftTelemetryAssertTriggeredNoArgs();
  *(_QWORD *)(a2 + 88) = 0;
  v4 = *(_QWORD *)(a2 + 152);
  winrt::Windows::Foundation::IUnknown::operator=(v4 + 88, a2 + 88);
  if ( *(_QWORD *)(a2 + 88) )
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(a2 + 88);
  *(_QWORD *)(a2 + 112) = 0;
  if ( (unsigned __int8)winrt::operator==(v4 + 72, L"location") )
  {
    phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(a2 + 112);
    Key = RegCreateKeyExW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\CapabilityAccessManager\\Capabilities\\Location",
            0,
            0,
            0,
            0x20119u,
            0,
            phkResult,
            0);
    if ( Key )
      wil::details::in1diag3::Throw_Win32(
        *(wil::details::in1diag3 **)(a2 + 728),
        (void *)0x78,
        (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.security.authorization.appcapabilityaccess\\security"
                      ".authorization.appcapabilityaccess.capabilityusageinfo.cpp",
        (const char *)Key,
        dwOptions);
  }
  else
  {
    if ( !(unsigned __int8)winrt::operator==(v4 + 72, L"microphone") )
      throw;
    v7 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(a2 + 112);
    v8 = RegCreateKeyExW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\Windows\\CurrentVersion\\CapabilityAccessManager\\Capabilities\\Microphone",
           0,
           0,
           0,
           0x20119u,
           0,
           v7,
           0);
    if ( v8 )
      wil::details::in1diag3::Throw_Win32(
        *(wil::details::in1diag3 **)(a2 + 728),
        (void *)0x7D,
        (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.security.authorization.appcapabilityaccess\\security"
                      ".authorization.appcapabilityaccess.capabilityusageinfo.cpp",
        (const char *)v8,
        dwOptionsa);
  }
  *(_DWORD *)(a2 + 80) = 8;
  ValueW = RegGetValueW(*(HKEY *)(a2 + 112), 0, L"UsageChangeWNF", 0x10048u, 0, (PVOID)(a2 + 160), (LPDWORD)(a2 + 80));
  if ( ValueW )
    wil::details::in1diag3::Throw_Win32(
      *(wil::details::in1diag3 **)(a2 + 728),
      (void *)0x89,
      (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.security.authorization.appcapabilityaccess\\security.a"
                    "uthorization.appcapabilityaccess.capabilityusageinfo.cpp",
      (const char *)ValueW,
      dwOptionsb);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(a2 + 112);
  return 1;
}

```

## disassembly

```asm
0x180479980  mov     [rsp+arg_8], rdx
0x180479985  push    rbx
0x180479986  push    rbp
0x180479987  sub     rsp, 58h
0x18047998b  mov     rbp, rdx
0x18047998e  mov     rax, [rbp+0D8h]
0x180479995  cmp     dword ptr [rax+0Ch], 80070057h
0x18047999c  jnz     short loc_1804799AD
0x18047999e  mov     rax, 0
0x1804799a8  jmp     loc_180479B68
0x1804799ad  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1804799b2  mov     qword ptr [rbp+58h], 0
0x1804799ba  mov     rbx, [rbp+98h]
0x1804799c1  lea     rcx, [rbx+58h]
0x1804799c5  lea     rdx, [rbp+58h]
0x1804799c9  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x1804799ce  cmp     qword ptr [rbp+58h], 0
0x1804799d3  jz      short loc_1804799DE
0x1804799d5  lea     rcx, [rbp+58h]
0x1804799d9  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x1804799de  mov     qword ptr [rbp+70h], 0
0x1804799e6  lea     rcx, [rbx+48h]
0x1804799ea  lea     rdx, aLocation; "location"
0x1804799f1  call    ??8winrt@@YA_NAEBUhstring@0@PEB_W@Z; winrt::operator==(winrt::hstring const &,wchar_t const *)
0x1804799f6  test    al, al
0x1804799f8  jz      short loc_180479A68
0x1804799fa  lea     rcx, [rbp+70h]
0x1804799fe  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180479a03  mov     [rsp+68h+lpdwDisposition], 0; lpdwDisposition
0x180479a0c  mov     [rsp+68h+phkResult], rax; phkResult
0x180479a11  mov     [rsp+68h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180479a1a  mov     [rsp+68h+samDesired], 20119h; samDesired
0x180479a22  mov     [rsp+68h+dwOptions], 0; unsigned int
0x180479a2a  xor     r9d, r9d; lpClass
0x180479a2d  xor     r8d, r8d; Reserved
0x180479a30  lea     rdx, aSoftwareMicros_77; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180479a37  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180479a3e  call    cs:__imp_RegCreateKeyExW
0x180479a44  mov     rcx, [rbp+2D8h]; this
0x180479a4b  test    eax, eax
0x180479a4d  jz      loc_180479AEA
0x180479a53  mov     r9d, eax; char *
0x180479a56  lea     r8, aShellcommonUnd_7; "shellcommon\\undockeddevkit\\libs\\wind"...
0x180479a5d  mov     edx, 78h ; 'x'; void *
0x180479a62  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180479a68  lea     rcx, [rbx+48h]
0x180479a6c  lea     rdx, aMicrophone; "microphone"
0x180479a73  call    ??8winrt@@YA_NAEBUhstring@0@PEB_W@Z; winrt::operator==(winrt::hstring const &,wchar_t const *)
0x180479a78  test    al, al
0x180479a7a  jz      loc_180479B5E
0x180479a80  lea     rcx, [rbp+70h]
0x180479a84  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180479a89  mov     [rsp+68h+lpdwDisposition], 0; lpdwDisposition
0x180479a92  mov     [rsp+68h+phkResult], rax; phkResult
0x180479a97  mov     [rsp+68h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180479aa0  mov     [rsp+68h+samDesired], 20119h; samDesired
0x180479aa8  mov     [rsp+68h+dwOptions], 0; unsigned int
0x180479ab0  xor     r9d, r9d; lpClass
0x180479ab3  xor     r8d, r8d; Reserved
0x180479ab6  lea     rdx, aSoftwareMicros_78; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180479abd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180479ac4  call    cs:__imp_RegCreateKeyExW
0x180479aca  mov     rcx, [rbp+2D8h]; this
0x180479ad1  test    eax, eax
0x180479ad3  jz      short loc_180479AEA
0x180479ad5  mov     r9d, eax; char *
0x180479ad8  lea     r8, aShellcommonUnd_7; "shellcommon\\undockeddevkit\\libs\\wind"...
0x180479adf  mov     edx, 7Dh ; '}'; void *
0x180479ae4  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180479aea  mov     dword ptr [rbp+50h], 8
0x180479af1  lea     rax, [rbp+50h]
0x180479af5  mov     [rsp+68h+lpSecurityAttributes], rax; pcbData
0x180479afa  lea     rax, [rbp+0A0h]
0x180479b01  mov     qword ptr [rsp+68h+samDesired], rax; pvData
0x180479b06  mov     qword ptr [rsp+68h+dwOptions], 0; unsigned int
0x180479b0f  mov     r9d, 10048h; dwFlags
0x180479b15  lea     r8, aUsagechangewnf; "UsageChangeWNF"
0x180479b1c  xor     edx, edx; lpSubKey
0x180479b1e  mov     rcx, [rbp+70h]; hkey
0x180479b22  call    cs:__imp_RegGetValueW
0x180479b28  test    eax, eax
0x180479b2a  jz      short loc_180479B48
0x180479b2c  mov     rcx, [rbp+2D8h]; this
0x180479b33  mov     r9d, eax; char *
0x180479b36  lea     r8, aShellcommonUnd_7; "shellcommon\\undockeddevkit\\libs\\wind"...
0x180479b3d  mov     edx, 89h; void *
0x180479b42  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180479b48  lea     rcx, [rbp+70h]
0x180479b4c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180479b51  nop
0x180479b52  mov     rax, 1
0x180479b5c  jmp     short loc_180479B68
0x180479b5e  xor     edx, edx; pThrowInfo
0x180479b60  xor     ecx, ecx; pExceptionObject
0x180479b62  call    _CxxThrowException_0
0x180479b68  add     rsp, 58h
0x180479b6c  pop     rbp
0x180479b6d  pop     rbx
0x180479b6e  retn
```
