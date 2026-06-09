# web::json::value::at(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x180029984`
- end: `0x180029a09`
- name: `?at@value@json@web@@QEBAAEBV123@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `133`
- prototype: `wchar_t *__fastcall(_QWORD *, __int64)`
- caller_count: `5`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000a5b0`
- `0x18000ab24`
- `0x180033750`
- `0x180033c14`
- `0x180035fe0`

## callees

- `0x180029984`
- `0x18002bc88`
- `0x18002ca68`
- `0x180044848`
- `0x180047a30`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
wchar_t *__fastcall web::json::value::at(_QWORD *a1, __int64 a2)
{
  __int64 v3; // rax
  __int64 v4; // rbx
  wchar_t *v6; // [rsp+20h] [rbp-48h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+28h] [rbp-40h] BYREF

  v3 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 168LL))(*a1);
  v6 = 0;
  v4 = v3;
  web::json::object::find_by_key(v3, &v6, a2);
  if ( v6 == *(wchar_t **)(v4 + 8) )
  {
    v6 = L"Key not found";
    web::json::json_exception::json_exception(
      (web::json::json_exception *)pExceptionObject,
      (const wchar_t *const *)&v6);
    throw (web::json::json_exception *)pExceptionObject;
  }
  return v6 + 16;
}

```

## disassembly

```asm
0x180029984  mov     [rsp+arg_10], rbx
0x180029989  push    rdi
0x18002998a  sub     rsp, 60h
0x18002998e  mov     rcx, [rcx]
0x180029991  mov     rdi, rdx
0x180029994  mov     rax, [rcx]
0x180029997  mov     rax, [rax+0A8h]
0x18002999e  call    _guard_dispatch_icall
0x1800299a3  mov     r8, rdi
0x1800299a6  mov     [rsp+68h+var_48], 0
0x1800299af  lea     rdx, [rsp+68h+var_48]
0x1800299b4  mov     rcx, rax
0x1800299b7  mov     rbx, rax
0x1800299ba  call    ?find_by_key@object@json@web@@AEBA?AV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@Vvalue@json@web@@@std@@@std@@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@@Z; web::json::object::find_by_key(std::wstring const &)
0x1800299bf  mov     rcx, [rsp+68h+var_48]
0x1800299c4  cmp     rcx, [rbx+8]
0x1800299c8  jz      short loc_1800299DC
0x1800299ca  mov     rbx, [rsp+68h+arg_10]
0x1800299d2  lea     rax, [rcx+20h]
0x1800299d6  add     rsp, 60h
0x1800299da  pop     rdi
0x1800299db  retn
0x1800299dc  lea     rax, aKeyNotFound; "Key not found"
0x1800299e3  lea     rdx, [rsp+68h+var_48]; wchar_t **
0x1800299e8  mov     [rsp+68h+var_48], rax
0x1800299ed  lea     rcx, [rsp+68h+pExceptionObject]; this
0x1800299f2  call    ??0json_exception@json@web@@QEAA@AEBQEB_W@Z; web::json::json_exception::json_exception(wchar_t const * const &)
0x1800299f7  lea     rdx, _TI2?AVjson_exception@json@web@@; pThrowInfo
0x1800299fe  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180029a03  call    _CxxThrowException
```
