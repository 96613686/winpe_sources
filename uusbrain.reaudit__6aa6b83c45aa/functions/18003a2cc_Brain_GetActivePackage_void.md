# Brain::GetActivePackage(void)

- ea: `0x18003a2cc`
- end: `0x18003a617`
- name: `?GetActivePackage@Brain@@AEAA?AVUusPackage@@XZ`
- size: `843`
- prototype: `struct UusPackage __high(void)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180037064`

## callees

- `0x180006614`
- `0x1800089f4`
- `0x18000ab24`
- `0x18000ae24`
- `0x18000b024`
- `0x18000d660`
- `0x180025610`
- `0x180027184`
- `0x180029344`
- `0x1800295e8`
- `0x180029644`
- `0x180039858`
- `0x18003a2cc`
- `0x1800427d0`
- `0x180044848`
- `0x180047a30`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a370`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a370`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void *__fastcall Brain::GetActivePackage(__int64 a1, void *a2)
{
  void *v3; // rdi
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 String; // rax
  unsigned int v8; // eax
  const char *v9; // rdx
  _QWORD v10[3]; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v11[2]; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v12[8]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v13[56]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v14; // [rsp+D0h] [rbp-30h]
  LPVOID pv[2]; // [rsp+E0h] [rbp-20h] BYREF
  _OWORD v16[2]; // [rsp+F0h] [rbp-10h] BYREF
  _QWORD pExceptionObject[2]; // [rsp+110h] [rbp+10h] BYREF
  char v18; // [rsp+120h] [rbp+20h]
  void **v19; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v20[32]; // [rsp+138h] [rbp+38h] BYREF
  __int64 v21; // [rsp+158h] [rbp+58h]
  void **v22; // [rsp+160h] [rbp+60h]
  void *v23; // [rsp+168h] [rbp+68h]
  _QWORD v24[2]; // [rsp+170h] [rbp+70h] BYREF
  char v25; // [rsp+180h] [rbp+80h]
  _QWORD v26[11]; // [rsp+190h] [rbp+90h] BYREF
  char v27; // [rsp+1E8h] [rbp+E8h]
  _QWORD v28[11]; // [rsp+1F0h] [rbp+F0h] BYREF
  char v29; // [rsp+248h] [rbp+148h]
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  pv[0] = a2;
  if ( !*(_BYTE *)(a1 + 392) )
  {
    std::runtime_error::runtime_error(
      (std::runtime_error *)pExceptionObject,
      "GetActivePackage() must not be called if there is no active package (lock isn't acquired).");
    throw (std::runtime_error *)pExceptionObject;
  }
  v3 = *(void **)(a1 + 384);
  v11[0] = &UusVersion::`vftable';
  v11[1] = v3;
  pv[0] = 0;
  wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(
    pv,
    L"%SystemRoot%\\uus");
  v4 = -1;
  do
    ++v4;
  while ( *((_WORD *)pv[0] + v4) );
  v10[0] = pv[0];
  v10[1] = v4;
  std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v16, v10);
  if ( pv[0] )
    CoTaskMemFree(pv[0]);
  UusPackage::UusPackage((UusPackage *)&v19, (const struct std::filesystem::path *)v16);
  std::wstring::_Tidy_deallocate(v16);
  if ( v23 == v3 )
  {
    UusPackage::UusPackage((UusPackage *)a2, (const struct UusPackage *)&v19);
  }
  else
  {
    Brain::GetPreviewPackage((UusPackage *)v26);
    if ( !v27 || (void *)v26[7] != v3 )
    {
      pv[0] = v3;
      v18 = 0;
      v16[0] = 0;
      v16[1] = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v16[0]) = 0;
      v14 = 0;
      v12[0] = &std::_Func_impl_no_alloc<_lambda_64bcd93cd23306193d5e3d57bb52b38d_,bool,UusPackage const &>::`vftable';
      v12[1] = pv;
      v12[2] = pExceptionObject;
      v12[3] = v16;
      v12[7] = v12;
      UusPackage::FindBestPackage((UusPackage *)v28, (__int64)v12, (__int64)v13);
      std::wstring::_Tidy_deallocate(v16);
      if ( v18 )
        (*(void (__fastcall **)(_QWORD *, _QWORD))pExceptionObject[0])(pExceptionObject, 0);
      if ( !v29 )
      {
        String = UusVersion::GetString(v11, v16);
        std::wstring::c_str(String);
        v8 = wil::verify_hresult<long>(2147942402LL);
        wil::details::in1diag3::Throw_HrMsg(
          retaddr,
          (void *)0x2D9,
          (unsigned int)"C:\\__w\\1\\s\\src\\brain\\lib\\Brain.cpp",
          (const char *)v8,
          (int)"Unable to find active package %s",
          v9);
      }
      UusPackage::UusPackage((UusPackage *)a2, (const struct UusPackage *)v28);
      if ( v29 )
        (*(void (__fastcall **)(_QWORD *, _QWORD))v28[0])(v28, 0);
      if ( v27 )
        (*(void (__fastcall **)(_QWORD *, _QWORD))v26[0])(v26, 0);
      v19 = &UusPackage::`vftable';
      if ( v25 )
        (*(void (__fastcall **)(_QWORD *, _QWORD))v24[0])(v24, 0);
      v22 = &UusVersion::`vftable';
      v5 = v21;
      if ( v21 )
        goto LABEL_26;
      goto LABEL_27;
    }
    UusPackage::UusPackage((UusPackage *)a2, (const struct UusPackage *)v26);
    if ( v27 )
      (*(void (__fastcall **)(_QWORD *, _QWORD))v26[0])(v26, 0);
  }
  v19 = &UusPackage::`vftable';
  if ( v25 )
    (*(void (__fastcall **)(_QWORD *, _QWORD))v24[0])(v24, 0);
  v22 = &UusVersion::`vftable';
  v5 = v21;
  if ( v21 )
LABEL_26:
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v21 + 192LL))(v5, 1);
LABEL_27:
  std::wstring::_Tidy_deallocate(v20);
  return a2;
}

```

## disassembly

```asm
0x18003a2cc  mov     [rsp-8+arg_0], rbx
0x18003a2d1  mov     [rsp-8+arg_10], rsi
0x18003a2d6  push    rbp
0x18003a2d7  push    rdi
0x18003a2d8  push    r14
0x18003a2da  lea     rbp, [rsp-160h]
0x18003a2e2  sub     rsp, 260h
0x18003a2e9  mov     rax, cs:__security_cookie
0x18003a2f0  xor     rax, rsp
0x18003a2f3  mov     [rbp+170h+var_20], rax
0x18003a2fa  mov     rbx, rdx
0x18003a2fd  mov     [rbp+170h+pv], rdx
0x18003a301  xor     esi, esi
0x18003a303  cmp     [rcx+188h], sil
0x18003a30a  jz      loc_18003A5A5
0x18003a310  mov     rdi, [rcx+180h]
0x18003a317  lea     r14, ??_7UusVersion@@6B@; const UusVersion::`vftable'
0x18003a31e  mov     [rsp+270h+var_228], r14
0x18003a323  mov     [rsp+270h+var_220], rdi
0x18003a328  mov     [rbp+170h+pv], rsi
0x18003a32c  lea     rdx, aSystemrootUus; "%SystemRoot%\\uus"
0x18003a333  lea     rcx, [rbp+170h+pv]
0x18003a337  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(wchar_t const *)
0x18003a33c  nop
0x18003a33d  mov     rax, [rbp+170h+pv]
0x18003a341  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18003a345  inc     rcx
0x18003a348  cmp     [rax+rcx*2], si
0x18003a34c  jnz     short loc_18003A345
0x18003a34e  mov     [rsp+270h+var_240], rax
0x18003a353  mov     [rsp+270h+var_238], rcx
0x18003a358  lea     rdx, [rsp+270h+var_240]
0x18003a35d  lea     rcx, [rbp+170h+var_180]
0x18003a361  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::wstring_view,std::filesystem::_Normal_conversion)
0x18003a366  nop
0x18003a367  mov     rcx, [rbp+170h+pv]; pv
0x18003a36b  test    rcx, rcx
0x18003a36e  jz      short loc_18003A377
0x18003a370  call    cs:__imp_CoTaskMemFree
0x18003a376  nop
0x18003a377  lea     rdx, [rbp+170h+var_180]; struct std::filesystem::path *
0x18003a37b  lea     rcx, [rbp+170h+var_140]; this
0x18003a37f  call    ??0UusPackage@@QEAA@AEBVpath@filesystem@std@@@Z; UusPackage::UusPackage(std::filesystem::path const &)
0x18003a384  nop
0x18003a385  lea     rcx, [rbp+170h+var_180]
0x18003a389  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003a38e  cmp     [rbp+170h+var_108], rdi
0x18003a392  jnz     short loc_18003A3E7
0x18003a394  lea     rdx, [rbp+170h+var_140]; struct UusPackage *
0x18003a398  mov     rcx, rbx; this
0x18003a39b  call    ??0UusPackage@@QEAA@AEBV0@@Z; UusPackage::UusPackage(UusPackage const &)
0x18003a3a0  nop
0x18003a3a1  lea     rax, ??_7UusPackage@@6B@; const UusPackage::`vftable'
0x18003a3a8  cmp     [rbp+170h+var_F0], sil
0x18003a3af  mov     [rbp+170h+var_140], rax
0x18003a3b3  jz      short loc_18003A3C7
0x18003a3b5  mov     rax, [rbp+170h+var_100]
0x18003a3b9  xor     edx, edx
0x18003a3bb  lea     rcx, [rbp+170h+var_100]
0x18003a3bf  mov     rax, [rax]
0x18003a3c2  call    _guard_dispatch_icall
0x18003a3c7  mov     [rbp+170h+var_110], r14
0x18003a3cb  mov     rcx, [rbp+170h+var_118]
0x18003a3cf  test    rcx, rcx
0x18003a3d2  jz      loc_18003A571
0x18003a3d8  mov     rax, [rcx]
0x18003a3db  mov     rax, [rax+0C0h]
0x18003a3e2  jmp     loc_18003A567
0x18003a3e7  lea     rcx, [rbp+170h+var_E0]; this
0x18003a3ee  call    ?GetPreviewPackage@Brain@@CA?AV?$optional@VUusPackage@@@std@@XZ; Brain::GetPreviewPackage(void)
0x18003a3f3  nop
0x18003a3f4  cmp     [rbp+170h+var_88], sil
0x18003a3fb  jz      short loc_18003A43C
0x18003a3fd  cmp     [rbp+170h+var_A8], rdi
0x18003a404  jnz     short loc_18003A43C
0x18003a406  lea     rdx, [rbp+170h+var_E0]; struct UusPackage *
0x18003a40d  mov     rcx, rbx; this
0x18003a410  call    ??0UusPackage@@QEAA@AEBV0@@Z; UusPackage::UusPackage(UusPackage const &)
0x18003a415  nop
0x18003a416  cmp     [rbp+170h+var_88], sil
0x18003a41d  jz      short loc_18003A3A1
0x18003a41f  mov     rax, [rbp+170h+var_E0]
0x18003a426  xor     edx, edx
0x18003a428  lea     rcx, [rbp+170h+var_E0]
0x18003a42f  mov     rax, [rax]
0x18003a432  call    _guard_dispatch_icall
0x18003a437  jmp     loc_18003A3A1
0x18003a43c  mov     [rbp+170h+pv], rdi
0x18003a440  mov     [rbp+170h+var_150], sil
0x18003a444  xorps   xmm0, xmm0
0x18003a447  movups  [rbp+170h+var_180], xmm0
0x18003a44b  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18003a453  movdqu  [rbp+170h+var_170], xmm1
0x18003a458  mov     word ptr [rbp+170h+var_180], si
0x18003a45c  mov     [rbp+170h+var_1A0], rsi
0x18003a460  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_64bcd93cd23306193d5e3d57bb52b38d_@@_NAEBVUusPackage@@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_64bcd93cd23306193d5e3d57bb52b38d_,bool,UusPackage const &>::`vftable'
0x18003a467  mov     [rsp+270h+var_218], rax
0x18003a46c  lea     rax, [rbp+170h+pv]
0x18003a470  mov     [rsp+270h+var_210], rax
0x18003a475  lea     rax, [rbp+170h+pExceptionObject]
0x18003a479  mov     [rsp+270h+var_208], rax
0x18003a47e  lea     rax, [rbp+170h+var_180]
0x18003a482  mov     [rsp+270h+var_200], rax
0x18003a487  lea     rax, [rsp+270h+var_218]
0x18003a48c  mov     [rbp+170h+var_1E0], rax
0x18003a490  lea     r8, [rbp+170h+var_1D8]
0x18003a494  lea     rdx, [rsp+270h+var_218]
0x18003a499  lea     rcx, [rbp+170h+var_80]
0x18003a4a0  call    ?FindBestPackage@UusPackage@@CA?AV?$optional@VUusPackage@@@std@@V?$function@$$A6A_NAEBVUusPackage@@@Z@3@V?$function@$$A6AXAEBVpath@filesystem@std@@PEBD@Z@3@@Z; UusPackage::FindBestPackage(std::function<bool (UusPackage const &)>,std::function<void (std::filesystem::path const &,char const *)>)
0x18003a4a5  nop
0x18003a4a6  lea     rcx, [rbp+170h+var_180]
0x18003a4aa  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003a4af  nop
0x18003a4b0  cmp     [rbp+170h+var_150], sil
0x18003a4b4  jz      short loc_18003A4C9
0x18003a4b6  mov     rax, [rbp+170h+pExceptionObject]
0x18003a4ba  xor     edx, edx
0x18003a4bc  lea     rcx, [rbp+170h+pExceptionObject]
0x18003a4c0  mov     rax, [rax]
0x18003a4c3  call    _guard_dispatch_icall
0x18003a4c8  nop
0x18003a4c9  cmp     [rbp+170h+var_28], sil
0x18003a4d0  jz      loc_18003A5C6
0x18003a4d6  lea     rdx, [rbp+170h+var_80]; struct UusPackage *
0x18003a4dd  mov     rcx, rbx; this
0x18003a4e0  call    ??0UusPackage@@QEAA@AEBV0@@Z; UusPackage::UusPackage(UusPackage const &)
0x18003a4e5  nop
0x18003a4e6  cmp     [rbp+170h+var_28], sil
0x18003a4ed  jz      short loc_18003A508
0x18003a4ef  mov     rax, [rbp+170h+var_80]
0x18003a4f6  xor     edx, edx
0x18003a4f8  lea     rcx, [rbp+170h+var_80]
0x18003a4ff  mov     rax, [rax]
0x18003a502  call    _guard_dispatch_icall
0x18003a507  nop
0x18003a508  cmp     [rbp+170h+var_88], sil
0x18003a50f  jz      short loc_18003A52A
0x18003a511  mov     rax, [rbp+170h+var_E0]
0x18003a518  xor     edx, edx
0x18003a51a  lea     rcx, [rbp+170h+var_E0]
0x18003a521  mov     rax, [rax]
0x18003a524  call    _guard_dispatch_icall
0x18003a529  nop
0x18003a52a  lea     rax, ??_7UusPackage@@6B@; const UusPackage::`vftable'
0x18003a531  mov     [rbp+170h+var_140], rax
0x18003a535  cmp     [rbp+170h+var_F0], sil
0x18003a53c  jz      short loc_18003A550
0x18003a53e  mov     rax, [rbp+170h+var_100]
0x18003a542  xor     edx, edx
0x18003a544  lea     rcx, [rbp+170h+var_100]
0x18003a548  mov     rax, [rax]
0x18003a54b  call    _guard_dispatch_icall
0x18003a550  mov     [rbp+170h+var_110], r14
0x18003a554  mov     rcx, [rbp+170h+var_118]
0x18003a558  test    rcx, rcx
0x18003a55b  jz      short loc_18003A571
0x18003a55d  mov     rdx, [rcx]
0x18003a560  mov     rax, [rdx+0C0h]
0x18003a567  mov     edx, 1
0x18003a56c  call    _guard_dispatch_icall
0x18003a571  lea     rcx, [rbp+170h+var_138]
0x18003a575  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003a57a  nop
0x18003a57b  mov     rax, rbx
0x18003a57e  mov     rcx, [rbp+170h+var_20]
0x18003a585  xor     rcx, rsp; StackCookie
0x18003a588  call    __security_check_cookie
0x18003a58d  lea     r11, [rsp+270h+var_10]
0x18003a595  mov     rbx, [r11+20h]
0x18003a599  mov     rsi, [r11+30h]
0x18003a59d  mov     rsp, r11
0x18003a5a0  pop     r14
0x18003a5a2  pop     rdi
0x18003a5a3  pop     rbp
0x18003a5a4  retn
0x18003a5a5  lea     rdx, aGetactivepacka; "GetActivePackage() must not be called i"...
0x18003a5ac  lea     rcx, [rbp+170h+pExceptionObject]; this
0x18003a5b0  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x18003a5b5  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18003a5bc  lea     rcx, [rbp+170h+pExceptionObject]; pExceptionObject
0x18003a5c0  call    _CxxThrowException
0x18003a5c6  lea     rdx, [rbp+170h+var_180]
0x18003a5ca  lea     rcx, [rsp+270h+var_228]
0x18003a5cf  call    ?GetString@UusVersion@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; UusVersion::GetString(void)
0x18003a5d4  nop
0x18003a5d5  mov     rcx, rax
0x18003a5d8  call    ?c_str@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBAPEB_WXZ; std::wstring::c_str(void)
0x18003a5dd  mov     rdx, rax
0x18003a5e0  mov     ecx, 80070002h
0x18003a5e5  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18003a5ea  mov     r9d, eax; char *
0x18003a5ed  mov     rcx, [rbp+178h]; this
0x18003a5f4  mov     [rsp+270h+var_248], rdx; char *
0x18003a5f9  lea     rax, aUnableToFindAc; "Unable to find active package %s"
0x18003a600  mov     qword ptr [rsp+270h+var_250], rax; int
0x18003a605  lea     r8, aCW1SSrcBrainLi; "C:\\__w\\1\\s\\src\\brain\\lib\\Brain.c"...
0x18003a60c  mov     edx, 2D9h; void *
0x18003a611  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
```
