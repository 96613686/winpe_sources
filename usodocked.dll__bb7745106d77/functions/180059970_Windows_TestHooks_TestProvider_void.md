# Windows::TestHooks::TestProvider(void)

- ea: `0x180059970`
- end: `0x180059cc5`
- name: `?TestProvider@TestHooks@Windows@@UEAA?AV?$optional@V?$unique_ptr@VUpdateProvider@@U?$default_delete@VUpdateProvider@@@std@@@std@@@std@@XZ`
- size: `853`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180007660`
- `0x18001ba70`
- `0x18001ee04`
- `0x180023a18`
- `0x180033070`
- `0x180058020`
- `0x180058210`
- `0x1800583a0`
- `0x180059970`
- `0x180067558`
- `0x180071010`

## import_xrefs

- `msvcp_win!?good@ios_base@std@@QEBA_NXZ` at `0x180059b10`
- `msvcp_win!?good@ios_base@std@@QEBA_NXZ` at `0x180059b10`
- `msvcp_win!??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x180059b5f`
- `msvcp_win!??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x180059bbb`
- `msvcp_win!??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x180059b5f`
- `msvcp_win!??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x180059bbb`
- `msvcp_win!??1?$basic_istream@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x180059b55`
- `msvcp_win!??1?$basic_istream@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x180059bb1`
- `msvcp_win!??1?$basic_istream@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x180059b55`
- `msvcp_win!??1?$basic_istream@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x180059bb1`
- `msvcp_win!_Mtx_unlock` at `0x180059ad3`
- `msvcp_win!_Mtx_unlock` at `0x180059c27`
- `msvcp_win!_Mtx_unlock` at `0x180059ad3`
- `msvcp_win!_Mtx_unlock` at `0x180059c27`
- `msvcp_win!_Mtx_lock` at `0x1800599ad`
- `msvcp_win!_Mtx_lock` at `0x1800599ad`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800599bc`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800599de`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800599bc`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800599de`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180059c3b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180059c3b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180059c0c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180059c0c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180059b74`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180059c1d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180059b74`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180059c1d`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180059bd9`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180059bd9`

## string_xrefs

- `0x180059a72`: `UpdateOrchestratorCurrentVersionRoot`
- `0x180059ade`: `%WINDIR%\System32\TestProvider.dll`
- `0x180059ca1`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\testhooks.cpp`
- `0x180059cb3`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\testhooks.cpp`

## pseudocode

```c
__int64 __fastcall Windows::TestHooks::TestProvider(__int64 a1, __int64 a2)
{
  char SystemBoolOrDefault; // bl
  bool v4; // zf
  __int64 v5; // rax
  const unsigned __int16 *v6; // rdx
  bool v7; // r8
  HMODULE LibraryW; // rax
  const char *v9; // r9
  HMODULE v10; // rcx
  FARPROC ProcAddress; // rax
  const char *v12; // r9
  __int64 *v13; // rax
  __int64 v14; // rcx
  LPVOID pv; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v17[2]; // [rsp+38h] [rbp-C8h] BYREF
  void *v18; // [rsp+48h] [rbp-B8h]
  _QWORD v19[2]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v20[8]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v21[152]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v22[96]; // [rsp+100h] [rbp+0h] BYREF
  _OWORD v23[2]; // [rsp+160h] [rbp+60h] BYREF
  _OWORD v24[2]; // [rsp+180h] [rbp+80h] BYREF
  _OWORD v25[2]; // [rsp+1A0h] [rbp+A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+F8h]

  v17[0] = a2;
  v18 = &Windows::g_testDllMutex;
  if ( _Mtx_lock((_Mtx_t)&Windows::g_testDllMutex) )
  {
    std::_Throw_Cpp_error(5);
    __debugbreak();
  }
  if ( dword_1800952CC == 0x7FFFFFFF )
  {
    dword_1800952CC = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  if ( !Windows::g_testDll )
  {
    v17[0] = &Windows::Registry::`vftable';
    memset(v25, 0, sizeof(v25));
    std::wstring::_Construct<1,unsigned short const *>(v25, L"TestProviderEnabled", 19);
    memset(v24, 0, sizeof(v24));
    std::wstring::_Construct<1,unsigned short const *>(v24, L"\\TestHooks", 10);
    memset(v23, 0, sizeof(v23));
    std::wstring::_Construct<1,unsigned short const *>(v23, L"UpdateOrchestratorCurrentVersionRoot", 36);
    SystemBoolOrDefault = SystemInterface::Registry::GetSystemBoolOrDefault(
                            (unsigned int)v17,
                            (unsigned int)v23,
                            (unsigned int)v24,
                            (unsigned int)v25,
                            0);
    std::wstring::_Tidy_deallocate(v23);
    std::wstring::_Tidy_deallocate(v24);
    std::wstring::_Tidy_deallocate(v25);
    if ( !SystemBoolOrDefault )
    {
      *(_BYTE *)(a2 + 8) = 0;
LABEL_8:
      _Mtx_unlock((_Mtx_t)&Windows::g_testDllMutex);
      return a2;
    }
    wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
      &pv,
      L"%WINDIR%\\System32\\TestProvider.dll");
    std::ifstream::ifstream(v19, pv);
    v4 = !std::ios_base::good((std::ios_base *)((char *)v19 + *(int *)(v19[0] + 4LL)));
    v5 = v19[0];
    if ( v4 )
    {
      *(_BYTE *)(a2 + 8) = 0;
      *(_QWORD *)((char *)v19 + *(int *)(v5 + 4)) = &std::ifstream::`vftable';
      *(_DWORD *)((char *)&v18 + *(int *)(v19[0] + 4LL) + 4) = *(_DWORD *)(v19[0] + 4LL) - 176;
      std::filebuf::~filebuf<char,std::char_traits<char>>(v20);
      std::istream::~istream<char,std::char_traits<char>>(v21);
      std::ios::~ios<char,std::char_traits<char>>(v22);
      goto LABEL_11;
    }
    *(_QWORD *)((char *)v19 + *(int *)(v19[0] + 4LL)) = &std::ifstream::`vftable';
    *(_DWORD *)((char *)&v18 + *(int *)(v19[0] + 4LL) + 4) = *(_DWORD *)(v19[0] + 4LL) - 176;
    std::filebuf::~filebuf<char,std::char_traits<char>>(v20);
    std::istream::~istream<char,std::char_traits<char>>(v21);
    std::ios::~ios<char,std::char_traits<char>>(v22);
    if ( !Windows::Trust::VerifySelfSignedFile((Windows::Trust *)pv, v6, v7) )
    {
      *(_BYTE *)(a2 + 8) = 0;
LABEL_11:
      if ( pv )
        CoTaskMemFree(pv);
      goto LABEL_8;
    }
    LibraryW = LoadLibraryW((LPCWSTR)pv);
    v17[0] = LibraryW;
    if ( !LibraryW )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x105,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\testhooks.cpp",
        v9);
    v10 = Windows::g_testDll;
    Windows::g_testDll = LibraryW;
    if ( v10 )
      FreeLibrary(v10);
    if ( pv )
      CoTaskMemFree(pv);
  }
  _Mtx_unlock((_Mtx_t)&Windows::g_testDllMutex);
  ProcAddress = GetProcAddress(Windows::g_testDll, "GetTestProvider");
  if ( !ProcAddress )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x10D,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\testhooks.cpp",
      v12);
  v13 = (__int64 *)((__int64 (__fastcall *)(_QWORD *))ProcAddress)(v17);
  v14 = *v13;
  *v13 = 0;
  *(_QWORD *)a2 = v14;
  *(_BYTE *)(a2 + 8) = 1;
  if ( v17[0] )
    (**(void (__fastcall ***)(_QWORD, __int64))v17[0])(v17[0], 1);
  return a2;
}

```

## disassembly

```asm
0x180059970  push    rbp
0x180059972  push    rbx
0x180059973  push    rdi
0x180059974  push    r14
0x180059976  lea     rbp, [rsp-0D8h]
0x18005997e  sub     rsp, 1D8h
0x180059985  mov     rax, cs:__security_cookie
0x18005998c  xor     rax, rsp
0x18005998f  mov     [rbp+0F0h+var_30], rax
0x180059996  mov     rdi, rdx
0x180059999  mov     [rsp+1F0h+var_1B8], rdx
0x18005999e  lea     r14, ?g_testDllMutex@Windows@@3Vmutex@std@@A; std::mutex Windows::g_testDllMutex
0x1800599a5  mov     [rsp+1F0h+var_1A8], r14
0x1800599aa  mov     rcx, r14; _Mtx_t
0x1800599ad  call    cs:__imp__Mtx_lock
0x1800599b3  test    eax, eax
0x1800599b5  jz      short loc_1800599C3
0x1800599b7  mov     ecx, 5
0x1800599bc  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800599c2  int     3; Trap to Debugger
0x1800599c3  cmp     cs:dword_1800952CC, 7FFFFFFFh
0x1800599cd  jnz     short loc_1800599E5
0x1800599cf  mov     cs:dword_1800952CC, 7FFFFFFEh
0x1800599d9  mov     ecx, 6
0x1800599de  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800599e4  nop
0x1800599e5  cmp     cs:?g_testDll@Windows@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A, 0; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>> Windows::g_testDll
0x1800599ed  jnz     loc_180059C24
0x1800599f3  lea     rax, ??_7Registry@Windows@@6B@; const Windows::Registry::`vftable'
0x1800599fa  mov     [rsp+1F0h+var_1B8], rax
0x1800599ff  xorps   xmm0, xmm0
0x180059a02  movups  [rbp+0F0h+var_50], xmm0
0x180059a09  xorps   xmm1, xmm1
0x180059a0c  movdqu  [rbp+0F0h+var_40], xmm1
0x180059a14  mov     r8d, 13h
0x180059a1a  lea     rdx, aTestprovideren; "TestProviderEnabled"
0x180059a21  lea     rcx, [rbp+0F0h+var_50]
0x180059a28  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180059a2d  nop
0x180059a2e  xorps   xmm0, xmm0
0x180059a31  movups  [rbp+0F0h+var_70], xmm0
0x180059a38  xorps   xmm1, xmm1
0x180059a3b  movdqu  [rbp+0F0h+var_60], xmm1
0x180059a43  mov     r8d, 0Ah
0x180059a49  lea     rdx, aTesthooks; "\\TestHooks"
0x180059a50  lea     rcx, [rbp+0F0h+var_70]
0x180059a57  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180059a5c  nop
0x180059a5d  xorps   xmm0, xmm0
0x180059a60  movups  [rbp+0F0h+var_90], xmm0
0x180059a64  xorps   xmm1, xmm1
0x180059a67  movdqu  [rbp+0F0h+var_80], xmm1
0x180059a6c  mov     r8d, 24h ; '$'
0x180059a72  lea     rdx, aUpdateorchestr_1; "UpdateOrchestratorCurrentVersionRoot"
0x180059a79  lea     rcx, [rbp+0F0h+var_90]
0x180059a7d  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180059a82  nop
0x180059a83  mov     [rsp+1F0h+var_1D0], 0
0x180059a88  lea     r9, [rbp+0F0h+var_50]
0x180059a8f  lea     r8, [rbp+0F0h+var_70]
0x180059a96  lea     rdx, [rbp+0F0h+var_90]
0x180059a9a  lea     rcx, [rsp+1F0h+var_1B8]
0x180059a9f  call    ?GetSystemBoolOrDefault@Registry@SystemInterface@@UEAA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00_N@Z; SystemInterface::Registry::GetSystemBoolOrDefault(std::wstring const &,std::wstring const &,std::wstring const &,bool)
0x180059aa4  mov     bl, al
0x180059aa6  lea     rcx, [rbp+0F0h+var_90]
0x180059aaa  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180059aaf  nop
0x180059ab0  lea     rcx, [rbp+0F0h+var_70]
0x180059ab7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180059abc  nop
0x180059abd  lea     rcx, [rbp+0F0h+var_50]
0x180059ac4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180059ac9  test    bl, bl
0x180059acb  jnz     short loc_180059ADE
0x180059acd  mov     [rdi+8], bl
0x180059ad0  mov     rcx, r14; _Mtx_t
0x180059ad3  call    cs:__imp__Mtx_unlock
0x180059ad9  jmp     loc_180059C7B
0x180059ade  lea     rdx, aWindirSystem32_0; "%WINDIR%\\System32\\TestProvider.dll"
0x180059ae5  lea     rcx, [rsp+1F0h+pv]
0x180059aea  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *)
0x180059aef  nop
0x180059af0  mov     rdx, [rsp+1F0h+pv]
0x180059af5  lea     rcx, [rsp+1F0h+var_1A0]
0x180059afa  call    ??0?$basic_ifstream@DU?$char_traits@D@std@@@std@@QEAA@PEBGHH@Z; std::ifstream::ifstream(ushort const *,int,int)
0x180059aff  mov     rax, [rsp+1F0h+var_1A0]
0x180059b04  movsxd  rcx, dword ptr [rax+4]
0x180059b08  lea     rax, [rsp+1F0h+var_1A0]
0x180059b0d  add     rcx, rax
0x180059b10  call    cs:__imp_?good@ios_base@std@@QEBA_NXZ; std::ios_base::good(void)
0x180059b16  test    al, al
0x180059b18  mov     rax, [rsp+1F0h+var_1A0]
0x180059b1d  jnz     short loc_180059B7F
0x180059b1f  mov     byte ptr [rdi+8], 0
0x180059b23  movsxd  rcx, dword ptr [rax+4]
0x180059b27  lea     rax, ??_7?$basic_ifstream@DU?$char_traits@D@std@@@std@@6B@; const std::ifstream::`vftable'
0x180059b2e  mov     [rsp+rcx+1F0h+var_1A0], rax
0x180059b33  mov     rax, [rsp+1F0h+var_1A0]
0x180059b38  movsxd  rcx, dword ptr [rax+4]
0x180059b3c  lea     edx, [rcx-0B0h]
0x180059b42  mov     dword ptr [rsp+rcx+1F0h+var_1A8+4], edx
0x180059b46  lea     rcx, [rsp+1F0h+var_190]
0x180059b4b  call    ??1?$basic_filebuf@DU?$char_traits@D@std@@@std@@UEAA@XZ; std::filebuf::~filebuf<char,std::char_traits<char>>(void)
0x180059b50  lea     rcx, [rsp+1F0h+var_188]
0x180059b55  call    cs:__imp_??1?$basic_istream@DU?$char_traits@D@std@@@std@@UEAA@XZ; std::istream::~istream<char,std::char_traits<char>>(void)
0x180059b5b  lea     rcx, [rbp+0F0h+var_F0]
0x180059b5f  call    cs:__imp_??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ; std::ios::~ios<char,std::char_traits<char>>(void)
0x180059b65  nop
0x180059b66  mov     rcx, [rsp+1F0h+pv]; pv
0x180059b6b  test    rcx, rcx
0x180059b6e  jz      loc_180059AD0
0x180059b74  call    cs:__imp_CoTaskMemFree
0x180059b7a  jmp     loc_180059AD0
0x180059b7f  movsxd  rcx, dword ptr [rax+4]
0x180059b83  lea     rax, ??_7?$basic_ifstream@DU?$char_traits@D@std@@@std@@6B@; const std::ifstream::`vftable'
0x180059b8a  mov     [rsp+rcx+1F0h+var_1A0], rax
0x180059b8f  mov     rax, [rsp+1F0h+var_1A0]
0x180059b94  movsxd  rcx, dword ptr [rax+4]
0x180059b98  lea     edx, [rcx-0B0h]
0x180059b9e  mov     dword ptr [rsp+rcx+1F0h+var_1A8+4], edx
0x180059ba2  lea     rcx, [rsp+1F0h+var_190]
0x180059ba7  call    ??1?$basic_filebuf@DU?$char_traits@D@std@@@std@@UEAA@XZ; std::filebuf::~filebuf<char,std::char_traits<char>>(void)
0x180059bac  lea     rcx, [rsp+1F0h+var_188]
0x180059bb1  call    cs:__imp_??1?$basic_istream@DU?$char_traits@D@std@@@std@@UEAA@XZ; std::istream::~istream<char,std::char_traits<char>>(void)
0x180059bb7  lea     rcx, [rbp+0F0h+var_F0]
0x180059bbb  call    cs:__imp_??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ; std::ios::~ios<char,std::char_traits<char>>(void)
0x180059bc1  mov     rcx, [rsp+1F0h+pv]; this
0x180059bc6  call    ?VerifySelfSignedFile@Trust@Windows@@YA_NPEBG_N@Z; Windows::Trust::VerifySelfSignedFile(ushort const *,bool)
0x180059bcb  test    al, al
0x180059bcd  jnz     short loc_180059BD4
0x180059bcf  mov     [rdi+8], al
0x180059bd2  jmp     short loc_180059B66
0x180059bd4  mov     rcx, [rsp+1F0h+pv]; lpLibFileName
0x180059bd9  call    cs:__imp_LoadLibraryW
0x180059bdf  mov     [rsp+1F0h+var_1B8], rax
0x180059be4  test    rax, rax
0x180059be7  setz    dl
0x180059bea  mov     rcx, [rbp+0F8h]; this
0x180059bf1  test    dl, dl
0x180059bf3  jnz     loc_180059CB3
0x180059bf9  mov     rcx, cs:?g_testDll@Windows@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; hLibModule
0x180059c00  mov     cs:?g_testDll@Windows@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A, rax; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>> Windows::g_testDll
0x180059c07  test    rcx, rcx
0x180059c0a  jz      short loc_180059C13
0x180059c0c  call    cs:__imp_FreeLibrary
0x180059c12  nop
0x180059c13  mov     rcx, [rsp+1F0h+pv]; pv
0x180059c18  test    rcx, rcx
0x180059c1b  jz      short loc_180059C24
0x180059c1d  call    cs:__imp_CoTaskMemFree
0x180059c23  nop
0x180059c24  mov     rcx, r14; _Mtx_t
0x180059c27  call    cs:__imp__Mtx_unlock
0x180059c2d  lea     rdx, aGettestprovide; "GetTestProvider"
0x180059c34  mov     rcx, cs:?g_testDll@Windows@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; hModule
0x180059c3b  call    cs:__imp_GetProcAddress
0x180059c41  test    rax, rax
0x180059c44  jz      short loc_180059C9A
0x180059c46  lea     rcx, [rsp+1F0h+var_1B8]
0x180059c4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059c50  mov     rcx, [rax]
0x180059c53  mov     qword ptr [rax], 0
0x180059c5a  mov     [rdi], rcx
0x180059c5d  mov     byte ptr [rdi+8], 1
0x180059c61  mov     rcx, [rsp+1F0h+var_1B8]
0x180059c66  test    rcx, rcx
0x180059c69  jz      short loc_180059C7B
0x180059c6b  mov     rax, [rcx]
0x180059c6e  mov     edx, 1
0x180059c73  mov     rax, [rax]
0x180059c76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059c7b  mov     rax, rdi
0x180059c7e  mov     rcx, [rbp+0F0h+var_30]
0x180059c85  xor     rcx, rsp; StackCookie
0x180059c88  call    __security_check_cookie
0x180059c8d  add     rsp, 1D8h
0x180059c94  pop     r14
0x180059c96  pop     rdi
0x180059c97  pop     rbx
0x180059c98  pop     rbp
0x180059c99  retn
0x180059c9a  mov     rcx, [rbp+0F8h]; this
0x180059ca1  lea     r8, aOnecoreEnduser_25; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180059ca8  mov     edx, 10Dh; void *
0x180059cad  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180059cb3  lea     r8, aOnecoreEnduser_25; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180059cba  mov     edx, 105h; void *
0x180059cbf  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
