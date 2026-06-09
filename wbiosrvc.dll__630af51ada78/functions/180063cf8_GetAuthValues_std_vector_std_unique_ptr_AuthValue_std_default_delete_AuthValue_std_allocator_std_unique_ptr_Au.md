# GetAuthValues(std::vector<std::unique_ptr<AuthValue,std::default_delete<AuthValue>>,std::allocator<std::unique_ptr<AuthValue,std::default_delete<AuthValue>>>> *)

- ea: `0x180063cf8`
- end: `0x18006418a`
- name: `?GetAuthValues@@YAJPEAV?$vector@V?$unique_ptr@VAuthValue@@U?$default_delete@VAuthValue@@@std@@@std@@V?$allocator@V?$unique_ptr@VAuthValue@@U?$default_delete@VAuthValue@@@std@@@std@@@2@@std@@@Z`
- size: `1170`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800260f8`

## callees

- `0x18000367c`
- `0x180011d90`
- `0x180014110`
- `0x18001451c`
- `0x180014854`
- `0x180014894`
- `0x180014914`
- `0x18001693c`
- `0x180016e10`
- `0x180031b14`
- `0x180035d78`
- `0x18003c8dc`
- `0x18005388c`
- `0x180063cf8`
- `0x180064190`
- `0x180068f60`
- `0x18006963c`
- `0x180072d58`
- `0x180072da0`
- `0x180092044`
- `0x18009207c`
- `0x1800962e8`
- `0x180096310`
- `0x180096438`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180063e2b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180063e5d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180063ef3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180063f1f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180064025`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006414b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180063e2b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180063e5d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180063ef3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180063f1f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180064025`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006414b`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180063ec1`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180063ec1`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180063fd7`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180063fd7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180063df4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180063df4`

## string_xrefs

- `0x180063d3e`: `onecore\ds\security\biometrics\service\server\authvalue.cpp`
- `0x180063d98`: `onecore\ds\security\biometrics\service\server\authvalue.cpp`
- `0x180063e0b`: `onecore\ds\security\biometrics\service\server\authvalue.cpp`
- `0x180063ed6`: `onecore\ds\security\biometrics\service\server\authvalue.cpp`
- `0x180063fec`: `onecore\ds\security\biometrics\service\server\authvalue.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall GetAuthValues(__int64 *a1, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned int v5; // esi
  __int64 v7; // rdx
  int WinBioRegistryLocation; // eax
  const WCHAR *v9; // rax
  PHKEY v10; // r8
  unsigned int v11; // eax
  signed int v12; // ebx
  unsigned int v13; // eax
  unsigned int v14; // ebx
  DWORD i; // ebx
  unsigned int v16; // eax
  unsigned int v17; // ebx
  const unsigned __int16 *v18; // r15
  AuthValue *v19; // r14
  __int64 v20; // r8
  __int64 v21; // r9
  int phkResult; // [rsp+20h] [rbp-108h]
  unsigned int phkResulta; // [rsp+20h] [rbp-108h]
  unsigned int phkResultb; // [rsp+20h] [rbp-108h]
  unsigned int phkResultc; // [rsp+20h] [rbp-108h]
  DWORD cchName; // [rsp+60h] [rbp-C8h] BYREF
  DWORD cSubKeys; // [rsp+64h] [rbp-C4h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-C0h] BYREF
  AuthValue *v29; // [rsp+70h] [rbp-B8h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+78h] [rbp-B0h] BYREF
  __int128 v31; // [rsp+80h] [rbp-A8h] BYREF
  __int64 v32; // [rsp+90h] [rbp-98h]
  LPWSTR lpName[3]; // [rsp+98h] [rbp-90h] BYREF
  _BYTE v34[32]; // [rsp+B0h] [rbp-78h] BYREF
  _BYTE v35[16]; // [rsp+D0h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]

  v5 = 0;
  cchName = 0;
  if ( a1 )
  {
    v7 = a1[1];
    if ( *a1 != v7 )
    {
      std::_Destroy_range<std::allocator<std::unique_ptr<AuthValue>>>(*a1, v7);
      a1[1] = *a1;
    }
    std::wstring::wstring(v34, v7, a3, a4);
    WinBioRegistryLocation = GetWinBioRegistryLocation((__int64)v34);
    if ( WinBioRegistryLocation < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x2E2,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\authvalue.cpp",
        (const char *)(unsigned int)WinBioRegistryLocation,
        phkResult);
    std::wstring::append(v34, L"SensorInfo\\");
    hKey = 0;
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
    v9 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v34);
    v11 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v9, 0, 0x20019u, v10);
    v12 = v11;
    if ( v11 )
    {
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0x2EC,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\authvalue.cpp",
        (const char *)v11,
        phkResulta);
      if ( v12 == 2 )
      {
        if ( hKey )
          RegCloseKey(hKey);
        std::wstring::_Tidy_deallocate(v34);
        return 0;
      }
      else
      {
        if ( v12 > 0 )
          v12 = (unsigned __int16)v12 | 0x80070000;
        if ( hKey )
          RegCloseKey(hKey);
        std::wstring::_Tidy_deallocate(v34);
        return (unsigned int)v12;
      }
    }
    else
    {
      cSubKeys = 0;
      cbMaxSubKeyLen = 0;
      v13 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
      if ( v13 )
      {
        v14 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x306,
                (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\authvalue.cpp",
                (const char *)v13,
                phkResultb);
        if ( hKey )
          RegCloseKey(hKey);
        std::wstring::_Tidy_deallocate(v34);
        return v14;
      }
      else if ( cSubKeys )
      {
        std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(&v31);
        v29 = (AuthValue *)cSubKeys;
        if ( cSubKeys > (unsigned __int64)((v32 - (__int64)v31) >> 3) )
          std::vector<std::unique_ptr<AuthValue>>::_Reallocate<0>(&v31, &v29);
        std::vector<unsigned short>::vector<unsigned short>(lpName, cbMaxSubKeyLen + 1);
        for ( i = 0; i < cSubKeys; ++i )
        {
          cchName = lpName[1] - lpName[0];
          v16 = RegEnumKeyExW(hKey, i, lpName[0], &cchName, 0, 0, 0, 0);
          if ( v16 )
          {
            v17 = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0x31E,
                    (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\authvalue.cpp",
                    (const char *)v16,
                    phkResultc);
            std::vector<unsigned short>::_Tidy(lpName);
            std::vector<std::unique_ptr<AuthValue>>::_Tidy(&v31);
            if ( hKey )
              RegCloseKey(hKey);
            std::wstring::_Tidy_deallocate(v34);
            return v17;
          }
          lpName[0][cchName] = 0;
          v18 = lpName[0];
          v19 = (AuthValue *)operator new(0x78u);
          v29 = v19;
          CWinBioUuid::Init((CWinBioUuid *)v35, v18);
          v29 = AuthValue::AuthValue(v19, (const struct CWinBioUuid *)v35, v20, v21);
          if ( *((_QWORD *)&v31 + 1) == v32 )
            std::vector<std::unique_ptr<AuthValue>>::_Emplace_reallocate<std::unique_ptr<AuthValue>>(
              (__int64 *)&v31,
              *((__int64 *)&v31 + 1),
              (__int64 *)&v29);
          else
            std::vector<std::unique_ptr<AuthValue>>::_Emplace_back_with_unused_capacity<std::unique_ptr<AuthValue>>(
              (__int64)&v31,
              (__int64 *)&v29);
          std::unique_ptr<AuthValue>::~unique_ptr<AuthValue>(&v29);
          v5 = v5 & 0xFFFFFFFC | 2;
        }
        if ( a1 != (__int64 *)&v31 )
        {
          std::vector<std::unique_ptr<AuthValue>>::_Tidy(a1);
          *(_OWORD *)a1 = v31;
          a1[2] = v32;
          v31 = 0;
          v32 = 0;
        }
        std::vector<unsigned short>::_Tidy(lpName);
        std::vector<std::unique_ptr<AuthValue>>::_Tidy(&v31);
        if ( hKey )
          RegCloseKey(hKey);
        std::wstring::_Tidy_deallocate(v34);
        return 0;
      }
      else
      {
        if ( hKey )
          RegCloseKey(hKey);
        std::wstring::_Tidy_deallocate(v34);
        return 0;
      }
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2DB,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\authvalue.cpp",
      (const char *)0x80004003LL,
      phkResult);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x180063cf8  push    rbx
0x180063cfa  push    rsi
0x180063cfb  push    rdi
0x180063cfc  push    r12
0x180063cfe  push    r14
0x180063d00  push    r15
0x180063d02  sub     rsp, 0F8h
0x180063d09  mov     rax, cs:__security_cookie
0x180063d10  xor     rax, rsp
0x180063d13  mov     [rsp+128h+var_48], rax
0x180063d1b  mov     rdi, rcx
0x180063d1e  xor     r12d, r12d
0x180063d21  mov     esi, r12d
0x180063d24  mov     [rsp+128h+cchName], r12d
0x180063d29  test    rcx, rcx
0x180063d2c  jnz     short loc_180063D56
0x180063d2e  mov     rcx, [rsp+128h]; this
0x180063d36  mov     ebx, 80004003h
0x180063d3b  mov     r9d, ebx; char *
0x180063d3e  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\biometrics\\serv"...
0x180063d45  mov     edx, 2DBh; void *
0x180063d4a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180063d4f  mov     eax, ebx
0x180063d51  jmp     loc_180064168
0x180063d56  mov     rdx, [rcx+8]
0x180063d5a  cmp     [rcx], rdx
0x180063d5d  jz      short loc_180063D6E
0x180063d5f  mov     rcx, [rcx]
0x180063d62  call    ??$_Destroy_range@V?$allocator@V?$unique_ptr@VAuthValue@@U?$default_delete@VAuthValue@@@std@@@std@@@std@@@std@@YAXPEAV?$unique_ptr@VAuthValue@@U?$default_delete@VAuthValue@@@std@@@0@QEAV10@AEAV?$allocator@V?$unique_ptr@VAuthValue@@U?$default_delete@VAuthValue@@@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::unique_ptr<AuthValue>>>(std::unique_ptr<AuthValue> *,std::unique_ptr<AuthValue> * const,std::allocator<std::unique_ptr<AuthValue>> &)
0x180063d67  mov     rax, [rdi]
0x180063d6a  mov     [rdi+8], rax
0x180063d6e  lea     rcx, [rsp+128h+var_78]
0x180063d76  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180063d7b  nop
0x180063d7c  lea     rcx, [rsp+128h+var_78]
0x180063d84  call    ?GetWinBioRegistryLocation@@YAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetWinBioRegistryLocation(std::wstring *)
0x180063d89  mov     rcx, [rsp+128h]; this
0x180063d91  test    eax, eax
0x180063d93  jns     short loc_180063DA9
0x180063d95  mov     r9d, eax; char *
0x180063d98  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\biometrics\\serv"...
0x180063d9f  mov     edx, 2E2h; void *
0x180063da4  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180063da9  lea     rdx, aSensorinfo; "SensorInfo\\"
0x180063db0  lea     rcx, [rsp+128h+var_78]
0x180063db8  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180063dbd  mov     [rsp+128h+hKey], r12
0x180063dc2  lea     rcx, [rsp+128h+hKey]
0x180063dc7  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180063dcc  mov     r8, rax
0x180063dcf  lea     rcx, [rsp+128h+var_78]
0x180063dd7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180063ddc  mov     rdx, rax; lpSubKey
0x180063ddf  mov     [rsp+128h+phkResult], r8; unsigned int
0x180063de4  mov     r9d, 20019h; samDesired
0x180063dea  xor     r8d, r8d; ulOptions
0x180063ded  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180063df4  call    cs:__imp_RegOpenKeyExW
0x180063dfa  mov     ebx, eax
0x180063dfc  mov     rcx, [rsp+128h]; this
0x180063e04  test    eax, eax
0x180063e06  jz      short loc_180063E78
0x180063e08  mov     r9d, eax; char *
0x180063e0b  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\biometrics\\serv"...
0x180063e12  mov     edx, 2ECh; void *
0x180063e17  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180063e1c  cmp     ebx, 2
0x180063e1f  jnz     short loc_180063E46
0x180063e21  mov     rcx, [rsp+128h+hKey]; hKey
0x180063e26  test    rcx, rcx
0x180063e29  jz      short loc_180063E32
0x180063e2b  call    cs:__imp_RegCloseKey
0x180063e31  nop
0x180063e32  lea     rcx, [rsp+128h+var_78]
0x180063e3a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180063e3f  xor     eax, eax
0x180063e41  jmp     loc_180064168
0x180063e46  test    ebx, ebx
0x180063e48  jle     short loc_180063E53
0x180063e4a  movzx   ebx, bx
0x180063e4d  or      ebx, 80070000h
0x180063e53  mov     rcx, [rsp+128h+hKey]; hKey
0x180063e58  test    rcx, rcx
0x180063e5b  jz      short loc_180063E64
0x180063e5d  call    cs:__imp_RegCloseKey
0x180063e63  nop
0x180063e64  lea     rcx, [rsp+128h+var_78]
0x180063e6c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180063e71  mov     eax, ebx
0x180063e73  jmp     loc_180064168
0x180063e78  mov     [rsp+128h+cSubKeys], r12d
0x180063e7d  mov     [rsp+128h+cbMaxSubKeyLen], r12d
0x180063e82  mov     [rsp+128h+lpftLastWriteTime], r12; lpftLastWriteTime
0x180063e87  mov     [rsp+128h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x180063e8c  mov     [rsp+128h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x180063e91  mov     [rsp+128h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x180063e96  mov     [rsp+128h+lpcValues], r12; lpcValues
0x180063e9b  mov     [rsp+128h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x180063ea0  lea     rax, [rsp+128h+cbMaxSubKeyLen]
0x180063ea5  mov     [rsp+128h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180063eaa  lea     rax, [rsp+128h+cSubKeys]
0x180063eaf  mov     [rsp+128h+phkResult], rax; unsigned int
0x180063eb4  xor     r9d, r9d; lpReserved
0x180063eb7  xor     r8d, r8d; lpcchClass
0x180063eba  xor     edx, edx; lpClass
0x180063ebc  mov     rcx, [rsp+128h+hKey]; hKey
0x180063ec1  call    cs:__imp_RegQueryInfoKeyW
0x180063ec7  test    eax, eax
0x180063ec9  jz      short loc_180063F0E
0x180063ecb  mov     rcx, [rsp+128h]; this
0x180063ed3  mov     r9d, eax; char *
0x180063ed6  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\biometrics\\serv"...
0x180063edd  mov     edx, 306h; void *
0x180063ee2  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180063ee7  mov     ebx, eax
0x180063ee9  mov     rcx, [rsp+128h+hKey]; hKey
0x180063eee  test    rcx, rcx
0x180063ef1  jz      short loc_180063EFA
0x180063ef3  call    cs:__imp_RegCloseKey
0x180063ef9  nop
0x180063efa  lea     rcx, [rsp+128h+var_78]
0x180063f02  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180063f07  mov     eax, ebx
0x180063f09  jmp     loc_180064168
0x180063f0e  cmp     [rsp+128h+cSubKeys], r12d
0x180063f13  jnz     short loc_180063F3A
0x180063f15  mov     rcx, [rsp+128h+hKey]; hKey
0x180063f1a  test    rcx, rcx
0x180063f1d  jz      short loc_180063F26
0x180063f1f  call    cs:__imp_RegCloseKey
0x180063f25  nop
0x180063f26  lea     rcx, [rsp+128h+var_78]
0x180063f2e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180063f33  xor     eax, eax
0x180063f35  jmp     loc_180064168
0x180063f3a  lea     rcx, [rsp+128h+var_A8]
0x180063f42  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x180063f47  nop
0x180063f48  mov     ecx, [rsp+128h+cSubKeys]
0x180063f4c  mov     [rsp+128h+var_B8], rcx
0x180063f51  mov     rax, [rsp+128h+var_98]
0x180063f59  sub     rax, qword ptr [rsp+128h+var_A8]
0x180063f61  sar     rax, 3
0x180063f65  cmp     rcx, rax
0x180063f68  jbe     short loc_180063F7C
0x180063f6a  lea     rdx, [rsp+128h+var_B8]
0x180063f6f  lea     rcx, [rsp+128h+var_A8]
0x180063f77  call    ??$_Reallocate@$0A@@?$vector@V?$unique_ptr@VAuthValue@@U?$default_delete@VAuthValue@@@std@@@std@@V?$allocator@V?$unique_ptr@VAuthValue@@U?$default_delete@VAuthValue@@@std@@@std@@@2@@std@@AEAAXAEA_K@Z; std::vector<std::unique_ptr<AuthValue>>::_Reallocate<0>(unsigned __int64 &)
0x180063f7c  mov     edx, [rsp+128h+cbMaxSubKeyLen]
0x180063f80  inc     edx
0x180063f82  lea     rcx, [rsp+128h+lpName]
0x180063f8a  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@_KAEBV?$allocator@G@1@@Z; std::vector<ushort>::vector<ushort>(unsigned __int64,std::allocator<ushort> const &)
0x180063f8f  nop
0x180063f90  mov     ebx, r12d
0x180063f93  cmp     ebx, [rsp+128h+cSubKeys]
0x180063f97  jnb     loc_1800640D9
0x180063f9d  mov     rax, [rsp+128h+var_88]
0x180063fa5  mov     r8, [rsp+128h+lpName]; lpName
0x180063fad  sub     rax, r8
0x180063fb0  sar     rax, 1
0x180063fb3  mov     [rsp+128h+cchName], eax
0x180063fb7  mov     [rsp+128h+lpcValues], r12; lpftLastWriteTime
0x180063fbc  mov     [rsp+128h+lpcbMaxClassLen], r12; lpcchClass
0x180063fc1  mov     [rsp+128h+lpcbMaxSubKeyLen], r12; lpClass
0x180063fc6  mov     [rsp+128h+phkResult], r12; unsigned int
0x180063fcb  lea     r9, [rsp+128h+cchName]; lpcchName
0x180063fd0  mov     edx, ebx; dwIndex
0x180063fd2  mov     rcx, [rsp+128h+hKey]; hKey
0x180063fd7  call    cs:__imp_RegEnumKeyExW
0x180063fdd  test    eax, eax
0x180063fdf  jz      short loc_180064040
0x180063fe1  mov     rcx, [rsp+128h]; this
0x180063fe9  mov     r9d, eax; char *
0x180063fec  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\biometrics\\serv"...
0x180063ff3  mov     edx, 31Eh; void *
0x180063ff8  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180063ffd  mov     ebx, eax
0x180063fff  lea     rcx, [rsp+128h+lpName]
0x180064007  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x18006400c  nop
0x18006400d  lea     rcx, [rsp+128h+var_A8]
0x180064015  call    ?_Tidy@?$vector@V?$unique_ptr@VAuthValue@@U?$default_delete@VAuthValue@@@std@@@std@@V?$allocator@V?$unique_ptr@VAuthValue@@U?$default_delete@VAuthValue@@@std@@@std@@@2@@std@@AEAAXXZ; std::vector<std::unique_ptr<AuthValue>>::_Tidy(void)
0x18006401a  nop
0x18006401b  mov     rcx, [rsp+128h+hKey]; hKey
0x180064020  test    rcx, rcx
0x180064023  jz      short loc_18006402C
0x180064025  call    cs:__imp_RegCloseKey
0x18006402b  nop
0x18006402c  lea     rcx, [rsp+128h+var_78]
0x180064034  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180064039  mov     eax, ebx
0x18006403b  jmp     loc_180064168
0x180064040  mov     edx, [rsp+128h+cchName]
0x180064044  mov     rax, [rsp+128h+lpName]
0x18006404c  mov     [rax+rdx*2], r12w
0x180064051  mov     r15, [rsp+128h+lpName]
0x180064059  mov     ecx, 78h ; 'x'; Size
0x18006405e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180064063  mov     r14, rax
0x180064066  mov     [rsp+128h+var_B8], rax
0x18006406b  mov     rdx, r15; unsigned __int16 *
0x18006406e  lea     rcx, [rsp+128h+var_58]; this
0x180064076  call    ?Init@CWinBioUuid@@AEAAXPEBG@Z; CWinBioUuid::Init(ushort const *)
0x18006407b  lea     rdx, [rsp+128h+var_58]; struct CWinBioUuid *
0x180064083  mov     rcx, r14; this
0x180064086  call    ??0AuthValue@@QEAA@AEBVCWinBioUuid@@@Z; AuthValue::AuthValue(CWinBioUuid const &)
0x18006408b  nop
0x18006408c  mov     [rsp+128h+var_B8], rax
0x180064091  mov     rdx, qword ptr [rsp+128h+var_A8+8]
0x180064099  lea     rcx, [rsp+128h+var_A8]
0x1800640a1  cmp     rdx, [rsp+128h+var_98]
0x1800640a9  jz      short loc_1800640B7
0x1800640ab  lea     rdx, [rsp+128h+var_B8]
0x1800640b0  call    ??$_Emplace_back_with_unused_capacity@V?$unique_ptr@VAuthValue@@U?$default_delete@VAuthValue@@@std@@@std@@@?$vector@V?$unique_ptr@VAuthValue@@U?$default_delete@VAuthValue@@@std@@@std@@V?$allocator@V?$unique_ptr@VAuthValue@@U?$default_delete@VAuthValue@@@std@@@std@@@2@@std@@AEAAAEAV?$unique_ptr@VAuthValue@@U?$default_delete@VAuthValue@@@std@@@1@$$QEAV21@@Z; std::vector<std::unique_ptr<AuthValue>>::_Emplace_back_with_unused_capacity<std::unique_ptr<AuthValue>>(std::unique_ptr<AuthValue> &&)
0x1800640b5  jmp     short loc_1800640C2
0x1800640b7  lea     r8, [rsp+128h+var_B8]
0x1800640bc  call    ??$_Emplace_reallocate@V?$unique_ptr@VAuthValue@@U?$default_delete@VAuthValue@@@std@@@std@@@?$vector@V?$unique_ptr@VAuthValue@@U?$default_delete@VAuthValue@@@std@@@std@@V?$allocator@V?$unique_ptr@VAuthValue@@U?$default_delete@VAuthValue@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@VAuthValue@@U?$default_delete@VAuthValue@@@std@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::unique_ptr<AuthValue>>::_Emplace_reallocate<std::unique_ptr<AuthValue>>(std::unique_ptr<AuthValue> * const,std::unique_ptr<AuthValue> &&)
0x1800640c1  nop
0x1800640c2  lea     rcx, [rsp+128h+var_B8]
0x1800640c7  call    ??1?$unique_ptr@VAuthValue@@U?$default_delete@VAuthValue@@@std@@@std@@QEAA@XZ; std::unique_ptr<AuthValue>::~unique_ptr<AuthValue>(void)
0x1800640cc  inc     ebx
0x1800640ce  and     esi, 0FFFFFFFEh
0x1800640d1  or      esi, 2
0x1800640d4  jmp     loc_180063F93
0x1800640d9  lea     rax, [rsp+128h+var_A8]
0x1800640e1  cmp     rdi, rax
0x1800640e4  jz      short loc_180064125
0x1800640e6  mov     rcx, rdi
0x1800640e9  call    ?_Tidy@?$vector@V?$unique_ptr@VAuthValue@@U?$default_delete@VAuthValue@@@std@@@std@@V?$allocator@V?$unique_ptr@VAuthValue@@U?$default_delete@VAuthValue@@@std@@@std@@@2@@std@@AEAAXXZ; std::vector<std::unique_ptr<AuthValue>>::_Tidy(void)
0x1800640ee  mov     rax, qword ptr [rsp+128h+var_A8]
0x1800640f6  mov     [rdi], rax
0x1800640f9  mov     rax, qword ptr [rsp+128h+var_A8+8]
0x180064101  mov     [rdi+8], rax
0x180064105  mov     rax, [rsp+128h+var_98]
0x18006410d  mov     [rdi+10h], rax
0x180064111  xorps   xmm0, xmm0
0x180064114  movdqu  [rsp+128h+var_A8], xmm0
0x18006411d  mov     [rsp+128h+var_98], r12
0x180064125  lea     rcx, [rsp+128h+lpName]
0x18006412d  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x180064132  nop
0x180064133  lea     rcx, [rsp+128h+var_A8]
0x18006413b  call    ?_Tidy@?$vector@V?$unique_ptr@VAuthValue@@U?$default_delete@VAuthValue@@@std@@@std@@V?$allocator@V?$unique_ptr@VAuthValue@@U?$default_delete@VAuthValue@@@std@@@std@@@2@@std@@AEAAXXZ; std::vector<std::unique_ptr<AuthValue>>::_Tidy(void)
0x180064140  nop
0x180064141  mov     rcx, [rsp+128h+hKey]; hKey
0x180064146  test    rcx, rcx
0x180064149  jz      short loc_180064152
0x18006414b  call    cs:__imp_RegCloseKey
0x180064151  nop
0x180064152  lea     rcx, [rsp+128h+var_78]
0x18006415a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006415f  nop
0x180064160  xor     eax, eax
0x180064162  jmp     short loc_180064168
0x180064164  mov     eax, [rsp+128h+cchName]
0x180064168  mov     rcx, [rsp+128h+var_48]
0x180064170  xor     rcx, rsp; StackCookie
0x180064173  call    __security_check_cookie
0x180064178  add     rsp, 0F8h
0x18006417f  pop     r15
0x180064181  pop     r14
0x180064183  pop     r12
0x180064185  pop     rdi
0x180064186  pop     rsi
0x180064187  pop     rbx
0x180064188  retn
```
