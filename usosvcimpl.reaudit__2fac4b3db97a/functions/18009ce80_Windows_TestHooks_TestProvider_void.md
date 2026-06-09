# Windows::TestHooks::TestProvider(void)

- ea: `0x18009ce80`
- end: `0x18009d218`
- name: `?TestProvider@TestHooks@Windows@@UEAA?AV?$optional@V?$unique_ptr@VUpdateProvider@@U?$default_delete@VUpdateProvider@@@std@@@std@@@std@@XZ`
- size: `920`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180010890`
- `0x180010f24`
- `0x180011b8c`
- `0x180036f98`
- `0x1800420e0`
- `0x180042e00`
- `0x180042e48`
- `0x180062598`
- `0x18007d30c`
- `0x18009b2d4`
- `0x18009ce80`
- `0x18009d92c`
- `0x18009d9b0`
- `0x1800dd930`
- `0x1800e4630`
- `0x1800e46b0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009d145`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009d145`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18009d07b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18009d0ec`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18009d0fb`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18009d07b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18009d0ec`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18009d0fb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009d0ae`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009d131`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009d0ae`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009d131`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009d08c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009d10c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009d08c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009d10c`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18009d0be`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18009d0be`

## string_xrefs

- `0x18009d1bb`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x18009cfa9`: `%WINDIR%\System32\TestProvider.dll`
- `0x18009d1ed`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\TestHooks.cpp`
- `0x18009d206`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\TestHooks.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_BYTE *__fastcall Windows::TestHooks::TestProvider(__int64 a1, _BYTE *a2)
{
  int v3; // eax
  __int64 traits_2_unsigned_short; // rax
  const char *v5; // r9
  __int64 v6; // r11
  __int64 v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rcx
  HMODULE v11; // rbx
  bool v12; // si
  __int64 v13; // rcx
  HMODULE LibraryW; // rax
  const char *v15; // r9
  HMODULE v16; // rcx
  FARPROC ProcAddress; // rax
  const char *v18; // r9
  __int64 *v19; // rax
  __int64 v20; // rcx
  LPVOID pv; // [rsp+38h] [rbp-D0h] BYREF
  HMODULE hLibModule; // [rsp+40h] [rbp-C8h] BYREF
  const wchar_t *v24; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v25; // [rsp+50h] [rbp-B8h]
  _QWORD v26[2]; // [rsp+68h] [rbp-A0h] BYREF
  _QWORD v27[4]; // [rsp+78h] [rbp-90h] BYREF
  _QWORD v28[34]; // [rsp+98h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D0h] [rbp+C8h]

  pv = a2;
  v27[2] = &Windows::g_testDllMutex;
  if ( (unsigned int)mtx_do_lock(&Windows::g_testDllMutex) )
    std::_Throw_Cpp_error(5);
  v3 = dword_18014D4AC;
  if ( dword_18014D4AC == 0x7FFFFFFF )
  {
    dword_18014D4AC = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  if ( !Windows::g_testDll )
  {
    hLibModule = (HMODULE)&Windows::Registry::`vftable';
    traits_2_unsigned_short = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                                L"TestProviderEnabled",
                                L"ProSkuOverride",
                                0);
    if ( traits_2_unsigned_short == v6
      || (v7 = (traits_2_unsigned_short - (__int64)L"TestProviderEnabled") >> 1, v7 == -1) )
    {
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xC9,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
        v5);
    }
    v8 = -1;
    do
      ++v8;
    while ( SystemInterface::Registry::USO_TEST_HOOKS_PATH[v8] );
    v9 = -1;
    do
      ++v9;
    while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v9] );
    v26[0] = L"TestProviderEnabled";
    v26[1] = v7;
    v27[0] = SystemInterface::Registry::USO_TEST_HOOKS_PATH;
    v27[1] = v8;
    v24 = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
    v25 = v9;
    if ( !(unsigned __int8)SystemInterface::Registry::GetSystemBoolOrDefault(&hLibModule, &v24, v27, v26) )
    {
      a2[8] = 0;
LABEL_22:
      if ( !--dword_18014D4AC )
      {
        dword_18014D4A8 = -1;
        ReleaseSRWLockExclusive(&stru_18014D470);
      }
      return a2;
    }
    pv = 0;
    wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(
      &pv,
      L"%WINDIR%\\System32\\TestProvider.dll");
    memset(v28, 0, sizeof(v28));
    std::ifstream::ifstream(v28, pv);
    if ( *(_DWORD *)((char *)&v28[2] + *(int *)(v28[0] + 4LL)) )
    {
      a2[8] = 0;
      std::ifstream::~ifstream<char,std::char_traits<char>>(&v28[22]);
      v28[22] = &std::wios::`vftable';
      std::ios_base::~ios_base((std::ios_base *)&v28[22]);
LABEL_20:
      if ( pv )
        CoTaskMemFree(pv);
      goto LABEL_22;
    }
    std::ifstream::~ifstream<char,std::char_traits<char>>(&v28[22]);
    v28[22] = &std::wios::`vftable';
    std::ios_base::~ios_base((std::ios_base *)&v28[22]);
    hLibModule = 0;
    Windows::TestHooks::GetSelfHostDll(v10, &hLibModule);
    v11 = hLibModule;
    v12 = hLibModule != 0;
    if ( !hLibModule )
    {
      v13 = -1;
      do
        ++v13;
      while ( *((_WORD *)pv + v13) );
      v24 = (const wchar_t *)pv;
      v25 = v13;
      if ( !(unsigned __int8)Windows::Trust::IsFileSelfSigned(&v24) )
      {
        a2[8] = 0;
        if ( v12 )
          FreeLibrary(0);
        goto LABEL_20;
      }
    }
    LibraryW = LoadLibraryW((LPCWSTR)pv);
    v26[0] = LibraryW;
    if ( !LibraryW )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x140,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\TestHooks.cpp",
        v15);
    v16 = Windows::g_testDll;
    Windows::g_testDll = LibraryW;
    if ( v16 )
      FreeLibrary(v16);
    if ( v12 )
      FreeLibrary(v11);
    if ( pv )
      CoTaskMemFree(pv);
    v3 = dword_18014D4AC;
  }
  dword_18014D4AC = v3 - 1;
  if ( v3 == 1 )
  {
    dword_18014D4A8 = -1;
    ReleaseSRWLockExclusive(&stru_18014D470);
  }
  ProcAddress = GetProcAddress(Windows::g_testDll, "GetTestProvider");
  if ( !ProcAddress )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x148,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\TestHooks.cpp",
      v18);
  v19 = (__int64 *)((__int64 (__fastcall *)(LPVOID *))ProcAddress)(&pv);
  v20 = *v19;
  *v19 = 0;
  *(_QWORD *)a2 = v20;
  a2[8] = 1;
  if ( pv )
    (**(void (__fastcall ***)(LPVOID, __int64))pv)(pv, 1);
  return a2;
}

```

## disassembly

```asm
0x18009ce80  mov     rax, rsp
0x18009ce83  mov     [rax+8], rbx
0x18009ce87  mov     [rax+18h], rsi
0x18009ce8b  mov     [rax+20h], rdi
0x18009ce8f  push    rbp
0x18009ce90  push    r14
0x18009ce92  push    r15
0x18009ce94  lea     rbp, [rax-0C8h]
0x18009ce9b  sub     rsp, 1B0h
0x18009cea2  mov     rax, cs:__security_cookie
0x18009cea9  xor     rax, rsp
0x18009ceac  mov     [rbp+0C0h+var_20], rax
0x18009ceb3  mov     rdi, rdx
0x18009ceb6  mov     [rsp+1C0h+pv], rdx
0x18009cebb  xor     r14d, r14d
0x18009cebe  lea     rcx, ?g_testDllMutex@Windows@@3Vmutex@std@@A; std::mutex Windows::g_testDllMutex
0x18009cec5  mov     [rbp+0C0h+var_140], rcx
0x18009cec9  call    mtx_do_lock
0x18009cece  test    eax, eax
0x18009ced0  jnz     loc_18009D1CD
0x18009ced6  mov     eax, cs:dword_18014D4AC
0x18009cedc  cmp     eax, 7FFFFFFFh
0x18009cee1  jz      loc_18009D1D8
0x18009cee7  or      r15, 0FFFFFFFFFFFFFFFFh
0x18009ceeb  cmp     cs:?g_testDll@Windows@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A, r14; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>> Windows::g_testDll
0x18009cef2  jnz     loc_18009D118
0x18009cef8  lea     rax, ??_7Registry@Windows@@6B@; const Windows::Registry::`vftable'
0x18009ceff  mov     [rsp+1C0h+hLibModule], rax
0x18009cf04  xor     r8d, r8d
0x18009cf07  lea     r11, aProskuoverride; "ProSkuOverride"
0x18009cf0e  mov     rdx, r11
0x18009cf11  lea     rbx, aTestprovideren; "TestProviderEnabled"
0x18009cf18  mov     rcx, rbx
0x18009cf1b  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x18009cf20  cmp     rax, r11
0x18009cf23  jz      loc_18009D1B4
0x18009cf29  sub     rax, rbx
0x18009cf2c  sar     rax, 1
0x18009cf2f  cmp     rax, r15
0x18009cf32  jz      loc_18009D1B4
0x18009cf38  mov     r8, cs:?USO_TEST_HOOKS_PATH@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::USO_TEST_HOOKS_PATH
0x18009cf3f  mov     rcx, r15
0x18009cf42  inc     rcx
0x18009cf45  cmp     [r8+rcx*2], r14w
0x18009cf4a  jnz     short loc_18009CF42
0x18009cf4c  mov     r9, cs:?USOCURRENTVERSIONROOT_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID
0x18009cf53  mov     rdx, r15
0x18009cf56  inc     rdx
0x18009cf59  cmp     [r9+rdx*2], r14w
0x18009cf5e  jnz     short loc_18009CF56
0x18009cf60  mov     [rsp+1C0h+var_160], rbx
0x18009cf65  mov     [rsp+1C0h+var_158], rax
0x18009cf6a  mov     [rsp+1C0h+var_150], r8
0x18009cf6f  mov     [rsp+1C0h+var_148], rcx
0x18009cf74  mov     [rsp+1C0h+var_180], r9
0x18009cf79  mov     [rsp+1C0h+var_178], rdx
0x18009cf7e  lea     r9, [rsp+1C0h+var_160]
0x18009cf83  lea     r8, [rsp+1C0h+var_150]
0x18009cf88  lea     rdx, [rsp+1C0h+var_180]
0x18009cf8d  lea     rcx, [rsp+1C0h+hLibModule]
0x18009cf92  call    ?GetSystemBoolOrDefault@Registry@SystemInterface@@QEAA_NV?$basic_zstring_view@_W@wil@@00_N@Z; SystemInterface::Registry::GetSystemBoolOrDefault(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,bool)
0x18009cf97  test    al, al
0x18009cf99  jnz     short loc_18009CFA4
0x18009cf9b  mov     [rdi+8], r14b
0x18009cf9f  jmp     loc_18009D093
0x18009cfa4  mov     [rsp+1C0h+pv], r14
0x18009cfa9  lea     rdx, aWindirSystem32_0; "%WINDIR%\\System32\\TestProvider.dll"
0x18009cfb0  lea     rcx, [rsp+1C0h+pv]
0x18009cfb5  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(wchar_t const *)
0x18009cfba  nop
0x18009cfbb  xor     edx, edx; Val
0x18009cfbd  mov     r8d, 110h; Size
0x18009cfc3  lea     rcx, [rbp+0C0h+var_130]; void *
0x18009cfc7  call    memset
0x18009cfcc  mov     rdx, [rsp+1C0h+pv]
0x18009cfd1  lea     rcx, [rbp+0C0h+var_130]
0x18009cfd5  call    ??0?$basic_ifstream@DU?$char_traits@D@std@@@std@@QEAA@PEB_WHH@Z; std::ifstream::ifstream(wchar_t const *,int,int)
0x18009cfda  mov     rax, [rbp+0C0h+var_130]
0x18009cfde  movsxd  rcx, dword ptr [rax+4]
0x18009cfe2  cmp     [rbp+rcx+0C0h+var_120], r14d
0x18009cfe7  lea     rcx, [rbp+0C0h+var_80]
0x18009cfeb  jz      short loc_18009D00C
0x18009cfed  mov     [rdi+8], r14b
0x18009cff1  call    ??1?$basic_ifstream@DU?$char_traits@D@std@@@std@@UEAA@XZ; std::ifstream::~ifstream<char,std::char_traits<char>>(void)
0x18009cff6  lea     rax, ??_7?$basic_ios@_WU?$char_traits@_W@std@@@std@@6B@; const std::wios::`vftable'
0x18009cffd  mov     [rbp+0C0h+var_80], rax
0x18009d001  lea     rcx, [rbp+0C0h+var_80]; this
0x18009d005  call    ??1ios_base@std@@UEAA@XZ; std::ios_base::~ios_base(void)
0x18009d00a  jmp     short loc_18009D082
0x18009d00c  call    ??1?$basic_ifstream@DU?$char_traits@D@std@@@std@@UEAA@XZ; std::ifstream::~ifstream<char,std::char_traits<char>>(void)
0x18009d011  lea     rax, ??_7?$basic_ios@_WU?$char_traits@_W@std@@@std@@6B@; const std::wios::`vftable'
0x18009d018  mov     [rbp+0C0h+var_80], rax
0x18009d01c  lea     rcx, [rbp+0C0h+var_80]; this
0x18009d020  call    ??1ios_base@std@@UEAA@XZ; std::ios_base::~ios_base(void)
0x18009d025  mov     [rsp+1C0h+hLibModule], r14
0x18009d02a  lea     rdx, [rsp+1C0h+hLibModule]
0x18009d02f  call    ?GetSelfHostDll@TestHooks@Windows@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; Windows::TestHooks::GetSelfHostDll(void)
0x18009d034  nop
0x18009d035  mov     rbx, [rsp+1C0h+hLibModule]
0x18009d03a  test    rbx, rbx
0x18009d03d  setnz   sil
0x18009d041  test    rbx, rbx
0x18009d044  jnz     short loc_18009D0B9
0x18009d046  mov     rax, [rsp+1C0h+pv]
0x18009d04b  mov     rcx, r15
0x18009d04e  inc     rcx
0x18009d051  cmp     [rax+rcx*2], r14w
0x18009d056  jnz     short loc_18009D04E
0x18009d058  mov     [rsp+1C0h+var_180], rax
0x18009d05d  mov     [rsp+1C0h+var_178], rcx
0x18009d062  lea     rcx, [rsp+1C0h+var_180]
0x18009d067  call    ?IsFileSelfSigned@Trust@Windows@@YA_NV?$basic_zstring_view@_W@wil@@_N@Z; Windows::Trust::IsFileSelfSigned(wil::basic_zstring_view<wchar_t>,bool)
0x18009d06c  test    al, al
0x18009d06e  jnz     short loc_18009D0B9
0x18009d070  mov     [rdi+8], r14b
0x18009d074  test    sil, sil
0x18009d077  jz      short loc_18009D082
0x18009d079  xor     ecx, ecx; hLibModule
0x18009d07b  call    cs:__imp_FreeLibrary
0x18009d081  nop
0x18009d082  mov     rcx, [rsp+1C0h+pv]; pv
0x18009d087  test    rcx, rcx
0x18009d08a  jz      short loc_18009D093
0x18009d08c  call    cs:__imp_CoTaskMemFree
0x18009d092  nop
0x18009d093  sub     cs:dword_18014D4AC, 1
0x18009d09a  jnz     loc_18009D185
0x18009d0a0  mov     cs:dword_18014D4A8, r15d
0x18009d0a7  lea     rcx, stru_18014D470; SRWLock
0x18009d0ae  call    cs:__imp_ReleaseSRWLockExclusive
0x18009d0b4  jmp     loc_18009D185
0x18009d0b9  mov     rcx, [rsp+1C0h+pv]; lpLibFileName
0x18009d0be  call    cs:__imp_LoadLibraryW
0x18009d0c4  mov     [rsp+1C0h+var_160], rax
0x18009d0c9  mov     rcx, [rbp+0C8h]; this
0x18009d0d0  test    rax, rax
0x18009d0d3  jz      loc_18009D1ED
0x18009d0d9  mov     rcx, cs:?g_testDll@Windows@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; hLibModule
0x18009d0e0  mov     cs:?g_testDll@Windows@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A, rax; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>> Windows::g_testDll
0x18009d0e7  test    rcx, rcx
0x18009d0ea  jz      short loc_18009D0F3
0x18009d0ec  call    cs:__imp_FreeLibrary
0x18009d0f2  nop
0x18009d0f3  test    sil, sil
0x18009d0f6  jz      short loc_18009D102
0x18009d0f8  mov     rcx, rbx; hLibModule
0x18009d0fb  call    cs:__imp_FreeLibrary
0x18009d101  nop
0x18009d102  mov     rcx, [rsp+1C0h+pv]; pv
0x18009d107  test    rcx, rcx
0x18009d10a  jz      short loc_18009D112
0x18009d10c  call    cs:__imp_CoTaskMemFree
0x18009d112  mov     eax, cs:dword_18014D4AC
0x18009d118  sub     eax, 1
0x18009d11b  mov     cs:dword_18014D4AC, eax
0x18009d121  jnz     short loc_18009D137
0x18009d123  mov     cs:dword_18014D4A8, r15d
0x18009d12a  lea     rcx, stru_18014D470; SRWLock
0x18009d131  call    cs:__imp_ReleaseSRWLockExclusive
0x18009d137  lea     rdx, aGettestprovide; "GetTestProvider"
0x18009d13e  mov     rcx, cs:?g_testDll@Windows@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; hModule
0x18009d145  call    cs:__imp_GetProcAddress
0x18009d14b  test    rax, rax
0x18009d14e  jz      loc_18009D1FF
0x18009d154  lea     rcx, [rsp+1C0h+pv]
0x18009d159  call    _guard_dispatch_icall
0x18009d15e  mov     rcx, [rax]
0x18009d161  mov     [rax], r14
0x18009d164  mov     [rdi], rcx
0x18009d167  mov     byte ptr [rdi+8], 1
0x18009d16b  mov     rcx, [rsp+1C0h+pv]
0x18009d170  test    rcx, rcx
0x18009d173  jz      short loc_18009D185
0x18009d175  mov     r8, [rcx]
0x18009d178  mov     edx, 1
0x18009d17d  mov     rax, [r8]
0x18009d180  call    _guard_dispatch_icall
0x18009d185  mov     rax, rdi
0x18009d188  mov     rcx, [rbp+0C0h+var_20]
0x18009d18f  xor     rcx, rsp; StackCookie
0x18009d192  call    __security_check_cookie
0x18009d197  lea     r11, [rsp+1C0h+var_10]
0x18009d19f  mov     rbx, [r11+20h]
0x18009d1a3  mov     rsi, [r11+30h]
0x18009d1a7  mov     rdi, [r11+38h]
0x18009d1ab  mov     rsp, r11
0x18009d1ae  pop     r15
0x18009d1b0  pop     r14
0x18009d1b2  pop     rbp
0x18009d1b3  retn
0x18009d1b4  mov     rcx, [rbp+0C8h]; this
0x18009d1bb  lea     r8, aCW1SPackagesMi_2; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18009d1c2  mov     edx, 0C9h; void *
0x18009d1c7  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18009d1cd  mov     ecx, 5; int
0x18009d1d2  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18009d1d8  mov     cs:dword_18014D4AC, 7FFFFFFEh
0x18009d1e2  mov     ecx, 6; int
0x18009d1e7  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18009d1ed  lea     r8, aCW1SSrcOrchest_17; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18009d1f4  mov     edx, 140h; void *
0x18009d1f9  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18009d1ff  mov     rcx, [rbp+0C8h]; this
0x18009d206  lea     r8, aCW1SSrcOrchest_17; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18009d20d  mov     edx, 148h; void *
0x18009d212  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
