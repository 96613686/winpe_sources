# CheckXForestLogon

- ea: `0x1800197f0`
- end: `0x180019a13`
- name: `CheckXForestLogon`
- size: `547`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800040b0`
- `0x1800055d8`
- `0x1800065d8`
- `0x1800069c8`
- `0x18000d57c`
- `0x18000dae0`
- `0x18000db08`
- `0x18000e640`
- `0x180015c78`
- `0x180019404`
- `0x1800197f0`
- `0x180019a1c`

## import_xrefs

- `DNSAPI!DnsNameCompare_W` at `0x18001998d`
- `DNSAPI!DnsNameCompare_W` at `0x18001998d`
- `logoncli!DsEnumerateDomainTrustsW` at `0x180019933`
- `logoncli!DsEnumerateDomainTrustsW` at `0x180019933`

## string_xrefs

- `0x180019821`: `onecore\ds\security\gina\profile\userenv\dll\util.cpp`
- `0x1800198e6`: `onecore\ds\security\gina\profile\userenv\dll\util.cpp`
- `0x18001994e`: `onecore\ds\security\gina\profile\userenv\dll\util.cpp`

## pseudocode

```c
__int64 __fastcall CheckXForestLogon(HKEY a1, __int64 a2, int a3)
{
  unsigned int v4; // ebx
  int v6; // edi
  int UserNameAndDomain; // eax
  __int64 v8; // rdx
  DWORD v9; // eax
  ULONG i; // ebx
  BOOL v11; // eax
  int v12; // ecx
  int v13; // r8d
  unsigned int v14; // [rsp+20h] [rbp-29h]
  ULONG DomainCount; // [rsp+30h] [rbp-19h] BYREF
  PCWSTR pName1; // [rsp+38h] [rbp-11h] BYREF
  __int64 v17; // [rsp+40h] [rbp-9h]
  __int64 v18; // [rsp+48h] [rbp-1h]
  int v19; // [rsp+50h] [rbp+7h] BYREF
  __int64 v20; // [rsp+58h] [rbp+Fh]
  __int64 v21; // [rsp+60h] [rbp+17h]
  int v22; // [rsp+68h] [rbp+1Fh]
  __int128 v23; // [rsp+70h] [rbp+27h]
  PDS_DOMAIN_TRUSTSW Domains[2]; // [rsp+80h] [rbp+37h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  if ( !a1 )
  {
    v4 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x24C,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\dll\\util.cpp",
      (const char *)0x80070057LL,
      v14);
    return v4;
  }
  v6 = CheckPolicy(a1, L"AllowX-ForestPolicy-and-RUP", a3);
  if ( v6 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
      && (Microsoft_Windows_User_Profiles_GeneralEnableBits & 8) != 0 )
    {
      McGenEventWrite_EtwEventWriteTransfer(
        v12,
        (unsigned int)EVENT_CHECK_XFOREST_LOGON_POLICY_ENABLED,
        v13,
        1,
        (__int64)Domains);
    }
  }
  else
  {
    pName1 = 0;
    v17 = 0;
    v18 = 0;
    v23 = 0;
    v19 = 0;
    v20 = 0;
    v21 = 0;
    v22 = 0;
    UserNameAndDomain = CThreadContext::ImpersonateUser((CThreadContext *)&v19, a1);
    v4 = UserNameAndDomain;
    if ( UserNameAndDomain < 0 )
    {
      v8 = 600;
LABEL_11:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\dll\\util.cpp",
        (const char *)(unsigned int)UserNameAndDomain,
        v14);
LABEL_12:
      CThreadContext::~CThreadContext((CThreadContext *)&v19);
LABEL_13:
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&pName1);
      return v4;
    }
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&pName1);
    v17 = -1;
    v18 = -1;
    UserNameAndDomain = GetUserNameAndDomain(NameDnsDomain, 0, (unsigned __int16 **)&pName1);
    v4 = UserNameAndDomain;
    if ( UserNameAndDomain == -2147023541 || UserNameAndDomain == -2147023564 )
      goto LABEL_12;
    if ( UserNameAndDomain < 0 )
    {
      v8 = 605;
      goto LABEL_11;
    }
    CThreadContext::~CThreadContext((CThreadContext *)&v19);
    DomainCount = 0;
    Domains[0] = 0;
    v9 = DsEnumerateDomainTrustsW(0, 1u, Domains, &DomainCount);
    if ( v9 != 1722 )
    {
      if ( v9 )
      {
        v4 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x266,
               (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\dll\\util.cpp",
               (const char *)v9,
               v14);
        wil::details::unique_storage<wil::details::resource_policy<_DS_DOMAIN_TRUSTSW *,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_DS_DOMAIN_TRUSTSW *,_DS_DOMAIN_TRUSTSW *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DS_DOMAIN_TRUSTSW *,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_DS_DOMAIN_TRUSTSW *,_DS_DOMAIN_TRUSTSW *,0,std::nullptr_t>>(Domains);
        goto LABEL_13;
      }
      for ( i = 0; i < DomainCount; v6 = v11 )
      {
        if ( v6 )
          break;
        v11 = DnsNameCompare_W(pName1, Domains[0][i++].DnsDomainName);
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_DS_DOMAIN_TRUSTSW *,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_DS_DOMAIN_TRUSTSW *,_DS_DOMAIN_TRUSTSW *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DS_DOMAIN_TRUSTSW *,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_DS_DOMAIN_TRUSTSW *,_DS_DOMAIN_TRUSTSW *,0,std::nullptr_t>>(Domains);
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&pName1);
  }
  return v6 == 0;
}

```

## disassembly

```asm
0x1800197f0  mov     [rsp-8+arg_8], rbx
0x1800197f5  mov     [rsp-8+arg_10], rdi
0x1800197fa  push    rbp
0x1800197fb  lea     rbp, [rsp-57h]
0x180019800  sub     rsp, 0A0h
0x180019807  mov     rax, cs:__security_cookie
0x18001980e  xor     rax, rsp
0x180019811  mov     [rbp+57h+var_10], rax
0x180019815  mov     rbx, rcx
0x180019818  test    rcx, rcx
0x18001981b  jnz     short loc_180019841
0x18001981d  mov     rcx, [rbp+5Fh]; this
0x180019821  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\gina\\profile\\u"...
0x180019828  mov     ebx, 80070057h
0x18001982d  mov     edx, 24Ch; void *
0x180019832  mov     r9d, ebx; char *
0x180019835  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001983a  mov     eax, ebx
0x18001983c  jmp     loc_1800199F1
0x180019841  lea     rdx, aAllowxForestpo; "AllowX-ForestPolicy-and-RUP"
0x180019848  call    ?CheckPolicy@@YAHPEAUHKEY__@@PEBGH@Z; CheckPolicy(HKEY__ *,ushort const *,int)
0x18001984d  mov     edi, eax
0x18001984f  test    eax, eax
0x180019851  jnz     loc_1800199B6
0x180019857  xorps   xmm0, xmm0
0x18001985a  mov     [rbp+57h+pName1], 0
0x180019862  mov     rdx, rbx; void *
0x180019865  mov     [rbp+57h+var_60], 0
0x18001986d  lea     rcx, [rbp+57h+var_50]; this
0x180019871  mov     [rbp+57h+var_58], 0
0x180019879  movdqu  [rbp+57h+var_30], xmm0
0x18001987e  mov     [rbp+57h+var_50], eax
0x180019881  mov     [rbp+57h+var_48], 0
0x180019889  mov     [rbp+57h+var_40], 0
0x180019891  mov     [rbp+57h+var_38], eax
0x180019894  call    ?ImpersonateUser@CThreadContext@@QEAAJPEAX@Z; CThreadContext::ImpersonateUser(void *)
0x180019899  mov     ebx, eax
0x18001989b  test    eax, eax
0x18001989d  jns     short loc_1800198A6
0x18001989f  mov     edx, 258h
0x1800198a4  jmp     short loc_1800198E2
0x1800198a6  lea     rcx, [rbp+57h+pName1]
0x1800198aa  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800198af  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800198b3  lea     r8, [rbp+57h+pName1]; unsigned __int16 **
0x1800198b7  xor     edx, edx; unsigned __int16 **
0x1800198b9  mov     [rbp+57h+var_60], rax
0x1800198bd  mov     [rbp+57h+var_58], rax
0x1800198c1  lea     ecx, [rax+0Dh]; enum EXTENDED_NAME_FORMAT
0x1800198c4  call    ?GetUserNameAndDomain@@YAJW4EXTENDED_NAME_FORMAT@@PEAPEAG1@Z; GetUserNameAndDomain(EXTENDED_NAME_FORMAT,ushort * *,ushort * *)
0x1800198c9  mov     ebx, eax
0x1800198cb  cmp     eax, 8007054Bh
0x1800198d0  jz      short loc_1800198F5
0x1800198d2  cmp     eax, 80070534h
0x1800198d7  jz      short loc_1800198F5
0x1800198d9  test    eax, eax
0x1800198db  jns     short loc_18001990C
0x1800198dd  mov     edx, 25Dh; void *
0x1800198e2  mov     rcx, [rbp+5Fh]; this
0x1800198e6  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\gina\\profile\\u"...
0x1800198ed  mov     r9d, eax; char *
0x1800198f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800198f5  lea     rcx, [rbp+57h+var_50]; this
0x1800198f9  call    ??1CThreadContext@@QEAA@XZ; CThreadContext::~CThreadContext(void)
0x1800198fe  lea     rcx, [rbp+57h+pName1]
0x180019902  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180019907  jmp     loc_18001983A
0x18001990c  lea     rcx, [rbp+57h+var_50]; this
0x180019910  call    ??1CThreadContext@@QEAA@XZ; CThreadContext::~CThreadContext(void)
0x180019915  lea     r9, [rbp+57h+DomainCount]; DomainCount
0x180019919  mov     [rbp+57h+DomainCount], 0
0x180019920  lea     r8, [rbp+57h+Domains]; Domains
0x180019924  mov     [rbp+57h+Domains], 0
0x18001992c  mov     edx, 1; Flags
0x180019931  xor     ecx, ecx; ServerName
0x180019933  call    cs:__imp_DsEnumerateDomainTrustsW
0x18001993a  nop     dword ptr [rax+rax+00h]
0x18001993f  cmp     eax, 6BAh
0x180019944  jz      short loc_1800199A2
0x180019946  test    eax, eax
0x180019948  jz      short loc_18001996F
0x18001994a  mov     rcx, [rbp+5Fh]; this
0x18001994e  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\gina\\profile\\u"...
0x180019955  mov     r9d, eax; char *
0x180019958  mov     edx, 266h; void *
0x18001995d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180019962  lea     rcx, [rbp+57h+Domains]
0x180019966  mov     ebx, eax
0x180019968  call    ??1?$unique_storage@U?$resource_policy@PEAU_DS_DOMAIN_TRUSTSW@@P6AKPEAX@Z$1?NetApiBufferFree@@YAK0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_DS_DOMAIN_TRUSTSW *,ulong (*)(void *),&NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_DS_DOMAIN_TRUSTSW *,_DS_DOMAIN_TRUSTSW *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DS_DOMAIN_TRUSTSW *,ulong (*)(void *),&NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_DS_DOMAIN_TRUSTSW *,_DS_DOMAIN_TRUSTSW *,0,std::nullptr_t>>(void)
0x18001996d  jmp     short loc_1800198FE
0x18001996f  xor     ebx, ebx
0x180019971  cmp     [rbp+57h+DomainCount], ebx
0x180019974  jbe     short loc_1800199A2
0x180019976  test    edi, edi
0x180019978  jnz     short loc_1800199A2
0x18001997a  mov     rdx, [rbp+57h+Domains]
0x18001997e  mov     eax, ebx
0x180019980  imul    rcx, rax, 38h ; '8'
0x180019984  mov     rdx, [rcx+rdx+8]; pName2
0x180019989  mov     rcx, [rbp+57h+pName1]; pName1
0x18001998d  call    cs:__imp_DnsNameCompare_W
0x180019994  nop     dword ptr [rax+rax+00h]
0x180019999  inc     ebx
0x18001999b  mov     edi, eax
0x18001999d  cmp     ebx, [rbp+57h+DomainCount]
0x1800199a0  jb      short loc_180019976
0x1800199a2  lea     rcx, [rbp+57h+Domains]
0x1800199a6  call    ??1?$unique_storage@U?$resource_policy@PEAU_DS_DOMAIN_TRUSTSW@@P6AKPEAX@Z$1?NetApiBufferFree@@YAK0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_DS_DOMAIN_TRUSTSW *,ulong (*)(void *),&NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_DS_DOMAIN_TRUSTSW *,_DS_DOMAIN_TRUSTSW *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DS_DOMAIN_TRUSTSW *,ulong (*)(void *),&NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_DS_DOMAIN_TRUSTSW *,_DS_DOMAIN_TRUSTSW *,0,std::nullptr_t>>(void)
0x1800199ab  lea     rcx, [rbp+57h+pName1]
0x1800199af  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800199b4  jmp     short loc_1800199EA
0x1800199b6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x1800199bd  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x1800199c2  test    al, al
0x1800199c4  jz      short loc_1800199EA
0x1800199c6  test    byte ptr cs:Microsoft_Windows_User_Profiles_GeneralEnableBits, 8
0x1800199cd  jz      short loc_1800199EA
0x1800199cf  lea     rax, [rbp+57h+Domains]
0x1800199d3  mov     r9d, 1
0x1800199d9  lea     rdx, EVENT_CHECK_XFOREST_LOGON_POLICY_ENABLED
0x1800199e0  mov     qword ptr [rsp+0A0h+var_80], rax
0x1800199e5  call    McGenEventWrite_EtwEventWriteTransfer
0x1800199ea  xor     eax, eax
0x1800199ec  test    edi, edi
0x1800199ee  setz    al
0x1800199f1  mov     rcx, [rbp+57h+var_10]
0x1800199f5  xor     rcx, rsp; StackCookie
0x1800199f8  call    __security_check_cookie
0x1800199fd  lea     r11, [rsp+0A0h+var_s0]
0x180019a05  mov     rbx, [r11+18h]
0x180019a09  mov     rdi, [r11+20h]
0x180019a0d  mov     rsp, r11
0x180019a10  pop     rbp
0x180019a11  retn
```
