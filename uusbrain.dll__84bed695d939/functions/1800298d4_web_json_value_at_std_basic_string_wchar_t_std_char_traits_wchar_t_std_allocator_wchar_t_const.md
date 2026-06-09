# web::json::value::at(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x1800298d4`
- end: `0x18002997b`
- name: `?at@value@json@web@@QEAAAEAV123@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `167`
- prototype: `wchar_t *__fastcall(_QWORD *, __int64)`
- caller_count: `5`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180009f40`
- `0x180032b3c`
- `0x180032fc8`
- `0x180033750`
- `0x180035cb0`

## callees

- `0x1800298d4`
- `0x18002bd80`
- `0x18002be4c`
- `0x18002ca68`
- `0x180044848`
- `0x180047a30`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
wchar_t *__fastcall web::json::value::at(_QWORD *a1, __int64 a2)
{
  __int64 v3; // rax
  __int64 v4; // rdi
  wchar_t *v5; // rbx
  wchar_t *v7; // [rsp+20h] [rbp-48h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+28h] [rbp-40h] BYREF

  v3 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 168LL))(*a1);
  v7 = 0;
  v4 = v3;
  web::json::object::find_insert_location(v3, &v7, a2);
  v5 = v7;
  if ( v7 == *(wchar_t **)(v4 + 8) )
    goto LABEL_6;
  if ( (unsigned __int8)std::operator!=<wchar_t>(a2, v7) )
    v5 = *(wchar_t **)(v4 + 8);
  if ( v5 == *(wchar_t **)(v4 + 8) )
  {
LABEL_6:
    v7 = L"Key not found";
    web::json::json_exception::json_exception(
      (web::json::json_exception *)pExceptionObject,
      (const wchar_t *const *)&v7);
    throw (web::json::json_exception *)pExceptionObject;
  }
  return v5 + 16;
}

```

## disassembly

```asm
0x1800298d4  mov     [rsp+arg_10], rbx
0x1800298d9  mov     [rsp+arg_18], rsi
0x1800298de  push    rdi
0x1800298df  sub     rsp, 60h
0x1800298e3  mov     rcx, [rcx]
0x1800298e6  mov     rsi, rdx
0x1800298e9  mov     rax, [rcx]
0x1800298ec  mov     rax, [rax+0A8h]
0x1800298f3  call    _guard_dispatch_icall
0x1800298f8  mov     r8, rsi
0x1800298fb  mov     [rsp+68h+var_48], 0
0x180029904  lea     rdx, [rsp+68h+var_48]
0x180029909  mov     rcx, rax
0x18002990c  mov     rdi, rax
0x18002990f  call    ?find_insert_location@object@json@web@@AEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@Vvalue@json@web@@@std@@@std@@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@@Z; web::json::object::find_insert_location(std::wstring const &)
0x180029914  mov     rbx, [rsp+68h+var_48]
0x180029919  cmp     rbx, [rdi+8]
0x18002991d  jz      short loc_18002994E
0x18002991f  mov     rdx, rbx
0x180029922  mov     rcx, rsi
0x180029925  call    ??$?9_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@0@Z; std::operator!=<wchar_t>(std::wstring const &,std::wstring const &)
0x18002992a  test    al, al
0x18002992c  jz      short loc_180029932
0x18002992e  mov     rbx, [rdi+8]
0x180029932  cmp     rbx, [rdi+8]
0x180029936  jz      short loc_18002994E
0x180029938  lea     r11, [rsp+68h+var_8]
0x18002993d  mov     rsi, [r11+28h]
0x180029941  lea     rax, [rbx+20h]
0x180029945  mov     rbx, [r11+20h]
0x180029949  mov     rsp, r11
0x18002994c  pop     rdi
0x18002994d  retn
0x18002994e  lea     rax, aKeyNotFound; "Key not found"
0x180029955  lea     rdx, [rsp+68h+var_48]; wchar_t **
0x18002995a  mov     [rsp+68h+var_48], rax
0x18002995f  lea     rcx, [rsp+68h+pExceptionObject]; this
0x180029964  call    ??0json_exception@json@web@@QEAA@AEBQEB_W@Z; web::json::json_exception::json_exception(wchar_t const * const &)
0x180029969  lea     rdx, _TI2?AVjson_exception@json@web@@; pThrowInfo
0x180029970  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180029975  call    _CxxThrowException
```
