# CheckXForestLogon

- ea: `0x180017ee0`
- end: `0x1800180f6`
- name: `CheckXForestLogon`
- size: `534`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180003f60`
- `0x180004f28`
- `0x180005de0`
- `0x1800063d8`
- `0x18000c97c`
- `0x18000ce7c`
- `0x18000cea0`
- `0x18000d9b0`
- `0x180014a08`
- `0x180017a94`
- `0x180017ee0`
- `0x1800180fc`

## import_xrefs

- `DNSAPI!DnsNameCompare_W` at `0x180018077`
- `DNSAPI!DnsNameCompare_W` at `0x180018077`
- `logoncli!DsEnumerateDomainTrustsW` at `0x180018023`
- `logoncli!DsEnumerateDomainTrustsW` at `0x180018023`

## string_xrefs

- `0x180017f11`: `onecore\ds\security\gina\profile\userenv\dll\util.cpp`
- `0x180017fd6`: `onecore\ds\security\gina\profile\userenv\dll\util.cpp`
- `0x180018038`: `onecore\ds\security\gina\profile\userenv\dll\util.cpp`

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
  ULONG DomainCount; // [rsp+30h] [rbp-19h] BYREF
  PCWSTR pName1; // [rsp+38h] [rbp-11h] BYREF
  __int64 v16; // [rsp+40h] [rbp-9h]
  __int64 v17; // [rsp+48h] [rbp-1h]
  int v18; // [rsp+50h] [rbp+7h] BYREF
  __int64 v19; // [rsp+58h] [rbp+Fh]
  __int64 v20; // [rsp+60h] [rbp+17h]
  int v21; // [rsp+68h] [rbp+1Fh]
  __int128 v22; // [rsp+70h] [rbp+27h]
  PDS_DOMAIN_TRUSTSW Domains[2]; // [rsp+80h] [rbp+37h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  if ( !a1 )
  {
    v4 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x24C,
      (int)"onecore\\ds\\security\\gina\\profile\\userenv\\dll\\util.cpp",
      (const char *)0x80070057LL);
    return v4;
  }
  v6 = CheckPolicy(a1, L"AllowX-ForestPolicy-and-RUP", a3);
  if ( v6 )
  {
    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
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
    v16 = 0;
    v17 = 0;
    v22 = 0;
    v18 = 0;
    v19 = 0;
    v20 = 0;
    v21 = 0;
    UserNameAndDomain = CThreadContext::ImpersonateUser((CThreadContext *)&v18, a1);
    v4 = UserNameAndDomain;
    if ( UserNameAndDomain < 0 )
    {
      v8 = 600;
LABEL_11:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (int)"onecore\\ds\\security\\gina\\profile\\userenv\\dll\\util.cpp",
        (const char *)(unsigned int)UserNameAndDomain);
LABEL_12:
      CThreadContext::~CThreadContext((CThreadContext *)&v18);
LABEL_13:
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&pName1);
      return v4;
    }
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&pName1);
    v16 = -1;
    v17 = -1;
    UserNameAndDomain = GetUserNameAndDomain(NameDnsDomain, 0, (unsigned __int16 **)&pName1);
    v4 = UserNameAndDomain;
    if ( UserNameAndDomain == -2147023541 || UserNameAndDomain == -2147023564 )
      goto LABEL_12;
    if ( UserNameAndDomain < 0 )
    {
      v8 = 605;
      goto LABEL_11;
    }
    CThreadContext::~CThreadContext((CThreadContext *)&v18);
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
               (int)"onecore\\ds\\security\\gina\\profile\\userenv\\dll\\util.cpp",
               (const char *)v9);
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
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&pName1);
  }
  return v6 == 0;
}

```

## disassembly

```asm
0x180017ee0  mov     [rsp-8+arg_8], rbx
0x180017ee5  mov     [rsp-8+arg_10], rdi
0x180017eea  push    rbp
0x180017eeb  lea     rbp, [rsp-57h]
0x180017ef0  sub     rsp, 0A0h
0x180017ef7  mov     rax, cs:__security_cookie
0x180017efe  xor     rax, rsp
0x180017f01  mov     [rbp+57h+var_10], rax
0x180017f05  mov     rbx, rcx
0x180017f08  test    rcx, rcx
0x180017f0b  jnz     short loc_180017F31
0x180017f0d  mov     rcx, [rbp+5Fh]; this
0x180017f11  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\gina\\profile\\u"...
0x180017f18  mov     ebx, 80070057h
0x180017f1d  mov     edx, 24Ch; void *
0x180017f22  mov     r9d, ebx; char *
0x180017f25  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017f2a  mov     eax, ebx
0x180017f2c  jmp     loc_1800180D5
0x180017f31  lea     rdx, aAllowxForestpo; "AllowX-ForestPolicy-and-RUP"
0x180017f38  call    ?CheckPolicy@@YAHPEAUHKEY__@@PEBGH@Z; CheckPolicy(HKEY__ *,ushort const *,int)
0x180017f3d  mov     edi, eax
0x180017f3f  test    eax, eax
0x180017f41  jnz     loc_18001809A
0x180017f47  xorps   xmm0, xmm0
0x180017f4a  mov     [rbp+57h+pName1], 0
0x180017f52  mov     rdx, rbx; void *
0x180017f55  mov     [rbp+57h+var_60], 0
0x180017f5d  lea     rcx, [rbp+57h+var_50]; this
0x180017f61  mov     [rbp+57h+var_58], 0
0x180017f69  movdqu  [rbp+57h+var_30], xmm0
0x180017f6e  mov     [rbp+57h+var_50], eax
0x180017f71  mov     [rbp+57h+var_48], 0
0x180017f79  mov     [rbp+57h+var_40], 0
0x180017f81  mov     [rbp+57h+var_38], eax
0x180017f84  call    ?ImpersonateUser@CThreadContext@@QEAAJPEAX@Z; CThreadContext::ImpersonateUser(void *)
0x180017f89  mov     ebx, eax
0x180017f8b  test    eax, eax
0x180017f8d  jns     short loc_180017F96
0x180017f8f  mov     edx, 258h
0x180017f94  jmp     short loc_180017FD2
0x180017f96  lea     rcx, [rbp+57h+pName1]
0x180017f9a  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180017f9f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180017fa3  lea     r8, [rbp+57h+pName1]; unsigned __int16 **
0x180017fa7  xor     edx, edx; unsigned __int16 **
0x180017fa9  mov     [rbp+57h+var_60], rax
0x180017fad  mov     [rbp+57h+var_58], rax
0x180017fb1  lea     ecx, [rax+0Dh]; enum EXTENDED_NAME_FORMAT
0x180017fb4  call    ?GetUserNameAndDomain@@YAJW4EXTENDED_NAME_FORMAT@@PEAPEAG1@Z; GetUserNameAndDomain(EXTENDED_NAME_FORMAT,ushort * *,ushort * *)
0x180017fb9  mov     ebx, eax
0x180017fbb  cmp     eax, 8007054Bh
0x180017fc0  jz      short loc_180017FE5
0x180017fc2  cmp     eax, 80070534h
0x180017fc7  jz      short loc_180017FE5
0x180017fc9  test    eax, eax
0x180017fcb  jns     short loc_180017FFC
0x180017fcd  mov     edx, 25Dh; void *
0x180017fd2  mov     rcx, [rbp+5Fh]; this
0x180017fd6  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\gina\\profile\\u"...
0x180017fdd  mov     r9d, eax; char *
0x180017fe0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017fe5  lea     rcx, [rbp+57h+var_50]; this
0x180017fe9  call    ??1CThreadContext@@QEAA@XZ; CThreadContext::~CThreadContext(void)
0x180017fee  lea     rcx, [rbp+57h+pName1]
0x180017ff2  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180017ff7  jmp     loc_180017F2A
0x180017ffc  lea     rcx, [rbp+57h+var_50]; this
0x180018000  call    ??1CThreadContext@@QEAA@XZ; CThreadContext::~CThreadContext(void)
0x180018005  lea     r9, [rbp+57h+DomainCount]; DomainCount
0x180018009  mov     [rbp+57h+DomainCount], 0
0x180018010  lea     r8, [rbp+57h+Domains]; Domains
0x180018014  mov     [rbp+57h+Domains], 0
0x18001801c  mov     edx, 1; Flags
0x180018021  xor     ecx, ecx; ServerName
0x180018023  call    cs:__imp_DsEnumerateDomainTrustsW
0x180018029  cmp     eax, 6BAh
0x18001802e  jz      short loc_180018086
0x180018030  test    eax, eax
0x180018032  jz      short loc_180018059
0x180018034  mov     rcx, [rbp+5Fh]; this
0x180018038  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\gina\\profile\\u"...
0x18001803f  mov     r9d, eax; char *
0x180018042  mov     edx, 266h; void *
0x180018047  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001804c  lea     rcx, [rbp+57h+Domains]
0x180018050  mov     ebx, eax
0x180018052  call    ??1?$unique_storage@U?$resource_policy@PEAU_DS_DOMAIN_TRUSTSW@@P6AKPEAX@Z$1?NetApiBufferFree@@YAK0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_DS_DOMAIN_TRUSTSW *,ulong (*)(void *),&NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_DS_DOMAIN_TRUSTSW *,_DS_DOMAIN_TRUSTSW *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DS_DOMAIN_TRUSTSW *,ulong (*)(void *),&NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_DS_DOMAIN_TRUSTSW *,_DS_DOMAIN_TRUSTSW *,0,std::nullptr_t>>(void)
0x180018057  jmp     short loc_180017FEE
0x180018059  xor     ebx, ebx
0x18001805b  cmp     [rbp+57h+DomainCount], ebx
0x18001805e  jbe     short loc_180018086
0x180018060  test    edi, edi
0x180018062  jnz     short loc_180018086
0x180018064  mov     rdx, [rbp+57h+Domains]
0x180018068  mov     eax, ebx
0x18001806a  imul    rcx, rax, 38h ; '8'
0x18001806e  mov     rdx, [rcx+rdx+8]; pName2
0x180018073  mov     rcx, [rbp+57h+pName1]; pName1
0x180018077  call    cs:__imp_DnsNameCompare_W
0x18001807d  inc     ebx
0x18001807f  mov     edi, eax
0x180018081  cmp     ebx, [rbp+57h+DomainCount]
0x180018084  jb      short loc_180018060
0x180018086  lea     rcx, [rbp+57h+Domains]
0x18001808a  call    ??1?$unique_storage@U?$resource_policy@PEAU_DS_DOMAIN_TRUSTSW@@P6AKPEAX@Z$1?NetApiBufferFree@@YAK0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_DS_DOMAIN_TRUSTSW *,ulong (*)(void *),&NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_DS_DOMAIN_TRUSTSW *,_DS_DOMAIN_TRUSTSW *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DS_DOMAIN_TRUSTSW *,ulong (*)(void *),&NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_DS_DOMAIN_TRUSTSW *,_DS_DOMAIN_TRUSTSW *,0,std::nullptr_t>>(void)
0x18001808f  lea     rcx, [rbp+57h+pName1]
0x180018093  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180018098  jmp     short loc_1800180CE
0x18001809a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x1800180a1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x1800180a6  test    al, al
0x1800180a8  jz      short loc_1800180CE
0x1800180aa  test    byte ptr cs:Microsoft_Windows_User_Profiles_GeneralEnableBits, 8
0x1800180b1  jz      short loc_1800180CE
0x1800180b3  lea     rax, [rbp+57h+Domains]
0x1800180b7  mov     r9d, 1
0x1800180bd  lea     rdx, EVENT_CHECK_XFOREST_LOGON_POLICY_ENABLED
0x1800180c4  mov     [rsp+0A0h+var_80], rax
0x1800180c9  call    McGenEventWrite_EtwEventWriteTransfer
0x1800180ce  xor     eax, eax
0x1800180d0  test    edi, edi
0x1800180d2  setz    al
0x1800180d5  mov     rcx, [rbp+57h+var_10]
0x1800180d9  xor     rcx, rsp; StackCookie
0x1800180dc  call    __security_check_cookie
0x1800180e1  lea     r11, [rsp+0A0h+var_s0]
0x1800180e9  mov     rbx, [r11+18h]
0x1800180ed  mov     rdi, [r11+20h]
0x1800180f1  mov     rsp, r11
0x1800180f4  pop     rbp
0x1800180f5  retn
```
