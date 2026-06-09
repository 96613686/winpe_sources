# UusPackage::FindBestPackage(std::function<bool (UusPackage const &)>,std::function<void (std::filesystem::path const &,char const *)>)

- ea: `0x18000b024`
- end: `0x18000b62f`
- name: `?FindBestPackage@UusPackage@@CA?AV?$optional@VUusPackage@@@std@@V?$function@$$A6A_NAEBVUusPackage@@@Z@3@V?$function@$$A6AXAEBVpath@filesystem@std@@PEBD@Z@3@@Z`
- size: `1547`
- prototype: `UusPackage *__fastcall(UusPackage *, __int64, __int64)`
- caller_count: `2`
- callee_count: `27`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000a748`
- `0x18003a2cc`

## callees

- `0x180008af0`
- `0x18000ab24`
- `0x18000ae24`
- `0x18000b024`
- `0x18000d660`
- `0x18000dca4`
- `0x180011d2c`
- `0x180011e0c`
- `0x180013d18`
- `0x1800185f8`
- `0x1800240ac`
- `0x180025d10`
- `0x180025de8`
- `0x180025f88`
- `0x1800264ac`
- `0x180026648`
- `0x180027228`
- `0x180028514`
- `0x1800286d0`
- `0x180028728`
- `0x1800295e8`
- `0x180029644`
- `0x18003fd5c`
- `0x1800427d0`
- `0x180042bfc`
- `0x180047a30`
- `0x180047ab0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b0f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b0f3`

## string_xrefs

- `0x18000b2fb`: `Path folder version doesn't match package version `
- `0x18000b60e`: `directory_entry::status`
- `0x18000b5f9`: `directory_iterator::directory_iterator`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
UusPackage *__fastcall UusPackage::FindBestPackage(UusPackage *a1, __int64 a2, __int64 a3)
{
  UusPackage *v5; // rbx
  const struct UusPackage *v6; // rdi
  __int64 *v7; // rdx
  __int64 v8; // rcx
  struct std::error_code *v9; // r8
  bool v10; // al
  const struct std::filesystem::path *v11; // r9
  unsigned int v12; // eax
  volatile signed __int32 *v13; // r14
  UusPackage *v14; // rax
  const struct UusPackage *v15; // rbx
  __int64 v16; // rcx
  const struct UusPackage *v17; // rax
  _QWORD *StringA; // rax
  __int64 v19; // r8
  _QWORD *v20; // rax
  __int64 v21; // rcx
  unsigned int v22; // eax
  __int64 v23; // rcx
  volatile signed __int32 *v24; // rbx
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // rcx
  void (__fastcall *v28)(__int64, __int64); // rax
  __int64 v29; // rcx
  UusPackage *v31; // [rsp+20h] [rbp-278h]
  char v32[8]; // [rsp+28h] [rbp-270h] BYREF
  void ***v33; // [rsp+30h] [rbp-268h]
  __int128 v34; // [rsp+40h] [rbp-258h] BYREF
  __int128 v35; // [rsp+50h] [rbp-248h] BYREF
  const struct UusPackage *v36; // [rsp+60h] [rbp-238h]
  __int128 v37; // [rsp+70h] [rbp-228h] BYREF
  UusPackage *v38; // [rsp+90h] [rbp-208h]
  _QWORD v39[5]; // [rsp+A0h] [rbp-1F8h] BYREF
  LPVOID pv; // [rsp+C8h] [rbp-1D0h] BYREF
  UusPackage *v41; // [rsp+D0h] [rbp-1C8h]
  __int64 v42; // [rsp+D8h] [rbp-1C0h]
  __int64 v43; // [rsp+E0h] [rbp-1B8h]
  _BYTE v44[40]; // [rsp+E8h] [rbp-1B0h] BYREF
  _OWORD v45[2]; // [rsp+110h] [rbp-188h] BYREF
  _BYTE v46[32]; // [rsp+130h] [rbp-168h] BYREF
  _QWORD v47[32]; // [rsp+150h] [rbp-148h] BYREF

  v5 = a1;
  v41 = a1;
  v38 = a1;
  v43 = a2;
  v42 = a3;
  v6 = 0;
  v36 = 0;
  pv = 0;
  v7 = &UusPackage::_subdirSxSRoot;
  if ( (unsigned __int64)qword_1800638C8 > 7 )
    v7 = (__int64 *)UusPackage::_subdirSxSRoot;
  wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(
    &pv,
    v7);
  *(_QWORD *)&v34 = pv;
  v8 = -1;
  do
    ++v8;
  while ( *((_WORD *)pv + v8) );
  *((_QWORD *)&v34 + 1) = v8;
  v35 = v34;
  std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v44, &v35);
  if ( pv )
    CoTaskMemFree(pv);
  *(_QWORD *)v32 = 0;
  v33 = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
  v10 = std::filesystem::exists((std::filesystem *)v44, (const struct std::filesystem::path *)v32, v9);
  if ( *(_DWORD *)v32 )
    std::filesystem::_Throw_fs_error((std::filesystem *)"exists", v32, (const struct std::error_code *)v44, v11);
  if ( !v10 )
    goto LABEL_55;
  v37 = 0;
  v12 = std::filesystem::_Dir_enum_impl::_Initialize_dir_enum<std::filesystem::_Dir_enum_impl>(&v37, v44);
  if ( v12 )
    std::filesystem::_Throw_fs_error("directory_iterator::directory_iterator", v12, v44);
  v34 = 0;
  v13 = (volatile signed __int32 *)*((_QWORD *)&v37 + 1);
  if ( *((_QWORD *)&v37 + 1) )
    _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v37 + 1) + 8LL));
  v34 = v37;
  if ( v13 )
    _InterlockedIncrement(v13 + 2);
  v35 = 0;
  if ( v13 )
  {
    if ( _InterlockedExchangeAdd(v13 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
      if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
    }
  }
  while ( (_QWORD)v34 != (_QWORD)v35 )
  {
    v45[0] = *(_OWORD *)v34;
    v45[1] = *(_OWORD *)(v34 + 16);
    std::wstring::wstring(v46, v34 + 32);
    std::filesystem::directory_entry::_Get_any_status(v45, v32, 3);
    if ( (_DWORD)v33 && ((*(_DWORD *)v32 - 1) & 0xFFFFFFF7) != 0 )
      std::filesystem::_Throw_fs_error("directory_entry::status", (unsigned int)v33, v46);
    if ( *(_DWORD *)v32 != 3 )
      goto LABEL_22;
    v31 = (UusPackage *)operator new(0x58u);
    v14 = UusPackage::UusPackage(v31, (const struct std::filesystem::path *)v46);
    v15 = v14;
    if ( *((_BYTE *)v14 + 80) && *((_QWORD *)v14 + 9) == *((_QWORD *)v14 + 7) )
    {
      v16 = *(_QWORD *)(a2 + 56);
      if ( !v16 )
        std::_Xbad_function_call();
      if ( (*(unsigned __int8 (__fastcall **)(__int64, UusPackage *))(*(_QWORD *)v16 + 16LL))(v16, v14) )
      {
        v17 = v6;
        v6 = v15;
        v36 = v15;
        v15 = v17;
      }
      if ( v15 )
        (**(void (__fastcall ***)(const struct UusPackage *, __int64))v15)(v15, 1);
LABEL_22:
      std::wstring::_Tidy_deallocate(v46);
      goto LABEL_40;
    }
    if ( *((_BYTE *)v14 + 80) )
    {
      memset(v47, 0, 0xF8u);
      std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v47);
      pv = (LPVOID)std::operator<<<std::char_traits<char>>(
                     &v47[2],
                     "Path folder version doesn't match package version ");
      StringA = (_QWORD *)UusVersion::GetStringA((char *)v15 + 48, v39);
      v19 = StringA[2];
      if ( StringA[3] > 0xFu )
        StringA = (_QWORD *)*StringA;
      std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(pv, StringA, v19);
      std::string::~string(v39);
      if ( *(_QWORD *)(a3 + 56) )
      {
        std::stringbuf::str(&v47[3], v39);
        v20 = v39;
        if ( v39[3] > 0xFu )
          v20 = (_QWORD *)v39[0];
        pv = v20;
        v21 = *(_QWORD *)(a3 + 56);
        if ( !v21 )
          std::_Xbad_function_call();
        (*(void (__fastcall **)(__int64, _BYTE *, LPVOID *))(*(_QWORD *)v21 + 16LL))(v21, v46, &pv);
        std::string::~string(v39);
      }
      std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(&v47[19]);
      v47[19] = &std::wios::`vftable';
      std::ios_base::~ios_base((std::ios_base *)&v47[19]);
    }
    (**(void (__fastcall ***)(const struct UusPackage *, __int64))v15)(v15, 1);
    std::wstring::_Tidy_deallocate(v46);
LABEL_40:
    v22 = std::filesystem::_Dir_enum_impl::_Advance_and_reset_if_no_more_files(&v34);
    if ( v22 )
      std::filesystem::_Throw_fs_error(v23, v22);
  }
  v24 = (volatile signed __int32 *)*((_QWORD *)&v34 + 1);
  if ( *((_QWORD *)&v34 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v34 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v24)(v24);
      if ( _InterlockedExchangeAdd(v24 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v24 + 8LL))(v24);
    }
  }
  if ( v13 )
  {
    if ( _InterlockedExchangeAdd(v13 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
      if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
    }
  }
  v5 = v41;
  if ( v6 )
  {
    UusPackage::UusPackage(v41, v6);
    *((_BYTE *)v5 + 88) = 1;
    std::wstring::_Tidy_deallocate(v44);
    (**(void (__fastcall ***)(const struct UusPackage *, __int64))v6)(v6, 1);
    v26 = *(_QWORD *)(a2 + 56);
    if ( v26 )
    {
      LOBYTE(v25) = v26 != a2;
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v26 + 32LL))(v26, v25);
      *(_QWORD *)(a2 + 56) = 0;
    }
    v27 = *(_QWORD *)(a3 + 56);
    if ( v27 )
    {
      v28 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v27 + 32LL);
      goto LABEL_59;
    }
    return v5;
  }
LABEL_55:
  *((_BYTE *)v5 + 88) = 0;
  std::wstring::_Tidy_deallocate(v44);
  v29 = *(_QWORD *)(a2 + 56);
  if ( v29 )
  {
    LOBYTE(v25) = v29 != a2;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v29 + 32LL))(v29, v25);
    *(_QWORD *)(a2 + 56) = 0;
  }
  v27 = *(_QWORD *)(a3 + 56);
  if ( v27 )
  {
    v28 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v27 + 32LL);
LABEL_59:
    LOBYTE(v25) = v27 != a3;
    v28(v27, v25);
    *(_QWORD *)(a3 + 56) = 0;
  }
  return v5;
}

```

## disassembly

```asm
0x18000b024  mov     r11, rsp
0x18000b027  push    rbx
0x18000b028  push    rsi
0x18000b029  push    rdi
0x18000b02a  push    r12
0x18000b02c  push    r13
0x18000b02e  push    r14
0x18000b030  push    r15
0x18000b032  sub     rsp, 260h
0x18000b039  mov     rax, cs:__security_cookie
0x18000b040  xor     rax, rsp
0x18000b043  mov     [rsp+298h+var_48], rax
0x18000b04b  mov     r13, r8
0x18000b04e  mov     r12, rdx
0x18000b051  mov     rbx, rcx
0x18000b054  mov     [rsp+298h+var_1C8], rcx
0x18000b05c  mov     [rsp+298h+var_208], rcx
0x18000b064  mov     [r11-1B8h], rdx
0x18000b06b  mov     [r11-1C0h], r8
0x18000b072  xor     esi, esi
0x18000b074  mov     edi, esi
0x18000b076  mov     [rsp+298h+var_238], rsi
0x18000b07b  mov     [r11-1D0h], rsi
0x18000b082  lea     rdx, ?_subdirSxSRoot@UusPackage@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const UusPackage::_subdirSxSRoot
0x18000b089  cmp     cs:qword_1800638C8, 7
0x18000b091  cmova   rdx, cs:?_subdirSxSRoot@UusPackage@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const UusPackage::_subdirSxSRoot
0x18000b099  lea     rcx, [r11-1D0h]
0x18000b0a0  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(wchar_t const *)
0x18000b0a5  nop
0x18000b0a6  mov     rax, [rsp+298h+pv]
0x18000b0ae  mov     qword ptr [rsp+298h+var_258], rax
0x18000b0b3  or      r15, 0FFFFFFFFFFFFFFFFh
0x18000b0b7  mov     rcx, r15
0x18000b0ba  inc     rcx
0x18000b0bd  cmp     [rax+rcx*2], si
0x18000b0c1  jnz     short loc_18000B0BA
0x18000b0c3  mov     qword ptr [rsp+298h+var_258+8], rcx
0x18000b0c8  movaps  xmm0, [rsp+298h+var_258]
0x18000b0cd  movdqa  [rsp+298h+var_248], xmm0
0x18000b0d3  lea     rdx, [rsp+298h+var_248]
0x18000b0d8  lea     rcx, [rsp+298h+var_1B0]
0x18000b0e0  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::wstring_view,std::filesystem::_Normal_conversion)
0x18000b0e5  nop
0x18000b0e6  mov     rcx, [rsp+298h+pv]; pv
0x18000b0ee  test    rcx, rcx
0x18000b0f1  jz      short loc_18000B0FA
0x18000b0f3  call    cs:__imp_CoTaskMemFree
0x18000b0f9  nop
0x18000b0fa  mov     qword ptr [rsp+298h+var_270], rsi
0x18000b0ff  lea     rax, ?_Static@?1???$_Immortalize_memcpy_image@V_System_error_category@std@@@std@@YAAEBV_System_error_category@1@XZ@4U?$_Constexpr_immortalize_impl@V_System_error_category@std@@@1@A; std::_Constexpr_immortalize_impl<std::_System_error_category> `std::_Immortalize_memcpy_image<std::_System_error_category>(void)'::`2'::_Static
0x18000b106  mov     [rsp+298h+var_268], rax
0x18000b10b  lea     rdx, [rsp+298h+var_270]; struct std::filesystem::path *
0x18000b110  lea     rcx, [rsp+298h+var_1B0]; this
0x18000b118  call    ?exists@filesystem@std@@YA_NAEBVpath@12@AEAVerror_code@2@@Z; std::filesystem::exists(std::filesystem::path const &,std::error_code &)
0x18000b11d  cmp     dword ptr [rsp+298h+var_270], esi
0x18000b121  jnz     loc_18000B5D5
0x18000b127  test    al, al
0x18000b129  jz      loc_18000B55D
0x18000b12f  xorps   xmm0, xmm0
0x18000b132  movdqa  [rsp+298h+var_228], xmm0
0x18000b138  lea     rdx, [rsp+298h+var_1B0]
0x18000b140  lea     rcx, [rsp+298h+var_228]
0x18000b145  call    ??$_Initialize_dir_enum@U_Dir_enum_impl@filesystem@std@@@_Dir_enum_impl@filesystem@std@@SA?AW4__std_win_error@@AEAV?$shared_ptr@U_Dir_enum_impl@filesystem@std@@@2@AEBVpath@12@W4directory_options@12@@Z; std::filesystem::_Dir_enum_impl::_Initialize_dir_enum<std::filesystem::_Dir_enum_impl>(std::shared_ptr<std::filesystem::_Dir_enum_impl> &,std::filesystem::path const &,std::filesystem::directory_options)
0x18000b14a  test    eax, eax
0x18000b14c  jnz     loc_18000B5EF
0x18000b152  xorps   xmm0, xmm0
0x18000b155  movups  [rsp+298h+var_258], xmm0
0x18000b15a  mov     r14, qword ptr [rsp+298h+var_228+8]
0x18000b15f  test    r14, r14
0x18000b162  jz      short loc_18000B169
0x18000b164  lock inc dword ptr [r14+8]
0x18000b169  movaps  xmm0, [rsp+298h+var_228]
0x18000b16e  movdqa  [rsp+298h+var_258], xmm0
0x18000b174  test    r14, r14
0x18000b177  jz      short loc_18000B17E
0x18000b179  lock inc dword ptr [r14+8]
0x18000b17e  xorps   xmm1, xmm1
0x18000b181  movdqu  [rsp+298h+var_248], xmm1
0x18000b187  test    r14, r14
0x18000b18a  jz      short loc_18000B1C6
0x18000b18c  mov     eax, r15d
0x18000b18f  lock xadd [r14+8], eax
0x18000b195  add     eax, r15d
0x18000b198  jnz     short loc_18000B1C6
0x18000b19a  mov     rax, [r14]
0x18000b19d  mov     rcx, r14
0x18000b1a0  mov     rax, [rax]
0x18000b1a3  call    _guard_dispatch_icall
0x18000b1a8  mov     eax, r15d
0x18000b1ab  lock xadd [r14+0Ch], eax
0x18000b1b1  add     eax, r15d
0x18000b1b4  jnz     short loc_18000B1C6
0x18000b1b6  mov     rax, [r14]
0x18000b1b9  mov     rcx, r14
0x18000b1bc  mov     rax, [rax+8]
0x18000b1c0  call    _guard_dispatch_icall
0x18000b1c5  nop
0x18000b1c6  mov     rdx, qword ptr [rsp+298h+var_258]
0x18000b1cb  cmp     rdx, qword ptr [rsp+298h+var_248]
0x18000b1d0  jz      loc_18000B46C
0x18000b1d6  movups  xmm0, xmmword ptr [rdx]
0x18000b1d9  movaps  [rsp+298h+var_188], xmm0
0x18000b1e1  movups  xmm1, xmmword ptr [rdx+10h]
0x18000b1e5  movaps  [rsp+298h+var_178], xmm1
0x18000b1ed  add     rdx, 20h ; ' '
0x18000b1f1  lea     rcx, [rsp+298h+var_168]
0x18000b1f9  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000b1fe  nop
0x18000b1ff  mov     r8d, 3
0x18000b205  lea     rdx, [rsp+298h+var_270]
0x18000b20a  lea     rcx, [rsp+298h+var_188]
0x18000b212  call    ?_Get_any_status@directory_entry@filesystem@std@@AEBA?AU_File_status_and_error@23@W4__std_fs_stats_flags@@@Z; std::filesystem::directory_entry::_Get_any_status(__std_fs_stats_flags)
0x18000b217  mov     edx, dword ptr [rsp+298h+var_268]
0x18000b21b  mov     rax, qword ptr [rsp+298h+var_270]
0x18000b220  test    edx, edx
0x18000b222  jz      short loc_18000B233
0x18000b224  lea     ecx, [rax-1]
0x18000b227  test    ecx, 0FFFFFFF7h
0x18000b22d  jnz     loc_18000B606
0x18000b233  cmp     eax, 3
0x18000b236  jz      short loc_18000B24A
0x18000b238  lea     rcx, [rsp+298h+var_168]
0x18000b240  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000b245  jmp     loc_18000B455
0x18000b24a  mov     ecx, 58h ; 'X'; Size
0x18000b24f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b254  mov     [rsp+298h+var_278], rax
0x18000b259  lea     rdx, [rsp+298h+var_168]; struct std::filesystem::path *
0x18000b261  mov     rcx, rax; this
0x18000b264  call    ??0UusPackage@@QEAA@AEBVpath@filesystem@std@@@Z; UusPackage::UusPackage(std::filesystem::path const &)
0x18000b269  mov     rbx, rax
0x18000b26c  mov     [rsp+298h+var_278], rax
0x18000b271  cmp     [rax+50h], sil
0x18000b275  jz      short loc_18000B2CE
0x18000b277  mov     rax, [rax+38h]
0x18000b27b  cmp     [rbx+48h], rax
0x18000b27f  jnz     short loc_18000B2CE
0x18000b281  mov     rcx, [r12+38h]
0x18000b286  test    rcx, rcx
0x18000b289  jz      loc_18000B61B
0x18000b28f  mov     rax, [rcx]
0x18000b292  mov     rdx, rbx
0x18000b295  mov     rax, [rax+10h]
0x18000b299  call    _guard_dispatch_icall
0x18000b29e  test    al, al
0x18000b2a0  jz      short loc_18000B2B0
0x18000b2a2  mov     rax, rdi
0x18000b2a5  mov     rdi, rbx
0x18000b2a8  mov     [rsp+298h+var_238], rbx
0x18000b2ad  mov     rbx, rax
0x18000b2b0  test    rbx, rbx
0x18000b2b3  jz      short loc_18000B2C9
0x18000b2b5  mov     rax, [rbx]
0x18000b2b8  mov     edx, 1
0x18000b2bd  mov     rcx, rbx
0x18000b2c0  mov     rax, [rax]
0x18000b2c3  call    _guard_dispatch_icall
0x18000b2c8  nop
0x18000b2c9  jmp     loc_18000B448
0x18000b2ce  cmp     [rbx+50h], sil
0x18000b2d2  jz      loc_18000B3F5
0x18000b2d8  xor     edx, edx; Val
0x18000b2da  mov     r8d, 0F8h; Size
0x18000b2e0  lea     rcx, [rsp+298h+var_148]; void *
0x18000b2e8  call    memset
0x18000b2ed  lea     rcx, [rsp+298h+var_148]
0x18000b2f5  call    ??0?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x18000b2fa  nop
0x18000b2fb  lea     rdx, aPathFolderVers; "Path folder version doesn't match packa"...
0x18000b302  lea     rcx, [rsp+298h+var_138]
0x18000b30a  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18000b30f  mov     [rsp+298h+pv], rax
0x18000b317  lea     rcx, [rbx+30h]
0x18000b31b  lea     rdx, [rsp+298h+var_1F8]
0x18000b323  call    ?GetStringA@UusVersion@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; UusVersion::GetStringA(void)
0x18000b328  nop
0x18000b329  mov     r8, [rax+10h]
0x18000b32d  cmp     qword ptr [rax+18h], 0Fh
0x18000b332  jbe     short loc_18000B337
0x18000b334  mov     rax, [rax]
0x18000b337  mov     rdx, rax
0x18000b33a  mov     rcx, [rsp+298h+pv]
0x18000b342  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18000b347  nop
0x18000b348  lea     rcx, [rsp+298h+var_1F8]
0x18000b350  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18000b355  cmp     [r13+38h], rsi
0x18000b359  jz      short loc_18000B3CB
0x18000b35b  lea     rdx, [rsp+298h+var_1F8]
0x18000b363  lea     rcx, [rsp+298h+var_130]
0x18000b36b  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x18000b370  nop
0x18000b371  lea     rax, [rsp+298h+var_1F8]
0x18000b379  cmp     [rsp+298h+var_1E0], 0Fh
0x18000b382  cmova   rax, [rsp+298h+var_1F8]
0x18000b38b  mov     [rsp+298h+pv], rax
0x18000b393  mov     rcx, [r13+38h]
0x18000b397  test    rcx, rcx
0x18000b39a  jz      loc_18000B621
0x18000b3a0  mov     rax, [rcx]
0x18000b3a3  lea     r8, [rsp+298h+pv]
0x18000b3ab  lea     rdx, [rsp+298h+var_168]
0x18000b3b3  mov     rax, [rax+10h]
0x18000b3b7  call    _guard_dispatch_icall
0x18000b3bc  nop
0x18000b3bd  lea     rcx, [rsp+298h+var_1F8]
0x18000b3c5  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18000b3ca  nop
0x18000b3cb  lea     rcx, [rsp+298h+var_B0]
0x18000b3d3  call    ??1?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@UEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x18000b3d8  lea     rax, ??_7?$basic_ios@_WU?$char_traits@_W@std@@@std@@6B@; const std::wios::`vftable'
0x18000b3df  mov     [rsp+298h+var_B0], rax
0x18000b3e7  lea     rcx, [rsp+298h+var_B0]; this
0x18000b3ef  call    ??1ios_base@std@@UEAA@XZ; std::ios_base::~ios_base(void)
0x18000b3f4  nop
0x18000b3f5  mov     rax, [rbx]
0x18000b3f8  mov     edx, 1
0x18000b3fd  mov     rcx, rbx
0x18000b400  mov     rax, [rax]
0x18000b403  call    _guard_dispatch_icall
0x18000b408  nop
0x18000b409  lea     rcx, [rsp+298h+var_168]
0x18000b411  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000b416  jmp     short loc_18000B455
0x18000b418  xor     esi, esi
0x18000b41a  or      r15, 0FFFFFFFFFFFFFFFFh
0x18000b41e  mov     rdi, [rsp+298h+var_238]
0x18000b423  mov     r14, qword ptr [rsp+298h+var_228+8]
0x18000b428  mov     rax, [rsp+298h+var_208]
0x18000b430  mov     [rsp+298h+var_1C8], rax
0x18000b438  mov     r12, [rsp+298h+var_1B8]
0x18000b440  mov     r13, [rsp+298h+var_1C0]
0x18000b448  lea     rcx, [rsp+298h+var_168]
0x18000b450  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000b455  lea     rcx, [rsp+298h+var_258]
0x18000b45a  call    ?_Advance_and_reset_if_no_more_files@_Dir_enum_impl@filesystem@std@@SA?AW4__std_win_error@@AEAV?$shared_ptr@U_Dir_enum_impl@filesystem@std@@@3@@Z; std::filesystem::_Dir_enum_impl::_Advance_and_reset_if_no_more_files(std::shared_ptr<std::filesystem::_Dir_enum_impl> &)
0x18000b45f  test    eax, eax
0x18000b461  jnz     loc_18000B627
0x18000b467  jmp     loc_18000B1C6
0x18000b46c  mov     rbx, qword ptr [rsp+298h+var_258+8]
0x18000b471  test    rbx, rbx
0x18000b474  jz      short loc_18000B4AE
0x18000b476  mov     eax, r15d
0x18000b479  lock xadd [rbx+8], eax
0x18000b47e  add     eax, r15d
0x18000b481  jnz     short loc_18000B4AE
0x18000b483  mov     rax, [rbx]
0x18000b486  mov     rcx, rbx
0x18000b489  mov     rax, [rax]
0x18000b48c  call    _guard_dispatch_icall
0x18000b491  mov     eax, r15d
0x18000b494  lock xadd [rbx+0Ch], eax
0x18000b499  add     eax, r15d
0x18000b49c  jnz     short loc_18000B4AE
0x18000b49e  mov     rax, [rbx]
0x18000b4a1  mov     rcx, rbx
0x18000b4a4  mov     rax, [rax+8]
0x18000b4a8  call    _guard_dispatch_icall
0x18000b4ad  nop
0x18000b4ae  test    r14, r14
0x18000b4b1  jz      short loc_18000B4EC
0x18000b4b3  mov     eax, r15d
0x18000b4b6  lock xadd [r14+8], eax
0x18000b4bc  add     eax, r15d
0x18000b4bf  jnz     short loc_18000B4EC
0x18000b4c1  mov     rax, [r14]
0x18000b4c4  mov     rcx, r14
0x18000b4c7  mov     rax, [rax]
0x18000b4ca  call    _guard_dispatch_icall
0x18000b4cf  mov     eax, r15d
0x18000b4d2  lock xadd [r14+0Ch], eax
0x18000b4d8  add     eax, r15d
0x18000b4db  jnz     short loc_18000B4EC
0x18000b4dd  mov     rax, [r14]
0x18000b4e0  mov     rcx, r14
0x18000b4e3  mov     rax, [rax+8]
0x18000b4e7  call    _guard_dispatch_icall
0x18000b4ec  mov     rbx, [rsp+298h+var_1C8]
0x18000b4f4  test    rdi, rdi
0x18000b4f7  jz      short loc_18000B55D
0x18000b4f9  mov     rdx, rdi; struct UusPackage *
0x18000b4fc  mov     rcx, rbx; this
0x18000b4ff  call    ??0UusPackage@@QEAA@AEBV0@@Z; UusPackage::UusPackage(UusPackage const &)
0x18000b504  mov     byte ptr [rbx+58h], 1
0x18000b508  lea     rcx, [rsp+298h+var_1B0]
0x18000b510  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000b515  nop
0x18000b516  mov     rax, [rdi]
0x18000b519  mov     edx, 1
0x18000b51e  mov     rcx, rdi
0x18000b521  mov     rax, [rax]
0x18000b524  call    _guard_dispatch_icall
0x18000b529  nop
0x18000b52a  mov     rcx, [r12+38h]
0x18000b52f  test    rcx, rcx
0x18000b532  jz      short loc_18000B54B
0x18000b534  cmp     rcx, r12
0x18000b537  setnz   dl
0x18000b53a  mov     rax, [rcx]
0x18000b53d  mov     rax, [rax+20h]
  ... truncated ...
```
