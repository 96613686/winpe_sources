# UusExclusion::UusExclusion(std::filesystem::path const &)

- ea: `0x180032760`
- end: `0x1800329e4`
- name: `??0UusExclusion@@QEAA@AEBVpath@filesystem@std@@@Z`
- size: `644`
- prototype: `UusExclusion *__fastcall(UusExclusion *this, const struct std::filesystem::path *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180036a04`
- `0x180039904`

## callees

- `0x18000d660`
- `0x180028728`
- `0x180029158`
- `0x1800295e8`
- `0x180029644`
- `0x1800296cc`
- `0x180032760`
- `0x180032fc8`
- `0x180047a30`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032897`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032897`

## pseudocode

```c
UusExclusion *__fastcall UusExclusion::UusExclusion(UusExclusion *this, const struct std::filesystem::path *a2)
{
  __int64 *v4; // rsi
  __int64 *v5; // rdi
  __int64 *v6; // rax
  __int64 *v7; // rax
  __int64 *v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 *v11; // rax
  __int64 v12; // rcx
  LPVOID pv[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 *v15; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v16; // [rsp+38h] [rbp-C8h]
  _QWORD v17[2]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v18[4]; // [rsp+50h] [rbp-B0h] BYREF
  char v19; // [rsp+70h] [rbp-90h]
  _BYTE v20[32]; // [rsp+78h] [rbp-88h] BYREF
  UusExclusion *v21; // [rsp+98h] [rbp-68h]
  _QWORD v22[4]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v23[4]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v24[48]; // [rsp+E0h] [rbp-20h] BYREF

  v21 = this;
  *(_QWORD *)this = &UusExclusion::`vftable';
  v4 = (__int64 *)((char *)this + 8);
  web::json::value::value((UusExclusion *)((char *)this + 8));
  v5 = (__int64 *)((char *)this + 16);
  web::json::value::value((UusExclusion *)((char *)this + 16));
  v6 = &UusExclusion::_filenameJsonLocal;
  if ( (unsigned __int64)qword_1800636C8 > 7 )
    v6 = (__int64 *)UusExclusion::_filenameJsonLocal;
  v15 = v6;
  v16 = qword_1800636C0;
  std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v18, (__int64)&v15);
  std::filesystem::operator/((char *)this + 24, a2, v18);
  std::wstring::_Tidy_deallocate(v18);
  v7 = &UusExclusion::_filenameJsonCloud;
  if ( (unsigned __int64)qword_1800636E8 > 7 )
    v7 = (__int64 *)UusExclusion::_filenameJsonCloud;
  v15 = v7;
  v16 = qword_1800636E0;
  std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v23, (__int64)&v15);
  pv[0] = 0;
  v8 = &UusExclusion::_subdirOneSettingsRoot;
  if ( (unsigned __int64)qword_180063708 > 7 )
    v8 = (__int64 *)UusExclusion::_subdirOneSettingsRoot;
  wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(
    (char *)pv,
    (__int64)v8);
  v9 = -1;
  do
    ++v9;
  while ( *((_WORD *)pv[0] + v9) );
  v15 = (__int64 *)pv[0];
  v16 = v9;
  std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v22, (__int64)&v15);
  if ( pv[0] )
    CoTaskMemFree(pv[0]);
  std::filesystem::operator/((char *)this + 56, v22, v23);
  std::wstring::_Tidy_deallocate(v22);
  std::wstring::_Tidy_deallocate(v23);
  std::wstring::wstring((__int64)v18, (__int64)this + 24);
  v17[1] = v18;
  pv[0] = v24;
  v24[32] = 0;
  std::wstring::wstring((__int64)v20, (__int64)v18);
  UusExclusion::Load((web::json::value *)v17, (struct std::error_code *)v20);
  std::wstring::_Tidy_deallocate(v18);
  if ( v4 == v17 )
  {
    v10 = v17[0];
  }
  else
  {
    v10 = *v4;
    *v4 = v17[0];
    v17[0] = v10;
  }
  if ( v10 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v10 + 192LL))(v10, 1);
  v15 = v18;
  std::wstring::wstring((__int64)v18, (__int64)UusExclusion::_oneSettingsFormatKeySettings);
  v19 = 1;
  std::wstring::wstring((__int64)v20, (__int64)this + 56);
  v11 = (__int64 *)UusExclusion::Load((web::json::value *)pv, (struct std::error_code *)v20);
  if ( v5 != v11 )
  {
    v12 = *v5;
    *v5 = *v11;
    *v11 = v12;
  }
  if ( pv[0] )
    (*(void (__fastcall **)(LPVOID, __int64))(*(_QWORD *)pv[0] + 192LL))(pv[0], 1);
  return this;
}

```

## disassembly

```asm
0x180032760  mov     [rsp-8+arg_10], rbx
0x180032765  mov     [rsp-8+arg_18], rsi
0x18003276a  push    rbp
0x18003276b  push    rdi
0x18003276c  push    r12
0x18003276e  push    r14
0x180032770  push    r15
0x180032772  lea     rbp, [rsp-10h]
0x180032777  sub     rsp, 110h
0x18003277e  mov     rbx, rdx
0x180032781  mov     r14, rcx
0x180032784  mov     [rbp+30h+var_98], rcx
0x180032788  xor     r12d, r12d
0x18003278b  lea     rax, ??_7UusExclusion@@6B@; const UusExclusion::`vftable'
0x180032792  mov     [rcx], rax
0x180032795  lea     rsi, [rcx+8]
0x180032799  mov     rcx, rsi; this
0x18003279c  call    ??0value@json@web@@QEAA@XZ; web::json::value::value(void)
0x1800327a1  nop
0x1800327a2  lea     rdi, [r14+10h]
0x1800327a6  mov     rcx, rdi; this
0x1800327a9  call    ??0value@json@web@@QEAA@XZ; web::json::value::value(void)
0x1800327ae  nop
0x1800327af  mov     rcx, cs:qword_1800636C0
0x1800327b6  lea     rax, ?_filenameJsonLocal@UusExclusion@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const UusExclusion::_filenameJsonLocal
0x1800327bd  cmp     cs:qword_1800636C8, 7
0x1800327c5  cmova   rax, cs:?_filenameJsonLocal@UusExclusion@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const UusExclusion::_filenameJsonLocal
0x1800327cd  mov     [rsp+130h+var_100], rax
0x1800327d2  mov     [rsp+130h+var_F8], rcx
0x1800327d7  lea     rdx, [rsp+130h+var_100]
0x1800327dc  lea     rcx, [rsp+130h+var_E0]
0x1800327e1  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::wstring_view,std::filesystem::_Normal_conversion)
0x1800327e6  nop
0x1800327e7  lea     r8, [rsp+130h+var_E0]; void *
0x1800327ec  mov     rdx, rbx; void *
0x1800327ef  lea     rcx, [r14+18h]; Src
0x1800327f3  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x1800327f8  nop
0x1800327f9  lea     rcx, [rsp+130h+var_E0]
0x1800327fe  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180032803  mov     rcx, cs:qword_1800636E0
0x18003280a  lea     rax, ?_filenameJsonCloud@UusExclusion@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const UusExclusion::_filenameJsonCloud
0x180032811  cmp     cs:qword_1800636E8, 7
0x180032819  cmova   rax, cs:?_filenameJsonCloud@UusExclusion@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const UusExclusion::_filenameJsonCloud
0x180032821  mov     [rsp+130h+var_100], rax
0x180032826  mov     [rsp+130h+var_F8], rcx
0x18003282b  lea     rdx, [rsp+130h+var_100]
0x180032830  lea     rcx, [rbp+30h+var_70]
0x180032834  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::wstring_view,std::filesystem::_Normal_conversion)
0x180032839  nop
0x18003283a  mov     [rsp+130h+pv], r12
0x18003283f  lea     rdx, ?_subdirOneSettingsRoot@UusExclusion@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const UusExclusion::_subdirOneSettingsRoot
0x180032846  cmp     cs:qword_180063708, 7
0x18003284e  cmova   rdx, cs:?_subdirOneSettingsRoot@UusExclusion@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const UusExclusion::_subdirOneSettingsRoot
0x180032856  lea     rcx, [rsp+130h+pv]
0x18003285b  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(wchar_t const *)
0x180032860  nop
0x180032861  mov     rax, [rsp+130h+pv]
0x180032866  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18003286a  inc     rcx
0x18003286d  cmp     [rax+rcx*2], r12w
0x180032872  jnz     short loc_18003286A
0x180032874  mov     [rsp+130h+var_100], rax
0x180032879  mov     [rsp+130h+var_F8], rcx
0x18003287e  lea     rdx, [rsp+130h+var_100]
0x180032883  lea     rcx, [rbp+30h+var_90]
0x180032887  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::wstring_view,std::filesystem::_Normal_conversion)
0x18003288c  nop
0x18003288d  mov     rcx, [rsp+130h+pv]; pv
0x180032892  test    rcx, rcx
0x180032895  jz      short loc_18003289E
0x180032897  call    cs:__imp_CoTaskMemFree
0x18003289d  nop
0x18003289e  lea     r8, [rbp+30h+var_70]; void *
0x1800328a2  lea     rdx, [rbp+30h+var_90]; void *
0x1800328a6  lea     rcx, [r14+38h]; Src
0x1800328aa  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x1800328af  nop
0x1800328b0  lea     rcx, [rbp+30h+var_90]
0x1800328b4  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800328b9  nop
0x1800328ba  lea     rcx, [rbp+30h+var_70]
0x1800328be  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800328c3  lea     rdx, [r14+18h]
0x1800328c7  lea     rcx, [rsp+130h+var_E0]
0x1800328cc  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800328d1  lea     rax, [rsp+130h+var_E0]
0x1800328d6  mov     [rsp+130h+var_E8], rax
0x1800328db  lea     rax, [rbp+30h+var_50]
0x1800328df  mov     [rsp+130h+pv], rax
0x1800328e4  mov     [rbp+30h+var_30], r12b
0x1800328e8  lea     rdx, [rsp+130h+var_E0]
0x1800328ed  lea     rcx, [rsp+130h+var_B8]
0x1800328f2  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800328f7  nop
0x1800328f8  lea     r8, [rbp+30h+var_50]
0x1800328fc  lea     rdx, [rsp+130h+var_B8]; struct std::error_code *
0x180032901  lea     rcx, [rsp+130h+var_F0]; this
0x180032906  call    ?Load@UusExclusion@@CA?AVvalue@json@web@@Vpath@filesystem@std@@V?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@7@@Z; UusExclusion::Load(std::filesystem::path,std::optional<std::wstring>)
0x18003290b  nop
0x18003290c  lea     rcx, [rsp+130h+var_E0]
0x180032911  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180032916  lea     rax, [rsp+130h+var_F0]
0x18003291b  cmp     rsi, rax
0x18003291e  jz      short loc_180032932
0x180032920  mov     rcx, [rsi]
0x180032923  mov     rax, [rsp+130h+var_F0]
0x180032928  mov     [rsi], rax
0x18003292b  mov     [rsp+130h+var_F0], rcx
0x180032930  jmp     short loc_180032937
0x180032932  mov     rcx, [rsp+130h+var_F0]
0x180032937  mov     esi, 1
0x18003293c  test    rcx, rcx
0x18003293f  jz      short loc_180032952
0x180032941  mov     rax, [rcx]
0x180032944  mov     edx, esi
0x180032946  mov     rax, [rax+0C0h]
0x18003294d  call    _guard_dispatch_icall
0x180032952  lea     rax, [rsp+130h+var_E0]
0x180032957  mov     [rsp+130h+var_100], rax
0x18003295c  lea     rdx, ?_oneSettingsFormatKeySettings@UusExclusion@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const UusExclusion::_oneSettingsFormatKeySettings
0x180032963  lea     rcx, [rsp+130h+var_E0]
0x180032968  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003296d  mov     [rsp+130h+var_C0], sil
0x180032972  lea     rdx, [r14+38h]
0x180032976  lea     rcx, [rsp+130h+var_B8]
0x18003297b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180032980  nop
0x180032981  lea     r8, [rsp+130h+var_E0]
0x180032986  lea     rdx, [rsp+130h+var_B8]; struct std::error_code *
0x18003298b  lea     rcx, [rsp+130h+pv]; this
0x180032990  call    ?Load@UusExclusion@@CA?AVvalue@json@web@@Vpath@filesystem@std@@V?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@7@@Z; UusExclusion::Load(std::filesystem::path,std::optional<std::wstring>)
0x180032995  mov     r8, rax
0x180032998  cmp     rdi, rax
0x18003299b  jz      short loc_1800329A9
0x18003299d  mov     rcx, [rdi]
0x1800329a0  mov     rax, [rax]
0x1800329a3  mov     [rdi], rax
0x1800329a6  mov     [r8], rcx
0x1800329a9  mov     rcx, [rsp+130h+pv]
0x1800329ae  test    rcx, rcx
0x1800329b1  jz      short loc_1800329C5
0x1800329b3  mov     r8, [rcx]
0x1800329b6  mov     edx, esi
0x1800329b8  mov     rax, [r8+0C0h]
0x1800329bf  call    _guard_dispatch_icall
0x1800329c4  nop
0x1800329c5  mov     rax, r14
0x1800329c8  lea     r11, [rsp+130h+var_20]
0x1800329d0  mov     rbx, [r11+40h]
0x1800329d4  mov     rsi, [r11+48h]
0x1800329d8  mov     rsp, r11
0x1800329db  pop     r15
0x1800329dd  pop     r14
0x1800329df  pop     r12
0x1800329e1  pop     rdi
0x1800329e2  pop     rbp
0x1800329e3  retn
```
