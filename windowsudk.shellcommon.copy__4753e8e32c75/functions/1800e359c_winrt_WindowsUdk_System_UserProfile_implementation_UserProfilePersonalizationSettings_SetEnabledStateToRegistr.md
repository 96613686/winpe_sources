# winrt::WindowsUdk::System::UserProfile::implementation::UserProfilePersonalizationSettings::SetEnabledStateToRegistry(bool)

- ea: `0x1800e359c`
- end: `0x1800e3659`
- name: `?SetEnabledStateToRegistry@UserProfilePersonalizationSettings@implementation@UserProfile@System@WindowsUdk@winrt@@AEAAJ_N@Z`
- size: `189`
- prototype: `__int64 __fastcall(winrt::WindowsUdk::System::UserProfile::implementation::UserProfilePersonalizationSettings *__hidden this, bool)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18009ace4`
- `0x180337fcc`

## callees

- `0x18000fea0`
- `0x180010940`
- `0x1800e359c`
- `0x1800e3660`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e35fc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e35fc`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800e3632`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800e3632`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x1800e35cd`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x1800e35cd`

## string_xrefs

- `0x1800e35dc`: `shellcommon\undockeddevkit\libs\windowsudk.system.userprofile\userprofilepersonalizationsettings.cpp`

## pseudocode

```c
__int64 __fastcall winrt::WindowsUdk::System::UserProfile::implementation::UserProfilePersonalizationSettings::SetEnabledStateToRegistry(
        winrt::WindowsUdk::System::UserProfile::implementation::UserProfilePersonalizationSettings *this,
        unsigned __int8 a2)
{
  int v2; // ebx
  HKEY *v3; // rax
  unsigned int KeyW; // eax
  unsigned int v5; // ebx
  LSTATUS v6; // eax
  unsigned int lpData; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  winrt::WindowsUdk::System::UserProfile::implementation::UserProfilePersonalizationSettings *Data; // [rsp+40h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  Data = this;
  v2 = a2;
  hKey = 0;
  v3 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
  KeyW = RegCreateKeyW(
           HKEY_CURRENT_USER,
           L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\DesktopSpotlight\\Settings",
           v3);
  if ( KeyW )
  {
    v5 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x1C6,
           (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.system.userprofile\\userprofilepersonalizationsettings.cpp",
           (const char *)KeyW,
           lpData);
    if ( hKey )
      RegCloseKey(hKey);
  }
  else
  {
    LODWORD(Data) = v2;
    v6 = RegSetKeyValueW(
           HKEY_CURRENT_USER,
           L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\DesktopSpotlight\\Settings",
           L"EnabledState",
           4u,
           &Data,
           4u);
    v5 = v6;
    if ( v6 > 0 )
      v5 = (unsigned __int16)v6 | 0x80070000;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  }
  return v5;
}

```

## disassembly

```asm
0x1800e359c  mov     [rsp+Data], rcx
0x1800e35a1  push    rbx
0x1800e35a2  sub     rsp, 30h
0x1800e35a6  lea     rcx, [rsp+38h+hKey]
0x1800e35ab  movzx   ebx, dl
0x1800e35ae  mov     [rsp+38h+hKey], 0
0x1800e35b7  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1800e35bc  mov     r8, rax; phkResult
0x1800e35bf  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800e35c6  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800e35cd  call    cs:__imp_RegCreateKeyW
0x1800e35d3  test    eax, eax
0x1800e35d5  jz      short loc_1800E3604
0x1800e35d7  mov     rcx, [rsp+38h]; this
0x1800e35dc  lea     r8, aShellcommonUnd_92; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1800e35e3  mov     r9d, eax; char *
0x1800e35e6  mov     edx, 1C6h; void *
0x1800e35eb  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800e35f0  mov     rcx, [rsp+38h+hKey]; hKey
0x1800e35f5  mov     ebx, eax
0x1800e35f7  test    rcx, rcx
0x1800e35fa  jz      short loc_1800E3651
0x1800e35fc  call    cs:__imp_RegCloseKey
0x1800e3602  jmp     short loc_1800E3651
0x1800e3604  mov     r9d, 4; dwType
0x1800e360a  mov     dword ptr [rsp+38h+Data], ebx
0x1800e360e  lea     rax, [rsp+38h+Data]
0x1800e3613  mov     [rsp+38h+cbData], r9d; cbData
0x1800e3618  lea     r8, aEnabledstate; "EnabledState"
0x1800e361f  mov     [rsp+38h+lpData], rax; lpData
0x1800e3624  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800e362b  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800e3632  call    cs:__imp_RegSetKeyValueW
0x1800e3638  mov     ebx, eax
0x1800e363a  test    eax, eax
0x1800e363c  jle     short loc_1800E3647
0x1800e363e  movzx   ebx, ax
0x1800e3641  or      ebx, 80070000h
0x1800e3647  lea     rcx, [rsp+38h+hKey]
0x1800e364c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800e3651  mov     eax, ebx
0x1800e3653  add     rsp, 30h
0x1800e3657  pop     rbx
0x1800e3658  retn
```
