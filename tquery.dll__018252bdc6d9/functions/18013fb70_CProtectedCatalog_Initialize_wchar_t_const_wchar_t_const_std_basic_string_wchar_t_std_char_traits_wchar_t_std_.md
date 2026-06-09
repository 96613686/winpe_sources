# CProtectedCatalog::Initialize(wchar_t const *,wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,void *,IProtectedIndex *,bool)

- ea: `0x18013fb70`
- end: `0x18013ff01`
- name: `?Initialize@CProtectedCatalog@@QEAAXPEB_W0AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAXPEAUIProtectedIndex@@_N@Z`
- size: `913`
- prototype: `__int64 __fastcall(unsigned int *, const WCHAR *, __int64, __int64, void *, __int64, char)`
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180180910`

## callees

- `0x18002a3f8`
- `0x18002be24`
- `0x180036d60`
- `0x180038f08`
- `0x18006380c`
- `0x18006961c`
- `0x18008b084`
- `0x180098390`
- `0x180099f2c`
- `0x18009e1dc`
- `0x1800e98fc`
- `0x18013ecc4`
- `0x18013edc0`
- `0x18013f910`
- `0x18013fb70`
- `0x18014164c`
- `0x180147154`
- `0x18014f0e8`
- `0x180150f94`
- `0x18015708c`
- `0x180182e18`
- `0x180188d90`
- `0x1802c0010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18013fe18`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18013fe18`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18013fd81`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18013fd81`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18013fd6a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18013fd6a`
- `efswrt!CdplProtectFileToLevel` at `0x18013fdc4`
- `efswrt!CdplProtectFileToLevel` at `0x18013fdc4`

## pseudocode

```c
__int64 __fastcall CProtectedCatalog::Initialize(
        unsigned int *a1,
        const WCHAR *a2,
        __int64 a3,
        __int64 a4,
        void *a5,
        __int64 a6,
        char a7)
{
  const wchar_t *v11; // rcx
  int v12; // eax
  __int64 v13; // rbx
  __int64 v14; // r8
  __int64 v15; // rax
  __int128 v16; // xmm6
  __int64 v17; // rdi
  __int64 v18; // rax
  const WCHAR *v19; // rcx
  const char *v20; // r9
  wchar_t **v21; // rcx
  int v22; // eax
  __int64 v23; // rax
  __int64 v24; // r8
  __int64 CatalogStorageManager; // rax
  __int64 v26; // rax
  __int64 (__fastcall *v27)(__int64, const WCHAR *, _QWORD, __int64); // r10
  int v28; // eax
  int v30; // [rsp+20h] [rbp-E0h]
  bool v31; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE hToken; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v34[2]; // [rsp+40h] [rbp-C0h] BYREF
  std::_Ref_count_base *v35[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v36; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v37[16]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v38[16]; // [rsp+80h] [rbp-80h] BYREF
  wchar_t *v39[3]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int64 v40; // [rsp+A8h] [rbp-58h]
  _BYTE Src[32]; // [rsp+B0h] [rbp-50h] BYREF
  LPCWSTR pszPath[4]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v43[32]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v44[32]; // [rsp+110h] [rbp+10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  hToken = a5;
  if ( *a1 != 2 )
    MicrosoftTelemetryAssertTriggeredNoArgs(a1);
  if ( *((_QWORD *)a1 + 1) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xE5,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\tripolipi\\invertedapplication.cpp",
      (const char *)0x8000FFFFLL,
      v30);
  std::wstring::wstring(v39, a4);
  std::wstring::push_back(v39, (unsigned __int16)(*(_WORD *)a1 + 48));
  v11 = (const wchar_t *)v39;
  if ( v40 > 7 )
    v11 = v39[0];
  v12 = EnsureDPLUserFolderCreated(v11, a2);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xEA,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\tripolipi\\invertedapplication.cpp",
      (const char *)(unsigned int)v12,
      v30);
  std::wstring::wstring(Src);
  std::wstring::_Append<wchar_t>(Src);
  v13 = -1;
  v14 = -1;
  do
    ++v14;
  while ( a2[v14] );
  std::wstring::_Append<wchar_t>(Src);
  std::wstring::_Append<wchar_t>(Src);
  std::wstring::push_back(Src, (unsigned __int16)(*(_WORD *)a1 + 48));
  v36 = *(_OWORD *)std::wstring::operator std::wstring_view(Src, v37);
  v15 = to_utf8(v44, &v36);
  v16 = *(_OWORD *)std::string::operator std::string_view(v15, v38);
  do
    ++v13;
  while ( *(_WORD *)(a3 + 2 * v13) );
  std::filesystem::path::path(v43, v39);
  *(_OWORD *)v35 = v16;
  *(_QWORD *)&v36 = a3;
  *((_QWORD *)&v36 + 1) = v13;
  CreateDatabaseEngineBuilder(v34, v43, &v36, v35);
  std::wstring::_Tidy_deallocate(v43);
  std::string::_Tidy_deallocate(v44);
  v17 = v34[0];
  v18 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v34[0] + 8LL))(v34[0]);
  std::wstring::wstring(pszPath, v18);
  v19 = (const WCHAR *)pszPath;
  if ( pszPath[3] > (LPCWSTR)7 )
    v19 = pszPath[0];
  v31 = !PathFileExistsW(v19);
  if ( !ImpersonateLoggedOnUser(hToken) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xF9,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\tripolipi\\invertedapplication.cpp",
      v20);
  v21 = v39;
  if ( v40 > 7 )
    v21 = (wchar_t **)v39[0];
  v22 = CdplProtectFileToLevel(v21, *a1);
  if ( v22 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xFB,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\tripolipi\\invertedapplication.cpp",
      (const char *)(unsigned int)v22,
      v30);
  if ( v31 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    v31 = 0;
  }
  (*(void (__fastcall **)(__int64, bool *))(*(_QWORD *)v17 + 24LL))(v17, &v31);
  RevertToSelf();
  v23 = (*(__int64 (__fastcall **)(__int64, HANDLE *))(*(_QWORD *)v17 + 40LL))(v17, &hToken);
  LOBYTE(v24) = a7;
  CatalogStorageManager = CreateCatalogStorageManager(v35, v23, v24);
  std::shared_ptr<inverted::ICatalogStorage>::operator=(a1 + 2, CatalogStorageManager);
  if ( v35[1] )
    std::_Ref_count_base::_Decref(v35[1]);
  std::unique_ptr<inverted::IDatabaseConnection>::~unique_ptr<inverted::IDatabaseConnection>(&hToken);
  v26 = std::shared_ptr<inverted::IInvertedQueryProps>::shared_ptr<inverted::IInvertedQueryProps>(v35, a1 + 2);
  v28 = v27(a6, a2, *a1, v26);
  if ( v28 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x107,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\tripolipi\\invertedapplication.cpp",
      (const char *)(unsigned int)v28,
      v30);
  std::wstring::_Tidy_deallocate(pszPath);
  std::unique_ptr<inverted::IDatabaseConnection>::~unique_ptr<inverted::IDatabaseConnection>(v34);
  std::wstring::_Tidy_deallocate(Src);
  return std::wstring::_Tidy_deallocate(v39);
}

```

## disassembly

```asm
0x18013fb70  mov     rax, rsp
0x18013fb73  push    rbp
0x18013fb74  push    rbx
0x18013fb75  push    rsi
0x18013fb76  push    rdi
0x18013fb77  push    r12
0x18013fb79  push    r13
0x18013fb7b  push    r14
0x18013fb7d  push    r15
0x18013fb7f  lea     rbp, [rsp-58h]
0x18013fb84  sub     rsp, 158h
0x18013fb8b  movaps  xmmword ptr [rax-58h], xmm6
0x18013fb8f  mov     rax, cs:__security_cookie
0x18013fb96  xor     rax, rsp
0x18013fb99  mov     [rbp+90h+var_60], rax
0x18013fb9d  mov     rbx, r9
0x18013fba0  mov     rdi, r8
0x18013fba3  mov     r14, rdx
0x18013fba6  mov     rsi, rcx
0x18013fba9  mov     rax, [rbp+90h+arg_20]
0x18013fbb0  mov     [rsp+190h+hToken], rax
0x18013fbb5  mov     r12, [rbp+90h+arg_28]
0x18013fbbc  mov     r13b, [rbp+90h+arg_30]
0x18013fbc3  cmp     dword ptr [rcx], 2
0x18013fbc6  jz      short loc_18013FBCD
0x18013fbc8  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18013fbcd  lea     r15, [rsi+8]
0x18013fbd1  mov     rcx, [rbp+98h]; this
0x18013fbd8  cmp     qword ptr [r15], 0
0x18013fbdc  jz      short loc_18013FBF6
0x18013fbde  mov     r9d, 8000FFFFh; char *
0x18013fbe4  lea     r8, aOnecoreuapBase_246; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x18013fbeb  mov     edx, 0E5h; void *
0x18013fbf0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18013fbf6  mov     rdx, rbx
0x18013fbf9  lea     rcx, [rbp+90h+var_100]
0x18013fbfd  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18013fc02  nop
0x18013fc03  movzx   edx, word ptr [rsi]
0x18013fc06  add     dx, 30h ; '0'
0x18013fc0a  lea     rcx, [rbp+90h+var_100]
0x18013fc0e  call    ?push_back@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_W@Z; std::wstring::push_back(wchar_t)
0x18013fc13  lea     rcx, [rbp+90h+var_100]
0x18013fc17  cmp     [rbp+90h+var_E8], 7
0x18013fc1c  cmova   rcx, [rbp+90h+var_100]; this
0x18013fc21  mov     rdx, r14; StringSid
0x18013fc24  call    ?EnsureDPLUserFolderCreated@@YAJPEB_W0@Z; EnsureDPLUserFolderCreated(wchar_t const *,wchar_t const *)
0x18013fc29  mov     rcx, [rbp+98h]; this
0x18013fc30  test    eax, eax
0x18013fc32  jns     short loc_18013FC49
0x18013fc34  mov     r9d, eax; char *
0x18013fc37  lea     r8, aOnecoreuapBase_246; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x18013fc3e  mov     edx, 0EAh; void *
0x18013fc43  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18013fc49  mov     rdx, rdi
0x18013fc4c  lea     rcx, [rbp+90h+Src]
0x18013fc50  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18013fc55  nop
0x18013fc56  mov     r8d, 1
0x18013fc5c  lea     rdx, asc_1802EC4D0; "-"
0x18013fc63  lea     rcx, [rbp+90h+Src]; Src
0x18013fc67  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x18013fc6c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18013fc70  mov     r8, rbx
0x18013fc73  xor     eax, eax
0x18013fc75  inc     r8
0x18013fc78  cmp     [r14+r8*2], ax
0x18013fc7d  jnz     short loc_18013FC75
0x18013fc7f  mov     rdx, r14
0x18013fc82  lea     rcx, [rbp+90h+Src]; Src
0x18013fc86  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x18013fc8b  mov     r8d, 1
0x18013fc91  lea     rdx, asc_1802EC4D0; "-"
0x18013fc98  lea     rcx, [rbp+90h+Src]; Src
0x18013fc9c  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x18013fca1  movzx   edx, word ptr [rsi]
0x18013fca4  add     dx, 30h ; '0'
0x18013fca8  lea     rcx, [rbp+90h+Src]
0x18013fcac  call    ?push_back@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_W@Z; std::wstring::push_back(wchar_t)
0x18013fcb1  lea     rdx, [rsp+190h+var_120]
0x18013fcb6  lea     rcx, [rbp+90h+Src]
0x18013fcba  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18013fcbf  movups  xmm0, xmmword ptr [rax]
0x18013fcc2  movdqu  [rsp+190h+var_130], xmm0
0x18013fcc8  lea     rdx, [rsp+190h+var_130]
0x18013fccd  lea     rcx, [rbp+90h+var_80]
0x18013fcd1  call    ?to_utf8@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@2@@Z; to_utf8(std::wstring_view)
0x18013fcd6  nop
0x18013fcd7  lea     rdx, [rbp+90h+var_110]
0x18013fcdb  mov     rcx, rax
0x18013fcde  call    ??B?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string_view@DU?$char_traits@D@std@@@1@XZ; std::string::operator std::string_view(void)
0x18013fce3  movups  xmm6, xmmword ptr [rax]
0x18013fce6  xor     eax, eax
0x18013fce8  inc     rbx
0x18013fceb  cmp     [rdi+rbx*2], ax
0x18013fcef  jnz     short loc_18013FCE8
0x18013fcf1  lea     rdx, [rbp+90h+var_100]
0x18013fcf5  lea     rcx, [rbp+90h+var_A0]
0x18013fcf9  call    ??$?0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$0A@@path@filesystem@std@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@W4format@012@@Z; std::filesystem::path::path(std::wstring const &,std::filesystem::path::format)
0x18013fcfe  nop
0x18013fcff  movdqu  xmmword ptr [rsp+190h+var_140], xmm6
0x18013fd05  mov     qword ptr [rsp+190h+var_130], rdi
0x18013fd0a  mov     qword ptr [rsp+190h+var_130+8], rbx
0x18013fd0f  lea     r9, [rsp+190h+var_140]
0x18013fd14  lea     r8, [rsp+190h+var_130]
0x18013fd19  lea     rdx, [rbp+90h+var_A0]
0x18013fd1d  lea     rcx, [rsp+190h+var_150]
0x18013fd22  call    ?CreateDatabaseEngineBuilder@@YA?AV?$unique_ptr@UIDatabaseEngineBuilder@@U?$default_delete@UIDatabaseEngineBuilder@@@std@@@std@@AEBVpath@filesystem@2@V?$basic_string_view@_WU?$char_traits@_W@std@@@2@V?$basic_string_view@DU?$char_traits@D@std@@@2@@Z; CreateDatabaseEngineBuilder(std::filesystem::path const &,std::wstring_view,std::string_view)
0x18013fd27  nop
0x18013fd28  lea     rcx, [rbp+90h+var_A0]
0x18013fd2c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013fd31  nop
0x18013fd32  lea     rcx, [rbp+90h+var_80]
0x18013fd36  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18013fd3b  mov     rdi, [rsp+190h+var_150]
0x18013fd40  mov     rax, [rdi]
0x18013fd43  mov     rcx, rdi
0x18013fd46  mov     rax, [rax+8]
0x18013fd4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013fd4f  mov     rdx, rax
0x18013fd52  lea     rcx, [rbp+90h+pszPath]
0x18013fd56  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18013fd5b  nop
0x18013fd5c  lea     rcx, [rbp+90h+pszPath]
0x18013fd60  cmp     [rbp+90h+var_A8], 7
0x18013fd65  cmova   rcx, [rbp+90h+pszPath]; pszPath
0x18013fd6a  call    cs:__imp_PathFileExistsW
0x18013fd70  xor     ecx, ecx
0x18013fd72  test    eax, eax
0x18013fd74  setz    [rsp+190h+var_160]
0x18013fd79  movzx   ebx, cl
0x18013fd7c  mov     rcx, [rsp+190h+hToken]; hToken
0x18013fd81  call    cs:__imp_ImpersonateLoggedOnUser
0x18013fd87  mov     edx, ebx
0x18013fd89  xor     ebx, ebx
0x18013fd8b  test    eax, eax
0x18013fd8d  lea     eax, [rbx+1]
0x18013fd90  cmovnz  edx, eax
0x18013fd93  mov     [rsp+190h+var_15F], dl
0x18013fd97  mov     rcx, [rbp+98h]; this
0x18013fd9e  test    dl, dl
0x18013fda0  jnz     short loc_18013FDB4
0x18013fda2  lea     r8, aOnecoreuapBase_246; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x18013fda9  mov     edx, 0F9h; void *
0x18013fdae  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18013fdb4  lea     rcx, [rbp+90h+var_100]
0x18013fdb8  cmp     [rbp+90h+var_E8], 7
0x18013fdbd  cmova   rcx, [rbp+90h+var_100]
0x18013fdc2  mov     edx, [rsi]
0x18013fdc4  call    cs:__imp_CdplProtectFileToLevel
0x18013fdca  mov     rcx, [rbp+98h]; this
0x18013fdd1  test    eax, eax
0x18013fdd3  jns     short loc_18013FDEA
0x18013fdd5  mov     r9d, eax; char *
0x18013fdd8  lea     r8, aOnecoreuapBase_246; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x18013fddf  mov     edx, 0FBh; void *
0x18013fde4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18013fdea  cmp     [rsp+190h+var_160], bl
0x18013fdee  jz      short loc_18013FE03
0x18013fdf0  mov     rax, [rdi]
0x18013fdf3  mov     rcx, rdi
0x18013fdf6  mov     rax, [rax+10h]
0x18013fdfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013fdff  mov     [rsp+190h+var_160], bl
0x18013fe03  mov     rax, [rdi]
0x18013fe06  lea     rdx, [rsp+190h+var_160]
0x18013fe0b  mov     rcx, rdi
0x18013fe0e  mov     rax, [rax+18h]
0x18013fe12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013fe17  nop
0x18013fe18  call    cs:__imp_RevertToSelf
0x18013fe1e  mov     rax, [rdi]
0x18013fe21  lea     rdx, [rsp+190h+hToken]
0x18013fe26  mov     rcx, rdi
0x18013fe29  mov     rax, [rax+28h]
0x18013fe2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013fe32  nop
0x18013fe33  mov     r8b, r13b
0x18013fe36  mov     rdx, rax
0x18013fe39  lea     rcx, [rsp+190h+var_140]
0x18013fe3e  call    CreateCatalogStorageManager
0x18013fe43  mov     rdx, rax
0x18013fe46  mov     rcx, r15
0x18013fe49  call    ??4?$shared_ptr@UICatalogStorage@inverted@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<inverted::ICatalogStorage>::operator=(std::shared_ptr<inverted::ICatalogStorage> &&)
0x18013fe4e  mov     rcx, [rsp+190h+var_140+8]; this
0x18013fe53  test    rcx, rcx
0x18013fe56  jz      short loc_18013FE5E
0x18013fe58  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18013fe5d  nop
0x18013fe5e  lea     rcx, [rsp+190h+hToken]
0x18013fe63  call    ??1?$unique_ptr@UIDatabaseConnection@inverted@@U?$default_delete@UIDatabaseConnection@inverted@@@std@@@std@@QEAA@XZ; std::unique_ptr<inverted::IDatabaseConnection>::~unique_ptr<inverted::IDatabaseConnection>(void)
0x18013fe68  mov     rax, [r12]
0x18013fe6c  mov     r10, [rax+20h]
0x18013fe70  mov     rdx, r15
0x18013fe73  lea     rcx, [rsp+190h+var_140]
0x18013fe78  call    ??0?$shared_ptr@UIInvertedQueryProps@inverted@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<inverted::IInvertedQueryProps>::shared_ptr<inverted::IInvertedQueryProps>(std::shared_ptr<inverted::IInvertedQueryProps> const &)
0x18013fe7d  mov     r9, rax
0x18013fe80  mov     r8d, [rsi]
0x18013fe83  mov     rdx, r14
0x18013fe86  mov     rcx, r12
0x18013fe89  mov     rax, r10
0x18013fe8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013fe91  mov     rcx, [rbp+98h]; this
0x18013fe98  test    eax, eax
0x18013fe9a  jns     short loc_18013FEB1
0x18013fe9c  mov     r9d, eax; char *
0x18013fe9f  lea     r8, aOnecoreuapBase_246; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x18013fea6  mov     edx, 107h; void *
0x18013feab  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18013feb1  lea     rcx, [rbp+90h+pszPath]
0x18013feb5  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013feba  nop
0x18013febb  lea     rcx, [rsp+190h+var_150]
0x18013fec0  call    ??1?$unique_ptr@UIDatabaseConnection@inverted@@U?$default_delete@UIDatabaseConnection@inverted@@@std@@@std@@QEAA@XZ; std::unique_ptr<inverted::IDatabaseConnection>::~unique_ptr<inverted::IDatabaseConnection>(void)
0x18013fec5  nop
0x18013fec6  lea     rcx, [rbp+90h+Src]
0x18013feca  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013fecf  nop
0x18013fed0  lea     rcx, [rbp+90h+var_100]
0x18013fed4  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013fed9  mov     rcx, [rbp+90h+var_60]
0x18013fedd  xor     rcx, rsp; StackCookie
0x18013fee0  call    __security_check_cookie
0x18013fee5  movaps  xmm6, [rsp+190h+var_50]
0x18013feed  add     rsp, 158h
0x18013fef4  pop     r15
0x18013fef6  pop     r14
0x18013fef8  pop     r13
0x18013fefa  pop     r12
0x18013fefc  pop     rdi
0x18013fefd  pop     rsi
0x18013fefe  pop     rbx
0x18013feff  pop     rbp
0x18013ff00  retn
```
