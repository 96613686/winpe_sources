# CAccountManager::SetEnrolledFactorState(_WINBIO_IDENTITY *,uint,ulong,bool,bool *)

- ea: `0x180046664`
- end: `0x180046aa2`
- name: `?SetEnrolledFactorState@CAccountManager@@SAJPEAU_WINBIO_IDENTITY@@IK_NPEA_N@Z`
- size: `1086`
- prototype: `__int64 __usercall@<rax>(struct _WINBIO_IDENTITY *this@<rcx>, unsigned int@<edx>, unsigned int@<r8d>, bool@<r9b>, bool *)`
- caller_count: `8`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180049970`
- `0x18004a2f0`
- `0x180053ff0`
- `0x180063224`
- `0x18007330c`
- `0x180073538`
- `0x18008f340`
- `0x1800907a0`

## callees

- `0x18000986c`
- `0x18000a794`
- `0x1800119c4`
- `0x180011d90`
- `0x180014110`
- `0x18001451c`
- `0x180014854`
- `0x180014894`
- `0x180016d38`
- `0x180028af0`
- `0x18002b2f8`
- `0x18002b7c0`
- `0x180033378`
- `0x180035d78`
- `0x18003f2dc`
- `0x180046664`
- `0x18005388c`
- `0x180057908`
- `0x180058458`
- `0x180068f60`
- `0x18006e4c4`
- `0x180077c7c`
- `0x180077d64`
- `0x1800be068`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800467e5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180046a5e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800467e5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180046a5e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180046928`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004695a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004699c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180046928`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004695a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004699c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800467b8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800467b8`

## string_xrefs

- `0x1800466ba`: `onecore\ds\security\biometrics\service\server\accountmanager.cpp`
- `0x180046749`: `onecore\ds\security\biometrics\service\server\accountmanager.cpp`
- `0x1800467ce`: `onecore\ds\security\biometrics\service\server\accountmanager.cpp`
- `0x180046821`: `onecore\ds\security\biometrics\service\server\accountmanager.cpp`
- `0x1800469cd`: `onecore\ds\security\biometrics\service\server\accountmanager.cpp`
- `0x180046a1a`: `onecore\ds\security\biometrics\service\server\accountmanager.cpp`
- `0x180046a48`: `onecore\ds\security\biometrics\service\server\accountmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CAccountManager::SetEnrolledFactorState(
        struct _WINBIO_IDENTITY *this,
        unsigned int a2,
        BOOL a3,
        char a4,
        bool *a5)
{
  unsigned int v8; // edx
  int v9; // ebx
  char v10; // r12
  __int64 v11; // rdx
  int WinBioRegistryLocation; // eax
  __int64 v13; // rdx
  struct CAccountManager *v14; // rax
  const WCHAR *v15; // rax
  PHKEY phkResult; // r8
  unsigned int Key; // eax
  unsigned int *v18; // r9
  __int64 v19; // rdx
  int EnrolledFactorsCommon; // eax
  __int64 v21; // rdx
  unsigned int *v22; // r9
  char v23; // r13
  int v24; // ecx
  int v25; // edx
  int v26; // ecx
  WINBIO_IDENTITY_TYPE Type; // eax
  CAccountManager *v28; // rcx
  int v29; // eax
  CAccountManager *v30; // rax
  int refreshed; // eax
  wil::details::in1diag3 *v32; // rcx
  __int64 v33; // rdx
  CAccountManager *v34; // rcx
  int v35; // eax
  CAccountManager *v36; // rax
  int dwOptions; // [rsp+20h] [rbp-61h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-61h]
  __int64 v40; // [rsp+50h] [rbp-31h] BYREF
  char v41; // [rsp+58h] [rbp-29h]
  struct _WINBIO_IDENTITY v42; // [rsp+5Ch] [rbp-25h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+57h]

  v41 = a4;
  v9 = winbio::ValidateIdentity((winbio *)this, 0, a3);
  v10 = 0;
  if ( v9 >= 0 )
  {
    v9 = winbio::ValidateFactor((winbio *)a2, v8);
    if ( v9 < 0 )
    {
      v11 = 346;
      goto LABEL_3;
    }
    if ( !a5 )
    {
      v9 = -2147467261;
      v11 = 347;
      goto LABEL_3;
    }
    *a5 = 0;
    *(_OWORD *)&v42.Value.AccountSid.Data[12] = 0;
    *(__m128i *)&v42.Value.AccountSid.Data[28] = _mm_load_si128((const __m128i *)&_xmm);
    *(_WORD *)&v42.Value.AccountSid.Data[12] = 0;
    WinBioRegistryLocation = GetWinBioRegistryLocation((__int64)&v42.Value.AccountSid.Data[12]);
    v9 = WinBioRegistryLocation;
    if ( WinBioRegistryLocation < 0 )
    {
      v13 = 351;
LABEL_12:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\accountmanager.cpp",
        (const char *)(unsigned int)WinBioRegistryLocation,
        dwOptions);
LABEL_64:
      std::wstring::_Tidy_deallocate(&v42.Value.AccountSid.Data[12]);
      return (unsigned int)v9;
    }
    std::wstring::append(&v42.Value.AccountSid.Data[12], L"AccountInfo\\");
    WinBioRegistryLocation = IdentityToRegPath(this, &v42.Value.AccountSid.Data[12]);
    v9 = WinBioRegistryLocation;
    if ( WinBioRegistryLocation < 0 )
    {
      v13 = 354;
      goto LABEL_12;
    }
    v14 = CAccountManager::Instance();
    winbio::lockable_object::lock_exclusive(v14, &v42.Value.AccountSid.Data[4]);
    *(_QWORD *)&v42.Value.Null = 0;
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&v42.Value);
    v15 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v42.Value.AccountSid.Data[12]);
    Key = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v15, 0, 0, 0, 0xF003Fu, 0, phkResult, 0);
    if ( Key )
    {
      v19 = 360;
LABEL_15:
      v9 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v19,
             (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\accountmanager.cpp",
             (const char *)Key,
             dwOptionsa);
LABEL_16:
      if ( *(_QWORD *)&v42.Value.Null )
        RegCloseKey(*(HKEY *)&v42.Value.Null);
      Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockExclusive *)&v42.Value.AccountSid.Data[4]);
      goto LABEL_64;
    }
    v40 = 0;
    v42.Type = 0;
    EnrolledFactorsCommon = winbio::GetEnrolledFactorsCommon(
                              (winbio *)this,
                              (struct _WINBIO_IDENTITY *)((char *)&v40 + 4),
                              (unsigned int *)&v40,
                              v18);
    v9 = EnrolledFactorsCommon;
    if ( EnrolledFactorsCommon < 0 )
    {
      v21 = 368;
LABEL_21:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v21,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\accountmanager.cpp",
        (const char *)(unsigned int)EnrolledFactorsCommon,
        dwOptionsa);
      goto LABEL_16;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_EssFprPeripherals>::GetImpl'::`2'::impl) )
    {
      EnrolledFactorsCommon = winbio::GetEnrolledFactorsForIdentity((winbio *)this, &v42, (unsigned int *)&v40, v22);
      v9 = EnrolledFactorsCommon;
      if ( EnrolledFactorsCommon < 0 )
      {
        v21 = 373;
        goto LABEL_21;
      }
    }
    v23 = 0;
    v24 = HIDWORD(v40);
    *a5 = (a2 & HIDWORD(v40)) != 0;
    if ( v41 )
    {
      HIDWORD(v40) = a2 | v24;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_EssFprPeripherals>::GetImpl'::`2'::impl) )
      {
        if ( !a3 )
        {
          v42.Type |= a2;
          goto LABEL_43;
        }
      }
      else if ( !a3 )
      {
        goto LABEL_43;
      }
      LODWORD(v40) = a2 | v40;
    }
    else
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_EssFprPeripherals>::GetImpl'::`2'::impl) )
      {
        v25 = ~a2;
        v26 = v40;
        Type = v42.Type;
        if ( a3 )
        {
          v26 = v25 & v40;
          LODWORD(v40) = v25 & v40;
        }
        else
        {
          Type = v25 & v42.Type;
          v42.Type &= v25;
        }
        HIDWORD(v40) = v26 | Type;
      }
      else
      {
        HIDWORD(v40) &= ~a2;
        CHardwareManager::Instance();
        if ( !CHardwareManager::IsPeripheralsWithESSChangeDetected() || a3 )
          LODWORD(v40) = ~a2 & v40;
        else
          HIDWORD(v40) |= v40;
      }
      if ( HIDWORD(v40) )
        v10 = 1;
      else
        v23 = 1;
    }
LABEL_43:
    Key = RegSetValueExW(*(HKEY *)&v42.Value.Null, L"EnrolledFactors", 0, 4u, (const BYTE *)&v40 + 4, 4u);
    if ( Key )
    {
      v19 = 453;
      goto LABEL_15;
    }
    Key = RegSetValueExW(*(HKEY *)&v42.Value.Null, L"VirtualSecureModeFactors", 0, 4u, (const BYTE *)&v40, 4u);
    if ( Key )
    {
      v19 = 454;
      goto LABEL_15;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_EssFprPeripherals>::GetImpl'::`2'::impl) )
    {
      Key = RegSetValueExW(*(HKEY *)&v42.Value.Null, L"NonVsmFactors", 0, 4u, (const BYTE *)&v42, 4u);
      if ( Key )
      {
        v19 = 457;
        goto LABEL_15;
      }
    }
    if ( v23 )
    {
      CAccountManager::Instance();
      v29 = CAccountManager::DeleteRegAccount(v28, this);
      if ( v29 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1CE,
          (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\accountmanager.cpp",
          (const char *)(unsigned int)v29,
          dwOptionsa);
      v30 = CAccountManager::Instance();
      refreshed = CAccountManager::RefreshPolicyCache(v30);
      v32 = retaddr;
      if ( refreshed >= 0 )
        goto LABEL_61;
      v33 = 463;
    }
    else
    {
      if ( !v10 )
        goto LABEL_61;
      CAccountManager::Instance();
      v35 = CAccountManager::DeleteRegAccountPolicy(v34, this, a2);
      if ( v35 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1D3,
          (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\accountmanager.cpp",
          (const char *)(unsigned int)v35,
          dwOptionsa);
      v36 = CAccountManager::Instance();
      refreshed = CAccountManager::RefreshPolicyCache(v36);
      v32 = retaddr;
      if ( refreshed >= 0 )
        goto LABEL_61;
      v33 = 468;
    }
    wil::details::in1diag3::_Log_Hr(
      v32,
      (void *)v33,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\accountmanager.cpp",
      (const char *)(unsigned int)refreshed,
      dwOptionsa);
LABEL_61:
    if ( *(_QWORD *)&v42.Value.Null )
      RegCloseKey(*(HKEY *)&v42.Value.Null);
    Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockExclusive *)&v42.Value.AccountSid.Data[4]);
    v9 = 0;
    goto LABEL_64;
  }
  v11 = 345;
LABEL_3:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v11,
    (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\accountmanager.cpp",
    (const char *)(unsigned int)v9,
    dwOptions);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180046664  mov     [rsp-8+arg_10], rbx
0x180046669  push    rbp
0x18004666a  push    rsi
0x18004666b  push    rdi
0x18004666c  push    r12
0x18004666e  push    r13
0x180046670  push    r14
0x180046672  push    r15
0x180046674  lea     rbp, [rsp-1Fh]
0x180046679  sub     rsp, 0A0h
0x180046680  mov     rax, cs:__security_cookie
0x180046687  xor     rax, rsp
0x18004668a  mov     [rbp+4Fh+var_40], rax
0x18004668e  mov     [rbp+4Fh+var_78], r9b
0x180046692  mov     esi, r8d
0x180046695  mov     edi, edx
0x180046697  mov     r14, rcx
0x18004669a  mov     r15, [rbp+4Fh+arg_20]
0x18004669e  xor     edx, edx; struct _WINBIO_IDENTITY *
0x1800466a0  call    ?ValidateIdentity@winbio@@YAJPEAU_WINBIO_IDENTITY@@_N@Z; winbio::ValidateIdentity(_WINBIO_IDENTITY *,bool)
0x1800466a5  mov     ebx, eax
0x1800466a7  xor     r12d, r12d
0x1800466aa  test    eax, eax
0x1800466ac  jns     short loc_1800466CB
0x1800466ae  mov     edx, 159h; void *
0x1800466b3  mov     rcx, [rbp+57h]; this
0x1800466b7  mov     r9d, ebx; char *
0x1800466ba  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\biometrics\\serv"...
0x1800466c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800466c6  jmp     loc_180046A79
0x1800466cb  mov     ecx, edi; this
0x1800466cd  call    ?ValidateFactor@winbio@@YAJI@Z; winbio::ValidateFactor(uint)
0x1800466d2  mov     ebx, eax
0x1800466d4  test    eax, eax
0x1800466d6  jns     short loc_1800466DF
0x1800466d8  mov     edx, 15Ah
0x1800466dd  jmp     short loc_1800466B3
0x1800466df  test    r15, r15
0x1800466e2  jnz     short loc_1800466F0
0x1800466e4  mov     ebx, 80004003h
0x1800466e9  mov     edx, 15Bh
0x1800466ee  jmp     short loc_1800466B3
0x1800466f0  mov     [r15], r12b
0x1800466f3  xorps   xmm0, xmm0
0x1800466f6  movups  [rbp+4Fh+var_60], xmm0
0x1800466fa  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180046702  movdqu  [rbp+4Fh+var_50], xmm1
0x180046707  mov     word ptr [rbp+4Fh+var_60], r12w
0x18004670c  lea     rcx, [rbp+4Fh+var_60]
0x180046710  call    ?GetWinBioRegistryLocation@@YAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetWinBioRegistryLocation(std::wstring *)
0x180046715  mov     ebx, eax
0x180046717  test    eax, eax
0x180046719  jns     short loc_180046722
0x18004671b  mov     edx, 15Fh
0x180046720  jmp     short loc_180046749
0x180046722  lea     rdx, aAccountinfo; "AccountInfo\\"
0x180046729  lea     rcx, [rbp+4Fh+var_60]
0x18004672d  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180046732  lea     rdx, [rbp+4Fh+var_60]
0x180046736  mov     rcx, r14
0x180046739  call    IdentityToRegPath
0x18004673e  mov     ebx, eax
0x180046740  test    eax, eax
0x180046742  jns     short loc_180046761
0x180046744  mov     edx, 162h; void *
0x180046749  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\biometrics\\serv"...
0x180046750  mov     r9d, eax; char *
0x180046753  mov     rcx, [rbp+57h]; this
0x180046757  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004675c  jmp     loc_180046A70
0x180046761  call    ?Instance@CAccountManager@@CAAEAV1@XZ; CAccountManager::Instance(void)
0x180046766  lea     rdx, [rbp+4Fh+var_68]
0x18004676a  mov     rcx, rax
0x18004676d  call    ?lock_exclusive@lockable_object@winbio@@QEBA?AVSyncLockExclusive@Details@Wrappers@WRL@Microsoft@@XZ; winbio::lockable_object::lock_exclusive(void)
0x180046772  nop
0x180046773  mov     [rbp+4Fh+hKey], r12
0x180046777  lea     rcx, [rbp+4Fh+hKey]
0x18004677b  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180046780  mov     r8, rax
0x180046783  lea     rcx, [rbp+4Fh+var_60]
0x180046787  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004678c  mov     rdx, rax; lpSubKey
0x18004678f  mov     [rsp+0D0h+lpdwDisposition], r12; lpdwDisposition
0x180046794  mov     [rsp+0D0h+phkResult], r8; phkResult
0x180046799  mov     [rsp+0D0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x18004679e  mov     [rsp+0D0h+samDesired], 0F003Fh; samDesired
0x1800467a6  mov     [rsp+0D0h+dwOptions], r12d; int
0x1800467ab  xor     r9d, r9d; lpClass
0x1800467ae  xor     r8d, r8d; Reserved
0x1800467b1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800467b8  call    cs:__imp_RegCreateKeyExW
0x1800467be  test    eax, eax
0x1800467c0  jz      short loc_1800467FA
0x1800467c2  mov     edx, 168h; void *
0x1800467c7  mov     rcx, [rbp+57h]; this
0x1800467cb  mov     r9d, eax; char *
0x1800467ce  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\biometrics\\serv"...
0x1800467d5  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800467da  mov     ebx, eax
0x1800467dc  mov     rcx, [rbp+4Fh+hKey]; hKey
0x1800467e0  test    rcx, rcx
0x1800467e3  jz      short loc_1800467EC
0x1800467e5  call    cs:__imp_RegCloseKey
0x1800467eb  nop
0x1800467ec  lea     rcx, [rbp+4Fh+var_68]; this
0x1800467f0  call    ?InternalUnlock@SyncLockExclusive@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock(void)
0x1800467f5  jmp     loc_180046A70
0x1800467fa  mov     dword ptr [rbp+4Fh+var_80+4], r12d
0x1800467fe  mov     dword ptr [rbp+4Fh+var_80], r12d
0x180046802  mov     dword ptr [rbp+4Fh+var_74], r12d
0x180046806  lea     r8, [rbp+4Fh+var_80]; unsigned int *
0x18004680a  lea     rdx, [rbp+4Fh+var_80+4]; struct _WINBIO_IDENTITY *
0x18004680e  mov     rcx, r14; this
0x180046811  call    ?GetEnrolledFactorsCommon@winbio@@YAJPEAU_WINBIO_IDENTITY@@PEAI1@Z; winbio::GetEnrolledFactorsCommon(_WINBIO_IDENTITY *,uint *,uint *)
0x180046816  mov     ebx, eax
0x180046818  test    eax, eax
0x18004681a  jns     short loc_180046836
0x18004681c  mov     edx, 170h; void *
0x180046821  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\biometrics\\serv"...
0x180046828  mov     r9d, eax; char *
0x18004682b  mov     rcx, [rbp+57h]; this
0x18004682f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180046834  jmp     short loc_1800467DC
0x180046836  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EssFprPeripherals@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EssFprPeripherals@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals> `wil::Feature<__WilFeatureTraits_Feature_EssFprPeripherals>::GetImpl(void)'::`2'::impl
0x18004683d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EssFprPeripherals@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals>::__private_IsEnabled(void)
0x180046842  test    al, al
0x180046844  jz      short loc_180046863
0x180046846  lea     r8, [rbp+4Fh+var_80]; unsigned int *
0x18004684a  lea     rdx, [rbp+4Fh+var_74]; struct _WINBIO_IDENTITY *
0x18004684e  mov     rcx, r14; this
0x180046851  call    ?GetEnrolledFactorsForIdentity@winbio@@YAJPEAU_WINBIO_IDENTITY@@PEAI1@Z; winbio::GetEnrolledFactorsForIdentity(_WINBIO_IDENTITY *,uint *,uint *)
0x180046856  mov     ebx, eax
0x180046858  test    eax, eax
0x18004685a  jns     short loc_180046863
0x18004685c  mov     edx, 175h
0x180046861  jmp     short loc_180046821
0x180046863  mov     r13b, r12b
0x180046866  mov     ecx, dword ptr [rbp+4Fh+var_80+4]
0x180046869  test    ecx, edi
0x18004686b  setnz   al
0x18004686e  mov     [r15], al
0x180046871  cmp     [rbp+4Fh+var_78], r12b
0x180046875  jz      short loc_1800468A0
0x180046877  or      ecx, edi
0x180046879  mov     dword ptr [rbp+4Fh+var_80+4], ecx
0x18004687c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EssFprPeripherals@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EssFprPeripherals@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals> `wil::Feature<__WilFeatureTraits_Feature_EssFprPeripherals>::GetImpl(void)'::`2'::impl
0x180046883  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EssFprPeripherals@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals>::__private_IsEnabled(void)
0x180046888  test    al, al
0x18004688a  jz      short loc_180046896
0x18004688c  cmp     esi, 1
0x18004688f  jz      short loc_18004689B
0x180046891  or      dword ptr [rbp+4Fh+var_74], edi
0x180046894  jmp     short loc_180046905
0x180046896  cmp     esi, 1
0x180046899  jnz     short loc_180046905
0x18004689b  or      dword ptr [rbp+4Fh+var_80], edi
0x18004689e  jmp     short loc_180046905
0x1800468a0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EssFprPeripherals@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EssFprPeripherals@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals> `wil::Feature<__WilFeatureTraits_Feature_EssFprPeripherals>::GetImpl(void)'::`2'::impl
0x1800468a7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EssFprPeripherals@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals>::__private_IsEnabled(void)
0x1800468ac  test    al, al
0x1800468ae  jz      short loc_1800468D2
0x1800468b0  mov     edx, edi
0x1800468b2  not     edx
0x1800468b4  mov     ecx, dword ptr [rbp+4Fh+var_80]
0x1800468b7  mov     eax, dword ptr [rbp+4Fh+var_74]
0x1800468ba  cmp     esi, 1
0x1800468bd  jnz     short loc_1800468C6
0x1800468bf  and     ecx, edx
0x1800468c1  mov     dword ptr [rbp+4Fh+var_80], ecx
0x1800468c4  jmp     short loc_1800468CB
0x1800468c6  and     eax, edx
0x1800468c8  mov     dword ptr [rbp+4Fh+var_74], eax
0x1800468cb  or      eax, ecx
0x1800468cd  mov     dword ptr [rbp+4Fh+var_80+4], eax
0x1800468d0  jmp     short loc_1800468F7
0x1800468d2  mov     ebx, edi
0x1800468d4  not     ebx
0x1800468d6  and     dword ptr [rbp+4Fh+var_80+4], ebx
0x1800468d9  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x1800468de  call    ?IsPeripheralsWithESSChangeDetected@CHardwareManager@@SA_NXZ; CHardwareManager::IsPeripheralsWithESSChangeDetected(void)
0x1800468e3  test    al, al
0x1800468e5  jz      short loc_1800468F4
0x1800468e7  cmp     esi, 1
0x1800468ea  jz      short loc_1800468F4
0x1800468ec  mov     eax, dword ptr [rbp+4Fh+var_80]
0x1800468ef  or      dword ptr [rbp+4Fh+var_80+4], eax
0x1800468f2  jmp     short loc_1800468F7
0x1800468f4  and     dword ptr [rbp+4Fh+var_80], ebx
0x1800468f7  cmp     dword ptr [rbp+4Fh+var_80+4], 0
0x1800468fb  jnz     short loc_180046902
0x1800468fd  mov     r13b, 1
0x180046900  jmp     short loc_180046905
0x180046902  mov     r12b, 1
0x180046905  mov     ebx, 4
0x18004690a  mov     [rsp+0D0h+samDesired], ebx; cbData
0x18004690e  lea     rax, [rbp+4Fh+var_80+4]
0x180046912  mov     qword ptr [rsp+0D0h+dwOptions], rax; lpData
0x180046917  mov     r9d, ebx; dwType
0x18004691a  xor     r8d, r8d; Reserved
0x18004691d  lea     rdx, aEnrolledfactor; "EnrolledFactors"
0x180046924  mov     rcx, [rbp+4Fh+hKey]; hKey
0x180046928  call    cs:__imp_RegSetValueExW
0x18004692e  test    eax, eax
0x180046930  jz      short loc_18004693C
0x180046932  mov     edx, 1C5h
0x180046937  jmp     loc_1800467C7
0x18004693c  mov     [rsp+0D0h+samDesired], ebx; cbData
0x180046940  lea     rax, [rbp+4Fh+var_80]
0x180046944  mov     qword ptr [rsp+0D0h+dwOptions], rax; int
0x180046949  mov     r9d, ebx; dwType
0x18004694c  xor     r8d, r8d; Reserved
0x18004694f  lea     rdx, aVirtualsecurem_0; "VirtualSecureModeFactors"
0x180046956  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18004695a  call    cs:__imp_RegSetValueExW
0x180046960  test    eax, eax
0x180046962  jz      short loc_18004696E
0x180046964  mov     edx, 1C6h
0x180046969  jmp     loc_1800467C7
0x18004696e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EssFprPeripherals@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EssFprPeripherals@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals> `wil::Feature<__WilFeatureTraits_Feature_EssFprPeripherals>::GetImpl(void)'::`2'::impl
0x180046975  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EssFprPeripherals@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals>::__private_IsEnabled(void)
0x18004697a  test    al, al
0x18004697c  jz      short loc_1800469B0
0x18004697e  mov     [rsp+0D0h+samDesired], ebx; cbData
0x180046982  lea     rax, [rbp+4Fh+var_74]
0x180046986  mov     qword ptr [rsp+0D0h+dwOptions], rax; lpData
0x18004698b  mov     r9d, ebx; dwType
0x18004698e  xor     r8d, r8d; Reserved
0x180046991  lea     rdx, aNonvsmfactors; "NonVsmFactors"
0x180046998  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18004699c  call    cs:__imp_RegSetValueExW
0x1800469a2  test    eax, eax
0x1800469a4  jz      short loc_1800469B0
0x1800469a6  mov     edx, 1C9h
0x1800469ab  jmp     loc_1800467C7
0x1800469b0  test    r13b, r13b
0x1800469b3  jz      short loc_1800469FA
0x1800469b5  call    ?Instance@CAccountManager@@CAAEAV1@XZ; CAccountManager::Instance(void)
0x1800469ba  mov     rdx, r14; struct _WINBIO_IDENTITY *
0x1800469bd  call    ?DeleteRegAccount@CAccountManager@@AEAAJPEAU_WINBIO_IDENTITY@@@Z; CAccountManager::DeleteRegAccount(_WINBIO_IDENTITY *)
0x1800469c2  mov     rcx, [rbp+57h]; this
0x1800469c6  test    eax, eax
0x1800469c8  jns     short loc_1800469DE
0x1800469ca  mov     r9d, eax; char *
0x1800469cd  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\biometrics\\serv"...
0x1800469d4  mov     edx, 1CEh; void *
0x1800469d9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800469de  call    ?Instance@CAccountManager@@CAAEAV1@XZ; CAccountManager::Instance(void)
0x1800469e3  mov     rcx, rax; this
0x1800469e6  call    ?RefreshPolicyCache@CAccountManager@@AEAAJXZ; CAccountManager::RefreshPolicyCache(void)
0x1800469eb  mov     rcx, [rbp+57h]
0x1800469ef  test    eax, eax
0x1800469f1  jns     short loc_180046A55
0x1800469f3  mov     edx, 1CFh
0x1800469f8  jmp     short loc_180046A45
0x1800469fa  test    r12b, r12b
0x1800469fd  jz      short loc_180046A55
0x1800469ff  call    ?Instance@CAccountManager@@CAAEAV1@XZ; CAccountManager::Instance(void)
0x180046a04  mov     r8d, edi; unsigned int
0x180046a07  mov     rdx, r14; struct _WINBIO_IDENTITY *
0x180046a0a  call    ?DeleteRegAccountPolicy@CAccountManager@@AEAAJPEAU_WINBIO_IDENTITY@@I@Z; CAccountManager::DeleteRegAccountPolicy(_WINBIO_IDENTITY *,uint)
0x180046a0f  mov     rcx, [rbp+57h]; this
0x180046a13  test    eax, eax
0x180046a15  jns     short loc_180046A2B
0x180046a17  mov     r9d, eax; char *
0x180046a1a  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\biometrics\\serv"...
0x180046a21  mov     edx, 1D3h; void *
0x180046a26  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180046a2b  call    ?Instance@CAccountManager@@CAAEAV1@XZ; CAccountManager::Instance(void)
0x180046a30  mov     rcx, rax; this
0x180046a33  call    ?RefreshPolicyCache@CAccountManager@@AEAAJXZ; CAccountManager::RefreshPolicyCache(void)
0x180046a38  mov     rcx, [rbp+57h]; this
0x180046a3c  test    eax, eax
0x180046a3e  jns     short loc_180046A55
0x180046a40  mov     edx, 1D4h; void *
0x180046a45  mov     r9d, eax; char *
0x180046a48  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\biometrics\\serv"...
0x180046a4f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180046a54  nop
0x180046a55  mov     rcx, [rbp+4Fh+hKey]; hKey
0x180046a59  test    rcx, rcx
0x180046a5c  jz      short loc_180046A65
0x180046a5e  call    cs:__imp_RegCloseKey
0x180046a64  nop
0x180046a65  lea     rcx, [rbp+4Fh+var_68]; this
0x180046a69  call    ?InternalUnlock@SyncLockExclusive@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock(void)
0x180046a6e  xor     ebx, ebx
0x180046a70  lea     rcx, [rbp+4Fh+var_60]
0x180046a74  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180046a79  mov     eax, ebx
0x180046a7b  mov     rcx, [rbp+4Fh+var_40]
0x180046a7f  xor     rcx, rsp; StackCookie
0x180046a82  call    __security_check_cookie
0x180046a87  mov     rbx, [rsp+0D0h+arg_10]
0x180046a8f  add     rsp, 0A0h
0x180046a96  pop     r15
0x180046a98  pop     r14
0x180046a9a  pop     r13
0x180046a9c  pop     r12
0x180046a9e  pop     rdi
0x180046a9f  pop     rsi
  ... truncated ...
```
