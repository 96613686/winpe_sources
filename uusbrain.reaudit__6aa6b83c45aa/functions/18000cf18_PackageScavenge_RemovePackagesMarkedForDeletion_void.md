# PackageScavenge::RemovePackagesMarkedForDeletion(void)

- ea: `0x18000cf18`
- end: `0x18000d527`
- name: `?RemovePackagesMarkedForDeletion@PackageScavenge@@CA?AU?$pair@_K_K@std@@XZ`
- size: `1551`
- prototype: ``
- caller_count: `1`
- callee_count: `26`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000c510`

## callees

- `0x18000cf18`
- `0x18000d660`
- `0x18000ea38`
- `0x18000ec44`
- `0x18000f84c`
- `0x180017680`
- `0x18001913c`
- `0x18001a390`
- `0x18001a84c`
- `0x18001a8cc`
- `0x1800252e0`
- `0x180025de8`
- `0x180025f88`
- `0x1800264ac`
- `0x180026648`
- `0x1800266b0`
- `0x180027228`
- `0x1800286d0`
- `0x180028728`
- `0x180028e4c`
- `0x1800293bc`
- `0x1800295e8`
- `0x180029644`
- `0x1800427d0`
- `0x180047a30`
- `0x180047ab0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cfd4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cfd4`

## string_xrefs

- `0x18000d50c`: `directory_iterator::directory_iterator`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 **__fastcall PackageScavenge::RemovePackagesMarkedForDeletion(__int64 **a1)
{
  __int64 **v1; // r12
  __int64 *v2; // r15
  __int64 *v3; // r13
  __int64 *v4; // rdx
  __int64 v5; // rcx
  struct std::error_code *v6; // r8
  bool v7; // al
  const struct std::filesystem::path *v8; // r9
  unsigned int v9; // eax
  volatile signed __int32 *v10; // rbx
  void **Src; // rax
  __int64 v12; // rax
  _QWORD *v13; // r15
  __int64 v14; // rdx
  _QWORD *v15; // rcx
  char *v16; // r12
  char v17; // r15
  char *i; // rdx
  char *v19; // rax
  const struct std::filesystem::path *v20; // rdx
  bool v21; // zf
  unsigned int v22; // eax
  __int64 v23; // rcx
  volatile signed __int32 *v24; // r14
  const char *v26; // rax
  const wchar_t *v27; // rcx
  LPVOID pv; // [rsp+40h] [rbp-2B8h] BYREF
  char v29[8]; // [rsp+48h] [rbp-2B0h] BYREF
  void ***v30; // [rsp+50h] [rbp-2A8h]
  __int64 *v31; // [rsp+58h] [rbp-2A0h]
  __int64 **v32; // [rsp+60h] [rbp-298h]
  __int128 v33; // [rsp+70h] [rbp-288h] BYREF
  __int64 *v34; // [rsp+80h] [rbp-278h]
  __int64 **v35; // [rsp+88h] [rbp-270h]
  __int128 v36; // [rsp+90h] [rbp-268h] BYREF
  __int128 v37; // [rsp+A0h] [rbp-258h]
  __int64 **v38; // [rsp+B0h] [rbp-248h]
  _QWORD v39[4]; // [rsp+B8h] [rbp-240h] BYREF
  __int128 v40; // [rsp+D8h] [rbp-220h] BYREF
  __int128 v41; // [rsp+E8h] [rbp-210h]
  const std::exception *v42; // [rsp+F8h] [rbp-200h] BYREF
  _BYTE v43[32]; // [rsp+100h] [rbp-1F8h] BYREF
  _BYTE v44[32]; // [rsp+120h] [rbp-1D8h] BYREF
  _BYTE v45[40]; // [rsp+140h] [rbp-1B8h] BYREF
  _BYTE v46[40]; // [rsp+168h] [rbp-190h] BYREF
  __int128 v47; // [rsp+190h] [rbp-168h]
  __int128 v48; // [rsp+1A0h] [rbp-158h]
  _QWORD v49[4]; // [rsp+1B0h] [rbp-148h] BYREF
  _QWORD v50[30]; // [rsp+1D0h] [rbp-128h] BYREF

  v35 = a1;
  v38 = a1;
  v1 = a1;
  v32 = a1;
  v2 = 0;
  v31 = 0;
  v3 = 0;
  v34 = 0;
  pv = 0;
  v4 = &UusPackage::_subdirSxSRoot;
  if ( (unsigned __int64)qword_1800638C8 > 7 )
    v4 = (__int64 *)UusPackage::_subdirSxSRoot;
  wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(
    &pv,
    v4);
  v5 = -1;
  do
    ++v5;
  while ( *((_WORD *)pv + v5) );
  *(_QWORD *)&v33 = pv;
  *((_QWORD *)&v33 + 1) = v5;
  std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v46, &v33);
  if ( pv )
    CoTaskMemFree(pv);
  *(_QWORD *)v29 = 0;
  v30 = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
  v7 = std::filesystem::exists((std::filesystem *)v46, (const struct std::filesystem::path *)v29, v6);
  if ( *(_DWORD *)v29 )
    std::filesystem::_Throw_fs_error((std::filesystem *)"exists", v29, (const struct std::error_code *)v46, v8);
  if ( v7 )
  {
    v36 = 0;
    v9 = std::filesystem::_Dir_enum_impl::_Initialize_dir_enum<std::filesystem::_Dir_enum_impl>(&v36, v46);
    if ( v9 )
      std::filesystem::_Throw_fs_error("directory_iterator::directory_iterator", v9, v46);
    v33 = 0;
    v10 = (volatile signed __int32 *)*((_QWORD *)&v36 + 1);
    if ( *((_QWORD *)&v36 + 1) )
      _InterlockedAdd((volatile signed __int32 *)(*((_QWORD *)&v36 + 1) + 8LL), 1u);
    v33 = v36;
    if ( v10 )
      _InterlockedAdd(v10 + 2, 1u);
    v37 = 0;
    if ( v10 )
    {
      if ( _InterlockedExchangeAdd(v10 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
        if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
      }
    }
    while ( (_QWORD)v33 != (_QWORD)v37 )
    {
      v47 = *(_OWORD *)v33;
      v48 = *(_OWORD *)(v33 + 16);
      std::wstring::wstring(v49, v33 + 32);
      if ( 0x7FFFFFFFFFFFFFFELL == qword_180063B00 )
        std::_Xlen_string();
      Src = &PackageScavenge::_deletionPreffix;
      if ( (unsigned __int64)qword_180063B08 > 7 )
        Src = (void **)PackageScavenge::_deletionPreffix;
      std::wstring::wstring(v43, 1, Src, qword_180063B00);
      v12 = std::wstring::append(v43);
      v40 = 0;
      v41 = 0;
      v40 = *(_OWORD *)v12;
      v41 = *(_OWORD *)(v12 + 16);
      *(_QWORD *)(v12 + 16) = 0;
      *(_QWORD *)(v12 + 24) = 7;
      *(_WORD *)v12 = 0;
      v13 = (_QWORD *)std::basic_regex<wchar_t,std::regex_traits<wchar_t>>::basic_regex<wchar_t,std::regex_traits<wchar_t>>(
                        v45,
                        &v40);
      *(_QWORD *)v29 = v13;
      v14 = std::filesystem::path::filename(v49, v44);
      std::wstring::wstring(v39, v14);
      v15 = v39;
      if ( v39[3] > 7u )
        v15 = (_QWORD *)v39[0];
      pv = v15;
      v16 = (char *)v15 + 2 * v39[2];
      if ( *v13 )
      {
        v17 = 0;
        memset(v50, 0, 0xE8u);
        std::_Matcher<wchar_t const *,wchar_t,std::regex_traits<wchar_t>,wchar_t const *>::_Matcher<wchar_t const *,wchar_t,std::regex_traits<wchar_t>,wchar_t const *>(
          (unsigned int)v50,
          (_DWORD)pv,
          (_DWORD)v16,
          *(_DWORD *)v29 + 8,
          **(_QWORD **)v29,
          *(_DWORD *)(**(_QWORD **)v29 + 40LL),
          *(_DWORD *)(**(_QWORD **)v29 + 32LL),
          16);
        if ( (unsigned __int8)std::_Matcher<wchar_t const *,wchar_t,std::regex_traits<wchar_t>,wchar_t const *>::_Match<std::allocator<std::sub_match<wchar_t const *>>>(v50) )
        {
LABEL_37:
          v17 = 1;
        }
        else if ( pv != v16 )
        {
          HIDWORD(v50[23]) = HIDWORD(v50[23]) & 0xFFFFDEFF | 0x100;
          for ( i = (char *)pv + 2; ; i = (char *)pv + 2 )
          {
            v19 = (char *)std::_Matcher<wchar_t const *,wchar_t,std::regex_traits<wchar_t>,wchar_t const *>::_Skip(
                            v50,
                            i,
                            v16,
                            0);
            pv = v19;
            if ( v19 == v16 )
              break;
            v50[21] = v19;
            if ( (unsigned __int8)std::_Matcher<wchar_t const *,wchar_t,std::regex_traits<wchar_t>,wchar_t const *>::_Match<std::allocator<std::sub_match<wchar_t const *>>>(v50) )
              goto LABEL_37;
          }
          v50[21] = v16;
          if ( (unsigned __int8)std::_Matcher<wchar_t const *,wchar_t,std::regex_traits<wchar_t>,wchar_t const *>::_Match<std::allocator<std::sub_match<wchar_t const *>>>(v50) )
            v17 = 1;
        }
        std::vector<std::_Loop_vals_t>::~vector<std::_Loop_vals_t>(&v50[16]);
        std::vector<std::_Loop_vals_t>::~vector<std::_Loop_vals_t>(&v50[13]);
        std::vector<enum UusCapability>::~vector<enum UusCapability>(&v50[9]);
        std::vector<std::_Loop_vals_t>::~vector<std::_Loop_vals_t>(&v50[5]);
        std::vector<enum UusCapability>::~vector<enum UusCapability>(&v50[1]);
      }
      else
      {
        v17 = 0;
      }
      std::wstring::_Tidy_deallocate(v39);
      std::wstring::_Tidy_deallocate(v44);
      std::basic_regex<wchar_t,std::regex_traits<wchar_t>>::~basic_regex<wchar_t,std::regex_traits<wchar_t>>(v45);
      std::wstring::_Tidy_deallocate(&v40);
      std::wstring::_Tidy_deallocate(v43);
      v21 = v17 == 0;
      v2 = v31;
      if ( !v21 )
      {
        try
        {
          v2 = (__int64 *)((char *)v31 + 1);
          v31 = v2;
          *(_QWORD *)v29 = v2;
          std::filesystem::remove_all((std::filesystem *)v49, v20);
          v3 = (__int64 *)((char *)v3 + 1);
          v34 = v3;
        }
        catch ( const std::exception *v42 )
        {
          v26 = (const char *)(*(__int64 (__fastcall **)(const std::exception *))(*(_QWORD *)v42 + 8LL))(v42);
          v27 = (const wchar_t *)v49;
          if ( v49[3] > 7u )
            v27 = (const wchar_t *)v49[0];
          uus::UndockedUpdateTelemetry::UusFailedToRemoveInvalidPackage(v27, v26);
          v2 = *(__int64 **)v29;
          v31 = *(__int64 **)v29;
          v3 = v34;
          v10 = (volatile signed __int32 *)*((_QWORD *)&v36 + 1);
          v35 = v38;
        }
      }
      std::wstring::_Tidy_deallocate(v49);
      v22 = std::filesystem::_Dir_enum_impl::_Advance_and_reset_if_no_more_files(&v33);
      if ( v22 )
        std::filesystem::_Throw_fs_error(v23, v22);
    }
    v24 = (volatile signed __int32 *)*((_QWORD *)&v33 + 1);
    if ( *((_QWORD *)&v33 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v33 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v24)(v24);
        if ( _InterlockedExchangeAdd(v24 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v24 + 8LL))(v24);
      }
    }
    if ( v10 )
    {
      if ( _InterlockedExchangeAdd(v10 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
        if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
      }
    }
    v1 = v32;
  }
  *v35 = v2;
  v1[1] = v3;
  std::wstring::_Tidy_deallocate(v46);
  return v1;
}

```

## disassembly

```asm
0x18000cf18  mov     [rsp+arg_8], rbx
0x18000cf1d  mov     [rsp+arg_10], rsi
0x18000cf22  push    rdi
0x18000cf23  push    r12
0x18000cf25  push    r13
0x18000cf27  push    r14
0x18000cf29  push    r15
0x18000cf2b  sub     rsp, 2D0h
0x18000cf32  mov     rax, cs:__security_cookie
0x18000cf39  xor     rax, rsp
0x18000cf3c  mov     [rsp+2F8h+var_38], rax
0x18000cf44  mov     [rsp+2F8h+var_270], rcx
0x18000cf4c  mov     [rsp+2F8h+var_248], rcx
0x18000cf54  mov     r12, rcx
0x18000cf57  mov     [rsp+2F8h+var_298], rcx
0x18000cf5c  xor     edi, edi
0x18000cf5e  mov     r15d, edi
0x18000cf61  mov     [rsp+2F8h+var_2A0], rdi
0x18000cf66  mov     r13d, edi
0x18000cf69  mov     [rsp+2F8h+var_278], rdi
0x18000cf71  mov     [rsp+2F8h+pv], rdi
0x18000cf76  lea     rdx, ?_subdirSxSRoot@UusPackage@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const UusPackage::_subdirSxSRoot
0x18000cf7d  cmp     cs:qword_1800638C8, 7
0x18000cf85  cmova   rdx, cs:?_subdirSxSRoot@UusPackage@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const UusPackage::_subdirSxSRoot
0x18000cf8d  lea     rcx, [rsp+2F8h+pv]
0x18000cf92  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(wchar_t const *)
0x18000cf97  nop
0x18000cf98  mov     rax, [rsp+2F8h+pv]
0x18000cf9d  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000cfa1  mov     rcx, rsi
0x18000cfa4  inc     rcx
0x18000cfa7  cmp     [rax+rcx*2], di
0x18000cfab  jnz     short loc_18000CFA4
0x18000cfad  mov     qword ptr [rsp+2F8h+var_288], rax
0x18000cfb2  mov     qword ptr [rsp+2F8h+var_288+8], rcx
0x18000cfb7  lea     rdx, [rsp+2F8h+var_288]
0x18000cfbc  lea     rcx, [rsp+2F8h+var_190]
0x18000cfc4  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::wstring_view,std::filesystem::_Normal_conversion)
0x18000cfc9  nop
0x18000cfca  mov     rcx, [rsp+2F8h+pv]; pv
0x18000cfcf  test    rcx, rcx
0x18000cfd2  jz      short loc_18000CFDB
0x18000cfd4  call    cs:__imp_CoTaskMemFree
0x18000cfda  nop
0x18000cfdb  mov     qword ptr [rsp+2F8h+var_2B0], rdi
0x18000cfe0  lea     rax, ?_Static@?1???$_Immortalize_memcpy_image@V_System_error_category@std@@@std@@YAAEBV_System_error_category@1@XZ@4U?$_Constexpr_immortalize_impl@V_System_error_category@std@@@1@A; std::_Constexpr_immortalize_impl<std::_System_error_category> `std::_Immortalize_memcpy_image<std::_System_error_category>(void)'::`2'::_Static
0x18000cfe7  mov     [rsp+2F8h+var_2A8], rax
0x18000cfec  lea     rdx, [rsp+2F8h+var_2B0]; struct std::filesystem::path *
0x18000cff1  lea     rcx, [rsp+2F8h+var_190]; this
0x18000cff9  call    ?exists@filesystem@std@@YA_NAEBVpath@12@AEAVerror_code@2@@Z; std::filesystem::exists(std::filesystem::path const &,std::error_code &)
0x18000cffe  cmp     dword ptr [rsp+2F8h+var_2B0], edi
0x18000d002  jnz     loc_18000D4E8
0x18000d008  test    al, al
0x18000d00a  jz      loc_18000D49B
0x18000d010  xorps   xmm0, xmm0
0x18000d013  movdqa  [rsp+2F8h+var_268], xmm0
0x18000d01c  lea     rdx, [rsp+2F8h+var_190]
0x18000d024  lea     rcx, [rsp+2F8h+var_268]
0x18000d02c  call    ??$_Initialize_dir_enum@U_Dir_enum_impl@filesystem@std@@@_Dir_enum_impl@filesystem@std@@SA?AW4__std_win_error@@AEAV?$shared_ptr@U_Dir_enum_impl@filesystem@std@@@2@AEBVpath@12@W4directory_options@12@@Z; std::filesystem::_Dir_enum_impl::_Initialize_dir_enum<std::filesystem::_Dir_enum_impl>(std::shared_ptr<std::filesystem::_Dir_enum_impl> &,std::filesystem::path const &,std::filesystem::directory_options)
0x18000d031  test    eax, eax
0x18000d033  jnz     loc_18000D502
0x18000d039  xorps   xmm0, xmm0
0x18000d03c  movups  [rsp+2F8h+var_288], xmm0
0x18000d041  mov     rbx, qword ptr [rsp+2F8h+var_268+8]
0x18000d049  mov     r14d, 1
0x18000d04f  test    rbx, rbx
0x18000d052  jz      short loc_18000D059
0x18000d054  lock add [rbx+8], r14d
0x18000d059  movaps  xmm0, [rsp+2F8h+var_268]
0x18000d061  movdqa  [rsp+2F8h+var_288], xmm0
0x18000d067  test    rbx, rbx
0x18000d06a  jz      short loc_18000D071
0x18000d06c  lock add [rbx+8], r14d
0x18000d071  xorps   xmm1, xmm1
0x18000d074  movdqu  [rsp+2F8h+var_258], xmm1
0x18000d07d  test    rbx, rbx
0x18000d080  jz      short loc_18000D0B6
0x18000d082  mov     eax, esi
0x18000d084  lock xadd [rbx+8], eax
0x18000d089  add     eax, esi
0x18000d08b  jnz     short loc_18000D0B6
0x18000d08d  mov     rax, [rbx]
0x18000d090  mov     rcx, rbx
0x18000d093  mov     rax, [rax]
0x18000d096  call    _guard_dispatch_icall
0x18000d09b  mov     eax, esi
0x18000d09d  lock xadd [rbx+0Ch], eax
0x18000d0a2  add     eax, esi
0x18000d0a4  jnz     short loc_18000D0B6
0x18000d0a6  mov     rax, [rbx]
0x18000d0a9  mov     rcx, rbx
0x18000d0ac  mov     rax, [rax+8]
0x18000d0b0  call    _guard_dispatch_icall
0x18000d0b5  nop
0x18000d0b6  mov     rdx, qword ptr [rsp+2F8h+var_288]
0x18000d0bb  cmp     rdx, qword ptr [rsp+2F8h+var_258]
0x18000d0c3  jz      loc_18000D41E
0x18000d0c9  movups  xmm0, xmmword ptr [rdx]
0x18000d0cc  movaps  [rsp+2F8h+var_168], xmm0
0x18000d0d4  movups  xmm1, xmmword ptr [rdx+10h]
0x18000d0d8  movaps  [rsp+2F8h+var_158], xmm1
0x18000d0e0  add     rdx, 20h ; ' '
0x18000d0e4  lea     rcx, [rsp+2F8h+var_148]
0x18000d0ec  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000d0f1  nop
0x18000d0f2  mov     rcx, cs:qword_180063B00
0x18000d0f9  mov     rax, 7FFFFFFFFFFFFFFEh
0x18000d103  sub     rax, rcx
0x18000d106  cmp     rax, r14
0x18000d109  jb      loc_18000D519
0x18000d10f  lea     rax, ?_deletionPreffix@PackageScavenge@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const PackageScavenge::_deletionPreffix
0x18000d116  cmp     cs:qword_180063B08, 7
0x18000d11e  cmova   rax, cs:?_deletionPreffix@PackageScavenge@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const PackageScavenge::_deletionPreffix
0x18000d126  mov     [rsp+2F8h+var_2C8], rcx; __int64
0x18000d12b  mov     [rsp+2F8h+Src], rax; Src
0x18000d130  mov     [rsp+2F8h+var_2D8], r14; __int64
0x18000d135  lea     rcx, [rsp+2F8h+var_1F8]; void *
0x18000d13d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEB_W_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x18000d142  nop
0x18000d143  mov     r8d, 2
0x18000d149  lea     rdx, asc_1800514C0; ".+"
0x18000d150  lea     rcx, [rsp+2F8h+var_1F8]; Src
0x18000d158  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x18000d15d  xorps   xmm0, xmm0
0x18000d160  movups  [rsp+2F8h+var_220], xmm0
0x18000d168  xorps   xmm1, xmm1
0x18000d16b  movdqu  [rsp+2F8h+var_210], xmm1
0x18000d174  movups  xmm0, xmmword ptr [rax]
0x18000d177  movups  [rsp+2F8h+var_220], xmm0
0x18000d17f  movups  xmm1, xmmword ptr [rax+10h]
0x18000d183  movups  [rsp+2F8h+var_210], xmm1
0x18000d18b  mov     [rax+10h], rdi
0x18000d18f  mov     qword ptr [rax+18h], 7
0x18000d197  mov     [rax], di
0x18000d19a  lea     rdx, [rsp+2F8h+var_220]
0x18000d1a2  lea     rcx, [rsp+2F8h+var_1B8]
0x18000d1aa  call    ??$?0U?$char_traits@_W@std@@V?$allocator@_W@1@@?$basic_regex@_WV?$regex_traits@_W@std@@@std@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@W4syntax_option_type@regex_constants@1@@Z; std::basic_regex<wchar_t,std::regex_traits<wchar_t>>::basic_regex<wchar_t,std::regex_traits<wchar_t>>(std::wstring const &,std::regex_constants::syntax_option_type)
0x18000d1af  mov     r15, rax
0x18000d1b2  mov     qword ptr [rsp+2F8h+var_2B0], rax
0x18000d1b7  lea     rdx, [rsp+2F8h+var_1D8]
0x18000d1bf  lea     rcx, [rsp+2F8h+var_148]
0x18000d1c7  call    ?filename@path@filesystem@std@@QEBA?AV123@XZ; std::filesystem::path::filename(void)
0x18000d1cc  nop
0x18000d1cd  mov     rdx, rax
0x18000d1d0  lea     rcx, [rsp+2F8h+var_240]
0x18000d1d8  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000d1dd  nop
0x18000d1de  lea     rcx, [rsp+2F8h+var_240]
0x18000d1e6  cmp     [rsp+2F8h+var_228], 7
0x18000d1ef  cmova   rcx, [rsp+2F8h+var_240]
0x18000d1f8  mov     [rsp+2F8h+pv], rcx
0x18000d1fd  mov     rax, [rsp+2F8h+var_230]
0x18000d205  lea     r12, [rcx+rax*2]
0x18000d209  cmp     qword ptr [r15], 0
0x18000d20d  jnz     short loc_18000D217
0x18000d20f  mov     r15b, dil
0x18000d212  jmp     loc_18000D348
0x18000d217  movzx   r15d, dil
0x18000d21b  xor     edx, edx; Val
0x18000d21d  mov     r8d, 0E8h; Size
0x18000d223  lea     rcx, [rsp+2F8h+var_128]; void *
0x18000d22b  call    memset
0x18000d230  mov     rax, qword ptr [rsp+2F8h+var_2B0]
0x18000d235  lea     r9, [rax+8]
0x18000d239  mov     [rsp+2F8h+var_2C0], 10h
0x18000d241  mov     rcx, [rax]
0x18000d244  mov     eax, [rcx+20h]
0x18000d247  mov     dword ptr [rsp+2F8h+var_2C8], eax
0x18000d24b  mov     eax, [rcx+28h]
0x18000d24e  mov     dword ptr [rsp+2F8h+Src], eax
0x18000d252  mov     [rsp+2F8h+var_2D8], rcx
0x18000d257  mov     r8, r12
0x18000d25a  mov     rdx, [rsp+2F8h+pv]
0x18000d25f  lea     rcx, [rsp+2F8h+var_128]
0x18000d267  call    ??0?$_Matcher@PEB_W_WV?$regex_traits@_W@std@@PEB_W@std@@QEAA@PEB_W0AEBV?$regex_traits@_W@1@PEAV_Root_node@1@IW4syntax_option_type@regex_constants@1@W4match_flag_type@51@@Z; std::_Matcher<wchar_t const *,wchar_t,std::regex_traits<wchar_t>,wchar_t const *>::_Matcher<wchar_t const *,wchar_t,std::regex_traits<wchar_t>,wchar_t const *>(wchar_t const *,wchar_t const *,std::regex_traits<wchar_t> const &,std::_Root_node *,uint,std::regex_constants::syntax_option_type,std::regex_constants::match_flag_type)
0x18000d26c  nop
0x18000d26d  lea     rcx, [rsp+2F8h+var_128]
0x18000d275  call    ??$_Match@V?$allocator@V?$sub_match@PEB_W@std@@@std@@@?$_Matcher@PEB_W_WV?$regex_traits@_W@std@@PEB_W@std@@QEAA_NPEAV?$match_results@PEB_WV?$allocator@V?$sub_match@PEB_W@std@@@std@@@1@_N@Z; std::_Matcher<wchar_t const *,wchar_t,std::regex_traits<wchar_t>,wchar_t const *>::_Match<std::allocator<std::sub_match<wchar_t const *>>>(std::match_results<wchar_t const *> *,bool)
0x18000d27a  test    al, al
0x18000d27c  jnz     loc_18000D3BE
0x18000d282  mov     rcx, [rsp+2F8h+pv]
0x18000d287  cmp     rcx, r12
0x18000d28a  jz      short loc_18000D306
0x18000d28c  mov     eax, [rsp+2F8h+var_6C]
0x18000d293  btr     eax, 0Dh
0x18000d297  bts     eax, 8
0x18000d29b  mov     [rsp+2F8h+var_6C], eax
0x18000d2a2  lea     rdx, [rcx+2]
0x18000d2a6  jmp     short loc_18000D2CE
0x18000d2a8  mov     [rsp+2F8h+var_80], rax
0x18000d2b0  lea     rcx, [rsp+2F8h+var_128]
0x18000d2b8  call    ??$_Match@V?$allocator@V?$sub_match@PEB_W@std@@@std@@@?$_Matcher@PEB_W_WV?$regex_traits@_W@std@@PEB_W@std@@QEAA_NPEAV?$match_results@PEB_WV?$allocator@V?$sub_match@PEB_W@std@@@std@@@1@_N@Z; std::_Matcher<wchar_t const *,wchar_t,std::regex_traits<wchar_t>,wchar_t const *>::_Match<std::allocator<std::sub_match<wchar_t const *>>>(std::match_results<wchar_t const *> *,bool)
0x18000d2bd  test    al, al
0x18000d2bf  jnz     loc_18000D3BE
0x18000d2c5  mov     rdx, [rsp+2F8h+pv]
0x18000d2ca  add     rdx, 2
0x18000d2ce  xor     r9d, r9d
0x18000d2d1  mov     r8, r12
0x18000d2d4  lea     rcx, [rsp+2F8h+var_128]
0x18000d2dc  call    ?_Skip@?$_Matcher@PEB_W_WV?$regex_traits@_W@std@@PEB_W@std@@QEAAPEB_WPEB_W0PEAV_Node_base@2@@Z; std::_Matcher<wchar_t const *,wchar_t,std::regex_traits<wchar_t>,wchar_t const *>::_Skip(wchar_t const *,wchar_t const *,std::_Node_base *)
0x18000d2e1  cmp     rax, r12
0x18000d2e4  mov     [rsp+2F8h+pv], rax
0x18000d2e9  jnz     short loc_18000D2A8
0x18000d2eb  mov     [rsp+2F8h+var_80], r12
0x18000d2f3  lea     rcx, [rsp+2F8h+var_128]
0x18000d2fb  call    ??$_Match@V?$allocator@V?$sub_match@PEB_W@std@@@std@@@?$_Matcher@PEB_W_WV?$regex_traits@_W@std@@PEB_W@std@@QEAA_NPEAV?$match_results@PEB_WV?$allocator@V?$sub_match@PEB_W@std@@@std@@@1@_N@Z; std::_Matcher<wchar_t const *,wchar_t,std::regex_traits<wchar_t>,wchar_t const *>::_Match<std::allocator<std::sub_match<wchar_t const *>>>(std::match_results<wchar_t const *> *,bool)
0x18000d300  test    al, al
0x18000d302  cmovnz  r15d, r14d
0x18000d306  lea     rcx, [rsp+2F8h+var_A8]
0x18000d30e  call    ??1?$vector@U_Loop_vals_t@std@@V?$allocator@U_Loop_vals_t@std@@@2@@std@@QEAA@XZ; std::vector<std::_Loop_vals_t>::~vector<std::_Loop_vals_t>(void)
0x18000d313  lea     rcx, [rsp+2F8h+var_C0]
0x18000d31b  call    ??1?$vector@U_Loop_vals_t@std@@V?$allocator@U_Loop_vals_t@std@@@2@@std@@QEAA@XZ; std::vector<std::_Loop_vals_t>::~vector<std::_Loop_vals_t>(void)
0x18000d320  lea     rcx, [rsp+2F8h+var_E0]
0x18000d328  call    ??1?$vector@W4UusCapability@@V?$allocator@W4UusCapability@@@std@@@std@@QEAA@XZ; std::vector<UusCapability>::~vector<UusCapability>(void)
0x18000d32d  lea     rcx, [rsp+2F8h+var_100]
0x18000d335  call    ??1?$vector@U_Loop_vals_t@std@@V?$allocator@U_Loop_vals_t@std@@@2@@std@@QEAA@XZ; std::vector<std::_Loop_vals_t>::~vector<std::_Loop_vals_t>(void)
0x18000d33a  lea     rcx, [rsp+2F8h+var_120]
0x18000d342  call    ??1?$vector@W4UusCapability@@V?$allocator@W4UusCapability@@@std@@@std@@QEAA@XZ; std::vector<UusCapability>::~vector<UusCapability>(void)
0x18000d347  nop
0x18000d348  lea     rcx, [rsp+2F8h+var_240]
0x18000d350  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000d355  nop
0x18000d356  lea     rcx, [rsp+2F8h+var_1D8]
0x18000d35e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000d363  nop
0x18000d364  lea     rcx, [rsp+2F8h+var_1B8]
0x18000d36c  call    ??1?$basic_regex@_WV?$regex_traits@_W@std@@@std@@QEAA@XZ; std::basic_regex<wchar_t,std::regex_traits<wchar_t>>::~basic_regex<wchar_t,std::regex_traits<wchar_t>>(void)
0x18000d371  nop
0x18000d372  lea     rcx, [rsp+2F8h+var_220]
0x18000d37a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000d37f  nop
0x18000d380  lea     rcx, [rsp+2F8h+var_1F8]
0x18000d388  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000d38d  test    r15b, r15b
0x18000d390  mov     r15, [rsp+2F8h+var_2A0]
0x18000d395  jz      short loc_18000D3FA
0x18000d397  add     r15, r14
0x18000d39a  mov     [rsp+2F8h+var_2A0], r15
0x18000d39f  mov     qword ptr [rsp+2F8h+var_2B0], r15
0x18000d3a4  lea     rcx, [rsp+2F8h+var_148]; this
0x18000d3ac  call    ?remove_all@filesystem@std@@YA_KAEBVpath@12@@Z; std::filesystem::remove_all(std::filesystem::path const &)
0x18000d3b1  add     r13, r14
0x18000d3b4  mov     [rsp+2F8h+var_278], r13
0x18000d3bc  jmp     short loc_18000D3FA
0x18000d3be  mov     r15b, r14b
0x18000d3c1  jmp     loc_18000D306
0x18000d3c6  xor     edi, edi
0x18000d3c8  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000d3cc  lea     r14d, [rdi+1]
0x18000d3d0  mov     r15, qword ptr [rsp+2F8h+var_2B0]
0x18000d3d5  mov     [rsp+2F8h+var_2A0], r15
0x18000d3da  mov     r13, [rsp+2F8h+var_278]
0x18000d3e2  mov     rbx, qword ptr [rsp+2F8h+var_268+8]
0x18000d3ea  mov     rax, [rsp+2F8h+var_248]
0x18000d3f2  mov     [rsp+2F8h+var_270], rax
0x18000d3fa  lea     rcx, [rsp+2F8h+var_148]
0x18000d402  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000d407  lea     rcx, [rsp+2F8h+var_288]
0x18000d40c  call    ?_Advance_and_reset_if_no_more_files@_Dir_enum_impl@filesystem@std@@SA?AW4__std_win_error@@AEAV?$shared_ptr@U_Dir_enum_impl@filesystem@std@@@3@@Z; std::filesystem::_Dir_enum_impl::_Advance_and_reset_if_no_more_files(std::shared_ptr<std::filesystem::_Dir_enum_impl> &)
0x18000d411  test    eax, eax
0x18000d413  jnz     loc_18000D51F
0x18000d419  jmp     loc_18000D0B6
0x18000d41e  mov     r14, qword ptr [rsp+2F8h+var_288+8]
0x18000d423  test    r14, r14
0x18000d426  jz      short loc_18000D45E
0x18000d428  mov     eax, esi
0x18000d42a  lock xadd [r14+8], eax
0x18000d430  add     eax, esi
0x18000d432  jnz     short loc_18000D45E
0x18000d434  mov     rax, [r14]
0x18000d437  mov     rcx, r14
0x18000d43a  mov     rax, [rax]
0x18000d43d  call    _guard_dispatch_icall
0x18000d442  mov     eax, esi
0x18000d444  lock xadd [r14+0Ch], eax
0x18000d44a  add     eax, esi
0x18000d44c  jnz     short loc_18000D45E
0x18000d44e  mov     rax, [r14]
0x18000d451  mov     rcx, r14
0x18000d454  mov     rax, [rax+8]
0x18000d458  call    _guard_dispatch_icall
0x18000d45d  nop
0x18000d45e  test    rbx, rbx
0x18000d461  jz      short loc_18000D496
0x18000d463  mov     eax, esi
0x18000d465  lock xadd [rbx+8], eax
0x18000d46a  add     eax, esi
0x18000d46c  jnz     short loc_18000D496
0x18000d46e  mov     rax, [rbx]
0x18000d471  mov     rcx, rbx
0x18000d474  mov     rax, [rax]
0x18000d477  call    _guard_dispatch_icall
0x18000d47c  mov     eax, esi
0x18000d47e  lock xadd [rbx+0Ch], eax
0x18000d483  add     eax, esi
0x18000d485  jnz     short loc_18000D496
0x18000d487  mov     rdx, [rbx]
0x18000d48a  mov     rcx, rbx
0x18000d48d  mov     rax, [rdx+8]
0x18000d491  call    _guard_dispatch_icall
  ... truncated ...
```
