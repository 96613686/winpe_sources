# SystemSettingEntryPointUtils::_anonymous_namespace_::TryGetOrCreateMRTHelperForFullyQualifiedResource

- ea: `0x18004766c`
- end: `0x180047c59`
- name: `SystemSettingEntryPointUtils::_anonymous_namespace_::TryGetOrCreateMRTHelperForFullyQualifiedResource`
- size: `1517`
- prototype: ``
- caller_count: `1`
- callee_count: `28`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180046fac`

## callees

- `0x180007e18`
- `0x1800252a0`
- `0x180026860`
- `0x180037df8`
- `0x18004766c`
- `0x1800483f4`
- `0x180048888`
- `0x18004b894`
- `0x180053fec`
- `0x180054098`
- `0x18005ee04`
- `0x18005f0fc`
- `0x18005f1e0`
- `0x180088844`
- `0x18008c938`
- `0x1800cd5a4`
- `0x1800cd7e4`
- `0x1800cd814`
- `0x1800d94d8`
- `0x1800e3a88`
- `0x18011d4e4`
- `0x18011d52c`
- `0x1801588c4`
- `0x18015cb00`
- `0x18015cfa0`
- `0x18015cfdc`
- `0x1804682b4`
- `0x180468750`

## import_xrefs

- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180047b1e`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180047b43`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180047b1e`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180047b43`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1800479a4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1800479a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047856`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047856`

## string_xrefs

- `0x1800477c3`: `shellcommon\undockeddevkit\libs\helpers\systemsettingentrypointutils.cpp`
- `0x18004787e`: `shellcommon\undockeddevkit\libs\helpers\systemsettingentrypointutils.cpp`
- `0x18004793b`: `shellcommon\undockeddevkit\libs\helpers\systemsettingentrypointutils.cpp`
- `0x180047b74`: `shellcommon\undockeddevkit\libs\helpers\systemsettingentrypointutils.cpp`
- `0x180047ba2`: `shellcommon\undockeddevkit\libs\helpers\systemsettingentrypointutils.cpp`
- `0x180047bbb`: `shellcommon\undockeddevkit\libs\helpers\systemsettingentrypointutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
__int64 __fastcall SystemSettingEntryPointUtils::_anonymous_namespace_::TryGetOrCreateMRTHelperForFullyQualifiedResource(
        __int64 a1,
        _QWORD *a2)
{
  _WORD *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // rax
  __int64 v7; // rbx
  __int64 v8; // rsi
  unsigned __int64 v9; // r8
  PCWSTR *v10; // rcx
  unsigned __int16 **v11; // r8
  char v12; // bl
  const WCHAR *v13; // rcx
  int SinglePackageFullNameFromPackageFamilyName; // eax
  const wchar_t *v15; // rbx
  __int64 v16; // rsi
  ShellMRTHelper::MRTHelperBase *v17; // rbx
  __int64 v19; // rbx
  unsigned __int64 v20; // rcx
  unsigned __int64 v21; // rbx
  char *v22; // rbx
  void *v23; // rdi
  __int64 v24; // rdx
  const char *v25; // r9
  __int64 v26; // rax
  __int64 v27; // rax
  const wchar_t *v28; // rbx
  __int64 v29; // rax
  PCWSTR *v30; // rax
  ShellMRTHelper::MRTHelperBase *v31; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v32; // [rsp+28h] [rbp-D8h]
  LPVOID *v33; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 v34[4]; // [rsp+38h] [rbp-C8h] BYREF
  char v35; // [rsp+40h] [rbp-C0h]
  PCWSTR packageFamilyName[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v37; // [rsp+58h] [rbp-A8h]
  unsigned __int64 v38; // [rsp+60h] [rbp-A0h]
  LPVOID pv[4]; // [rsp+68h] [rbp-98h] BYREF
  _QWORD Src[4]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v41[32]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v42[32]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v43[32]; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v44[32]; // [rsp+108h] [rbp+8h] BYREF
  _BYTE v45[40]; // [rsp+128h] [rbp+28h] BYREF
  WCHAR Buffer[264]; // [rsp+150h] [rbp+50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+398h] [rbp+298h]

  v4 = (_WORD *)*a2;
  if ( *(_WORD *)*a2 != 64 )
    return 0;
  if ( v4[1] != 123 )
    return 0;
  v5 = a2[1];
  if ( v4[v5 - 1] != 125 )
    return 0;
  v6 = std::_Traits_find_ch<std::char_traits<wchar_t>>(v4, v5, 2, 63);
  v7 = v6;
  v8 = -1;
  if ( v6 == -1 )
  {
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0xDF,
      (unsigned int)"shellcommon\\undockeddevkit\\libs\\helpers\\systemsettingentrypointutils.cpp",
      (const char *)0x80070057LL,
      (int)v31);
    return 0;
  }
  v9 = a2[1];
  if ( v9 < 2 )
  {
    std::_Xout_of_range("invalid string_view position");
    __debugbreak();
  }
  *(_OWORD *)packageFamilyName = 0;
  v37 = 0;
  v38 = 0;
  if ( v9 - 2 >= v6 - 2 )
    v9 = v6;
  std::wstring::_Construct<1,wchar_t *>(packageFamilyName, *a2 + 4LL, v9 - 2);
  std::_Hash<std::_Umap_traits<std::wstring,std::unique_ptr<ShellMRTHelper::MRTHelperBase>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::unique_ptr<ShellMRTHelper::MRTHelperBase>>>,0>>::find(
    a1,
    &v31,
    packageFamilyName);
  if ( v31 != *(ShellMRTHelper::MRTHelperBase **)(a1 + 8) )
  {
    v19 = *((_QWORD *)v31 + 6);
    if ( v38 > 7 )
      std::_Deallocate<16>(packageFamilyName[0], 2 * v38 + 2);
    return v19;
  }
  v10 = packageFamilyName;
  if ( v38 > 7 )
    v10 = (PCWSTR *)packageFamilyName[0];
  if ( (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(v10, v37, L"windows", 7) )
  {
    v20 = v7 + 1;
    v21 = a2[1];
    if ( v21 < v20 )
    {
      std::_Xout_of_range("invalid string_view position");
      __debugbreak();
    }
    v22 = (char *)(v21 - v20);
    if ( v22 )
      --v22;
    v23 = (void *)(*a2 + 2 * v20);
    pv[0] = v23;
    pv[1] = v22;
    v24 = 14;
    if ( (unsigned __int64)v22 < 0xE )
      v24 = (__int64)v22;
    if ( (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(v23, v24, L"ms-resource://", 14) )
    {
      v29 = std::_Traits_find_ch<std::char_traits<wchar_t>>(v23, v22, 14, 47);
      if ( v29 != -1 )
      {
        std::wstring_view::substr(pv, &v31, 14, v29 - 14);
        if ( v32 )
        {
          if ( !GetSystemWindowsDirectoryW(Buffer, 0x104u) )
            wil::details::in1diag3::Throw_GetLastError(
              retaddr,
              (void *)0x10E,
              (unsigned int)"shellcommon\\undockeddevkit\\libs\\helpers\\systemsettingentrypointutils.cpp",
              v25);
          std::filesystem::_Convert_Source_to_wide<std::wstring_view,std::filesystem::_Normal_conversion>(v43, &v31);
          std::filesystem::_Convert_Source_to_wide<std::wstring_view,std::filesystem::_Normal_conversion>(v42, &v31);
          v31 = (ShellMRTHelper::MRTHelperBase *)L"SystemResources";
          v32 = 15;
          std::filesystem::_Convert_Source_to_wide<std::wstring_view,std::filesystem::_Normal_conversion>(v41, &v31);
          do
            ++v8;
          while ( Buffer[v8] );
          v31 = (ShellMRTHelper::MRTHelperBase *)Buffer;
          v32 = v8;
          std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(pv, &v31);
          v26 = std::filesystem::operator/(v45, pv, v41);
          v27 = std::filesystem::operator/(v44, v26, v42);
          std::filesystem::operator/(Src, v27, v43);
          std::filesystem::path::~path((std::filesystem::path *)v44);
          std::filesystem::path::~path((std::filesystem::path *)v45);
          std::filesystem::path::~path((std::filesystem::path *)pv);
          std::filesystem::path::~path((std::filesystem::path *)v41);
          std::filesystem::path::~path((std::filesystem::path *)v42);
          std::filesystem::path::~path((std::filesystem::path *)v43);
          std::wstring::_Append<wchar_t>(Src);
          v28 = (const wchar_t *)Src;
          if ( Src[3] > 7u )
            v28 = (const wchar_t *)Src[0];
          v31 = (ShellMRTHelper::MRTHelperBase *)operator new(0x60u);
          pv[0] = (LPVOID)ShellMRTHelper::MRTHelperForPath::MRTHelperForPath(v31, v28);
          v19 = *(_QWORD *)(*(_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,std::unique_ptr<ShellMRTHelper::MRTHelperBase>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::unique_ptr<ShellMRTHelper::MRTHelperBase>>>,0>>::emplace<std::wstring,std::unique_ptr<ShellMRTHelper::MRTHelperForPath>>(
                                         a1,
                                         &v33,
                                         packageFamilyName,
                                         pv)
                          + 48LL);
          std::unique_ptr<ShellMRTHelper::MRTHelperBase>::~unique_ptr<ShellMRTHelper::MRTHelperBase>(pv);
          std::filesystem::path::~path((std::filesystem::path *)Src);
        }
        else
        {
          wil::details::in1diag3::Log_Hr(
            retaddr,
            (void *)0x109,
            (unsigned int)"shellcommon\\undockeddevkit\\libs\\helpers\\systemsettingentrypointutils.cpp",
            (const char *)0x80070057LL,
            (int)v31);
          v19 = 0;
        }
        goto LABEL_46;
      }
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x102,
        (unsigned int)"shellcommon\\undockeddevkit\\libs\\helpers\\systemsettingentrypointutils.cpp",
        (const char *)0x80070057LL,
        (int)v31);
      std::filesystem::path::~path((std::filesystem::path *)packageFamilyName);
    }
    else
    {
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0xFB,
        (unsigned int)"shellcommon\\undockeddevkit\\libs\\helpers\\systemsettingentrypointutils.cpp",
        (const char *)0x80070057LL,
        (int)v31);
      if ( v38 > 7 )
        std::_Deallocate<16>(packageFamilyName[0], 2 * v38 + 2);
    }
    return 0;
  }
  pv[0] = 0;
  v33 = pv;
  *(_QWORD *)v34 = 0;
  v12 = 1;
  v35 = 1;
  v13 = (const WCHAR *)packageFamilyName;
  if ( v38 > 7 )
    v13 = packageFamilyName[0];
  SinglePackageFullNameFromPackageFamilyName = CallerIdentity::GetSinglePackageFullNameFromPackageFamilyName(
                                                 v13,
                                                 v34,
                                                 v11);
  if ( SinglePackageFullNameFromPackageFamilyName < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x11C,
      (unsigned int)"shellcommon\\undockeddevkit\\libs\\helpers\\systemsettingentrypointutils.cpp",
      (const char *)(unsigned int)SinglePackageFullNameFromPackageFamilyName,
      (int)v31);
    v12 = 0;
  }
  if ( v35 )
    wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::reset(
      v33,
      *(_QWORD *)v34);
  if ( !v12 )
  {
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(pv);
    v30 = packageFamilyName;
    if ( v38 > 7 )
      v30 = (PCWSTR *)packageFamilyName[0];
    pv[0] = v30;
    std::make_unique<ShellMRTHelper::MRTHelperForPackage,wchar_t *,0>(&v31, pv);
    v19 = *(_QWORD *)(*(_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,std::unique_ptr<ShellMRTHelper::MRTHelperBase>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::unique_ptr<ShellMRTHelper::MRTHelperBase>>>,0>>::emplace<std::wstring,std::unique_ptr<ShellMRTHelper::MRTHelperForPackage>>(
                                   a1,
                                   &v33,
                                   packageFamilyName,
                                   &v31)
                    + 48LL);
    std::unique_ptr<ShellMRTHelper::MRTHelperBase>::~unique_ptr<ShellMRTHelper::MRTHelperBase>(&v31);
LABEL_46:
    std::filesystem::path::~path((std::filesystem::path *)packageFamilyName);
    return v19;
  }
  v15 = (const wchar_t *)pv[0];
  v31 = (ShellMRTHelper::MRTHelperBase *)operator new(0x60u);
  v31 = (ShellMRTHelper::MRTHelperBase *)ShellMRTHelper::MRTHelperForPackage::MRTHelperForPackage(v31, v15);
  v16 = *(_QWORD *)(*(_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,std::unique_ptr<ShellMRTHelper::MRTHelperBase>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::unique_ptr<ShellMRTHelper::MRTHelperBase>>>,0>>::emplace<std::wstring,std::unique_ptr<ShellMRTHelper::MRTHelperForPackage>>(
                                 a1,
                                 &v33,
                                 packageFamilyName,
                                 &v31)
                  + 48LL);
  v17 = v31;
  if ( v31 )
  {
    ShellMRTHelper::MRTHelperBase::~MRTHelperBase(v31);
    operator delete(v17, (const struct std::nothrow_t *)0x60);
  }
  if ( pv[0] )
    CoTaskMemFree(pv[0]);
  if ( v38 > 7 )
    std::_Deallocate<16>(packageFamilyName[0], 2 * v38 + 2);
  return v16;
}

```

## disassembly

```asm
0x18004766c  mov     [rsp-8+arg_10], rbx
0x180047671  mov     [rsp-8+arg_18], rsi
0x180047676  push    rbp
0x180047677  push    rdi
0x180047678  push    r12
0x18004767a  push    r14
0x18004767c  push    r15
0x18004767e  lea     rbp, [rsp-270h]
0x180047686  sub     rsp, 370h
0x18004768d  mov     rax, cs:__security_cookie
0x180047694  xor     rax, rsp
0x180047697  mov     [rbp+290h+var_30], rax
0x18004769e  mov     rdi, rdx
0x1800476a1  mov     r14, rcx
0x1800476a4  xor     r15d, r15d
0x1800476a7  mov     rcx, [rdx]
0x1800476aa  cmp     word ptr [rcx], 40h ; '@'
0x1800476ae  jnz     loc_18004788F
0x1800476b4  cmp     word ptr [rcx+2], 7Bh ; '{'
0x1800476b9  jnz     loc_18004788F
0x1800476bf  mov     rdx, [rdx+8]
0x1800476c3  cmp     word ptr [rcx+rdx*2-2], 7Dh ; '}'
0x1800476c9  jnz     loc_18004788F
0x1800476cf  lea     r9d, [r15+3Fh]
0x1800476d3  lea     r8d, [r15+2]
0x1800476d7  call    ??$_Traits_find_ch@U?$char_traits@_W@std@@@std@@YA_KQEB_W_K1_W@Z; std::_Traits_find_ch<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,unsigned __int64,wchar_t)
0x1800476dc  mov     rbx, rax
0x1800476df  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800476e3  cmp     rax, rsi
0x1800476e6  jz      loc_180047871
0x1800476ec  mov     r8, [rdi+8]
0x1800476f0  cmp     r8, 2
0x1800476f4  jb      loc_180047B17
0x1800476fa  xorps   xmm0, xmm0
0x1800476fd  movups  xmmword ptr [rsp+390h+packageFamilyName], xmm0
0x180047702  mov     [rsp+390h+var_338], r15
0x180047707  mov     [rsp+390h+var_330], r15
0x18004770c  lea     rcx, [r8-2]
0x180047710  add     rax, 0FFFFFFFFFFFFFFFEh
0x180047714  cmp     rcx, rax
0x180047717  cmovnb  r8, rbx
0x18004771b  sub     r8, 2
0x18004771f  mov     rdx, [rdi]
0x180047722  add     rdx, 4
0x180047726  lea     rcx, [rsp+390h+packageFamilyName]
0x18004772b  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x180047730  nop
0x180047731  lea     r8, [rsp+390h+packageFamilyName]
0x180047736  lea     rdx, [rsp+390h+var_370]
0x18004773b  mov     rcx, r14
0x18004773e  call    ?find@?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@VMRTHelperBase@ShellMRTHelper@@U?$default_delete@VMRTHelperBase@ShellMRTHelper@@@std@@@2@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@VMRTHelperBase@ShellMRTHelper@@U?$default_delete@VMRTHelperBase@ShellMRTHelper@@@std@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@VMRTHelperBase@ShellMRTHelper@@U?$default_delete@VMRTHelperBase@ShellMRTHelper@@@std@@@2@@std@@@std@@@std@@@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::unique_ptr<ShellMRTHelper::MRTHelperBase>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::unique_ptr<ShellMRTHelper::MRTHelperBase>>>,0>>::find(std::wstring const &)
0x180047743  mov     rax, [rsp+390h+var_370]
0x180047748  cmp     rax, [r14+8]
0x18004774c  jnz     loc_180047893
0x180047752  lea     rcx, [rsp+390h+packageFamilyName]
0x180047757  cmp     [rsp+390h+var_330], 7
0x18004775d  cmova   rcx, [rsp+390h+packageFamilyName]
0x180047763  lea     r9d, [r15+7]
0x180047767  lea     r8, aWindows; "windows"
0x18004776e  mov     rdx, [rsp+390h+var_338]
0x180047773  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x180047778  test    al, al
0x18004777a  jnz     loc_1800478D4
0x180047780  mov     [rsp+390h+pv], r15
0x180047785  lea     rax, [rsp+390h+pv]
0x18004778a  mov     [rsp+390h+var_360], rax
0x18004778f  mov     qword ptr [rsp+390h+var_358], r15
0x180047794  mov     bl, 1
0x180047796  mov     [rsp+390h+var_350], bl
0x18004779a  lea     rcx, [rsp+390h+packageFamilyName]
0x18004779f  cmp     [rsp+390h+var_330], 7
0x1800477a5  cmova   rcx, [rsp+390h+packageFamilyName]; packageFamilyName
0x1800477ab  lea     rdx, [rsp+390h+var_358]; unsigned __int16 *
0x1800477b0  call    ?GetSinglePackageFullNameFromPackageFamilyName@CallerIdentity@@YAJPEBGPEAPEAG@Z; CallerIdentity::GetSinglePackageFullNameFromPackageFamilyName(ushort const *,ushort * *)
0x1800477b5  mov     rcx, [rbp+298h]; this
0x1800477bc  test    eax, eax
0x1800477be  jns     short loc_1800477D7
0x1800477c0  mov     r9d, eax; char *
0x1800477c3  lea     r8, aShellcommonUnd_41; "shellcommon\\undockeddevkit\\libs\\help"...
0x1800477ca  mov     edx, 11Ch; void *
0x1800477cf  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800477d4  mov     bl, r15b
0x1800477d7  cmp     [rsp+390h+var_350], r15b
0x1800477dc  jnz     loc_180047BD0
0x1800477e2  test    bl, bl
0x1800477e4  jz      loc_180047BFB
0x1800477ea  mov     rbx, [rsp+390h+pv]
0x1800477ef  mov     edi, 60h ; '`'
0x1800477f4  mov     ecx, edi; Size
0x1800477f6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800477fb  mov     [rsp+390h+var_370], rax
0x180047800  mov     rdx, rbx; wchar_t *
0x180047803  mov     rcx, rax; this
0x180047806  call    ??0MRTHelperForPackage@ShellMRTHelper@@QEAA@PEB_W@Z; ShellMRTHelper::MRTHelperForPackage::MRTHelperForPackage(wchar_t const *)
0x18004780b  nop
0x18004780c  mov     [rsp+390h+var_370], rax
0x180047811  lea     r9, [rsp+390h+var_370]
0x180047816  lea     r8, [rsp+390h+packageFamilyName]
0x18004781b  lea     rdx, [rsp+390h+var_360]
0x180047820  mov     rcx, r14
0x180047823  call    ??$emplace@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@VMRTHelperForPackage@ShellMRTHelper@@U?$default_delete@VMRTHelperForPackage@ShellMRTHelper@@@std@@@2@@?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@VMRTHelperBase@ShellMRTHelper@@U?$default_delete@VMRTHelperBase@ShellMRTHelper@@@std@@@2@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@VMRTHelperBase@ShellMRTHelper@@U?$default_delete@VMRTHelperBase@ShellMRTHelper@@@std@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@VMRTHelperBase@ShellMRTHelper@@U?$default_delete@VMRTHelperBase@ShellMRTHelper@@@std@@@2@@std@@@std@@@std@@@std@@_N@1@$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@$$QEAV?$unique_ptr@VMRTHelperForPackage@ShellMRTHelper@@U?$default_delete@VMRTHelperForPackage@ShellMRTHelper@@@std@@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::unique_ptr<ShellMRTHelper::MRTHelperBase>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::unique_ptr<ShellMRTHelper::MRTHelperBase>>>,0>>::emplace<std::wstring,std::unique_ptr<ShellMRTHelper::MRTHelperForPackage>>(std::wstring &&,std::unique_ptr<ShellMRTHelper::MRTHelperForPackage> &&)
0x180047828  mov     rcx, [rax]
0x18004782b  mov     rsi, [rcx+30h]
0x18004782f  mov     rbx, [rsp+390h+var_370]
0x180047834  test    rbx, rbx
0x180047837  jz      short loc_18004784C
0x180047839  mov     rcx, rbx; this
0x18004783c  call    ??1MRTHelperBase@ShellMRTHelper@@QEAA@XZ; ShellMRTHelper::MRTHelperBase::~MRTHelperBase(void)
0x180047841  mov     edx, edi; struct std::nothrow_t *
0x180047843  mov     rcx, rbx; void *
0x180047846  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004784b  nop
0x18004784c  mov     rcx, [rsp+390h+pv]; pv
0x180047851  test    rcx, rcx
0x180047854  jz      short loc_18004785D
0x180047856  call    cs:__imp_CoTaskMemFree
0x18004785c  nop
0x18004785d  mov     rdx, [rsp+390h+var_330]
0x180047862  cmp     rdx, 7
0x180047866  ja      loc_180047BE4
0x18004786c  mov     rax, rsi
0x18004786f  jmp     short loc_1800478A9
0x180047871  mov     rcx, [rbp+298h]; this
0x180047878  mov     r9d, 80070057h; char *
0x18004787e  lea     r8, aShellcommonUnd_41; "shellcommon\\undockeddevkit\\libs\\help"...
0x180047885  mov     edx, 0DFh; void *
0x18004788a  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18004788f  xor     eax, eax
0x180047891  jmp     short loc_1800478A9
0x180047893  mov     rbx, [rax+30h]
0x180047897  mov     rdx, [rsp+390h+var_330]
0x18004789c  cmp     rdx, 7
0x1800478a0  ja      loc_180047B25
0x1800478a6  mov     rax, rbx
0x1800478a9  mov     rcx, [rbp+290h+var_30]
0x1800478b0  xor     rcx, rsp; StackCookie
0x1800478b3  call    __security_check_cookie
0x1800478b8  lea     r11, [rsp+390h+var_20]
0x1800478c0  mov     rbx, [r11+40h]
0x1800478c4  mov     rsi, [r11+48h]
0x1800478c8  mov     rsp, r11
0x1800478cb  pop     r15
0x1800478cd  pop     r14
0x1800478cf  pop     r12
0x1800478d1  pop     rdi
0x1800478d2  pop     rbp
0x1800478d3  retn
0x1800478d4  lea     rcx, [rbx+1]
0x1800478d8  mov     rbx, [rdi+8]
0x1800478dc  cmp     rbx, rcx
0x1800478df  jb      loc_180047B3C
0x1800478e5  sub     rbx, rcx
0x1800478e8  lea     rax, [rbx-1]
0x1800478ec  cmp     rbx, rax
0x1800478ef  cmovnb  rbx, rax
0x1800478f3  mov     rax, [rdi]
0x1800478f6  lea     rdi, [rax+rcx*2]
0x1800478fa  mov     [rsp+390h+pv], rdi
0x1800478ff  mov     [rsp+390h+var_320], rbx
0x180047904  mov     r12d, 0Eh
0x18004790a  mov     edx, r12d
0x18004790d  cmp     rbx, r12
0x180047910  cmovb   rdx, rbx
0x180047914  mov     r9d, r12d
0x180047917  lea     r8, aMsResource_0; "ms-resource://"
0x18004791e  mov     rcx, rdi
0x180047921  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x180047926  test    al, al
0x180047928  jnz     loc_180047B4A
0x18004792e  mov     rcx, [rbp+298h]; this
0x180047935  mov     r9d, 80070057h; char *
0x18004793b  lea     r8, aShellcommonUnd_41; "shellcommon\\undockeddevkit\\libs\\help"...
0x180047942  mov     edx, 0FBh; void *
0x180047947  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18004794c  nop
0x18004794d  mov     rdx, [rsp+390h+var_330]
0x180047952  cmp     rdx, 7
0x180047956  jbe     loc_18004788F
0x18004795c  lea     rdx, ds:2[rdx*2]
0x180047964  mov     rcx, [rsp+390h+packageFamilyName]
0x180047969  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18004796e  jmp     loc_18004788F
0x180047973  lea     r9, [rax-0Eh]
0x180047977  mov     r8, r12
0x18004797a  lea     rdx, [rsp+390h+var_370]
0x18004797f  lea     rcx, [rsp+390h+pv]
0x180047984  call    ?substr@?$basic_string_view@_WU?$char_traits@_W@std@@@std@@QEBA?AV12@_K_K@Z; std::wstring_view::substr(unsigned __int64,unsigned __int64)
0x180047989  cmp     [rsp+390h+var_368], r15
0x18004798e  jz      loc_180047B95
0x180047994  mov     rbx, [rbp+298h]
0x18004799b  mov     edx, 104h; uSize
0x1800479a0  lea     rcx, [rbp+290h+Buffer]; lpBuffer
0x1800479a4  call    cs:__imp_GetSystemWindowsDirectoryW
0x1800479aa  test    eax, eax
0x1800479ac  jz      loc_180047BBB
0x1800479b2  lea     rdx, [rsp+390h+var_370]
0x1800479b7  lea     rcx, [rbp+290h+var_2A8]
0x1800479bb  call    ??$_Convert_Source_to_wide@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@U_Normal_conversion@filesystem@2@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_Source_to_wide<std::wstring_view,std::filesystem::_Normal_conversion>(std::wstring_view const &,std::filesystem::_Normal_conversion)
0x1800479c0  nop
0x1800479c1  lea     rdx, [rsp+390h+var_370]
0x1800479c6  lea     rcx, [rbp+290h+var_2C8]
0x1800479ca  call    ??$_Convert_Source_to_wide@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@U_Normal_conversion@filesystem@2@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_Source_to_wide<std::wstring_view,std::filesystem::_Normal_conversion>(std::wstring_view const &,std::filesystem::_Normal_conversion)
0x1800479cf  nop
0x1800479d0  lea     rax, aSystemresource; "SystemResources"
0x1800479d7  mov     [rsp+390h+var_370], rax
0x1800479dc  mov     [rsp+390h+var_368], 0Fh
0x1800479e5  lea     rdx, [rsp+390h+var_370]
0x1800479ea  lea     rcx, [rbp+290h+var_2E8]
0x1800479ee  call    ??$_Convert_Source_to_wide@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@U_Normal_conversion@filesystem@2@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_Source_to_wide<std::wstring_view,std::filesystem::_Normal_conversion>(std::wstring_view const &,std::filesystem::_Normal_conversion)
0x1800479f3  nop
0x1800479f4  lea     rax, [rbp+290h+Buffer]
0x1800479f8  inc     rsi
0x1800479fb  cmp     [rax+rsi*2], r15w
0x180047a00  jnz     short loc_1800479F8
0x180047a02  lea     rax, [rbp+290h+Buffer]
0x180047a06  mov     [rsp+390h+var_370], rax
0x180047a0b  mov     [rsp+390h+var_368], rsi
0x180047a10  lea     rdx, [rsp+390h+var_370]
0x180047a15  lea     rcx, [rsp+390h+pv]
0x180047a1a  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::wstring_view,std::filesystem::_Normal_conversion)
0x180047a1f  nop
0x180047a20  lea     r8, [rbp+290h+var_2E8]
0x180047a24  lea     rdx, [rsp+390h+pv]
0x180047a29  lea     rcx, [rbp+290h+var_268]
0x180047a2d  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x180047a32  nop
0x180047a33  lea     r8, [rbp+290h+var_2C8]
0x180047a37  mov     rdx, rax
0x180047a3a  lea     rcx, [rbp+290h+var_288]
0x180047a3e  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x180047a43  nop
0x180047a44  lea     r8, [rbp+290h+var_2A8]
0x180047a48  mov     rdx, rax
0x180047a4b  lea     rcx, [rbp+290h+Src]
0x180047a4f  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x180047a54  nop
0x180047a55  lea     rcx, [rbp+290h+var_288]; this
0x180047a59  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x180047a5e  nop
0x180047a5f  lea     rcx, [rbp+290h+var_268]; this
0x180047a63  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x180047a68  nop
0x180047a69  lea     rcx, [rsp+390h+pv]; this
0x180047a6e  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x180047a73  nop
0x180047a74  lea     rcx, [rbp+290h+var_2E8]; this
0x180047a78  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x180047a7d  nop
0x180047a7e  lea     rcx, [rbp+290h+var_2C8]; this
0x180047a82  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x180047a87  nop
0x180047a88  lea     rcx, [rbp+290h+var_2A8]; this
0x180047a8c  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x180047a91  mov     r8d, 4
0x180047a97  lea     rdx, aPri; ".pri"
0x180047a9e  lea     rcx, [rbp+290h+Src]; Src
0x180047aa2  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x180047aa7  lea     rbx, [rbp+290h+Src]
0x180047aab  cmp     [rbp+290h+var_2F0], 7
0x180047ab0  cmova   rbx, [rbp+290h+Src]
0x180047ab5  mov     ecx, 60h ; '`'; Size
0x180047aba  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180047abf  mov     [rsp+390h+var_370], rax
0x180047ac4  mov     rdx, rbx; wchar_t *
0x180047ac7  mov     rcx, rax; this
0x180047aca  call    ??0MRTHelperForPath@ShellMRTHelper@@QEAA@PEB_W@Z; ShellMRTHelper::MRTHelperForPath::MRTHelperForPath(wchar_t const *)
0x180047acf  nop
0x180047ad0  mov     [rsp+390h+pv], rax
0x180047ad5  lea     r9, [rsp+390h+pv]
0x180047ada  lea     r8, [rsp+390h+packageFamilyName]
0x180047adf  lea     rdx, [rsp+390h+var_360]
0x180047ae4  mov     rcx, r14
0x180047ae7  call    ??$emplace@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@VMRTHelperForPath@ShellMRTHelper@@U?$default_delete@VMRTHelperForPath@ShellMRTHelper@@@std@@@2@@?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@VMRTHelperBase@ShellMRTHelper@@U?$default_delete@VMRTHelperBase@ShellMRTHelper@@@std@@@2@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@VMRTHelperBase@ShellMRTHelper@@U?$default_delete@VMRTHelperBase@ShellMRTHelper@@@std@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@VMRTHelperBase@ShellMRTHelper@@U?$default_delete@VMRTHelperBase@ShellMRTHelper@@@std@@@2@@std@@@std@@@std@@@std@@_N@1@$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@$$QEAV?$unique_ptr@VMRTHelperForPath@ShellMRTHelper@@U?$default_delete@VMRTHelperForPath@ShellMRTHelper@@@std@@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::unique_ptr<ShellMRTHelper::MRTHelperBase>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::unique_ptr<ShellMRTHelper::MRTHelperBase>>>,0>>::emplace<std::wstring,std::unique_ptr<ShellMRTHelper::MRTHelperForPath>>(std::wstring &&,std::unique_ptr<ShellMRTHelper::MRTHelperForPath> &&)
0x180047aec  mov     rcx, [rax]
0x180047aef  mov     rbx, [rcx+30h]
0x180047af3  lea     rcx, [rsp+390h+pv]
0x180047af8  call    ??1?$unique_ptr@VMRTHelperBase@ShellMRTHelper@@U?$default_delete@VMRTHelperBase@ShellMRTHelper@@@std@@@std@@QEAA@XZ; std::unique_ptr<ShellMRTHelper::MRTHelperBase>::~unique_ptr<ShellMRTHelper::MRTHelperBase>(void)
0x180047afd  nop
0x180047afe  lea     rcx, [rbp+290h+Src]; this
0x180047b02  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x180047b07  nop
0x180047b08  lea     rcx, [rsp+390h+packageFamilyName]; this
0x180047b0d  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x180047b12  jmp     loc_1800478A6
0x180047b17  lea     rcx, aInvalidStringV; "invalid string_view position"
0x180047b1e  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x180047b24  int     3; Trap to Debugger
0x180047b25  lea     rdx, ds:2[rdx*2]
0x180047b2d  mov     rcx, [rsp+390h+packageFamilyName]
0x180047b32  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180047b37  jmp     loc_1800478A6
0x180047b3c  lea     rcx, aInvalidStringV; "invalid string_view position"
0x180047b43  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x180047b49  int     3; Trap to Debugger
0x180047b4a  mov     r9d, 2Fh ; '/'
0x180047b50  mov     r8, r12
0x180047b53  mov     rdx, rbx
0x180047b56  mov     rcx, rdi
0x180047b59  call    ??$_Traits_find_ch@U?$char_traits@_W@std@@@std@@YA_KQEB_W_K1_W@Z; std::_Traits_find_ch<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,unsigned __int64,wchar_t)
0x180047b5e  cmp     rax, rsi
  ... truncated ...
```
