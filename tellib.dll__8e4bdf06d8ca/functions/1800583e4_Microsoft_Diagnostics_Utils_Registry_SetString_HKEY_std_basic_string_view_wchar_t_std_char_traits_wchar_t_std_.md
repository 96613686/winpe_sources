# Microsoft::Diagnostics::Utils::Registry::SetString(HKEY__ *,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,ulong)

- ea: `0x1800583e4`
- end: `0x180058745`
- name: `?SetString@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@11K@Z`
- size: `865`
- prototype: `__int64 __fastcall(int, int, int, int, DWORD)`
- caller_count: `14`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180055964`
- `0x180058358`
- `0x18009c344`
- `0x18009ff40`
- `0x1800a0f08`
- `0x1800fde44`
- `0x1801125dc`
- `0x180120664`
- `0x18018efe0`
- `0x180197744`
- `0x1801ac168`
- `0x180272c08`
- `0x1802d0710`
- `0x1802fbf00`

## callees

- `0x18001d160`
- `0x180024e2c`
- `0x180026ecc`
- `0x180027e64`
- `0x1800583e4`
- `0x18005af1c`
- `0x180098d5c`
- `0x1800acd9c`
- `0x1800b83bc`
- `0x18012de40`
- `0x180171888`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180058484`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800586be`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180058484`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800586be`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800584f7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800584f7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180058645`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180058645`

## string_xrefs

- `0x180058525`: `onecore\base\telemetry\utc\include\RegistryUtils.h`
- `0x18005858a`: `onecore\base\telemetry\utc\include\RegistryUtils.h`
- `0x180058681`: `onecore\base\telemetry\utc\include\RegistryUtils.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::Diagnostics::Utils::Registry::SetString(
        HKEY a1,
        __int64 a2,
        _QWORD *a3,
        __int64 a4,
        DWORD a5)
{
  HKEY v8; // rdi
  const WCHAR *v9; // rdx
  LSTATUS v10; // eax
  unsigned int v11; // edi
  const char *v12; // r9
  __int64 result; // rax
  HKEY v14; // rdi
  const WCHAR *v15; // rdx
  int v16; // eax
  unsigned int v17; // edi
  int dwOptions; // [rsp+20h] [rbp-E8h]
  int dwOptionsa; // [rsp+20h] [rbp-E8h]
  int dwOptionsb; // [rsp+20h] [rbp-E8h]
  char *v21; // [rsp+50h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-B0h] BYREF
  BYTE *lpData[2]; // [rsp+60h] [rbp-A8h] BYREF
  HKEY v24; // [rsp+70h] [rbp-98h] BYREF
  _QWORD v25[5]; // [rsp+78h] [rbp-90h] BYREF
  char v26; // [rsp+A0h] [rbp-68h]
  LPCWSTR lpSubKey[4]; // [rsp+A8h] [rbp-60h] BYREF
  LPCWSTR lpValueName[2]; // [rsp+C8h] [rbp-40h] BYREF
  __int128 v29; // [rsp+D8h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  try
  {
    v24 = a1;
    LODWORD(v21) = 0;
    hKey = 0;
    v25[0] = &v24;
    v25[1] = a2;
    v25[2] = a3;
    v25[3] = a4;
    v25[4] = &v21;
    v26 = 1;
    *(_OWORD *)lpData = *(_OWORD *)a2;
    Microsoft::Diagnostics::Utils::Registry::TryExpandKeyName((LPCWSTR)lpSubKey);
    if ( *(_QWORD *)(a2 + 8) )
    {
      v8 = hKey;
      if ( hKey )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)lpData);
        RegCloseKey(v8);
        wil::last_error_context::~last_error_context((wil::last_error_context *)lpData);
      }
      hKey = 0;
      v9 = (const WCHAR *)lpSubKey;
      if ( lpSubKey[3] > (LPCWSTR)7 )
        v9 = lpSubKey[0];
      v10 = RegCreateKeyExW(v24, v9, 0, 0, a5, 2u, 0, &hKey, 0);
      v11 = v10;
      if ( v10 > 0 )
        v11 = (unsigned __int16)v10 | 0x80070000;
      LODWORD(v21) = v11;
      if ( (v11 & 0x80000000) != 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xF5,
          (unsigned int)"onecore\\base\\telemetry\\utc\\include\\RegistryUtils.h",
          (const char *)v11,
          dwOptionsa);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpSubKey);
        v26 = 0;
        `Microsoft::Diagnostics::Utils::Registry::SetString'::`2'::_lambda_1_::operator()(v25);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        return v11;
      }
      v14 = hKey;
    }
    else
    {
      v14 = v24;
      if ( !v24 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xFB,
          (unsigned int)"onecore\\base\\telemetry\\utc\\include\\RegistryUtils.h",
          (const char *)0x80070057LL,
          dwOptions);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpSubKey);
        v26 = 0;
        `Microsoft::Diagnostics::Utils::Registry::SetString'::`2'::_lambda_1_::operator()(v25);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        return 2147942487LL;
      }
    }
    gslp::container_to_bytes<std::wstring_view>(lpData, a4);
    *(_OWORD *)lpValueName = 0;
    v29 = 0;
    std::wstring::_Construct<1,wchar_t *>(lpValueName, *a3, a3[1]);
    v15 = (const WCHAR *)lpValueName;
    if ( *((_QWORD *)&v29 + 1) > 7u )
      v15 = lpValueName[0];
    v16 = RegSetValueExW(v14, v15, 0, 1u, lpData[1], (DWORD)lpData[0]);
    if ( v16 > 0 )
      v16 = (unsigned __int16)v16 | 0x80070000;
    LODWORD(v21) = v16;
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpValueName);
    v17 = (unsigned int)v21;
    if ( (int)v21 >= 0 )
    {
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpSubKey);
      v26 = 0;
      `Microsoft::Diagnostics::Utils::Registry::SetString'::`2'::_lambda_1_::operator()(v25);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      result = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x106,
        (unsigned int)"onecore\\base\\telemetry\\utc\\include\\RegistryUtils.h",
        (const char *)(unsigned int)v21,
        dwOptionsb);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpSubKey);
      v26 = 0;
      `Microsoft::Diagnostics::Utils::Registry::SetString'::`2'::_lambda_1_::operator()(v25);
      if ( hKey )
        RegCloseKey(hKey);
      result = v17;
    }
  }
  catch ( ... )
  {
    LODWORD(lpData[0]) = wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x10A,
                           (unsigned int)"onecore\\base\\telemetry\\utc\\include\\RegistryUtils.h",
                           v12);
    if ( v26 )
    {
      v26 = 0;
      `Microsoft::Diagnostics::Utils::Registry::SetString'::`2'::_lambda_1_::operator()(v25);
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return LODWORD(lpData[0]);
  }
  return result;
}

```

## disassembly

```asm
0x1800583e4  mov     r11, rsp
0x1800583e7  push    rsi
0x1800583e8  push    rdi
0x1800583e9  push    r14
0x1800583eb  sub     rsp, 0F0h
0x1800583f2  mov     rax, cs:__security_cookie
0x1800583f9  xor     rax, rsp
0x1800583fc  mov     [rsp+108h+var_20], rax
0x180058404  mov     r14, r9
0x180058407  mov     rsi, r8
0x18005840a  mov     rdi, rdx
0x18005840d  mov     [rsp+108h+var_98], rcx
0x180058412  mov     dword ptr [rsp+108h+var_B8], 0
0x18005841a  mov     [rsp+108h+hKey], 0
0x180058423  lea     rax, [rsp+108h+var_98]
0x180058428  mov     [rsp+108h+var_90], rax
0x18005842d  mov     [r11-88h], rdx
0x180058434  mov     [r11-80h], r8
0x180058438  mov     [r11-78h], r9
0x18005843c  lea     rax, [rsp+108h+var_B8]
0x180058441  mov     [r11-70h], rax
0x180058445  mov     byte ptr [r11-68h], 1
0x18005844a  movups  xmm0, xmmword ptr [rdx]
0x18005844d  movdqu  xmmword ptr [rsp+108h+lpData], xmm0
0x180058453  lea     rdx, [rsp+108h+lpData]
0x180058458  lea     rcx, [r11-60h]
0x18005845c  call    ?TryExpandKeyName@Registry@Utils@Diagnostics@Microsoft@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@6@@Z; Microsoft::Diagnostics::Utils::Registry::TryExpandKeyName(std::wstring_view)
0x180058461  nop
0x180058462  cmp     qword ptr [rdi+8], 0
0x180058467  jz      loc_180058570
0x18005846d  mov     rdi, [rsp+108h+hKey]
0x180058472  test    rdi, rdi
0x180058475  jz      short loc_18005849A
0x180058477  lea     rcx, [rsp+108h+lpData]; this
0x18005847c  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180058481  mov     rcx, rdi; hKey
0x180058484  call    cs:__imp_RegCloseKey
0x18005848b  nop     dword ptr [rax+rax+00h]
0x180058490  lea     rcx, [rsp+108h+lpData]; this
0x180058495  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18005849a  mov     [rsp+108h+hKey], 0
0x1800584a3  lea     rdx, [rsp+108h+lpSubKey]
0x1800584ab  cmp     [rsp+108h+var_48], 7
0x1800584b4  cmova   rdx, [rsp+108h+lpSubKey]; lpSubKey
0x1800584bd  mov     [rsp+108h+lpdwDisposition], 0; lpdwDisposition
0x1800584c6  lea     rax, [rsp+108h+hKey]
0x1800584cb  mov     [rsp+108h+phkResult], rax; phkResult
0x1800584d0  mov     [rsp+108h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800584d9  mov     [rsp+108h+samDesired], 2; samDesired
0x1800584e1  mov     eax, [rsp+108h+arg_20]
0x1800584e8  mov     [rsp+108h+dwOptions], eax; int
0x1800584ec  xor     r9d, r9d; lpClass
0x1800584ef  xor     r8d, r8d; Reserved
0x1800584f2  mov     rcx, [rsp+108h+var_98]; hKey
0x1800584f7  call    cs:__imp_RegCreateKeyExW
0x1800584fe  nop     dword ptr [rax+rax+00h]
0x180058503  mov     edi, eax
0x180058505  test    eax, eax
0x180058507  jle     short loc_180058512
0x180058509  movzx   edi, ax
0x18005850c  or      edi, 80070000h
0x180058512  mov     dword ptr [rsp+108h+var_B8], edi
0x180058516  test    edi, edi
0x180058518  jns     short loc_180058569
0x18005851a  mov     rcx, [rsp+108h]; this
0x180058522  mov     r9d, edi; char *
0x180058525  lea     r8, aOnecoreBaseTel_200; "onecore\\base\\telemetry\\utc\\include"...
0x18005852c  mov     edx, 0F5h; void *
0x180058531  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058536  nop
0x180058537  lea     rcx, [rsp+108h+lpSubKey]; this
0x18005853f  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x180058544  nop
0x180058545  mov     [rsp+108h+var_68], 0
0x18005854d  lea     rcx, [rsp+108h+var_90]
0x180058552  call    ??R_lambda_1_@?1??SetString@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@11K@Z@QEBA@XZ; `Microsoft::Diagnostics::Utils::Registry::SetString(HKEY__ *,std::wstring_view,std::wstring_view,std::wstring_view,ulong)'::`2'::_lambda_1_::operator()(void)
0x180058557  nop
0x180058558  lea     rcx, [rsp+108h+hKey]
0x18005855d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180058562  mov     eax, edi
0x180058564  jmp     loc_180058728
0x180058569  mov     rdi, [rsp+108h+hKey]
0x18005856e  jmp     short loc_1800585CE
0x180058570  mov     rdi, [rsp+108h+var_98]
0x180058575  test    rdi, rdi
0x180058578  jnz     short loc_1800585CE
0x18005857a  mov     rcx, [rsp+108h]; this
0x180058582  mov     edi, 80070057h
0x180058587  mov     r9d, edi; char *
0x18005858a  lea     r8, aOnecoreBaseTel_200; "onecore\\base\\telemetry\\utc\\include"...
0x180058591  mov     edx, 0FBh; void *
0x180058596  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005859b  nop
0x18005859c  lea     rcx, [rsp+108h+lpSubKey]; this
0x1800585a4  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1800585a9  nop
0x1800585aa  mov     [rsp+108h+var_68], 0
0x1800585b2  lea     rcx, [rsp+108h+var_90]
0x1800585b7  call    ??R_lambda_1_@?1??SetString@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@11K@Z@QEBA@XZ; `Microsoft::Diagnostics::Utils::Registry::SetString(HKEY__ *,std::wstring_view,std::wstring_view,std::wstring_view,ulong)'::`2'::_lambda_1_::operator()(void)
0x1800585bc  nop
0x1800585bd  lea     rcx, [rsp+108h+hKey]
0x1800585c2  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800585c7  mov     eax, edi
0x1800585c9  jmp     loc_180058728
0x1800585ce  mov     rdx, r14
0x1800585d1  lea     rcx, [rsp+108h+lpData]
0x1800585d6  call    ??$container_to_bytes@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@gslp@@YA?AV?$span@$$CBW4byte@gsl@@$0?0@gsl@@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; gslp::container_to_bytes<std::wstring_view>(std::wstring_view const &)
0x1800585db  xorps   xmm0, xmm0
0x1800585de  movups  xmmword ptr [rsp+108h+lpValueName], xmm0
0x1800585e6  xorps   xmm1, xmm1
0x1800585e9  movdqu  [rsp+108h+var_30], xmm1
0x1800585f2  mov     r8, [rsi+8]
0x1800585f6  mov     rdx, [rsi]
0x1800585f9  lea     rcx, [rsp+108h+lpValueName]
0x180058601  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x180058606  lea     rdx, [rsp+108h+lpValueName]
0x18005860e  cmp     qword ptr [rsp+108h+var_30+8], 7
0x180058617  setnbe  al
0x18005861a  mov     r8d, dword ptr [rsp+108h+lpData]
0x18005861f  mov     r10, [rsp+108h+lpData+8]
0x180058624  test    al, al
0x180058626  cmovnz  rdx, [rsp+108h+lpValueName]; lpValueName
0x18005862f  mov     [rsp+108h+samDesired], r8d; cbData
0x180058634  mov     qword ptr [rsp+108h+dwOptions], r10; int
0x180058639  mov     r9d, 1; dwType
0x18005863f  xor     r8d, r8d; Reserved
0x180058642  mov     rcx, rdi; hKey
0x180058645  call    cs:__imp_RegSetValueExW
0x18005864c  nop     dword ptr [rax+rax+00h]
0x180058651  test    eax, eax
0x180058653  jle     short loc_18005865D
0x180058655  movzx   eax, ax
0x180058658  or      eax, 80070000h
0x18005865d  mov     dword ptr [rsp+108h+var_B8], eax
0x180058661  lea     rcx, [rsp+108h+lpValueName]; this
0x180058669  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18005866e  mov     edi, dword ptr [rsp+108h+var_B8]
0x180058672  test    edi, edi
0x180058674  jns     short loc_1800586CE
0x180058676  mov     rcx, [rsp+108h]; this
0x18005867e  mov     r9d, edi; char *
0x180058681  lea     r8, aOnecoreBaseTel_200; "onecore\\base\\telemetry\\utc\\include"...
0x180058688  mov     edx, 106h; void *
0x18005868d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058692  nop
0x180058693  lea     rcx, [rsp+108h+lpSubKey]; this
0x18005869b  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1800586a0  nop
0x1800586a1  mov     [rsp+108h+var_68], 0
0x1800586a9  lea     rcx, [rsp+108h+var_90]
0x1800586ae  call    ??R_lambda_1_@?1??SetString@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@11K@Z@QEBA@XZ; `Microsoft::Diagnostics::Utils::Registry::SetString(HKEY__ *,std::wstring_view,std::wstring_view,std::wstring_view,ulong)'::`2'::_lambda_1_::operator()(void)
0x1800586b3  nop
0x1800586b4  mov     rcx, [rsp+108h+hKey]; hKey
0x1800586b9  test    rcx, rcx
0x1800586bc  jz      short loc_1800586CA
0x1800586be  call    cs:__imp_RegCloseKey
0x1800586c5  nop     dword ptr [rax+rax+00h]
0x1800586ca  mov     eax, edi
0x1800586cc  jmp     short loc_180058728
0x1800586ce  lea     rcx, [rsp+108h+lpSubKey]; this
0x1800586d6  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1800586db  nop
0x1800586dc  mov     [rsp+108h+var_68], 0
0x1800586e4  lea     rcx, [rsp+108h+var_90]
0x1800586e9  call    ??R_lambda_1_@?1??SetString@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@11K@Z@QEBA@XZ; `Microsoft::Diagnostics::Utils::Registry::SetString(HKEY__ *,std::wstring_view,std::wstring_view,std::wstring_view,ulong)'::`2'::_lambda_1_::operator()(void)
0x1800586ee  nop
0x1800586ef  lea     rcx, [rsp+108h+hKey]
0x1800586f4  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800586f9  xor     eax, eax
0x1800586fb  jmp     short loc_180058728
0x1800586fd  cmp     [rsp+108h+var_68], 0
0x180058705  jz      short loc_18005871A
0x180058707  mov     [rsp+108h+var_68], 0
0x18005870f  lea     rcx, [rsp+108h+var_90]
0x180058714  call    ??R_lambda_1_@?1??SetString@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@11K@Z@QEBA@XZ; `Microsoft::Diagnostics::Utils::Registry::SetString(HKEY__ *,std::wstring_view,std::wstring_view,std::wstring_view,ulong)'::`2'::_lambda_1_::operator()(void)
0x180058719  nop
0x18005871a  lea     rcx, [rsp+108h+hKey]
0x18005871f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180058724  mov     eax, dword ptr [rsp+108h+lpData]
0x180058728  mov     rcx, [rsp+108h+var_20]
0x180058730  xor     rcx, rsp; StackCookie
0x180058733  call    __security_check_cookie
0x180058738  add     rsp, 0F0h
0x18005873f  pop     r14
0x180058741  pop     rdi
0x180058742  pop     rsi
0x180058743  retn
```
