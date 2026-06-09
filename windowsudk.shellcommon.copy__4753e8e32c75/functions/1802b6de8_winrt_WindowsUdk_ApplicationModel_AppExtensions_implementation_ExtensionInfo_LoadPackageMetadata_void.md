# winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::LoadPackageMetadata(void)

- ea: `0x1802b6de8`
- end: `0x1802b7252`
- name: `?LoadPackageMetadata@ExtensionInfo@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@AEAAXXZ`
- size: `1130`
- prototype: `void __fastcall(winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18006df80`

## callees

- `0x18000fea0`
- `0x180010940`
- `0x180015344`
- `0x180024734`
- `0x180025264`
- `0x180026860`
- `0x180037df8`
- `0x18004b6d8`
- `0x18008cef4`
- `0x1800d9000`
- `0x18015cb00`
- `0x18015d9fc`
- `0x1802b6de8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x1802b7121`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x1802b7204`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x1802b7121`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x1802b7204`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1802b6eb3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1802b6eb3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1802b6ef6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1802b6f49`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1802b6f8e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1802b6fe0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1802b7025`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1802b7069`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1802b70b2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1802b7153`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1802b719c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1802b6ef6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1802b6f49`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1802b6f8e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1802b6fe0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1802b7025`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1802b7069`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1802b70b2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1802b7153`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1802b719c`

## string_xrefs

- `0x1802b6e33`: `Software\Microsoft\Windows\CurrentVersion\Shell\Update`
- `0x1802b6f81`: `BlockIncompatible`
- `0x1802b6f3c`: `ReportIncompatible`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::LoadPackageMetadata(
        winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo *this)
{
  int v2; // esi
  __int64 v3; // rbx
  __int64 v4; // rax
  __int64 v5; // rax
  HKEY *phkResult; // rax
  const WCHAR *v7; // rdx
  wchar_t *i; // rcx
  _DWORD *v9; // rdx
  wchar_t *v10; // rax
  wchar_t *j; // rcx
  _DWORD *v12; // rdx
  wchar_t *v13; // rax
  _BYTE v14[32]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v15[32]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v16[32]; // [rsp+80h] [rbp-80h] BYREF
  DWORD pcbData; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t *Context; // [rsp+A8h] [rbp-58h] BYREF
  wchar_t *v19; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int pvData; // [rsp+B8h] [rbp-48h] BYREF
  int v21; // [rsp+BCh] [rbp-44h] BYREF
  HKEY hkey; // [rsp+C0h] [rbp-40h] BYREF
  PVOID v23; // [rsp+C8h] [rbp-38h] BYREF
  LPCWSTR lpSubKey[4]; // [rsp+D0h] [rbp-30h] BYREF

  v2 = 100000;
  *((_DWORD *)this + 128) = 100000;
  hkey = 0;
  v3 = std::wstring::wstring(v16, L"\\Packages\\");
  v4 = std::wstring::wstring(v15, L"Software\\Microsoft\\Windows\\CurrentVersion\\Shell\\Update");
  v5 = std::operator+<wchar_t>(v14, v4, v3);
  std::operator+<wchar_t>(lpSubKey, v5, (char *)this + 136);
  std::filesystem::path::~path((std::filesystem::path *)v14);
  std::filesystem::path::~path((std::filesystem::path *)v15);
  std::filesystem::path::~path((std::filesystem::path *)v16);
  phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hkey);
  v7 = (const WCHAR *)lpSubKey;
  if ( lpSubKey[3] > (LPCWSTR)7 )
    v7 = lpSubKey[0];
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, v7, 0, 1u, phkResult) )
  {
    pvData = 0;
    pcbData = 4;
    if ( !RegGetValueW(hkey, 0, L"Priority", 0x18u, 0, &pvData, &pcbData) )
    {
      if ( pvData < 0x186A0 )
        v2 = pvData;
      *((_DWORD *)this + 128) = v2;
    }
    *((_BYTE *)this + 516) = winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::CheckPackageCompatibility(this);
    pvData = 0;
    pcbData = 4;
    if ( !RegGetValueW(hkey, 0, L"ReportIncompatible", 0x18u, 0, &pvData, &pcbData) )
      *((_BYTE *)this + 519) = pvData != 0;
    pvData = 0;
    pcbData = 4;
    if ( !RegGetValueW(hkey, 0, L"BlockIncompatible", 0x18u, 0, &pvData, &pcbData) )
      *((_BYTE *)this + 520) = pvData != 0;
    if ( *((_DWORD *)this + 95) != 1 )
    {
      pvData = 0;
      pcbData = 4;
      if ( !RegGetValueW(hkey, 0, L"RequireAllVelocity", 0x18u, 0, &pvData, &pcbData) )
        *((_BYTE *)this + 517) = pvData != 0;
      pvData = 0;
      pcbData = 4;
      if ( !RegGetValueW(hkey, 0, L"InvertVelocityCheck", 0x18u, 0, &pvData, &pcbData) )
        *((_BYTE *)this + 518) = pvData != 0;
      pcbData = 0;
      if ( !RegGetValueW(hkey, 0, L"VelocityId", 2u, 0, 0, &pcbData) )
      {
        v23 = 0;
        wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(
          &v23,
          0,
          pcbData);
        if ( !RegGetValueW(hkey, 0, L"VelocityId", 2u, 0, v23, &pcbData) )
        {
          Context = 0;
          for ( i = (wchar_t *)v23; ; i = 0 )
          {
            v10 = wcstok_s(i, L",", &Context);
            if ( !v10 )
              break;
            if ( *v10 )
            {
              v21 = 0;
              if ( swscanf_s(v10, L"%u", &v21) == 1 )
              {
                if ( v21 )
                {
                  v9 = (_DWORD *)*((_QWORD *)this + 59);
                  if ( v9 == *((_DWORD **)this + 60) )
                  {
                    std::vector<unsigned int>::_Emplace_reallocate<unsigned int const &>((char *)this + 464, v9, &v21);
                  }
                  else
                  {
                    *v9 = v21;
                    *((_QWORD *)this + 59) += 4LL;
                  }
                }
              }
            }
          }
        }
        pcbData = 0;
        if ( !RegGetValueW(hkey, 0, L"CFROnlyVelocityId", 2u, 0, 0, &pcbData) )
        {
          Context = 0;
          wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(
            &Context,
            0,
            pcbData);
          if ( !RegGetValueW(hkey, 0, L"CFROnlyVelocityId", 2u, 0, Context, &pcbData) )
          {
            v19 = 0;
            for ( j = Context; ; j = 0 )
            {
              v13 = wcstok_s(j, L",", &v19);
              if ( !v13 )
                break;
              if ( *v13 )
              {
                v21 = 0;
                if ( swscanf_s(v13, L"%u", &v21) == 1 )
                {
                  if ( v21 )
                  {
                    v12 = (_DWORD *)*((_QWORD *)this + 62);
                    if ( v12 == *((_DWORD **)this + 63) )
                    {
                      std::vector<unsigned int>::_Emplace_reallocate<unsigned int const &>(
                        (char *)this + 488,
                        v12,
                        &v21);
                    }
                    else
                    {
                      *v12 = v21;
                      *((_QWORD *)this + 62) += 4LL;
                    }
                  }
                }
              }
            }
          }
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&Context);
        }
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v23);
      }
    }
  }
  std::filesystem::path::~path((std::filesystem::path *)lpSubKey);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
}

```

## disassembly

```asm
0x1802b6de8  push    rbp
0x1802b6dea  push    rbx
0x1802b6deb  push    rsi
0x1802b6dec  push    rdi
0x1802b6ded  push    r14
0x1802b6def  push    r15
0x1802b6df1  lea     rbp, [rsp-8]
0x1802b6df6  sub     rsp, 108h
0x1802b6dfd  mov     rax, cs:__security_cookie
0x1802b6e04  xor     rax, rsp
0x1802b6e07  mov     [rbp+30h+var_40], rax
0x1802b6e0b  mov     rdi, rcx
0x1802b6e0e  mov     esi, 186A0h
0x1802b6e13  mov     [rcx+200h], esi
0x1802b6e19  xor     r14d, r14d
0x1802b6e1c  mov     [rbp+30h+hkey], r14
0x1802b6e20  lea     rdx, aPackages; "\\Packages\\"
0x1802b6e27  lea     rcx, [rbp+30h+var_B0]
0x1802b6e2b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1802b6e30  mov     rbx, rax
0x1802b6e33  lea     rdx, ?c_shellUpdateRegKey@Update@Shell@Internal@Windows@@3QB_WB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1802b6e3a  lea     rcx, [rsp+130h+var_D0]
0x1802b6e3f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1802b6e44  nop
0x1802b6e45  mov     r8, rbx
0x1802b6e48  mov     rdx, rax
0x1802b6e4b  lea     rcx, [rsp+130h+var_F0]
0x1802b6e50  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@0@Z; std::operator+<wchar_t>(std::wstring &&,std::wstring &&)
0x1802b6e55  nop
0x1802b6e56  lea     r8, [rdi+88h]
0x1802b6e5d  mov     rdx, rax
0x1802b6e60  lea     rcx, [rbp+30h+lpSubKey]
0x1802b6e64  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<wchar_t>(std::wstring &&,std::wstring const &)
0x1802b6e69  nop
0x1802b6e6a  lea     rcx, [rsp+130h+var_F0]; this
0x1802b6e6f  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x1802b6e74  nop
0x1802b6e75  lea     rcx, [rsp+130h+var_D0]; this
0x1802b6e7a  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x1802b6e7f  nop
0x1802b6e80  lea     rcx, [rbp+30h+var_B0]; this
0x1802b6e84  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x1802b6e89  lea     rcx, [rbp+30h+hkey]
0x1802b6e8d  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1802b6e92  lea     rdx, [rbp+30h+lpSubKey]
0x1802b6e96  cmp     [rbp+30h+var_48], 7
0x1802b6e9b  cmova   rdx, [rbp+30h+lpSubKey]; lpSubKey
0x1802b6ea0  mov     [rsp+130h+phkResult], rax; phkResult
0x1802b6ea5  lea     r9d, [r14+1]; samDesired
0x1802b6ea9  xor     r8d, r8d; ulOptions
0x1802b6eac  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1802b6eb3  call    cs:__imp_RegOpenKeyExW
0x1802b6eb9  test    eax, eax
0x1802b6ebb  jnz     loc_1802B7223
0x1802b6ec1  mov     [rbp+30h+var_78], r14d
0x1802b6ec5  lea     ebx, [rax+4]
0x1802b6ec8  mov     [rbp+30h+var_90], ebx
0x1802b6ecb  lea     rax, [rbp+30h+var_90]
0x1802b6ecf  mov     [rsp+130h+pcbData], rax; pcbData
0x1802b6ed4  lea     rax, [rbp+30h+var_78]
0x1802b6ed8  mov     [rsp+130h+pvData], rax; pvData
0x1802b6edd  mov     [rsp+130h+phkResult], r14; pdwType
0x1802b6ee2  lea     r15d, [r14+18h]
0x1802b6ee6  mov     r9d, r15d; dwFlags
0x1802b6ee9  lea     r8, aPriority; "Priority"
0x1802b6ef0  xor     edx, edx; lpSubKey
0x1802b6ef2  mov     rcx, [rbp+30h+hkey]; hkey
0x1802b6ef6  call    cs:__imp_RegGetValueW
0x1802b6efc  test    eax, eax
0x1802b6efe  jnz     short loc_1802B6F0D
0x1802b6f00  cmp     [rbp+30h+var_78], esi
0x1802b6f03  cmovb   esi, [rbp+30h+var_78]
0x1802b6f07  mov     [rdi+200h], esi
0x1802b6f0d  mov     rcx, rdi; this
0x1802b6f10  call    ?CheckPackageCompatibility@ExtensionInfo@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@AEAA_NXZ; winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::CheckPackageCompatibility(void)
0x1802b6f15  mov     [rdi+204h], al
0x1802b6f1b  mov     [rbp+30h+var_78], r14d
0x1802b6f1f  mov     [rbp+30h+var_90], ebx
0x1802b6f22  lea     rax, [rbp+30h+var_90]
0x1802b6f26  mov     [rsp+130h+pcbData], rax; pcbData
0x1802b6f2b  lea     rax, [rbp+30h+var_78]
0x1802b6f2f  mov     [rsp+130h+pvData], rax; pvData
0x1802b6f34  mov     [rsp+130h+phkResult], r14; pdwType
0x1802b6f39  mov     r9d, r15d; dwFlags
0x1802b6f3c  lea     r8, aReportincompat; "ReportIncompatible"
0x1802b6f43  xor     edx, edx; lpSubKey
0x1802b6f45  mov     rcx, [rbp+30h+hkey]; hkey
0x1802b6f49  call    cs:__imp_RegGetValueW
0x1802b6f4f  test    eax, eax
0x1802b6f51  jnz     short loc_1802B6F60
0x1802b6f53  cmp     [rbp+30h+var_78], r14d
0x1802b6f57  setnz   al
0x1802b6f5a  mov     [rdi+207h], al
0x1802b6f60  mov     [rbp+30h+var_78], r14d
0x1802b6f64  mov     [rbp+30h+var_90], ebx
0x1802b6f67  lea     rax, [rbp+30h+var_90]
0x1802b6f6b  mov     [rsp+130h+pcbData], rax; pcbData
0x1802b6f70  lea     rax, [rbp+30h+var_78]
0x1802b6f74  mov     [rsp+130h+pvData], rax; pvData
0x1802b6f79  mov     [rsp+130h+phkResult], r14; pdwType
0x1802b6f7e  mov     r9d, r15d; dwFlags
0x1802b6f81  lea     r8, aBlockincompati; "BlockIncompatible"
0x1802b6f88  xor     edx, edx; lpSubKey
0x1802b6f8a  mov     rcx, [rbp+30h+hkey]; hkey
0x1802b6f8e  call    cs:__imp_RegGetValueW
0x1802b6f94  test    eax, eax
0x1802b6f96  jnz     short loc_1802B6FA5
0x1802b6f98  cmp     [rbp+30h+var_78], r14d
0x1802b6f9c  setnz   al
0x1802b6f9f  mov     [rdi+208h], al
0x1802b6fa5  cmp     dword ptr [rdi+17Ch], 1
0x1802b6fac  jz      loc_1802B7223
0x1802b6fb2  mov     [rbp+30h+var_78], r14d
0x1802b6fb6  mov     [rbp+30h+var_90], ebx
0x1802b6fb9  lea     rax, [rbp+30h+var_90]
0x1802b6fbd  mov     [rsp+130h+pcbData], rax; pcbData
0x1802b6fc2  lea     rax, [rbp+30h+var_78]
0x1802b6fc6  mov     [rsp+130h+pvData], rax; pvData
0x1802b6fcb  mov     [rsp+130h+phkResult], r14; pdwType
0x1802b6fd0  mov     r9d, r15d; dwFlags
0x1802b6fd3  lea     r8, aRequireallvelo; "RequireAllVelocity"
0x1802b6fda  xor     edx, edx; lpSubKey
0x1802b6fdc  mov     rcx, [rbp+30h+hkey]; hkey
0x1802b6fe0  call    cs:__imp_RegGetValueW
0x1802b6fe6  test    eax, eax
0x1802b6fe8  jnz     short loc_1802B6FF7
0x1802b6fea  cmp     [rbp+30h+var_78], r14d
0x1802b6fee  setnz   al
0x1802b6ff1  mov     [rdi+205h], al
0x1802b6ff7  mov     [rbp+30h+var_78], r14d
0x1802b6ffb  mov     [rbp+30h+var_90], ebx
0x1802b6ffe  lea     rax, [rbp+30h+var_90]
0x1802b7002  mov     [rsp+130h+pcbData], rax; pcbData
0x1802b7007  lea     rax, [rbp+30h+var_78]
0x1802b700b  mov     [rsp+130h+pvData], rax; pvData
0x1802b7010  mov     [rsp+130h+phkResult], r14; pdwType
0x1802b7015  mov     r9d, r15d; dwFlags
0x1802b7018  lea     r8, aInvertvelocity; "InvertVelocityCheck"
0x1802b701f  xor     edx, edx; lpSubKey
0x1802b7021  mov     rcx, [rbp+30h+hkey]; hkey
0x1802b7025  call    cs:__imp_RegGetValueW
0x1802b702b  test    eax, eax
0x1802b702d  jnz     short loc_1802B703C
0x1802b702f  cmp     [rbp+30h+var_78], r14d
0x1802b7033  setnz   al
0x1802b7036  mov     [rdi+206h], al
0x1802b703c  mov     [rbp+30h+var_90], r14d
0x1802b7040  lea     rax, [rbp+30h+var_90]
0x1802b7044  mov     [rsp+130h+pcbData], rax; pcbData
0x1802b7049  mov     [rsp+130h+pvData], r14; pvData
0x1802b704e  mov     [rsp+130h+phkResult], r14; pdwType
0x1802b7053  mov     r15d, 2
0x1802b7059  mov     r9d, r15d; dwFlags
0x1802b705c  lea     r8, aVelocityid; "VelocityId"
0x1802b7063  xor     edx, edx; lpSubKey
0x1802b7065  mov     rcx, [rbp+30h+hkey]; hkey
0x1802b7069  call    cs:__imp_RegGetValueW
0x1802b706f  test    eax, eax
0x1802b7071  jnz     loc_1802B7223
0x1802b7077  mov     [rbp+30h+var_68], r14
0x1802b707b  mov     r8d, [rbp+30h+var_90]
0x1802b707f  xor     edx, edx
0x1802b7081  lea     rcx, [rbp+30h+var_68]
0x1802b7085  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(wchar_t const *,unsigned __int64)
0x1802b708a  nop
0x1802b708b  mov     rax, [rbp+30h+var_68]
0x1802b708f  lea     rcx, [rbp+30h+var_90]
0x1802b7093  mov     [rsp+130h+pcbData], rcx; pcbData
0x1802b7098  mov     [rsp+130h+pvData], rax; pvData
0x1802b709d  mov     [rsp+130h+phkResult], r14; pdwType
0x1802b70a2  mov     r9d, r15d; dwFlags
0x1802b70a5  lea     r8, aVelocityid; "VelocityId"
0x1802b70ac  xor     edx, edx; lpSubKey
0x1802b70ae  mov     rcx, [rbp+30h+hkey]; hkey
0x1802b70b2  call    cs:__imp_RegGetValueW
0x1802b70b8  lea     rsi, Delimiter; ","
0x1802b70bf  test    eax, eax
0x1802b70c1  jnz     short loc_1802B712C
0x1802b70c3  mov     [rbp+30h+Context], r14
0x1802b70c7  mov     rcx, [rbp+30h+var_68]
0x1802b70cb  jmp     short loc_1802B711A
0x1802b70cd  cmp     [rax], r14w
0x1802b70d1  jz      short loc_1802B7118
0x1802b70d3  mov     [rbp+30h+var_74], r14d
0x1802b70d7  lea     r8, [rbp+30h+var_74]
0x1802b70db  lea     rdx, aU; "%u"
0x1802b70e2  mov     rcx, rax; Buffer
0x1802b70e5  call    swscanf_s
0x1802b70ea  cmp     eax, 1
0x1802b70ed  jnz     short loc_1802B7118
0x1802b70ef  mov     eax, [rbp+30h+var_74]
0x1802b70f2  test    eax, eax
0x1802b70f4  jz      short loc_1802B7118
0x1802b70f6  lea     rcx, [rdi+1D0h]
0x1802b70fd  mov     rdx, [rcx+8]
0x1802b7101  cmp     rdx, [rcx+10h]
0x1802b7105  jz      short loc_1802B710F
0x1802b7107  mov     [rdx], eax
0x1802b7109  add     [rcx+8], rbx
0x1802b710d  jmp     short loc_1802B7118
0x1802b710f  lea     r8, [rbp+30h+var_74]
0x1802b7113  call    ??$_Emplace_reallocate@AEBI@?$vector@IV?$allocator@I@std@@@std@@AEAAPEAIQEAIAEBI@Z; std::vector<uint>::_Emplace_reallocate<uint const &>(uint * const,uint const &)
0x1802b7118  xor     ecx, ecx; String
0x1802b711a  lea     r8, [rbp+30h+Context]; Context
0x1802b711e  mov     rdx, rsi; Delimiter
0x1802b7121  call    cs:__imp_wcstok_s
0x1802b7127  test    rax, rax
0x1802b712a  jnz     short loc_1802B70CD
0x1802b712c  mov     [rbp+30h+var_90], r14d
0x1802b7130  lea     rax, [rbp+30h+var_90]
0x1802b7134  mov     [rsp+130h+pcbData], rax; pcbData
0x1802b7139  mov     [rsp+130h+pvData], r14; pvData
0x1802b713e  mov     [rsp+130h+phkResult], r14; pdwType
0x1802b7143  mov     r9d, r15d; dwFlags
0x1802b7146  lea     r8, aCfronlyvelocit; "CFROnlyVelocityId"
0x1802b714d  xor     edx, edx; lpSubKey
0x1802b714f  mov     rcx, [rbp+30h+hkey]; hkey
0x1802b7153  call    cs:__imp_RegGetValueW
0x1802b7159  test    eax, eax
0x1802b715b  jnz     loc_1802B7219
0x1802b7161  mov     [rbp+30h+Context], r14
0x1802b7165  mov     r8d, [rbp+30h+var_90]
0x1802b7169  xor     edx, edx
0x1802b716b  lea     rcx, [rbp+30h+Context]
0x1802b716f  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(wchar_t const *,unsigned __int64)
0x1802b7174  nop
0x1802b7175  mov     rax, [rbp+30h+Context]
0x1802b7179  lea     rcx, [rbp+30h+var_90]
0x1802b717d  mov     [rsp+130h+pcbData], rcx; pcbData
0x1802b7182  mov     [rsp+130h+pvData], rax; pvData
0x1802b7187  mov     [rsp+130h+phkResult], r14; pdwType
0x1802b718c  mov     r9d, r15d; dwFlags
0x1802b718f  lea     r8, aCfronlyvelocit; "CFROnlyVelocityId"
0x1802b7196  xor     edx, edx; lpSubKey
0x1802b7198  mov     rcx, [rbp+30h+hkey]; hkey
0x1802b719c  call    cs:__imp_RegGetValueW
0x1802b71a2  test    eax, eax
0x1802b71a4  jnz     short loc_1802B720F
0x1802b71a6  mov     [rbp+30h+var_80], r14
0x1802b71aa  mov     rcx, [rbp+30h+Context]
0x1802b71ae  jmp     short loc_1802B71FD
0x1802b71b0  cmp     [rax], r14w
0x1802b71b4  jz      short loc_1802B71FB
0x1802b71b6  mov     [rbp+30h+var_74], r14d
0x1802b71ba  lea     r8, [rbp+30h+var_74]
0x1802b71be  lea     rdx, aU; "%u"
0x1802b71c5  mov     rcx, rax; Buffer
0x1802b71c8  call    swscanf_s
0x1802b71cd  cmp     eax, 1
0x1802b71d0  jnz     short loc_1802B71FB
0x1802b71d2  mov     eax, [rbp+30h+var_74]
0x1802b71d5  test    eax, eax
0x1802b71d7  jz      short loc_1802B71FB
0x1802b71d9  lea     rcx, [rdi+1E8h]
0x1802b71e0  mov     rdx, [rcx+8]
0x1802b71e4  cmp     rdx, [rcx+10h]
0x1802b71e8  jz      short loc_1802B71F2
0x1802b71ea  mov     [rdx], eax
0x1802b71ec  add     [rcx+8], rbx
0x1802b71f0  jmp     short loc_1802B71FB
0x1802b71f2  lea     r8, [rbp+30h+var_74]
0x1802b71f6  call    ??$_Emplace_reallocate@AEBI@?$vector@IV?$allocator@I@std@@@std@@AEAAPEAIQEAIAEBI@Z; std::vector<uint>::_Emplace_reallocate<uint const &>(uint * const,uint const &)
0x1802b71fb  xor     ecx, ecx; String
0x1802b71fd  lea     r8, [rbp+30h+var_80]; Context
0x1802b7201  mov     rdx, rsi; Delimiter
0x1802b7204  call    cs:__imp_wcstok_s
0x1802b720a  test    rax, rax
0x1802b720d  jnz     short loc_1802B71B0
0x1802b720f  lea     rcx, [rbp+30h+Context]
0x1802b7213  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x1802b7218  nop
0x1802b7219  lea     rcx, [rbp+30h+var_68]
0x1802b721d  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x1802b7222  nop
0x1802b7223  lea     rcx, [rbp+30h+lpSubKey]; this
0x1802b7227  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x1802b722c  nop
0x1802b722d  lea     rcx, [rbp+30h+hkey]
0x1802b7231  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1802b7236  mov     rcx, [rbp+30h+var_40]
0x1802b723a  xor     rcx, rsp; StackCookie
0x1802b723d  call    __security_check_cookie
0x1802b7242  add     rsp, 108h
0x1802b7249  pop     r15
0x1802b724b  pop     r14
0x1802b724d  pop     rdi
0x1802b724e  pop     rsi
0x1802b724f  pop     rbx
0x1802b7250  pop     rbp
0x1802b7251  retn
```
