# Microsoft::Diagnostics::Utils::Registry::SetMultiSz(HKEY__ *,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const &,ulong)

- ea: `0x1801989b0`
- end: `0x180198fdb`
- name: `?SetMultiSz@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1AEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@7@K@Z`
- size: `1579`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180197fdc`

## callees

- `0x18001d160`
- `0x180024ee0`
- `0x180026ecc`
- `0x180027e64`
- `0x180035698`
- `0x18005af1c`
- `0x180098d5c`
- `0x1800b83bc`
- `0x18012de40`
- `0x18012eb08`
- `0x18018a008`
- `0x18018d598`
- `0x1801989b0`
- `0x1801990ec`
- `0x18019a800`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180198aeb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180198aeb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180198b54`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180198b54`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180198ebf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180198ebf`

## string_xrefs

- `0x180198a7f`: `onecore\base\telemetry\utc\include\RegistryUtils.h`
- `0x180198b82`: `onecore\base\telemetry\utc\include\RegistryUtils.h`
- `0x180198d39`: `onecore\base\telemetry\utc\include\RegistryUtils.h`
- `0x180198da5`: `onecore\base\telemetry\utc\include\RegistryUtils.h`
- `0x180198e24`: `onecore\base\telemetry\utc\include\RegistryUtils.h`
- `0x180198efb`: `onecore\base\telemetry\utc\include\RegistryUtils.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Microsoft::Diagnostics::Utils::Registry::SetMultiSz(HKEY a1, __int64 a2, _QWORD *a3, __int64 *a4)
{
  HKEY v7; // r12
  const char *v8; // r9
  __int64 result; // rax
  const WCHAR *v10; // rdx
  LSTATUS v11; // eax
  unsigned int v12; // ebx
  __int64 v13; // rcx
  char *v14; // rsi
  unsigned __int64 v15; // rcx
  BYTE *v16; // rax
  size_t v17; // rbx
  unsigned __int64 v18; // rbx
  wchar_t *v19; // rcx
  BYTE *v20; // rsi
  unsigned __int64 v21; // rdx
  size_t v22; // rbx
  unsigned __int64 v23; // rsi
  __int64 v24; // rbx
  __int64 v25; // r15
  const wchar_t *v26; // r8
  int v27; // eax
  unsigned int v28; // esi
  BYTE *v29; // rsi
  signed __int64 v30; // rbx
  __int64 v31; // rax
  int v32; // eax
  unsigned int v33; // ebx
  int dwOptions; // [rsp+20h] [rbp-128h]
  int dwOptionsa; // [rsp+20h] [rbp-128h]
  REGSAM samDesired; // [rsp+28h] [rbp-120h]
  HKEY hKey; // [rsp+50h] [rbp-F8h] BYREF
  char *v38; // [rsp+58h] [rbp-F0h] BYREF
  BYTE *lpData; // [rsp+60h] [rbp-E8h] BYREF
  void *v40; // [rsp+68h] [rbp-E0h]
  __int64 v41; // [rsp+70h] [rbp-D8h]
  unsigned __int64 v42; // [rsp+78h] [rbp-D0h] BYREF
  int v43; // [rsp+80h] [rbp-C8h] BYREF
  HKEY v44; // [rsp+88h] [rbp-C0h] BYREF
  _QWORD v45[5]; // [rsp+90h] [rbp-B8h] BYREF
  char v46; // [rsp+B8h] [rbp-90h]
  LPCWSTR lpSubKey[4]; // [rsp+C0h] [rbp-88h] BYREF
  wchar_t *v48[4]; // [rsp+E0h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+0h]

  try
  {
    v44 = a1;
    LODWORD(v38) = 0;
    hKey = 0;
    v43 = (a4[1] - *a4) >> 5;
    v45[0] = &v44;
    v45[1] = a2;
    v45[2] = a3;
    v45[3] = &v43;
    v45[4] = &v38;
    v46 = 1;
    *(_OWORD *)v48 = *(_OWORD *)a2;
    Microsoft::Diagnostics::Utils::Registry::TryExpandKeyName((LPCWSTR)lpSubKey);
    if ( *(_QWORD *)(a2 + 8) )
    {
      hKey = 0;
      v10 = (const WCHAR *)lpSubKey;
      if ( lpSubKey[3] > (LPCWSTR)7 )
        v10 = lpSubKey[0];
      v11 = RegCreateKeyExW(v44, v10, 0, 0, 0, 2u, 0, &hKey, 0);
      v12 = v11;
      if ( v11 > 0 )
        v12 = (unsigned __int16)v11 | 0x80070000;
      LODWORD(v38) = v12;
      if ( (v12 & 0x80000000) != 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x22F,
          (unsigned int)"onecore\\base\\telemetry\\utc\\include\\RegistryUtils.h",
          (const char *)v12,
          dwOptions);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpSubKey);
        v46 = 0;
        `Microsoft::Diagnostics::Utils::Registry::SetMultiSz'::`2'::_lambda_1_::operator()(v45);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        return v12;
      }
      v7 = hKey;
    }
    else
    {
      v7 = v44;
      if ( !v44 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x235,
          (unsigned int)"onecore\\base\\telemetry\\utc\\include\\RegistryUtils.h",
          (const char *)0x80070057LL,
          dwOptions);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpSubKey);
        v46 = 0;
        `Microsoft::Diagnostics::Utils::Registry::SetMultiSz'::`2'::_lambda_1_::operator()(v45);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        return 2147942487LL;
      }
    }
    std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioStateMapEntry>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioStateMapEntry>>>>>>(&lpData);
    v13 = *a4;
    if ( *a4 == a4[1] )
    {
      v14 = (char *)v40;
      v15 = ((_BYTE *)v40 - lpData) >> 1;
      if ( v15 > 2 )
      {
        v16 = lpData + 4;
LABEL_19:
        v40 = v16;
        goto LABEL_20;
      }
      if ( v15 < 2 )
      {
        if ( (unsigned __int64)((v41 - (__int64)lpData) >> 1) >= 2 )
        {
          v17 = 2 * (2 - v15);
          memset_0(v40, 0, v17);
          v16 = (BYTE *)&v14[v17];
          goto LABEL_19;
        }
        std::vector<wchar_t>::_Resize_reallocate<std::_Value_init_tag>(&lpData, 2);
      }
LABEL_20:
      *(_WORD *)lpData = 0;
      *((_WORD *)lpData + 1) = 0;
LABEL_43:
      v29 = lpData;
      v30 = ((_BYTE *)v40 - lpData) >> 1;
      v31 = std::wstring::wstring((__int64)v48, a3);
      if ( *(_QWORD *)(v31 + 24) > 7u )
        v31 = *(_QWORD *)v31;
      v32 = RegSetValueExW(v7, (LPCWSTR)v31, 0, 7u, v29, 2 * v30);
      if ( v32 > 0 )
        v32 = (unsigned __int16)v32 | 0x80070000;
      LODWORD(v38) = v32;
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v48);
      v33 = (unsigned int)v38;
      if ( (int)v38 >= 0 )
      {
        std::vector<wchar_t>::_Tidy(&lpData);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpSubKey);
        v46 = 0;
        `Microsoft::Diagnostics::Utils::Registry::SetMultiSz'::`2'::_lambda_1_::operator()(v45);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        return 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x263,
          (unsigned int)"onecore\\base\\telemetry\\utc\\include\\RegistryUtils.h",
          (const char *)(unsigned int)v38,
          dwOptionsa);
        std::vector<wchar_t>::_Tidy(&lpData);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpSubKey);
        v46 = 0;
        `Microsoft::Diagnostics::Utils::Registry::SetMultiSz'::`2'::_lambda_1_::operator()(v45);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        return v33;
      }
    }
    v18 = 1;
    do
    {
      v18 += *(_QWORD *)(v13 + 16) + 1LL;
      v13 += 32;
    }
    while ( v13 != a4[1] );
    v19 = (wchar_t *)lpData;
    v20 = (BYTE *)v40;
    v21 = ((_BYTE *)v40 - lpData) >> 1;
    if ( v18 >= v21 )
    {
      if ( v18 <= v21 )
        goto LABEL_30;
      if ( v18 > (v41 - (__int64)lpData) >> 1 )
      {
        std::vector<wchar_t>::_Resize_reallocate<std::_Value_init_tag>(&lpData, v18);
        v20 = (BYTE *)v40;
        v19 = (wchar_t *)lpData;
        goto LABEL_30;
      }
      v22 = 2 * (v18 - v21);
      memset_0(v40, 0, v22);
      v20 += v22;
      v19 = (wchar_t *)lpData;
    }
    else
    {
      v20 = &lpData[2 * v18];
    }
    v40 = v20;
LABEL_30:
    v23 = (v20 - (BYTE *)v19) >> 1;
    v24 = *a4;
    v25 = a4[1];
    while ( 1 )
    {
      v42 = v23;
      v48[0] = v19;
      if ( v24 == v25 )
        break;
      if ( *(_QWORD *)(v24 + 24) <= 7u )
        v26 = (const wchar_t *)v24;
      else
        v26 = *(const wchar_t **)v24;
      v27 = StringCchCopyExW(v19, v23, v26, v48, &v42, samDesired);
      v28 = v27;
      if ( v27 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x251,
          (unsigned int)"onecore\\base\\telemetry\\utc\\include\\RegistryUtils.h",
          (const char *)(unsigned int)v27,
          dwOptions);
        std::vector<wchar_t>::_Tidy(&lpData);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpSubKey);
        v46 = 0;
        `Microsoft::Diagnostics::Utils::Registry::SetMultiSz'::`2'::_lambda_1_::operator()(v45);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        return v28;
      }
      if ( !v42 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x253,
          (unsigned int)"onecore\\base\\telemetry\\utc\\include\\RegistryUtils.h",
          (const char *)0x80004005LL,
          dwOptions);
        std::vector<wchar_t>::_Tidy(&lpData);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpSubKey);
        v46 = 0;
        `Microsoft::Diagnostics::Utils::Registry::SetMultiSz'::`2'::_lambda_1_::operator()(v45);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        return 2147500037LL;
      }
      v23 = v42 - 1;
      v19 = v48[0] + 1;
      v24 += 32;
    }
    if ( v23 != 1 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x259,
        (unsigned int)"onecore\\base\\telemetry\\utc\\include\\RegistryUtils.h",
        (const char *)0x80004005LL,
        dwOptions);
      std::vector<wchar_t>::_Tidy(&lpData);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpSubKey);
      v46 = 0;
      `Microsoft::Diagnostics::Utils::Registry::SetMultiSz'::`2'::_lambda_1_::operator()(v45);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      return 2147500037LL;
    }
    *v19 = 0;
    goto LABEL_43;
  }
  catch ( ... )
  {
    LODWORD(v42) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0x267,
                     (unsigned int)"onecore\\base\\telemetry\\utc\\include\\RegistryUtils.h",
                     v8);
    if ( v46 )
    {
      v46 = 0;
      `Microsoft::Diagnostics::Utils::Registry::SetMultiSz'::`2'::_lambda_1_::operator()(v45);
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return (unsigned int)v42;
  }
  return result;
}

```

## disassembly

```asm
0x1801989b0  mov     r11, rsp
0x1801989b3  push    rbx
0x1801989b4  push    rsi
0x1801989b5  push    rdi
0x1801989b6  push    r12
0x1801989b8  push    r13
0x1801989ba  push    r14
0x1801989bc  push    r15
0x1801989be  sub     rsp, 110h
0x1801989c5  mov     rax, cs:__security_cookie
0x1801989cc  xor     rax, rsp
0x1801989cf  mov     [rsp+148h+var_48], rax
0x1801989d7  mov     r15, r9
0x1801989da  mov     r13, r8
0x1801989dd  mov     rbx, rdx
0x1801989e0  mov     [r11-0C0h], rcx
0x1801989e7  xor     edi, edi
0x1801989e9  mov     dword ptr [rsp+148h+var_F0], edi
0x1801989ed  mov     [rsp+148h+hKey], rdi
0x1801989f2  mov     rax, [r9+8]
0x1801989f6  sub     rax, [r9]
0x1801989f9  sar     rax, 5
0x1801989fd  mov     [rsp+148h+var_C8], eax
0x180198a04  lea     rax, [r11-0C0h]
0x180198a0b  mov     [r11-0B8h], rax
0x180198a12  mov     [r11-0B0h], rdx
0x180198a19  mov     [r11-0A8h], r8
0x180198a20  lea     rax, [r11-0C8h]
0x180198a27  mov     [r11-0A0h], rax
0x180198a2e  lea     rax, [rsp+148h+var_F0]
0x180198a33  mov     [r11-98h], rax
0x180198a3a  mov     [rsp+148h+var_90], 1
0x180198a42  movups  xmm0, xmmword ptr [rdx]
0x180198a45  movdqu  xmmword ptr [r11-68h], xmm0
0x180198a4b  lea     rdx, [r11-68h]
0x180198a4f  lea     rcx, [r11-88h]
0x180198a56  call    ?TryExpandKeyName@Registry@Utils@Diagnostics@Microsoft@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@6@@Z; Microsoft::Diagnostics::Utils::Registry::TryExpandKeyName(std::wstring_view)
0x180198a5b  nop
0x180198a5c  cmp     [rbx+8], rdi
0x180198a60  jnz     short loc_180198AD1
0x180198a62  mov     r12, [rsp+148h+var_C0]
0x180198a6a  test    r12, r12
0x180198a6d  jnz     short loc_180198AC6
0x180198a6f  mov     rcx, [rsp+148h]; this
0x180198a77  mov     ebx, 80070057h
0x180198a7c  mov     r9d, ebx; char *
0x180198a7f  lea     r8, aOnecoreBaseTel_200; "onecore\\base\\telemetry\\utc\\include"...
0x180198a86  mov     edx, 235h; void *
0x180198a8b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180198a90  nop
0x180198a91  lea     rcx, [rsp+148h+lpSubKey]; this
0x180198a99  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x180198a9e  nop
0x180198a9f  mov     [rsp+148h+var_90], dil
0x180198aa7  lea     rcx, [rsp+148h+var_B8]
0x180198aaf  call    ??R_lambda_1_@?1??SetMultiSz@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1AEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@8@K@Z@QEBA@XZ; `Microsoft::Diagnostics::Utils::Registry::SetMultiSz(HKEY__ *,std::wstring_view,std::wstring_view,std::vector<std::wstring> const &,ulong)'::`2'::_lambda_1_::operator()(void)
0x180198ab4  nop
0x180198ab5  lea     rcx, [rsp+148h+hKey]
0x180198aba  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180198abf  mov     eax, ebx
0x180198ac1  jmp     loc_180198FB7
0x180198ac6  mov     r14d, 2
0x180198acc  jmp     loc_180198BCE
0x180198ad1  mov     rbx, [rsp+148h+hKey]
0x180198ad6  test    rbx, rbx
0x180198ad9  jz      short loc_180198B04
0x180198adb  lea     rcx, [rsp+148h+var_68]; this
0x180198ae3  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180198ae8  mov     rcx, rbx; hKey
0x180198aeb  call    cs:__imp_RegCloseKey
0x180198af2  nop     dword ptr [rax+rax+00h]
0x180198af7  lea     rcx, [rsp+148h+var_68]; this
0x180198aff  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180198b04  mov     [rsp+148h+hKey], rdi
0x180198b09  lea     rdx, [rsp+148h+lpSubKey]
0x180198b11  cmp     [rsp+148h+var_70], 7
0x180198b1a  cmova   rdx, [rsp+148h+lpSubKey]; lpSubKey
0x180198b23  mov     [rsp+148h+lpdwDisposition], rdi; lpdwDisposition
0x180198b28  lea     rax, [rsp+148h+hKey]
0x180198b2d  mov     [rsp+148h+phkResult], rax; phkResult
0x180198b32  mov     [rsp+148h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180198b37  mov     r14d, 2
0x180198b3d  mov     [rsp+148h+samDesired], r14d; unsigned int
0x180198b42  mov     [rsp+148h+dwOptions], edi; int
0x180198b46  xor     r9d, r9d; lpClass
0x180198b49  xor     r8d, r8d; Reserved
0x180198b4c  mov     rcx, [rsp+148h+var_C0]; hKey
0x180198b54  call    cs:__imp_RegCreateKeyExW
0x180198b5b  nop     dword ptr [rax+rax+00h]
0x180198b60  mov     ebx, eax
0x180198b62  test    eax, eax
0x180198b64  jle     short loc_180198B6F
0x180198b66  movzx   ebx, ax
0x180198b69  or      ebx, 80070000h
0x180198b6f  mov     dword ptr [rsp+148h+var_F0], ebx
0x180198b73  test    ebx, ebx
0x180198b75  jns     short loc_180198BC9
0x180198b77  mov     rcx, [rsp+148h]; this
0x180198b7f  mov     r9d, ebx; char *
0x180198b82  lea     r8, aOnecoreBaseTel_200; "onecore\\base\\telemetry\\utc\\include"...
0x180198b89  mov     edx, 22Fh; void *
0x180198b8e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180198b93  nop
0x180198b94  lea     rcx, [rsp+148h+lpSubKey]; this
0x180198b9c  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x180198ba1  nop
0x180198ba2  mov     [rsp+148h+var_90], dil
0x180198baa  lea     rcx, [rsp+148h+var_B8]
0x180198bb2  call    ??R_lambda_1_@?1??SetMultiSz@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1AEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@8@K@Z@QEBA@XZ; `Microsoft::Diagnostics::Utils::Registry::SetMultiSz(HKEY__ *,std::wstring_view,std::wstring_view,std::vector<std::wstring> const &,ulong)'::`2'::_lambda_1_::operator()(void)
0x180198bb7  nop
0x180198bb8  lea     rcx, [rsp+148h+hKey]
0x180198bbd  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180198bc2  mov     eax, ebx
0x180198bc4  jmp     loc_180198FB7
0x180198bc9  mov     r12, [rsp+148h+hKey]
0x180198bce  lea     rcx, [rsp+148h+lpData]; void *
0x180198bd3  call    ??$?0AEBV?$allocator@U?$pair@$$CBU_GUID@@UScenarioStateMapEntry@Diagnostics@Microsoft@@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@UScenarioStateMapEntry@Diagnostics@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBU_GUID@@UScenarioStateMapEntry@Diagnostics@Microsoft@@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioStateMapEntry>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioStateMapEntry>>>>>>(std::allocator<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioStateMapEntry>> const &)
0x180198bd8  nop
0x180198bd9  mov     rcx, [r15]
0x180198bdc  cmp     rcx, [r15+8]
0x180198be0  jnz     short loc_180198C57
0x180198be2  mov     rdx, [rsp+148h+lpData]
0x180198be7  mov     rsi, [rsp+148h+var_E0]
0x180198bec  mov     rcx, rsi
0x180198bef  sub     rcx, rdx
0x180198bf2  sar     rcx, 1
0x180198bf5  cmp     rcx, r14
0x180198bf8  jbe     short loc_180198C00
0x180198bfa  lea     rax, [rdx+4]
0x180198bfe  jmp     short loc_180198C3C
0x180198c00  jnb     short loc_180198C41
0x180198c02  mov     rax, [rsp+148h+var_D8]
0x180198c07  sub     rax, rdx
0x180198c0a  sar     rax, 1
0x180198c0d  cmp     rax, r14
0x180198c10  jnb     short loc_180198C21
0x180198c12  mov     rdx, r14
0x180198c15  lea     rcx, [rsp+148h+lpData]
0x180198c1a  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@_WV?$allocator@_W@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<wchar_t>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180198c1f  jmp     short loc_180198C41
0x180198c21  mov     rax, r14
0x180198c24  sub     rax, rcx
0x180198c27  lea     rbx, [rax+rax]
0x180198c2b  mov     r8, rbx; Size
0x180198c2e  xor     edx, edx; Val
0x180198c30  mov     rcx, rsi; void *
0x180198c33  call    memset_0
0x180198c38  lea     rax, [rbx+rsi]
0x180198c3c  mov     [rsp+148h+var_E0], rax
0x180198c41  mov     rax, [rsp+148h+lpData]
0x180198c46  mov     [rax], di
0x180198c49  mov     rax, [rsp+148h+lpData]
0x180198c4e  mov     [rax+2], di
0x180198c52  jmp     loc_180198E79
0x180198c57  mov     ebx, 1
0x180198c5c  inc     rbx
0x180198c5f  add     rbx, [rcx+10h]
0x180198c63  add     rcx, 20h ; ' '
0x180198c67  cmp     rcx, [r15+8]
0x180198c6b  jnz     short loc_180198C5C
0x180198c6d  mov     rcx, [rsp+148h+lpData]
0x180198c72  mov     rsi, [rsp+148h+var_E0]
0x180198c77  mov     rdx, rsi
0x180198c7a  sub     rdx, rcx
0x180198c7d  sar     rdx, 1
0x180198c80  cmp     rbx, rdx
0x180198c83  jnb     short loc_180198C8B
0x180198c85  lea     rsi, [rcx+rbx*2]
0x180198c89  jmp     short loc_180198CD1
0x180198c8b  jbe     short loc_180198CD6
0x180198c8d  mov     rax, [rsp+148h+var_D8]
0x180198c92  sub     rax, rcx
0x180198c95  sar     rax, 1
0x180198c98  cmp     rbx, rax
0x180198c9b  jbe     short loc_180198CB6
0x180198c9d  mov     rdx, rbx
0x180198ca0  lea     rcx, [rsp+148h+lpData]
0x180198ca5  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@_WV?$allocator@_W@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<wchar_t>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180198caa  mov     rsi, [rsp+148h+var_E0]
0x180198caf  mov     rcx, [rsp+148h+lpData]
0x180198cb4  jmp     short loc_180198CD6
0x180198cb6  sub     rbx, rdx
0x180198cb9  add     rbx, rbx
0x180198cbc  mov     r8, rbx; Size
0x180198cbf  xor     edx, edx; Val
0x180198cc1  mov     rcx, rsi; void *
0x180198cc4  call    memset_0
0x180198cc9  add     rsi, rbx
0x180198ccc  mov     rcx, [rsp+148h+lpData]
0x180198cd1  mov     [rsp+148h+var_E0], rsi
0x180198cd6  sub     rsi, rcx
0x180198cd9  sar     rsi, 1
0x180198cdc  mov     rbx, [r15]
0x180198cdf  mov     r15, [r15+8]
0x180198ce3  mov     rax, rcx
0x180198ce6  mov     [rsp+148h+var_D0], rsi
0x180198ceb  mov     [rsp+148h+var_68], rcx
0x180198cf3  cmp     rbx, r15
0x180198cf6  jz      loc_180198E0E
0x180198cfc  cmp     qword ptr [rbx+18h], 7
0x180198d01  jbe     short loc_180198D08
0x180198d03  mov     r8, [rbx]
0x180198d06  jmp     short loc_180198D0B
0x180198d08  mov     r8, rbx; wchar_t *
0x180198d0b  lea     rcx, [rsp+148h+var_D0]
0x180198d10  mov     qword ptr [rsp+148h+dwOptions], rcx; int
0x180198d15  lea     r9, [rsp+148h+var_68]; wchar_t **
0x180198d1d  mov     rdx, rsi; unsigned __int64
0x180198d20  mov     rcx, rax; wchar_t *
0x180198d23  call    ?StringCchCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x180198d28  mov     esi, eax
0x180198d2a  test    eax, eax
0x180198d2c  jns     short loc_180198D8B
0x180198d2e  mov     rcx, [rsp+148h]; this
0x180198d36  mov     r9d, eax; char *
0x180198d39  lea     r8, aOnecoreBaseTel_200; "onecore\\base\\telemetry\\utc\\include"...
0x180198d40  mov     edx, 251h; void *
0x180198d45  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180198d4a  nop
0x180198d4b  lea     rcx, [rsp+148h+lpData]
0x180198d50  call    ?_Tidy@?$vector@_WV?$allocator@_W@std@@@std@@AEAAXXZ; std::vector<wchar_t>::_Tidy(void)
0x180198d55  nop
0x180198d56  lea     rcx, [rsp+148h+lpSubKey]; this
0x180198d5e  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x180198d63  nop
0x180198d64  mov     [rsp+148h+var_90], dil
0x180198d6c  lea     rcx, [rsp+148h+var_B8]
0x180198d74  call    ??R_lambda_1_@?1??SetMultiSz@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1AEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@8@K@Z@QEBA@XZ; `Microsoft::Diagnostics::Utils::Registry::SetMultiSz(HKEY__ *,std::wstring_view,std::wstring_view,std::vector<std::wstring> const &,ulong)'::`2'::_lambda_1_::operator()(void)
0x180198d79  nop
0x180198d7a  lea     rcx, [rsp+148h+hKey]
0x180198d7f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180198d84  mov     eax, esi
0x180198d86  jmp     loc_180198FB7
0x180198d8b  mov     rsi, [rsp+148h+var_D0]
0x180198d90  test    rsi, rsi
0x180198d93  jnz     short loc_180198DF7
0x180198d95  mov     rcx, [rsp+148h]; this
0x180198d9d  mov     ebx, 80004005h
0x180198da2  mov     r9d, ebx; char *
0x180198da5  lea     r8, aOnecoreBaseTel_200; "onecore\\base\\telemetry\\utc\\include"...
0x180198dac  mov     edx, 253h; void *
0x180198db1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180198db6  nop
0x180198db7  lea     rcx, [rsp+148h+lpData]
0x180198dbc  call    ?_Tidy@?$vector@_WV?$allocator@_W@std@@@std@@AEAAXXZ; std::vector<wchar_t>::_Tidy(void)
0x180198dc1  nop
0x180198dc2  lea     rcx, [rsp+148h+lpSubKey]; this
0x180198dca  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x180198dcf  nop
0x180198dd0  mov     [rsp+148h+var_90], dil
0x180198dd8  lea     rcx, [rsp+148h+var_B8]
0x180198de0  call    ??R_lambda_1_@?1??SetMultiSz@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1AEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@8@K@Z@QEBA@XZ; `Microsoft::Diagnostics::Utils::Registry::SetMultiSz(HKEY__ *,std::wstring_view,std::wstring_view,std::vector<std::wstring> const &,ulong)'::`2'::_lambda_1_::operator()(void)
0x180198de5  nop
0x180198de6  lea     rcx, [rsp+148h+hKey]
0x180198deb  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180198df0  mov     eax, ebx
0x180198df2  jmp     loc_180198FB7
0x180198df7  dec     rsi
0x180198dfa  mov     rcx, [rsp+148h+var_68]
0x180198e02  add     rcx, r14
0x180198e05  add     rbx, 20h ; ' '
0x180198e09  jmp     loc_180198CE3
0x180198e0e  cmp     rsi, 1
0x180198e12  jz      short loc_180198E76
0x180198e14  mov     rcx, [rsp+148h]; this
0x180198e1c  mov     ebx, 80004005h
0x180198e21  mov     r9d, ebx; char *
0x180198e24  lea     r8, aOnecoreBaseTel_200; "onecore\\base\\telemetry\\utc\\include"...
0x180198e2b  mov     edx, 259h; void *
0x180198e30  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180198e35  nop
0x180198e36  lea     rcx, [rsp+148h+lpData]
0x180198e3b  call    ?_Tidy@?$vector@_WV?$allocator@_W@std@@@std@@AEAAXXZ; std::vector<wchar_t>::_Tidy(void)
0x180198e40  nop
0x180198e41  lea     rcx, [rsp+148h+lpSubKey]; this
0x180198e49  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x180198e4e  nop
0x180198e4f  mov     [rsp+148h+var_90], dil
0x180198e57  lea     rcx, [rsp+148h+var_B8]
0x180198e5f  call    ??R_lambda_1_@?1??SetMultiSz@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1AEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@8@K@Z@QEBA@XZ; `Microsoft::Diagnostics::Utils::Registry::SetMultiSz(HKEY__ *,std::wstring_view,std::wstring_view,std::vector<std::wstring> const &,ulong)'::`2'::_lambda_1_::operator()(void)
0x180198e64  nop
0x180198e65  lea     rcx, [rsp+148h+hKey]
0x180198e6a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180198e6f  mov     eax, ebx
0x180198e71  jmp     loc_180198FB7
0x180198e76  mov     [rcx], di
0x180198e79  mov     rsi, [rsp+148h+lpData]
0x180198e7e  mov     rbx, [rsp+148h+var_E0]
0x180198e83  sub     rbx, rsi
0x180198e86  sar     rbx, 1
0x180198e89  mov     rdx, r13
0x180198e8c  lea     rcx, [rsp+148h+var_68]
0x180198e94  call    ??$?0V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_zstring_view@_W@wil@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wil::basic_zstring_view<wchar_t> const &,std::allocator<wchar_t> const &)
0x180198e99  cmp     qword ptr [rax+18h], 7
0x180198e9e  jbe     short loc_180198EA3
0x180198ea0  mov     rax, [rax]
0x180198ea3  imul    ebx, r14d
0x180198ea7  mov     [rsp+148h+samDesired], ebx; cbData
0x180198eab  mov     qword ptr [rsp+148h+dwOptions], rsi; int
0x180198eb0  mov     r9d, 7; dwType
  ... truncated ...
```
