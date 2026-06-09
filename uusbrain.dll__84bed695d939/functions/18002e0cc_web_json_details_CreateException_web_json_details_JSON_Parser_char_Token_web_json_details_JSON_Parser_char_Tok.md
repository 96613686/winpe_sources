# web::json::details::CreateException<web::json::details::JSON_Parser<char>::Token>(web::json::details::JSON_Parser<char>::Token const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x18002e0cc`
- end: `0x18002e190`
- name: `??$CreateException@UToken@?$JSON_Parser@D@details@json@web@@@details@json@web@@YAXAEBUToken@?$JSON_Parser@D@012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `196`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18002dbdc`
- `0x18002dd88`
- `0x18002df20`

## callees

- `0x18000deb8`
- `0x18000e3d8`
- `0x180027184`
- `0x18002ca68`
- `0x180031608`
- `0x18003162c`
- `0x1800318d4`
- `0x1800319f0`
- `0x180044848`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall __noreturn web::json::details::CreateException<web::json::details::JSON_Parser<char>::Token>(
        __int64 a1,
        __int64 a2)
{
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  wchar_t *v10; // [rsp+20h] [rbp-158h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+28h] [rbp-150h] BYREF
  _BYTE v12[32]; // [rsp+60h] [rbp-118h] BYREF
  _BYTE v13[248]; // [rsp+80h] [rbp-F8h] BYREF

  std::wostringstream::__autoclassinit2(v13);
  std::wostringstream::wostringstream(v13);
  v4 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(v13, L"* Line ");
  v5 = std::wostream::operator<<(v4, *(_QWORD *)(a1 + 40));
  v6 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(v5, L", Column ");
  v7 = std::wostream::operator<<(v6, *(_QWORD *)(a1 + 48));
  v8 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(v7, L" Syntax error: ");
  std::operator<<<wchar_t>(v8, a2);
  v9 = std::wostringstream::str(v13, v12);
  v10 = (wchar_t *)std::wstring::c_str(v9);
  web::json::json_exception::json_exception((web::json::json_exception *)pExceptionObject, (const wchar_t *const *)&v10);
  throw (web::json::json_exception *)pExceptionObject;
}

```

## disassembly

```asm
0x18002e0cc  mov     [rsp+arg_10], rbx
0x18002e0d1  push    rdi
0x18002e0d2  sub     rsp, 170h
0x18002e0d9  mov     rdi, rdx
0x18002e0dc  mov     rbx, rcx
0x18002e0df  lea     rcx, [rsp+178h+var_F8]
0x18002e0e7  call    ?__autoclassinit2@?$basic_ostringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K@Z; std::wostringstream::__autoclassinit2(unsigned __int64)
0x18002e0ec  lea     rcx, [rsp+178h+var_F8]
0x18002e0f4  call    ??0?$basic_ostringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wostringstream::wostringstream(void)
0x18002e0f9  nop
0x18002e0fa  lea     rdx, aLine; "* Line "
0x18002e101  lea     rcx, [rsp+178h+var_F8]
0x18002e109  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x18002e10e  mov     rdx, [rbx+28h]
0x18002e112  mov     rcx, rax
0x18002e115  call    ??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@_K@Z; std::wostream::operator<<(unsigned __int64)
0x18002e11a  mov     rcx, rax
0x18002e11d  lea     rdx, aColumn; ", Column "
0x18002e124  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x18002e129  mov     rdx, [rbx+30h]
0x18002e12d  mov     rcx, rax
0x18002e130  call    ??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@_K@Z; std::wostream::operator<<(unsigned __int64)
0x18002e135  mov     rcx, rax
0x18002e138  lea     rdx, aSyntaxError; " Syntax error: "
0x18002e13f  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x18002e144  mov     rcx, rax
0x18002e147  mov     rdx, rdi
0x18002e14a  call    ??$?6_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@@Z; std::operator<<<wchar_t>(std::wostream &,std::wstring const &)
0x18002e14f  lea     rdx, [rsp+178h+var_118]
0x18002e154  lea     rcx, [rsp+178h+var_F8]
0x18002e15c  call    ?str@?$basic_ostringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@XZ; std::wostringstream::str(void)
0x18002e161  nop
0x18002e162  mov     rcx, rax
0x18002e165  call    ?c_str@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBAPEB_WXZ; std::wstring::c_str(void)
0x18002e16a  mov     [rsp+178h+var_158], rax
0x18002e16f  lea     rdx, [rsp+178h+var_158]; wchar_t **
0x18002e174  lea     rcx, [rsp+178h+pExceptionObject]; this
0x18002e179  call    ??0json_exception@json@web@@QEAA@AEBQEB_W@Z; web::json::json_exception::json_exception(wchar_t const * const &)
0x18002e17e  lea     rdx, _TI2?AVjson_exception@json@web@@; pThrowInfo
0x18002e185  lea     rcx, [rsp+178h+pExceptionObject]; pExceptionObject
0x18002e18a  call    _CxxThrowException
```
