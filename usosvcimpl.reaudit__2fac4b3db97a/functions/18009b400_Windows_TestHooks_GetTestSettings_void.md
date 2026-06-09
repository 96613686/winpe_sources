# Windows::TestHooks::GetTestSettings(void)

- ea: `0x18009b400`
- end: `0x18009b919`
- name: `?GetTestSettings@TestHooks@Windows@@UEAA?AW4TestLevel@SystemInterface@@XZ`
- size: `1305`
- prototype: ``
- caller_count: `10`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18009bb20`
- `0x18009bbc4`
- `0x18009bde0`
- `0x18009c2e0`
- `0x18009c460`
- `0x18009c5e0`
- `0x18009c930`
- `0x18009d220`
- `0x18009d3a0`
- `0x18009d650`

## callees

- `0x180010890`
- `0x1800108b4`
- `0x180010f24`
- `0x1800112d0`
- `0x180011680`
- `0x180036f98`
- `0x1800420e0`
- `0x180062598`
- `0x18007d30c`
- `0x1800842c4`
- `0x18009b2d4`
- `0x18009b400`
- `0x18009d92c`
- `0x18009d9b0`
- `0x1800dd930`
- `0x1800e4630`
- `0x1800e46b0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009b699`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009b699`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18009b867`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18009b867`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009b4c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009b65f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009b878`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009b4c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009b65f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009b878`

## string_xrefs

- `0x18009b8b6`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x18009b906`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x18009b443`: `%WINDIR%\System32\UsoSelfhost.dll`
- `0x18009b8c8`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\TestHooks.cpp`
- `0x18009b8da`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\TestHooks.cpp`
- `0x18009b8ec`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\TestHooks.cpp`
- `0x18009b54f`: `USOSelfHostDllNotSigned`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::TestHooks::GetTestSettings(__int64 a1)
{
  __int64 result; // rax
  const char *v3; // r9
  __int64 v4; // rbx
  __int64 v5; // rcx
  __int64 v6; // rcx
  int *v7; // rax
  int v8; // edx
  const char *v9; // r9
  __int64 v10; // r11
  __int64 v11; // rax
  __int64 v12; // rax
  const char *v13; // r9
  FARPROC ProcAddress; // rax
  const char *v15; // r9
  int v16; // eax
  int v17; // eax
  const wchar_t *v18; // rdx
  __int64 v19; // r8
  int *traits_2_unsigned_short; // rax
  int v21; // edx
  const char *v22; // r9
  __int64 v23; // r11
  __int64 v24; // rax
  __int64 v25; // rax
  unsigned int v26; // ebx
  int v27; // [rsp+20h] [rbp-1B8h]
  LPVOID pv[2]; // [rsp+30h] [rbp-1A8h] BYREF
  __int128 v29; // [rsp+40h] [rbp-198h] BYREF
  __int128 v30; // [rsp+50h] [rbp-188h] BYREF
  __int128 v31; // [rsp+60h] [rbp-178h] BYREF
  HMODULE hModule; // [rsp+70h] [rbp-168h] BYREF
  __int128 v33; // [rsp+78h] [rbp-160h] BYREF
  __int64 v34; // [rsp+88h] [rbp-150h]
  __int64 v35; // [rsp+90h] [rbp-148h]
  char v36; // [rsp+98h] [rbp-140h]
  __int128 v37; // [rsp+A0h] [rbp-138h] BYREF
  _QWORD v38[34]; // [rsp+B0h] [rbp-128h] BYREF
  int v39; // [rsp+1C0h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+0h]

  if ( *(_BYTE *)(a1 + 12) )
    return *(unsigned int *)(a1 + 8);
  pv[0] = 0;
  try
  {
    wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(
      pv,
      L"%WINDIR%\\System32\\UsoSelfhost.dll");
    memset(v38, 0, sizeof(v38));
    std::ifstream::ifstream(v38, pv[0]);
    if ( *(_DWORD *)((char *)&v38[2] + *(int *)(v38[0] + 4LL)) )
    {
      std::ifstream::~ifstream<char,std::char_traits<char>>(&v38[22]);
      v38[22] = &std::wios::`vftable';
      std::ios_base::~ios_base((std::ios_base *)&v38[22]);
      if ( pv[0] )
        CoTaskMemFree(pv[0]);
      result = 0;
    }
    else
    {
      std::ifstream::~ifstream<char,std::char_traits<char>>(&v38[22]);
      v38[22] = &std::wios::`vftable';
      std::ios_base::~ios_base((std::ios_base *)&v38[22]);
      *(LPVOID *)&v29 = pv[0];
      v4 = -1;
      v5 = -1;
      do
        ++v5;
      while ( *((_WORD *)pv[0] + v5) );
      *((_QWORD *)&v29 + 1) = v5;
      v30 = v29;
      if ( (unsigned __int8)Windows::Trust::IsFileSelfSigned(&v30) )
      {
        hModule = 0;
        Windows::TestHooks::GetSelfHostDll(v6, &hModule);
        if ( !hModule )
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0x3F,
            (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\TestHooks.cpp",
            v13);
        ProcAddress = GetProcAddress(hModule, "IsTestMode");
        if ( !ProcAddress )
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0x42,
            (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\TestHooks.cpp",
            v15);
        v39 = 0;
        v16 = ((__int64 (__fastcall *)(int *))ProcAddress)(&v39);
        if ( v16 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x45,
            (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\TestHooks.cpp",
            (const char *)(unsigned int)v16,
            v27);
        LODWORD(v29) = (v39 != 0) + 1;
        BYTE4(v29) = 1;
        v17 = v29;
        *(_QWORD *)(a1 + 8) = v29;
        if ( *(_BYTE *)(a1 + 12) )
        {
          if ( v17 )
          {
            if ( v17 == 1 )
            {
              v18 = L"PPE";
            }
            else if ( v17 == 2 )
            {
              v18 = L"Sandbox";
            }
            else
            {
              v18 = L"Unknown to_wstring(TestLevel)";
            }
          }
          else
          {
            v18 = L"Production";
          }
        }
        else
        {
          v18 = L"ErrorNoValue";
        }
        v33 = 0;
        v34 = 0;
        v35 = 0;
        v19 = -1;
        do
          ++v19;
        while ( v18[v19] );
        std::wstring::_Construct<1,wchar_t const *>(&v33, v18, v19);
        v36 = 2;
        traits_2_unsigned_short = (int *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                                           L"GetTestSettingsStatus",
                                           &dword_180125054,
                                           0);
        if ( traits_2_unsigned_short == &dword_180125054
          || (v24 = ((__int64)traits_2_unsigned_short - v23) >> 1, v24 == -1) )
        {
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0xC9,
            (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
            v22);
        }
        *(_QWORD *)&v30 = v23;
        *((_QWORD *)&v30 + 1) = v24;
        v25 = -1;
        do
          ++v25;
        while ( SystemInterface::Registry::USO_TEST_HOOKS_PATH[v25] );
        *(_QWORD *)&v31 = SystemInterface::Registry::USO_TEST_HOOKS_PATH;
        *((_QWORD *)&v31 + 1) = v25;
        *(_QWORD *)&v29 = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
        do
          ++v4;
        while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v4] );
        *((_QWORD *)&v29 + 1) = v4;
        v37 = v30;
        v30 = v31;
        v31 = v29;
        Windows::Registry::SetValue(
          (unsigned int)&v29,
          v21,
          (unsigned int)&v31,
          (unsigned int)&v30,
          (__int64)&v37,
          (__int64)&v33);
        if ( v36 != -1 && v36 && v36 != 1 )
          std::wstring::~wstring(&v33);
        v26 = *(_DWORD *)(a1 + 8);
        if ( hModule )
          FreeLibrary(hModule);
        if ( pv[0] )
          CoTaskMemFree(pv[0]);
        result = v26;
      }
      else
      {
        v33 = 0;
        v34 = 0;
        v35 = 0;
        std::wstring::_Construct<1,wchar_t const *>(&v33, L"USOSelfHostDllNotSigned", 23);
        v36 = 2;
        v7 = (int *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                      L"GetTestSettingsStatus",
                      &dword_180125054,
                      0);
        if ( v7 == &dword_180125054 || (v11 = ((__int64)v7 - v10) >> 1, v11 == -1) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0xC9,
            (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
            v9);
        *(_QWORD *)&v29 = v10;
        *((_QWORD *)&v29 + 1) = v11;
        v12 = -1;
        do
          ++v12;
        while ( SystemInterface::Registry::USO_TEST_HOOKS_PATH[v12] );
        *(_QWORD *)&v31 = SystemInterface::Registry::USO_TEST_HOOKS_PATH;
        *((_QWORD *)&v31 + 1) = v12;
        *(_QWORD *)&v30 = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
        do
          ++v4;
        while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v4] );
        *((_QWORD *)&v30 + 1) = v4;
        v37 = v29;
        Windows::Registry::SetValue(
          (unsigned int)&v29,
          v8,
          (unsigned int)&v30,
          (unsigned int)&v31,
          (__int64)&v37,
          (__int64)&v33);
        if ( v36 != -1 && v36 && v36 != 1 )
          std::wstring::~wstring(&v33);
        if ( pv[0] )
          CoTaskMemFree(pv[0]);
        result = 0;
      }
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x53,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\TestHooks.cpp",
      v3);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18009b400  mov     [rsp+arg_8], rbx
0x18009b405  mov     [rsp+arg_10], rsi
0x18009b40a  mov     [rsp+arg_18], rdi
0x18009b40f  push    r14
0x18009b411  sub     rsp, 1D0h
0x18009b418  mov     rax, cs:__security_cookie
0x18009b41f  xor     rax, rsp
0x18009b422  mov     [rsp+1D8h+var_10], rax
0x18009b42a  mov     rdi, rcx
0x18009b42d  xor     r14d, r14d
0x18009b430  cmp     [rcx+0Ch], r14b
0x18009b434  jz      short loc_18009B43E
0x18009b436  mov     eax, [rcx+8]
0x18009b439  jmp     loc_18009B884
0x18009b43e  mov     [rsp+1D8h+pv], r14
0x18009b443  lea     rdx, aWindirSystem32; "%WINDIR%\\System32\\UsoSelfhost.dll"
0x18009b44a  lea     rcx, [rsp+1D8h+pv]
0x18009b44f  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(wchar_t const *)
0x18009b454  nop
0x18009b455  xor     edx, edx; Val
0x18009b457  mov     r8d, 110h; Size
0x18009b45d  lea     rcx, [rsp+1D8h+var_128]; void *
0x18009b465  call    memset
0x18009b46a  mov     rdx, [rsp+1D8h+pv]
0x18009b46f  lea     rcx, [rsp+1D8h+var_128]
0x18009b477  call    ??0?$basic_ifstream@DU?$char_traits@D@std@@@std@@QEAA@PEB_WHH@Z; std::ifstream::ifstream(wchar_t const *,int,int)
0x18009b47c  mov     rax, [rsp+1D8h+var_128]
0x18009b484  movsxd  rcx, dword ptr [rax+4]
0x18009b488  cmp     [rsp+rcx+1D8h+var_118], r14d
0x18009b490  lea     rcx, [rsp+1D8h+var_78]
0x18009b498  jz      short loc_18009B4D3
0x18009b49a  call    ??1?$basic_ifstream@DU?$char_traits@D@std@@@std@@UEAA@XZ; std::ifstream::~ifstream<char,std::char_traits<char>>(void)
0x18009b49f  lea     rax, ??_7?$basic_ios@_WU?$char_traits@_W@std@@@std@@6B@; const std::wios::`vftable'
0x18009b4a6  mov     [rsp+1D8h+var_78], rax
0x18009b4ae  lea     rcx, [rsp+1D8h+var_78]; this
0x18009b4b6  call    ??1ios_base@std@@UEAA@XZ; std::ios_base::~ios_base(void)
0x18009b4bb  nop
0x18009b4bc  mov     rcx, [rsp+1D8h+pv]; pv
0x18009b4c1  test    rcx, rcx
0x18009b4c4  jz      short loc_18009B4CC
0x18009b4c6  call    cs:__imp_CoTaskMemFree
0x18009b4cc  xor     eax, eax
0x18009b4ce  jmp     loc_18009B884
0x18009b4d3  call    ??1?$basic_ifstream@DU?$char_traits@D@std@@@std@@UEAA@XZ; std::ifstream::~ifstream<char,std::char_traits<char>>(void)
0x18009b4d8  lea     rax, ??_7?$basic_ios@_WU?$char_traits@_W@std@@@std@@6B@; const std::wios::`vftable'
0x18009b4df  mov     [rsp+1D8h+var_78], rax
0x18009b4e7  lea     rcx, [rsp+1D8h+var_78]; this
0x18009b4ef  call    ??1ios_base@std@@UEAA@XZ; std::ios_base::~ios_base(void)
0x18009b4f4  mov     rax, [rsp+1D8h+pv]
0x18009b4f9  mov     qword ptr [rsp+1D8h+var_198], rax
0x18009b4fe  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18009b502  mov     rcx, rbx
0x18009b505  inc     rcx
0x18009b508  cmp     [rax+rcx*2], r14w
0x18009b50d  jnz     short loc_18009B505
0x18009b50f  mov     qword ptr [rsp+1D8h+var_198+8], rcx
0x18009b514  movaps  xmm0, [rsp+1D8h+var_198]
0x18009b519  movdqa  [rsp+1D8h+var_188], xmm0
0x18009b51f  lea     rcx, [rsp+1D8h+var_188]
0x18009b524  call    ?IsFileSelfSigned@Trust@Windows@@YA_NV?$basic_zstring_view@_W@wil@@_N@Z; Windows::Trust::IsFileSelfSigned(wil::basic_zstring_view<wchar_t>,bool)
0x18009b529  test    al, al
0x18009b52b  jnz     loc_18009B66C
0x18009b531  xorps   xmm0, xmm0
0x18009b534  movups  [rsp+1D8h+var_160], xmm0
0x18009b539  mov     [rsp+1D8h+var_150], r14
0x18009b541  mov     [rsp+1D8h+var_148], r14
0x18009b549  mov     r8d, 17h
0x18009b54f  lea     rdx, aUsoselfhostdll; "USOSelfHostDllNotSigned"
0x18009b556  lea     rcx, [rsp+1D8h+var_160]
0x18009b55b  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18009b560  mov     [rsp+1D8h+var_140], 2
0x18009b568  xor     r8d, r8d
0x18009b56b  lea     rsi, dword_180125054
0x18009b572  mov     rdx, rsi
0x18009b575  lea     r11, aGettestsetting; "GetTestSettingsStatus"
0x18009b57c  mov     rcx, r11
0x18009b57f  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x18009b584  cmp     rax, rsi
0x18009b587  jz      loc_18009B8AE
0x18009b58d  sub     rax, r11
0x18009b590  sar     rax, 1
0x18009b593  cmp     rax, rbx
0x18009b596  jz      loc_18009B8AE
0x18009b59c  mov     qword ptr [rsp+1D8h+var_198], r11
0x18009b5a1  mov     qword ptr [rsp+1D8h+var_198+8], rax
0x18009b5a6  mov     rcx, cs:?USO_TEST_HOOKS_PATH@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::USO_TEST_HOOKS_PATH
0x18009b5ad  mov     rax, rbx
0x18009b5b0  inc     rax
0x18009b5b3  cmp     [rcx+rax*2], r14w
0x18009b5b8  jnz     short loc_18009B5B0
0x18009b5ba  mov     qword ptr [rsp+1D8h+var_178], rcx
0x18009b5bf  mov     qword ptr [rsp+1D8h+var_178+8], rax
0x18009b5c4  mov     rax, cs:?USOCURRENTVERSIONROOT_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID
0x18009b5cb  mov     qword ptr [rsp+1D8h+var_188], rax
0x18009b5d0  inc     rbx
0x18009b5d3  cmp     [rax+rbx*2], r14w
0x18009b5d8  jnz     short loc_18009B5D0
0x18009b5da  mov     qword ptr [rsp+1D8h+var_188+8], rbx
0x18009b5df  movups  xmm0, [rsp+1D8h+var_198]
0x18009b5e4  movdqu  [rsp+1D8h+var_138], xmm0
0x18009b5ed  movups  xmm1, [rsp+1D8h+var_178]
0x18009b5f2  movdqu  [rsp+1D8h+var_178], xmm1
0x18009b5f8  movaps  xmm0, [rsp+1D8h+var_188]
0x18009b5fd  movdqa  [rsp+1D8h+var_188], xmm0
0x18009b603  lea     rax, [rsp+1D8h+var_160]
0x18009b608  mov     [rsp+1D8h+var_1B0], rax
0x18009b60d  lea     rax, [rsp+1D8h+var_138]
0x18009b615  mov     [rsp+1D8h+var_1B8], rax
0x18009b61a  lea     r9, [rsp+1D8h+var_178]
0x18009b61f  lea     r8, [rsp+1D8h+var_188]
0x18009b624  lea     rcx, [rsp+1D8h+var_198]
0x18009b629  call    ?SetValue@Registry@Windows@@QEAAXQEAUHKEY__@@V?$basic_zstring_view@_W@wil@@11AEBV?$variant@I_KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@Z; Windows::Registry::SetValue(HKEY__ * const,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,std::variant<uint,unsigned __int64,std::wstring> const &)
0x18009b62e  nop
0x18009b62f  movsx   rax, [rsp+1D8h+var_140]
0x18009b638  add     rax, 1
0x18009b63c  jz      short loc_18009B655
0x18009b63e  sub     rax, 1
0x18009b642  jz      short loc_18009B655
0x18009b644  cmp     rax, 1
0x18009b648  jz      short loc_18009B655
0x18009b64a  lea     rcx, [rsp+1D8h+var_160]; void *
0x18009b64f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18009b654  nop
0x18009b655  mov     rcx, [rsp+1D8h+pv]; pv
0x18009b65a  test    rcx, rcx
0x18009b65d  jz      short loc_18009B665
0x18009b65f  call    cs:__imp_CoTaskMemFree
0x18009b665  xor     eax, eax
0x18009b667  jmp     loc_18009B884
0x18009b66c  mov     [rsp+1D8h+hModule], r14
0x18009b671  lea     rdx, [rsp+1D8h+hModule]
0x18009b676  call    ?GetSelfHostDll@TestHooks@Windows@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; Windows::TestHooks::GetSelfHostDll(void)
0x18009b67b  nop
0x18009b67c  mov     rax, [rsp+1D8h]
0x18009b684  mov     rcx, [rsp+1D8h+hModule]; hModule
0x18009b689  test    rcx, rcx
0x18009b68c  jz      loc_18009B8C8
0x18009b692  lea     rdx, aIstestmode; "IsTestMode"
0x18009b699  call    cs:__imp_GetProcAddress
0x18009b69f  mov     rcx, [rsp+1D8h]; this
0x18009b6a7  test    rax, rax
0x18009b6aa  jz      loc_18009B8DA
0x18009b6b0  mov     [rsp+1D8h+var_18], r14d
0x18009b6b8  lea     rcx, [rsp+1D8h+var_18]
0x18009b6c0  call    _guard_dispatch_icall
0x18009b6c5  mov     rcx, [rsp+1D8h]; this
0x18009b6cd  test    eax, eax
0x18009b6cf  js      loc_18009B8E9
0x18009b6d5  mov     eax, [rsp+1D8h+var_18]
0x18009b6dc  neg     eax
0x18009b6de  sbb     ecx, ecx
0x18009b6e0  neg     ecx
0x18009b6e2  inc     ecx
0x18009b6e4  mov     dword ptr [rsp+1D8h+var_198], ecx
0x18009b6e8  mov     byte ptr [rsp+1D8h+var_198+4], 1
0x18009b6ed  mov     rax, qword ptr [rsp+1D8h+var_198]
0x18009b6f2  mov     [rdi+8], rax
0x18009b6f6  cmp     [rdi+0Ch], r14b
0x18009b6fa  jz      short loc_18009B730
0x18009b6fc  mov     ecx, eax
0x18009b6fe  test    eax, eax
0x18009b700  jz      short loc_18009B727
0x18009b702  sub     ecx, 1
0x18009b705  jz      short loc_18009B71E
0x18009b707  cmp     ecx, 1
0x18009b70a  jz      short loc_18009B715
0x18009b70c  lea     rdx, aUnknownToWstri; "Unknown to_wstring(TestLevel)"
0x18009b713  jmp     short loc_18009B737
0x18009b715  lea     rdx, aSandbox; "Sandbox"
0x18009b71c  jmp     short loc_18009B737
0x18009b71e  lea     rdx, aPpe; "PPE"
0x18009b725  jmp     short loc_18009B737
0x18009b727  lea     rdx, aProduction; "Production"
0x18009b72e  jmp     short loc_18009B737
0x18009b730  lea     rdx, aErrornovalue; "ErrorNoValue"
0x18009b737  xorps   xmm0, xmm0
0x18009b73a  movups  [rsp+1D8h+var_160], xmm0
0x18009b73f  mov     [rsp+1D8h+var_150], r14
0x18009b747  mov     [rsp+1D8h+var_148], r14
0x18009b74f  mov     r8, rbx
0x18009b752  inc     r8
0x18009b755  cmp     [rdx+r8*2], r14w
0x18009b75a  jnz     short loc_18009B752
0x18009b75c  lea     rcx, [rsp+1D8h+var_160]
0x18009b761  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18009b766  mov     [rsp+1D8h+var_140], 2
0x18009b76e  xor     r8d, r8d
0x18009b771  lea     rsi, dword_180125054
0x18009b778  mov     rdx, rsi
0x18009b77b  lea     r11, aGettestsetting; "GetTestSettingsStatus"
0x18009b782  mov     rcx, r11
0x18009b785  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x18009b78a  cmp     rax, rsi
0x18009b78d  jz      loc_18009B8FE
0x18009b793  sub     rax, r11
0x18009b796  sar     rax, 1
0x18009b799  cmp     rax, rbx
0x18009b79c  jz      loc_18009B8FE
0x18009b7a2  mov     qword ptr [rsp+1D8h+var_188], r11
0x18009b7a7  mov     qword ptr [rsp+1D8h+var_188+8], rax
0x18009b7ac  mov     rcx, cs:?USO_TEST_HOOKS_PATH@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::USO_TEST_HOOKS_PATH
0x18009b7b3  mov     rax, rbx
0x18009b7b6  inc     rax
0x18009b7b9  cmp     [rcx+rax*2], r14w
0x18009b7be  jnz     short loc_18009B7B6
0x18009b7c0  mov     qword ptr [rsp+1D8h+var_178], rcx
0x18009b7c5  mov     qword ptr [rsp+1D8h+var_178+8], rax
0x18009b7ca  mov     rax, cs:?USOCURRENTVERSIONROOT_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID
0x18009b7d1  mov     qword ptr [rsp+1D8h+var_198], rax
0x18009b7d6  inc     rbx
0x18009b7d9  cmp     [rax+rbx*2], r14w
0x18009b7de  jnz     short loc_18009B7D6
0x18009b7e0  mov     qword ptr [rsp+1D8h+var_198+8], rbx
0x18009b7e5  movups  xmm0, [rsp+1D8h+var_188]
0x18009b7ea  movdqu  [rsp+1D8h+var_138], xmm0
0x18009b7f3  movups  xmm1, [rsp+1D8h+var_178]
0x18009b7f8  movdqu  [rsp+1D8h+var_188], xmm1
0x18009b7fe  movaps  xmm0, [rsp+1D8h+var_198]
0x18009b803  movdqa  [rsp+1D8h+var_178], xmm0
0x18009b809  lea     rax, [rsp+1D8h+var_160]
0x18009b80e  mov     [rsp+1D8h+var_1B0], rax
0x18009b813  lea     rax, [rsp+1D8h+var_138]
0x18009b81b  mov     [rsp+1D8h+var_1B8], rax
0x18009b820  lea     r9, [rsp+1D8h+var_188]
0x18009b825  lea     r8, [rsp+1D8h+var_178]
0x18009b82a  lea     rcx, [rsp+1D8h+var_198]
0x18009b82f  call    ?SetValue@Registry@Windows@@QEAAXQEAUHKEY__@@V?$basic_zstring_view@_W@wil@@11AEBV?$variant@I_KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@Z; Windows::Registry::SetValue(HKEY__ * const,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,std::variant<uint,unsigned __int64,std::wstring> const &)
0x18009b834  nop
0x18009b835  movsx   rax, [rsp+1D8h+var_140]
0x18009b83e  add     rax, 1
0x18009b842  jz      short loc_18009B85A
0x18009b844  sub     rax, 1
0x18009b848  jz      short loc_18009B85A
0x18009b84a  cmp     rax, 1
0x18009b84e  jz      short loc_18009B85A
0x18009b850  lea     rcx, [rsp+1D8h+var_160]; void *
0x18009b855  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18009b85a  mov     ebx, [rdi+8]
0x18009b85d  mov     rcx, [rsp+1D8h+hModule]; hLibModule
0x18009b862  test    rcx, rcx
0x18009b865  jz      short loc_18009B86E
0x18009b867  call    cs:__imp_FreeLibrary
0x18009b86d  nop
0x18009b86e  mov     rcx, [rsp+1D8h+pv]; pv
0x18009b873  test    rcx, rcx
0x18009b876  jz      short loc_18009B87E
0x18009b878  call    cs:__imp_CoTaskMemFree
0x18009b87e  mov     eax, ebx
0x18009b880  jmp     short loc_18009B884
0x18009b882  xor     eax, eax
0x18009b884  mov     rcx, [rsp+1D8h+var_10]
0x18009b88c  xor     rcx, rsp; StackCookie
0x18009b88f  call    __security_check_cookie
0x18009b894  lea     r11, [rsp+1D8h+var_8]
0x18009b89c  mov     rbx, [r11+18h]
0x18009b8a0  mov     rsi, [r11+20h]
0x18009b8a4  mov     rdi, [r11+28h]
0x18009b8a8  mov     rsp, r11
0x18009b8ab  pop     r14
0x18009b8ad  retn
0x18009b8ae  mov     rcx, [rsp+1D8h]; this
0x18009b8b6  lea     r8, aCW1SPackagesMi_2; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18009b8bd  mov     edx, 0C9h; void *
0x18009b8c2  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18009b8c8  lea     r8, aCW1SSrcOrchest_17; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18009b8cf  lea     edx, [rcx+3Fh]; void *
0x18009b8d2  mov     rcx, rax; this
0x18009b8d5  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18009b8da  lea     r8, aCW1SSrcOrchest_17; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18009b8e1  lea     edx, [rax+42h]; void *
0x18009b8e4  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18009b8e9  mov     r9d, eax; char *
0x18009b8ec  lea     r8, aCW1SSrcOrchest_17; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18009b8f3  mov     edx, 45h ; 'E'; void *
0x18009b8f8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009b8fe  mov     rcx, [rsp+1D8h]; this
0x18009b906  lea     r8, aCW1SPackagesMi_2; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18009b90d  mov     edx, 0C9h; void *
0x18009b912  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
