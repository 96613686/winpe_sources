# VaultCDSCleanupStaleVaults(void)

- ea: `0x18001dbe0`
- end: `0x18001e4e9`
- name: `?VaultCDSCleanupStaleVaults@@YAJXZ`
- size: `2313`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `29`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18001d7b4`

## callees

- `0x180003140`
- `0x180012210`
- `0x18001cea8`
- `0x18001dbe0`
- `0x18001eda0`
- `0x18001f668`
- `0x180021468`
- `0x180027340`
- `0x180030d14`
- `0x180031804`
- `0x1800318e8`
- `0x1800329f0`
- `0x180032a08`
- `0x1800357ac`
- `0x180035880`
- `0x180037640`
- `0x180037b0c`
- `0x180038730`
- `0x180038978`
- `0x180038a28`
- `0x180038c6c`
- `0x180038d64`
- `0x18003a580`
- `0x18003b7b0`
- `0x1800428f4`
- `0x180045600`
- `0x180045874`
- `0x18004b430`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18001dccb`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18001dccb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001dc40`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001dc40`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001dc57`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001dc57`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001df8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001df8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001df38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001df38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001dc2a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001dc2a`

## string_xrefs

- `0x18001dc23`: `Windows.Internal.Security.Authentication.Web.TokenBrokerInternal`
- `0x18001dc71`: `onecore\ds\security\vault\vaultserver\vaultcds.cpp`
- `0x18001dce1`: `onecore\ds\security\vault\vaultserver\vaultcds.cpp`
- `0x18001dd6a`: `onecore\ds\security\vault\vaultserver\vaultcds.cpp`
- `0x18001de45`: `onecore\ds\security\vault\vaultserver\vaultcds.cpp`
- `0x18001dee5`: `onecore\ds\security\vault\vaultserver\vaultcds.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
__int64 VaultCDSCleanupStaleVaults(void)
{
  HRESULT StringReference; // eax
  int ActivationFactory; // eax
  unsigned int v2; // ebx
  HRESULT v3; // eax
  CVaultMgr *v4; // rcx
  unsigned int UserVaultManager; // eax
  unsigned int v6; // r8d
  int DefaultAccount; // eax
  __int64 (__fastcall **v8)(__int64, GUID *, __int64 **); // rax
  int v9; // eax
  __int64 v10; // rax
  int v11; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 v13; // rax
  __int64 v14; // rcx
  unsigned int v15; // eax
  __int64 v16; // rdx
  unsigned int v17; // r8d
  HLOCAL v18; // rcx
  __int64 v19; // rdx
  _BYTE *v20; // rax
  CUserVault **v21; // r14
  int v22; // r15d
  __m128i si128; // xmm6
  unsigned int VaultStore; // eax
  unsigned int v25; // r8d
  _BYTE *v26; // rdi
  unsigned int v27; // eax
  unsigned int v28; // r8d
  __int64 v29; // rcx
  _BYTE *v30; // rax
  __int64 v31; // rcx
  _BYTE *v32; // rax
  unsigned int v33; // eax
  unsigned int v34; // r8d
  __int64 *v35; // rax
  __int64 v36; // rbx
  __int64 v37; // rsi
  __int64 v38; // rcx
  _BYTE *v39; // rax
  __int64 v40; // rax
  _BYTE *v41; // rcx
  HLOCAL v42; // rcx
  __int64 v43; // rax
  _BYTE *v44; // rcx
  _BYTE *v45; // rax
  unsigned int i; // ebx
  const struct _GUID *v47; // rbx
  struct _GUID *v48; // rdi
  unsigned int v49; // eax
  CUserVault **v50; // rax
  int dwAuthnLevel; // [rsp+20h] [rbp-E0h]
  int dwAuthnLevela; // [rsp+20h] [rbp-E0h]
  unsigned int dwAuthnLevelb; // [rsp+20h] [rbp-E0h]
  unsigned int v55; // [rsp+40h] [rbp-C0h] BYREF
  __int64 (__fastcall ***v56)(__int64, GUID *, __int64 **); // [rsp+48h] [rbp-B8h] BYREF
  IUnknown *pProxy; // [rsp+50h] [rbp-B0h] BYREF
  __int64 *v58; // [rsp+58h] [rbp-A8h] BYREF
  HSTRING v59; // [rsp+60h] [rbp-A0h] BYREF
  void (__fastcall *v60)(HLOCAL, __int64); // [rsp+68h] [rbp-98h]
  HLOCAL v61; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v62; // [rsp+78h] [rbp-88h]
  struct _GUID *v63[2]; // [rsp+80h] [rbp-80h] BYREF
  struct _GUID *v64; // [rsp+90h] [rbp-70h]
  __int64 (__fastcall *v65)(_QWORD); // [rsp+98h] [rbp-68h] BYREF
  CUserVaultMgr *v66; // [rsp+A0h] [rbp-60h] BYREF
  int v67; // [rsp+A8h] [rbp-58h]
  __int64 v68; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v69; // [rsp+B8h] [rbp-48h] BYREF
  int v70; // [rsp+C0h] [rbp-40h]
  void (*v71)(void); // [rsp+C8h] [rbp-38h]
  HLOCAL hMem; // [rsp+D0h] [rbp-30h] BYREF
  unsigned int v73; // [rsp+D8h] [rbp-28h]
  int v74; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD v75[2]; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v76[24]; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v77; // [rsp+110h] [rbp+10h]
  __int64 v78; // [rsp+118h] [rbp+18h]
  char v79[8]; // [rsp+120h] [rbp+20h] BYREF
  __int128 hstringHeader; // [rsp+128h] [rbp+28h] BYREF
  __m128i hstringHeader_16; // [rsp+138h] [rbp+38h] BYREF
  struct _GUID Buf2; // [rsp+148h] [rbp+48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  pProxy = 0;
  hstringHeader_16.m128i_i64[1] = 0;
  StringReference = WindowsCreateStringReference(
                      L"Windows.Internal.Security.Authentication.Web.TokenBrokerInternal",
                      0x40u,
                      (HSTRING_HEADER *)&hstringHeader,
                      (HSTRING *)&hstringHeader_16.m128i_i64[1]);
  if ( StringReference < 0 )
  {
    RaiseException(StringReference, 1u, 0, 0);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(
                        hstringHeader_16.m128i_i64[1],
                        &GUID_07650a66_66ea_489d_aa90_0dabc75f3567,
                        &pProxy);
  v2 = ActivationFactory;
  hstringHeader_16.m128i_i64[1] = 0;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2EF,
      (unsigned int)"onecore\\ds\\security\\vault\\vaultserver\\vaultcds.cpp",
      (const char *)(unsigned int)ActivationFactory,
      dwAuthnLevel);
    if ( pProxy )
      ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
    return v2;
  }
  v3 = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 2u, 3u, 0, 0x20u);
  v2 = v3;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2FE,
      (unsigned int)"onecore\\ds\\security\\vault\\vaultserver\\vaultcds.cpp",
      (const char *)(unsigned int)v3,
      dwAuthnLevela);
    goto LABEL_115;
  }
  v65 = AutoDereference<IVaultKeyManager>;
  v66 = 0;
  v67 = 0;
  UserVaultManager = CVaultMgr::GetUserVaultManager(v4, 0, &v66, 0, 0);
  if ( UserVaultManager )
  {
    v2 = wil::details::in1diag3::Return_Win32(retaddr, (void *)0x301, v6, (const char *)UserVaultManager, dwAuthnLevelb);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v65);
    goto LABEL_115;
  }
  v56 = 0;
  DefaultAccount = GetDefaultAccount(pProxy, &v56);
  v2 = DefaultAccount;
  if ( DefaultAccount < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x304,
      (unsigned int)"onecore\\ds\\security\\vault\\vaultserver\\vaultcds.cpp",
      (const char *)(unsigned int)DefaultAccount,
      dwAuthnLevelb);
    if ( v56 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, __int64 **)))(*v56)[2])(v56);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v65);
    if ( pProxy )
      ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
    return v2;
  }
  v74 = 0;
  v75[0] = 0;
  v75[1] = 0;
  std::list<std::wstring>::_Alloc_sentinel_and_proxy(v75);
  std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>(v76);
  v77 = 7;
  v78 = 8;
  v74 = 1065353216;
  std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Assign_grow(
    v76,
    16,
    v75[0]);
  if ( v56 )
  {
    v58 = 0;
    v8 = *v56;
    v58 = 0;
    v9 = (*v8)((__int64)v56, &GUID_7b56d6f8_990b_4eb5_94a7_5621f3a8b824, &v58);
    v2 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x30A,
        (unsigned int)"onecore\\ds\\security\\vault\\vaultserver\\vaultcds.cpp",
        (const char *)(unsigned int)v9,
        dwAuthnLevelb);
      if ( v58 )
        (*(void (__fastcall **)(__int64 *))(*v58 + 16))(v58);
      std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(&v74);
      if ( v56 )
        ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, __int64 **)))(*v56)[2])(v56);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v65);
      if ( pProxy )
        ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
      return v2;
    }
    v59 = 0;
    v10 = *v58;
    v59 = 0;
    v11 = (*(__int64 (__fastcall **)(__int64 *, HSTRING *))(v10 + 48))(v58, &v59);
    v2 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x30D,
        (unsigned int)"onecore\\ds\\security\\vault\\vaultserver\\vaultcds.cpp",
        (const char *)(unsigned int)v11,
        dwAuthnLevelb);
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v59);
      wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(&v58);
      std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(&v74);
      wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(&v56);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v65);
      goto LABEL_115;
    }
    StringRawBuffer = WindowsGetStringRawBuffer(v59, 0);
    hstringHeader = 0;
    hstringHeader_16 = 0;
    v13 = std::_WChar_traits<unsigned short>::length(StringRawBuffer);
    std::wstring::_Construct<1,unsigned short const *>(&hstringHeader, v14, v13);
    std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<std::wstring>(
      &v74,
      &Buf2,
      &hstringHeader);
    std::wstring::_Tidy_deallocate(&hstringHeader);
    if ( v59 )
      WindowsDeleteString(v59);
    if ( v58 )
      (*(void (__fastcall **)(__int64 *))(*v58 + 16))(v58);
  }
  hMem = 0;
  v73 = 0;
  v71 = 0;
  v55 = 0;
  v15 = CUserVaultMgr::EnumerateVaults(v66, (struct CUserVault ***)&hMem, &v55);
  if ( v15 )
  {
    v2 = wil::details::in1diag3::Return_Win32(retaddr, (void *)0x315, v17, (const char *)v15, dwAuthnLevelb);
    v18 = hMem;
    if ( hMem )
    {
      v19 = v73;
      if ( v73 )
      {
        v20 = hMem;
        do
        {
          *v20++ = 0;
          --v19;
        }
        while ( v19 );
      }
      if ( v71 )
        v71();
      else
        VaultFreeInternal(v18);
    }
    std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(&v74);
    wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(&v56);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v65);
    goto LABEL_115;
  }
  *(_OWORD *)v63 = 0;
  v64 = 0;
  v21 = (CUserVault **)hMem;
  if ( !v55 )
    goto LABEL_100;
  v22 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  while ( 1 )
  {
    v60 = (void (__fastcall *)(HLOCAL, __int64))AutoDereference<IVaultKeyManager>;
    v61 = 0;
    v62 = 0;
    Buf2 = 0;
    v69 = 0;
    v70 = 0;
    v68 = 0;
    VaultStore = CUserVault::GetVaultStore(v21[v22], (struct IVaultStore **)&v61, 1u);
    if ( VaultStore )
      break;
    v26 = v61;
    v27 = (*(__int64 (__fastcall **)(HLOCAL, struct _GUID *))(*(_QWORD *)v61 + 24LL))(v61, &Buf2);
    if ( v27 )
    {
      wil::details::in1diag3::_Log_Win32(retaddr, (void *)0x323, v28, (const char *)v27, dwAuthnLevelb);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v68);
      if ( !v26 )
        goto LABEL_97;
      v43 = v62;
      if ( v62 )
      {
        v44 = v26;
        do
        {
          *v44++ = 0;
          --v43;
        }
        while ( v43 );
      }
      goto LABEL_84;
    }
    if ( !memcmp_0(&Vault_DefaultVault_ID, &Buf2, 0x10u) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_fc3aaf5bf91a3534f189492db6bbf47b_Traceguids);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v68);
      if ( !v26 )
        goto LABEL_78;
      if ( v62 )
      {
        v29 = v62;
        v30 = v26;
        do
        {
          *v30++ = 0;
          --v29;
        }
        while ( v29 );
      }
      goto LABEL_53;
    }
    if ( !memcmp_0(&Vault_CredmanVault_ID, &Buf2, 0x10u) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_fc3aaf5bf91a3534f189492db6bbf47b_Traceguids);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v68);
      if ( !v26 )
        goto LABEL_78;
      if ( v62 )
      {
        v31 = v62;
        v32 = v26;
        do
        {
          *v32++ = 0;
          --v31;
        }
        while ( v31 );
      }
LABEL_53:
      if ( !v60 )
        goto LABEL_77;
LABEL_54:
      ((void (__fastcall *)(_BYTE *))v60)(v26);
      goto LABEL_78;
    }
    v33 = (*(__int64 (__fastcall **)(_BYTE *, __int64 *))(*(_QWORD *)v26 + 176LL))(v26, &v69);
    if ( v33 )
    {
      wil::details::in1diag3::_Log_Win32(retaddr, (void *)0x334, v34, (const char *)v33, dwAuthnLevelb);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v68);
      if ( !v26 )
        goto LABEL_97;
      v40 = v62;
      if ( v62 )
      {
        v41 = v26;
        do
        {
          *v41++ = 0;
          --v40;
        }
        while ( v40 );
      }
LABEL_84:
      v42 = v26;
      goto LABEL_94;
    }
    std::wstring::wstring(&hstringHeader, v69);
    v35 = (__int64 *)std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::find(
                       &v74,
                       v79,
                       &hstringHeader);
    v36 = v75[0];
    v37 = *v35;
    if ( hstringHeader_16.m128i_i64[1] > 7uLL )
      std::_Deallocate<16>(hstringHeader, 2 * hstringHeader_16.m128i_i64[1] + 2);
    hstringHeader_16 = si128;
    LOWORD(hstringHeader) = 0;
    if ( v37 == v36 )
    {
      if ( v63[1] == v64 )
        std::vector<_GUID>::_Emplace_reallocate<_GUID const &>(v63, v63[1], &Buf2);
      else
        *v63[1]++ = Buf2;
    }
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v68);
    if ( v26 )
    {
      if ( v62 )
      {
        v38 = v62;
        v39 = v26;
        do
        {
          *v39++ = 0;
          --v38;
        }
        while ( v38 );
      }
      if ( !v60 )
      {
LABEL_77:
        VaultFreeInternal(v26);
        goto LABEL_78;
      }
      goto LABEL_54;
    }
LABEL_78:
    if ( ++v22 >= v55 )
      goto LABEL_97;
  }
  wil::details::in1diag3::_Log_Win32(retaddr, (void *)0x31E, v25, (const char *)VaultStore, dwAuthnLevelb);
  CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v68);
  v42 = v61;
  if ( !v61 )
    goto LABEL_97;
  if ( v62 )
  {
    v16 = v62;
    v45 = v61;
    do
    {
      *v45++ = 0;
      --v16;
    }
    while ( v16 );
  }
LABEL_94:
  if ( v60 )
    v60(v42, v16);
  else
    VaultFreeInternal(v42);
LABEL_97:
  if ( v55 )
  {
    for ( i = 0; i < v55; ++i )
      (*(void (__fastcall **)(CUserVault *))(*(_QWORD *)v21[i] + 8LL))(v21[i]);
  }
LABEL_100:
  v47 = v63[0];
  v48 = v63[1];
  if ( v63[0] != v63[1] )
  {
    do
    {
      v49 = CUserVaultMgr::DeleteVault(v66, v47, v17);
      if ( v49 )
        wil::details::in1diag3::_Log_Win32(retaddr, (void *)0x34C, v17, (const char *)v49, dwAuthnLevelb);
      ++v47;
    }
    while ( v47 != v48 );
    v47 = v63[0];
  }
  if ( v47 )
  {
    std::_Deallocate<16>(v47, ((char *)v64 - (char *)v47) & 0xFFFFFFFFFFFFFFF0uLL);
    *(_OWORD *)v63 = 0;
    v64 = 0;
  }
  if ( v21 )
  {
    if ( v73 )
    {
      v16 = v73;
      v50 = v21;
      do
      {
        *(_BYTE *)v50 = 0;
        v50 = (CUserVault **)((char *)v50 + 1);
        --v16;
      }
      while ( v16 );
    }
    if ( v71 )
      ((void (__fastcall *)(CUserVault **, __int64))v71)(v21, v16);
    else
      VaultFreeInternal(v21);
  }
  std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(&v74);
  wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(&v56);
  CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v65);
  v2 = 0;
LABEL_115:
  wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(&pProxy);
  return v2;
}

```

## disassembly

```asm
0x18001dbe0  mov     rax, rsp
0x18001dbe3  push    rbp
0x18001dbe4  push    rbx
0x18001dbe5  push    rsi
0x18001dbe6  push    rdi
0x18001dbe7  push    r13
0x18001dbe9  push    r14
0x18001dbeb  push    r15
0x18001dbed  lea     rbp, [rsp-70h]
0x18001dbf2  sub     rsp, 170h
0x18001dbf9  movaps  xmmword ptr [rax-48h], xmm6
0x18001dbfd  mov     rax, cs:__security_cookie
0x18001dc04  xor     rax, rsp
0x18001dc07  mov     [rbp+0A0h+var_48], rax
0x18001dc0b  xor     r13d, r13d
0x18001dc0e  mov     [rsp+1A0h+pProxy], r13
0x18001dc13  mov     [rbp+0A0h+string], r13
0x18001dc17  lea     r9, [rbp+0A0h+string]; string
0x18001dc1b  lea     r8, [rbp+0A0h+hstringHeader]; hstringHeader
0x18001dc1f  lea     edx, [r13+40h]; length
0x18001dc23  lea     rcx, ?RuntimeClass_Windows_Internal_Security_Authentication_Web_TokenBrokerInternal@@3QBGB; "Windows.Internal.Security.Authenticatio"...
0x18001dc2a  call    cs:__imp_WindowsCreateStringReference
0x18001dc30  test    eax, eax
0x18001dc32  jns     short loc_18001DC47
0x18001dc34  xor     r9d, r9d; lpArguments
0x18001dc37  xor     r8d, r8d; nNumberOfArguments
0x18001dc3a  lea     edx, [r13+1]; dwExceptionFlags
0x18001dc3e  mov     ecx, eax; dwExceptionCode
0x18001dc40  call    cs:__imp_RaiseException
0x18001dc46  int     3; Trap to Debugger
0x18001dc47  lea     r8, [rsp+1A0h+pProxy]
0x18001dc4c  lea     rdx, _GUID_07650a66_66ea_489d_aa90_0dabc75f3567
0x18001dc53  mov     rcx, [rbp+0A0h+string]
0x18001dc57  call    cs:__imp_RoGetActivationFactory
0x18001dc5d  mov     ebx, eax
0x18001dc5f  mov     [rbp+0A0h+string], r13
0x18001dc63  test    eax, eax
0x18001dc65  jns     short loc_18001DC9F
0x18001dc67  mov     rcx, [rbp+0A8h]; this
0x18001dc6e  mov     r9d, eax; char *
0x18001dc71  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\vault\\vaultserv"...
0x18001dc78  mov     edx, 2EFh; void *
0x18001dc7d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001dc82  nop
0x18001dc83  mov     rcx, [rsp+1A0h+pProxy]
0x18001dc88  test    rcx, rcx
0x18001dc8b  jz      short loc_18001DC9A
0x18001dc8d  mov     rax, [rcx]
0x18001dc90  mov     rax, [rax+10h]
0x18001dc94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc99  nop
0x18001dc9a  jmp     loc_18001E4C1
0x18001dc9f  mov     [rsp+1A0h+dwCapabilities], 20h ; ' '; dwCapabilities
0x18001dca7  mov     [rsp+1A0h+pAuthInfo], r13; void **
0x18001dcac  mov     [rsp+1A0h+dwImpLevel], 3; unsigned int *
0x18001dcb4  mov     [rsp+1A0h+dwAuthnLevel], 2; int
0x18001dcbc  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x18001dcc0  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x18001dcc3  mov     r8d, edx; dwAuthzSvc
0x18001dcc6  mov     rcx, [rsp+1A0h+pProxy]; pProxy
0x18001dccb  call    cs:__imp_CoSetProxyBlanket
0x18001dcd1  mov     ebx, eax
0x18001dcd3  test    eax, eax
0x18001dcd5  jns     short loc_18001DCF7
0x18001dcd7  mov     rcx, [rbp+0A8h]; this
0x18001dcde  mov     r9d, eax; char *
0x18001dce1  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\vault\\vaultserv"...
0x18001dce8  mov     edx, 2FEh; void *
0x18001dced  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001dcf2  jmp     loc_18001E4B7
0x18001dcf7  lea     rax, ??$AutoDereference@UIVaultKeyManager@@@@YAXPEAUIVaultKeyManager@@@Z; AutoDereference<IVaultKeyManager>(IVaultKeyManager *)
0x18001dcfe  mov     [rbp+0A0h+var_108], rax
0x18001dd02  mov     [rbp+0A0h+var_100], r13
0x18001dd06  mov     [rbp+0A0h+var_F8], r13d
0x18001dd0a  mov     qword ptr [rsp+1A0h+dwAuthnLevel], r13; unsigned int
0x18001dd0f  xor     r9d, r9d; unsigned __int8 *
0x18001dd12  lea     r8, [rbp+0A0h+var_100]; struct CUserVaultMgr **
0x18001dd16  xor     edx, edx; unsigned __int8
0x18001dd18  call    ?GetUserVaultManager@CVaultMgr@@QEAAKEPEAPEAVCUserVaultMgr@@QEAEPEAU_LUID@@PEAKPEAPEAX@Z; CVaultMgr::GetUserVaultManager(uchar,CUserVaultMgr * *,uchar * const,_LUID *,ulong *,void * *)
0x18001dd1d  test    eax, eax
0x18001dd1f  jz      short loc_18001DD46
0x18001dd21  mov     rcx, [rbp+0A8h]; this
0x18001dd28  mov     r9d, eax; char *
0x18001dd2b  mov     edx, 301h; void *
0x18001dd30  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001dd35  mov     ebx, eax
0x18001dd37  lea     rcx, [rbp+0A0h+var_108]
0x18001dd3b  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18001dd40  nop
0x18001dd41  jmp     loc_18001E4B7
0x18001dd46  mov     [rsp+1A0h+var_158], r13
0x18001dd4b  lea     rdx, [rsp+1A0h+var_158]
0x18001dd50  mov     rcx, [rsp+1A0h+pProxy]
0x18001dd55  call    _GetDefaultAccount
0x18001dd5a  mov     ebx, eax
0x18001dd5c  test    eax, eax
0x18001dd5e  jns     short loc_18001DDB9
0x18001dd60  mov     rcx, [rbp+0A8h]; this
0x18001dd67  mov     r9d, eax; char *
0x18001dd6a  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\vault\\vaultserv"...
0x18001dd71  mov     edx, 304h; void *
0x18001dd76  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001dd7b  nop
0x18001dd7c  mov     rcx, [rsp+1A0h+var_158]
0x18001dd81  test    rcx, rcx
0x18001dd84  jz      short loc_18001DD93
0x18001dd86  mov     rax, [rcx]
0x18001dd89  mov     rax, [rax+10h]
0x18001dd8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd92  nop
0x18001dd93  lea     rcx, [rbp+0A0h+var_108]
0x18001dd97  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18001dd9c  nop
0x18001dd9d  mov     rcx, [rsp+1A0h+pProxy]
0x18001dda2  test    rcx, rcx
0x18001dda5  jz      short loc_18001DDB4
0x18001dda7  mov     rax, [rcx]
0x18001ddaa  mov     rax, [rax+10h]
0x18001ddae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ddb3  nop
0x18001ddb4  jmp     loc_18001E4C1
0x18001ddb9  mov     [rbp+0A0h+var_C0], 0
0x18001ddc0  mov     [rbp+0A0h+var_B8], r13
0x18001ddc4  mov     [rbp+0A0h+var_B0], r13
0x18001ddc8  lea     rcx, [rbp+0A0h+var_B8]
0x18001ddcc  call    ?_Alloc_sentinel_and_proxy@?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::list<std::wstring>::_Alloc_sentinel_and_proxy(void)
0x18001ddd1  nop
0x18001ddd2  lea     rcx, [rbp+0A0h+var_A8]
0x18001ddd6  call    ??$?0AEBV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAA@AEBV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>(std::allocator<std::wstring> const &)
0x18001dddb  nop
0x18001dddc  mov     [rbp+0A0h+var_90], 7
0x18001dde4  mov     [rbp+0A0h+var_88], 8
0x18001ddec  mov     [rbp+0A0h+var_C0], 3F800000h
0x18001ddf3  mov     r8, [rbp+0A0h+var_B8]
0x18001ddf7  mov     edx, 10h
0x18001ddfc  lea     rcx, [rbp+0A0h+var_A8]
0x18001de00  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>)
0x18001de05  nop
0x18001de06  mov     rcx, [rsp+1A0h+var_158]
0x18001de0b  test    rcx, rcx
0x18001de0e  jz      loc_18001DFA9
0x18001de14  mov     [rsp+1A0h+var_148], r13
0x18001de19  mov     rax, [rcx]
0x18001de1c  mov     [rsp+1A0h+var_148], r13
0x18001de21  lea     r8, [rsp+1A0h+var_148]
0x18001de26  lea     rdx, _GUID_7b56d6f8_990b_4eb5_94a7_5621f3a8b824
0x18001de2d  mov     rax, [rax]
0x18001de30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001de35  mov     ebx, eax
0x18001de37  test    eax, eax
0x18001de39  jns     short loc_18001DEB5
0x18001de3b  mov     rcx, [rbp+0A8h]; this
0x18001de42  mov     r9d, eax; char *
0x18001de45  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\vault\\vaultserv"...
0x18001de4c  mov     edx, 30Ah; void *
0x18001de51  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001de56  nop
0x18001de57  mov     rcx, [rsp+1A0h+var_148]
0x18001de5c  test    rcx, rcx
0x18001de5f  jz      short loc_18001DE6E
0x18001de61  mov     rax, [rcx]
0x18001de64  mov     rax, [rax+10h]
0x18001de68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001de6d  nop
0x18001de6e  lea     rcx, [rbp+0A0h+var_C0]
0x18001de72  call    ??1?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(void)
0x18001de77  nop
0x18001de78  mov     rcx, [rsp+1A0h+var_158]
0x18001de7d  test    rcx, rcx
0x18001de80  jz      short loc_18001DE8F
0x18001de82  mov     rax, [rcx]
0x18001de85  mov     rax, [rax+10h]
0x18001de89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001de8e  nop
0x18001de8f  lea     rcx, [rbp+0A0h+var_108]
0x18001de93  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18001de98  nop
0x18001de99  mov     rcx, [rsp+1A0h+pProxy]
0x18001de9e  test    rcx, rcx
0x18001dea1  jz      short loc_18001DEB0
0x18001dea3  mov     rax, [rcx]
0x18001dea6  mov     rax, [rax+10h]
0x18001deaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001deaf  nop
0x18001deb0  jmp     loc_18001E4C1
0x18001deb5  mov     [rsp+1A0h+var_140], r13
0x18001deba  mov     rcx, [rsp+1A0h+var_148]
0x18001debf  mov     rax, [rcx]
0x18001dec2  mov     [rsp+1A0h+var_140], r13
0x18001dec7  lea     rdx, [rsp+1A0h+var_140]
0x18001decc  mov     rax, [rax+30h]
0x18001ded0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ded5  mov     ebx, eax
0x18001ded7  test    eax, eax
0x18001ded9  jns     short loc_18001DF31
0x18001dedb  mov     rcx, [rbp+0A8h]; this
0x18001dee2  mov     r9d, eax; char *
0x18001dee5  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\vault\\vaultserv"...
0x18001deec  mov     edx, 30Dh; void *
0x18001def1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001def6  nop
0x18001def7  lea     rcx, [rsp+1A0h+var_140]
0x18001defc  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18001df01  nop
0x18001df02  lea     rcx, [rsp+1A0h+var_148]
0x18001df07  call    ??1?$com_ptr_t@UIWebAccountProvider3@Credentials@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(void)
0x18001df0c  nop
0x18001df0d  lea     rcx, [rbp+0A0h+var_C0]
0x18001df11  call    ??1?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(void)
0x18001df16  nop
0x18001df17  lea     rcx, [rsp+1A0h+var_158]
0x18001df1c  call    ??1?$com_ptr_t@UIWebAccountProvider3@Credentials@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(void)
0x18001df21  nop
0x18001df22  lea     rcx, [rbp+0A0h+var_108]
0x18001df26  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18001df2b  nop
0x18001df2c  jmp     loc_18001E4B7
0x18001df31  xor     edx, edx; length
0x18001df33  mov     rcx, [rsp+1A0h+var_140]; string
0x18001df38  call    cs:__imp_WindowsGetStringRawBuffer
0x18001df3e  mov     rcx, rax
0x18001df41  xorps   xmm0, xmm0
0x18001df44  movups  xmmword ptr [rbp+0A0h+hstringHeader.Reserved], xmm0
0x18001df48  xorps   xmm1, xmm1
0x18001df4b  movdqu  xmmword ptr [rbp+38h], xmm1
0x18001df50  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18001df55  mov     r8, rax
0x18001df58  mov     rdx, rcx
0x18001df5b  lea     rcx, [rbp+0A0h+hstringHeader]
0x18001df5f  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001df64  nop
0x18001df65  lea     r8, [rbp+0A0h+hstringHeader]
0x18001df69  lea     rdx, [rbp+0A0h+Buf2]
0x18001df6d  lea     rcx, [rbp+0A0h+var_C0]
0x18001df71  call    ??$emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<std::wstring>(std::wstring &&)
0x18001df76  nop
0x18001df77  lea     rcx, [rbp+0A0h+hstringHeader]
0x18001df7b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001df80  nop
0x18001df81  mov     rcx, [rsp+1A0h+var_140]; string
0x18001df86  test    rcx, rcx
0x18001df89  jz      short loc_18001DF92
0x18001df8b  call    cs:__imp_WindowsDeleteString
0x18001df91  nop
0x18001df92  mov     rcx, [rsp+1A0h+var_148]
0x18001df97  test    rcx, rcx
0x18001df9a  jz      short loc_18001DFA9
0x18001df9c  mov     rax, [rcx]
0x18001df9f  mov     rax, [rax+10h]
0x18001dfa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dfa8  nop
0x18001dfa9  mov     [rbp+0A0h+hMem], r13
0x18001dfad  mov     [rbp+0A0h+var_C8], r13d
0x18001dfb1  mov     [rbp+0A0h+var_D8], r13
0x18001dfb5  mov     [rsp+1A0h+var_160], r13d
0x18001dfba  lea     r8, [rsp+1A0h+var_160]; unsigned int *
0x18001dfbf  lea     rdx, [rbp+0A0h+hMem]; struct CUserVault ***
0x18001dfc3  mov     rcx, [rbp+0A0h+var_100]; this
0x18001dfc7  call    ?EnumerateVaults@CUserVaultMgr@@QEAAKPEAPEAPEAVCUserVault@@PEAK@Z; CUserVaultMgr::EnumerateVaults(CUserVault * * *,ulong *)
0x18001dfcc  test    eax, eax
0x18001dfce  jz      short loc_18001E049
0x18001dfd0  mov     rcx, [rbp+0A8h]; this
0x18001dfd7  mov     r9d, eax; char *
0x18001dfda  mov     edx, 315h; void *
0x18001dfdf  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001dfe4  mov     ebx, eax
0x18001dfe6  mov     rcx, [rbp+0A0h+hMem]; hMem
0x18001dfea  test    rcx, rcx
0x18001dfed  jz      short loc_18001E025
0x18001dfef  mov     edx, [rbp+0A0h+var_C8]
0x18001dff2  test    edx, edx
0x18001dff4  jz      short loc_18001E00F
0x18001dff6  test    rcx, rcx
0x18001dff9  jz      short loc_18001E00F
0x18001dffb  test    rdx, rdx
0x18001dffe  jz      short loc_18001E00F
0x18001e000  mov     rax, rcx
0x18001e003  mov     [rax], r13b
0x18001e006  inc     rax
0x18001e009  sub     rdx, 1
0x18001e00d  jnz     short loc_18001E003
0x18001e00f  mov     rax, [rbp+0A0h+var_D8]
0x18001e013  test    rax, rax
0x18001e016  jz      short loc_18001E01F
0x18001e018  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e01d  jmp     short loc_18001E025
0x18001e01f  call    ?VaultFreeInternal@@YAXPEAE@Z; VaultFreeInternal(uchar *)
0x18001e024  nop
0x18001e025  lea     rcx, [rbp+0A0h+var_C0]
0x18001e029  call    ??1?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(void)
0x18001e02e  nop
0x18001e02f  lea     rcx, [rsp+1A0h+var_158]
0x18001e034  call    ??1?$com_ptr_t@UIWebAccountProvider3@Credentials@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(void)
0x18001e039  nop
0x18001e03a  lea     rcx, [rbp+0A0h+var_108]
0x18001e03e  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18001e043  nop
0x18001e044  jmp     loc_18001E4B7
0x18001e049  xorps   xmm0, xmm0
0x18001e04c  movdqu  xmmword ptr [rbp+0A0h+var_120], xmm0
  ... truncated ...
```
