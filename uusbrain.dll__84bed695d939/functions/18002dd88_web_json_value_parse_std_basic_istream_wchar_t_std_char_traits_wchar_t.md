# web::json::value::parse(std::basic_istream<wchar_t,std::char_traits<wchar_t>> &)

- ea: `0x18002dd88`
- end: `0x18002df1a`
- name: `?parse@value@json@web@@SA?AV123@AEAV?$basic_istream@_WU?$char_traits@_W@std@@@std@@@Z`
- size: `402`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x180032fc8`
- `0x180035cb0`

## callees

- `0x18000f8cc`
- `0x18002769c`
- `0x180029644`
- `0x18002dd88`
- `0x18002e0cc`
- `0x18002e198`
- `0x18002f6a4`
- `0x1800322e8`
- `0x1800427d0`
- `0x180047a30`

## string_xrefs

- `0x18002dea5`: `Left-over characters in stream after parsing a JSON value`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
_QWORD *__fastcall web::json::value::parse(_QWORD *a1, __int64 a2)
{
  __int64 *v3; // rcx
  __int64 v4; // rax
  __int64 v5; // rcx
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  _QWORD v11[2]; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v12[32]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v13[40]; // [rsp+58h] [rbp-A8h] BYREF
  int v14; // [rsp+80h] [rbp-80h] BYREF
  __int128 v15; // [rsp+88h] [rbp-78h] BYREF
  __int64 v16; // [rsp+98h] [rbp-68h]
  __int64 v17; // [rsp+A0h] [rbp-60h]
  int v18; // [rsp+C8h] [rbp-38h] BYREF
  void ***v19; // [rsp+D0h] [rbp-30h]
  _QWORD v20[5]; // [rsp+E0h] [rbp-20h] BYREF

  v11[1] = a1;
  v20[1] = 1;
  v20[2] = 1;
  v20[3] = 0;
  v20[0] = &web::json::details::JSON_StreamParser<wchar_t>::`vftable';
  v20[4] = *(_QWORD *)(*(int *)(*(_QWORD *)a2 + 4LL) + a2 + 72);
  v14 = 0;
  v15 = 0;
  v16 = 0;
  v17 = 7;
  LOWORD(v15) = 0;
  v18 = 0;
  v19 = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
  web::json::details::JSON_Parser<wchar_t>::GetNextToken(v20, &v14);
  if ( v18 )
  {
    v7 = std::error_code::message(&v18, v12);
    v8 = utility::conversions::to_string_t(v13, v7);
    web::json::details::CreateException<web::json::details::JSON_Parser<char>::Token>((__int64)&v14, v8);
  }
  *a1 = 0;
  v3 = web::json::details::JSON_Parser<wchar_t>::_ParseValue((__int64)v20, v11, (__int64)&v14);
  v4 = *v3;
  *v3 = 0;
  *a1 = v4;
  v5 = *v3;
  if ( v5 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v5 + 192LL))(v5, 1);
  if ( v18 )
  {
    v9 = std::error_code::message(&v18, v13);
    v10 = utility::conversions::to_string_t(v12, v9);
    web::json::details::CreateException<web::json::details::JSON_Parser<char>::Token>((__int64)&v14, v10);
  }
  if ( v14 )
  {
    std::wstring::wstring(v12, L"Left-over characters in stream after parsing a JSON value");
    web::json::details::CreateException<web::json::details::JSON_Parser<char>::Token>((__int64)&v14, (__int64)v12);
  }
  std::wstring::_Tidy_deallocate((__int64)&v15);
  return a1;
}

```

## disassembly

```asm
0x18002dd88  mov     [rsp-8+arg_8], rbx
0x18002dd8d  mov     [rsp-8+arg_10], rdi
0x18002dd92  push    rbp
0x18002dd93  lea     rbp, [rsp-10h]
0x18002dd98  sub     rsp, 110h
0x18002dd9f  mov     rax, cs:__security_cookie
0x18002dda6  xor     rax, rsp
0x18002dda9  mov     [rbp+10h+var_8], rax
0x18002ddad  mov     rbx, rcx
0x18002ddb0  mov     [rsp+110h+var_E0], rcx
0x18002ddb5  xor     edi, edi
0x18002ddb7  mov     [rsp+110h+var_F0], edi
0x18002ddbb  mov     [rbp+10h+var_28], 1
0x18002ddc3  mov     [rbp+10h+var_20], 1
0x18002ddcb  mov     [rbp+10h+var_18], rdi
0x18002ddcf  lea     rax, ??_7?$JSON_StreamParser@_W@details@json@web@@6B@; const web::json::details::JSON_StreamParser<wchar_t>::`vftable'
0x18002ddd6  mov     [rbp+10h+var_30], rax
0x18002ddda  mov     rax, [rdx]
0x18002dddd  movsxd  rcx, dword ptr [rax+4]
0x18002dde1  mov     rax, [rcx+rdx+48h]
0x18002dde6  mov     [rbp+10h+var_10], rax
0x18002ddea  mov     [rbp+10h+var_90], edi
0x18002dded  xorps   xmm0, xmm0
0x18002ddf0  movups  [rbp+10h+var_88], xmm0
0x18002ddf4  mov     [rbp+10h+var_78], rdi
0x18002ddf8  mov     [rbp+10h+var_70], 7
0x18002de00  mov     word ptr [rbp+10h+var_88], di
0x18002de04  mov     [rbp+10h+var_48], edi
0x18002de07  lea     rax, ?_Static@?1???$_Immortalize_memcpy_image@V_System_error_category@std@@@std@@YAAEBV_System_error_category@1@XZ@4U?$_Constexpr_immortalize_impl@V_System_error_category@std@@@1@A; std::_Constexpr_immortalize_impl<std::_System_error_category> `std::_Immortalize_memcpy_image<std::_System_error_category>(void)'::`2'::_Static
0x18002de0e  mov     [rbp+10h+var_40], rax
0x18002de12  lea     rdx, [rbp+10h+var_90]
0x18002de16  lea     rcx, [rbp+10h+var_30]
0x18002de1a  call    ?GetNextToken@?$JSON_Parser@_W@details@json@web@@QEAAXAEAUToken@1234@@Z; web::json::details::JSON_Parser<wchar_t>::GetNextToken(web::json::details::JSON_Parser<wchar_t>::Token &)
0x18002de1f  cmp     [rbp+10h+var_48], edi
0x18002de22  jnz     loc_18002DEC6
0x18002de28  xor     eax, eax
0x18002de2a  mov     [rbx], rax
0x18002de2d  lea     r8, [rbp+10h+var_90]
0x18002de31  lea     rdx, [rsp+110h+var_E8]
0x18002de36  lea     rcx, [rbp+10h+var_30]
0x18002de3a  call    ?_ParseValue@?$JSON_Parser@_W@details@json@web@@AEAA?AV?$unique_ptr@V_Value@details@json@web@@U?$default_delete@V_Value@details@json@web@@@std@@@std@@AEAUToken@1234@@Z; web::json::details::JSON_Parser<wchar_t>::_ParseValue(web::json::details::JSON_Parser<wchar_t>::Token &)
0x18002de3f  mov     rcx, rax
0x18002de42  mov     rax, [rax]
0x18002de45  mov     [rcx], rdi
0x18002de48  mov     [rbx], rax
0x18002de4b  mov     rcx, [rcx]
0x18002de4e  test    rcx, rcx
0x18002de51  jz      short loc_18002DE65
0x18002de53  mov     rax, [rcx]
0x18002de56  lea     edx, [rdi+1]
0x18002de59  mov     rax, [rax+0C0h]
0x18002de60  call    _guard_dispatch_icall
0x18002de65  mov     [rsp+110h+var_F0], 6
0x18002de6d  cmp     [rbp+10h+var_48], edi
0x18002de70  jnz     short loc_18002DEF0
0x18002de72  cmp     [rbp+10h+var_90], edi
0x18002de75  jnz     short loc_18002DEA5
0x18002de77  lea     rcx, [rbp+10h+var_88]
0x18002de7b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002de80  nop
0x18002de81  mov     rax, rbx
0x18002de84  mov     rcx, [rbp+10h+var_8]
0x18002de88  xor     rcx, rsp; StackCookie
0x18002de8b  call    __security_check_cookie
0x18002de90  lea     r11, [rsp+110h+var_s0]
0x18002de98  mov     rbx, [r11+18h]
0x18002de9c  mov     rdi, [r11+20h]
0x18002dea0  mov     rsp, r11
0x18002dea3  pop     rbp
0x18002dea4  retn
0x18002dea5  lea     rdx, aLeftOverCharac; "Left-over characters in stream after pa"...
0x18002deac  lea     rcx, [rsp+110h+var_D8]
0x18002deb1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18002deb6  nop
0x18002deb7  lea     rdx, [rsp+110h+var_D8]
0x18002debc  lea     rcx, [rbp+10h+var_90]
0x18002dec0  call    ??$CreateException@UToken@?$JSON_Parser@D@details@json@web@@@details@json@web@@YAXAEBUToken@?$JSON_Parser@D@012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::details::CreateException<web::json::details::JSON_Parser<char>::Token>(web::json::details::JSON_Parser<char>::Token const &,std::wstring const &)
0x18002dec6  lea     rdx, [rsp+110h+var_D8]
0x18002decb  lea     rcx, [rbp+10h+var_48]
0x18002decf  call    ?message@error_code@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::error_code::message(void)
0x18002ded4  nop
0x18002ded5  mov     rdx, rax
0x18002ded8  lea     rcx, [rsp+110h+var_B8]
0x18002dedd  call    ?to_string_t@conversions@utility@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$QEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; utility::conversions::to_string_t(std::string &&)
0x18002dee2  nop
0x18002dee3  mov     rdx, rax
0x18002dee6  lea     rcx, [rbp+10h+var_90]
0x18002deea  call    ??$CreateException@UToken@?$JSON_Parser@D@details@json@web@@@details@json@web@@YAXAEBUToken@?$JSON_Parser@D@012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::details::CreateException<web::json::details::JSON_Parser<char>::Token>(web::json::details::JSON_Parser<char>::Token const &,std::wstring const &)
0x18002def0  lea     rdx, [rsp+110h+var_B8]
0x18002def5  lea     rcx, [rbp+10h+var_48]
0x18002def9  call    ?message@error_code@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::error_code::message(void)
0x18002defe  nop
0x18002deff  mov     rdx, rax
0x18002df02  lea     rcx, [rsp+110h+var_D8]
0x18002df07  call    ?to_string_t@conversions@utility@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$QEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; utility::conversions::to_string_t(std::string &&)
0x18002df0c  nop
0x18002df0d  mov     rdx, rax
0x18002df10  lea     rcx, [rbp+10h+var_90]
0x18002df14  call    ??$CreateException@UToken@?$JSON_Parser@D@details@json@web@@@details@json@web@@YAXAEBUToken@?$JSON_Parser@D@012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::details::CreateException<web::json::details::JSON_Parser<char>::Token>(web::json::details::JSON_Parser<char>::Token const &,std::wstring const &)
```
