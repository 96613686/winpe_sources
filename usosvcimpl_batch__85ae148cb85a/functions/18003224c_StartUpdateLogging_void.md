# StartUpdateLogging(void)

- ea: `0x18003224c`
- end: `0x180032804`
- name: `?StartUpdateLogging@@YAXXZ`
- size: `1464`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x1800349a8`

## callees

- `0x180010890`
- `0x1800108b4`
- `0x180011680`
- `0x18003224c`
- `0x180037044`
- `0x180037948`
- `0x180037a94`
- `0x180037b14`
- `0x1800420e0`
- `0x180042e00`
- `0x180042e48`
- `0x180065e54`
- `0x180066684`
- `0x180066b48`
- `0x1800dd930`
- `0x1800dddf4`
- `0x1800de12c`
- `0x1800e46b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003274b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003274b`

## string_xrefs

- `0x180032788`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x1800327bd`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x1800327d7`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x1800327f1`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x1800323e8`: `UpdateSessionOrchestration`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void StartUpdateLogging(void)
{
  int v0; // eax
  __int64 v1; // rcx
  __int64 v2; // rbx
  Windows::Logger *v3; // rdi
  __int64 traits_2_unsigned_short; // rax
  __int64 v5; // r8
  const char *v6; // r9
  __int64 v7; // r11
  __int64 v8; // rax
  __int64 v9; // rax
  const char *v10; // r9
  __int64 v11; // r11
  __int64 v12; // rax
  __int64 v13; // r8
  __int64 v14; // rcx
  __int64 v15; // rax
  Windows::Logger *v16; // rbx
  __int64 v17; // rcx
  __int64 v18; // rbx
  void *v19; // rdi
  __int64 v20; // rax
  __int64 v21; // r8
  const char *v22; // r9
  __int64 v23; // r11
  __int64 v24; // rax
  __int64 v25; // rax
  const char *v26; // r9
  __int64 v27; // r11
  __int64 v28; // rax
  __int64 v29; // r8
  __int64 v30; // rcx
  __int64 v31; // rax
  Windows::Logger *v32; // rbx
  const char *v33; // r9
  __int128 v34; // [rsp+40h] [rbp-178h] BYREF
  Windows::Logger *v35[2]; // [rsp+50h] [rbp-168h] BYREF
  __int128 v36; // [rsp+60h] [rbp-158h]
  __int128 v37; // [rsp+70h] [rbp-148h] BYREF
  __int64 v38; // [rsp+80h] [rbp-138h]
  __int64 v39; // [rsp+88h] [rbp-130h]
  __int128 v40; // [rsp+90h] [rbp-128h] BYREF
  __int128 v41; // [rsp+A0h] [rbp-118h]
  __int128 v42; // [rsp+B0h] [rbp-108h]
  _OWORD v43[9]; // [rsp+C0h] [rbp-F8h] BYREF
  void *v44; // [rsp+150h] [rbp-68h] BYREF
  _BYTE v45[32]; // [rsp+158h] [rbp-60h] BYREF
  __int128 v46; // [rsp+178h] [rbp-40h] BYREF
  __int64 v47; // [rsp+188h] [rbp-30h]
  __int128 v48; // [rsp+190h] [rbp-28h] BYREF
  __int64 v49; // [rsp+1A0h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+0h]

  v44 = &g_LoggerMutex;
  v0 = mtx_do_lock(&g_LoggerMutex);
  try
  {
    if ( v0 )
      std::_Throw_Cpp_error(5);
    if ( dword_18014D11C == 0x7FFFFFFF )
    {
      dword_18014D11C = 2147483646;
      std::_Throw_Cpp_error(6);
    }
    v48 = 0;
    v49 = 0;
    v43[0] = xmmword_1800FF7F0;
    v43[1] = xmmword_1800FF7E0;
    v43[2] = xmmword_1800FF7D0;
    v43[3] = xmmword_1800FF7A0;
    v43[4] = xmmword_1800FF7B0;
    v43[5] = xmmword_1800FF7C0;
    v43[6] = xmmword_1800FF780;
    v43[7] = xmmword_1800FF760;
    v43[8] = xmmword_1800FF790;
    *(_QWORD *)&v36 = v43;
    *((_QWORD *)&v36 + 1) = &v44;
    v34 = v36;
    std::vector<_GUID>::vector<_GUID>(&v48, &v34);
    v2 = Windows::FileSystem::Logs(v1, v45);
    v3 = (Windows::Logger *)operator new(0x98u);
    v35[0] = v3;
    memset(v3, 0, 0x98u);
    v40 = *(_OWORD *)v2;
    v41 = *(_OWORD *)(v2 + 16);
    *(_QWORD *)(v2 + 16) = 0;
    *(_QWORD *)(v2 + 24) = 7;
    *(_WORD *)v2 = 0;
    traits_2_unsigned_short = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                                L"UpdateSessionOrchestration",
                                &word_1800FF6FE,
                                0);
    if ( traits_2_unsigned_short == v7
      || (v8 = (traits_2_unsigned_short - (__int64)L"UpdateSessionOrchestration") >> 1, v8 == -1) )
    {
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xC9,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
        v6);
    }
    *(_QWORD *)&v36 = L"UpdateSessionOrchestration";
    *((_QWORD *)&v36 + 1) = v8;
    v9 = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
           L"UpdateSessionOrchestration",
           v7,
           v5);
    if ( v9 == v11 || (v12 = (v9 - (__int64)L"UpdateSessionOrchestration") >> 1, v12 == -1) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xC9,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
        v10);
    *(_QWORD *)&v34 = L"UpdateSessionOrchestration";
    *((_QWORD *)&v34 + 1) = v12;
    v35[0] = (Windows::Logger *)Windows::Logger::Logger(v3, &v40, 0);
    v37 = 0;
    v38 = 0;
    v39 = 0;
    v13 = -1;
    do
      ++v13;
    while ( aUpdatesessiono[v13] );
    std::wstring::_Construct<1,wchar_t const *>(&v37, L"UpdateSessionOrchestration");
    v15 = std::map<std::wstring,std::shared_ptr<Windows::Logger>>::operator[](v14, &v37);
    std::shared_ptr<Windows::Logger>::operator=<Windows::Logger,std::default_delete<Windows::Logger>,0>(v15, v35);
    std::wstring::~wstring(&v37);
    v16 = v35[0];
    if ( v35[0] )
    {
      Windows::Logger::~Logger(v35[0]);
      operator delete(v16, (const struct std::nothrow_t *)0x98);
    }
    std::wstring::~wstring(v45);
    v46 = 0;
    v47 = 0;
    v40 = xmmword_1800FF770;
    v41 = xmmword_1800FF750;
    v42 = xmmword_1800FF740;
    *(_QWORD *)&v34 = &v40;
    *((_QWORD *)&v34 + 1) = v43;
    std::vector<_GUID>::vector<_GUID>(&v46, &v34);
    v18 = Windows::FileSystem::Logs(v17, v45);
    v19 = operator new(0x98u);
    *(_QWORD *)&v36 = v19;
    memset(v19, 0, 0x98u);
    v40 = *(_OWORD *)v18;
    v41 = *(_OWORD *)(v18 + 16);
    *(_QWORD *)(v18 + 16) = 0;
    *(_QWORD *)(v18 + 24) = 7;
    *(_WORD *)v18 = 0;
    v20 = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
            L"MoUxCoreWorker",
            &word_1800FF6C6,
            0);
    if ( v20 == v23 || (v24 = (v20 - (__int64)L"MoUxCoreWorker") >> 1, v24 == -1) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xC9,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
        v22);
    *(_QWORD *)&v34 = L"MoUxCoreWorker";
    *((_QWORD *)&v34 + 1) = v24;
    v25 = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
            L"MoUxCoreWorker",
            v23,
            v21);
    if ( v25 == v27 || (v28 = (v25 - (__int64)L"MoUxCoreWorker") >> 1, v28 == -1) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xC9,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
        v26);
    v35[0] = (Windows::Logger *)L"MoUxCoreWorker";
    v35[1] = (Windows::Logger *)v28;
    v35[0] = (Windows::Logger *)Windows::Logger::Logger((Windows::Logger *)v19, &v40, 0);
    v37 = 0;
    v38 = 0;
    v39 = 0;
    v29 = -1;
    do
      ++v29;
    while ( aMouxcoreworker[v29] );
    std::wstring::_Construct<1,wchar_t const *>(&v37, L"MoUxCoreWorker");
    v31 = std::map<std::wstring,std::shared_ptr<Windows::Logger>>::operator[](v30, &v37);
    std::shared_ptr<Windows::Logger>::operator=<Windows::Logger,std::default_delete<Windows::Logger>,0>(v31, v35);
    std::wstring::~wstring(&v37);
    v32 = v35[0];
    if ( v35[0] )
    {
      Windows::Logger::~Logger(v35[0]);
      operator delete(v32, (const struct std::nothrow_t *)0x98);
    }
    std::wstring::~wstring(v45);
    std::vector<_GUID>::~vector<_GUID>(&v46);
    std::vector<_GUID>::~vector<_GUID>(&v48);
    if ( !--dword_18014D11C )
    {
      dword_18014D118 = -1;
      ReleaseSRWLockExclusive(&stru_18014D0E0);
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x18B,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\Service.cpp",
      v33);
  }
}

```

## disassembly

```asm
0x18003224c  mov     r11, rsp
0x18003224f  mov     [r11+8], rbx
0x180032253  mov     [r11+10h], rsi
0x180032257  mov     [r11+18h], rdi
0x18003225b  mov     [r11+20h], r14
0x18003225f  push    r15
0x180032261  sub     rsp, 1B0h
0x180032268  mov     rax, cs:__security_cookie
0x18003226f  xor     rax, rsp
0x180032272  mov     [rsp+1B8h+var_10], rax
0x18003227a  xor     esi, esi
0x18003227c  lea     rcx, ?g_LoggerMutex@@3Vmutex@std@@A; std::mutex g_LoggerMutex
0x180032283  mov     [r11-68h], rcx
0x180032287  call    mtx_do_lock
0x18003228c  test    eax, eax
0x18003228e  jnz     loc_18003279A
0x180032294  mov     eax, cs:dword_18014D11C
0x18003229a  cmp     eax, 7FFFFFFFh
0x18003229f  jz      loc_1800327A2
0x1800322a5  xorps   xmm0, xmm0
0x1800322a8  xor     eax, eax
0x1800322aa  movups  [rsp+1B8h+var_28], xmm0
0x1800322b2  mov     [rsp+1B8h+var_18], rax
0x1800322ba  movups  xmm1, cs:xmmword_1800FF7F0
0x1800322c1  movdqu  [rsp+1B8h+var_F8], xmm1
0x1800322ca  movups  xmm1, cs:xmmword_1800FF7E0
0x1800322d1  movdqu  [rsp+1B8h+var_E8], xmm1
0x1800322da  movups  xmm1, cs:xmmword_1800FF7D0
0x1800322e1  movdqu  [rsp+1B8h+var_D8], xmm1
0x1800322ea  movups  xmm1, cs:xmmword_1800FF7A0
0x1800322f1  movdqu  [rsp+1B8h+var_C8], xmm1
0x1800322fa  movups  xmm1, cs:xmmword_1800FF7B0
0x180032301  movdqu  [rsp+1B8h+var_B8], xmm1
0x18003230a  movups  xmm1, cs:xmmword_1800FF7C0
0x180032311  movdqu  [rsp+1B8h+var_A8], xmm1
0x18003231a  movups  xmm1, cs:xmmword_1800FF780
0x180032321  movdqu  [rsp+1B8h+var_98], xmm1
0x18003232a  movups  xmm1, cs:xmmword_1800FF760
0x180032331  movdqu  [rsp+1B8h+var_88], xmm1
0x18003233a  movups  xmm1, cs:xmmword_1800FF790
0x180032341  movdqu  [rsp+1B8h+var_78], xmm1
0x18003234a  lea     rax, [rsp+1B8h+var_F8]
0x180032352  mov     qword ptr [rsp+1B8h+var_158], rax
0x180032357  lea     rax, [rsp+1B8h+var_68]
0x18003235f  mov     qword ptr [rsp+1B8h+var_158+8], rax
0x180032364  movaps  xmm0, [rsp+1B8h+var_158]
0x180032369  movdqa  [rsp+1B8h+var_178], xmm0
0x18003236f  lea     rdx, [rsp+1B8h+var_178]
0x180032374  lea     rcx, [rsp+1B8h+var_28]
0x18003237c  call    ??0?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@V?$initializer_list@U_GUID@@@1@AEBV?$allocator@U_GUID@@@1@@Z; std::vector<_GUID>::vector<_GUID>(std::initializer_list<_GUID>,std::allocator<_GUID> const &)
0x180032381  nop
0x180032382  lea     rdx, [rsp+1B8h+var_60]
0x18003238a  call    ?Logs@FileSystem@Windows@@QEAA?AVpath@filesystem@std@@XZ; Windows::FileSystem::Logs(void)
0x18003238f  mov     rbx, rax
0x180032392  mov     r15d, 98h
0x180032398  mov     ecx, r15d; Size
0x18003239b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800323a0  mov     rdi, rax
0x1800323a3  mov     [rsp+1B8h+var_168], rax
0x1800323a8  mov     r8d, r15d; Size
0x1800323ab  xor     edx, edx; Val
0x1800323ad  mov     rcx, rax; void *
0x1800323b0  call    memset
0x1800323b5  movups  xmm0, xmmword ptr [rbx]
0x1800323b8  movups  [rsp+1B8h+var_128], xmm0
0x1800323c0  movups  xmm1, xmmword ptr [rbx+10h]
0x1800323c4  movups  [rsp+1B8h+var_118], xmm1
0x1800323cc  mov     [rbx+10h], rsi
0x1800323d0  mov     qword ptr [rbx+18h], 7
0x1800323d8  mov     [rbx], si
0x1800323db  xor     r8d, r8d
0x1800323de  lea     r11, word_1800FF6FE
0x1800323e5  mov     rdx, r11
0x1800323e8  lea     rbx, aUpdatesessiono; "UpdateSessionOrchestration"
0x1800323ef  mov     rcx, rbx
0x1800323f2  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x1800323f7  cmp     rax, r11
0x1800323fa  jz      loc_180032780
0x180032400  sub     rax, rbx
0x180032403  sar     rax, 1
0x180032406  or      r14, 0FFFFFFFFFFFFFFFFh
0x18003240a  cmp     rax, r14
0x18003240d  jz      loc_180032780
0x180032413  mov     qword ptr [rsp+1B8h+var_158], rbx
0x180032418  mov     qword ptr [rsp+1B8h+var_158+8], rax
0x18003241d  mov     rdx, r11
0x180032420  mov     rcx, rbx
0x180032423  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x180032428  cmp     rax, r11
0x18003242b  jz      loc_1800327E9
0x180032431  sub     rax, rbx
0x180032434  sar     rax, 1
0x180032437  cmp     rax, r14
0x18003243a  jz      loc_1800327E9
0x180032440  mov     qword ptr [rsp+1B8h+var_178], rbx
0x180032445  mov     qword ptr [rsp+1B8h+var_178+8], rax
0x18003244a  movups  xmm0, [rsp+1B8h+var_158]
0x18003244f  movdqu  [rsp+1B8h+var_158], xmm0
0x180032455  movaps  xmm1, [rsp+1B8h+var_178]
0x18003245a  movdqa  [rsp+1B8h+var_178], xmm1
0x180032460  mov     [rsp+1B8h+var_190], sil; char
0x180032465  lea     rax, [rsp+1B8h+var_128]
0x18003246d  mov     [rsp+1B8h+var_198], rax; void *
0x180032472  lea     r9, [rsp+1B8h+var_158]
0x180032477  lea     r8, [rsp+1B8h+var_178]
0x18003247c  lea     rdx, [rsp+1B8h+var_28]
0x180032484  mov     rcx, rdi; this
0x180032487  call    ??0Logger@Windows@@QEAA@AEBV?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@V?$basic_zstring_view@_W@wil@@1Vpath@filesystem@3@_NI@Z; Windows::Logger::Logger(std::vector<_GUID> const &,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,std::filesystem::path,bool,uint)
0x18003248c  nop
0x18003248d  mov     [rsp+1B8h+var_168], rax
0x180032492  xorps   xmm0, xmm0
0x180032495  movups  [rsp+1B8h+var_148], xmm0
0x18003249a  mov     [rsp+1B8h+var_138], rsi
0x1800324a2  mov     [rsp+1B8h+var_130], rsi
0x1800324aa  mov     r8, r14
0x1800324ad  inc     r8
0x1800324b0  cmp     [rbx+r8*2], si
0x1800324b5  jnz     short loc_1800324AD
0x1800324b7  mov     rdx, rbx
0x1800324ba  lea     rcx, [rsp+1B8h+var_148]
0x1800324bf  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800324c4  nop
0x1800324c5  lea     rdx, [rsp+1B8h+var_148]
0x1800324ca  call    ??A?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@VLogger@Windows@@@2@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@VLogger@Windows@@@2@@std@@@2@@std@@QEAAAEAV?$shared_ptr@VLogger@Windows@@@1@$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::map<std::wstring,std::shared_ptr<Windows::Logger>>::operator[](std::wstring &&)
0x1800324cf  lea     rdx, [rsp+1B8h+var_168]
0x1800324d4  mov     rcx, rax
0x1800324d7  call    ??$?4VLogger@Windows@@U?$default_delete@VLogger@Windows@@@std@@$0A@@?$shared_ptr@VLogger@Windows@@@std@@QEAAAEAV01@$$QEAV?$unique_ptr@VLogger@Windows@@U?$default_delete@VLogger@Windows@@@std@@@1@@Z; std::shared_ptr<Windows::Logger>::operator=<Windows::Logger,std::default_delete<Windows::Logger>,0>(std::unique_ptr<Windows::Logger> &&)
0x1800324dc  nop
0x1800324dd  lea     rcx, [rsp+1B8h+var_148]; void *
0x1800324e2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800324e7  nop
0x1800324e8  mov     rbx, [rsp+1B8h+var_168]
0x1800324ed  test    rbx, rbx
0x1800324f0  jz      short loc_180032506
0x1800324f2  mov     rcx, rbx; this
0x1800324f5  call    ??1Logger@Windows@@UEAA@XZ; Windows::Logger::~Logger(void)
0x1800324fa  mov     rdx, r15; struct std::nothrow_t *
0x1800324fd  mov     rcx, rbx; void *
0x180032500  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180032505  nop
0x180032506  lea     rcx, [rsp+1B8h+var_60]; void *
0x18003250e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180032513  xorps   xmm0, xmm0
0x180032516  xor     eax, eax
0x180032518  movups  [rsp+1B8h+var_40], xmm0
0x180032520  mov     [rsp+1B8h+var_30], rax
0x180032528  movups  xmm1, cs:xmmword_1800FF770
0x18003252f  movdqu  [rsp+1B8h+var_128], xmm1
0x180032538  movups  xmm1, cs:xmmword_1800FF750
0x18003253f  movdqu  [rsp+1B8h+var_118], xmm1
0x180032548  movups  xmm1, cs:xmmword_1800FF740
0x18003254f  movdqu  [rsp+1B8h+var_108], xmm1
0x180032558  lea     rax, [rsp+1B8h+var_128]
0x180032560  mov     qword ptr [rsp+1B8h+var_178], rax
0x180032565  lea     rax, [rsp+1B8h+var_F8]
0x18003256d  mov     qword ptr [rsp+1B8h+var_178+8], rax
0x180032572  movaps  xmm0, [rsp+1B8h+var_178]
0x180032577  movdqa  [rsp+1B8h+var_178], xmm0
0x18003257d  lea     rdx, [rsp+1B8h+var_178]
0x180032582  lea     rcx, [rsp+1B8h+var_40]
0x18003258a  call    ??0?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@V?$initializer_list@U_GUID@@@1@AEBV?$allocator@U_GUID@@@1@@Z; std::vector<_GUID>::vector<_GUID>(std::initializer_list<_GUID>,std::allocator<_GUID> const &)
0x18003258f  nop
0x180032590  lea     rdx, [rsp+1B8h+var_60]
0x180032598  call    ?Logs@FileSystem@Windows@@QEAA?AVpath@filesystem@std@@XZ; Windows::FileSystem::Logs(void)
0x18003259d  mov     rbx, rax
0x1800325a0  mov     rcx, r15; Size
0x1800325a3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800325a8  mov     rdi, rax
0x1800325ab  mov     qword ptr [rsp+1B8h+var_158], rax
0x1800325b0  mov     r8, r15; Size
0x1800325b3  xor     edx, edx; Val
0x1800325b5  mov     rcx, rax; void *
0x1800325b8  call    memset
0x1800325bd  movups  xmm0, xmmword ptr [rbx]
0x1800325c0  movups  [rsp+1B8h+var_128], xmm0
0x1800325c8  movups  xmm1, xmmword ptr [rbx+10h]
0x1800325cc  movups  [rsp+1B8h+var_118], xmm1
0x1800325d4  mov     [rbx+10h], rsi
0x1800325d8  mov     qword ptr [rbx+18h], 7
0x1800325e0  mov     [rbx], si
0x1800325e3  xor     r8d, r8d
0x1800325e6  lea     r11, word_1800FF6C6
0x1800325ed  mov     rdx, r11
0x1800325f0  lea     rbx, aMouxcoreworker; "MoUxCoreWorker"
0x1800325f7  mov     rcx, rbx
0x1800325fa  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x1800325ff  cmp     rax, r11
0x180032602  jz      loc_1800327CF
0x180032608  sub     rax, rbx
0x18003260b  sar     rax, 1
0x18003260e  cmp     rax, r14
0x180032611  jz      loc_1800327CF
0x180032617  mov     qword ptr [rsp+1B8h+var_178], rbx
0x18003261c  mov     qword ptr [rsp+1B8h+var_178+8], rax
0x180032621  mov     rdx, r11
0x180032624  mov     rcx, rbx
0x180032627  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x18003262c  cmp     rax, r11
0x18003262f  jz      loc_1800327B5
0x180032635  sub     rax, rbx
0x180032638  sar     rax, 1
0x18003263b  cmp     rax, r14
0x18003263e  jz      loc_1800327B5
0x180032644  mov     [rsp+1B8h+var_168], rbx
0x180032649  mov     [rsp+1B8h+var_168+8], rax
0x18003264e  movups  xmm0, [rsp+1B8h+var_178]
0x180032653  movdqu  [rsp+1B8h+var_178], xmm0
0x180032659  movaps  xmm1, xmmword ptr [rsp+1B8h+var_168]
0x18003265e  movdqa  xmmword ptr [rsp+1B8h+var_168], xmm1
0x180032664  mov     [rsp+1B8h+var_190], sil; char
0x180032669  lea     rax, [rsp+1B8h+var_128]
0x180032671  mov     [rsp+1B8h+var_198], rax; void *
0x180032676  lea     r9, [rsp+1B8h+var_178]
0x18003267b  lea     r8, [rsp+1B8h+var_168]
0x180032680  lea     rdx, [rsp+1B8h+var_40]
0x180032688  mov     rcx, rdi; this
0x18003268b  call    ??0Logger@Windows@@QEAA@AEBV?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@V?$basic_zstring_view@_W@wil@@1Vpath@filesystem@3@_NI@Z; Windows::Logger::Logger(std::vector<_GUID> const &,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,std::filesystem::path,bool,uint)
0x180032690  nop
0x180032691  mov     [rsp+1B8h+var_168], rax
0x180032696  xorps   xmm0, xmm0
0x180032699  movups  [rsp+1B8h+var_148], xmm0
0x18003269e  mov     [rsp+1B8h+var_138], rsi
0x1800326a6  mov     [rsp+1B8h+var_130], rsi
0x1800326ae  mov     r8, r14
0x1800326b1  inc     r8
0x1800326b4  cmp     [rbx+r8*2], si
0x1800326b9  jnz     short loc_1800326B1
0x1800326bb  mov     rdx, rbx
0x1800326be  lea     rcx, [rsp+1B8h+var_148]
0x1800326c3  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800326c8  nop
0x1800326c9  lea     rdx, [rsp+1B8h+var_148]
0x1800326ce  call    ??A?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@VLogger@Windows@@@2@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@VLogger@Windows@@@2@@std@@@2@@std@@QEAAAEAV?$shared_ptr@VLogger@Windows@@@1@$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::map<std::wstring,std::shared_ptr<Windows::Logger>>::operator[](std::wstring &&)
0x1800326d3  lea     rdx, [rsp+1B8h+var_168]
0x1800326d8  mov     rcx, rax
0x1800326db  call    ??$?4VLogger@Windows@@U?$default_delete@VLogger@Windows@@@std@@$0A@@?$shared_ptr@VLogger@Windows@@@std@@QEAAAEAV01@$$QEAV?$unique_ptr@VLogger@Windows@@U?$default_delete@VLogger@Windows@@@std@@@1@@Z; std::shared_ptr<Windows::Logger>::operator=<Windows::Logger,std::default_delete<Windows::Logger>,0>(std::unique_ptr<Windows::Logger> &&)
0x1800326e0  nop
0x1800326e1  lea     rcx, [rsp+1B8h+var_148]; void *
0x1800326e6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800326eb  nop
0x1800326ec  mov     rbx, [rsp+1B8h+var_168]
0x1800326f1  test    rbx, rbx
0x1800326f4  jz      short loc_18003270A
0x1800326f6  mov     rcx, rbx; this
0x1800326f9  call    ??1Logger@Windows@@UEAA@XZ; Windows::Logger::~Logger(void)
0x1800326fe  mov     rdx, r15; struct std::nothrow_t *
0x180032701  mov     rcx, rbx; void *
0x180032704  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180032709  nop
0x18003270a  lea     rcx, [rsp+1B8h+var_60]; void *
0x180032712  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180032717  nop
0x180032718  lea     rcx, [rsp+1B8h+var_40]
0x180032720  call    ??1?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::~vector<_GUID>(void)
0x180032725  nop
0x180032726  lea     rcx, [rsp+1B8h+var_28]
0x18003272e  call    ??1?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::~vector<_GUID>(void)
0x180032733  nop
0x180032734  sub     cs:dword_18014D11C, 1
0x18003273b  jnz     short loc_180032752
0x18003273d  mov     cs:dword_18014D118, r14d
0x180032744  lea     rcx, stru_18014D0E0; SRWLock
0x18003274b  call    cs:__imp_ReleaseSRWLockExclusive
0x180032751  nop
0x180032752  mov     rcx, [rsp+1B8h+var_10]
0x18003275a  xor     rcx, rsp; StackCookie
0x18003275d  call    __security_check_cookie
0x180032762  lea     r11, [rsp+1B8h+var_8]
0x18003276a  mov     rbx, [r11+10h]
0x18003276e  mov     rsi, [r11+18h]
0x180032772  mov     rdi, [r11+20h]
0x180032776  mov     r14, [r11+28h]
0x18003277a  mov     rsp, r11
0x18003277d  pop     r15
0x18003277f  retn
0x180032780  mov     rcx, [rsp+1B8h]; this
0x180032788  lea     r8, aCW1SPackagesMi_2; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18003278f  mov     edx, 0C9h; void *
0x180032794  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18003279a  lea     ecx, [rsi+5]; int
0x18003279d  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800327a2  dec     eax
0x1800327a4  mov     cs:dword_18014D11C, eax
0x1800327aa  mov     ecx, 6; int
0x1800327af  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800327b5  mov     rcx, [rsp+1B8h]; this
0x1800327bd  lea     r8, aCW1SPackagesMi_2; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x1800327c4  mov     edx, 0C9h; void *
0x1800327c9  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800327cf  mov     rcx, [rsp+1B8h]; this
0x1800327d7  lea     r8, aCW1SPackagesMi_2; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x1800327de  mov     edx, 0C9h; void *
0x1800327e3  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800327e9  mov     rcx, [rsp+1B8h]; this
0x1800327f1  lea     r8, aCW1SPackagesMi_2; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x1800327f8  mov     edx, 0C9h; void *
0x1800327fd  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
