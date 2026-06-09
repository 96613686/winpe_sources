# Microsoft::Diagnostics::Utils::Registry::SetDword(HKEY__ *,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,ulong,ulong)

- ea: `0x180052964`
- end: `0x180052c92`
- name: `?SetDword@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1KK@Z`
- size: `814`
- prototype: `__int64 __fastcall(int, int, int, int, DWORD)`
- caller_count: `32`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180052734`
- `0x180055964`
- `0x18009c9c0`
- `0x18009e49c`
- `0x18009e51c`
- `0x1800a131c`
- `0x1800aad84`
- `0x1800eae10`
- `0x1800edcd8`
- `0x1800f68c0`
- `0x18010c924`
- `0x18011f1e4`
- `0x180120664`
- `0x18018efe0`
- `0x180197744`
- `0x1801b5764`
- `0x1801ce2c8`
- `0x1801ee694`
- `0x180218150`
- `0x18021ccac`
- `0x18021ce64`
- `0x1802209a8`
- `0x18026c3f0`
- `0x180272c08`
- `0x1802ac480`
- `0x1802ac6d0`
- `0x1802d7b1c`
- `0x1802db8bc`
- `0x1802dbc84`
- `0x1802dbd54`
- `0x1802dbe24`
- `0x1802fbf00`

## callees

- `0x18001d160`
- `0x180026ecc`
- `0x180027e64`
- `0x180035698`
- `0x180052964`
- `0x18005af1c`
- `0x180098d5c`
- `0x1800b83bc`
- `0x18012de40`
- `0x18016d310`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180052a0c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180052aed`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180052a0c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180052aed`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180052a82`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180052a82`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180052b9d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180052b9d`

## string_xrefs

- `0x180052ab0`: `onecore\base\telemetry\utc\include\RegistryUtils.h`
- `0x180052b21`: `onecore\base\telemetry\utc\include\RegistryUtils.h`
- `0x180052bd9`: `onecore\base\telemetry\utc\include\RegistryUtils.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::Diagnostics::Utils::Registry::SetDword(HKEY a1, __int64 a2, _QWORD *a3, int a4, DWORD a5)
{
  HKEY v7; // rdi
  const WCHAR *v8; // rdx
  LSTATUS v9; // eax
  unsigned int v10; // edi
  const char *v11; // r9
  __int64 result; // rax
  HKEY v13; // rdi
  __int64 v14; // rax
  int v15; // eax
  unsigned int v16; // edi
  int dwOptions; // [rsp+20h] [rbp-E8h]
  int dwOptionsa; // [rsp+20h] [rbp-E8h]
  int dwOptionsb; // [rsp+20h] [rbp-E8h]
  char *v20; // [rsp+50h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-B0h] BYREF
  BYTE Data[8]; // [rsp+60h] [rbp-A8h] BYREF
  HKEY v23; // [rsp+68h] [rbp-A0h] BYREF
  _QWORD v24[5]; // [rsp+70h] [rbp-98h] BYREF
  char v25; // [rsp+98h] [rbp-70h]
  _OWORD v26[2]; // [rsp+A0h] [rbp-68h] BYREF
  LPCWSTR lpSubKey[4]; // [rsp+C0h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  try
  {
    v23 = a1;
    *(_DWORD *)Data = a4;
    LODWORD(v20) = 0;
    hKey = 0;
    v24[0] = &v23;
    v24[1] = a2;
    v24[2] = a3;
    v24[3] = Data;
    v24[4] = &v20;
    v25 = 1;
    v26[0] = *(_OWORD *)a2;
    Microsoft::Diagnostics::Utils::Registry::TryExpandKeyName((LPCWSTR)lpSubKey);
    if ( *(_QWORD *)(a2 + 8) )
    {
      v7 = hKey;
      if ( hKey )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)v26);
        RegCloseKey(v7);
        wil::last_error_context::~last_error_context((wil::last_error_context *)v26);
      }
      hKey = 0;
      v8 = (const WCHAR *)lpSubKey;
      if ( lpSubKey[3] > (LPCWSTR)7 )
        v8 = lpSubKey[0];
      v9 = RegCreateKeyExW(v23, v8, 0, 0, a5, 2u, 0, &hKey, 0);
      v10 = v9;
      if ( v9 > 0 )
        v10 = (unsigned __int16)v9 | 0x80070000;
      LODWORD(v20) = v10;
      if ( (v10 & 0x80000000) != 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3EC,
          (unsigned int)"onecore\\base\\telemetry\\utc\\include\\RegistryUtils.h",
          (const char *)v10,
          dwOptionsa);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpSubKey);
        v25 = 0;
        `Microsoft::Diagnostics::Utils::Registry::SetDword'::`2'::_lambda_1_::operator()(v24);
        if ( hKey )
          RegCloseKey(hKey);
        return v10;
      }
      v13 = hKey;
    }
    else
    {
      v13 = v23;
      if ( !v23 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3F2,
          (unsigned int)"onecore\\base\\telemetry\\utc\\include\\RegistryUtils.h",
          (const char *)0x80070057LL,
          dwOptions);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpSubKey);
        v25 = 0;
        `Microsoft::Diagnostics::Utils::Registry::SetDword'::`2'::_lambda_1_::operator()(v24);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        return 2147942487LL;
      }
    }
    v14 = std::wstring::wstring((__int64)v26, a3);
    if ( *(_QWORD *)(v14 + 24) > 7u )
      v14 = *(_QWORD *)v14;
    v15 = RegSetValueExW(v13, (LPCWSTR)v14, 0, 4u, Data, 4u);
    if ( v15 > 0 )
      v15 = (unsigned __int16)v15 | 0x80070000;
    LODWORD(v20) = v15;
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v26);
    v16 = (unsigned int)v20;
    if ( (int)v20 >= 0 )
    {
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpSubKey);
      v25 = 0;
      `Microsoft::Diagnostics::Utils::Registry::SetDword'::`2'::_lambda_1_::operator()(v24);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      result = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3FC,
        (unsigned int)"onecore\\base\\telemetry\\utc\\include\\RegistryUtils.h",
        (const char *)(unsigned int)v20,
        dwOptionsb);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpSubKey);
      v25 = 0;
      `Microsoft::Diagnostics::Utils::Registry::SetDword'::`2'::_lambda_1_::operator()(v24);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      result = v16;
    }
  }
  catch ( ... )
  {
    LODWORD(v26[0]) = wil::details::in1diag3::Return_CaughtException(
                        retaddr,
                        (void *)0x400,
                        (unsigned int)"onecore\\base\\telemetry\\utc\\include\\RegistryUtils.h",
                        v11);
    if ( v25 )
    {
      v25 = 0;
      `Microsoft::Diagnostics::Utils::Registry::SetDword'::`2'::_lambda_1_::operator()(v24);
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return LODWORD(v26[0]);
  }
  return result;
}

```

## disassembly

```asm
0x180052964  mov     r11, rsp
0x180052967  push    rsi
0x180052968  push    rdi
0x180052969  sub     rsp, 0F8h
0x180052970  mov     rax, cs:__security_cookie
0x180052977  xor     rax, rsp
0x18005297a  mov     [rsp+108h+var_28], rax
0x180052982  mov     rsi, r8
0x180052985  mov     rdi, rdx
0x180052988  mov     [rsp+108h+var_A0], rcx
0x18005298d  mov     dword ptr [rsp+108h+Data], r9d
0x180052992  mov     dword ptr [rsp+108h+var_B8], 0
0x18005299a  mov     [rsp+108h+hKey], 0
0x1800529a3  lea     rax, [rsp+108h+var_A0]
0x1800529a8  mov     [rsp+108h+var_98], rax
0x1800529ad  mov     [rsp+108h+var_90], rdx
0x1800529b2  mov     [r11-88h], r8
0x1800529b9  lea     rax, [rsp+108h+Data]
0x1800529be  mov     [r11-80h], rax
0x1800529c2  lea     rax, [rsp+108h+var_B8]
0x1800529c7  mov     [r11-78h], rax
0x1800529cb  mov     byte ptr [r11-70h], 1
0x1800529d0  movups  xmm0, xmmword ptr [rdx]
0x1800529d3  movdqu  xmmword ptr [r11-68h], xmm0
0x1800529d9  lea     rdx, [r11-68h]
0x1800529dd  lea     rcx, [r11-48h]
0x1800529e1  call    ?TryExpandKeyName@Registry@Utils@Diagnostics@Microsoft@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@6@@Z; Microsoft::Diagnostics::Utils::Registry::TryExpandKeyName(std::wstring_view)
0x1800529e6  nop
0x1800529e7  cmp     qword ptr [rdi+8], 0
0x1800529ec  jz      loc_180052B07
0x1800529f2  mov     rdi, [rsp+108h+hKey]
0x1800529f7  test    rdi, rdi
0x1800529fa  jz      short loc_180052A25
0x1800529fc  lea     rcx, [rsp+108h+var_68]; this
0x180052a04  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180052a09  mov     rcx, rdi; hKey
0x180052a0c  call    cs:__imp_RegCloseKey
0x180052a13  nop     dword ptr [rax+rax+00h]
0x180052a18  lea     rcx, [rsp+108h+var_68]; this
0x180052a20  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180052a25  mov     [rsp+108h+hKey], 0
0x180052a2e  lea     rdx, [rsp+108h+lpSubKey]
0x180052a36  cmp     [rsp+108h+var_30], 7
0x180052a3f  cmova   rdx, [rsp+108h+lpSubKey]; lpSubKey
0x180052a48  mov     [rsp+108h+lpdwDisposition], 0; lpdwDisposition
0x180052a51  lea     rax, [rsp+108h+hKey]
0x180052a56  mov     [rsp+108h+phkResult], rax; phkResult
0x180052a5b  mov     [rsp+108h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180052a64  mov     [rsp+108h+samDesired], 2; samDesired
0x180052a6c  mov     eax, [rsp+108h+arg_20]
0x180052a73  mov     [rsp+108h+dwOptions], eax; int
0x180052a77  xor     r9d, r9d; lpClass
0x180052a7a  xor     r8d, r8d; Reserved
0x180052a7d  mov     rcx, [rsp+108h+var_A0]; hKey
0x180052a82  call    cs:__imp_RegCreateKeyExW
0x180052a89  nop     dword ptr [rax+rax+00h]
0x180052a8e  mov     edi, eax
0x180052a90  test    eax, eax
0x180052a92  jle     short loc_180052A9D
0x180052a94  movzx   edi, ax
0x180052a97  or      edi, 80070000h
0x180052a9d  mov     dword ptr [rsp+108h+var_B8], edi
0x180052aa1  test    edi, edi
0x180052aa3  jns     short loc_180052B00
0x180052aa5  mov     rcx, [rsp+108h]; this
0x180052aad  mov     r9d, edi; char *
0x180052ab0  lea     r8, aOnecoreBaseTel_200; "onecore\\base\\telemetry\\utc\\include"...
0x180052ab7  mov     edx, 3ECh; void *
0x180052abc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052ac1  nop
0x180052ac2  lea     rcx, [rsp+108h+lpSubKey]; this
0x180052aca  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x180052acf  nop
0x180052ad0  mov     [rsp+108h+var_70], 0
0x180052ad8  lea     rcx, [rsp+108h+var_98]
0x180052add  call    ??R_lambda_1_@?1??SetDword@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1KK@Z@QEBA@XZ; `Microsoft::Diagnostics::Utils::Registry::SetDword(HKEY__ *,std::wstring_view,std::wstring_view,ulong,ulong)'::`2'::_lambda_1_::operator()(void)
0x180052ae2  nop
0x180052ae3  mov     rcx, [rsp+108h+hKey]; hKey
0x180052ae8  test    rcx, rcx
0x180052aeb  jz      short loc_180052AF9
0x180052aed  call    cs:__imp_RegCloseKey
0x180052af4  nop     dword ptr [rax+rax+00h]
0x180052af9  mov     eax, edi
0x180052afb  jmp     loc_180052C77
0x180052b00  mov     rdi, [rsp+108h+hKey]
0x180052b05  jmp     short loc_180052B65
0x180052b07  mov     rdi, [rsp+108h+var_A0]
0x180052b0c  test    rdi, rdi
0x180052b0f  jnz     short loc_180052B65
0x180052b11  mov     rcx, [rsp+108h]; this
0x180052b19  mov     edi, 80070057h
0x180052b1e  mov     r9d, edi; char *
0x180052b21  lea     r8, aOnecoreBaseTel_200; "onecore\\base\\telemetry\\utc\\include"...
0x180052b28  mov     edx, 3F2h; void *
0x180052b2d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052b32  nop
0x180052b33  lea     rcx, [rsp+108h+lpSubKey]; this
0x180052b3b  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x180052b40  nop
0x180052b41  mov     [rsp+108h+var_70], 0
0x180052b49  lea     rcx, [rsp+108h+var_98]
0x180052b4e  call    ??R_lambda_1_@?1??SetDword@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1KK@Z@QEBA@XZ; `Microsoft::Diagnostics::Utils::Registry::SetDword(HKEY__ *,std::wstring_view,std::wstring_view,ulong,ulong)'::`2'::_lambda_1_::operator()(void)
0x180052b53  nop
0x180052b54  lea     rcx, [rsp+108h+hKey]
0x180052b59  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180052b5e  mov     eax, edi
0x180052b60  jmp     loc_180052C77
0x180052b65  mov     rdx, rsi
0x180052b68  lea     rcx, [rsp+108h+var_68]
0x180052b70  call    ??$?0V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_zstring_view@_W@wil@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wil::basic_zstring_view<wchar_t> const &,std::allocator<wchar_t> const &)
0x180052b75  cmp     qword ptr [rax+18h], 7
0x180052b7a  jbe     short loc_180052B7F
0x180052b7c  mov     rax, [rax]
0x180052b7f  mov     r9d, 4; dwType
0x180052b85  mov     [rsp+108h+samDesired], r9d; cbData
0x180052b8a  lea     rcx, [rsp+108h+Data]
0x180052b8f  mov     qword ptr [rsp+108h+dwOptions], rcx; int
0x180052b94  xor     r8d, r8d; Reserved
0x180052b97  mov     rdx, rax; lpValueName
0x180052b9a  mov     rcx, rdi; hKey
0x180052b9d  call    cs:__imp_RegSetValueExW
0x180052ba4  nop     dword ptr [rax+rax+00h]
0x180052ba9  test    eax, eax
0x180052bab  jle     short loc_180052BB5
0x180052bad  movzx   eax, ax
0x180052bb0  or      eax, 80070000h
0x180052bb5  mov     dword ptr [rsp+108h+var_B8], eax
0x180052bb9  lea     rcx, [rsp+108h+var_68]; this
0x180052bc1  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x180052bc6  mov     edi, dword ptr [rsp+108h+var_B8]
0x180052bca  test    edi, edi
0x180052bcc  jns     short loc_180052C1A
0x180052bce  mov     rcx, [rsp+108h]; this
0x180052bd6  mov     r9d, edi; char *
0x180052bd9  lea     r8, aOnecoreBaseTel_200; "onecore\\base\\telemetry\\utc\\include"...
0x180052be0  mov     edx, 3FCh; void *
0x180052be5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052bea  nop
0x180052beb  lea     rcx, [rsp+108h+lpSubKey]; this
0x180052bf3  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x180052bf8  nop
0x180052bf9  mov     [rsp+108h+var_70], 0
0x180052c01  lea     rcx, [rsp+108h+var_98]
0x180052c06  call    ??R_lambda_1_@?1??SetDword@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1KK@Z@QEBA@XZ; `Microsoft::Diagnostics::Utils::Registry::SetDword(HKEY__ *,std::wstring_view,std::wstring_view,ulong,ulong)'::`2'::_lambda_1_::operator()(void)
0x180052c0b  nop
0x180052c0c  lea     rcx, [rsp+108h+hKey]
0x180052c11  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180052c16  mov     eax, edi
0x180052c18  jmp     short loc_180052C77
0x180052c1a  lea     rcx, [rsp+108h+lpSubKey]; this
0x180052c22  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x180052c27  nop
0x180052c28  mov     [rsp+108h+var_70], 0
0x180052c30  lea     rcx, [rsp+108h+var_98]
0x180052c35  call    ??R_lambda_1_@?1??SetDword@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1KK@Z@QEBA@XZ; `Microsoft::Diagnostics::Utils::Registry::SetDword(HKEY__ *,std::wstring_view,std::wstring_view,ulong,ulong)'::`2'::_lambda_1_::operator()(void)
0x180052c3a  nop
0x180052c3b  lea     rcx, [rsp+108h+hKey]
0x180052c40  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180052c45  xor     eax, eax
0x180052c47  jmp     short loc_180052C77
0x180052c49  cmp     [rsp+108h+var_70], 0
0x180052c51  jz      short loc_180052C66
0x180052c53  mov     [rsp+108h+var_70], 0
0x180052c5b  lea     rcx, [rsp+108h+var_98]
0x180052c60  call    ??R_lambda_1_@?1??SetDword@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1KK@Z@QEBA@XZ; `Microsoft::Diagnostics::Utils::Registry::SetDword(HKEY__ *,std::wstring_view,std::wstring_view,ulong,ulong)'::`2'::_lambda_1_::operator()(void)
0x180052c65  nop
0x180052c66  lea     rcx, [rsp+108h+hKey]
0x180052c6b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180052c70  mov     eax, [rsp+108h+var_68]
0x180052c77  mov     rcx, [rsp+108h+var_28]
0x180052c7f  xor     rcx, rsp; StackCookie
0x180052c82  call    __security_check_cookie
0x180052c87  add     rsp, 0F8h
0x180052c8e  pop     rdi
0x180052c8f  pop     rsi
0x180052c90  retn
```
