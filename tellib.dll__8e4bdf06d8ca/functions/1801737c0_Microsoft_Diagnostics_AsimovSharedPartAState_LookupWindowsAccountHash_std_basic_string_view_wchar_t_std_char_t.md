# Microsoft::Diagnostics::AsimovSharedPartAState::LookupWindowsAccountHash(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>)

- ea: `0x1801737c0`
- end: `0x180173cdc`
- name: `?LookupWindowsAccountHash@AsimovSharedPartAState@Diagnostics@Microsoft@@QEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@5@@Z`
- size: `1308`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180173050`

## callees

- `0x180001d28`
- `0x1800035ec`
- `0x180003c74`
- `0x180003f58`
- `0x18001d160`
- `0x180020fbc`
- `0x180027be0`
- `0x180030a50`
- `0x180035698`
- `0x1800495cc`
- `0x18005d050`
- `0x180080054`
- `0x1800edba8`
- `0x18012de40`
- `0x1801732cc`
- `0x180173794`
- `0x1801737c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180173855`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801738e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180173999`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180173c80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180173855`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801738e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180173999`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180173c80`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180173812`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180173812`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1801738cd`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180173965`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1801738cd`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180173965`
- `api-ms-win-security-lsalookup-l1-1-2!LsaLookupUserAccountType` at `0x180173a26`
- `api-ms-win-security-lsalookup-l1-1-2!LsaLookupUserAccountType` at `0x180173a26`
- `logoncli!DsGetDcNameW` at `0x180173a85`
- `logoncli!DsGetDcNameW` at `0x180173a85`

## string_xrefs

- `0x180173c93`: `onecore\base\telemetry\utc\service\asimov\asimovsharedpartastate.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
struct _DOMAIN_CONTROLLER_INFOW *__fastcall Microsoft::Diagnostics::AsimovSharedPartAState::LookupWindowsAccountHash(
        __int64 a1,
        struct _DOMAIN_CONTROLLER_INFOW *a2,
        _QWORD *a3)
{
  __int64 v5; // rax
  BOOL v6; // ebx
  signed int LastError; // eax
  int v8; // r8d
  int v9; // r9d
  WCHAR *v10; // rax
  WCHAR *v11; // r8
  signed int v12; // eax
  int v13; // r8d
  int v14; // r9d
  char v15; // bl
  const WCHAR *v16; // rdx
  int v17; // r8d
  LPWSTR *v18; // rdx
  __int64 v19; // rax
  int v20; // r8d
  int v21; // r9d
  __int128 *v22; // r9
  __int128 *v23; // r8
  LPWSTR DomainName; // rdx
  __int64 v25; // r8
  LPWSTR *v26; // rdx
  LPWSTR *v27; // rdx
  __int64 v28; // rax
  int v29; // r8d
  __int64 v30; // r9
  int v31; // r8d
  int v32; // r9d
  DWORD v33; // eax
  unsigned int ReferencedDomainName; // [rsp+20h] [rbp-E0h]
  int ReferencedDomainNamea; // [rsp+20h] [rbp-E0h]
  int v37; // [rsp+40h] [rbp-C0h] BYREF
  char v38[4]; // [rsp+44h] [rbp-BCh] BYREF
  DWORD cchName; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cchReferencedDomainName; // [rsp+4Ch] [rbp-B4h] BYREF
  PSID Sid; // [rsp+50h] [rbp-B0h] BYREF
  int v42; // [rsp+58h] [rbp-A8h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+5Ch] [rbp-A4h] BYREF
  PDOMAIN_CONTROLLER_INFOW DomainControllerInfo; // [rsp+60h] [rbp-A0h] BYREF
  _OWORD v45[2]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v46; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v47[16]; // [rsp+A0h] [rbp-60h] BYREF
  LPWSTR v48[2]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int v49; // [rsp+C0h] [rbp-40h]
  unsigned __int64 v50; // [rsp+C8h] [rbp-38h]
  LPWSTR Name[2]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned int v52; // [rsp+E0h] [rbp-20h]
  unsigned __int64 v53; // [rsp+E8h] [rbp-18h]
  _BYTE v54[32]; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  DomainControllerInfo = a2;
  Sid = 0;
  v5 = std::wstring::wstring((__int64)v54, a3);
  if ( *(_QWORD *)(v5 + 24) > 7u )
    v5 = *(_QWORD *)v5;
  v6 = ConvertStringSidToSidW((LPCWSTR)v5, &Sid);
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v54);
  if ( !v6 )
  {
    if ( (unsigned int)dword_18042D328 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 0x4000000) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v37 = LastError;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (unsigned int)&dword_18042D328,
        (unsigned int)&unk_1803C116F,
        v8,
        v9,
        (__int64)&v37);
    }
    goto LABEL_51;
  }
  cchName = 0;
  cchReferencedDomainName = 0;
  peUse = SidTypeUnknown;
  if ( LookupAccountSidW(0, Sid, 0, &cchName, 0, &cchReferencedDomainName, &peUse) || GetLastError() != 122 )
  {
    v33 = GetLastError();
    wil::details::in1diag3::Log_Win32(
      retaddr,
      (void *)0x206,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\asimov\\asimovsharedpartastate.cpp",
      (const char *)v33,
      ReferencedDomainName);
LABEL_51:
    std::wstring::wstring(a2, &unk_18043B390);
    goto LABEL_52;
  }
  std::wstring::wstring(Name);
  std::wstring::wstring(v48);
  std::wstring::resize(Name, cchName);
  std::wstring::resize(v48, cchReferencedDomainName);
  v10 = (WCHAR *)v48;
  if ( v50 > 7 )
    v10 = v48[0];
  v11 = (WCHAR *)Name;
  if ( v53 > 7 )
    v11 = Name[0];
  if ( !LookupAccountSidW(0, Sid, v11, &cchName, v10, &cchReferencedDomainName, &peUse) )
  {
    if ( (unsigned int)dword_18042D328 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 0x4000000) )
    {
      v12 = GetLastError();
      if ( v12 > 0 )
        v12 = (unsigned __int16)v12 | 0x80070000;
      v37 = v12;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (unsigned int)&dword_18042D328,
        (unsigned int)&unk_1803C111A,
        v13,
        v14,
        (__int64)&v37);
    }
    std::wstring::wstring(a2, &unk_18043B390);
    goto LABEL_22;
  }
  std::wstring::resize(Name, cchName);
  std::wstring::resize(v48, cchReferencedDomainName);
  v42 = 0;
  v15 = 0;
  if ( (int)LsaLookupUserAccountType(Sid, &v42) < 0 )
  {
    if ( (unsigned int)dword_18042D328 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 0x4000000) )
    {
      v37 = v31 | 0x10000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (unsigned int)&dword_18042D328,
        (unsigned int)&unk_1803C1064,
        v31 | 0x10000000,
        v32,
        (__int64)&v37);
    }
  }
  else
  {
    if ( ((v42 - 2) & 0xFFFFFFFC) == 0 && v42 != 4 )
    {
      DomainControllerInfo = 0;
      v16 = (const WCHAR *)v48;
      if ( v50 > 7 )
        v16 = v48[0];
      if ( DsGetDcNameW(0, v16, 0, 0, 0x40000000u, &DomainControllerInfo) )
      {
        if ( (unsigned int)dword_18042D328 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 0x4000000) )
        {
          v37 = v17;
          v18 = v48;
          if ( v50 > 7 )
            v18 = (LPWSTR *)v48[0];
          v19 = _tlgWrapBinary<wchar_t,2>(v45, v18, v49);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperArray<1>,_tlgWrapperByVal<4>>(
            (unsigned int)&v37,
            (unsigned int)&unk_1803C10B9,
            v20,
            v21,
            v19,
            (__int64)&v37);
        }
        v46 = *(_OWORD *)std::wstring::operator std::wstring_view(Name, v47);
        v45[0] = *(_OWORD *)std::wstring::operator std::wstring_view(v48, v54);
        LOBYTE(ReferencedDomainNamea) = 0;
        v22 = &v46;
        v23 = v45;
        goto LABEL_35;
      }
      v15 = 1;
      DomainName = DomainControllerInfo->DomainName;
      v25 = -1;
      do
        ++v25;
      while ( DomainName[v25] );
      std::wstring::_Assign<wchar_t>((char **)v48, DomainName, (char *)v25);
    }
    if ( (unsigned int)dword_18042D328 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 0x4000000) )
    {
      v26 = Name;
      if ( v53 > 7 )
        v26 = (LPWSTR *)Name[0];
      _tlgWrapBinary<wchar_t,2>(v54, v26, v52);
      v27 = v48;
      if ( v50 > 7 )
        v27 = (LPWSTR *)v48[0];
      v28 = _tlgWrapBinary<wchar_t,2>(v47, v27, v49);
      v38[0] = v15;
      v37 = v42;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperArray<1>>(
        v42,
        (unsigned int)&unk_1803C0F84,
        v29,
        v30,
        (__int64)&v37,
        (__int64)v38,
        v28,
        v30);
    }
  }
  v45[0] = *(_OWORD *)std::wstring::operator std::wstring_view(Name, v54);
  v46 = *(_OWORD *)std::wstring::operator std::wstring_view(v48, v47);
  LOBYTE(ReferencedDomainNamea) = v15;
  v22 = v45;
  v23 = &v46;
LABEL_35:
  Microsoft::Diagnostics::AsimovSharedPartAState::HashWindowsAccount(a1, a2, v23, v22, ReferencedDomainNamea);
LABEL_22:
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v48);
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Name);
LABEL_52:
  wil::details::unique_storage<wil::details::resource_policy<_ACL *,void * (void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ACL *,void * (void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>(&Sid);
  return a2;
}

```

## disassembly

```asm
0x1801737c0  push    rbp
0x1801737c2  push    rbx
0x1801737c3  push    rsi
0x1801737c4  push    rdi
0x1801737c5  push    r14
0x1801737c7  lea     rbp, [rsp-20h]
0x1801737cc  sub     rsp, 120h
0x1801737d3  mov     rax, cs:__security_cookie
0x1801737da  xor     rax, rsp
0x1801737dd  mov     [rbp+40h+var_30], rax
0x1801737e1  mov     rdi, rdx
0x1801737e4  mov     rsi, rcx
0x1801737e7  mov     [rsp+140h+DomainControllerInfo], rdx
0x1801737ec  xor     r14d, r14d
0x1801737ef  mov     [rsp+140h+Sid], r14
0x1801737f4  mov     rdx, r8
0x1801737f7  lea     rcx, [rbp+40h+var_50]
0x1801737fb  call    ??$?0V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_zstring_view@_W@wil@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wil::basic_zstring_view<wchar_t> const &,std::allocator<wchar_t> const &)
0x180173800  cmp     qword ptr [rax+18h], 7
0x180173805  jbe     short loc_18017380A
0x180173807  mov     rax, [rax]
0x18017380a  lea     rdx, [rsp+140h+Sid]; Sid
0x18017380f  mov     rcx, rax; StringSid
0x180173812  call    cs:__imp_ConvertStringSidToSidW
0x180173819  nop     dword ptr [rax+rax+00h]
0x18017381e  mov     ebx, eax
0x180173820  lea     rcx, [rbp+40h+var_50]; this
0x180173824  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x180173829  test    ebx, ebx
0x18017382b  jnz     short loc_180173893
0x18017382d  mov     eax, cs:dword_18042D328
0x180173833  cmp     eax, 5
0x180173836  jbe     loc_180173CA4
0x18017383c  mov     edx, 4000000h
0x180173841  lea     rcx, dword_18042D328
0x180173848  call    _tlgKeywordOn
0x18017384d  test    al, al
0x18017384f  jz      loc_180173CA4
0x180173855  call    cs:__imp_GetLastError
0x18017385c  nop     dword ptr [rax+rax+00h]
0x180173861  test    eax, eax
0x180173863  jle     short loc_18017386D
0x180173865  movzx   eax, ax
0x180173868  or      eax, 80070000h
0x18017386d  mov     [rsp+140h+var_100], eax
0x180173871  lea     rax, [rsp+140h+var_100]
0x180173876  mov     [rsp+140h+ReferencedDomainName], rax
0x18017387b  lea     rdx, unk_1803C116F
0x180173882  lea     rcx, dword_18042D328
0x180173889  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18017388e  jmp     loc_180173CA4
0x180173893  mov     [rsp+140h+cchName], r14d
0x180173898  mov     [rsp+140h+var_F4], r14d
0x18017389d  mov     [rsp+140h+var_E4], 8
0x1801738a5  lea     rax, [rsp+140h+var_E4]
0x1801738aa  mov     [rsp+140h+peUse], rax; peUse
0x1801738af  lea     rax, [rsp+140h+var_F4]
0x1801738b4  mov     [rsp+140h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1801738b9  mov     [rsp+140h+ReferencedDomainName], r14; unsigned int
0x1801738be  lea     r9, [rsp+140h+cchName]; cchName
0x1801738c3  xor     r8d, r8d; Name
0x1801738c6  mov     rdx, [rsp+140h+Sid]; Sid
0x1801738cb  xor     ecx, ecx; lpSystemName
0x1801738cd  call    cs:__imp_LookupAccountSidW
0x1801738d4  nop     dword ptr [rax+rax+00h]
0x1801738d9  test    eax, eax
0x1801738db  jnz     loc_180173C80
0x1801738e1  call    cs:__imp_GetLastError
0x1801738e8  nop     dword ptr [rax+rax+00h]
0x1801738ed  cmp     eax, 7Ah ; 'z'
0x1801738f0  jnz     loc_180173C80
0x1801738f6  lea     rcx, [rbp+40h+Name]; void *
0x1801738fa  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1801738ff  nop
0x180173900  lea     rcx, [rbp+40h+var_90]; void *
0x180173904  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180173909  nop
0x18017390a  mov     edx, [rsp+140h+cchName]
0x18017390e  lea     rcx, [rbp+40h+Name]
0x180173912  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x180173917  mov     edx, [rsp+140h+var_F4]
0x18017391b  lea     rcx, [rbp+40h+var_90]
0x18017391f  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x180173924  lea     rax, [rbp+40h+var_90]
0x180173928  cmp     [rbp+40h+var_78], 7
0x18017392d  cmova   rax, [rbp+40h+var_90]
0x180173932  lea     r8, [rbp+40h+Name]
0x180173936  cmp     [rbp+40h+var_58], 7
0x18017393b  cmova   r8, [rbp+40h+Name]; Name
0x180173940  lea     rcx, [rsp+140h+var_E4]
0x180173945  mov     [rsp+140h+peUse], rcx; peUse
0x18017394a  lea     rcx, [rsp+140h+var_F4]
0x18017394f  mov     [rsp+140h+cchReferencedDomainName], rcx; cchReferencedDomainName
0x180173954  mov     [rsp+140h+ReferencedDomainName], rax; ReferencedDomainName
0x180173959  lea     r9, [rsp+140h+cchName]; cchName
0x18017395e  mov     rdx, [rsp+140h+Sid]; Sid
0x180173963  xor     ecx, ecx; lpSystemName
0x180173965  call    cs:__imp_LookupAccountSidW
0x18017396c  nop     dword ptr [rax+rax+00h]
0x180173971  test    eax, eax
0x180173973  jnz     loc_1801739FA
0x180173979  mov     eax, cs:dword_18042D328
0x18017397f  cmp     eax, 5
0x180173982  jbe     short loc_1801739D2
0x180173984  mov     edx, 4000000h
0x180173989  lea     rcx, dword_18042D328
0x180173990  call    _tlgKeywordOn
0x180173995  test    al, al
0x180173997  jz      short loc_1801739D2
0x180173999  call    cs:__imp_GetLastError
0x1801739a0  nop     dword ptr [rax+rax+00h]
0x1801739a5  test    eax, eax
0x1801739a7  jle     short loc_1801739B1
0x1801739a9  movzx   eax, ax
0x1801739ac  or      eax, 80070000h
0x1801739b1  mov     [rsp+140h+var_100], eax
0x1801739b5  lea     rax, [rsp+140h+var_100]
0x1801739ba  mov     [rsp+140h+ReferencedDomainName], rax
0x1801739bf  lea     rdx, unk_1803C111A
0x1801739c6  lea     rcx, dword_18042D328
0x1801739cd  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1801739d2  lea     rdx, unk_18043B390
0x1801739d9  mov     rcx, rdi
0x1801739dc  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1801739e1  nop
0x1801739e2  lea     rcx, [rbp+40h+var_90]; this
0x1801739e6  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1801739eb  nop
0x1801739ec  lea     rcx, [rbp+40h+Name]; this
0x1801739f0  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1801739f5  jmp     loc_180173CB4
0x1801739fa  mov     edx, [rsp+140h+cchName]
0x1801739fe  lea     rcx, [rbp+40h+Name]
0x180173a02  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x180173a07  mov     edx, [rsp+140h+var_F4]
0x180173a0b  lea     rcx, [rbp+40h+var_90]
0x180173a0f  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x180173a14  mov     [rsp+140h+var_E8], r14d
0x180173a19  mov     bl, r14b
0x180173a1c  lea     rdx, [rsp+140h+var_E8]
0x180173a21  mov     rcx, [rsp+140h+Sid]
0x180173a26  call    cs:__imp_LsaLookupUserAccountType
0x180173a2d  nop     dword ptr [rax+rax+00h]
0x180173a32  mov     r8d, eax
0x180173a35  test    eax, eax
0x180173a37  js      loc_180173BFC
0x180173a3d  mov     ecx, [rsp+140h+var_E8]
0x180173a41  lea     eax, [rcx-2]
0x180173a44  test    eax, 0FFFFFFFCh
0x180173a49  jnz     loc_180173B63
0x180173a4f  cmp     ecx, 4
0x180173a52  jz      loc_180173B63
0x180173a58  mov     [rsp+140h+DomainControllerInfo], r14
0x180173a5d  lea     rdx, [rbp+40h+var_90]
0x180173a61  cmp     [rbp+40h+var_78], 7
0x180173a66  cmova   rdx, [rbp+40h+var_90]; DomainName
0x180173a6b  lea     rax, [rsp+140h+DomainControllerInfo]
0x180173a70  mov     [rsp+140h+cchReferencedDomainName], rax; DomainControllerInfo
0x180173a75  mov     dword ptr [rsp+140h+ReferencedDomainName], 40000000h; Flags
0x180173a7d  xor     r9d, r9d; SiteName
0x180173a80  xor     r8d, r8d; DomainGuid
0x180173a83  xor     ecx, ecx; ComputerName
0x180173a85  call    cs:__imp_DsGetDcNameW
0x180173a8c  nop     dword ptr [rax+rax+00h]
0x180173a91  mov     r8d, eax
0x180173a94  test    eax, eax
0x180173a96  jz      loc_180173B41
0x180173a9c  mov     ecx, cs:dword_18042D328
0x180173aa2  cmp     ecx, 5
0x180173aa5  jbe     short loc_180173AF8
0x180173aa7  mov     edx, 4000000h
0x180173aac  lea     rcx, dword_18042D328
0x180173ab3  call    _tlgKeywordOn
0x180173ab8  test    al, al
0x180173aba  jz      short loc_180173AF8
0x180173abc  mov     [rsp+140h+var_100], r8d
0x180173ac1  lea     rdx, [rbp+40h+var_90]
0x180173ac5  cmp     [rbp+40h+var_78], 7
0x180173aca  cmova   rdx, [rbp+40h+var_90]
0x180173acf  mov     r8d, [rbp+40h+var_80]
0x180173ad3  lea     rcx, [rsp+140h+var_D0]
0x180173ad8  call    ??$_tlgWrapBinary@_W$01@@YA?AU?$_tlgWrapperArray@$00@@PEB_W_K@Z; _tlgWrapBinary<wchar_t,2>(wchar_t const *,unsigned __int64)
0x180173add  lea     rcx, [rsp+140h+var_100]
0x180173ae2  mov     [rsp+140h+cchReferencedDomainName], rcx
0x180173ae7  mov     [rsp+140h+ReferencedDomainName], rax
0x180173aec  lea     rdx, unk_1803C10B9
0x180173af3  call    ??$Write@U?$_tlgWrapperArray@$00@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperArray@$00@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperArray<1>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperArray<1> const &,_tlgWrapperByVal<4> const &)
0x180173af8  lea     rdx, [rbp+40h+var_A0]
0x180173afc  lea     rcx, [rbp+40h+Name]
0x180173b00  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x180173b05  movups  xmm0, xmmword ptr [rax]
0x180173b08  movdqu  [rbp+40h+var_B0], xmm0
0x180173b0d  lea     rdx, [rbp+40h+var_50]
0x180173b11  lea     rcx, [rbp+40h+var_90]
0x180173b15  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x180173b1a  movups  xmm0, xmmword ptr [rax]
0x180173b1d  movdqu  [rsp+140h+var_D0], xmm0
0x180173b23  mov     byte ptr [rsp+140h+ReferencedDomainName], r14b
0x180173b28  lea     r9, [rbp+40h+var_B0]
0x180173b2c  lea     r8, [rsp+140h+var_D0]
0x180173b31  mov     rdx, rdi
0x180173b34  mov     rcx, rsi
0x180173b37  call    ?HashWindowsAccount@AsimovSharedPartAState@Diagnostics@Microsoft@@QEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@5@0_N@Z; Microsoft::Diagnostics::AsimovSharedPartAState::HashWindowsAccount(std::wstring_view,std::wstring_view,bool)
0x180173b3c  jmp     loc_1801739E2
0x180173b41  mov     bl, 1
0x180173b43  mov     rax, [rsp+140h+DomainControllerInfo]
0x180173b48  mov     rdx, [rax+28h]
0x180173b4c  or      r8, 0FFFFFFFFFFFFFFFFh
0x180173b50  inc     r8
0x180173b53  cmp     [rdx+r8*2], r14w
0x180173b58  jnz     short loc_180173B50
0x180173b5a  lea     rcx, [rbp+40h+var_90]
0x180173b5e  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x180173b63  mov     eax, cs:dword_18042D328
0x180173b69  cmp     eax, 5
0x180173b6c  jbe     loc_180173C43
0x180173b72  mov     edx, 4000000h
0x180173b77  lea     rcx, dword_18042D328
0x180173b7e  call    _tlgKeywordOn
0x180173b83  test    al, al
0x180173b85  jz      loc_180173C43
0x180173b8b  lea     rdx, [rbp+40h+Name]
0x180173b8f  cmp     [rbp+40h+var_58], 7
0x180173b94  cmova   rdx, [rbp+40h+Name]
0x180173b99  mov     r8d, [rbp+40h+var_60]
0x180173b9d  lea     rcx, [rbp+40h+var_50]
0x180173ba1  call    ??$_tlgWrapBinary@_W$01@@YA?AU?$_tlgWrapperArray@$00@@PEB_W_K@Z; _tlgWrapBinary<wchar_t,2>(wchar_t const *,unsigned __int64)
0x180173ba6  mov     r9, rax
0x180173ba9  lea     rdx, [rbp+40h+var_90]
0x180173bad  cmp     [rbp+40h+var_78], 7
0x180173bb2  cmova   rdx, [rbp+40h+var_90]
0x180173bb7  mov     r8d, [rbp+40h+var_80]
0x180173bbb  lea     rcx, [rbp+40h+var_A0]
0x180173bbf  call    ??$_tlgWrapBinary@_W$01@@YA?AU?$_tlgWrapperArray@$00@@PEB_W_K@Z; _tlgWrapBinary<wchar_t,2>(wchar_t const *,unsigned __int64)
0x180173bc4  mov     [rsp+140h+var_FC], bl
0x180173bc8  mov     ecx, [rsp+140h+var_E8]
0x180173bcc  mov     [rsp+140h+var_100], ecx
0x180173bd0  mov     [rsp+140h+var_108], r9
0x180173bd5  mov     [rsp+140h+peUse], rax
0x180173bda  lea     rax, [rsp+140h+var_FC]
0x180173bdf  mov     [rsp+140h+cchReferencedDomainName], rax
0x180173be4  lea     rax, [rsp+140h+var_100]
0x180173be9  mov     [rsp+140h+ReferencedDomainName], rax
0x180173bee  lea     rdx, unk_1803C0F84
0x180173bf5  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperArray@$00@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperArray@$00@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperArray<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperArray<1> const &)
0x180173bfa  jmp     short loc_180173C43
0x180173bfc  mov     eax, cs:dword_18042D328
0x180173c02  cmp     eax, 5
0x180173c05  jbe     short loc_180173C43
0x180173c07  mov     edx, 4000000h
0x180173c0c  lea     rcx, dword_18042D328
0x180173c13  call    _tlgKeywordOn
0x180173c18  test    al, al
0x180173c1a  jz      short loc_180173C43
0x180173c1c  bts     r8d, 1Ch
0x180173c21  mov     [rsp+140h+var_100], r8d
0x180173c26  lea     rax, [rsp+140h+var_100]
0x180173c2b  mov     [rsp+140h+ReferencedDomainName], rax
0x180173c30  lea     rdx, unk_1803C1064
0x180173c37  lea     rcx, dword_18042D328
0x180173c3e  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180173c43  lea     rdx, [rbp+40h+var_50]
0x180173c47  lea     rcx, [rbp+40h+Name]
0x180173c4b  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x180173c50  movups  xmm0, xmmword ptr [rax]
0x180173c53  movdqu  [rsp+140h+var_D0], xmm0
0x180173c59  lea     rdx, [rbp+40h+var_A0]
0x180173c5d  lea     rcx, [rbp+40h+var_90]
0x180173c61  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x180173c66  movups  xmm0, xmmword ptr [rax]
0x180173c69  movdqu  [rbp+40h+var_B0], xmm0
0x180173c6e  mov     byte ptr [rsp+140h+ReferencedDomainName], bl
0x180173c72  lea     r9, [rsp+140h+var_D0]
0x180173c77  lea     r8, [rbp+40h+var_B0]
0x180173c7b  jmp     loc_180173B31
0x180173c80  call    cs:__imp_GetLastError
0x180173c87  nop     dword ptr [rax+rax+00h]
0x180173c8c  mov     r9d, eax; char *
0x180173c8f  mov     rcx, [rbp+48h]; this
0x180173c93  lea     r8, aOnecoreBaseTel_241; "onecore\\base\\telemetry\\utc\\service"...
0x180173c9a  mov     edx, 206h; void *
0x180173c9f  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x180173ca4  lea     rdx, unk_18043B390
0x180173cab  mov     rcx, rdi
0x180173cae  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180173cb3  nop
0x180173cb4  lea     rcx, [rsp+140h+Sid]
0x180173cb9  call    ??1?$unique_storage@U?$resource_policy@PEAU_ACL@@$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_ACL *,void * (void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ACL *,void * (void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>(void)
0x180173cbe  mov     rax, rdi
0x180173cc1  mov     rcx, [rbp+40h+var_30]
0x180173cc5  xor     rcx, rsp; StackCookie
0x180173cc8  call    __security_check_cookie
0x180173ccd  add     rsp, 120h
0x180173cd4  pop     r14
0x180173cd6  pop     rdi
0x180173cd7  pop     rsi
0x180173cd8  pop     rbx
0x180173cd9  pop     rbp
0x180173cda  retn
```
