# winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::CheckPackageCompatibility(void)

- ea: `0x1800d9000`
- end: `0x1800d94d2`
- name: `?CheckPackageCompatibility@ExtensionInfo@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@AEAA_NXZ`
- size: `1234`
- prototype: `bool __fastcall(winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo *__hidden this)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1802b6de8`

## callees

- `0x18000fea0`
- `0x180010940`
- `0x180015344`
- `0x180015368`
- `0x18001cb54`
- `0x180020a14`
- `0x180021e18`
- `0x18002522c`
- `0x180025264`
- `0x1800252a0`
- `0x180026860`
- `0x180038f3c`
- `0x1800cd5a4`
- `0x1800d9000`
- `0x1800d94d8`
- `0x1800d9554`
- `0x1800d974c`
- `0x18015cb00`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800d9448`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800d9448`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800d9032`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800d9032`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800d906c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800d906c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800d9075`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800d9075`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800d9299`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800d9299`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d9237`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d9336`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d9237`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d9336`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800d93e9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800d942f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800d93e9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800d942f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d9261`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d9261`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800d939d`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800d939d`

## string_xrefs

- `0x1800d90d8`: `Software\Microsoft\Windows\CurrentVersion\Shell\Update`
- `0x1800d92c0`: `Software\Microsoft\Windows\CurrentVersion\Shell\Update`
- `0x1800d912d`: `\Components`
- `0x1800d92ac`: `\Packages\Components`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
char __fastcall winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::CheckPackageCompatibility(
        winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo *this)
{
  char *v2; // rdi
  __int64 v3; // rcx
  __int128 v4; // xmm0
  __int64 v5; // rdx
  __int64 v6; // rax
  __int64 v7; // rax
  __m128i si128; // xmm0
  HKEY *phkResult; // rax
  const WCHAR *v10; // rdx
  __int64 v11; // rcx
  char v12; // bl
  __int64 v13; // rbx
  __int64 v14; // rax
  __int64 v15; // rax
  HKEY *v16; // rax
  const WCHAR *v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // rax
  DWORD v20; // esi
  __int64 v21; // rcx
  __int64 v22; // rcx
  RTL_SRWLOCK *v24; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD Src[2]; // [rsp+48h] [rbp-B8h] BYREF
  __m128i v26; // [rsp+58h] [rbp-A8h]
  __int128 v27; // [rsp+68h] [rbp-98h] BYREF
  __int128 v28; // [rsp+78h] [rbp-88h]
  __int128 v29; // [rsp+88h] [rbp-78h] BYREF
  __int128 v30; // [rsp+98h] [rbp-68h]
  _QWORD v31[3]; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int64 v32; // [rsp+C0h] [rbp-40h]
  DWORD cchValueName; // [rsp+C8h] [rbp-38h] BYREF
  HKEY hKey; // [rsp+D0h] [rbp-30h] BYREF
  HKEY hkey; // [rsp+D8h] [rbp-28h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+E0h] [rbp-20h] BYREF
  __m128i v37; // [rsp+F0h] [rbp-10h]
  DWORD pcbData[4]; // [rsp+100h] [rbp+0h] BYREF
  __m128i v39; // [rsp+110h] [rbp+10h]
  _BYTE pvData[96]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v41[96]; // [rsp+180h] [rbp+80h] BYREF
  WCHAR ValueName[72]; // [rsp+1E0h] [rbp+E0h] BYREF

  AcquireSRWLockShared(&winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::s_srwCompatibleMapLock);
  v24 = &winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::s_srwCompatibleMapLock;
  *(_QWORD *)pcbData = 0;
  v2 = (char *)this + 136;
  std::_Hash<std::_Umap_traits<std::wstring,bool,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,bool>>,0>>::find(
    v3,
    pcbData,
    v2);
  if ( *(_QWORD *)pcbData == qword_1805E8158 )
  {
    ReleaseSRWLockShared(&winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::s_srwCompatibleMapLock);
    AcquireSRWLockExclusive(&winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::s_srwCompatibleMapLock);
    v24 = &winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::s_srwCompatibleMapLock;
    v4 = 0;
    *(_OWORD *)lpSubKey = 0;
    v37 = 0;
    *(double *)&v4 = std::wstring::_Construct_empty(lpSubKey);
    hKey = 0;
    v29 = v4;
    v30 = 0;
    std::wstring::_Construct<1,wchar_t *>(&v29, L"\\Packages\\", 10);
    v27 = 0;
    v28 = 0;
    std::wstring::_Construct<1,wchar_t *>(&v27, L"Software\\Microsoft\\Windows\\CurrentVersion\\Shell\\Update", 54);
    std::wstring::wstring(pcbData, v5, &v27, &v29);
    v6 = std::wstring::_Append<wchar_t>(pcbData);
    std::wstring::wstring(Src, v6);
    v7 = std::wstring::_Append<wchar_t>(Src);
    std::wstring::wstring(v31, v7);
    std::wstring::operator=(lpSubKey, v31);
    if ( v32 > 7 )
      std::_Deallocate<16>(v31[0], 2 * v32 + 2);
    if ( v26.m128i_i64[1] > 7uLL )
      std::_Deallocate<16>(Src[0], 2 * v26.m128i_i64[1] + 2);
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v26 = si128;
    LOWORD(Src[0]) = 0;
    if ( v39.m128i_i64[1] > 7uLL )
    {
      std::_Deallocate<16>(*(_QWORD *)pcbData, 2 * v39.m128i_i64[1] + 2);
      si128 = _mm_load_si128((const __m128i *)&_xmm);
    }
    v39 = si128;
    LOWORD(pcbData[0]) = 0;
    if ( *((_QWORD *)&v28 + 1) > 7u )
      std::_Deallocate<16>(v27, 2LL * *((_QWORD *)&v28 + 1) + 2);
    if ( *((_QWORD *)&v30 + 1) > 7u )
      std::_Deallocate<16>(v29, 2LL * *((_QWORD *)&v30 + 1) + 2);
    phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
    v10 = (const WCHAR *)lpSubKey;
    if ( v37.m128i_i64[1] > 7uLL )
      v10 = lpSubKey[0];
    if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, v10, 0, 0x20019u, phkResult) )
    {
      v12 = 1;
      *(_BYTE *)(*(_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,bool,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,bool>>,0>>::_Try_emplace<std::wstring const &,>(
                              v11,
                              pcbData,
                              v2)
               + 48LL) = 1;
      if ( hKey )
        RegCloseKey(hKey);
      if ( v37.m128i_i64[1] > 7uLL )
        std::_Deallocate<16>(lpSubKey[0], 2 * v37.m128i_i64[1] + 2);
      v37 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(lpSubKey[0]) = 0;
      ReleaseSRWLockExclusive(&winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::s_srwCompatibleMapLock);
    }
    else
    {
      hkey = 0;
      v13 = std::wstring::wstring(&v27, L"\\Packages\\Components");
      v14 = std::wstring::wstring(&v29, L"Software\\Microsoft\\Windows\\CurrentVersion\\Shell\\Update");
      v15 = std::operator+<wchar_t>(v31, v14, v13);
      std::wstring::operator=(lpSubKey, v15);
      std::filesystem::path::~path((std::filesystem::path *)v31);
      std::filesystem::path::~path((std::filesystem::path *)&v29);
      std::filesystem::path::~path((std::filesystem::path *)&v27);
      v16 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hkey);
      v17 = (const WCHAR *)lpSubKey;
      if ( v37.m128i_i64[1] > 7uLL )
        v17 = lpSubKey[0];
      if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, v17, 0, 0x20019u, v16) )
      {
        v19 = std::_Hash<std::_Umap_traits<std::wstring,bool,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,bool>>,0>>::_Try_emplace<std::wstring const &,>(
                v18,
                pcbData,
                v2);
        v12 = 1;
      }
      else
      {
        v20 = 0;
        cchValueName = 65;
        v12 = 1;
        while ( !RegEnumValueW(hKey, v20, ValueName, &cchValueName, 0, 0, 0, 0) )
        {
          ++v20;
          cchValueName = 65;
          pcbData[0] = 82;
          if ( !RegGetValueW(hkey, 0, ValueName, 2u, 0, pvData, pcbData) )
          {
            pcbData[0] = 82;
            if ( !RegGetValueW(hKey, 0, ValueName, 2u, 0, v41, pcbData) )
            {
              if ( (unsigned int)_o__wcsicmp(v41, pvData) )
              {
                *(_BYTE *)(*(_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,bool,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,bool>>,0>>::_Try_emplace<std::wstring const &,>(
                                        v22,
                                        Src,
                                        v2)
                         + 48LL) = 0;
                v12 = 0;
                goto LABEL_31;
              }
            }
          }
        }
        v19 = std::_Hash<std::_Umap_traits<std::wstring,bool,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,bool>>,0>>::_Try_emplace<std::wstring const &,>(
                v21,
                Src,
                v2);
      }
      *(_BYTE *)(*(_QWORD *)v19 + 48LL) = 1;
LABEL_31:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      std::filesystem::path::~path((std::filesystem::path *)lpSubKey);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v24);
    }
  }
  else
  {
    v12 = *(_BYTE *)(*(_QWORD *)pcbData + 48LL);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v24);
  }
  return v12;
}

```

## disassembly

```asm
0x1800d9000  push    rbp
0x1800d9002  push    rbx
0x1800d9003  push    rsi
0x1800d9004  push    rdi
0x1800d9005  lea     rbp, [rsp-188h]
0x1800d900d  sub     rsp, 288h
0x1800d9014  mov     rax, cs:__security_cookie
0x1800d901b  xor     rax, rsp
0x1800d901e  mov     [rbp+1A0h+var_30], rax
0x1800d9025  mov     rdi, rcx
0x1800d9028  lea     rsi, ?s_srwCompatibleMapLock@ExtensionInfo@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@0Vsrwlock@wil@@A; wil::srwlock winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::s_srwCompatibleMapLock
0x1800d902f  mov     rcx, rsi; SRWLock
0x1800d9032  call    cs:__imp_AcquireSRWLockShared
0x1800d9038  mov     [rsp+2A0h+var_260], rsi
0x1800d903d  mov     qword ptr [rbp+1A0h+pcbData], 0
0x1800d9045  add     rdi, 88h
0x1800d904c  mov     r8, rdi
0x1800d904f  lea     rdx, [rbp+1A0h+pcbData]
0x1800d9053  call    ?find@?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_NV?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_N@std@@@2@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_N@std@@@std@@@std@@@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@@Z; std::_Hash<std::_Umap_traits<std::wstring,bool,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,bool>>,0>>::find(std::wstring const &)
0x1800d9058  mov     rax, qword ptr [rbp+1A0h+pcbData]
0x1800d905c  cmp     rax, cs:qword_1805E8158
0x1800d9063  jnz     loc_1800D94A8
0x1800d9069  mov     rcx, rsi; SRWLock
0x1800d906c  call    cs:__imp_ReleaseSRWLockShared
0x1800d9072  mov     rcx, rsi; SRWLock
0x1800d9075  call    cs:__imp_AcquireSRWLockExclusive
0x1800d907b  mov     [rsp+2A0h+var_260], rsi
0x1800d9080  xorps   xmm0, xmm0
0x1800d9083  movups  xmmword ptr [rbp+1A0h+lpSubKey], xmm0
0x1800d9087  xorps   xmm1, xmm1
0x1800d908a  movdqu  [rbp+1A0h+var_1B0], xmm1
0x1800d908f  lea     rcx, [rbp+1A0h+lpSubKey]
0x1800d9093  call    ?_Construct_empty@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x1800d9098  nop
0x1800d9099  mov     [rbp+1A0h+hKey], 0
0x1800d90a1  movups  [rbp+1A0h+var_218], xmm0
0x1800d90a5  movdqu  [rbp+1A0h+var_208], xmm1
0x1800d90aa  mov     r8d, 0Ah
0x1800d90b0  lea     rdx, aPackages; "\\Packages\\"
0x1800d90b7  lea     rcx, [rbp+1A0h+var_218]
0x1800d90bb  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x1800d90c0  nop
0x1800d90c1  xorps   xmm0, xmm0
0x1800d90c4  movups  [rsp+2A0h+var_238], xmm0
0x1800d90c9  xorps   xmm1, xmm1
0x1800d90cc  movdqu  [rsp+2A0h+var_228], xmm1
0x1800d90d2  mov     r8d, 36h ; '6'
0x1800d90d8  lea     rdx, ?c_shellUpdateRegKey@Update@Shell@Internal@Windows@@3QB_WB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800d90df  lea     rcx, [rsp+2A0h+var_238]
0x1800d90e4  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x1800d90e9  nop
0x1800d90ea  lea     r9, [rbp+1A0h+var_218]
0x1800d90ee  lea     r8, [rsp+2A0h+var_238]
0x1800d90f3  lea     rcx, [rbp+1A0h+pcbData]
0x1800d90f7  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring &,std::wstring &)
0x1800d90fc  nop
0x1800d90fd  cmp     qword ptr [rdi+18h], 7
0x1800d9102  jbe     short loc_1800D9109
0x1800d9104  mov     rdx, [rdi]
0x1800d9107  jmp     short loc_1800D910C
0x1800d9109  mov     rdx, rdi
0x1800d910c  mov     r8, [rdi+10h]
0x1800d9110  lea     rcx, [rbp+1A0h+pcbData]; Src
0x1800d9114  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x1800d9119  mov     rdx, rax
0x1800d911c  lea     rcx, [rsp+2A0h+Src]
0x1800d9121  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x1800d9126  nop
0x1800d9127  mov     r8d, 0Bh
0x1800d912d  lea     rdx, aComponents; "\\Components"
0x1800d9134  lea     rcx, [rsp+2A0h+Src]; Src
0x1800d9139  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x1800d913e  mov     rdx, rax
0x1800d9141  lea     rcx, [rbp+1A0h+var_1F8]
0x1800d9145  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x1800d914a  lea     rdx, [rbp+1A0h+var_1F8]
0x1800d914e  lea     rcx, [rbp+1A0h+lpSubKey]
0x1800d9152  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800d9157  mov     rdx, [rbp+1A0h+var_1E0]
0x1800d915b  cmp     rdx, 7
0x1800d915f  jbe     short loc_1800D9173
0x1800d9161  lea     rdx, ds:2[rdx*2]
0x1800d9169  mov     rcx, [rbp+1A0h+var_1F8]
0x1800d916d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800d9172  nop
0x1800d9173  mov     rdx, [rsp+2A0h+var_240]
0x1800d9178  cmp     rdx, 7
0x1800d917c  jbe     short loc_1800D9190
0x1800d917e  lea     rdx, ds:2[rdx*2]
0x1800d9186  mov     rcx, [rsp+2A0h+Src]
0x1800d918b  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800d9190  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x1800d9198  movdqu  xmmword ptr [rsp+58h], xmm0
0x1800d919e  xor     eax, eax
0x1800d91a0  mov     word ptr [rsp+2A0h+Src], ax
0x1800d91a5  mov     rdx, [rbp+1A0h+var_188]
0x1800d91a9  cmp     rdx, 7
0x1800d91ad  jbe     short loc_1800D91C8
0x1800d91af  lea     rdx, ds:2[rdx*2]
0x1800d91b7  mov     rcx, qword ptr [rbp+1A0h+pcbData]
0x1800d91bb  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800d91c0  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x1800d91c8  movdqu  xmmword ptr [rbp+10h], xmm0
0x1800d91cd  xor     eax, eax
0x1800d91cf  mov     word ptr [rbp+1A0h+pcbData], ax
0x1800d91d3  mov     rdx, qword ptr [rbp+1A0h+var_228+8]
0x1800d91d7  cmp     rdx, 7
0x1800d91db  jbe     short loc_1800D91F0
0x1800d91dd  lea     rdx, ds:2[rdx*2]
0x1800d91e5  mov     rcx, qword ptr [rsp+2A0h+var_238]
0x1800d91ea  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800d91ef  nop
0x1800d91f0  mov     rdx, qword ptr [rbp+1A0h+var_208+8]
0x1800d91f4  cmp     rdx, 7
0x1800d91f8  jbe     short loc_1800D920B
0x1800d91fa  lea     rdx, ds:2[rdx*2]
0x1800d9202  mov     rcx, qword ptr [rbp+1A0h+var_218]
0x1800d9206  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800d920b  lea     rcx, [rbp+1A0h+hKey]
0x1800d920f  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1800d9214  lea     rdx, [rbp+1A0h+lpSubKey]
0x1800d9218  cmp     qword ptr [rbp+1A0h+var_1B0+8], 7
0x1800d921d  cmova   rdx, [rbp+1A0h+lpSubKey]; lpSubKey
0x1800d9222  mov     [rsp+2A0h+phkResult], rax; phkResult
0x1800d9227  mov     r9d, 20019h; samDesired
0x1800d922d  xor     r8d, r8d; ulOptions
0x1800d9230  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800d9237  call    cs:__imp_RegOpenKeyExW
0x1800d923d  test    eax, eax
0x1800d923f  jz      short loc_1800D92A4
0x1800d9241  mov     r8, rdi
0x1800d9244  lea     rdx, [rbp+1A0h+pcbData]
0x1800d9248  call    ??$_Try_emplace@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_NV?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_N@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_N@std@@PEAX@std@@_N@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,bool,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,bool>>,0>>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x1800d924d  mov     rcx, [rax]
0x1800d9250  mov     ebx, 1
0x1800d9255  mov     [rcx+30h], bl
0x1800d9258  mov     rcx, [rbp+1A0h+hKey]; hKey
0x1800d925c  test    rcx, rcx
0x1800d925f  jz      short loc_1800D9268
0x1800d9261  call    cs:__imp_RegCloseKey
0x1800d9267  nop
0x1800d9268  mov     rdx, qword ptr [rbp+1A0h+var_1B0+8]
0x1800d926c  cmp     rdx, 7
0x1800d9270  jbe     short loc_1800D9283
0x1800d9272  lea     rdx, ds:2[rdx*2]
0x1800d927a  mov     rcx, [rbp+1A0h+lpSubKey]
0x1800d927e  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800d9283  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x1800d928b  movdqu  [rbp+1A0h+var_1B0], xmm0
0x1800d9290  xor     edx, edx
0x1800d9292  mov     word ptr [rbp+1A0h+lpSubKey], dx
0x1800d9296  mov     rcx, rsi; SRWLock
0x1800d9299  call    cs:__imp_ReleaseSRWLockExclusive
0x1800d929f  jmp     loc_1800D94B5
0x1800d92a4  mov     [rbp+1A0h+hkey], 0
0x1800d92ac  lea     rdx, aPackagesCompon; "\\Packages\\Components"
0x1800d92b3  lea     rcx, [rsp+2A0h+var_238]
0x1800d92b8  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800d92bd  mov     rbx, rax
0x1800d92c0  lea     rdx, ?c_shellUpdateRegKey@Update@Shell@Internal@Windows@@3QB_WB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800d92c7  lea     rcx, [rbp+1A0h+var_218]
0x1800d92cb  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800d92d0  nop
0x1800d92d1  mov     r8, rbx
0x1800d92d4  mov     rdx, rax
0x1800d92d7  lea     rcx, [rbp+1A0h+var_1F8]
0x1800d92db  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@0@Z; std::operator+<wchar_t>(std::wstring &&,std::wstring &&)
0x1800d92e0  mov     rdx, rax
0x1800d92e3  lea     rcx, [rbp+1A0h+lpSubKey]
0x1800d92e7  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800d92ec  lea     rcx, [rbp+1A0h+var_1F8]; this
0x1800d92f0  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x1800d92f5  nop
0x1800d92f6  lea     rcx, [rbp+1A0h+var_218]; this
0x1800d92fa  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x1800d92ff  nop
0x1800d9300  lea     rcx, [rsp+2A0h+var_238]; this
0x1800d9305  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x1800d930a  lea     rcx, [rbp+1A0h+hkey]
0x1800d930e  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1800d9313  lea     rdx, [rbp+1A0h+lpSubKey]
0x1800d9317  cmp     qword ptr [rbp+1A0h+var_1B0+8], 7
0x1800d931c  cmova   rdx, [rbp+1A0h+lpSubKey]; lpSubKey
0x1800d9321  mov     [rsp+2A0h+phkResult], rax; phkResult
0x1800d9326  mov     r9d, 20019h; samDesired
0x1800d932c  xor     r8d, r8d; ulOptions
0x1800d932f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800d9336  call    cs:__imp_RegOpenKeyExW
0x1800d933c  test    eax, eax
0x1800d933e  jz      short loc_1800D935C
0x1800d9340  mov     r8, rdi
0x1800d9343  lea     rdx, [rbp+1A0h+pcbData]
0x1800d9347  call    ??$_Try_emplace@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_NV?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_N@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_N@std@@PEAX@std@@_N@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,bool,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,bool>>,0>>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x1800d934c  mov     ebx, 1
0x1800d9351  mov     rcx, [rax]
0x1800d9354  mov     [rcx+30h], bl
0x1800d9357  jmp     loc_1800D946C
0x1800d935c  xor     esi, esi
0x1800d935e  mov     [rbp+1A0h+cchValueName], 41h ; 'A'
0x1800d9365  lea     ebx, [rsi+1]
0x1800d9368  mov     [rsp+2A0h+lpcbData], 0; lpcbData
0x1800d9371  mov     [rsp+2A0h+lpData], 0; lpData
0x1800d937a  mov     [rsp+2A0h+lpType], 0; lpType
0x1800d9383  mov     [rsp+2A0h+phkResult], 0; lpReserved
0x1800d938c  lea     r9, [rbp+1A0h+cchValueName]; lpcchValueName
0x1800d9390  lea     r8, [rbp+1A0h+ValueName]; lpValueName
0x1800d9397  mov     edx, esi; dwIndex
0x1800d9399  mov     rcx, [rbp+1A0h+hKey]; hKey
0x1800d939d  call    cs:__imp_RegEnumValueW
0x1800d93a3  test    eax, eax
0x1800d93a5  jnz     loc_1800D9496
0x1800d93ab  add     esi, ebx
0x1800d93ad  mov     [rbp+1A0h+cchValueName], 41h ; 'A'
0x1800d93b4  mov     [rbp+1A0h+pcbData], 52h ; 'R'
0x1800d93bb  lea     rax, [rbp+1A0h+pcbData]
0x1800d93bf  mov     [rsp+2A0h+lpData], rax; pcbData
0x1800d93c4  lea     rax, [rbp+1A0h+pvData]
0x1800d93c8  mov     [rsp+2A0h+lpType], rax; pvData
0x1800d93cd  mov     [rsp+2A0h+phkResult], 0; pdwType
0x1800d93d6  mov     r9d, 2; dwFlags
0x1800d93dc  lea     r8, [rbp+1A0h+ValueName]; lpValue
0x1800d93e3  xor     edx, edx; lpSubKey
0x1800d93e5  mov     rcx, [rbp+1A0h+hkey]; hkey
0x1800d93e9  call    cs:__imp_RegGetValueW
0x1800d93ef  test    eax, eax
0x1800d93f1  jnz     loc_1800D9368
0x1800d93f7  mov     [rbp+1A0h+pcbData], 52h ; 'R'
0x1800d93fe  lea     rax, [rbp+1A0h+pcbData]
0x1800d9402  mov     [rsp+2A0h+lpData], rax; pcbData
0x1800d9407  lea     rax, [rbp+1A0h+var_120]
0x1800d940e  mov     [rsp+2A0h+lpType], rax; pvData
0x1800d9413  mov     [rsp+2A0h+phkResult], 0; pdwType
0x1800d941c  mov     r9d, 2; dwFlags
0x1800d9422  lea     r8, [rbp+1A0h+ValueName]; lpValue
0x1800d9429  xor     edx, edx; lpSubKey
0x1800d942b  mov     rcx, [rbp+1A0h+hKey]; hkey
0x1800d942f  call    cs:__imp_RegGetValueW
0x1800d9435  test    eax, eax
0x1800d9437  jnz     loc_1800D9368
0x1800d943d  lea     rdx, [rbp+1A0h+pvData]
0x1800d9441  lea     rcx, [rbp+1A0h+var_120]
0x1800d9448  call    cs:__imp__o__wcsicmp
0x1800d944e  test    eax, eax
0x1800d9450  jz      loc_1800D9368
0x1800d9456  mov     r8, rdi
0x1800d9459  lea     rdx, [rsp+2A0h+Src]
0x1800d945e  call    ??$_Try_emplace@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_NV?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_N@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_N@std@@PEAX@std@@_N@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,bool,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,bool>>,0>>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x1800d9463  mov     rcx, [rax]
0x1800d9466  mov     byte ptr [rcx+30h], 0
0x1800d946a  xor     bl, bl
0x1800d946c  lea     rcx, [rbp+1A0h+hkey]
0x1800d9470  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800d9475  nop
0x1800d9476  lea     rcx, [rbp+1A0h+hKey]
0x1800d947a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800d947f  nop
0x1800d9480  lea     rcx, [rbp+1A0h+lpSubKey]; this
0x1800d9484  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x1800d9489  nop
0x1800d948a  lea     rcx, [rsp+2A0h+var_260]
0x1800d948f  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x1800d9494  jmp     short loc_1800D94B5
0x1800d9496  mov     r8, rdi
0x1800d9499  lea     rdx, [rsp+2A0h+Src]
0x1800d949e  call    ??$_Try_emplace@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_NV?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_N@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_N@std@@PEAX@std@@_N@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,bool,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,bool>>,0>>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x1800d94a3  jmp     loc_1800D9351
0x1800d94a8  mov     bl, [rax+30h]
0x1800d94ab  lea     rcx, [rsp+2A0h+var_260]
0x1800d94b0  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x1800d94b5  mov     al, bl
0x1800d94b7  mov     rcx, [rbp+1A0h+var_30]
0x1800d94be  xor     rcx, rsp; StackCookie
0x1800d94c1  call    __security_check_cookie
0x1800d94c6  add     rsp, 288h
0x1800d94cd  pop     rdi
0x1800d94ce  pop     rsi
0x1800d94cf  pop     rbx
0x1800d94d0  pop     rbp
0x1800d94d1  retn
```
