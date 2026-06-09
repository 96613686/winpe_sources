# Diagnostics::NerdHerd::FindOfflineFiles(std::filesystem::path)

- ea: `0x180039744`
- end: `0x180039b97`
- name: `?FindOfflineFiles@NerdHerd@Diagnostics@@CA?AV?$vector@Vpath@filesystem@std@@V?$allocator@Vpath@filesystem@std@@@3@@std@@Vpath@filesystem@4@@Z`
- size: `1107`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x180038ebc`

## callees

- `0x18001639c`
- `0x180018b04`
- `0x180018eec`
- `0x180028ed4`
- `0x180039744`
- `0x1800648e4`
- `0x180064c68`
- `0x180065084`
- `0x180065408`
- `0x1800664ec`
- `0x18006716c`
- `0x18008fc40`
- `0x18008fe00`
- `0x180095af0`
- `0x180096170`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800398b7`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800398b7`

## string_xrefs

- `0x180039969`: `Skipping entry during directory enumeration: %hs (%d)`
- `0x180039b89`: `recursive_directory_iterator::recursive_directory_iterator`

## pseudocode

```c
__int64 __fastcall Diagnostics::NerdHerd::FindOfflineFiles(__int64 a1, __int64 a2)
{
  __int64 v2; // r12
  __int64 v3; // rdi
  int v4; // r15d
  unsigned int v5; // esi
  char v6; // al
  char *v7; // rbx
  char *v8; // r14
  int v9; // esi
  unsigned int v10; // ebx
  const char *v11; // rax
  int v12; // ebx
  unsigned int v13; // esi
  char **v14; // rax
  char *v15; // r14
  const char *v17; // rax
  const char *v18; // [rsp+20h] [rbp-348h]
  __int64 v19; // [rsp+30h] [rbp-338h]
  __int64 v20; // [rsp+38h] [rbp-330h]
  __int64 v21; // [rsp+40h] [rbp-328h]
  __int128 v22; // [rsp+48h] [rbp-320h] BYREF
  __int64 v23; // [rsp+58h] [rbp-310h]
  __int128 v24; // [rsp+60h] [rbp-308h]
  char *v25; // [rsp+70h] [rbp-2F8h] BYREF
  char *v26; // [rsp+78h] [rbp-2F0h]
  char *v27[3]; // [rsp+80h] [rbp-2E8h] BYREF
  unsigned __int64 v28; // [rsp+98h] [rbp-2D0h]
  __int64 v29; // [rsp+A0h] [rbp-2C8h]
  _BYTE v30[32]; // [rsp+B0h] [rbp-2B8h] BYREF
  HANDLE hFindFile; // [rsp+D0h] [rbp-298h] BYREF
  _BYTE v32[593]; // [rsp+D8h] [rbp-290h] BYREF
  __int16 v33; // [rsp+329h] [rbp-3Fh]
  char v34; // [rsp+32Bh] [rbp-3Dh]
  unsigned int v35; // [rsp+32Ch] [rbp-3Ch]
  wil::details::in1diag3 *retaddr; // [rsp+368h] [rbp+0h]

  try
  {
    v2 = a2;
    v3 = a1;
    v23 = a1;
    v29 = a2;
    v4 = 1;
    *(_OWORD *)a1 = 0;
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_QWORD *)(a1 + 16) = 0;
    v22 = 0;
    v24 = 0;
    std::wstring::wstring(v30, a2);
    hFindFile = (HANDLE)-1LL;
    v5 = std::filesystem::_Dir_enum_impl::_Open_dir(v30, 2, &hFindFile, v32);
    if ( v5 )
    {
      v6 = 0;
      if ( v5 != 18 )
      {
LABEL_6:
        v32[592] = v6;
        v33 = 0;
        v34 = 0;
        v35 = v5;
        if ( v6 )
        {
          v7 = (char *)operator new(0x78u);
          v25 = v7;
          *((_DWORD *)v7 + 2) = 1;
          *((_DWORD *)v7 + 3) = 1;
          *(_QWORD *)v7 = &std::_Ref_count_obj2<std::filesystem::_Recursive_dir_enum_impl>::`vftable';
          v8 = v7 + 16;
          std::filesystem::_Dir_enum_impl::_Dir_enum_impl((std::filesystem::_Dir_enum_impl *)(v7 + 16));
          *((_QWORD *)v7 + 11) = 0;
          *((_QWORD *)v7 + 12) = 0;
          *((_QWORD *)v7 + 13) = 0;
          *((_DWORD *)v7 + 28) = 2;
          v7[116] = 1;
          v4 = 9;
          *(_QWORD *)&v24 = v7 + 16;
          *((_QWORD *)&v24 + 1) = v7;
          v5 = v35;
        }
        else
        {
          v7 = (char *)*((_QWORD *)&v24 + 1);
          v8 = (char *)v24;
        }
        if ( hFindFile != (HANDLE)-1LL && !FindClose(hFindFile) )
          abort();
        std::wstring::~wstring(v30);
        if ( v5 )
          std::filesystem::_Throw_fs_error("recursive_directory_iterator::recursive_directory_iterator", v5, v2);
        *(_QWORD *)&v22 = v8;
        *((_QWORD *)&v22 + 1) = v7;
        v9 = 0;
        v24 = 0;
        goto LABEL_53;
      }
    }
    else
    {
      v6 = 1;
    }
    v5 = 0;
    goto LABEL_6;
  }
  catch ( ... )
  {
    v17 = (const char *)v29;
    if ( *(_QWORD *)(v29 + 24) > 7u )
      v17 = *(const char **)v29;
    wil::details::in1diag3::Log_CaughtExceptionMsg(
      retaddr,
      (void *)0x1E7,
      (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\libs\\diag\\NerdHerd.hpp",
      "Failed to open directory for enumeration: %ls",
      v17);
    if ( *((_QWORD *)&v22 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v22 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (***((void (__fastcall ****)(_QWORD))&v22 + 1))(*((_QWORD *)&v22 + 1));
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v22 + 1) + 12LL), 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v22 + 1) + 8LL))(*((_QWORD *)&v22 + 1));
      }
    }
    v2 = v29;
    v3 = v23;
    goto LABEL_44;
  }
LABEL_53:
  try
  {
    while ( 1 )
    {
      if ( !v8 )
        goto LABEL_58;
      if ( !v9 )
        break;
      v10 = (unsigned __int16)v9 | 0x80070000;
      if ( v9 <= 0 )
        v10 = v9;
      ((void (__fastcall *)(void ***, char **, _QWORD))`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static[2])(
        &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static,
        v27,
        (unsigned int)v9);
      v4 |= 2u;
      v11 = (const char *)v27;
      if ( v28 > 0xF )
        v11 = v27[0];
      LODWORD(v19) = v9;
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)0x1F4,
        (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\libs\\diag\\NerdHerd.hpp",
        (const char *)v10,
        (int)"Skipping entry during directory enumeration: %hs (%d)",
        v11,
        v19);
LABEL_33:
      std::string::~string(v27);
LABEL_34:
      v9 = std::filesystem::_Recursive_dir_enum_impl::_Advance_and_reset_if_no_more_files(&v22);
      v7 = (char *)*((_QWORD *)&v22 + 1);
      v8 = (char *)v22;
    }
    std::filesystem::directory_entry::_Get_any_status(v8, &v25, 3);
    v12 = (int)v26;
    if ( (_DWORD)v25 == 2 )
    {
      if ( (_DWORD)v26 )
      {
LABEL_26:
        v13 = (unsigned __int16)v12 | 0x80070000;
        if ( v12 <= 0 )
          v13 = v12;
        ((void (__fastcall *)(void ***, char **, _QWORD))`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static[2])(
          &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static,
          v27,
          (unsigned int)v12);
        v4 |= 4u;
        LODWORD(v21) = v4;
        v14 = v27;
        if ( v28 > 0xF )
          v14 = (char **)v27[0];
        v15 = v8 + 32;
        if ( *((_QWORD *)v15 + 3) > 7u )
          v15 = *(char **)v15;
        LODWORD(v20) = v12;
        wil::details::in1diag3::Log_HrMsg(
          retaddr,
          (void *)0x202,
          (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\libs\\diag\\NerdHerd.hpp",
          (const char *)v13,
          (int)"Skipping entry '%ls': %hs (%d)",
          v15,
          v14,
          v20,
          v21);
        goto LABEL_33;
      }
      if ( *(_QWORD *)(v3 + 8) == *(_QWORD *)(v3 + 16) )
      {
        std::vector<std::filesystem::path>::_Emplace_reallocate<std::filesystem::path const &>(
          v3,
          *(_QWORD *)(v3 + 8),
          v8 + 32);
      }
      else
      {
        std::wstring::wstring(*(_QWORD *)(v3 + 8), v8 + 32);
        *(_QWORD *)(v3 + 8) += 32LL;
      }
    }
    if ( !v12 )
      goto LABEL_34;
    goto LABEL_26;
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtExceptionMsg(
      retaddr,
      (void *)0x209,
      (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\libs\\diag\\NerdHerd.hpp",
      "Error during directory enumeration, returning partial results",
      v18);
    v7 = (char *)*((_QWORD *)&v22 + 1);
    v3 = v23;
    v2 = v29;
  }
LABEL_58:
  if ( v7 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v7 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(void *))v7)(v7);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v7 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(char *))(*(_QWORD *)v7 + 8LL))(v7);
    }
  }
LABEL_44:
  std::wstring::~wstring(v2);
  return v3;
}

```

## disassembly

```asm
0x180039744  mov     r11, rsp
0x180039747  mov     [r11+18h], rbx
0x18003974b  mov     [r11+20h], rsi
0x18003974f  push    rdi
0x180039750  push    r12
0x180039752  push    r13
0x180039754  push    r14
0x180039756  push    r15
0x180039758  sub     rsp, 340h
0x18003975f  mov     rax, cs:__security_cookie
0x180039766  xor     rax, rsp
0x180039769  mov     [rsp+368h+var_38], rax
0x180039771  mov     r12, rdx
0x180039774  mov     rdi, rcx
0x180039777  mov     [rsp+368h+var_310], rcx
0x18003977c  mov     [r11-2C8h], rdx
0x180039783  mov     r15d, 1
0x180039789  mov     dword ptr [rsp+368h+var_328], r15d
0x18003978e  xorps   xmm0, xmm0
0x180039791  xor     eax, eax
0x180039793  movups  xmmword ptr [rcx], xmm0
0x180039796  mov     [rcx], rax
0x180039799  mov     [rcx+8], rax
0x18003979d  mov     [rcx+10h], rax
0x1800397a1  mov     dword ptr [rsp+368h+var_328], r15d
0x1800397a6  xorps   xmm1, xmm1
0x1800397a9  movdqu  [rsp+368h+var_320], xmm1
0x1800397af  movdqu  [rsp+368h+var_308], xmm0
0x1800397b5  lea     rcx, [r11-2B8h]
0x1800397bc  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800397c1  nop
0x1800397c2  mov     [rsp+368h+hFindFile], 0FFFFFFFFFFFFFFFFh
0x1800397ce  lea     r9, [rsp+368h+var_290]
0x1800397d6  lea     r8, [rsp+368h+hFindFile]
0x1800397de  lea     r13d, [r15+1]
0x1800397e2  mov     edx, r13d
0x1800397e5  lea     rcx, [rsp+368h+var_2B8]
0x1800397ed  call    ?_Open_dir@_Dir_enum_impl@filesystem@std@@SA?AW4__std_win_error@@AEAVpath@23@W4directory_options@23@AEAU_Find_file_handle@23@AEAU__std_fs_find_data@@@Z; std::filesystem::_Dir_enum_impl::_Open_dir(std::filesystem::path &,std::filesystem::directory_options,std::filesystem::_Find_file_handle &,__std_fs_find_data &)
0x1800397f2  mov     esi, eax
0x1800397f4  xor     ecx, ecx
0x1800397f6  test    eax, eax
0x1800397f8  jnz     short loc_1800397FF
0x1800397fa  mov     al, r15b
0x1800397fd  jmp     short loc_180039806
0x1800397ff  xor     al, al
0x180039801  cmp     esi, 12h
0x180039804  jnz     short loc_180039808
0x180039806  xor     esi, esi
0x180039808  mov     [rsp+368h+var_40], al
0x18003980f  mov     [rsp+368h+var_3F], cx
0x180039817  mov     [rsp+368h+var_3D], cl
0x18003981e  mov     [rsp+368h+var_3C], esi
0x180039825  test    al, al
0x180039827  jz      short loc_18003989F
0x180039829  mov     ecx, 78h ; 'x'; Size
0x18003982e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180039833  mov     rbx, rax
0x180039836  mov     [rsp+368h+var_2F8], rax
0x18003983b  mov     [rax+8], r15d
0x18003983f  mov     [rax+0Ch], r15d
0x180039843  lea     rax, ??_7?$_Ref_count_obj2@U_Recursive_dir_enum_impl@filesystem@std@@@std@@6B@; const std::_Ref_count_obj2<std::filesystem::_Recursive_dir_enum_impl>::`vftable'
0x18003984a  mov     [rbx], rax
0x18003984d  lea     r14, [rbx+10h]
0x180039851  lea     rdx, [rsp+368h+var_2B8]
0x180039859  mov     rcx, r14; this
0x18003985c  call    ??0_Dir_enum_impl@filesystem@std@@QEAA@$$QEAU_Creator@012@W4directory_options@12@@Z; std::filesystem::_Dir_enum_impl::_Dir_enum_impl(std::filesystem::_Dir_enum_impl::_Creator &&,std::filesystem::directory_options)
0x180039861  mov     qword ptr [rbx+58h], 0
0x180039869  mov     qword ptr [rbx+60h], 0
0x180039871  mov     qword ptr [rbx+68h], 0
0x180039879  mov     [rbx+70h], r13d
0x18003987d  mov     [rbx+74h], r15b
0x180039881  mov     r15d, 9
0x180039887  mov     dword ptr [rsp+368h+var_328], r15d
0x18003988c  mov     qword ptr [rsp+368h+var_308], r14
0x180039891  mov     qword ptr [rsp+368h+var_308+8], rbx
0x180039896  mov     esi, [rsp+368h+var_3C]
0x18003989d  jmp     short loc_1800398A9
0x18003989f  mov     rbx, qword ptr [rsp+368h+var_308+8]
0x1800398a4  mov     r14, qword ptr [rsp+368h+var_308]
0x1800398a9  mov     rcx, [rsp+368h+hFindFile]; hFindFile
0x1800398b1  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800398b5  jz      short loc_1800398C5
0x1800398b7  call    cs:__imp_FindClose
0x1800398bd  test    eax, eax
0x1800398bf  jz      loc_180039B7E
0x1800398c5  lea     rcx, [rsp+368h+var_2B8]
0x1800398cd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800398d2  test    esi, esi
0x1800398d4  jnz     loc_180039B84
0x1800398da  mov     qword ptr [rsp+368h+var_320], r14
0x1800398df  mov     qword ptr [rsp+368h+var_320+8], rbx
0x1800398e4  xor     esi, esi
0x1800398e6  xorps   xmm1, xmm1
0x1800398e9  movdqu  [rsp+368h+var_308], xmm1
0x1800398ef  movq    r13, xmm1
0x1800398f4  cmp     r14, r13
0x1800398f7  jz      loc_180039AA2
0x1800398fd  test    esi, esi
0x1800398ff  jz      loc_18003998E
0x180039905  movzx   ebx, si
0x180039908  or      ebx, 80070000h
0x18003990e  test    esi, esi
0x180039910  cmovle  ebx, esi
0x180039913  mov     rax, cs:?_Static@?1???$_Immortalize_memcpy_image@V_System_error_category@std@@@std@@YAAEBV_System_error_category@1@XZ@4V21@B; std::_System_error_category const `std::_Immortalize_memcpy_image<std::_System_error_category>(void)'::`2'::_Static
0x18003991a  mov     r8d, esi
0x18003991d  lea     rdx, [rsp+368h+var_2E8]
0x180039925  lea     rcx, ?_Static@?1???$_Immortalize_memcpy_image@V_System_error_category@std@@@std@@YAAEBV_System_error_category@1@XZ@4V21@B; std::_System_error_category const `std::_Immortalize_memcpy_image<std::_System_error_category>(void)'::`2'::_Static
0x18003992c  mov     rax, [rax+10h]
0x180039930  call    _guard_dispatch_icall
0x180039935  or      r15d, 2
0x180039939  mov     dword ptr [rsp+368h+var_328], r15d
0x18003993e  lea     rax, [rsp+368h+var_2E8]
0x180039946  cmp     [rsp+368h+var_2D0], 0Fh
0x18003994f  cmova   rax, [rsp+368h+var_2E8]
0x180039958  mov     rcx, [rsp+368h]; this
0x180039960  mov     dword ptr [rsp+368h+var_338], esi
0x180039964  mov     [rsp+368h+var_340], rax; char *
0x180039969  lea     rax, aSkippingEntryD; "Skipping entry during directory enumera"...
0x180039970  mov     qword ptr [rsp+368h+var_348], rax; int
0x180039975  mov     r9d, ebx; char *
0x180039978  lea     r8, aCW1SSrcCalliop; "C:\\__w\\1\\s\\src\\Calliope\\libs\\dia"...
0x18003997f  mov     edx, 1F4h; void *
0x180039984  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180039989  jmp     loc_180039A7A
0x18003998e  mov     r8d, 3
0x180039994  lea     rdx, [rsp+368h+var_2F8]
0x180039999  mov     rcx, r14
0x18003999c  call    ?_Get_any_status@directory_entry@filesystem@std@@AEBA?AU_File_status_and_error@23@W4__std_fs_stats_flags@@@Z; std::filesystem::directory_entry::_Get_any_status(__std_fs_stats_flags)
0x1800399a1  mov     ebx, dword ptr [rsp+368h+var_2F0]
0x1800399a5  cmp     dword ptr [rsp+368h+var_2F8], 2
0x1800399aa  jnz     short loc_1800399DB
0x1800399ac  test    ebx, ebx
0x1800399ae  jnz     short loc_1800399E3
0x1800399b0  lea     r8, [r14+20h]
0x1800399b4  mov     rax, [rdi+8]
0x1800399b8  cmp     rax, [rdi+10h]
0x1800399bc  jz      short loc_1800399D0
0x1800399be  mov     rdx, r8
0x1800399c1  mov     rcx, rax
0x1800399c4  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800399c9  add     qword ptr [rdi+8], 20h ; ' '
0x1800399ce  jmp     short loc_1800399DB
0x1800399d0  mov     rdx, rax
0x1800399d3  mov     rcx, rdi
0x1800399d6  call    ??$_Emplace_reallocate@AEBVpath@filesystem@std@@@?$vector@Vpath@filesystem@std@@V?$allocator@Vpath@filesystem@std@@@3@@std@@AEAAPEAVpath@filesystem@1@QEAV231@AEBV231@@Z; std::vector<std::filesystem::path>::_Emplace_reallocate<std::filesystem::path const &>(std::filesystem::path * const,std::filesystem::path const &)
0x1800399db  test    ebx, ebx
0x1800399dd  jz      loc_180039A87
0x1800399e3  movzx   esi, bx
0x1800399e6  or      esi, 80070000h
0x1800399ec  test    ebx, ebx
0x1800399ee  cmovle  esi, ebx
0x1800399f1  mov     rax, cs:?_Static@?1???$_Immortalize_memcpy_image@V_System_error_category@std@@@std@@YAAEBV_System_error_category@1@XZ@4V21@B; std::_System_error_category const `std::_Immortalize_memcpy_image<std::_System_error_category>(void)'::`2'::_Static
0x1800399f8  mov     r8d, ebx
0x1800399fb  lea     rdx, [rsp+368h+var_2E8]
0x180039a03  lea     rcx, ?_Static@?1???$_Immortalize_memcpy_image@V_System_error_category@std@@@std@@YAAEBV_System_error_category@1@XZ@4V21@B; std::_System_error_category const `std::_Immortalize_memcpy_image<std::_System_error_category>(void)'::`2'::_Static
0x180039a0a  mov     rax, [rax+10h]
0x180039a0e  call    _guard_dispatch_icall
0x180039a13  or      r15d, 4
0x180039a17  mov     dword ptr [rsp+368h+var_328], r15d
0x180039a1c  lea     rax, [rsp+368h+var_2E8]
0x180039a24  cmp     [rsp+368h+var_2D0], 0Fh
0x180039a2d  cmova   rax, [rsp+368h+var_2E8]
0x180039a36  add     r14, 20h ; ' '
0x180039a3a  cmp     qword ptr [r14+18h], 7
0x180039a3f  jbe     short loc_180039A44
0x180039a41  mov     r14, [r14]
0x180039a44  mov     rcx, [rsp+368h]; this
0x180039a4c  mov     dword ptr [rsp+368h+var_330], ebx
0x180039a50  mov     [rsp+368h+var_338], rax
0x180039a55  mov     [rsp+368h+var_340], r14; char *
0x180039a5a  lea     rax, aSkippingEntryL; "Skipping entry '%ls': %hs (%d)"
0x180039a61  mov     qword ptr [rsp+368h+var_348], rax; int
0x180039a66  mov     r9d, esi; char *
0x180039a69  lea     r8, aCW1SSrcCalliop; "C:\\__w\\1\\s\\src\\Calliope\\libs\\dia"...
0x180039a70  mov     edx, 202h; void *
0x180039a75  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180039a7a  lea     rcx, [rsp+368h+var_2E8]
0x180039a82  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180039a87  lea     rcx, [rsp+368h+var_320]
0x180039a8c  call    ?_Advance_and_reset_if_no_more_files@_Recursive_dir_enum_impl@filesystem@std@@SA?AW4__std_win_error@@AEAV?$shared_ptr@U_Recursive_dir_enum_impl@filesystem@std@@@3@@Z; std::filesystem::_Recursive_dir_enum_impl::_Advance_and_reset_if_no_more_files(std::shared_ptr<std::filesystem::_Recursive_dir_enum_impl> &)
0x180039a91  mov     esi, eax
0x180039a93  mov     rbx, qword ptr [rsp+368h+var_320+8]
0x180039a98  mov     r14, qword ptr [rsp+368h+var_320]
0x180039a9d  jmp     loc_1800398F4
0x180039aa2  jmp     short loc_180039AB6
0x180039aa4  mov     rbx, qword ptr [rsp+368h+var_320+8]
0x180039aa9  mov     rdi, [rsp+368h+var_310]
0x180039aae  mov     r12, [rsp+368h+var_2C8]
0x180039ab6  test    rbx, rbx
0x180039ab9  jz      loc_180039B46
0x180039abf  or      eax, 0FFFFFFFFh
0x180039ac2  lock xadd [rbx+8], eax
0x180039ac7  cmp     eax, 1
0x180039aca  jnz     short loc_180039B46
0x180039acc  mov     rax, [rbx]
0x180039acf  mov     rcx, rbx
0x180039ad2  mov     rax, [rax]
0x180039ad5  call    _guard_dispatch_icall
0x180039ada  or      eax, 0FFFFFFFFh
0x180039add  lock xadd [rbx+0Ch], eax
0x180039ae2  cmp     eax, 1
0x180039ae5  jnz     short loc_180039B46
0x180039ae7  mov     rax, [rbx]
0x180039aea  mov     rcx, rbx
0x180039aed  mov     rax, [rax+8]
0x180039af1  call    _guard_dispatch_icall
0x180039af6  jmp     short loc_180039B46
0x180039af8  mov     rbx, qword ptr [rsp+368h+var_320+8]
0x180039afd  test    rbx, rbx
0x180039b00  jz      short loc_180039B39
0x180039b02  or      eax, 0FFFFFFFFh
0x180039b05  lock xadd [rbx+8], eax
0x180039b0a  cmp     eax, 1
0x180039b0d  jnz     short loc_180039B39
0x180039b0f  mov     rax, [rbx]
0x180039b12  mov     rcx, rbx
0x180039b15  mov     rax, [rax]
0x180039b18  call    _guard_dispatch_icall
0x180039b1d  or      eax, 0FFFFFFFFh
0x180039b20  lock xadd [rbx+0Ch], eax
0x180039b25  cmp     eax, 1
0x180039b28  jnz     short loc_180039B39
0x180039b2a  mov     rax, [rbx]
0x180039b2d  mov     rcx, rbx
0x180039b30  mov     rax, [rax+8]
0x180039b34  call    _guard_dispatch_icall
0x180039b39  mov     r12, [rsp+368h+var_2C8]
0x180039b41  mov     rdi, [rsp+368h+var_310]
0x180039b46  mov     rcx, r12
0x180039b49  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180039b4e  mov     rax, rdi
0x180039b51  mov     rcx, [rsp+368h+var_38]
0x180039b59  xor     rcx, rsp; StackCookie
0x180039b5c  call    __security_check_cookie
0x180039b61  lea     r11, [rsp+368h+var_28]
0x180039b69  mov     rbx, [r11+40h]
0x180039b6d  mov     rsi, [r11+48h]
0x180039b71  mov     rsp, r11
0x180039b74  pop     r15
0x180039b76  pop     r14
0x180039b78  pop     r13
0x180039b7a  pop     r12
0x180039b7c  pop     rdi
0x180039b7d  retn
0x180039b7e  call    abort
0x180039b84  mov     r8, r12
0x180039b87  mov     edx, esi
0x180039b89  lea     rcx, aRecursiveDirec; "recursive_directory_iterator::recursive"...
0x180039b90  call    ?_Throw_fs_error@filesystem@std@@YAXPEBDW4__std_win_error@@AEBVpath@12@@Z; std::filesystem::_Throw_fs_error(char const *,__std_win_error,std::filesystem::path const &)
```
