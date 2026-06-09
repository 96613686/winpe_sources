# srstor::MSFT_Volume::ObjectId(void)

- ea: `0x180029970`
- end: `0x1800299de`
- name: `?ObjectId@MSFT_Volume@srstor@@QEBA?BV?$read_property@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@XZ`
- size: `110`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x180021da4`
- `0x180021f64`
- `0x18002214c`
- `0x18002231c`
- `0x180022490`

## callees

- `0x1800014e0`
- `0x1800058c8`
- `0x180006724`
- `0x180020138`

## pseudocode

```c
_QWORD *__fastcall srstor::MSFT_Volume::ObjectId(__int64 a1, _QWORD *a2)
{
  _BYTE v5[32]; // [rsp+30h] [rbp-38h] BYREF

  std::wstring::wstring(v5, L"ObjectId");
  srstor::read_property<std::wstring>::read_property<std::wstring>(a2, a1 + 8, (__int64)v5);
  std::wstring::_Tidy_deallocate(v5);
  return a2;
}

```

## disassembly

```asm
0x180029970  mov     [rsp+arg_0], rbx
0x180029975  push    rdi
0x180029976  sub     rsp, 60h
0x18002997a  mov     rax, cs:__security_cookie
0x180029981  xor     rax, rsp
0x180029984  mov     [rsp+68h+var_18], rax
0x180029989  mov     rdi, rdx
0x18002998c  mov     rbx, rcx
0x18002998f  mov     [rsp+68h+var_40], rdx
0x180029994  lea     rdx, aObjectid; "ObjectId"
0x18002999b  lea     rcx, [rsp+68h+var_38]
0x1800299a0  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800299a5  nop
0x1800299a6  lea     rdx, [rbx+8]
0x1800299aa  lea     r8, [rsp+68h+var_38]
0x1800299af  mov     rcx, rdi
0x1800299b2  call    ??0?$read_property@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@srstor@@QEAA@AEBVMiInstance@mi@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; srstor::read_property<std::wstring>::read_property<std::wstring>(mi::MiInstance const &,std::wstring const &)
0x1800299b7  nop
0x1800299b8  lea     rcx, [rsp+68h+var_38]
0x1800299bd  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800299c2  mov     rax, rdi
0x1800299c5  mov     rcx, [rsp+68h+var_18]
0x1800299ca  xor     rcx, rsp; StackCookie
0x1800299cd  call    __security_check_cookie
0x1800299d2  mov     rbx, [rsp+68h+arg_0]
0x1800299d7  add     rsp, 60h
0x1800299db  pop     rdi
0x1800299dc  retn
```
