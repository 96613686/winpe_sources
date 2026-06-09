# EngineAdapterControlUnitPrivileged

- ea: `0x1800952a0`
- end: `0x180095537`
- name: `EngineAdapterControlUnitPrivileged`
- size: `663`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x1800025f8`
- `0x18001434c`
- `0x180014854`
- `0x180014894`
- `0x1800405e4`
- `0x180043744`
- `0x180044b1c`
- `0x18005388c`
- `0x180056358`
- `0x180060254`
- `0x180068f60`
- `0x1800952a0`
- `0x1800b5fdc`
- `0x1800bb4f4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18009540c`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18009540c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800953e0`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800953e0`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x180095366`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x180095366`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x180095372`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x180095372`

## string_xrefs

- `0x180095380`: `onecore\ds\security\biometrics\service\server\winbiopassthroughadapter.cpp`
- `0x1800953bb`: `onecore\ds\security\biometrics\service\server\winbiopassthroughadapter.cpp`
- `0x1800953ee`: `onecore\ds\security\biometrics\service\server\winbiopassthroughadapter.cpp`
- `0x1800954bf`: `onecore\ds\security\biometrics\service\server\winbiopassthroughadapter.cpp`
- `0x18009541d`: `UserSIDDidNotMatch`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall EngineAdapterControlUnitPrivileged(
        __int64 a1,
        unsigned int a2,
        unsigned __int8 *a3,
        unsigned __int64 a4,
        unsigned __int8 *a5,
        unsigned __int64 a6,
        unsigned __int64 *a7,
        unsigned int *a8)
{
  __int64 v12; // rax
  __int64 v13; // rsi
  unsigned int v14; // ebx
  __int64 v15; // r9
  __int64 v16; // rdx
  char v17; // di
  DWORD active; // eax
  const char *v19; // r9
  int v20; // eax
  const char *v21; // r9
  unsigned int LastError; // eax
  __int64 v23; // rcx
  __int64 v24; // r8
  __int64 v25; // r9
  void *v26; // rcx
  int v28; // [rsp+20h] [rbp-91h]
  PSID Sid; // [rsp+48h] [rbp-69h] BYREF
  void *phToken; // [rsp+50h] [rbp-61h] BYREF
  LPCWSTR StringSid[2]; // [rsp+58h] [rbp-59h] BYREF
  int v32[2]; // [rsp+68h] [rbp-49h] BYREF
  unsigned int *v33; // [rsp+70h] [rbp-41h]
  unsigned __int64 *v34; // [rsp+78h] [rbp-39h]
  _BYTE v35[32]; // [rsp+80h] [rbp-31h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+47h]

  v34 = a7;
  v33 = a8;
  std::wstring::wstring((__int64)v35, (__int64)L"NA");
  v12 = WinBioFramework::PipelineToBiometricUnitObject(a1);
  v13 = v12;
  if ( !v12 )
  {
    v14 = -2147467261;
    v15 = 2147500035LL;
    v16 = 490;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\winbiopassthroughadapter.cpp",
      (const char *)v15,
      v28);
    goto LABEL_26;
  }
  v17 = 1;
  if ( *(_DWORD *)(v12 + 88) != 2 )
  {
    v17 = 0;
    std::wstring::_Assign<unsigned short>(v35, L"BioUnitNotSupported");
  }
  if ( a2 != 1 )
  {
    v17 = 0;
    std::wstring::_Assign<unsigned short>(v35, L"ControlCodeNotSupported");
  }
  phToken = 0;
  active = WTSGetActiveConsoleSessionId();
  if ( WTSQueryUserToken(active, &phToken) )
  {
    StringSid[0] = 0;
    v20 = SHGetUserSid(phToken, StringSid);
    v14 = v20;
    if ( v20 < 0 )
    {
      v15 = (unsigned int)v20;
      v16 = 511;
      goto LABEL_11;
    }
    Sid = 0;
    if ( ConvertStringSidToSidW(StringSid[0], &Sid) )
    {
      if ( !EqualSid(a3 + 24, Sid) )
      {
        v17 = 0;
        std::wstring::_Assign<unsigned short>(v35, L"UserSIDDidNotMatch");
      }
      if ( (unsigned int)dword_18010F170 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18010F170, 0x400000000000LL) )
      {
        StringSid[1] = (LPCWSTR)50331648;
        *(_QWORD *)v32 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v35);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>>(
          v23,
          (__int64)byte_1800EFCBD,
          v24,
          v25,
          v32);
      }
      if ( !v17 )
      {
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Sid);
        v14 = -2146861012;
        goto LABEL_26;
      }
      v26 = *(void **)(v13 + 2920);
      if ( !v26 )
      {
        v14 = -2146861054;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x215,
          (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\winbiopassthroughadapter.cpp",
          (const char *)0x80098002LL,
          v28);
LABEL_25:
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Sid);
        goto LABEL_26;
      }
      LastError = BioIsoEngineControlUnitPrivileged(v26, a2, a3, a4, a5, a6, v34, v33);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x201,
                    (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\winbiopassthroughadapter.cpp",
                    v21);
    }
    v14 = LastError;
    goto LABEL_25;
  }
  v14 = wil::details::in1diag3::Return_GetLastError(
          retaddr,
          (void *)0x1FD,
          (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\winbiopassthroughadapter.cpp",
          v19);
LABEL_26:
  std::wstring::_Tidy_deallocate(v35);
  return v14;
}

```

## disassembly

```asm
0x1800952a0  push    rbp
0x1800952a2  push    rbx
0x1800952a3  push    rsi
0x1800952a4  push    rdi
0x1800952a5  push    r12
0x1800952a7  push    r13
0x1800952a9  push    r14
0x1800952ab  push    r15
0x1800952ad  lea     rbp, [rsp-7]
0x1800952b2  sub     rsp, 0B8h
0x1800952b9  mov     rax, cs:__security_cookie
0x1800952c0  xor     rax, rsp
0x1800952c3  mov     [rbp+3Fh+var_50], rax
0x1800952c7  mov     r12, r9
0x1800952ca  mov     r15, r8
0x1800952cd  mov     r14d, edx
0x1800952d0  mov     rbx, rcx
0x1800952d3  mov     r13, [rbp+3Fh+arg_20]
0x1800952d7  mov     rax, [rbp+3Fh+arg_30]
0x1800952db  mov     [rbp+3Fh+var_78], rax
0x1800952df  mov     rax, [rbp+3Fh+arg_38]
0x1800952e6  mov     [rbp+3Fh+var_80], rax
0x1800952ea  lea     rdx, aNa; "NA"
0x1800952f1  lea     rcx, [rbp+3Fh+var_70]
0x1800952f5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800952fa  nop
0x1800952fb  mov     rcx, rbx
0x1800952fe  call    WinBioFramework__PipelineToBiometricUnitObject
0x180095303  mov     rsi, rax
0x180095306  test    rax, rax
0x180095309  jnz     short loc_18009531D
0x18009530b  mov     ebx, 80004003h
0x180095310  mov     r9d, ebx
0x180095313  mov     edx, 1EAh
0x180095318  jmp     loc_1800953BB
0x18009531d  mov     dil, 1
0x180095320  cmp     dword ptr [rax+58h], 2
0x180095324  jz      short loc_18009533F
0x180095326  xor     dil, dil
0x180095329  mov     r8d, 13h
0x18009532f  lea     rdx, aBiounitnotsupp; "BioUnitNotSupported"
0x180095336  lea     rcx, [rbp+3Fh+var_70]
0x18009533a  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18009533f  cmp     r14d, 1
0x180095343  jz      short loc_18009535E
0x180095345  xor     dil, dil
0x180095348  mov     r8d, 17h
0x18009534e  lea     rdx, aControlcodenot; "ControlCodeNotSupported"
0x180095355  lea     rcx, [rbp+3Fh+var_70]
0x180095359  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18009535e  mov     [rbp+3Fh+phToken], 0
0x180095366  call    cs:__imp_WTSGetActiveConsoleSessionId
0x18009536c  mov     ecx, eax; SessionId
0x18009536e  lea     rdx, [rbp+3Fh+phToken]; phToken
0x180095372  call    cs:__imp_WTSQueryUserToken
0x180095378  test    eax, eax
0x18009537a  jnz     short loc_180095398
0x18009537c  mov     rcx, [rbp+47h]; this
0x180095380  lea     r8, aOnecoreDsSecur_39; "onecore\\ds\\security\\biometrics\\serv"...
0x180095387  mov     edx, 1FDh; void *
0x18009538c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180095391  mov     ebx, eax
0x180095393  jmp     loc_18009550C
0x180095398  mov     [rbp+3Fh+StringSid], 0
0x1800953a0  lea     rdx, [rbp+3Fh+StringSid]
0x1800953a4  mov     rcx, [rbp+3Fh+phToken]
0x1800953a8  call    SHGetUserSid
0x1800953ad  mov     ebx, eax
0x1800953af  test    eax, eax
0x1800953b1  jns     short loc_1800953D0
0x1800953b3  mov     r9d, eax; char *
0x1800953b6  mov     edx, 1FFh; void *
0x1800953bb  lea     r8, aOnecoreDsSecur_39; "onecore\\ds\\security\\biometrics\\serv"...
0x1800953c2  mov     rcx, [rbp+47h]; this
0x1800953c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800953cb  jmp     loc_18009550C
0x1800953d0  mov     [rbp+3Fh+Sid], 0
0x1800953d8  lea     rdx, [rbp+3Fh+Sid]; Sid
0x1800953dc  mov     rcx, [rbp+3Fh+StringSid]; StringSid
0x1800953e0  call    cs:__imp_ConvertStringSidToSidW
0x1800953e6  test    eax, eax
0x1800953e8  jnz     short loc_180095404
0x1800953ea  mov     rcx, [rbp+47h]; this
0x1800953ee  lea     r8, aOnecoreDsSecur_39; "onecore\\ds\\security\\biometrics\\serv"...
0x1800953f5  mov     edx, 201h; void *
0x1800953fa  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800953ff  jmp     loc_180095500
0x180095404  lea     rcx, [r15+18h]; pSid1
0x180095408  mov     rdx, [rbp+3Fh+Sid]; pSid2
0x18009540c  call    cs:__imp_EqualSid
0x180095412  test    eax, eax
0x180095414  jnz     short loc_18009542D
0x180095416  xor     dil, dil
0x180095419  lea     r8d, [rax+12h]
0x18009541d  lea     rdx, aUsersiddidnotm; "UserSIDDidNotMatch"
0x180095424  lea     rcx, [rbp+3Fh+var_70]
0x180095428  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18009542d  mov     eax, cs:dword_18010F170
0x180095433  cmp     eax, 5
0x180095436  jbe     short loc_180095492
0x180095438  mov     rdx, 400000000000h
0x180095442  lea     rcx, dword_18010F170
0x180095449  call    _tlgKeywordOn
0x18009544e  test    al, al
0x180095450  jz      short loc_180095492
0x180095452  mov     [rbp+3Fh+var_90], 3000000h
0x18009545a  mov     [rbp+3Fh+var_B0], dil
0x18009545e  lea     rcx, [rbp+3Fh+var_70]
0x180095462  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180095467  mov     qword ptr [rbp+3Fh+var_88], rax
0x18009546b  lea     rax, [rbp+3Fh+var_90]
0x18009546f  mov     [rsp+0F0h+var_C0], rax
0x180095474  lea     rax, [rbp+3Fh+var_B0]
0x180095478  mov     [rsp+0F0h+var_C8], rax
0x18009547d  lea     rax, [rbp+3Fh+var_88]
0x180095481  mov     [rsp+0F0h+var_D0], rax; int
0x180095486  lea     rdx, byte_1800EFCBD
0x18009548d  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<8> const &)
0x180095492  test    dil, dil
0x180095495  jnz     short loc_1800954A7
0x180095497  lea     rcx, [rbp+3Fh+Sid]
0x18009549b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800954a0  mov     ebx, 8009802Ch
0x1800954a5  jmp     short loc_18009550C
0x1800954a7  mov     rcx, [rsi+0B68h]; void *
0x1800954ae  test    rcx, rcx
0x1800954b1  jnz     short loc_1800954D2
0x1800954b3  mov     rcx, [rbp+47h]; this
0x1800954b7  mov     ebx, 80098002h
0x1800954bc  mov     r9d, ebx; char *
0x1800954bf  lea     r8, aOnecoreDsSecur_39; "onecore\\ds\\security\\biometrics\\serv"...
0x1800954c6  mov     edx, 215h; void *
0x1800954cb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800954d0  jmp     short loc_180095502
0x1800954d2  mov     rax, [rbp+3Fh+var_80]
0x1800954d6  mov     [rsp+0F0h+var_B8], rax; unsigned int *
0x1800954db  mov     rax, [rbp+3Fh+var_78]
0x1800954df  mov     [rsp+0F0h+var_C0], rax; unsigned __int64 *
0x1800954e4  mov     rax, [rbp+3Fh+arg_28]
0x1800954e8  mov     [rsp+0F0h+var_C8], rax; unsigned __int64
0x1800954ed  mov     [rsp+0F0h+var_D0], r13; unsigned __int8 *
0x1800954f2  mov     r9, r12; unsigned __int64
0x1800954f5  mov     r8, r15; unsigned __int8 *
0x1800954f8  mov     edx, r14d; unsigned int
0x1800954fb  call    ?BioIsoEngineControlUnitPrivileged@@YAJPEAXKPEAE_K12PEA_KPEAK@Z; BioIsoEngineControlUnitPrivileged(void *,ulong,uchar *,unsigned __int64,uchar *,unsigned __int64,unsigned __int64 *,ulong *)
0x180095500  mov     ebx, eax
0x180095502  lea     rcx, [rbp+3Fh+Sid]
0x180095506  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18009550b  nop
0x18009550c  lea     rcx, [rbp+3Fh+var_70]
0x180095510  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180095515  mov     eax, ebx
0x180095517  mov     rcx, [rbp+3Fh+var_50]
0x18009551b  xor     rcx, rsp; StackCookie
0x18009551e  call    __security_check_cookie
0x180095523  add     rsp, 0B8h
0x18009552a  pop     r15
0x18009552c  pop     r14
0x18009552e  pop     r13
0x180095530  pop     r12
0x180095532  pop     rdi
0x180095533  pop     rsi
0x180095534  pop     rbx
0x180095535  pop     rbp
0x180095536  retn
```
