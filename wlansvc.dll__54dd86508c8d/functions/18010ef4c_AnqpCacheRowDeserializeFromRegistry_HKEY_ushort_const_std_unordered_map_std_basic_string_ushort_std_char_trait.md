# AnqpCacheRowDeserializeFromRegistry(HKEY__ *,ushort const *,std::unordered_map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ulong,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,ulong>>> &)

- ea: `0x18010ef4c`
- end: `0x18010f37d`
- name: `?AnqpCacheRowDeserializeFromRegistry@@YAJPEAUHKEY__@@PEBGAEAV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KU?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@@std@@@Z`
- size: `1073`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWCH lpWideCharStr)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800e18d4`

## callees

- `0x18001c9cc`
- `0x18003fda0`
- `0x18006a050`
- `0x1800ba438`
- `0x1800ba588`
- `0x1800ca87c`
- `0x180106340`
- `0x180107330`
- `0x18010d224`
- `0x18010e4f4`
- `0x18010e5ac`
- `0x18010e870`
- `0x18010ec70`
- `0x18010ef4c`
- `0x18010f384`
- `0x1801d4c10`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18010f32d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18010f32d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18010efbe`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18010efbe`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18010f031`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18010f031`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18010f14b`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18010f1da`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18010f14b`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18010f1da`

## string_xrefs

- `0x18010efd3`: `onecoreuap\net\wlan\autocfg\server\anqpcache.cpp`
- `0x18010f046`: `onecoreuap\net\wlan\autocfg\server\anqpcache.cpp`
- `0x18010f0c0`: `onecoreuap\net\wlan\autocfg\server\anqpcache.cpp`
- `0x18010f160`: `onecoreuap\net\wlan\autocfg\server\anqpcache.cpp`
- `0x18010f1ef`: `onecoreuap\net\wlan\autocfg\server\anqpcache.cpp`
- `0x18010f263`: `onecoreuap\net\wlan\autocfg\server\anqpcache.cpp`
- `0x18010f2e1`: `onecoreuap\net\wlan\autocfg\server\anqpcache.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall AnqpCacheRowDeserializeFromRegistry(HKEY hKey, LPCWCH lpWideCharStr)
{
  HKEY *v4; // rax
  unsigned int v5; // eax
  unsigned int v6; // ebx
  unsigned int v8; // eax
  unsigned int v9; // ebx
  unsigned int v10; // eax
  unsigned int v11; // ebx
  DWORD i; // ebx
  unsigned int v13; // eax
  unsigned int v14; // ebx
  unsigned int v15; // eax
  unsigned int v16; // ebx
  int v17; // eax
  unsigned int v18; // edi
  int v19; // eax
  unsigned int v20; // ebx
  __int64 v21; // rbx
  unsigned int phkResult; // [rsp+20h] [rbp-2D8h]
  unsigned int phkResulta; // [rsp+20h] [rbp-2D8h]
  unsigned int phkResultb; // [rsp+20h] [rbp-2D8h]
  unsigned int phkResultc; // [rsp+20h] [rbp-2D8h]
  HKEY hKeya; // [rsp+60h] [rbp-298h] BYREF
  DWORD cbData[2]; // [rsp+68h] [rbp-290h] BYREF
  DWORD cchValueName; // [rsp+70h] [rbp-288h] BYREF
  DWORD cValues; // [rsp+74h] [rbp-284h] BYREF
  struct wlan::legacyparser::autocfg::_HS20_ANQP_METADATA *v30; // [rsp+78h] [rbp-280h] BYREF
  LPBYTE lpData[3]; // [rsp+80h] [rbp-278h] BYREF
  struct _DOT11_SSID v32; // [rsp+98h] [rbp-260h] BYREF
  WCHAR ValueName[264]; // [rsp+C0h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2F8h] [rbp+0h]

  hKeya = 0;
  cValues = 0;
  memset(&v32, 0, sizeof(v32));
  v4 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKeya);
  v5 = RegOpenKeyExW(hKey, lpWideCharStr, 0, 0x20019u, v4);
  if ( v5 )
  {
    v6 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x8E1,
           (unsigned int)"onecoreuap\\net\\wlan\\autocfg\\server\\anqpcache.cpp",
           (const char *)v5,
           phkResult);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKeya);
    return v6;
  }
  else
  {
    v8 = RegQueryInfoKeyW(hKeya, 0, 0, 0, 0, 0, 0, &cValues, 0, 0, 0, 0);
    if ( v8 )
    {
      v9 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x8E3,
             (unsigned int)"onecoreuap\\net\\wlan\\autocfg\\server\\anqpcache.cpp",
             (const char *)v8,
             phkResulta);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKeya);
      return v9;
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          88,
          WPP_77f44af9887132860a58109bfa42ec18_Traceguids,
          lpWideCharStr);
      }
      v10 = WlanStringToSsid(lpWideCharStr);
      if ( v10 )
      {
        v11 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x8E6,
                (unsigned int)"onecoreuap\\net\\wlan\\autocfg\\server\\anqpcache.cpp",
                (const char *)v10,
                phkResulta);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKeya);
        return v11;
      }
      else
      {
        std::make_unique<wlan::legacyparser::autocfg::_HS20_ANQP_METADATA,,0>(&v30);
        for ( i = 0; i < cValues; ++i )
        {
          memset_0(ValueName, 0, 0x208u);
          cchValueName = 260;
          cbData[0] = 0;
          v13 = RegEnumValueW(hKeya, i, ValueName, &cchValueName, 0, 0, 0, cbData);
          if ( v13 )
          {
            v14 = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0x8EE,
                    (unsigned int)"onecoreuap\\net\\wlan\\autocfg\\server\\anqpcache.cpp",
                    (const char *)v13,
                    phkResultb);
            std::unique_ptr<wlan::legacyparser::autocfg::_HS20_ANQP_METADATA>::~unique_ptr<wlan::legacyparser::autocfg::_HS20_ANQP_METADATA>(&v30);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKeya);
            return v14;
          }
          std::vector<unsigned char>::vector<unsigned char>(lpData, cbData[0]);
          ++cchValueName;
          v15 = RegEnumValueW(hKeya, i, ValueName, &cchValueName, 0, 0, lpData[0], cbData);
          if ( v15 )
          {
            v16 = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0x8F5,
                    (unsigned int)"onecoreuap\\net\\wlan\\autocfg\\server\\anqpcache.cpp",
                    (const char *)v15,
                    phkResultc);
            std::vector<unsigned char>::_Tidy(lpData);
            std::unique_ptr<wlan::legacyparser::autocfg::_HS20_ANQP_METADATA>::~unique_ptr<wlan::legacyparser::autocfg::_HS20_ANQP_METADATA>(&v30);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKeya);
            return v16;
          }
          v17 = AnqpCacheRowMetadataDeserialize(
                  (wlan::legacyparser::autocfg *)lpData[0],
                  (unsigned __int8 *)cbData[0],
                  v30);
          v18 = v17;
          if ( v17 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x8F7,
              (unsigned int)"onecoreuap\\net\\wlan\\autocfg\\server\\anqpcache.cpp",
              (const char *)(unsigned int)v17,
              phkResulta);
            std::vector<unsigned char>::_Tidy(lpData);
            std::unique_ptr<wlan::legacyparser::autocfg::_HS20_ANQP_METADATA>::~unique_ptr<wlan::legacyparser::autocfg::_HS20_ANQP_METADATA>(&v30);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKeya);
            return v18;
          }
          std::vector<unsigned char>::_Tidy(lpData);
        }
        cbData[0] = 0;
        LOWORD(cbData[1]) = 0;
        v19 = AnqpCacheAddNewRow(&v32, (unsigned __int8 (*)[6])cbData);
        v20 = v19;
        if ( v19 >= 0 )
        {
          v21 = qword_1802A1948;
          std::unique_ptr<wlan::legacyparser::autocfg::_HS20_ANQP_METADATA>::operator=<std::default_delete<wlan::legacyparser::autocfg::_HS20_ANQP_METADATA>,0>(
            (__int64 *)(*(_QWORD *)(qword_1802A1948 - 8) + 120LL),
            (__int64 *)&v30);
          *(_BYTE *)(*(_QWORD *)(v21 - 8) + 112LL) = 1;
          *(_QWORD *)(*(_QWORD *)(v21 - 8) + 96LL) = GetTickCount64();
          std::unique_ptr<wlan::legacyparser::autocfg::_HS20_ANQP_METADATA>::~unique_ptr<wlan::legacyparser::autocfg::_HS20_ANQP_METADATA>(&v30);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKeya);
          return 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x8FD,
            (unsigned int)"onecoreuap\\net\\wlan\\autocfg\\server\\anqpcache.cpp",
            (const char *)(unsigned int)v19,
            phkResulta);
          std::unique_ptr<wlan::legacyparser::autocfg::_HS20_ANQP_METADATA>::~unique_ptr<wlan::legacyparser::autocfg::_HS20_ANQP_METADATA>(&v30);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKeya);
          return v20;
        }
      }
    }
  }
}

```

## disassembly

```asm
0x18010ef4c  mov     [rsp+arg_18], rbx
0x18010ef51  push    rsi
0x18010ef52  push    rdi
0x18010ef53  push    r14
0x18010ef55  sub     rsp, 2E0h
0x18010ef5c  mov     rax, cs:__security_cookie
0x18010ef63  xor     rax, rsp
0x18010ef66  mov     [rsp+2F8h+var_28], rax
0x18010ef6e  mov     rsi, r8
0x18010ef71  mov     rbx, rdx
0x18010ef74  mov     rdi, rcx
0x18010ef77  xor     r14d, r14d
0x18010ef7a  mov     [rsp+2F8h+hKey], r14
0x18010ef7f  mov     [rsp+2F8h+cValues], r14d
0x18010ef84  xorps   xmm0, xmm0
0x18010ef87  xor     eax, eax
0x18010ef89  movups  xmmword ptr [rsp+2F8h+var_260.uSSIDLength], xmm0
0x18010ef91  movups  xmmword ptr [rsp+2F8h+var_260.ucSSID+0Ch], xmm0
0x18010ef99  mov     dword ptr [rsp+2F8h+var_260.ucSSID+1Ch], eax
0x18010efa0  lea     rcx, [rsp+2F8h+hKey]
0x18010efa5  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18010efaa  mov     [rsp+2F8h+phkResult], rax; unsigned int
0x18010efaf  mov     r9d, 20019h; samDesired
0x18010efb5  xor     r8d, r8d; ulOptions
0x18010efb8  mov     rdx, rbx; lpSubKey
0x18010efbb  mov     rcx, rdi; hKey
0x18010efbe  call    cs:__imp_RegOpenKeyExW
0x18010efc4  test    eax, eax
0x18010efc6  jz      short loc_18010EFF7
0x18010efc8  mov     rcx, [rsp+2F8h]; this
0x18010efd0  mov     r9d, eax; char *
0x18010efd3  lea     r8, aOnecoreuapNetW_59; "onecoreuap\\net\\wlan\\autocfg\\server"...
0x18010efda  mov     edx, 8E1h; void *
0x18010efdf  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18010efe4  mov     ebx, eax
0x18010efe6  lea     rcx, [rsp+2F8h+hKey]
0x18010efeb  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18010eff0  mov     eax, ebx
0x18010eff2  jmp     loc_18010F358
0x18010eff7  mov     [rsp+2F8h+lpftLastWriteTime], r14; lpftLastWriteTime
0x18010effc  mov     [rsp+2F8h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x18010f001  mov     [rsp+2F8h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x18010f006  mov     [rsp+2F8h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x18010f00b  lea     rax, [rsp+2F8h+cValues]
0x18010f010  mov     [rsp+2F8h+lpcValues], rax; lpcValues
0x18010f015  mov     [rsp+2F8h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x18010f01a  mov     [rsp+2F8h+lpcbMaxSubKeyLen], r14; lpcbMaxSubKeyLen
0x18010f01f  mov     [rsp+2F8h+phkResult], r14; int
0x18010f024  xor     r9d, r9d; lpReserved
0x18010f027  xor     r8d, r8d; lpcchClass
0x18010f02a  xor     edx, edx; lpClass
0x18010f02c  mov     rcx, [rsp+2F8h+hKey]; hKey
0x18010f031  call    cs:__imp_RegQueryInfoKeyW
0x18010f037  test    eax, eax
0x18010f039  jz      short loc_18010F06A
0x18010f03b  mov     rcx, [rsp+2F8h]; this
0x18010f043  mov     r9d, eax; char *
0x18010f046  lea     r8, aOnecoreuapNetW_59; "onecoreuap\\net\\wlan\\autocfg\\server"...
0x18010f04d  mov     edx, 8E3h; void *
0x18010f052  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18010f057  mov     ebx, eax
0x18010f059  lea     rcx, [rsp+2F8h+hKey]
0x18010f05e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18010f063  mov     eax, ebx
0x18010f065  jmp     loc_18010F358
0x18010f06a  lea     rax, WPP_GLOBAL_Control
0x18010f071  mov     rcx, cs:WPP_GLOBAL_Control
0x18010f078  cmp     rcx, rax
0x18010f07b  jz      short loc_18010F0A1
0x18010f07d  cmp     byte ptr [rcx+69h], 3
0x18010f081  jb      short loc_18010F0A1
0x18010f083  test    byte ptr [rcx+6Ch], 1
0x18010f087  jz      short loc_18010F0A1
0x18010f089  mov     edx, 58h ; 'X'
0x18010f08e  mov     r9, rbx
0x18010f091  lea     r8, WPP_77f44af9887132860a58109bfa42ec18_Traceguids
0x18010f098  mov     rcx, [rcx+60h]
0x18010f09c  call    WPP_SF_S
0x18010f0a1  lea     rdx, [rsp+2F8h+var_260]
0x18010f0a9  mov     rcx, rbx; lpWideCharStr
0x18010f0ac  call    WlanStringToSsid
0x18010f0b1  test    eax, eax
0x18010f0b3  jz      short loc_18010F0E4
0x18010f0b5  mov     rcx, [rsp+2F8h]; this
0x18010f0bd  mov     r9d, eax; char *
0x18010f0c0  lea     r8, aOnecoreuapNetW_59; "onecoreuap\\net\\wlan\\autocfg\\server"...
0x18010f0c7  mov     edx, 8E6h; void *
0x18010f0cc  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18010f0d1  mov     ebx, eax
0x18010f0d3  lea     rcx, [rsp+2F8h+hKey]
0x18010f0d8  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18010f0dd  mov     eax, ebx
0x18010f0df  jmp     loc_18010F358
0x18010f0e4  lea     rcx, [rsp+2F8h+var_280]
0x18010f0e9  call    ??$make_unique@U_HS20_ANQP_METADATA@autocfg@legacyparser@wlan@@$$V$0A@@std@@YA?AV?$unique_ptr@U_HS20_ANQP_METADATA@autocfg@legacyparser@wlan@@U?$default_delete@U_HS20_ANQP_METADATA@autocfg@legacyparser@wlan@@@std@@@0@XZ; std::make_unique<wlan::legacyparser::autocfg::_HS20_ANQP_METADATA,,0>(void)
0x18010f0ee  nop
0x18010f0ef  mov     ebx, r14d
0x18010f0f2  cmp     ebx, [rsp+2F8h+cValues]
0x18010f0f6  jnb     loc_18010F2B3
0x18010f0fc  xor     edx, edx; Val
0x18010f0fe  mov     r8d, 208h; Size
0x18010f104  lea     rcx, [rsp+2F8h+ValueName]; void *
0x18010f10c  call    memset_0
0x18010f111  mov     [rsp+2F8h+cchValueName], 104h
0x18010f119  mov     [rsp+2F8h+cbData], r14d
0x18010f11e  lea     rax, [rsp+2F8h+cbData]
0x18010f123  mov     [rsp+2F8h+lpcValues], rax; lpcbData
0x18010f128  mov     [rsp+2F8h+lpcbMaxClassLen], r14; lpData
0x18010f12d  mov     [rsp+2F8h+lpcbMaxSubKeyLen], r14; lpType
0x18010f132  mov     [rsp+2F8h+phkResult], r14; unsigned int
0x18010f137  lea     r9, [rsp+2F8h+cchValueName]; lpcchValueName
0x18010f13c  lea     r8, [rsp+2F8h+ValueName]; lpValueName
0x18010f144  mov     edx, ebx; dwIndex
0x18010f146  mov     rcx, [rsp+2F8h+hKey]; hKey
0x18010f14b  call    cs:__imp_RegEnumValueW
0x18010f151  test    eax, eax
0x18010f153  jz      short loc_18010F18F
0x18010f155  mov     rcx, [rsp+2F8h]; this
0x18010f15d  mov     r9d, eax; char *
0x18010f160  lea     r8, aOnecoreuapNetW_59; "onecoreuap\\net\\wlan\\autocfg\\server"...
0x18010f167  mov     edx, 8EEh; void *
0x18010f16c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18010f171  mov     ebx, eax
0x18010f173  lea     rcx, [rsp+2F8h+var_280]
0x18010f178  call    ??1?$unique_ptr@U_HS20_ANQP_METADATA@autocfg@legacyparser@wlan@@U?$default_delete@U_HS20_ANQP_METADATA@autocfg@legacyparser@wlan@@@std@@@std@@QEAA@XZ; std::unique_ptr<wlan::legacyparser::autocfg::_HS20_ANQP_METADATA>::~unique_ptr<wlan::legacyparser::autocfg::_HS20_ANQP_METADATA>(void)
0x18010f17d  nop
0x18010f17e  lea     rcx, [rsp+2F8h+hKey]
0x18010f183  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18010f188  mov     eax, ebx
0x18010f18a  jmp     loc_18010F358
0x18010f18f  mov     edx, [rsp+2F8h+cbData]
0x18010f193  lea     rcx, [rsp+2F8h+lpData]
0x18010f19b  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x18010f1a0  nop
0x18010f1a1  inc     [rsp+2F8h+cchValueName]
0x18010f1a5  mov     rax, [rsp+2F8h+lpData]
0x18010f1ad  lea     rcx, [rsp+2F8h+cbData]
0x18010f1b2  mov     [rsp+2F8h+lpcValues], rcx; lpcbData
0x18010f1b7  mov     [rsp+2F8h+lpcbMaxClassLen], rax; lpData
0x18010f1bc  mov     [rsp+2F8h+lpcbMaxSubKeyLen], r14; lpType
0x18010f1c1  mov     [rsp+2F8h+phkResult], r14; unsigned int
0x18010f1c6  lea     r9, [rsp+2F8h+cchValueName]; lpcchValueName
0x18010f1cb  lea     r8, [rsp+2F8h+ValueName]; lpValueName
0x18010f1d3  mov     edx, ebx; dwIndex
0x18010f1d5  mov     rcx, [rsp+2F8h+hKey]; hKey
0x18010f1da  call    cs:__imp_RegEnumValueW
0x18010f1e0  test    eax, eax
0x18010f1e2  jz      short loc_18010F22C
0x18010f1e4  mov     rcx, [rsp+2F8h]; this
0x18010f1ec  mov     r9d, eax; char *
0x18010f1ef  lea     r8, aOnecoreuapNetW_59; "onecoreuap\\net\\wlan\\autocfg\\server"...
0x18010f1f6  mov     edx, 8F5h; void *
0x18010f1fb  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18010f200  mov     ebx, eax
0x18010f202  lea     rcx, [rsp+2F8h+lpData]
0x18010f20a  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18010f20f  nop
0x18010f210  lea     rcx, [rsp+2F8h+var_280]
0x18010f215  call    ??1?$unique_ptr@U_HS20_ANQP_METADATA@autocfg@legacyparser@wlan@@U?$default_delete@U_HS20_ANQP_METADATA@autocfg@legacyparser@wlan@@@std@@@std@@QEAA@XZ; std::unique_ptr<wlan::legacyparser::autocfg::_HS20_ANQP_METADATA>::~unique_ptr<wlan::legacyparser::autocfg::_HS20_ANQP_METADATA>(void)
0x18010f21a  nop
0x18010f21b  lea     rcx, [rsp+2F8h+hKey]
0x18010f220  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18010f225  mov     eax, ebx
0x18010f227  jmp     loc_18010F358
0x18010f22c  mov     rax, [rsp+2F8h+var_280]
0x18010f231  mov     [rsp+2F8h+phkResult], rax; int
0x18010f236  mov     r9, rsi
0x18010f239  lea     r8, [rsp+2F8h+ValueName]
0x18010f241  mov     edx, [rsp+2F8h+cbData]; unsigned __int8 *
0x18010f245  mov     rcx, [rsp+2F8h+lpData]; this
0x18010f24d  call    ?AnqpCacheRowMetadataDeserialize@@YAJPEAEKPEBGAEAV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KU?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@@std@@PEAU_HS20_ANQP_METADATA@autocfg@legacyparser@wlan@@@Z; AnqpCacheRowMetadataDeserialize(uchar *,ulong,ushort const *,std::unordered_map<std::wstring,ulong> &,wlan::legacyparser::autocfg::_HS20_ANQP_METADATA *)
0x18010f252  mov     edi, eax
0x18010f254  test    eax, eax
0x18010f256  jns     short loc_18010F29F
0x18010f258  mov     rcx, [rsp+2F8h]; this
0x18010f260  mov     r9d, eax; char *
0x18010f263  lea     r8, aOnecoreuapNetW_59; "onecoreuap\\net\\wlan\\autocfg\\server"...
0x18010f26a  mov     edx, 8F7h; void *
0x18010f26f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010f274  nop
0x18010f275  lea     rcx, [rsp+2F8h+lpData]
0x18010f27d  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18010f282  nop
0x18010f283  lea     rcx, [rsp+2F8h+var_280]
0x18010f288  call    ??1?$unique_ptr@U_HS20_ANQP_METADATA@autocfg@legacyparser@wlan@@U?$default_delete@U_HS20_ANQP_METADATA@autocfg@legacyparser@wlan@@@std@@@std@@QEAA@XZ; std::unique_ptr<wlan::legacyparser::autocfg::_HS20_ANQP_METADATA>::~unique_ptr<wlan::legacyparser::autocfg::_HS20_ANQP_METADATA>(void)
0x18010f28d  nop
0x18010f28e  lea     rcx, [rsp+2F8h+hKey]
0x18010f293  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18010f298  mov     eax, edi
0x18010f29a  jmp     loc_18010F358
0x18010f29f  lea     rcx, [rsp+2F8h+lpData]
0x18010f2a7  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18010f2ac  inc     ebx
0x18010f2ae  jmp     loc_18010F0F2
0x18010f2b3  xor     eax, eax
0x18010f2b5  mov     [rsp+2F8h+cbData], eax
0x18010f2b9  mov     [rsp+2F8h+var_28C], ax
0x18010f2be  lea     rdx, [rsp+2F8h+cbData]; unsigned __int8 (*)[6]
0x18010f2c3  lea     rcx, [rsp+2F8h+var_260]; struct _DOT11_SSID *
0x18010f2cb  call    ?AnqpCacheAddNewRow@@YAJPEAU_DOT11_SSID@@PEAY05E@Z; AnqpCacheAddNewRow(_DOT11_SSID *,uchar (*)[6])
0x18010f2d0  mov     ebx, eax
0x18010f2d2  test    eax, eax
0x18010f2d4  jns     short loc_18010F30C
0x18010f2d6  mov     rcx, [rsp+2F8h]; this
0x18010f2de  mov     r9d, eax; char *
0x18010f2e1  lea     r8, aOnecoreuapNetW_59; "onecoreuap\\net\\wlan\\autocfg\\server"...
0x18010f2e8  mov     edx, 8FDh; void *
0x18010f2ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010f2f2  nop
0x18010f2f3  lea     rcx, [rsp+2F8h+var_280]
0x18010f2f8  call    ??1?$unique_ptr@U_HS20_ANQP_METADATA@autocfg@legacyparser@wlan@@U?$default_delete@U_HS20_ANQP_METADATA@autocfg@legacyparser@wlan@@@std@@@std@@QEAA@XZ; std::unique_ptr<wlan::legacyparser::autocfg::_HS20_ANQP_METADATA>::~unique_ptr<wlan::legacyparser::autocfg::_HS20_ANQP_METADATA>(void)
0x18010f2fd  nop
0x18010f2fe  lea     rcx, [rsp+2F8h+hKey]
0x18010f303  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18010f308  mov     eax, ebx
0x18010f30a  jmp     short loc_18010F358
0x18010f30c  mov     rbx, cs:qword_1802A1948
0x18010f313  mov     rcx, [rbx-8]
0x18010f317  add     rcx, 78h ; 'x'
0x18010f31b  lea     rdx, [rsp+2F8h+var_280]
0x18010f320  call    ??$?4U?$default_delete@U_HS20_ANQP_METADATA@autocfg@legacyparser@wlan@@@std@@$0A@@?$unique_ptr@U_HS20_ANQP_METADATA@autocfg@legacyparser@wlan@@U?$default_delete@U_HS20_ANQP_METADATA@autocfg@legacyparser@wlan@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<wlan::legacyparser::autocfg::_HS20_ANQP_METADATA>::operator=<std::default_delete<wlan::legacyparser::autocfg::_HS20_ANQP_METADATA>,0>(std::unique_ptr<wlan::legacyparser::autocfg::_HS20_ANQP_METADATA> &&)
0x18010f325  mov     rax, [rbx-8]
0x18010f329  mov     byte ptr [rax+70h], 1
0x18010f32d  call    cs:__imp_GetTickCount64
0x18010f333  mov     rcx, [rbx-8]
0x18010f337  mov     [rcx+60h], rax
0x18010f33b  lea     rcx, [rsp+2F8h+var_280]
0x18010f340  call    ??1?$unique_ptr@U_HS20_ANQP_METADATA@autocfg@legacyparser@wlan@@U?$default_delete@U_HS20_ANQP_METADATA@autocfg@legacyparser@wlan@@@std@@@std@@QEAA@XZ; std::unique_ptr<wlan::legacyparser::autocfg::_HS20_ANQP_METADATA>::~unique_ptr<wlan::legacyparser::autocfg::_HS20_ANQP_METADATA>(void)
0x18010f345  nop
0x18010f346  lea     rcx, [rsp+2F8h+hKey]
0x18010f34b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18010f350  xor     eax, eax
0x18010f352  jmp     short loc_18010F358
0x18010f354  mov     eax, [rsp+2F8h+cValues]
0x18010f358  mov     rcx, [rsp+2F8h+var_28]
0x18010f360  xor     rcx, rsp; StackCookie
0x18010f363  call    __security_check_cookie
0x18010f368  mov     rbx, [rsp+2F8h+arg_18]
0x18010f370  add     rsp, 2E0h
0x18010f377  pop     r14
0x18010f379  pop     rdi
0x18010f37a  pop     rsi
0x18010f37b  retn
```
