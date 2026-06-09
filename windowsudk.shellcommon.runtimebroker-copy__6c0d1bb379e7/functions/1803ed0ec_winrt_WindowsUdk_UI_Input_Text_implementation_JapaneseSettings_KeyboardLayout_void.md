# winrt::WindowsUdk::UI::Input::Text::implementation::JapaneseSettings::KeyboardLayout(void)

- ea: `0x1803ed0ec`
- end: `0x1803ed262`
- name: `?KeyboardLayout@JapaneseSettings@implementation@Text@Input@UI@WindowsUdk@winrt@@QEAA?AW4JapaneseKeyboardLayoutKind@34567@XZ`
- size: `374`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1803ed270`

## callees

- `0x180021c00`
- `0x180025264`
- `0x180026860`
- `0x18009d6e4`
- `0x18011e940`
- `0x18015cb00`
- `0x18015d868`
- `0x1803ed0a0`
- `0x1803ed0ec`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1803ed1e3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1803ed205`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1803ed1e3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1803ed205`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x1803ed150`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x1803ed150`

## string_xrefs

- `0x1803ed1fe`: `kbd106n.dll`
- `0x1803ed1bf`: `kbd101.dll`
- `0x1803ed1dc`: `kbd106.dll`
- `0x1803ed174`: `shellcommon\undockeddevkit\libs\windowsudk.ui.input.text.settings\japanesesettings.cpp`
- `0x1803ed142`: `System\CurrentControlSet\Services\i8042prt\Parameters`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winrt::WindowsUdk::UI::Input::Text::implementation::JapaneseSettings::KeyboardLayout(__int64 a1)
{
  unsigned int PersistedRegistryLocationW; // eax
  _QWORD *v3; // rcx
  _QWORD *v4; // rcx
  char *v6; // [rsp+28h] [rbp-D8h]
  _BYTE v7[40]; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v8[3]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v9; // [rsp+78h] [rbp-88h]
  _BYTE v10[528]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  memset_0(v10, 0, 0x208u);
  PersistedRegistryLocationW = GetPersistedRegistryLocationW(
                                 L"InputSettings",
                                 L"System\\CurrentControlSet\\Services\\i8042prt\\Parameters",
                                 v10,
                                 260);
  LODWORD(v6) = 0;
  wil::details::in1diag3::FailFast_IfNtStatusFailedMsg(
    retaddr,
    (void *)0x36,
    (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.ui.input.text.settings\\japanesesettings.cpp",
    (const char *)PersistedRegistryLocationW,
    (int)"required=%d",
    v6);
  winrt::WindowsUdk::UI::Input::Text::implementation::RegistryAccessorBase::TryGetStringSetting(
    *(_QWORD *)(a1 + 32),
    (unsigned int)v7,
    (unsigned int)v10,
    (unsigned int)L"LayerDriver JPN",
    1);
  if ( v7[32] )
    std::wstring::wstring(v8, v7);
  else
    std::wstring::wstring(v8, L"kbd101.dll");
  v3 = v8;
  if ( v9 > 7 )
    v3 = (_QWORD *)v8[0];
  if ( !(unsigned int)_o__wcsicmp(v3, L"kbd106.dll") )
    goto LABEL_11;
  v4 = v8;
  if ( v9 > 7 )
    v4 = (_QWORD *)v8[0];
  if ( (unsigned int)_o__wcsicmp(v4, L"kbd106n.dll") )
  {
    std::filesystem::path::~path((std::filesystem::path *)v8);
    std::_Optional_destruct_base<std::wstring,0>::~_Optional_destruct_base<std::wstring,0>(v7);
    return 0;
  }
  else
  {
LABEL_11:
    std::filesystem::path::~path((std::filesystem::path *)v8);
    std::_Optional_destruct_base<std::wstring,0>::~_Optional_destruct_base<std::wstring,0>(v7);
    return 1;
  }
}

```

## disassembly

```asm
0x1803ed0ec  mov     [rsp-8+arg_8], rbx
0x1803ed0f1  push    rbp
0x1803ed0f2  lea     rbp, [rsp-1A0h]
0x1803ed0fa  sub     rsp, 2A0h
0x1803ed101  mov     rax, cs:__security_cookie
0x1803ed108  xor     rax, rsp
0x1803ed10b  mov     [rbp+1A0h+var_10], rax
0x1803ed112  mov     rbx, rcx
0x1803ed115  xor     edx, edx; Val
0x1803ed117  mov     r8d, 208h; Size
0x1803ed11d  lea     rcx, [rbp+1A0h+var_220]; void *
0x1803ed121  call    memset_0
0x1803ed126  mov     dword ptr [rsp+2A0h+var_270], 0
0x1803ed12e  lea     rax, [rsp+2A0h+var_270]
0x1803ed133  mov     qword ptr [rsp+2A0h+var_280], rax
0x1803ed138  mov     r9d, 104h
0x1803ed13e  lea     r8, [rbp+1A0h+var_220]
0x1803ed142  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\i8"...
0x1803ed149  lea     rcx, aInputsettings; "InputSettings"
0x1803ed150  call    cs:__imp_GetPersistedRegistryLocationW
0x1803ed156  mov     rcx, [rbp+1A8h]; this
0x1803ed15d  mov     edx, dword ptr [rsp+2A0h+var_270]
0x1803ed161  mov     dword ptr [rsp+2A0h+var_278], edx; char *
0x1803ed165  lea     rdx, aRequiredD; "required=%d"
0x1803ed16c  mov     qword ptr [rsp+2A0h+var_280], rdx; int
0x1803ed171  mov     r9d, eax; char *
0x1803ed174  lea     r8, aShellcommonUnd_76; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1803ed17b  mov     edx, 36h ; '6'; void *
0x1803ed180  call    ?FailFast_IfNtStatusFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::FailFast_IfNtStatusFailedMsg(void *,uint,char const *,long,char const *,...)
0x1803ed185  mov     [rsp+2A0h+var_280], 1
0x1803ed18d  lea     r9, aLayerdriverJpn; "LayerDriver JPN"
0x1803ed194  lea     r8, [rbp+1A0h+var_220]
0x1803ed198  lea     rdx, [rsp+2A0h+var_268]
0x1803ed19d  mov     rcx, [rbx+20h]
0x1803ed1a1  call    ?TryGetStringSetting@RegistryAccessorBase@implementation@Text@Input@UI@WindowsUdk@winrt@@QEAA?AV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@PEB_W0W4RegistryType@1234567@@Z; winrt::WindowsUdk::UI::Input::Text::implementation::RegistryAccessorBase::TryGetStringSetting(wchar_t const *,wchar_t const *,winrt::WindowsUdk::UI::Input::Text::implementation::RegistryAccessorBase::RegistryType)
0x1803ed1a6  nop
0x1803ed1a7  lea     rcx, [rsp+2A0h+var_240]
0x1803ed1ac  cmp     [rsp+2A0h+var_248], 0
0x1803ed1b1  jz      short loc_1803ED1BF
0x1803ed1b3  lea     rdx, [rsp+2A0h+var_268]
0x1803ed1b8  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1803ed1bd  jmp     short loc_1803ED1CB
0x1803ed1bf  lea     rdx, aKbd101Dll; "kbd101.dll"
0x1803ed1c6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1803ed1cb  lea     rcx, [rsp+2A0h+var_240]
0x1803ed1d0  cmp     [rsp+2A0h+var_228], 7
0x1803ed1d6  cmova   rcx, [rsp+2A0h+var_240]
0x1803ed1dc  lea     rdx, aKbd106Dll; "kbd106.dll"
0x1803ed1e3  call    cs:__imp__o__wcsicmp
0x1803ed1e9  test    eax, eax
0x1803ed1eb  jz      short loc_1803ED228
0x1803ed1ed  lea     rcx, [rsp+2A0h+var_240]
0x1803ed1f2  cmp     [rsp+2A0h+var_228], 7
0x1803ed1f8  cmova   rcx, [rsp+2A0h+var_240]
0x1803ed1fe  lea     rdx, aKbd106nDll; "kbd106n.dll"
0x1803ed205  call    cs:__imp__o__wcsicmp
0x1803ed20b  test    eax, eax
0x1803ed20d  jz      short loc_1803ED228
0x1803ed20f  lea     rcx, [rsp+2A0h+var_240]; this
0x1803ed214  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x1803ed219  nop
0x1803ed21a  lea     rcx, [rsp+2A0h+var_268]
0x1803ed21f  call    ??1?$_Optional_destruct_base@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<std::wstring,0>::~_Optional_destruct_base<std::wstring,0>(void)
0x1803ed224  xor     eax, eax
0x1803ed226  jmp     short loc_1803ED242
0x1803ed228  lea     rcx, [rsp+2A0h+var_240]; this
0x1803ed22d  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x1803ed232  nop
0x1803ed233  lea     rcx, [rsp+2A0h+var_268]
0x1803ed238  call    ??1?$_Optional_destruct_base@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<std::wstring,0>::~_Optional_destruct_base<std::wstring,0>(void)
0x1803ed23d  mov     eax, 1
0x1803ed242  mov     rcx, [rbp+1A0h+var_10]
0x1803ed249  xor     rcx, rsp; StackCookie
0x1803ed24c  call    __security_check_cookie
0x1803ed251  mov     rbx, [rsp+2A0h+arg_8]
0x1803ed259  add     rsp, 2A0h
0x1803ed260  pop     rbp
0x1803ed261  retn
```
