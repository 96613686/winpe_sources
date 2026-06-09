# Microsoft::Diagnostics::Utils::Registry::SetQword(HKEY__ *,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,unsigned __int64,ulong)

- ea: `0x1800562b8`
- end: `0x180056629`
- name: `?SetQword@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1_KK@Z`
- size: `881`
- prototype: `__int64 __fastcall(int, int, int, int, DWORD)`
- caller_count: `26`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18006102c`
- `0x18009addc`
- `0x1800ef4b8`
- `0x1800f1698`
- `0x1800f5fe4`
- `0x180101678`
- `0x1801058b4`
- `0x18010c924`
- `0x1801201b4`
- `0x180120664`
- `0x180128d30`
- `0x1801702d8`
- `0x18018efe0`
- `0x180194dac`
- `0x180197744`
- `0x1801ac060`
- `0x1801ac168`
- `0x1801ac750`
- `0x1801b446c`
- `0x180267498`
- `0x180268620`
- `0x180272c08`
- `0x1802830c8`
- `0x1802ad018`
- `0x1802fbf00`
- `0x180306a50`

## callees

- `0x18001d160`
- `0x180024e2c`
- `0x180026ecc`
- `0x180027e64`
- `0x1800562b8`
- `0x18005af1c`
- `0x180098d5c`
- `0x1800b83bc`
- `0x18012de40`
- `0x180160c84`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180056360`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180056441`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180056595`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800565d0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180056360`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180056441`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180056595`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800565d0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800563d6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800563d6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005651c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005651c`

## string_xrefs

- `0x180056404`: `onecore\base\telemetry\utc\include\RegistryUtils.h`
- `0x180056475`: `onecore\base\telemetry\utc\include\RegistryUtils.h`
- `0x180056558`: `onecore\base\telemetry\utc\include\RegistryUtils.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::Diagnostics::Utils::Registry::SetQword(
        HKEY a1,
        __int64 a2,
        _QWORD *a3,
        __int64 a4,
        DWORD a5)
{
  HKEY v7; // rdi
  const WCHAR *v8; // rdx
  LSTATUS v9; // eax
  unsigned int v10; // edi
  const char *v11; // r9
  __int64 result; // rax
  HKEY v13; // rdi
  const WCHAR *v14; // rdx
  int v15; // eax
  unsigned int v16; // edi
  int dwOptions; // [rsp+20h] [rbp-E8h]
  int dwOptionsa; // [rsp+20h] [rbp-E8h]
  int dwOptionsb; // [rsp+20h] [rbp-E8h]
  char *v20; // [rsp+50h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-B0h] BYREF
  HKEY v22; // [rsp+60h] [rbp-A8h] BYREF
  BYTE Data[8]; // [rsp+68h] [rbp-A0h] BYREF
  _QWORD v24[5]; // [rsp+70h] [rbp-98h] BYREF
  char v25; // [rsp+98h] [rbp-70h]
  LPCWSTR lpValueName[2]; // [rsp+A0h] [rbp-68h] BYREF
  __int128 v27; // [rsp+B0h] [rbp-58h]
  LPCWSTR lpSubKey[4]; // [rsp+C0h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  try
  {
    v22 = a1;
    *(_QWORD *)Data = a4;
    LODWORD(v20) = 0;
    hKey = 0;
    v24[0] = &v22;
    v24[1] = a2;
    v24[2] = a3;
    v24[3] = Data;
    v24[4] = &v20;
    v25 = 1;
    *(_OWORD *)lpValueName = *(_OWORD *)a2;
    Microsoft::Diagnostics::Utils::Registry::TryExpandKeyName((LPCWSTR)lpSubKey);
    if ( *(_QWORD *)(a2 + 8) )
    {
      v7 = hKey;
      if ( hKey )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)lpValueName);
        RegCloseKey(v7);
        wil::last_error_context::~last_error_context((wil::last_error_context *)lpValueName);
      }
      hKey = 0;
      v8 = (const WCHAR *)lpSubKey;
      if ( lpSubKey[3] > (LPCWSTR)7 )
        v8 = lpSubKey[0];
      v9 = RegCreateKeyExW(v22, v8, 0, 0, a5, 2u, 0, &hKey, 0);
      v10 = v9;
      if ( v9 > 0 )
        v10 = (unsigned __int16)v9 | 0x80070000;
      LODWORD(v20) = v10;
      if ( (v10 & 0x80000000) != 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4FF,
          (unsigned int)"onecore\\base\\telemetry\\utc\\include\\RegistryUtils.h",
          (const char *)v10,
          dwOptionsa);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpSubKey);
        v25 = 0;
        `Microsoft::Diagnostics::Utils::Registry::SetQword'::`2'::_lambda_1_::operator()(v24);
        if ( hKey )
          RegCloseKey(hKey);
        return v10;
      }
      v13 = hKey;
    }
    else
    {
      v13 = v22;
      if ( !v22 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x505,
          (unsigned int)"onecore\\base\\telemetry\\utc\\include\\RegistryUtils.h",
          (const char *)0x80070057LL,
          dwOptions);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpSubKey);
        v25 = 0;
        `Microsoft::Diagnostics::Utils::Registry::SetQword'::`2'::_lambda_1_::operator()(v24);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        return 2147942487LL;
      }
    }
    *(_OWORD *)lpValueName = 0;
    v27 = 0;
    std::wstring::_Construct<1,wchar_t *>(lpValueName, *a3, a3[1]);
    v14 = (const WCHAR *)lpValueName;
    if ( *((_QWORD *)&v27 + 1) > 7u )
      v14 = lpValueName[0];
    v15 = RegSetValueExW(v13, v14, 0, 0xBu, Data, 8u);
    if ( v15 > 0 )
      v15 = (unsigned __int16)v15 | 0x80070000;
    LODWORD(v20) = v15;
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpValueName);
    v16 = (unsigned int)v20;
    if ( (int)v20 >= 0 )
    {
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpSubKey);
      v25 = 0;
      `Microsoft::Diagnostics::Utils::Registry::SetQword'::`2'::_lambda_1_::operator()(v24);
      if ( hKey )
        RegCloseKey(hKey);
      result = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x509,
        (unsigned int)"onecore\\base\\telemetry\\utc\\include\\RegistryUtils.h",
        (const char *)(unsigned int)v20,
        dwOptionsb);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpSubKey);
      v25 = 0;
      `Microsoft::Diagnostics::Utils::Registry::SetQword'::`2'::_lambda_1_::operator()(v24);
      if ( hKey )
        RegCloseKey(hKey);
      result = v16;
    }
  }
  catch ( ... )
  {
    LODWORD(lpValueName[0]) = wil::details::in1diag3::Return_CaughtException(
                                retaddr,
                                (void *)0x50D,
                                (unsigned int)"onecore\\base\\telemetry\\utc\\include\\RegistryUtils.h",
                                v11);
    if ( v25 )
    {
      v25 = 0;
      `Microsoft::Diagnostics::Utils::Registry::SetQword'::`2'::_lambda_1_::operator()(v24);
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return LODWORD(lpValueName[0]);
  }
  return result;
}

```

## disassembly

```asm
0x1800562b8  mov     r11, rsp
0x1800562bb  push    rsi
0x1800562bc  push    rdi
0x1800562bd  sub     rsp, 0F8h
0x1800562c4  mov     rax, cs:__security_cookie
0x1800562cb  xor     rax, rsp
0x1800562ce  mov     [rsp+108h+var_28], rax
0x1800562d6  mov     rsi, r8
0x1800562d9  mov     rdi, rdx
0x1800562dc  mov     [rsp+108h+var_A8], rcx
0x1800562e1  mov     qword ptr [rsp+108h+Data], r9
0x1800562e6  mov     dword ptr [rsp+108h+var_B8], 0
0x1800562ee  mov     [rsp+108h+hKey], 0
0x1800562f7  lea     rax, [rsp+108h+var_A8]
0x1800562fc  mov     [rsp+108h+var_98], rax
0x180056301  mov     [rsp+108h+var_90], rdx
0x180056306  mov     [r11-88h], r8
0x18005630d  lea     rax, [rsp+108h+Data]
0x180056312  mov     [r11-80h], rax
0x180056316  lea     rax, [rsp+108h+var_B8]
0x18005631b  mov     [r11-78h], rax
0x18005631f  mov     byte ptr [r11-70h], 1
0x180056324  movups  xmm0, xmmword ptr [rdx]
0x180056327  movdqu  xmmword ptr [r11-68h], xmm0
0x18005632d  lea     rdx, [r11-68h]
0x180056331  lea     rcx, [r11-48h]
0x180056335  call    ?TryExpandKeyName@Registry@Utils@Diagnostics@Microsoft@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@6@@Z; Microsoft::Diagnostics::Utils::Registry::TryExpandKeyName(std::wstring_view)
0x18005633a  nop
0x18005633b  cmp     qword ptr [rdi+8], 0
0x180056340  jz      loc_18005645B
0x180056346  mov     rdi, [rsp+108h+hKey]
0x18005634b  test    rdi, rdi
0x18005634e  jz      short loc_180056379
0x180056350  lea     rcx, [rsp+108h+lpValueName]; this
0x180056358  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18005635d  mov     rcx, rdi; hKey
0x180056360  call    cs:__imp_RegCloseKey
0x180056367  nop     dword ptr [rax+rax+00h]
0x18005636c  lea     rcx, [rsp+108h+lpValueName]; this
0x180056374  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180056379  mov     [rsp+108h+hKey], 0
0x180056382  lea     rdx, [rsp+108h+lpSubKey]
0x18005638a  cmp     [rsp+108h+var_30], 7
0x180056393  cmova   rdx, [rsp+108h+lpSubKey]; lpSubKey
0x18005639c  mov     [rsp+108h+lpdwDisposition], 0; lpdwDisposition
0x1800563a5  lea     rax, [rsp+108h+hKey]
0x1800563aa  mov     [rsp+108h+phkResult], rax; phkResult
0x1800563af  mov     [rsp+108h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800563b8  mov     [rsp+108h+samDesired], 2; samDesired
0x1800563c0  mov     eax, [rsp+108h+arg_20]
0x1800563c7  mov     [rsp+108h+dwOptions], eax; int
0x1800563cb  xor     r9d, r9d; lpClass
0x1800563ce  xor     r8d, r8d; Reserved
0x1800563d1  mov     rcx, [rsp+108h+var_A8]; hKey
0x1800563d6  call    cs:__imp_RegCreateKeyExW
0x1800563dd  nop     dword ptr [rax+rax+00h]
0x1800563e2  mov     edi, eax
0x1800563e4  test    eax, eax
0x1800563e6  jle     short loc_1800563F1
0x1800563e8  movzx   edi, ax
0x1800563eb  or      edi, 80070000h
0x1800563f1  mov     dword ptr [rsp+108h+var_B8], edi
0x1800563f5  test    edi, edi
0x1800563f7  jns     short loc_180056454
0x1800563f9  mov     rcx, [rsp+108h]; this
0x180056401  mov     r9d, edi; char *
0x180056404  lea     r8, aOnecoreBaseTel_200; "onecore\\base\\telemetry\\utc\\include"...
0x18005640b  mov     edx, 4FFh; void *
0x180056410  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180056415  nop
0x180056416  lea     rcx, [rsp+108h+lpSubKey]; this
0x18005641e  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x180056423  nop
0x180056424  mov     [rsp+108h+var_70], 0
0x18005642c  lea     rcx, [rsp+108h+var_98]
0x180056431  call    ??R_lambda_1_@?1??SetQword@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1_KK@Z@QEBA@XZ; `Microsoft::Diagnostics::Utils::Registry::SetQword(HKEY__ *,std::wstring_view,std::wstring_view,unsigned __int64,ulong)'::`2'::_lambda_1_::operator()(void)
0x180056436  nop
0x180056437  mov     rcx, [rsp+108h+hKey]; hKey
0x18005643c  test    rcx, rcx
0x18005643f  jz      short loc_18005644D
0x180056441  call    cs:__imp_RegCloseKey
0x180056448  nop     dword ptr [rax+rax+00h]
0x18005644d  mov     eax, edi
0x18005644f  jmp     loc_18005660E
0x180056454  mov     rdi, [rsp+108h+hKey]
0x180056459  jmp     short loc_1800564B9
0x18005645b  mov     rdi, [rsp+108h+var_A8]
0x180056460  test    rdi, rdi
0x180056463  jnz     short loc_1800564B9
0x180056465  mov     rcx, [rsp+108h]; this
0x18005646d  mov     edi, 80070057h
0x180056472  mov     r9d, edi; char *
0x180056475  lea     r8, aOnecoreBaseTel_200; "onecore\\base\\telemetry\\utc\\include"...
0x18005647c  mov     edx, 505h; void *
0x180056481  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180056486  nop
0x180056487  lea     rcx, [rsp+108h+lpSubKey]; this
0x18005648f  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x180056494  nop
0x180056495  mov     [rsp+108h+var_70], 0
0x18005649d  lea     rcx, [rsp+108h+var_98]
0x1800564a2  call    ??R_lambda_1_@?1??SetQword@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1_KK@Z@QEBA@XZ; `Microsoft::Diagnostics::Utils::Registry::SetQword(HKEY__ *,std::wstring_view,std::wstring_view,unsigned __int64,ulong)'::`2'::_lambda_1_::operator()(void)
0x1800564a7  nop
0x1800564a8  lea     rcx, [rsp+108h+hKey]
0x1800564ad  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800564b2  mov     eax, edi
0x1800564b4  jmp     loc_18005660E
0x1800564b9  xorps   xmm0, xmm0
0x1800564bc  movups  xmmword ptr [rsp+108h+lpValueName], xmm0
0x1800564c4  xorps   xmm1, xmm1
0x1800564c7  movdqu  [rsp+108h+var_58], xmm1
0x1800564d0  mov     r8, [rsi+8]
0x1800564d4  mov     rdx, [rsi]
0x1800564d7  lea     rcx, [rsp+108h+lpValueName]
0x1800564df  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x1800564e4  lea     rdx, [rsp+108h+lpValueName]
0x1800564ec  cmp     qword ptr [rsp+108h+var_58+8], 7
0x1800564f5  cmova   rdx, [rsp+108h+lpValueName]; lpValueName
0x1800564fe  mov     [rsp+108h+samDesired], 8; cbData
0x180056506  lea     rax, [rsp+108h+Data]
0x18005650b  mov     qword ptr [rsp+108h+dwOptions], rax; int
0x180056510  mov     r9d, 0Bh; dwType
0x180056516  xor     r8d, r8d; Reserved
0x180056519  mov     rcx, rdi; hKey
0x18005651c  call    cs:__imp_RegSetValueExW
0x180056523  nop     dword ptr [rax+rax+00h]
0x180056528  test    eax, eax
0x18005652a  jle     short loc_180056534
0x18005652c  movzx   eax, ax
0x18005652f  or      eax, 80070000h
0x180056534  mov     dword ptr [rsp+108h+var_B8], eax
0x180056538  lea     rcx, [rsp+108h+lpValueName]; this
0x180056540  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x180056545  mov     edi, dword ptr [rsp+108h+var_B8]
0x180056549  test    edi, edi
0x18005654b  jns     short loc_1800565A5
0x18005654d  mov     rcx, [rsp+108h]; this
0x180056555  mov     r9d, edi; char *
0x180056558  lea     r8, aOnecoreBaseTel_200; "onecore\\base\\telemetry\\utc\\include"...
0x18005655f  mov     edx, 509h; void *
0x180056564  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180056569  nop
0x18005656a  lea     rcx, [rsp+108h+lpSubKey]; this
0x180056572  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x180056577  nop
0x180056578  mov     [rsp+108h+var_70], 0
0x180056580  lea     rcx, [rsp+108h+var_98]
0x180056585  call    ??R_lambda_1_@?1??SetQword@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1_KK@Z@QEBA@XZ; `Microsoft::Diagnostics::Utils::Registry::SetQword(HKEY__ *,std::wstring_view,std::wstring_view,unsigned __int64,ulong)'::`2'::_lambda_1_::operator()(void)
0x18005658a  nop
0x18005658b  mov     rcx, [rsp+108h+hKey]; hKey
0x180056590  test    rcx, rcx
0x180056593  jz      short loc_1800565A1
0x180056595  call    cs:__imp_RegCloseKey
0x18005659c  nop     dword ptr [rax+rax+00h]
0x1800565a1  mov     eax, edi
0x1800565a3  jmp     short loc_18005660E
0x1800565a5  lea     rcx, [rsp+108h+lpSubKey]; this
0x1800565ad  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1800565b2  nop
0x1800565b3  mov     [rsp+108h+var_70], 0
0x1800565bb  lea     rcx, [rsp+108h+var_98]
0x1800565c0  call    ??R_lambda_1_@?1??SetQword@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1_KK@Z@QEBA@XZ; `Microsoft::Diagnostics::Utils::Registry::SetQword(HKEY__ *,std::wstring_view,std::wstring_view,unsigned __int64,ulong)'::`2'::_lambda_1_::operator()(void)
0x1800565c5  nop
0x1800565c6  mov     rcx, [rsp+108h+hKey]; hKey
0x1800565cb  test    rcx, rcx
0x1800565ce  jz      short loc_1800565DC
0x1800565d0  call    cs:__imp_RegCloseKey
0x1800565d7  nop     dword ptr [rax+rax+00h]
0x1800565dc  xor     eax, eax
0x1800565de  jmp     short loc_18005660E
0x1800565e0  cmp     [rsp+108h+var_70], 0
0x1800565e8  jz      short loc_1800565FD
0x1800565ea  mov     [rsp+108h+var_70], 0
0x1800565f2  lea     rcx, [rsp+108h+var_98]
0x1800565f7  call    ??R_lambda_1_@?1??SetQword@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1_KK@Z@QEBA@XZ; `Microsoft::Diagnostics::Utils::Registry::SetQword(HKEY__ *,std::wstring_view,std::wstring_view,unsigned __int64,ulong)'::`2'::_lambda_1_::operator()(void)
0x1800565fc  nop
0x1800565fd  lea     rcx, [rsp+108h+hKey]
0x180056602  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180056607  mov     eax, dword ptr [rsp+108h+lpValueName]
0x18005660e  mov     rcx, [rsp+108h+var_28]
0x180056616  xor     rcx, rsp; StackCookie
0x180056619  call    __security_check_cookie
0x18005661e  add     rsp, 0F8h
0x180056625  pop     rdi
0x180056626  pop     rsi
0x180056627  retn
```
