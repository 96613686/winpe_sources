# _StackLockFile<StackLockFileWin32Reader,StackLockFileWin32Writer>::EnumerateTokens(wchar_t const *,std::function<void (std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)>)

- ea: `0x18000ecdc`
- end: `0x18000f0f6`
- name: `?EnumerateTokens@?$_StackLockFile@UStackLockFileWin32Reader@@UStackLockFileWin32Writer@@@@SAXPEB_WV?$function@$$A6AXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z@std@@@Z`
- size: `1050`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000c510`

## callees

- `0x18000ecdc`
- `0x180024a7c`
- `0x180024b60`
- `0x180025aa0`
- `0x180025d10`
- `0x180025de8`
- `0x180025f88`
- `0x1800264ac`
- `0x180026648`
- `0x1800266b0`
- `0x180027228`
- `0x1800286d0`
- `0x180028728`
- `0x1800295e8`
- `0x180029644`
- `0x18003fd5c`
- `0x1800427d0`
- `0x180047a30`

## string_xrefs

- `0x18000f0e9`: `directory_entry::status`
- `0x18000f0d5`: `directory_iterator::directory_iterator`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall _StackLockFile<StackLockFileWin32Reader,StackLockFileWin32Writer>::EnumerateTokens(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rax
  struct std::error_code *v4; // r8
  bool v5; // al
  const struct std::filesystem::path *v6; // r9
  unsigned int v7; // eax
  volatile signed __int32 *v8; // rbx
  _QWORD *v9; // rax
  _QWORD *v10; // rax
  _QWORD *v11; // rax
  __int64 *v12; // rax
  std::filesystem::path *v13; // rax
  struct std::filesystem::path *v14; // rax
  __int64 v15; // rcx
  unsigned int v16; // eax
  __int64 v17; // rcx
  volatile signed __int32 *v18; // rdi
  __int64 result; // rax
  __int64 v20; // rdx
  __int64 v21; // rcx
  char v22[8]; // [rsp+30h] [rbp-D8h] BYREF
  void ***v23; // [rsp+38h] [rbp-D0h]
  __int128 v24; // [rsp+48h] [rbp-C0h] BYREF
  _OWORD v25[2]; // [rsp+58h] [rbp-B0h] BYREF
  _QWORD v26[2]; // [rsp+78h] [rbp-90h] BYREF
  _QWORD v27[2]; // [rsp+88h] [rbp-80h] BYREF
  _QWORD v28[4]; // [rsp+98h] [rbp-70h] BYREF
  _BYTE v29[32]; // [rsp+B8h] [rbp-50h] BYREF
  _BYTE v30[32]; // [rsp+D8h] [rbp-30h] BYREF
  _BYTE v31[16]; // [rsp+F8h] [rbp-10h] BYREF
  _BYTE v32[16]; // [rsp+108h] [rbp+0h] BYREF
  _BYTE v33[32]; // [rsp+118h] [rbp+10h] BYREF
  __int64 v34; // [rsp+138h] [rbp+30h]
  _QWORD v35[2]; // [rsp+140h] [rbp+38h] BYREF
  __int64 v36; // [rsp+150h] [rbp+48h]
  unsigned __int64 v37; // [rsp+158h] [rbp+50h]
  _BYTE v38[32]; // [rsp+160h] [rbp+58h] BYREF
  _BYTE v39[40]; // [rsp+180h] [rbp+78h] BYREF
  _OWORD v40[2]; // [rsp+1A8h] [rbp+A0h] BYREF
  _BYTE v41[32]; // [rsp+1C8h] [rbp+C0h] BYREF

  v34 = a2;
  v3 = -1;
  do
    ++v3;
  while ( *(_WORD *)(a1 + 2 * v3) );
  *(_QWORD *)&v24 = a1;
  *((_QWORD *)&v24 + 1) = v3;
  std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v38, &v24);
  *(_QWORD *)v22 = 0;
  v23 = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
  v5 = std::filesystem::exists((std::filesystem *)v38, (const struct std::filesystem::path *)v22, v4);
  if ( *(_DWORD *)v22 )
    std::filesystem::_Throw_fs_error((std::filesystem *)"exists", v22, (const struct std::error_code *)v38, v6);
  if ( v5 )
  {
    v24 = 0;
    v7 = std::filesystem::_Dir_enum_impl::_Initialize_dir_enum<std::filesystem::_Dir_enum_impl>(&v24, v38);
    if ( v7 )
      std::filesystem::_Throw_fs_error("directory_iterator::directory_iterator", v7, v38);
    v25[0] = 0;
    v8 = (volatile signed __int32 *)*((_QWORD *)&v24 + 1);
    if ( *((_QWORD *)&v24 + 1) )
      _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v24 + 1) + 8LL));
    v25[0] = v24;
    if ( v8 )
      _InterlockedIncrement(v8 + 2);
    v25[1] = 0;
    if ( v8 )
    {
      if ( _InterlockedExchangeAdd(v8 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
        if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
      }
    }
    while ( *(_QWORD *)&v25[0] )
    {
      v40[0] = **(_OWORD **)&v25[0];
      v40[1] = *(_OWORD *)(*(_QWORD *)&v25[0] + 16LL);
      std::wstring::wstring(v41, *(_QWORD *)&v25[0] + 32LL);
      std::filesystem::directory_entry::_Get_any_status(v40, v22, 3);
      if ( (_DWORD)v23 && ((*(_DWORD *)v22 - 1) & 0xFFFFFFF7) != 0 )
        std::filesystem::_Throw_fs_error("directory_entry::status", (unsigned int)v23, v41);
      if ( *(_DWORD *)v22 != 3 )
      {
        std::wstring::wstring(v35, v41);
        v9 = v35;
        if ( v37 > 7 )
          v9 = (_QWORD *)v35[0];
        v26[0] = v9;
        v26[1] = v36;
        if ( *(_QWORD *)(std::filesystem::_Parse_extension(v31, v26) + 8) )
        {
          v10 = v35;
          if ( v37 > 7 )
            v10 = (_QWORD *)v35[0];
          v27[0] = v10;
          v27[1] = v36;
          v11 = (_QWORD *)std::filesystem::_Parse_extension(v32, v27);
          v28[0] = *v11;
          v28[1] = v11[1];
          std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v39, v28);
          v12 = &_StackLockFile<StackLockFileWin32Reader,StackLockFileWin32Writer>::_extensionLockFile;
          if ( (unsigned __int64)qword_180063AE8 > 7 )
            v12 = (__int64 *)_StackLockFile<StackLockFileWin32Reader,StackLockFileWin32Writer>::_extensionLockFile;
          v28[2] = v12;
          v28[3] = qword_180063AE0;
          if ( !(unsigned int)std::filesystem::path::compare((std::filesystem *)v39) )
          {
            v13 = (std::filesystem::path *)std::filesystem::path::filename(v35, v33);
            v14 = std::filesystem::path::replace_extension(v13);
            std::wstring::wstring(v30, v14);
            std::wstring::_Tidy_deallocate(v33);
            std::wstring::wstring(v29, v30);
            v15 = *(_QWORD *)(a2 + 56);
            if ( !v15 )
              std::_Xbad_function_call();
            (*(void (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v15 + 16LL))(v15, v29);
            std::wstring::_Tidy_deallocate(v29);
            std::wstring::_Tidy_deallocate(v30);
          }
          std::wstring::_Tidy_deallocate(v39);
        }
        std::wstring::_Tidy_deallocate(v35);
      }
      std::wstring::_Tidy_deallocate(v41);
      v16 = std::filesystem::_Dir_enum_impl::_Advance_and_reset_if_no_more_files(v25);
      if ( v16 )
        std::filesystem::_Throw_fs_error(v17, v16);
    }
    v18 = (volatile signed __int32 *)*((_QWORD *)&v25[0] + 1);
    if ( *((_QWORD *)&v25[0] + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v25[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
        if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
      }
    }
    if ( v8 )
    {
      if ( _InterlockedExchangeAdd(v8 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
        if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
      }
    }
  }
  result = std::wstring::_Tidy_deallocate(v38);
  v21 = *(_QWORD *)(a2 + 56);
  if ( v21 )
  {
    LOBYTE(v20) = v21 != a2;
    result = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v21 + 32LL))(v21, v20);
    *(_QWORD *)(a2 + 56) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000ecdc  mov     rax, rsp
0x18000ecdf  mov     [rax+8], rbx
0x18000ece3  mov     [rax+18h], rsi
0x18000ece7  mov     [rax+20h], rdi
0x18000eceb  push    rbp
0x18000ecec  push    r14
0x18000ecee  push    r15
0x18000ecf0  lea     rbp, [rax-108h]
0x18000ecf7  sub     rsp, 1F0h
0x18000ecfe  mov     rax, cs:__security_cookie
0x18000ed05  xor     rax, rsp
0x18000ed08  mov     [rbp+100h+var_20], rax
0x18000ed0f  mov     rsi, rdx
0x18000ed12  mov     [rbp+100h+var_D0], rdx
0x18000ed16  xor     r14d, r14d
0x18000ed19  or      r15, 0FFFFFFFFFFFFFFFFh
0x18000ed1d  mov     rax, r15
0x18000ed20  inc     rax
0x18000ed23  cmp     [rcx+rax*2], r14w
0x18000ed28  jnz     short loc_18000ED20
0x18000ed2a  mov     qword ptr [rsp+200h+var_1C8+8], rcx
0x18000ed2f  mov     qword ptr [rsp+200h+var_1B8], rax
0x18000ed34  lea     rdx, [rsp+200h+var_1C8+8]
0x18000ed39  lea     rcx, [rbp+100h+var_A8]
0x18000ed3d  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::wstring_view,std::filesystem::_Normal_conversion)
0x18000ed42  nop
0x18000ed43  mov     qword ptr [rsp+200h+var_1D8], r14
0x18000ed48  lea     rax, ?_Static@?1???$_Immortalize_memcpy_image@V_System_error_category@std@@@std@@YAAEBV_System_error_category@1@XZ@4U?$_Constexpr_immortalize_impl@V_System_error_category@std@@@1@A; std::_Constexpr_immortalize_impl<std::_System_error_category> `std::_Immortalize_memcpy_image<std::_System_error_category>(void)'::`2'::_Static
0x18000ed4f  mov     [rsp+200h+var_1D0], rax
0x18000ed54  lea     rdx, [rsp+200h+var_1D8]; struct std::filesystem::path *
0x18000ed59  lea     rcx, [rbp+100h+var_A8]; this
0x18000ed5d  call    ?exists@filesystem@std@@YA_NAEBVpath@12@AEAVerror_code@2@@Z; std::filesystem::exists(std::filesystem::path const &,std::error_code &)
0x18000ed62  cmp     dword ptr [rsp+200h+var_1D8], r14d
0x18000ed67  jnz     loc_18000F0B9
0x18000ed6d  test    al, al
0x18000ed6f  jz      loc_18000F056
0x18000ed75  xorps   xmm0, xmm0
0x18000ed78  movdqa  [rsp+200h+var_1C8+8], xmm0
0x18000ed7e  lea     rdx, [rbp+100h+var_A8]
0x18000ed82  lea     rcx, [rsp+200h+var_1C8+8]
0x18000ed87  call    ??$_Initialize_dir_enum@U_Dir_enum_impl@filesystem@std@@@_Dir_enum_impl@filesystem@std@@SA?AW4__std_win_error@@AEAV?$shared_ptr@U_Dir_enum_impl@filesystem@std@@@2@AEBVpath@12@W4directory_options@12@@Z; std::filesystem::_Dir_enum_impl::_Initialize_dir_enum<std::filesystem::_Dir_enum_impl>(std::shared_ptr<std::filesystem::_Dir_enum_impl> &,std::filesystem::path const &,std::filesystem::directory_options)
0x18000ed8c  test    eax, eax
0x18000ed8e  jnz     loc_18000F0CF
0x18000ed94  xorps   xmm0, xmm0
0x18000ed97  movups  [rsp+200h+var_1B8+8], xmm0
0x18000ed9c  mov     rbx, qword ptr [rsp+200h+var_1B8]
0x18000eda1  test    rbx, rbx
0x18000eda4  jz      short loc_18000EDAA
0x18000eda6  lock inc dword ptr [rbx+8]
0x18000edaa  movaps  xmm0, [rsp+200h+var_1C8+8]
0x18000edaf  movdqa  [rsp+200h+var_1B8+8], xmm0
0x18000edb5  test    rbx, rbx
0x18000edb8  jz      short loc_18000EDBE
0x18000edba  lock inc dword ptr [rbx+8]
0x18000edbe  xorps   xmm1, xmm1
0x18000edc1  movdqu  [rsp+200h+var_1A8+8], xmm1
0x18000edc7  test    rbx, rbx
0x18000edca  jz      short loc_18000EE04
0x18000edcc  mov     eax, r15d
0x18000edcf  lock xadd [rbx+8], eax
0x18000edd4  add     eax, r15d
0x18000edd7  jnz     short loc_18000EE04
0x18000edd9  mov     rax, [rbx]
0x18000eddc  mov     rcx, rbx
0x18000eddf  mov     rax, [rax]
0x18000ede2  call    _guard_dispatch_icall
0x18000ede7  mov     eax, r15d
0x18000edea  lock xadd [rbx+0Ch], eax
0x18000edef  add     eax, r15d
0x18000edf2  jnz     short loc_18000EE04
0x18000edf4  mov     rax, [rbx]
0x18000edf7  mov     rcx, rbx
0x18000edfa  mov     rax, [rax+8]
0x18000edfe  call    _guard_dispatch_icall
0x18000ee03  nop
0x18000ee04  mov     rdx, qword ptr [rsp+200h+var_1B8+8]
0x18000ee09  test    rdx, rdx
0x18000ee0c  jz      loc_18000EFD7
0x18000ee12  movups  xmm0, xmmword ptr [rdx]
0x18000ee15  movaps  [rbp+100h+var_60], xmm0
0x18000ee1c  movups  xmm1, xmmword ptr [rdx+10h]
0x18000ee20  movaps  [rbp+100h+var_50], xmm1
0x18000ee27  add     rdx, 20h ; ' '
0x18000ee2b  lea     rcx, [rbp+100h+var_40]
0x18000ee32  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000ee37  nop
0x18000ee38  mov     r8d, 3
0x18000ee3e  lea     rdx, [rsp+200h+var_1D8]
0x18000ee43  lea     rcx, [rbp+100h+var_60]
0x18000ee4a  call    ?_Get_any_status@directory_entry@filesystem@std@@AEBA?AU_File_status_and_error@23@W4__std_fs_stats_flags@@@Z; std::filesystem::directory_entry::_Get_any_status(__std_fs_stats_flags)
0x18000ee4f  mov     rax, qword ptr [rsp+200h+var_1D8]
0x18000ee54  mov     edx, dword ptr [rsp+200h+var_1D0]
0x18000ee58  test    edx, edx
0x18000ee5a  jz      short loc_18000EE6B
0x18000ee5c  lea     ecx, [rax-1]
0x18000ee5f  test    ecx, 0FFFFFFF7h
0x18000ee65  jnz     loc_18000F0E2
0x18000ee6b  cmp     eax, 3
0x18000ee6e  jz      loc_18000EFB4
0x18000ee74  lea     rdx, [rbp+100h+var_40]
0x18000ee7b  lea     rcx, [rbp+100h+var_C8]
0x18000ee7f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000ee84  nop
0x18000ee85  lea     rax, [rbp+100h+var_C8]
0x18000ee89  cmp     [rbp+100h+var_B0], 7
0x18000ee8e  cmova   rax, [rbp+100h+var_C8]
0x18000ee93  mov     [rsp+200h+var_190], rax
0x18000ee98  mov     rax, [rbp+100h+var_B8]
0x18000ee9c  mov     [rsp+200h+var_188], rax
0x18000eea1  lea     rdx, [rsp+200h+var_190]
0x18000eea6  lea     rcx, [rbp+100h+var_110]
0x18000eeaa  call    ?_Parse_extension@filesystem@std@@YA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@2@V32@@Z; std::filesystem::_Parse_extension(std::wstring_view)
0x18000eeaf  cmp     [rax+8], r14
0x18000eeb3  jz      loc_18000EFAA
0x18000eeb9  lea     rax, [rbp+100h+var_C8]
0x18000eebd  cmp     [rbp+100h+var_B0], 7
0x18000eec2  cmova   rax, [rbp+100h+var_C8]
0x18000eec7  mov     [rbp+100h+var_180], rax
0x18000eecb  mov     rax, [rbp+100h+var_B8]
0x18000eecf  mov     [rbp+100h+var_178], rax
0x18000eed3  lea     rdx, [rbp+100h+var_180]
0x18000eed7  lea     rcx, [rbp+100h+var_100]
0x18000eedb  call    ?_Parse_extension@filesystem@std@@YA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@2@V32@@Z; std::filesystem::_Parse_extension(std::wstring_view)
0x18000eee0  mov     rcx, [rax]
0x18000eee3  mov     [rbp+100h+var_170], rcx
0x18000eee7  mov     rax, [rax+8]
0x18000eeeb  mov     [rbp+100h+var_168], rax
0x18000eeef  lea     rdx, [rbp+100h+var_170]
0x18000eef3  lea     rcx, [rbp+100h+var_88]
0x18000eef7  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::wstring_view,std::filesystem::_Normal_conversion)
0x18000eefc  nop
0x18000eefd  lea     rax, ?_extensionLockFile@?$_StackLockFile@UStackLockFileWin32Reader@@UStackLockFileWin32Writer@@@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const _StackLockFile<StackLockFileWin32Reader,StackLockFileWin32Writer>::_extensionLockFile
0x18000ef04  cmp     cs:qword_180063AE8, 7
0x18000ef0c  cmova   rax, cs:?_extensionLockFile@?$_StackLockFile@UStackLockFileWin32Reader@@UStackLockFileWin32Writer@@@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const _StackLockFile<StackLockFileWin32Reader,StackLockFileWin32Writer>::_extensionLockFile
0x18000ef14  mov     [rbp+100h+var_160], rax
0x18000ef18  mov     rax, cs:qword_180063AE0
0x18000ef1f  mov     [rbp+100h+var_158], rax
0x18000ef23  lea     rdx, [rbp+100h+var_160]
0x18000ef27  lea     rcx, [rbp+100h+var_88]; this
0x18000ef2b  call    ?compare@path@filesystem@std@@QEBAHV?$basic_string_view@_WU?$char_traits@_W@std@@@3@@Z; std::filesystem::path::compare(std::wstring_view)
0x18000ef30  test    eax, eax
0x18000ef32  jnz     short loc_18000EFA0
0x18000ef34  lea     rdx, [rbp+100h+var_F0]
0x18000ef38  lea     rcx, [rbp+100h+var_C8]
0x18000ef3c  call    ?filename@path@filesystem@std@@QEBA?AV123@XZ; std::filesystem::path::filename(void)
0x18000ef41  nop
0x18000ef42  mov     rcx, rax; this
0x18000ef45  call    ?replace_extension@path@filesystem@std@@QEAAAEAV123@XZ; std::filesystem::path::replace_extension(void)
0x18000ef4a  mov     rdx, rax
0x18000ef4d  lea     rcx, [rbp+100h+var_130]
0x18000ef51  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000ef56  nop
0x18000ef57  lea     rcx, [rbp+100h+var_F0]
0x18000ef5b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000ef60  lea     rdx, [rbp+100h+var_130]
0x18000ef64  lea     rcx, [rbp+100h+var_150]
0x18000ef68  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000ef6d  nop
0x18000ef6e  mov     rcx, [rsi+38h]
0x18000ef72  test    rcx, rcx
0x18000ef75  jz      loc_18000F0AB
0x18000ef7b  mov     rax, [rcx]
0x18000ef7e  lea     rdx, [rbp+100h+var_150]
0x18000ef82  mov     rax, [rax+10h]
0x18000ef86  call    _guard_dispatch_icall
0x18000ef8b  nop
0x18000ef8c  lea     rcx, [rbp+100h+var_150]
0x18000ef90  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000ef95  nop
0x18000ef96  lea     rcx, [rbp+100h+var_130]
0x18000ef9a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000ef9f  nop
0x18000efa0  lea     rcx, [rbp+100h+var_88]
0x18000efa4  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000efa9  nop
0x18000efaa  lea     rcx, [rbp+100h+var_C8]
0x18000efae  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000efb3  nop
0x18000efb4  lea     rcx, [rbp+100h+var_40]
0x18000efbb  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000efc0  lea     rcx, [rsp+200h+var_1B8+8]
0x18000efc5  call    ?_Advance_and_reset_if_no_more_files@_Dir_enum_impl@filesystem@std@@SA?AW4__std_win_error@@AEAV?$shared_ptr@U_Dir_enum_impl@filesystem@std@@@3@@Z; std::filesystem::_Dir_enum_impl::_Advance_and_reset_if_no_more_files(std::shared_ptr<std::filesystem::_Dir_enum_impl> &)
0x18000efca  test    eax, eax
0x18000efcc  jnz     loc_18000F0B1
0x18000efd2  jmp     loc_18000EE04
0x18000efd7  mov     rdi, qword ptr [rsp+200h+var_1A8]
0x18000efdc  test    rdi, rdi
0x18000efdf  jz      short loc_18000F019
0x18000efe1  mov     eax, r15d
0x18000efe4  lock xadd [rdi+8], eax
0x18000efe9  add     eax, r15d
0x18000efec  jnz     short loc_18000F019
0x18000efee  mov     rax, [rdi]
0x18000eff1  mov     rcx, rdi
0x18000eff4  mov     rax, [rax]
0x18000eff7  call    _guard_dispatch_icall
0x18000effc  mov     eax, r15d
0x18000efff  lock xadd [rdi+0Ch], eax
0x18000f004  add     eax, r15d
0x18000f007  jnz     short loc_18000F019
0x18000f009  mov     rax, [rdi]
0x18000f00c  mov     rcx, rdi
0x18000f00f  mov     rax, [rax+8]
0x18000f013  call    _guard_dispatch_icall
0x18000f018  nop
0x18000f019  test    rbx, rbx
0x18000f01c  jz      short loc_18000F056
0x18000f01e  mov     eax, r15d
0x18000f021  lock xadd [rbx+8], eax
0x18000f026  add     eax, r15d
0x18000f029  jnz     short loc_18000F056
0x18000f02b  mov     rax, [rbx]
0x18000f02e  mov     rcx, rbx
0x18000f031  mov     rax, [rax]
0x18000f034  call    _guard_dispatch_icall
0x18000f039  mov     eax, r15d
0x18000f03c  lock xadd [rbx+0Ch], eax
0x18000f041  add     eax, r15d
0x18000f044  jnz     short loc_18000F056
0x18000f046  mov     rax, [rbx]
0x18000f049  mov     rcx, rbx
0x18000f04c  mov     rax, [rax+8]
0x18000f050  call    _guard_dispatch_icall
0x18000f055  nop
0x18000f056  lea     rcx, [rbp+100h+var_A8]
0x18000f05a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000f05f  nop
0x18000f060  mov     rcx, [rsi+38h]
0x18000f064  test    rcx, rcx
0x18000f067  jz      short loc_18000F07F
0x18000f069  cmp     rcx, rsi
0x18000f06c  setnz   dl
0x18000f06f  mov     rax, [rcx]
0x18000f072  mov     rax, [rax+20h]
0x18000f076  call    _guard_dispatch_icall
0x18000f07b  mov     [rsi+38h], r14
0x18000f07f  mov     rcx, [rbp+100h+var_20]
0x18000f086  xor     rcx, rsp; StackCookie
0x18000f089  call    __security_check_cookie
0x18000f08e  lea     r11, [rsp+200h+var_10]
0x18000f096  mov     rbx, [r11+20h]
0x18000f09a  mov     rsi, [r11+30h]
0x18000f09e  mov     rdi, [r11+38h]
0x18000f0a2  mov     rsp, r11
0x18000f0a5  pop     r15
0x18000f0a7  pop     r14
0x18000f0a9  pop     rbp
0x18000f0aa  retn
0x18000f0ab  call    ?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18000f0b1  mov     edx, eax
0x18000f0b3  call    ?_Throw_fs_error@filesystem@std@@YAXPEBDW4__std_win_error@@@Z; std::filesystem::_Throw_fs_error(char const *,__std_win_error)
0x18000f0b9  lea     r8, [rbp+100h+var_A8]; struct std::error_code *
0x18000f0bd  lea     rdx, [rsp+200h+var_1D8]; char *
0x18000f0c2  lea     rcx, aExists; "exists"
0x18000f0c9  call    ?_Throw_fs_error@filesystem@std@@YAXPEBDAEBVerror_code@2@AEBVpath@12@@Z; std::filesystem::_Throw_fs_error(char const *,std::error_code const &,std::filesystem::path const &)
0x18000f0cf  lea     r8, [rbp+100h+var_A8]
0x18000f0d3  mov     edx, eax
0x18000f0d5  lea     rcx, aDirectoryItera_0; "directory_iterator::directory_iterator"
0x18000f0dc  call    ?_Throw_fs_error@filesystem@std@@YAXPEBDW4__std_win_error@@AEBVpath@12@@Z; std::filesystem::_Throw_fs_error(char const *,__std_win_error,std::filesystem::path const &)
0x18000f0e2  lea     r8, [rbp+100h+var_40]
0x18000f0e9  lea     rcx, aDirectoryEntry; "directory_entry::status"
0x18000f0f0  call    ?_Throw_fs_error@filesystem@std@@YAXPEBDW4__std_win_error@@AEBVpath@12@@Z; std::filesystem::_Throw_fs_error(char const *,__std_win_error,std::filesystem::path const &)
```
