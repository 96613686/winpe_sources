# Microsoft::Diagnostics::UserManager::GetUserNameFromSid(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>)

- ea: `0x1800ed8ec`
- end: `0x1800edb9f`
- name: `?GetUserNameFromSid@UserManager@Diagnostics@Microsoft@@AEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@5@@Z`
- size: `691`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1801bf0a4`

## callees

- `0x18001d160`
- `0x180030a50`
- `0x180031c08`
- `0x180032718`
- `0x18004a750`
- `0x18005af1c`
- `0x1800a1e24`
- `0x1800b83bc`
- `0x1800bc2e0`
- `0x1800ed8ec`
- `0x1800edba8`
- `0x18012de40`
- `0x18016ff48`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800eda37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800eda37`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ed96d`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800ed9ba`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800ed9ba`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1800eda27`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1800edafc`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1800eda27`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1800edafc`

## string_xrefs

- `0x1800ed929`: `onecore\base\telemetry\utc\service\engine\usermanager.cpp`
- `0x1800ed9d2`: `onecore\base\telemetry\utc\service\engine\usermanager.cpp`
- `0x1800eda64`: `onecore\base\telemetry\utc\service\engine\usermanager.cpp`
- `0x1800edb14`: `onecore\base\telemetry\utc\service\engine\usermanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall Microsoft::Diagnostics::UserManager::GetUserNameFromSid(__int64 a1, __int64 a2, _QWORD *a3)
{
  __int64 v5; // r8
  const WCHAR *v6; // rcx
  const char *v7; // r9
  signed int LastError; // eax
  const char *v9; // r9
  WCHAR *v10; // rax
  WCHAR *v11; // r8
  const char *v12; // r9
  int ReferencedDomainName; // [rsp+20h] [rbp-D8h]
  int ReferencedDomainNamea; // [rsp+20h] [rbp-D8h]
  DWORD cchReferencedDomainName; // [rsp+40h] [rbp-B8h] BYREF
  DWORD cchName; // [rsp+44h] [rbp-B4h] BYREF
  PSID Sid; // [rsp+48h] [rbp-B0h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+50h] [rbp-A8h] BYREF
  __int64 v20; // [rsp+58h] [rbp-A0h]
  LPWSTR Name[4]; // [rsp+80h] [rbp-78h] BYREF
  LPWSTR v22[4]; // [rsp+A0h] [rbp-58h] BYREF
  LPCWSTR StringSid[4]; // [rsp+C0h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  v20 = a2;
  v5 = a3[1];
  if ( !v5 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x51F,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\usermanager.cpp",
      (const char *)0x8000FFFFLL,
      ReferencedDomainName);
  Sid = 0;
  std::wstring::wstring(StringSid, *a3, v5);
  Sid = 0;
  v6 = (const WCHAR *)StringSid;
  if ( StringSid[3] > (LPCWSTR)7 )
    v6 = StringSid[0];
  if ( !ConvertStringSidToSidW(v6, &Sid) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x524,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\usermanager.cpp",
      v7);
  cchName = 0;
  cchReferencedDomainName = 0;
  peUse = SidTypeUnknown;
  if ( !LookupAccountSidW(0, Sid, 0, &cchName, 0, &cchReferencedDomainName, &peUse) )
  {
    LastError = GetLastError();
    v9 = LastError > 0
       ? (const char *)((unsigned __int16)LastError | 0x80070000)
       : (const char *)(unsigned int)LastError;
    if ( LastError != 122 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x533,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\usermanager.cpp",
        v9,
        ReferencedDomainNamea);
  }
  std::wstring::wstring(Name, cchName - 1, 0);
  std::wstring::wstring(v22, cchReferencedDomainName - 1, 0);
  v10 = (WCHAR *)v22;
  if ( v22[3] > (LPWSTR)7 )
    v10 = v22[0];
  v11 = (WCHAR *)Name;
  if ( Name[3] > (LPWSTR)7 )
    v11 = Name[0];
  if ( !LookupAccountSidW(0, Sid, v11, &cchName, v10, &cchReferencedDomainName, &peUse) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x540,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\usermanager.cpp",
      v12);
  std::wstring::wstring(a2, Name);
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v22);
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Name);
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)StringSid);
  wil::details::unique_storage<wil::details::resource_policy<_ACL *,void * (void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ACL *,void * (void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>(&Sid);
  return a2;
}

```

## disassembly

```asm
0x1800ed8ec  push    rbx
0x1800ed8ee  sub     rsp, 0F0h
0x1800ed8f5  mov     rax, cs:__security_cookie
0x1800ed8fc  xor     rax, rsp
0x1800ed8ff  mov     [rsp+0F8h+var_18], rax
0x1800ed907  mov     rax, r8
0x1800ed90a  mov     rbx, rdx
0x1800ed90d  mov     [rsp+0F8h+var_A0], rdx
0x1800ed912  mov     r8, [r8+8]
0x1800ed916  mov     rcx, [rsp+0F8h]; this
0x1800ed91e  test    r8, r8
0x1800ed921  jnz     short loc_1800ED93A
0x1800ed923  mov     r9d, 8000FFFFh; char *
0x1800ed929  lea     r8, aOnecoreBaseTel_121; "onecore\\base\\telemetry\\utc\\service"...
0x1800ed930  mov     edx, 51Fh; void *
0x1800ed935  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ed93a  mov     [rsp+0F8h+Sid], 0
0x1800ed943  mov     rdx, [rax]
0x1800ed946  lea     rcx, [rsp+0F8h+StringSid]
0x1800ed94e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W_K@Z; std::wstring::wstring(wchar_t const * const,unsigned __int64)
0x1800ed953  nop
0x1800ed954  mov     rax, [rsp+0F8h+Sid]
0x1800ed959  test    rax, rax
0x1800ed95c  jz      short loc_1800ED992
0x1800ed95e  mov     [rsp+0F8h+var_90], rax
0x1800ed963  lea     rcx, [rsp+0F8h+var_80]; this
0x1800ed968  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800ed96d  mov     rax, cs:__imp_LocalFree
0x1800ed974  mov     [rsp+0F8h+var_88], rax
0x1800ed979  lea     rdx, [rsp+0F8h+var_90]
0x1800ed97e  lea     rcx, [rsp+0F8h+var_88]
0x1800ed983  call    ??$invoke@P6APEAXPEAX@ZAEAPEAX@wistd@@YAPEAX$$QEAP6APEAXPEAX@ZAEAPEAX@Z; wistd::invoke<void * (*)(void *),void * &>(void * (*&&)(void *),void * &)
0x1800ed988  lea     rcx, [rsp+0F8h+var_80]; this
0x1800ed98d  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800ed992  mov     [rsp+0F8h+Sid], 0
0x1800ed99b  lea     rcx, [rsp+0F8h+StringSid]
0x1800ed9a3  cmp     [rsp+0F8h+var_20], 7
0x1800ed9ac  cmova   rcx, [rsp+0F8h+StringSid]; StringSid
0x1800ed9b5  lea     rdx, [rsp+0F8h+Sid]; Sid
0x1800ed9ba  call    cs:__imp_ConvertStringSidToSidW
0x1800ed9c1  nop     dword ptr [rax+rax+00h]
0x1800ed9c6  mov     rcx, [rsp+0F8h]; this
0x1800ed9ce  test    eax, eax
0x1800ed9d0  jnz     short loc_1800ED9E3
0x1800ed9d2  lea     r8, aOnecoreBaseTel_121; "onecore\\base\\telemetry\\utc\\service"...
0x1800ed9d9  mov     edx, 524h; void *
0x1800ed9de  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800ed9e3  mov     [rsp+0F8h+cchName], 0
0x1800ed9eb  mov     [rsp+0F8h+var_B8], 0
0x1800ed9f3  mov     [rsp+0F8h+var_A8], 8
0x1800ed9fb  lea     rax, [rsp+0F8h+var_A8]
0x1800eda00  mov     [rsp+0F8h+peUse], rax; peUse
0x1800eda05  lea     rax, [rsp+0F8h+var_B8]
0x1800eda0a  mov     [rsp+0F8h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800eda0f  mov     [rsp+0F8h+ReferencedDomainName], 0; int
0x1800eda18  lea     r9, [rsp+0F8h+cchName]; cchName
0x1800eda1d  xor     r8d, r8d; Name
0x1800eda20  mov     rdx, [rsp+0F8h+Sid]; Sid
0x1800eda25  xor     ecx, ecx; lpSystemName
0x1800eda27  call    cs:__imp_LookupAccountSidW
0x1800eda2e  nop     dword ptr [rax+rax+00h]
0x1800eda33  test    eax, eax
0x1800eda35  jnz     short loc_1800EDA75
0x1800eda37  call    cs:__imp_GetLastError
0x1800eda3e  nop     dword ptr [rax+rax+00h]
0x1800eda43  test    eax, eax
0x1800eda45  jg      short loc_1800EDA4C
0x1800eda47  mov     r9d, eax
0x1800eda4a  jmp     short loc_1800EDA57
0x1800eda4c  movzx   r9d, ax
0x1800eda50  or      r9d, 80070000h; char *
0x1800eda57  mov     rcx, [rsp+0F8h]; this
0x1800eda5f  cmp     eax, 7Ah ; 'z'
0x1800eda62  jz      short loc_1800EDA75
0x1800eda64  lea     r8, aOnecoreBaseTel_121; "onecore\\base\\telemetry\\utc\\service"...
0x1800eda6b  mov     edx, 533h; void *
0x1800eda70  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800eda75  xor     r8d, r8d
0x1800eda78  mov     edx, [rsp+0F8h+cchName]
0x1800eda7c  dec     edx
0x1800eda7e  lea     rcx, [rsp+0F8h+Name]
0x1800eda86  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@_K_W@Z; std::wstring::wstring(unsigned __int64,wchar_t)
0x1800eda8b  nop
0x1800eda8c  xor     r8d, r8d
0x1800eda8f  mov     edx, [rsp+0F8h+var_B8]
0x1800eda93  dec     edx
0x1800eda95  lea     rcx, [rsp+0F8h+var_58]
0x1800eda9d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@_K_W@Z; std::wstring::wstring(unsigned __int64,wchar_t)
0x1800edaa2  nop
0x1800edaa3  lea     rax, [rsp+0F8h+var_58]
0x1800edaab  cmp     [rsp+0F8h+var_40], 7
0x1800edab4  cmova   rax, [rsp+0F8h+var_58]
0x1800edabd  lea     r8, [rsp+0F8h+Name]
0x1800edac5  cmp     [rsp+0F8h+var_60], 7
0x1800edace  cmova   r8, [rsp+0F8h+Name]; Name
0x1800edad7  lea     rcx, [rsp+0F8h+var_A8]
0x1800edadc  mov     [rsp+0F8h+peUse], rcx; peUse
0x1800edae1  lea     rcx, [rsp+0F8h+var_B8]
0x1800edae6  mov     [rsp+0F8h+cchReferencedDomainName], rcx; cchReferencedDomainName
0x1800edaeb  mov     [rsp+0F8h+ReferencedDomainName], rax; ReferencedDomainName
0x1800edaf0  lea     r9, [rsp+0F8h+cchName]; cchName
0x1800edaf5  mov     rdx, [rsp+0F8h+Sid]; Sid
0x1800edafa  xor     ecx, ecx; lpSystemName
0x1800edafc  call    cs:__imp_LookupAccountSidW
0x1800edb03  nop     dword ptr [rax+rax+00h]
0x1800edb08  mov     rcx, [rsp+0F8h]; this
0x1800edb10  test    eax, eax
0x1800edb12  jnz     short loc_1800EDB25
0x1800edb14  lea     r8, aOnecoreBaseTel_121; "onecore\\base\\telemetry\\utc\\service"...
0x1800edb1b  mov     edx, 540h; void *
0x1800edb20  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800edb25  lea     rdx, [rsp+0F8h+Name]
0x1800edb2d  mov     rcx, rbx
0x1800edb30  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x1800edb35  nop
0x1800edb36  lea     rcx, [rsp+0F8h+var_58]; this
0x1800edb3e  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1800edb43  nop
0x1800edb44  lea     rcx, [rsp+0F8h+Name]; this
0x1800edb4c  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1800edb51  nop
0x1800edb52  lea     rcx, [rsp+0F8h+StringSid]; this
0x1800edb5a  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1800edb5f  nop
0x1800edb60  lea     rcx, [rsp+0F8h+Sid]
0x1800edb65  call    ??1?$unique_storage@U?$resource_policy@PEAU_ACL@@$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_ACL *,void * (void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ACL *,void * (void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>(void)
0x1800edb6a  mov     rax, rbx
0x1800edb6d  jmp     short loc_1800EDB85
0x1800edb6f  lea     rdx, unk_18043B530
0x1800edb76  mov     rcx, [rsp+0F8h+var_A0]
0x1800edb7b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800edb80  mov     rax, [rsp+0F8h+var_A0]
0x1800edb85  mov     rcx, [rsp+0F8h+var_18]
0x1800edb8d  xor     rcx, rsp; StackCookie
0x1800edb90  call    __security_check_cookie
0x1800edb95  add     rsp, 0F0h
0x1800edb9c  pop     rbx
0x1800edb9d  retn
```
